# Actualizaciones de Billeteras

## Billetera **GUI**

Cuando NIX Core tiene una actualización disponible, la billetera GUI descargará e instalará automáticamente, haciendo que la última versión esté disponible para usar la próxima vez que ejecute su billetera.

 Cuando la GUI tiene una actualización disponible, aparecerá una notificación en la pantalla "Actualizaciones". Estas actualizaciones requieren que el usuario descargue e instale la última versión del [sitio web de NIX](https://wiki.nixplatform.io/home/getting-started/choose-your-wallet/wallet-updates) o directamente desde [GitHub](https://github.com/NixPlatform/Nix-GUI/releases).

## Billetera QT

Descargue la última actualización para su sistema operativo específico a través del [sitio web de NIX](https://nixplatform.io/wallet#download) o directamente desde [GitHub](https://github.com/NixPlatform/NixCore/releases). Para MacOS y Windows, simplemente haga clic en el archivo para comenzar la instalación. Para todos los demás, desempaquete el archivo .tar.gz y copie los archivos binarios del directorio bin/ en la ubicación adecuada para instalarlos para todos los usuarios, o simplemente ejecútelos desde donde los haya desempaquetado si ningún otro usuario necesita acceso.

## VPS Staking y Ghostnodes

Es importante estar al tanto de las actualizaciones de la billetera cuando se opera nixd en un VPS. Las actualizaciones de billetera a menudo son obligatorias, pero generalmente se lanzan con un período de gracia de varios días antes de que el operador deba actualizar.

{% hint style="info" %}
**Importante -** si el bloque especificado no actualiza una billetera, el nodo puede separarse de la cadena más larga y se requerirá una resincronización. En este escenario, cualquier recompensa / tarifa resultante recibida en la cadena bifurcada no tiene valor. 
{% endhint %}

### **Actualización** Manual

Inicie sesión en su VPS y use wget para descargar la última versión:

```bash
wget https://github.com/NixPlatform/NixCore/releases/download/v3.0.5/nix-3.0.5-x86_64-linux-gnu.tar.gz
```

Descomprima el Archivo con:

```bash
tar -zxvf nix-3.0.5-x86_64-linux-gnu.tar.gz
```

As the root user, install the binaries with:

```bash
cp nix-3.0.5/bin/* /usr/bin/
```

### Cryptosharks Easy-Updater

Si utilizó el script de instalación automática de CryptoSharks, necesitará usar su actualizador automático para actualizar su VPS con la última versión. El script de actualización en sí necesita actualizarse, así que espere hasta que esté listo.

 Actualice el script con:

```bash
rm nix_update.sh* wget -q https://raw.githubusercontent.com/cryptosharks131/Ghostnode/master/nix_update.sh 
./nix_update.sh
```

Si se usa para staking, desbloquee con:

```text
nix-cli walletpassphrase YOURWALLETPASSPHRASE 0 true
```

Finalmente, elimine su historial de bash para eliminar su frase de contraseña tanto del archivo de historial como de la memoria del sistema.

```bash
history -c;history -w
```

