# Preguntas frecuentes

## **Cómo solucionar problemas de replanteo en QT Wallet**

Para habilitar el replanteo, [encripte su billetera](https://wiki.nixplatform.io/home/v/espanol/wallet-functionality/backup-and-security-1/qt-wallet-encryption) y presione Desbloquear para replantear en Configuración. Debería ver Replanteo: con "habilitado" en verde. Para verificar aún más que está jugando, vaya a la consola y escriba: getstakinginfo y presione enter. Debería ver un "1" junto al replanteo.

Si ve monedas en su saldo disponible pero no junto a "estacado" en la pestaña de resumen, es posible que haya alcanzado una apuesta o que haya enviado recientemente una transacción. Si el replanteo está habilitado, puede consultar la pestaña de transacciones y hacer clic en las transacciones más recientes y ver cuántas confirmaciones tienen. Sus monedas volverán a aparecer después de 200 confirmaciones. Si te encuentras con un bloque huérfano o alguien encuentra la misma apuesta justo antes que tú, es probable que veas un "?" junto a la transacción en la pestaña de transacciones. La billetera abandonará automáticamente estas transacciones por usted y devolverá esas monedas a su monto apostado.

También recuerde que solo las direcciones N y nix1 pueden apostar. Entonces, si está ejecutando un nodo fantasma, deberá enviar manualmente esas monedas desde la dirección "G" a una dirección "N" y esperar las 200 confirmaciones. Puede mover sus monedas o verificar en qué direcciones están sus monedas a través del control de monedas. Para habilitar el control de monedas. Configuración&gt; Opciones&gt; pestaña Billetera&gt; marque Activar control de monedas.

Siempre puede verificar el canal \#info-bot en discord escribiendo “!staking 1000” o cualquier cantidad. Solo recuerde que esto es solo una estimación y los tiempos pueden fluctuar enormemente ya que el bot no tiene en cuenta la antigüedad de la moneda ni las confirmaciones.

## **Cómo solucionar problemas de sincronización de billetera**

### **Windows: \(siempre haga una copia de seguridad de wallet.dat primero para estar seguro\)**

1. Asegúrese de estar en la última billetera verificando la versión: ayuda&gt; sobre nix core. Compare esto con la versión github o nixplatform.io en la página de billeteras.

2. Si está utilizando la última billetera, cierre la billetera y en la barra de búsqueda del menú de inicio de Windows escriba:% appdata%. Si la carpeta NIX no aparece, haga clic en el icono de la carpeta en la barra de tareas inferior de Windows&gt; presione Ver&gt; y asegúrese de que los elementos ocultos estén marcados

3. Una vez que encuentre la carpeta NIX en appdata: elimine la carpeta chainstate, la carpeta de bloques, banlist.dat y peers.dat. Luego reinicie la billetera y vea si se sincroniza. 

## **Cómo agregar nodos si la billetera aún no se sincroniza después de la descarga**

1. Vaya a Ayuda&gt; Ventana de depuración

2. Haga clic en: "Consola"

3. En la "barra de búsqueda", ingrese el texto a continuación, \(copie y pegue exactamente como está escrito\) después de copiar y pegar, presione "Entrar": addnode ny.nixplatform.io add

4. En la "barra de búsqueda" ingrese el texto a continuación, \(copie y pegue exactamente como está escrito\) después de copiar y pegar presione "Enter": addnode sf.nixplatform.io add

## **Cómo importar su archivo wallet.dat**

### **Windows**

1. Comience cerrando su billetera  
2. Abra un explorador de archivos y en el cuadro de ruta de archivo  
3. Escriba o copie y pegue:% appdata% \ nix \ wallets  
4. Extraiga / saque el wallet.dat actual en la carpeta NIX \(colóquelo en un lugar seguro si desea guardarlo, de lo contrario puede eliminarlo. Solo elimínelo si no hay monedas vinculadas a este wallet.dat\).  
5. Importe / inserte el archivo wallet.dat en la carpeta NIX.  
6. Abra / reinicie su billetera.  
7. NO COMPARTA SU billetera.dat CON NADIE. CONTIENE SUS CLAVES PRIVADAS.

### **Mac OS**

1. Comience cerrando su billetera.  
****2. En la barra superior, lado izquierdo, de su pantalla, haga clic en "Ir". Luego haga clic en "Ir a la carpeta"  
3. Escriba o copie y pegue: ~ / Library / Application Support / nix /  
4. Exporte / extraiga el wallet.dat actual en la carpeta NIX \(colóquelo en un lugar seguro si desea guardarlo, si no puede eliminarlo. Solo elimínelo si no hay monedas vinculadas a este wallet.dat\).  
5. Importe / inserte el archivo wallet.dat en la carpeta NIX.  
6. Abra / reinicie su billetera.  
7. NO COMPARTA SU billetera.dat con NADIE. CONTIENE SUS CLAVES PRIVADAS.

###  **Linux**

1. Comience cerrando su billetera.  
2. Abra un explorador de archivos y en el cuadro de ruta de archivo.  
3. Escriba o copie y pegue: $ HOME / .nix / wallets.  
4. Extraiga / saque el wallet.dat actual en la carpeta NIX \(colóquelo en un lugar seguro si desea guardarlo, de lo contrario puede eliminarlo. Solo elimínelo si no hay monedas vinculadas a este wallet.dat\).  
5. Importe / inserte el archivo wallet.dat en la carpeta NIX.  
6. Abra / reinicie su billetera.  
7. NO COMPARTA SU billetera.dat CON NADIE. CONTIENE SUS CLAVES PRIVADAS.

## **Cómo obtener tus claves privadas**

Si su billetera NIX está encriptada, para obtener su clave privada para una determinada dirección NIX, siga los pasos: \(si su billetera no está encriptada ignore el paso 3\) \(No ingrese el "" en ninguno de los pasos, son usado para mostrar la entrada\).

1. Vaya a: Ayuda&gt; "Ventana de depuración"  
2. Haga clic en: "Consola"  
3. En la "barra de búsqueda", ingrese: walletpassphrase "Frase de contraseña para su billetera NIX" "60" - "Frase de contraseña para su billetera NIX" = Frase de contraseña que ingresó para cifrar su billetera. - "60" = los segundos que quieres desbloquear.  
4. En la misma "barra de búsqueda", ingrese: dumpprivkey "Dirección NIX" - "Dirección NIX" = dirección a la que desea acceder a la clave privada.

NO COMPARTA SUS CLAVES PRIVADAS CON NADIE

## **Qué hacer si su transacción no se envía**

Asegúrate de estar usando la billetera más actualizada. Si no lo está, actualice y esto debería solucionarlo. Si tiene la última billetera y todavía no se enviará. Vaya a Ayuda&gt; Ventana de depuración&gt; Consola&gt; escriba: resendwallettransactions y luego presione Entrar.

## **Qué hacer si faltan sus monedas después de actualizar su billetera**

Una vez que la billetera esté completamente sincronizada, haga clic en la pestaña de transacciones. Busque cualquier transacción que tenga un "?" a su lado Si ve algún clic derecho y seleccione abandonar. Deberían aparecer de nuevo. A veces tus monedas pueden faltar porque alcanzas una recompensa de apuesta. Aparecerán automáticamente una copia de seguridad después de 200 confirmaciones. 

## **Cómo verificar la cantidad en las confirmaciones en un TX**

En la pestaña de transacciones, simplemente haga clic en la transacción y se mostrará la cantidad de confirmaciones.

## **Cómo verificar y actualizar Ghostnode y solución de problemas**

Inicie sesión en vps a través de putty \(windows\) o terminal \(unix\) y ejecute estos comandos:

`nix-cli getnetworkinfo` verifique la versión vps cerca de la parte superior \(debe coincidir con Nix Core: 3.0.7\) Si no coincide y usó el instalador automático de cryptosharks \(lo más probable\) necesita usar su actualizador automático aquí: https: //github.com/cryptosharks131/Ghostnode\#updating: pegue las 3 líneas y presione Enter.

`nix-cli getblockchaininfo` verifique la altura del bloque vps cerca de la parte superior \(debe coincidir con https://blockchain.nixplatform.io/\) Si no coincide, entonces debe seguir el bootstrap de dacx fijado en \# billeteras en discordia. Primero detenga el servicio NIX pegando en el vps: systemctl stop NIX Para obtener los archivos de arranque en su VPS, puede usar algo como FileZilla desde su máquina local. Instale pero desmarque el bloatware en la instalación, no los necesita. Inicie sesión en su vps a través de FileZilla usando las mismas credenciales que putty / terminal en la sección de conexión rápida y use el Puerto 22. Navegue a la carpeta nix y elimine los elementos en la guía de arranque de dacx. Descomprima los archivos que descargó en el enlace de la guía y arrástrelos a la carpeta Nix en la sesión de Filezilla. Ahora regrese a putty / terminal e inicie el servicio nuevamente con systemctl start NIX. Verifique la altura en masilla / terminal nuevamente contra la altura del explorador de bloques con nix-cli getblockchaininfo Si eso se verifica y coincide, está listo para comenzar. Cierre y vuelva a abrir su billetera local, vaya a ghostnodes&gt; iniciar todo. Deben pasar a PREHABILITADO y pasar a HABILITADO en 20 minutos más o menos.

PD: mientras está conectado a VPS a través de masilla / terminal, lo mejor es actualizar los paquetes del servidor. pegue este comando para actualizar / actualizar: apt-get update && apt-get upgrade.



