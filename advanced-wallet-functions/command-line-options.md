# Opciones de línea de comando

 **Uso:**

 nix-qt \[opciones de línea de comandos\]

 nixd \[opciones de línea de comandos\]

 **o, si corresponde, agregue al archivo nix.conf como:**

 \[opción \(sin -\)\] = \[valor\]

## **Opciones**

 -? Imprima este mensaje de ayuda y salga

 -version Versión de impresión y salir

 -alertnotify = &lt;cmd&gt; Ejecutar comando cuando se recibe una alerta relevante o vemos una bifurcación realmente larga \(% s en cmd se reemplaza por mensaje\)

 -blocknotify = &lt;cmd&gt; Ejecuta el comando cuando cambia el mejor bloque \(% s en cmd se reemplaza por hash de bloque\)

 -assumevalid = &lt;hex&gt; Si este bloque se encuentra en la cadena de asumir que él y sus antepasados ​​son válidos y potencialmente omitir la verificación de la escritura \(de 0 a verificar todo, por defecto: 0000000000000000000000000000000000000000000000000000000000000000, testnet: 0000000000000000000000000000000000000000000000000000000000000000\)

 -conf = &lt;file&gt; Especifica el archivo de configuración \(predeterminado: nix.conf\)

 -datadir = &lt;dir&gt; Especificar directorio de datos

 -dbcache = &lt;n&gt; Establecer el tamaño de caché de la base de datos en megabytes \(4 a 16384, predeterminado: 450\)

 -loadblock = &lt;file&gt; Importa bloques desde un archivo externo blk000 ??. dat al inicio

 -debuglogfile = &lt;file&gt; Especifique la ubicación del archivo de registro de depuración: puede ser una ruta absoluta o una ruta relativa al directorio de datos \(predeterminado: debug.log\)

 -maxorphantx = &lt;n&gt; Mantener como máximo &lt;n&gt; transacciones desconectables en la memoria \(valor predeterminado: 100\)

 -maxmempool = &lt;n&gt; Mantener el grupo de memoria de transacciones por debajo de &lt;n&gt; megabytes \(predeterminado: 300\)

 -mempoolexpiry = &lt;n&gt; No guarde las transacciones en el mempool por más de &lt;n&gt; horas \(predeterminado: 336\)

 -persistmempool Si guardar el mempool al apagar y cargar al reiniciar \(predeterminado: 1\)

 -blockreconstructionextratxn = &lt;n&gt; Transacciones adicionales para mantener en la memoria para reconstrucciones de bloques compactos \(predeterminado: 100\)

 -par = &lt;n&gt; Establece el número de hilos de verificación de script \(-4 a 16, 0 = automático, &lt;0 = deja tantos núcleos libres, por defecto: 0\)

 -pid = &lt;file&gt; Especificar archivo pid \(predeterminado: nixd.pid\)

 -prune = &lt;n&gt; Reduce los requisitos de almacenamiento al habilitar la poda \(eliminación\) de bloques antiguos. Esto permite que se llame al RPC de cadena de bloques de ciruela pasa para eliminar bloques específicos, y permite la poda automática de bloques antiguos si se proporciona un tamaño objetivo en MiB. Este modo es incompatible con -txindex y -rescan. Advertencia: revertir esta configuración requiere volver a descargar toda la cadena de bloques. \(predeterminado: 0 = deshabilitar los bloques de poda, 1 = permitir la poda manual a través de RPC,&gt; 550 = podar automáticamente los archivos de bloques para que se mantengan por debajo del tamaño objetivo especificado en MiB\)

 -reindex-chainstate Reconstruye el estado de la cadena a partir de los bloques indexados actualmente

 -reindex Reconstruir el estado de la cadena y bloquear el índice de los archivos blk \* .dat en el disco

 -sysperms Crear nuevos archivos con permisos predeterminados del sistema, en lugar de umask 077 \(solo efectivo con la funcionalidad de billetera deshabilitada\)

 -txindex Mantener un índice de transacción completo, utilizado por la llamada getrawtransaction rpc \(valor predeterminado: 1\)

 -addressindex Mantiene un índice de dirección completo, utilizado para consultar el saldo, txids y salidas no gastadas para direcciones \(valor predeterminado: 0\)

 -timestampindex Mantiene un índice de marca de tiempo para hashes de bloque, utilizado para consultar hashes de bloques por un rango de marcas de tiempo \(valor predeterminado: 0\)

 -spentindex Mantener un índice de gasto completo, utilizado para consultar el txid de gasto y el índice de entrada para un punto de salida \(predeterminado: 0\)

