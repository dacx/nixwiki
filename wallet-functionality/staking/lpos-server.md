---
description: Cómo configurar su propio servidor LPoS.
---

# Servidor LPoS

## **Cómo configurar su propio servidor LPoS.**

**Este artículo asumirá que está utilizando un servidor privado virtual de Linux de 64 bits.**

{% hint style="info" %}
**AVISO:** si está utilizando un servidor basado en Windows, las versiones .zip contienen nixd.exe y nix-cli.exe. Los pasos de configuración seguirán siendo esencialmente los mismos, solo usará comandos y editores de Windows en lugar de los que se usan en Linux aquí.
{% endhint %}

Inicie sesión en su VPS utilizando un cliente Secure Shell \(ssh\) de acuerdo con las instrucciones de su proveedor. [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/) es un cliente ssh popular que es de código abierto y está disponible para Windows y Unix / Linux de forma gratuita.

Si inicia sesión como root, lo primero que querrá hacer es crear un usuario normal. Ejecutar servicios como usuario root generalmente se considera una mala práctica. Puede crear un nuevo usuario con:

```bash
useradd -m NEW_USERNAME_HERE
```

El siguiente comando le permitirá elegir una contraseña para su nuevo nombre de usuario:

```bash
passwd NEW_USERNAME_HERE
```

A continuación, "usuario sustituto" en su nuevo usuario y su directorio de inicio utilizando:

```bash
su - NEW_USERNAME_HERE
```

{% hint style="success" %}
**SUGERENCIA:** Para futuras conexiones ssh, inicie sesión como su usuario normal.
{% endhint %}

Descargue la última versión del software NIX Platform Core con wget:

```bash
wget https://github.com/NixPlatform/NixCore/releases/download/v3.0.5/nix-3.0.5-x86_64-linux-gnu.tar.gz
```

Descomprima el archivo:

```bash
tar -zxvf nix-3.0.5-x86_64-linux-gnu.tar.gz
```

Ahora deberá ser el usuario root para instalar los archivos binarios. Use el comando de usuario sustituto:

```bash
su
```

Después de ingresar su contraseña de root, instale los archivos binarios NIX.

```bash
cp nix-3.0.5/bin/* /usr/bin/
```

Ya no necesita permisos de root, así que vuelva a su usuario normal con:

```bash
exit
```

Ahora que ha vuelto a su usuario normal, inicie el demonio NIX y póngalo en segundo plano.

```bash
nixd&
```

Ahora cree su archivo nix.conf. Esto debe estar en el directorio de datos, que por defecto se crea como un directorio oculto llamado .nix en la página de inicio de los usuarios. Usa el comando:

```bash
nano .nix/nix.conf
```

Para una configuración mínima, agregue las siguientes líneas a nix.conf:

{% code title="nix.conf" %}
```text
daemon=1
minimumleasepercentage=1191
leaserewardaddresses=RewardAddress1,RewardAddress2,etc
```
{% endcode %}

{% hint style="success" %}
**SUGERENCIA:** Su dirección de recompensa se puede generar desde la billetera VPS, pero para las mejores prácticas de seguridad, debe estar en una billetera completamente diferente. De esta manera, nunca hay monedas gastables en su servidor LPoS.
{% endhint %}

Usando la configuración anterior, esta billetera solo apostará contratos con una tarifa no inferior al 11.91% y su \(s\) dirección \(es\) de recompensa especificada \(s\). Para configuraciones más avanzadas, vea las opciones de la [línea de comandos](https://wiki.nixplatform.io/home/v/espanol/advanced-wallet-functions/command-line-options). 

 Salga y guarde el archivo usando 'Ctrl + x', presionando 'y' y presionando &lt;Enter&gt;.

{% hint style="success" %}
**SUGERENCIA:** Si desea utilizar esto para apostar en privado sus propias monedas, simplemente omita las líneas 'minimumleasepercentage =' y 'leaserewardaddresses =' y cree su contrato [de cliente LPoS](https://wiki.nixplatform.io/home/v/espanol/wallet-functionality/staking/lpos-client) sin cargo.
{% endhint %}

Luego, encripte su billetera y elija una frase de contraseña:

```bash
nix-cli encryptwallet YOUR_PASSPHRASE
```

Después del cifrado, nixd se apagará automáticamente. Reinicia el daemon:

```bash
nixd
```

{% hint style="info" %}
**NOTA:** Ahora que tiene 'daemon = 1' en su archivo nix.conf, ya no necesitará agregar y nixd para poner el proceso en segundo plano.
{% endhint %}

Ahora puedes generar una nueva dirección. Esto se utilizará para el campo de dirección "Arrendamiento a:" al crear un contrato de [cliente LPoS](https://wiki.nixplatform.io/home/v/espanol/wallet-functionality/staking/lpos-client). El siguiente comando generará y almacenará una nueva dirección estándar \(que comienza con "N"\) en un archivo de texto llamado LeaseToAddress.txt:

```text
nix-cli getnewaddress >> LeaseToAddress.txt
```

Para crear una dirección Bech32 "nix1" y agregarla a LeaseToAddress.txt, escriba:

```text
nix-cli getnewaddress LPoS-Bech32 bech32 >> LeaseToAddress.txt
```

Si desea ver rápidamente el contenido de LeaseToAddress.txt, use:

```bash
cat LeaseToAddress.txt
```

{% hint style="success" %}
**SUGERENCIA:** Ahora sería un buen momento para descargar sus archivos wallet.dat, nix.conf y LeaseToAddress.txt usando el programa pscp \(copia segura\) de PuTTY para tener una copia de seguridad.
{% endhint %}

Verifique que su billetera esté sincronizada con:

```bash
nix-cli getblockcount
```

..y compare la salida con el número de bloque actual de la red. Si continúa leyendo cero, es probable que necesite un poco de ayuda para encontrar un compañero. Para agregar un nodo manualmente, use:

```bash
nix-cli addnode sf.nixplatform.io add
```

Una vez que haya confirmado que su billetera está sincronizada, desbloquéela para replantearla con:

```text
nix-cli walletpassphrase YOUR_PASSPHRASE 0 true
```

Su billetera VPS ahora está lista para aceptar contratos y comenzar a hacer staking.

Finalmente, elimine su historial de bash para eliminar su frase de contraseña tanto del archivo de historial como de la memoria del sistema. 

```bash
history -c;history -w
```

{% hint style="danger" %}
**Si su billetera VPS contiene monedas gastables, siempre debe ejecutar este comando antes de cerrar sesión cada vez que ingrese su contraseña a través del indicador bash en texto sin formato.**
{% endhint %}

Ahora puede cerrar su conexión ssh.

#### **Un par de otros comandos utiles…**

Para ver su archivo de depuración en tiempo real, use:

```bash
tail -f .nix/debug.log
```

Para detener nixd, use:

```bash
nix-cli stop
```

## **Instalación Automática/Programada**

Alternativamente, también puede usar el siguiente método y utilizar el script de CryptoSharks:

Estas instrucciones ayudarán a guiarlo a configurar su propio stake frío en un VPS. Inicie sesión en el servidor utilizando ssh \(Putty para Windows o terminal para usuarios de Mac\) y ejecute los siguientes comandos:

```text
wget -q https://raw.githubusercontent.com/cryptosharks131/Ghostnode/master/nix_cold_stake.sh
bash nix_cold_stake.sh
nix-cli encryptwallet "create_password_here"
nix-cli getnewaddress
nix-cli walletpassphrase "put_your_password_here" 0 true
```



