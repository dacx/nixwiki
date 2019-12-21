# Restauración

## **Billeteras QT y UI**

 El método de restaurar un archivo wallet.dat Core \(y GUI\) es esencialmente el reverso de la [copia de seguridad manual](https://wiki.nixplatform.io/home/wallet-functionality/backup-and-security-1/wallet-backup#manual-backup). Las ubicaciones predeterminadas para cada sistema operativo se pueden encontrar a continuación.

### Windows

Por defecto, el directorio de datos NIX se creará como C:\Users\\(su nombre de usuario\)\ AppData\roaming \nix\

{% hint style="success" %}
**SUGERENCIA:** Windows oculta la carpeta AppData de manera predeterminada cuando se usa el explorador de archivos gráficos. Para ingresar a la carpeta AppData, puede escribir "%AppData%" en la barra de búsqueda o marcar la casilla "Elementos ocultos" en el menú Ver para mostrar archivos ocultos en la ventana del explorador de archivos y navegar hasta allí.
{% endhint %}

Para restaurar una copia de seguridad del archivo wallet.dat, simplemente cópielo en la siguiente ubicación:

{% hint style="info" %}
**NOTA:** Si existe un directorio de "billeteras", el software lo usará como el directorio de billetera predeterminado. Si no existe, se utilizará el directorio raíz.
{% endhint %}

C:\Users\\(your username\)\AppData\roaming\nix\wallets\wallet.dat

o

C:\Users\\(your username\)\AppData\roaming\nix\wallet.dat

### MacOS

Por defecto, el directorio de datos NIX se creará como ~ /Library/Application Support /nix/

{% hint style="success" %}
**SUGERENCIA:** MacOS oculta la carpeta Soporte de aplicaciones de forma predeterminada.  
1. En la barra superior, en el lado izquierdo de la pantalla, haga clic en "Ir", luego haga clic en "Ir a la carpeta".  
2. Escriba o copie y pegue: ~/Library/Application Support/nix/
{% endhint %}

Para restaurar una copia de seguridad del archivo wallet.dat, simplemente cópielo en la siguiente ubicación:

{% hint style="info" %}
**NOTA:** Si existe un directorio de "billeteras", el software lo usará como el directorio de billetera predeterminado. Si no existe, se utilizará el directorio raíz.
{% endhint %}

~/Library/Application Support/nix/wallets/wallet.dat

o

~/Library/Application Support/nix/wallet.dat

### Linux

Por defecto, el directorio de datos NIX se creará como ~/.nix/

Para restaurar una copia de seguridad del archivo wallet.dat, simplemente cópielo en la siguiente ubicación:

{% hint style="info" %}
**NOTA:** Si existe un directorio de "billeteras", el software lo usará como el directorio de billetera predeterminado. Si no existe, se utilizará el directorio raíz.
{% endhint %}

~/.nix/wallets/wallet.dat

o

~/.nix/wallet.dat

## **Carteras moviles y eléctronicas**

 Simplemente use su lista de palabras guardadas para restaurar sus billeteras móviles y Electrum.