## **Opciones de conexión**

 -addnode = &lt;ip&gt; Agregue un nodo para conectarse e intente mantener la conexión abierta \(consulte la ayuda del comando 'addnode' RPC para obtener más información\)

 -banscore = &lt;n&gt; Umbral para desconectar pares que se portan mal \(predeterminado: 100\)

 -bantime = &lt;n&gt; Número de segundos para evitar que los compañeros que se portan mal se vuelvan a conectar \(valor predeterminado: 86400\)

 -bind = &lt;addr&gt; Enlazar a la dirección dada y siempre escucharla. Utilice \[host\]: notación de puerto para IPv6

 -connect = &lt;ip&gt; Conéctese solo a los nodos especificados; -connect = 0 deshabilita las conexiones automáticas \(las reglas para este par son las mismas que para -addnode\)-discover Discover own IP addresses \(default: 1 when listening and no -externalip or -proxy\)

 -dns Permitir búsquedas de DNS para -addnode, -seednode y -connect \(predeterminado: 1\)

 -dnsseed Consulta de direcciones de pares a través de la búsqueda de DNS, si las direcciones son bajas \(valor predeterminado: 1 a menos que se use -connect\)

 -externalip = &lt;ip&gt; Especifique su propia dirección pública

 -forcednsseed Siempre consulta las direcciones de pares a través de la búsqueda de DNS \(predeterminado: 0\)

 -listen Acepta conexiones desde el exterior \(predeterminado: 1 si no -proxy o -connect\)

 -listenonion Crea automáticamente el servicio oculto Tor \(predeterminado: 1\)

 -maxconnections = &lt;n&gt; Mantener como máximo &lt;n&gt; conexiones a pares \(valor predeterminado: 125\)

 -maxreceivebuffer = &lt;n&gt; Buffer de recepción máximo por conexión, &lt;n&gt; \* 1000 bytes \(predeterminado: 5000\)

 -maxsendbuffer = &lt;n&gt; Buffer de envío máximo por conexión, &lt;n&gt; \* 1000 bytes \(predeterminado: 1000\)

 -adjust maxtime Ajuste de compensación de tiempo medio entre pares máximo permitido. La perspectiva local del tiempo puede verse influenciada por pares hacia adelante o hacia atrás por esta cantidad. \(predeterminado: 4200 segundos\)

 -onion = &lt;ip: port&gt; Use un proxy SOCKS5 separado para llegar a sus pares a través de los servicios ocultos de Tor \(predeterminado: -proxy\)

 -onlynet = &lt;net&gt; Solo conéctate a los nodos en la red &lt;net&gt; \(ipv4, ipv6 o cebolla\)

 -mitmitbaremultisig Relay multisig no P2SH \(predeterminado: 1\)

 -peerbloomfilters Soporta el filtrado de bloques y transacciones con filtros bloom \(predeterminado: 1\)

 -port = &lt;port&gt; Escucha las conexiones en &lt;port&gt; \(predeterminado: 6214 o testnet: 16214\)

 -proxy = &lt;ip: puerto&gt; Conectarse a través del proxy SOCKS5

 -proxyrandomize Aleatoriza las credenciales para cada conexión proxy. Esto permite el aislamiento de la corriente Tor \(predeterminado: 1\)

 -seednode = &lt;ip&gt; Conéctese a un nodo para recuperar direcciones de pares y desconecte

 -timeout = &lt;n&gt; Especifique el tiempo de espera de conexión en milisegundos \(mínimo: 1, predeterminado: 5000\)

 -torcontrol = &lt;ip&gt;: &lt;port&gt; Puerto de control Tor para usar si la escucha de cebolla está habilitada \(por defecto: 127.0.0.1:9051\)

 -torpassword = &lt;pass&gt; Contraseña del puerto de control Tor \(predeterminado: vacío\)

 -upnp Use UPnP para asignar el puerto de escucha \(predeterminado: 0\)

 -whitebind = &lt;addr&gt; Se une a la dirección dada y los pares de la lista blanca que se conectan a ella. Utilice \[host\]: notación de puerto para IPv6

 -whitelist = &lt;dirección IP o red&gt; La lista blanca se conecta desde la dirección IP dada \(por ejemplo, 1.2.3.4\) o la red con notación CIDR \(por ejemplo, 1.2.3.0/24\). Se puede especificar varias veces. Los pares de la lista blanca no se pueden prohibir DoS y sus transacciones siempre se transmiten, incluso si ya están en el mempool, útil p. para una puerta de enlace

 -maxuploadtarget = &lt;n&gt; Intenta mantener el tráfico saliente por debajo del objetivo dado \(en MiB por 24 h\), 0 = sin límite \(predeterminado: 0\)

