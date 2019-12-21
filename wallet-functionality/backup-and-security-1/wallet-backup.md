# Copia de Seguridad de las Billeteras

Tanto para las billeteras QT como para la GUI, el archivo wallet.dat contiene sus claves privadas que otorgan acceso a sus monedas en la cadena de bloques. Si este archivo se corrompe o se pierde, ya no podrá acceder a sus monedas sin restaurar una copia de seguridad válida.

Es mejor almacenar su billetera respaldada. En un lugar que no sea la computadora que usa normalmente para ejecutar su billetera. Las tarjetas SD y las unidades de memoria USB son candidatos ideales.

##  **Frecuencia de Respaldo**

Debido a que todas las billeteras NIX utilizan la generación de claves HD, no necesita hacer una copia de seguridad de su billetera después de generar 100 o 1000 direcciones de recepción. Todas las direcciones de recepción que genera se basan en una única clave privada maestra que le otorgará acceso a todas las direcciones futuras generadas.

Al cifrar su archivo wallet.dat, se genera una nueva clave maestra y se utiliza a partir de ese momento. Esto evita que cualquier persona que pueda obtener acceso a su archivo wallet.dat no cifrado anteriormente obtenga el control de las direcciones que ha generado después del cifrado. Debido a esto, cifrar su billetera requerirá que cree una nueva copia de seguridad de su billetera.dat. También debe eliminar cualquier copia de seguridad creada anteriormente que no esté encriptada.

{% hint style="warning" %}
**AVISO:** Cambiar su contraseña no requerirá una nueva copia de seguridad, pero las copias de seguridad antiguas seguirán utilizando su contraseña respectiva. Por lo tanto, se recomienda encarecidamente que reemplace cualquier copia de seguridad de wallet.dat anterior.
{% endhint %}

{% hint style="success" %}
**SUGERENCIA:** una forma segura de proteger cualquier moneda que aún esté en una dirección de recepción anterior que haya generado antes de cifrar su billetera es enviándosela a usted mismo usando una dirección de recepción recién generada después del cifrado.
{% endhint %}

## Billeteras QT

Puede hacer una copia de seguridad de su archivo wallet.dat desde la aplicación nix-qt en ejecución seleccionando "Backup Wallet..." en el menú Archivo. Luego se le presentará una ventana estándar "Guardar archivo como" donde puede seleccionar una ubicación y un nombre para su archivo de respaldo.

![Seleccione &quot;Backup Wallet...&quot; en el men&#xFA; Archivo.](../../.gitbook/assets/qt-backupmenu.png)

## **Manual y Copia de Seguridad de la Billetera UI**

Puede copiar manualmente su archivo wallet.dat a una nueva ubicación navegando al directorio de datos NIX y haciendo una copia de wallet.dat. La ubicación predeterminada para este archivo está dentro del directorio de billeteras si existe, de lo contrario, el directorio de datos raíz \(nix\).

#### Windows

{% hint style="success" %}
**SUGERENCIA:** Windows oculta la carpeta AppData de manera predeterminada cuando se usa el explorador de archivos gráficos. Para ingresar a la carpeta AppData, puede escribir "% AppData%" en la barra de búsqueda o marcar la casilla "Elementos ocultos" en el menú Ver para mostrar archivos ocultos en la ventana del explorador de archivos y navegar hasta allí.
{% endhint %}

C:\Users\\(your username\)\AppData\roaming\nix\wallets\wallet.dat

o

C:\Users\\(your username\)\AppData\roaming\nix\wallet.dat

#### MacOS

{% hint style="success" %}
 **SUGERENCIA:** MacOS oculta la carpeta Soporte de aplicaciones de forma predeterminada.

1.  En la barra superior, en el lado izquierdo de la pantalla, haga clic en "Ir", luego haga clic en "Ir a la carpeta".
2.  Escriba o copie y pegue: ~ /Library/Application Suppor/nix/
{% endhint %}

~/Library/Application Support/nix/wallets/wallet.dat

o

~/Library/Application Support/nix/wallet.dat

#### Linux

~/.nix/wallets/wallet.dat

o

~/.nix/wallet.dat

## **Billeteras Móviles y Electrónicas**

Estas billeteras usan una frase semilla que se mostrará una vez que abra/cree su billetera por primera vez. Simplemente escriba la lista de palabras y guárdelas en un lugar seguro. Sin estas palabras \(y en el orden correcto\), la recuperación no es posible.

