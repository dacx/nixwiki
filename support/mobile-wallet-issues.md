# Problemas de billetera móvil

## **Los fondos no aparecen**

Si algunos/todos sus fondos no se muestran \(generalmente después de importar/recuperar su frase semilla de un dispositivo antiguo/otro\), es probable que su billetera no esté sincronizada.

**Cosas fáciles de probar primero:**

1. Cierra y vuelve a abrir la aplicación.  
2. Reinicia el dispositivo.  
3. Si usa WiFi, desactívelo e intente usar su conexión de datos móviles.

**Fuerce la billetera para volver a sincronizar:**

1. Menú  
2. Configuraciones  
3. Sincronizar Blockchain  
4. Iniciar sincronización

**Si aún no puede volver a sincronizar correctamente, intente:**

1. Menú  
2. Configuraciones  
3. Avanzado  
4. NIX Nodos  
5. Cambiar al modo manual

Aquí, le pedirá una dirección IP. Una forma fácil de obtener uno es desde un explorador de bloques como https://chainz.cryptoid.info/nix/\#!network. Encuentre un nodo de última versión y haga clic en el botón "lista de nodos". Es posible que deba intentar una nueva sincronización una vez más.

Una vez que se haya sincronizado y haya completado los envíos que desea hacer, es probable que desee volver a la sección Nodos de NIX y volver al modo automático, ya que no hay garantía de que el nodo que agregó manualmente permanecerá en línea para siempre.

## **Cómo importar su frase de semilla móvil en Electrum-NIX**

Si por alguna razón no puede hacer que su billetera móvil funcione correctamente, o si su dispositivo se destruye / pierde / se lo roban y quiere usar los fondos pero aún no tiene otro dispositivo para restaurar, puede importar fácilmente su frase inicial en una billetera de escritorio electrum-nix.

Comience descargando la billetera electrum-nix para su sistema operativo desde el [sitio web de NIX](https://nixplatform.io/wallet) o directamente desde [GitHub](https://github.com/NixPlatform/electrum-nix/releases). Después de instalarlo, ábralo y:

1. Seleccione Archivo, Nuevo / Recuperar \(o pase al \# 2 si acaba de instalar electrum-nix por primera vez\)  
2. Déle un nombre a su billetera \(la billetera móvil podría ser una opción obvia\)  
3. Seleccione "Monedero estándar"  
4. Seleccione "Ya tengo una semilla"  
5. Ingrese sus 12 palabras y luego haga clic en el botón Opciones y seleccione "semilla BIP39"  
6. Seleccione "legado \(p2pkh\)"  
7. Cambie la ruta de derivación a: m / 0 '  
8. Si desea mantener esta billetera instalada, probablemente debería encriptarla cuando se le solicite.

Ahora tendrá acceso a su billetera SPV usando electrum-nix. Desde aquí, puedes enviarlos a donde quieras.

Una vez que haya vaciado su billetera / enviado los fondos que desea enviar, puede conservar la billetera para uso futuro \(se recomienda el cifrado\) o eliminarla usando Archivo, Eliminar.