## **Opciones de billetera**

 -addresstype Qué tipo de direcciones usar \("legacy", "p2sh-segwit" o "bech32", por defecto: "p2sh-segwit"\)

 -changetype Qué tipo de cambio usar \("legacy", "p2sh-segwit" o "bech32"\). El valor predeterminado es el mismo que -addresstype, excepto cuando -addresstype = p2sh-segwit se utiliza una salida de segwit nativa cuando se envía a una dirección de segwit nativa\)

 -disablewallet No cargue la billetera y deshabilite las llamadas RPC de la billetera

 -keypool = &lt;n&gt; Establecer el tamaño del grupo de claves en &lt;n&gt; \(predeterminado: 1000\)

 -fallbackfee = &lt;amt&gt; Una tasa de tarifa \(en NIX / kB\) que se usará cuando la estimación de tarifa tenga datos insuficientes \(valor predeterminado: 0.0002\)

 -discardfee = &lt;amt&gt; La tarifa \(en NIX / kB\) que indica su tolerancia para descartar el cambio al agregarlo a la tarifa \(valor predeterminado: 0.0001\). Nota: Una salida se descarta si es polvo a esta velocidad, pero siempre descartamos hasta la tarifa de retransmisión de polvo y una tarifa de descarte superior que está limitada por la estimación de tarifa para el objetivo más largo

 -mintxfee = &lt;amt&gt; Las tarifas \(en NIX / kB\) más pequeñas que esta se consideran tarifa cero para la creación de transacciones \(valor predeterminado: 0.00001\)

 -paytxfee = &lt;amt&gt; Tarifa \(en NIX / kB\) para agregar a las transacciones que envía \(valor predeterminado: 0.00\)

 -rescan Volver a analizar la cadena de bloques para las transacciones de billetera que faltan en el inicio

 -salvagewallet Intenta recuperar claves privadas de una billetera corrupta en el inicio

 -spendzeroconfchange Pasa cambios no confirmados al enviar transacciones \(valor predeterminado: 1\)

 -txconfirmtarget = &lt;n&gt; Si paytxfee no está configurado, incluya una tarifa suficiente para que las transacciones comiencen la confirmación en promedio dentro de n bloques \(valor predeterminado: 6\)

 -walletrbf Envía transacciones con la opción de suscripción completa a RBF habilitada \(solo RPC, predeterminado: 0\)

 -upgradewallet Actualiza la billetera al último formato al inicio

 -wallet = &lt;file&gt; Especifica el archivo de billetera \(dentro del directorio de datos\) \(predeterminado: wallet.dat\)

 -walletbroadcast Realiza las transacciones de difusión de la billetera \(valor predeterminado: 1\)

 -walletdir = &lt;dir&gt; Especifica el directorio para guardar billeteras \(predeterminado: &lt;datadir&gt; / wallets si existe, de lo contrario &lt;datadir&gt;\)

 -walletnotify = &lt;cmd&gt; Ejecutar comando cuando cambia una transacción de billetera \(% s en cmd se reemplaza por TxID\)

 -zapwallettxes = &lt;mode&gt; Eliminar todas las transacciones de billetera y solo recuperar esas partes de la cadena de bloques a través de -rescan al inicio \(1 = mantener metadatos tx, por ejemplo, titular de la cuenta e información de solicitud de pago, 2 = soltar metadatos tx\)

## **Opciones de replanteo de billetera**

 Apuesta tus monedas para apoyar la red y obtener recompensas \(predeterminado: verdadero\)

 -stakingthreads Número de subprocesos para iniciar el replanteo, máximo 1 por billetera activa, dividirá las billeteras de manera uniforme entre los subprocesos \(predeterminado: 1\)

 -minstakeinterval = &lt;n&gt; Tiempo mínimo en segundos entre apuestas exitosas \(predeterminado: 0\)

 -minersleep = &lt;n&gt; Milisegundos entre intentos de estaca. Bajar este parámetro no dará como resultado más apuestas. \(predeterminado: 500\)

 -reservebalance = &lt;amount&gt; Asegúrese de que el saldo disponible permanezca por encima del balance de reserva. \(predeterminado: 0\)

 -donationpercent = &lt;n&gt; Porcentaje de recompensa en bloque donada a la dirección de donación. p.ej. 1190 \(11.90%\) \(predeterminado: 0\)

 -donationaddress = &lt;n&gt; Destino para enviar recompensas de apuesta donadas. \(predeterminado: N / A\)

 -stakesplitthreshold = &lt;n&gt; Cantidad máxima de monedas para apostar antes de dividirse en dos salidas. \(predeterminado: 10000\)

 -stakecombinethreshold = &lt;n&gt; Cantidad mínima de NIX para combinar en una apuesta si la billetera tiene múltiples salidas para apostar. \(predeterminado: 5000\)

 -maxstakecombine=&lt;n&gt; Máximo de resultados para combinar al alcanzar el umbral de combinación de estaca. \(predeterminado: 3\)

 -generatenewstakingaddress Crea nuevas direcciones bech32 en apuestas exitosas. \(predeterminado: falso\)

 -minimumleasepercentage = &lt;n&gt; Porcentaje mínimo de arrendamiento requerido para que un contrato apueste si está alquilando participaciones. El valor puede estar entre 0 y 10000, p. 1191 \(11.91%\) \(predeterminado: 0\)

 -leaserewardaddresses = &lt;n&gt; Apuesta solo contratos LPoS con direcciones de tarifa de recompensa especificadas por este comando. p.ej. x1, x2, x3 \(predeterminado: ""\)

 -leaserewardtome = &lt;n&gt; Apuesta solo contratos LPoS con direcciones de tarifa de recompensa que posee esta billetera local &lt;verdadero / falso&gt; \(predeterminado: falso\)

 -dxmode Establece el cambio de billetera y el direccionamiento predeterminado en heredado para el soporte de dx de terceros \(predeterminado: falso\)

## **Opciones de notificación de ZeroMQ**

 -zmqpubhashblock = &lt;dirección&gt; Habilitar el bloque de hash de publicación en &lt;dirección&gt;

 -zmqpubhashtx = &lt;dirección&gt; Habilitar la transacción de publicación de hash en &lt;dirección&gt;

 -zmqpubrawblock = &lt;dirección&gt; Habilitar la publicación del bloque sin procesar en &lt;dirección&gt;

 -zmqpubrawtx = &lt;dirección&gt; Habilitar la publicación de la transacción sin procesar en &lt;dirección&gt;

## **Opciones de depuración / prueba**

 -uacomment = &lt;cmt&gt; Añadir comentario a la cadena del agente de usuario

 -debug = &lt;categoría&gt; Información de depuración de salida \(valor predeterminado: 0, el suministro de &lt;categoría&gt; es opcional\). Si no se proporciona &lt;categoría&gt; o si &lt;categoría&gt; = 1, genera toda la información de depuración. &lt;categoría&gt; puede ser: net, tor, mempool, http, bench, zmq, db, rpc, Estimatefee, addrman, selectcoins, reindex, cmpctblock, rand, podar, proxy, mempoolrej, libevent, coindb, qt, leveldb.

 -debugexclude = &lt;categoría&gt; Excluir información de depuración para una categoría. Se puede usar junto con -debug = 1 para generar registros de depuración para todas las categorías, excepto una o más categorías especificadas.

 -help-debug Muestra todas las opciones de depuración \(uso: --help -help-debug\)

 -logips Incluye direcciones IP en la salida de depuración \(predeterminado: 0\)

 -logtimestamps Anteponer salida de depuración con marca de tiempo \(predeterminado: 1\)

 -maxtxfee = &lt;amt&gt; Tarifas totales máximas \(en NIX\) para usar en una sola transacción de billetera o transacción sin procesar; establecer esto demasiado bajo puede anular grandes transacciones \(por defecto: 0.10\)

 -printtoconsole Enviar información de rastreo / depuración a la consola en lugar del archivo debug.log

 -shrinkdebugfile Reduce el archivo debug.log al iniciar el cliente \(predeterminado: 1 cuando no hay -debug\)

##  **Opciones de selección de cadena**

 -testnet Usa la cadena de prueba

##  **Opciones de relé de nodo**

 -bytespersigop Bytes equivalentes por sigop en transacciones para retransmisión y minería \(predeterminado: 20\)

 -Retransportador de datos y transacciones de portador de datos de mina \(predeterminado: 1\)

 -datacarriersize Tamaño máximo de datos en transacciones de soporte de datos que transmitimos y extraemos \(predeterminado: 83\)

 -mempoolreplacement Habilita la sustitución de transacciones en el grupo de memoria \(predeterminado: 1\)

 -minrelaytxfee = &lt;amt&gt; Las tarifas \(en NIX / kB\) más pequeñas que esta se consideran tarifa cero para retransmisión, minería y creación de transacciones \(valor predeterminado: 0.00001\)

 -whitelistrelay Acepta transacciones retransmitidas recibidas de pares de la lista blanca incluso cuando no se retransmiten transacciones \(valor predeterminado: 1\)

 -whitelistforcerelay Fuerza la retransmisión de transacciones de pares de la lista blanca incluso si violan la política de retransmisión local \(valor predeterminado: 1\)

##  **Opciones de creación de bloque**

 -blockmaxweight = &lt;n&gt; Establecer el peso máximo de bloque BIP141 \(predeterminado: 3996000\)

 -blockmaxsize = &lt;n&gt; Establezca el peso máximo de bloque BIP141 en esto \* 4. En desuso, use blockmaxweight

 -blockmintxfee = &lt;amt&gt; Establece la tarifa más baja \(en NIX / kB\) para que las transacciones se incluyan en la creación de bloques. \(predeterminado: 0.00001\)

##  **Opciones de servidor RPC**

 -server Aceptar línea de comandos y comandos JSON-RPC

 -rest Acepta solicitudes REST públicas \(predeterminado: 0\)

 -rpcbind = &lt;addr&gt; \[: puerto\] Enlace a la dirección dada para escuchar las conexiones JSON-RPC. Esta opción se ignora a menos que también se pase

 -rpcallowip. El puerto es opcional y anula -rpcport. Utilice \[host\]: notación de puerto para IPv6. Esta opción se puede especificar varias veces \(valor predeterminado: 127.0.0.1 y :: 1, es decir, localhost, o si -rpcallowip ha sido especificado, 0.0.0.0 and :: i.e., all addresses\)

 -rpccookiefile = &lt;loc&gt; Ubicación de la cookie de autenticación \(predeterminado: directorio de datos\)

 -rpcuser = &lt;usuario&gt; Nombre de usuario para conexiones JSON-RPC

 -rpcpassword = &lt;pw&gt; Contraseña para conexiones JSON-RPC

 -rpcauth = &lt;userpw&gt; Nombre de usuario y contraseña hash para conexiones JSON-RPC. El campo &lt;userpw&gt; viene en el formato: &lt;USERNAME&gt;: &lt;SALT&gt; $ &lt;HASH&gt;. Se incluye un script canónico de python en share / rpcuser. El cliente se conecta normalmente utilizando el par de argumentos rpcuser = &lt;USERNAME&gt; / rpcpassword = &lt;PASSWORD&gt;. Esta opción se puede especificar varias veces

 -rpcport = &lt;port&gt; Escuche las conexiones JSON-RPC en &lt;puerto&gt; \(predeterminado: 6215 o testnet: 16215\)

 -rpcallowip = &lt;ip&gt; Permitir conexiones JSON-RPC desde la fuente especificada. Válidos para &lt;ip&gt; son una sola IP \(por ejemplo, 1.2.3.4\), una red / máscara de red \(por ejemplo, 1.2.3.4/255.255.255.0\) o una red / CIDR \(por ejemplo, 1.2.3.4/24\). Esta opción se puede especificar varias veces

 -rpcserialversion Establece la serialización de la transacción sin procesar o el bloque hexadecimal devuelto en modo no detallado, no segwit \(0\) o segwit \(1\) \(predeterminado: 1\)

 -rpcthreads = &lt;n&gt; Establece el número de subprocesos para atender llamadas RPC \(predeterminado: 4\)

##  **Opciones de IU**

 -choosedatadir Elegir directorio de datos al inicio \(predeterminado: 0\)

 -lang = &lt;lang&gt; Establecer idioma, por ejemplo "de\_DE" \(predeterminado: configuración regional del sistema\)

 -min Inicio minimizado

 -rootcertificates = &lt;file&gt; Establecer certificados raíz SSL para solicitud de pago \(predeterminado: -sistema-\)

 -splash Mostrar pantalla de inicio al inicio \(predeterminado: 1\)

 -resetguisettings Restablecer todas las configuraciones modificadas en la GUI

