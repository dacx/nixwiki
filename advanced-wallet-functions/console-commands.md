# Comandos de Consola

Esta es una lista de todos los comandos disponibles en NIX Core, utilizables en la consola de depuración de billetera nix-qt y la interfaz de línea de comandos nix-cli.

## **NIX Ghostnode**

getpoolinfo Devuelve un objeto que contiene información relacionada con el pool de mezcla.

ghostnode "command"... Conjunto de comandos para ejecutar acciones relacionadas con ghostnode.  
  
**Argumentos:**

1.  "command" \(cadena o conjuntos de cadena, requerido\) El comando a ejecutar.

**Comandos disponibles:**  
		@page { size: 8.5in 11in; margin: 0.79in }  
		p { margin-bottom: 0.1in; direction: ltr; line-height: 115%; text-align: left; orphans: 2; widows: 2; background: transparent }  
		a:link { color: \#0563c1; text-decoration: underline }  
		a:visited { color: \#800000; so-language: zxx; text-decoration: underline }  
	

*  count: Imprime el número de todos los nodos fantasmas conocidos \(opcional: 'ps', 'habilitado', 'todos', califique '\)
*  current: Imprima información sobre el ganador actual de Ghosthost para recibir el siguiente bloque \(calculado localmente\)
*  debug: Imprimir estado de nodo fantasma
*  genkey: Generar nueva clave fantasma outputs Imprime salidas compatibles con Ghosthost
*  start: Inicie el Hot Ghosthost local configurado en nix.conf
*  start alias: Inicie un solo ghostnode remoto mediante un alias asignado configurado en ghostnode.conf
*  start-&lt;mode&gt; :Iniciar ghostnodes remotos configurados en ghostnode.conf \(&lt;mode&gt;: 'all', 'missing', 'disabled'\)
*  status: Imprimir información de estado del nodo fantasma
*  list: Imprima la lista de todos los nodos fantasmas conocidos \(consulte la lista de fantasmas para obtener más información\)
*  list-conf: Imprima ghostnode.conf en formato JSON
*  winner: Imprima información sobre el próximo ganador del fantasma para votar
*  winners: Imprimir lista de ganadores de Ghosthost

 ghostnodebroadcast "command"...: Conjunto de comandos para crear y transmitir mensajes de difusión de ghostnode

 **Argumentos:**

 1. "command" \(cadena o conjunto de cadenas, requerido\) El comando para ejecutar

 **Comandos disponibles:**

*  create-alias: crea un único mensaje de difusión remoto de ghostnode mediante el alias asignado configurado en ghostnode.conf
*  create-all: crea mensajes de difusión de nodos fantasmas remotos para todos los nodos fantasmas configurados en ghostnode.conf
*  decode: Decodifica el mensaje de difusión del fantasma
*  relay: retransmitir mensaje de difusión del nodo fantasma a la red

 ghostnodebroadcast "command"...: Conjunto de comandos para crear y retransmitir mensajes de difusión ghostnode.

 **Argumentos:**

1.  "command"\(cadena o conjunto de cadenas, requerido\) El comando para ejecutar.

 **Comandos disponibles:**

*  ghostnodelist \("mode" "filter"\): Obtenga una lista de nodos fantasmas en diferentes modos

 **Argumentos:**

 1. "mode" \(cadena, opcional / requerido para usar filtro, predeterminado = estado\) El modo para ejecutar la lista en

 2. "filter" \(cadena, opcional\) Filtrar resultados. Coincidencia parcial por punto por defecto en todos los modos, también se encuentran disponibles coincidencias adicionales en algunos modos

 **Modos disponibles:**

*  activeseconds: número de segundos de rint ghostnode reconocido por la red como habilitado \(desde el último "ghostnode start / start-many / start-alias"\)
*  addr: Imprima la dirección IP asociada con un nodo fantasma \(se puede filtrar adicionalmente, coincidencia parcial\)
*  full: último pago último lastpaidblock IP' \(se puede filtrar adicionalmente, coincidencia parcial\)
*  lastpaidblock: Imprima la última altura de bloque que se pagó un nodo en la red
*  lastpaidtime: Imprima la última vez que se pagó un nodo en la red
*  lastseen: Imprima la marca de tiempo de cuándo se vio por última vez un nodo fantasma en la red
*  payee: Imprima la dirección NIX asociada con un nodo fantasma \(puede ser adicionalmente filtrado, coincidencia parcial\)
*  protocol: Protocolo de impresión de un nodo fantasma \(se puede filtrar adicionalmente, coincidencia exacta\)
*  rank: Imprimir rango de un fantasma basado en el bloque actual
*  quialify: Imprimir el estado calificado de un nodo fantasma basado en el bloque actual
*  status: imprimir el status del ghostnode: PRE\_ENABLED / ENABLED / EXPIRED / WATCHDOG\_EXPIRED / NEW\_START\_REQUIRED / UPDATE\_REQUIRED / POSE\_BAN / OUTPOINT\_SPENT \(puede filtrarse adicionalmente , coincidencia parcial
*  create-alias: Crear un único mensaje de difusión remoto de ghostnode mediante el alias asignado configurado en ghostnode.conf
*  create-all: Cree mensajes de difusión remotos ghostnode para todos los ghostnodes configurados en ghostnode.conf
*  decode: Decodificar mensaje de difusión del fantasma
*  relay: Retransmitir mensaje de difusión de fantasma a la red

 ghostsync \[status\|next\|reset\]: Devuelve el estado de sincronización, actualiza el siguiente paso o lo restablece por completo

## **Gobernanza NIX**

eraseallgoventires: Borra todas las entradas de votación de la base de datos de billetera para la billetera local actual. Requiere que la frase de contraseña de billetera se configure con la llamada de frase de contraseña de billetera  
  
Getaddressvoteweight: Devuelve el peso del voto para una dirección \(requiere que el índice de dirección esté habilitado\)

 **Argumentos:**

 {

 "addresses"

 \[

 "address" \(cadena\) La dirección codificada base58check

 , ...

 \]

 "start" \(número\) Hora de inicio del período de ponderación de votos

 "end" \(número\) Hora de finalización del período de ponderación de votos

 }

 **Resultado:**

 \[

 {

 "voteweight" \(número\) El peso del voto de la dirección

 }

 \]

 **Ejemplos:**

 &gt; nix-cli getaddressvoteweight '{"addresses":

 \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\], "inicio": 10, "fin": 20}'

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getaddressvoteweight", "params": \[' {"addresses": \[" NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg "\]} '\]}' -H 'type content: text / plain;' [http://127.0.0.1:8332/](http://127.0.0.1:8332/)

*  Getoffchainproposals: Devuelve una lista de todas las propuestas
*  Getproposaltimeframeinfo: Devuelve el peso total que puede tener una propuesta en un período de tiempo determinado

 **Argumentos:**

 {

 "start" \(número\) Hora de inicio del período de ponderación de votos

 "end" \(número\) Hora de finalización del período de ponderación de votos

 }

 **Resultado:**

 \[

 {

 "total\_possible\_votes" \(número\) El peso total posible del período de tiempo

 }

 \]

 **Ejemplos:**

 &gt; nix-cli getproposaltimeframeinfo '{"inicio": 1559229685, "fin": 1569229685}'

*  getvoteweight start\_time end\_time: Requiere que la frase de contraseña de billetera se configure con la llamada de frase de contraseña de billetera

 **Argumentos:**

1.  "start\_time" \(int, obligatorio\) El tiempo de inicio \(unix\) para el cálculo del peso.
2.  "end\_time" \(int, requerido\) El tiempo de finalización \(unix\) para el cálculo del peso.

## **Privacidad NIX**

 decryptallzerocoins: Descifrar todos los datos cifrados de cero monedas

*  enabletor &lt;enable&gt;: \(false / true\) Para habilitar la ofuscación, establezca enable "true". Reinicie el Domain NIX para actualizar sus cambios.
*  encryptallzerocoins: Cifra todos los datos de cero monedas
*  eraseunusedzerocoindata: Borra metadatos zerocoin de zerocoins gastados
*  getzerocoinacc, getpubcoinpack amount \(default=10\): resultado un paquete de claves de compromiso
*  getpubcoinpackv2 amount \(default = 10\): da como resultado un paquete de claves de compromiso
*  getsigmaseed: Vuelca la semilla sigma determinada para todas las monedas sigma. Requiere que la frase de contraseña de billetera se configure.

 **Resultado:**

 "seed": s, \(cadena\) La semilla determinista zPIV.

 **Ejemplos:**

 &gt; nix-cli getsigmaseed

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0" , "id": "curltest", "method": "getsigmaseed", "params": \[\] }' -H 'content-type: text/plain;' [http://127.0.0.1:8332/](http://127.0.0.1:8332/)

*  getzerocoinacc
*  ghostamount &lt;amount&gt;\(whole numbers only\) &lt;commitment key pack&gt;: Requiere que la frase de contraseña de billetera se configure.
*  ghostamountv2 &lt;amount&gt;\(whole numbers only\) &lt;commitment\_key\_pack&gt;\(optional\): Requiere que la frase de contraseña de billetera se configure.
*  ghostfeepayouttotal: Obtenga el pago total de ghostfee en el próximo ciclo.
*  ghostprivacysets: Obtenga las cantidades totales de denominación fantasma en la red.
*  ghostprivacysetsv2: Obtenga las cantidades totales de denominación fantasma en la red.
*  listallserials height\(default=current\_height\): Enumera todos los seriales de cero monedas gastados desde la altura

 listpubcoin &lt;all&gt;\(1/5/10/50/100/500/1000/5000\)

 **Argumentos:**

1.  &lt;all&gt; \(int, opcional\) 1,5,10,50,100,500,1000,5000 \(predeterminado\) para devolver todos los pubcoins con denominación. vacío para devolver todo el pubcoin.

 **Los resultados son una matriz de objetos, cada uno de los cuales tiene:**

 {id, IsUsed, denominación, valor, serialNumber, nHeight, randomness}

*  listsigmaentries &lt;true / false&gt; \(default = false\): Lista las entradas sigma en la billetera
*  listunspentghostednix \[minconf=1\] \[maxconf=9999999\]: Requiere que la frase de contraseña de billetera se configure

 **Argumentos:**

1.  &lt;true / false&gt; \(cadena, requerido\) Si se listarán todas las entradas, incluidas las gastadas.

*  listunloadedpubcoins amount\(default=all\): Los resultados son una seride de claves fantasmas públicas
*  listunspentghostednix \[minconf=1\] \[maxconf=9999999\]: Devuelve una matriz de salidas de transacciones no gastadas con confirmaciones entre minconf y maxconf \(inclusive\).

 **Los resltados son una matriz de objetos, cada uno de los cuales tiene:** {txid, vout, scriptPubKey, cantidad, confirmaciones}

*  mintghostdata &lt;amount&gt;\(1,5,10,50,100,500,1000,5000\)
*  payunloadedpubcoins

 **Argumentos:**

 Monto a pagar

 Cadena de llave fantasma:

*  refillghostkeys &lt;amount&gt;\(default=100\): Requiere que la frase de contraseña de billetera se configure
*  resetmintzerocoin: Requiere que la frase de contraseña de billetera se configure.
*  resetzerocoinamounts: Borra zerocoins sin confirmar
*  resetzerocoinunconfirmed: Borra zerocoins sin confirmar
*  setsigmaseed "seed": Establece la semilla sigma determinista de la billetera en un valor específico. Requiere que la frase de contraseña de billetera se configure.

 **Argumentos:**

 1. "seed" \(cadena, requerida\) La sigma determinista sigma.

 **Resultado:**

 "succes": b, \(boolean\) Si la semilla se estableció con éxito

 **Ejemplos:**

 &gt; nix-cli setsigmaseed

 6b54736b13ce6990753b41ca2ce5c5847125b4bf3ffa15f47f5001cd

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "setsigmaseed", "params": \[6b54736b13ce6990753b7345a9b41ca2ce5c5847125b49bf3ffa15f47f5001f47f5f5f5f5f5f5f5f5f5f5f5f5f5f5f5f5f5f5f47f5f5f47f47f5f5f47f5f5f5f47f5f5f47f47f5f5f47f5f5f5f47f5f5f47b\)-type: text/plain;' [http://127.0.0.1:8332/](http://127.0.0.1:8332/)

*  spendghostdata &lt;amount&gt;\(1,5,10,50,100,500,1000,5000\), &lt;seckey&gt;, &lt;randomness&gt;, &lt;serial&gt;, &lt;pubValue&gt;, &lt;spendtoaddress&gt;
*  torstatus: Devuelve el estado de ofuscación de tu domain NIX
*  unghostamount &lt;amount&gt;\(whole numbers only\) &lt;addresstosend&gt;\(either address or commitment key pack\): Requiere que la frase de contraseña de billetera se configure
*  unghostamountv2 &lt;amount&gt;\(whole numbers only\) &lt;addresstosend&gt;\(either address or commitment key pack\): Requiere que la frase de contraseña de billetera se configure

  
		@page { size: 8.5in 11in; margin: 0.79in }  
		p { margin-bottom: 0.1in; direction: ltr; line-height: 115%; text-align: left; orphans: 2; widows: 2; background: transparent }  
		a:link { color: \#0563c1; text-decoration: underline }  
		a:visited { color: \#800000; so-language: zxx; text-decoration: underline }  
	

 **Direcciones Index**

*  getaddressbalance: Devuelve el saldo de una \(s\) dirección \(es\) \(requiere que el índice de dirección esté habilitado\)

 **Argumentos:**

 {

 "addresses"

 \[

 "address" \(cadena\) La dirección codificada base58check

 ...

 \]

 }

 **Resultado:**

 {

 "balance" \(string\) El saldo actual en nix

 "received" \(string\) El número total de nix recibido \(incluido el cambio\)

 }

 **Ejemplos:**

 &gt; nix-cli getaddressbalance '{"direcciones": \["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}'

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getaddressbalance", "params": \[{"direcciones": \["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg "\]}\]} '-H' content type: text / plain; '[http://127.0.0.1:8332/](http://127.0.0.1:8332/)

*  getaddressdeltas: Devuelve todos los cambios para una dirección \(requiere que el índice de dirección esté habilitado\)

 **Argumentos:**

 {

 "addresses"

 \[

 "address" \(cadena\) La dirección codificada base58check

 ...

 \]

 "start" \(number\) La altura del bloque de inicio

 "end" \(number\) La altura del bloque final

 }

 **Resultado:**

 \[

 {

 "satoshis" \(número\) La diferencia de nix

 "txid" \(cadena\) El txid relacionado

 "index" \(número\) El índice de entrada o salida relacionado

 "blockindex" \(número\) El índice de bloque relacionado

 "height" \(número\) La altura del bloque

 "address" \(cadena\) La dirección codificada base58check

 }

 \]

 **Ejemplos:**

 &gt; nix-cli getaddressdeltas '{"direcciones":

 \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}' &gt; curl --user myusername --data-binary '{"jsonrpc":"1.0" , "id": "curtlest", "method": "getaddressmempool", "params": \[{"addresses": \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}\] }' -H 'content-type: text/plain;' [http://127.0.0.1:8332/](http://127.0.0.1:8332/)

*  getaddressmempool: Devuelve todos los deltas de mempool para una dirección \(requiere que el índice de dirección esté habilitado\)

 **Argumentos:**

 {

 "addresses"

 \[

 "address" \(cadena\) la dirección codificada base58check

 ...

 \]

 }

 **Resultado:**

\[

 {

 "address" \(cadena\) La dirección codificada base58check

  "txid" \(cadena\) El txid relacionado

  "index" \(número\) El índice de entrada o salida relacionado

  "satoshis" \(número\) La diferencia de nix

 "timeframe" \(número\) La hora en que la transacción ingresó al mempool \(segundos\)

  "prevtxid" \(cadena\) El txid anterior \(si se gasta\)

 "prevout" \(cadena\) El índice de salida de la transacción anterior \(si se gasta\)

 }

 \]

 **Ejemplos:**

 &gt; nix-cli getaddressbalance ' {"direciones": \["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curtlest", "method": "getaddressbalance", "params": \[{"addresses" \["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}\]} '-H' tipo de contenido: text / plain; 'http//127.0.0.1:8332/

*  getaddresstxids: Devuelve todos los cambios para una dirección \(requiere que el ir d dirección esté habilitado\)

 **Argumentos:**

 {

 “addresses”

 \[

 "address" \(cadena\) La dirección codificada base58check

 ,...

 \]

 "start" \(number\) La altura del bloque de inicio

 "end" \(number\) La altura del bloque final

 }

 **Resultado:**

 \[

 "transactionid" \(string\) El id de transacción

 ,...

 \]

 \]

 **Ejemplos:**

 &gt; nix-cli getaddressdeltas '{"direcciones": \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwgst"\]}'

 &gt; curl --user myusername --data-binary '{"jsornpc":1.0", "id": "curltest", "method": "getaddressmempool", "params": \[{"dirrecciones":

 \["NwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwgst"\]} '-H' content type: tex/ plain; ' [http://127.0.0.1:8332/](http://127.0.0.1:8332/)

*  getaddressutxos: Devuelve todas las salidas no utilizadas para una dirección \(requiere que el índice de dirección esté habilitado\).

 **Argumentos:**

 {

 "addresses"

 \[

 "addresses" \(cadena\) La dirección codificada base58check

 , ...

 \]

 **Resultado:**

 \[

   {

   "address" \(cadena\) La dirección base58check codificada

   "txid" \(cadena\) El txid de salida

   "outputIndex" \(número\) El índice de salida

   "script" \(cadena\) El script hexadecimal codificado

   "satoshis" \(número\) El número de nix de la salida

   "height" \(número\) La altura del bloque

   }

 \]

 **Ejemplos:**

 &gt; nix-cli getaddresstxids '{"addresses": \["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}'

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curtlest", "method": "getaddresstxids", "params": \[{"direcciones": \["XwnLY9Tf7Zsef8gMGL2fhWA9ZmMjt4KPwg"\]}'\]} '-H' content type: text / plain; ' http//127.0.0.1:8332/

  
		@page { size: 8.5in 11in; margin: 0.79in }  
		p { margin-bottom: 0.1in; direction: ltr; line-height: 115%; text-align: left; orphans: 2; widows: 2; background: transparent }  
		a:link { color: \#0563c1; text-decoration: underline }  
		a:visited { color: \#800000; so-language: zxx; text-decoration: underline }  
	

 **Blockchain**

*  getbestblockhash: Devuelve el hash del mejor bloque \(tip\) en la cadena de bloques más larga.

 **Resultado:**

 “hex"\(cadena\) el hash del bloque codificado en hexadecimal.

 **Ejemplos:**

 &gt; nix-cli getbestblockhash

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method":

 "getbestblockhash", "params": \[\] }' -H 'content-type: text/plain;' [http://127.0.0.1:8332/](http://127.0.0.1:8332/)

*  getblock "blockhash" \(verbosidad\)

 Si la verbosidad es 0, devuelve una cadena de datos serializados, codificados en hexadecimal para el bloque 'hash'.

 Si la verbosidad es 1, devuelve un objeto con información sobre el bloque &lt;hash&gt;.

 Si la verbosidad es 2, devuelve un Objeto con información sobre el bloque &lt;hash&gt; e información sobre cada transacción.

 **Argumentos:**

 1. "blockhash"\(cadena, requerida\) El hash de bloque

      2. “verbosity” \(numérica, opcional, predeterminada = 1\) 0 para datos codificados hexadecimales, 1 para un objeto json y 2 para un objeto json con datos de transacción

 **Resultado \(para verbosidad = 0\):**

 "data" \(cadena\) Una cadena que es datos serializados, codificados en hexadecimal para el bloque 'hash'.

 **Resultado \(para verbosidad = 1\):**

 {

   "hash": "hash", \(cadena\) el hash de bloque \(igual que el proporcionado\)

   "confirmations": n, \(numérico\) El número de confirmaciones, o -1 si el bloque no está en la cadena principal

 "size": n, \(numérico\) El tamaño del bloque

 "strippedsize": n, \(numérico\) El tamaño del bloque excluyendo datos de testigos

 "height": n \(numérico\) El peso del bloque como se define en BIP 141

 "height": n, \(numérico\) La altura del bloque o índice

 "version": n, \(numérico\) La versión de bloque

 "versionHex": "00000000", \(cadena\) La versión de bloque formateada en hexadecimal

 "merkleroot": "xxxx", \(cadena\) La raíz de merkle

 "tx": \[\(matriz de cadena\) Los identificadores de transacción

 "transactionid" \(cadena\) El ID de la transacción

     \[

     ,...

     \],

   "time": ttt, \(numérico\) El tiempo de bloqueo en segundos desde la época \(1 de enero de 1970 GMT\)

   "mediantime": ttt, \(numérico\) La mediana del tiempo de bloqueo en segundos desde la época \(1 de enero de 1970 GMT\)

   "nonce": n, \(numérico\) El nonce

   "bits": "1d00ffff", \(cadena\) Los bits

   "dificultad": x.xxx, \(numérico\) La dificultad

   "chainwork": "xxxx", \(string\) Número esperado de hashes necesarios para producir la cadena hasta este bloque \(en hexadecimal\)

   "previousblockhash": "hash", \(string\) El hash del bloque anterior

   "nextblockhash": "hash" \(cadena\) El hash del siguiente bloque

 }

 **Resultado \(para verbosidad = 2\):**

 {

   ..., Misma salida que verbosidad = 1.

   "tx": \[\(matriz de objetos\) Las transacciones en el formato de getrawtransaction RPC. Diferente de verbosidad = 1 resultado "tx". \[

 ,...

 \],

 ,... Same output as verbosity = 1.

 }

 **Ejemplos:**

 &gt; nix-cli getblock "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblock", "params": \["00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  getblockchaininfo: Devuelve un objeto que contiene información de varios estados con respecto al procesamiento de blockchain.

 **Resultado:**

 {

   "chain": "xxxx", \(cadena\) nombre de red actual como se define en BIP70 \(main, test, regtest\)

   "blocks": xxxxxx, \(numérico\) el número actual de bloques procesados ​​en el servidor

   "headers": xxxxxx, \(numérico\) el número actual de encabezados que hemos validado

   "bestblockhash": "...", \(cadena\) el hash del bloque actualmente mejor

   "dificult": xxxxxx, \(numérico\) la dificultad actual

   "mediantime": xxxxxx, tiempo medio \(numérico\) para el mejor bloque actual

   "verify progress": xxxx, estimación \(numérica\) del progreso de verificación \[0..1\]

   "initialblockdownload": xxxx, \(bool\) \(información de depuración\) estimación de si este nodo está en Inicial Block Download mode.

 "chainwork": "xxxx" \(cadena\) cantidad total de trabajo en la cadena activa, en hexadecimal

 "size\_on\_disk": xxxxxx, \(numérico\) el tamaño estimado del bloque y deshacer archivos en el disco

 "pruned": xx, \(booleano\) si los bloques están sujetos a poda

   "pruneheight": xxxxxx, bloque numérico de altura más baja \(numérico\) almacenado \(solo presente si la poda está habilitada\)

   "automatic\_pruning": xx, \(boolean\) si la poda automática está habilitada \(solo está presente si la poda está habilitada\)

   "prune\_target\_size": xxxxxx, \(numérico\) el tamaño de destino utilizado por la poda \(solo presente si la poda automática está habilitada\)

   "softforks": estado \[\(matriz\) de softforks en progreso

     {

       "id": "xxxx", \(cadena\) nombre de softfork

       "version": xx, versión de bloque \(numérico\)

       "reject": {\(objeto\) progreso hacia rechazar bloques pre-softfork

       "status": xx, \(booleano\) verdadero si se alcanza el umbral

     },

   }, ...

 \],

   "bip9\_softforks": {\(objeto\) estado de BIP9 softforks en progreso

   "xxxx": {\(cadena\) nombre del softfork

   "status": "xxxx", \(cadena\) uno de "definido", "iniciado", "bloqueado", "activo", "fallido"

   "bit": xx, \(numérico\) el bit \(0-28\) en el campo de versión de bloque utilizado para señalar este softfork \(solo para el estado "iniciado"\)

   "startTime": xx, \(numérico\) el tiempo medio mínimo pasado de un bloque en el que el bit adquiere su significado

   "timeframe": xx, \(numérico\) la mediana del tiempo pasado de un bloque en el que el despliegue se considera fallido si aún no está bloqueado

   "since": xx, altura \(numérica\) del primer bloque al que se aplica el estado

 "statistics": { \(object\) estadísticas numéricas sobre la señalización BIP9 para un softfork \(solo para el estado "iniciado"\)

   "period": xx, \(numérico\) la longitud en bloques del período de señalización BIP9

   "threshold": xx, \(numérico\) el número de bloques con el conjunto de bits de versión requerido para activar la función

   "elapsed": xx, \(numérico\) el número de bloques transcurridos desde el comienzo del período actual

   "count": xx, \(numérico\) el número de bloques con el bit de versión establecido en el período actual

   "possible": xx \(boolean\) devuelve falso si no quedan suficientes bloques en este período para pasar el umbral de activación

   }

  }

 }

   "warnings": "...", \(string\) cualquier red y advertencias de blockchain

 }

 **Ejemplos:**

 &gt; nix-cli getblockchaininfo

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getblockchaininfo", "params": \[\]}' -H 'content type: texto / sin formato; ' http://127.0.0.1:8332/

*  getblockcount: Devuelve el número de bloques en la cadena de bloques más larga

 **Resultado:**

 n \(numérico\) El recuento de bloque actual

 **Ejemplos:**

 &gt; nix-cli getblockcount

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getblockcount","params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  getblockhash &lt;height&gt;: Devuelve el hash del bloque en la mejor cadena de bloques a la altura provista.

 **Argumentos:**

1.  “height” \(numérico, requerido\) El índice de altura

 **Resultado:**

 "hash" \(cadena\) El hash de bloque

 **Ejemplos:**

 &gt; nix-cli getblockhash 1000

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getblockhash", "params": \[1000\]}' -H 'content -type: text / plain; ' http://127.0.0.1:8332/

*  getblockhashes &lt;timestamp timestamp&gt;: Devuelve una matriz de hashes de bloques dentro del rango de marca de tiempo proporcionado

 **Argumentos:**

1.  high \(numérico, requerido\) La nueva marca de tiempo del bloque
2.  low \(numérico, requerido\) La marca de tiempo del bloque anterior

 **Resultado:**

 \[

   "hash" \(cadena\) El hash de bloque

 \]

 **Ejemplos:**

 &gt; nix-cli getblockhashes 1231614698 1231024505

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getblockhashes", "params": \[1231614698, 1231024505\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

 getblockheader "hash" \(verbose\) If verbose is false, returns a string that is serialized, hex-encoded data for blockheader 'hash'. If verbose is true, returns an Object with information about blockheader &lt;hash&gt;.

 **Argumentos:**

 1. "hash" \(cadena, requerida\) El hash de bloque

 2. “detailed” \(booleano, opcional, predeterminado = verdadero\) verdadero para un objeto json, falso para los datos codificados hexadecimales

 **Resultado \(para verbose = verdadero\):**

 {

   "hash": "hash", \(cadena\) el hash de bloque \(igual que el proporcionado\)

   "confirmations": n, \(numérico\) El número de confirmaciones, o -1 si el bloque no está en la cadena principal

   "height": n, \(numérico\) La altura del bloque o índice

   "version": n, \(numérico\) La versión de bloque

   "versionHex": "00000000", \(cadena\) La versión de bloque formateada en hexadecimal

   "merkleroot": "xxxx", \(cadena\) La raíz de merkle

   "time": ttt, \(numérico\) El tiempo de bloqueo en segundos desde la época \(1 de enero de 1970 GMT\)

   "mediantime": ttt, \(numérico\) La mediana del tiempo de bloqueo en segundos desde la época \(1 de enero de 1970 GMT\)

   "nonce": n, \(numérico\) El nonce

   "bits": "1d00ffff", \(cadena\) Los bits

   "dificult": x.xxx, \(numérico\) La dificultad

   "chainwork": "0000 ... 1f3" \(cadena\) Número esperado de hashes necesarios para producir la cadena actual \(en hexadecimal\)

   "previousblockhash": "hash", \(string\) El hash del bloque anterior

   "nextblockhash": "hash", \(string\) El hash del siguiente bloque

 }

 **Resultado \(para detallado = falso\):**

 "data" \(cadena\) Una cadena que es datos serializados, codificados en hexadecimal para el bloque 'hash'.

 **Ejemplos:**

 &gt; nix-cli getblockheader "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getblockheader", "params": \["00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd14 }f6ed-h3dd146f6ed-h3d14} -6 'content-type: text / plain;' [http://127.0.0.1:8332/](http://127.0.0.1:8332/)

*  getchaintips: Devuelve información sobre todos los consejos conocidos en el árbol de bloques, incluida la cadena principal y las ramas huérfanas

 **Resultado:**

 \[

   {

     "high": xxxx, altura \(numérica\) de la punta de la cadena

     "hash": "xxxx", hash de bloque \(cadena\) de la punta

     "branchlen": 0 \(numérico\) cero para la cadena principal

     "status": "activo" \(cadena\) "activo" para la cadena principal

   },

   {

     "high": xxxx,

     "hash": "xxxx",

     "branchlen": 1 longitud \(numérica\) de rama que conecta la punta a la cadena principal

     "status": estado "xxxx" \(cadena\) de la cadena \(activo, fork válido, encabezados válidos, solo encabezados, inválido\)

   }

 \]

 **Posibles valores para el estado:**

1.  "invalid" Esta rama contiene al menos un bloque inválido.
2.  "only headers" No todos los bloques para esta rama están disponibles, pero los encabezados son válidos.
3.  "valid headers" Todos los bloques están disponibles para esta rama, pero nunca fueron completamente validados.
4.  "valid-fork" Esta rama no es parte de la cadena activa, pero está completamente validada
5.  "active" Esta es la punta de la cadena principal activa, que sin duda es válida.

 **Ejemplos:**

 &gt; nix-cli getchaintips

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getchaintips", "params": \[\]}' -H 'content- type: texto / plain; ' http://127.0.0.1:8332/

*  getchaintxstats \(nblocks blockhash\): Calcule estadísticas sobre el número total y la tasa de transacciones en la cadena

 **Argumentos:**

 1. “nblocks” \(numérico, opcional\) Tamaño de la ventana en número de bloques \(predeterminado: un mes\).

 2. "blockhash" \(cadena, opcional\) El hash del bloque que finaliza la ventana.

 **Resultado:**

 {

   "time": xxxxx, \(numérico\) La marca de tiempo para el bloque final en la ventana en formato UNIX.

   "txcount": xxxxx, \(numérico\) El número total de transacciones en la cadena hasta ese punto.

   "window\_block\_count": xxxxx, \(numérico\) Tamaño de la ventana en número de bloques.

   "window\_tx\_count": xxxxx, \(numérico\) El número de transacciones en la ventana. Solo se devuelve si "window\_block\_count" es&gt; 0.

   "window\_interval": xxxxx, \(numérico\) El tiempo transcurrido en la ventana en segundos. Solo se devuelve si "window\_block\_count" es&gt; 0.

   "txrate": x.xx, \(numérico\) La tasa promedio de transacciones por segundo en la ventana. Solo se devuelve si "window\_interval" es&gt; 0.

 }

 **Ejemplos:**

 &gt; nix-cli getchaintxstats&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getchaintxstats", "params": \[2016\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  getdifficulty: Returns the proof-of-stake difficulty as a multiple of the minimum difficulty.

 **Resultado:**

 n.nnn \(numérico\) la dificultad de la prueba de trabajo como un múltiplo de la dificultad mínima.

 **Ejemplos:**

 &gt; dificultad nix-cli

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getdifficulty", "params": \[\]}' -H 'content- typo: text / plain; ' http://127.0.0.1:8332/

*  getmempoolancestors &lt;txid&gt; \(detailed\): Si txid está en el mempool, devuelve todos los ancestros en el mempool

 **Argumentos:**

 1. "txid" \(cadena, requerida\) La identificación de la transacción \(debe estar en mempool\).

 2. “detailed” \(booleano, opcional, predeterminado = falso\) Verdadero para un objeto json, falso para la matriz de identificadores de transacción.

 **Resultado \(para detallado = falso\):**

 \[\(matriz de cadenas json\)

   "transactionid" \(cadena\) El ID de la transacción de una transacción de antepasados ​​en mempool

   , ...

 \]

 **Resultado \(para verbose = verdadero\):**

 {\(object json\)

   "transactionid": {\(objeto json\)

   "size": n, tamaño de transacción virtual \(numérico\) como se define en BIP 141. Esto es diferente del tamaño serializado real para transacciones de testigos a medida que se descuentan los datos de testigos.

   "fee": n, tarifa de transacción \(numérica\) en NIX

   "modifiedfee": n, tarifa de transacción \(numérica\) con deltas de tarifas utilizadas para la prioridad de minería.

   "time": n, la transacción de hora local \(numérica\) ingresó al grupo en segundos desde el 1 de enero de 1970 GMT.

   "high": n, altura de bloque \(numérico\) cuando la transacción ingresó al grupo.

 "descendantcount": n, número \(numérico\) de transacciones descendientes en el mempool \(incluida esta\)

 "descendantsizes": n, tamaño de transacción virtual \(numérico\) de los descendientes dentro del mempool \(incluido este\)

   "descendantsizes fee": n, tarifas modificadas \(numéricas\) \(ver arriba\) de descendientes en el mempool \(incluido este\)

   "ancestorcount": n, número \(numérico\) de transacciones de antepasados ​​en el mempool \(incluida esta\)

   "ancestorsize": n, tamaño de transacción virtual \(numérico\) de antepasados ​​en mempool \(incluido este\)

   "ancestorfees": n, honorarios modificados \(numéricos\) \(ver arriba\) de antepasados ​​en el mempool \(incluido este\)

   "wtxid": hash, hash \(string\) de transacción serializada, incluidos datos de testigos

   "depend": \[\(matriz\) transacciones no confirmadas utilizadas como entradas para esta transacción

   "transactionid", ID de transacción principal \(cadena\)

   ...\]

   }, ...

 }

 **Ejemplos:**

 &gt; nix-cli getmempoolancestors "mytxid"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getmempoolancestors", "params": \["mytxid"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  getmempooldescendants &lt;txid&gt; \(detailed\): Si txid está en el mempool, devuelve todos los descendientes en el mempool

 **Argumentos:**

1.  "txid" \(cadena, requerida\) La identificación de la transacción \(debe estar en mempool\).
2.  detallado \(booleano, opcional, predeterminado = falso\) Verdadero para un objeto json, falso para la matriz de identificadores de transacción.

 **Resultado \(para detallado = falso\):**

 \[\(matriz de cadenas json\) "transactionid" \(string\) The transaction id of an in-mempool descendant transaction

 ,...

 \]

 **Resultado \(para verbose = verdadero\):**

 {\(object json\)

   "transactionid": {\(objeto json\)

   "size": n, tamaño de transacción virtual \(numérico\) como se define en BIP 141. Esto es diferente del tamaño serializado real para transacciones de testigos a medida que se descuentan los datos de testigos.

   "fee": n, tarifa de transacción \(numérica\) en NIX

   "modifiedfee": n, tarifa de transacción \(numérica\) con deltas de tarifas utilizadas para la prioridad de minería

   "time": n, la transacción de hora local \(numérica\) ingresó al grupo en segundos desde el 1 de enero de 1970 GMT

   "high": n, altura de bloque \(numérico\) cuando la transacción ingresó al grupo

   "descendantcount": n, número \(numérico\) de transacciones descendientes en el mempool \(incluida esta\)

   "descendant": n, tamaño de transacción virtual \(numérico\) de los descendientes dentro del mempool \(incluido este\)

   "descendants fees": n, tarifas modificadas \(numéricas\) \(ver arriba\) de descendientes en el mempool \(incluido este\)

   "ancestorcount": n, número \(numérico\) de transacciones de antepasados ​​en el mempool \(incluida esta\)

   "ancestorsize": n, tamaño de transacción virtual \(numérico\) de antepasados ​​en mempool \(incluido este\)

   "ancestors": n, honorarios modificados \(numéricos\) \(ver arriba\) de antepasados ​​en el mempool \(incluido este\)

   "wtxid": hash, hash \(string\) de transacción serializada, incluidos datos de testigos

   "depend": \[\(matriz\) transacciones no confirmadas utilizadas como entradas para esta transacción

   "transactionid", ID de transacción principal \(cadena\)

   ...\]

   }, ...

 }

 **Ejemplos:**

 &gt; nix-cli getmempooldescendientes "mytxid"&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmempooldescendants", "params": \["mytxid"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  getmempoolentry &lt;txid&gt;: Devuelve datos de mempool para una transacción dada

 **Argumentos:**

1.  "txid" \(cadena, requerida\) La identificación de la transacción \(debe estar en mempool\)

 **Resultado:**

 {\(object json\)

   "size": n, tamaño de transacción virtual \(numérico\) como se define en BIP 141. Esto es diferente del tamaño serializado real para transacciones de testigos a medida que se descuentan los datos de testigos.

   "fee": n, tarifa de transacción \(numérica\) en NIX

   "modifiedfee": n, tarifa de transacción \(numérica\) con deltas de tarifas utilizadas para la prioridad de minería

   "time": n, la transacción de hora local \(numérica\) ingresó al grupo en segundos desde el 1 de enero de 1970 GMT

   "high": n, altura de bloque \(numérico\) cuando la transacción ingresó al grupo

   "descendantcount": n, número \(numérico\) de transacciones descendientes en el mempool \(incluida esta\)

   "descendants": n, tamaño de transacción virtual \(numérico\) de los descendientes dentro del mempool \(incluido este\)

   "descendants fees": n, tarifas modificadas \(numéricas\) \(ver arriba\) de descendientes en el mempool \(incluido este\)

   "ancestorcount": n, número \(numérico\) de transacciones de antepasados ​​en el mempool \(incluida esta\)

   "ancestorsize": n, tamaño de transacción virtual \(numérico\) de antepasados ​​en mempool \(incluido este\)

   "ancestors": n, honorarios modificados \(numéricos\) \(ver arriba\) de antepasados ​​en el mempool \(incluido este\) "wtxid" : hash, \(string\) hash of serialized transaction, including witness data

 "depends": \[\(matriz\) transacciones no confirmadas utilizadas como entradas para esta transacción

  "transactionid", ID de transacción principal \(cadena\)

   ...\]

 }

 **Ejemplos:**

 &gt; nix-cli getmempoolentry "mytxid"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getmempoolentry", "params": \["mytxid"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  getmempoolinfo: Devuelve detalles sobre el estado activo del grupo de memoria TX.

 **Resultado:**

 {

   "size": xxxxx, \(numérico\) Conteo actual de tx

   "bytes": xxxxx, \(numérico\) Suma de todos los tamaños de transacciones virtuales tal como se define en BIP 141. Difiere del tamaño serializado real porque los datos de testigos se descuentan

   "use": xxxxx, \(numérico\) Uso total de memoria para el mempool

   "maxmempool": xxxxx, \(numérico\) Uso máximo de memoria para el mempool

   "mempoolminfee": xxxxx \(numérico\) Tarifa mínima en NIX / kB para que tx sea aceptado. Es el máximo de minrelaytxfee y la tarifa mínima de mempool

   "minrelaytxfee": xxxxx \(numérico\) Tarifa de retransmisión mínima actual para transacciones

 }

 **Ejemplos:**

 &gt; nix-cli getmempoolinfo

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getmempoolinfo","params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  getrawmempool \(verbose\): Devuelve todos los identificadores de transacción en el grupo de memoria como una matriz json de identificadores de transacción de cadena. Sugerencia: use getmempoolentry para obtener una transacción específica del mempool

 **Argumentos:**

1.  “detailed” \(booleano, opcional, predeterminado = falso\) Verdadero para un objeto json, falso para la matriz de identificadores de transacción

 **Resultado: \(para detallado = falso\):**

 \[\(matriz json de cadena\)

   "transactionid" \(cadena\) El ID de la transacción

   , ...

 \]

 **Resultado: \(para detallado = verdadero\):**

 {\(object json\)

   "transactionid": {\(objeto json\)

   "size": n, tamaño de transacción virtual \(numérico\) como se define en BIP 141. Esto es diferente del tamaño serializado real para transacciones de testigos a medida que se descuentan los datos de testigos.

   "fee": n, tarifa de transacción \(numérica\) en NIX

   "modifiedfee": n, tarifa de transacción \(numérica\) con deltas de tarifas utilizadas para la prioridad de minería

   "time": n, la transacción de hora local \(numérica\) ingresó al grupo en segundos desde el 1 de enero de 1970 GMT

   "high": n, altura de bloque \(numérico\) cuando la transacción ingresó al grupo

   "descendantcount": n, número \(numérico\) de transacciones descendientes en el mempool \(incluida esta\)

   "descendant": n, tamaño de transacción virtual \(numérico\) de los descendientes dentro del mempool \(incluido este\)

   "descendant fees": n, tarifas modificadas \(numéricas\) \(ver arriba\) de descendientes en el mempool \(incluido este\)

   "ancestorcount": n, número \(numérico\) de transacciones de antepasados ​​en el mempool \(incluida esta\)

   "ancestorsize": n, tamaño de transacción virtual \(numérico\) de antepasados ​​en mempool \(incluido este\)

   "ancestors": n, honorarios modificados \(numéricos\) \(ver arriba\) de antepasados ​​en el mempool \(incluido este\)

   "wtxid": hash, hash \(string\) de transacción serializada, incluidos datos de testigos "depends" : \[ \(array\) unconfirmed transactions used as inputs for this transaction

 "transactionid", \(string\) parent transaction id

 ... \]

 }, ...

 }

 **Ejemplos:**

 &gt; nix-cli getrawmempool verdadero

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getrawmempool", "params": \[true\]}' -H 'contenido -type: text / plain; ' http://127.0.0.1:8332/

*  gettxout "txid" n \(include\_mempool\): Devuelve detalles sobre una salida de transacción no utilizada.

 **Argumentos:**

1.  "txid" \(cadena, requerida\) La identificación de la transacción
2.  "n" \(numérico, requerido\) número de pedido
3.  "include\_mempool" \(booleano, opcional\) Si se incluye el mempool. Predeterminado: verdadero. Tenga en cuenta que no aparecerá una salida no gastada que se gasta en el mempool.

 **Resultado:**

 {

   "bestblock": "hash", \(cadena\) el hash de bloque

   "confirmaciones": n, \(numérico\) El número de confirmaciones

   "value": x.xxx, \(numérico\) El valor de la transacción en NIX "scriptPubKey" : { \(json object\)

 "asm" : "code", \(string\)

 "hex" : "hex", \(string\)

 "reqSigs" : n, \(numeric\) Number of required signatures

 "type": "pubkeyhash", \(string\) El tipo, por ejemplo, pubkeyhash

  "addresses": \[\(matriz de cadena\) matriz de direcciones nix

  "address" \(cadena\) dirección nix

   , ...

   \]

   },

   "coinbase": verdadero \| falso \(booleano\) Coinbase o no

 }

 **Ejemplos:**

 Obtienes transacciones no gastadas:

 &gt; nix-cli listunspent

 Ver los detalles:

 &gt; nix-cli gettxout "txid" 1

 Como una llamada json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "gettxout", "params": \["txid", 1\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  gettxoutproof \["txid", ...\] \(blockhash\) Devuelve una prueba codificada en hexadecimal de que "txid" se incluyó en un bloque.

 **NOTA:** Por defecto, esta función solo funciona a veces. Esto es cuando hay una salida no utilizada en el utxo para esta transacción. Para que siempre funcione, debe mantener un índice de transacción, utilizando la opción de línea de comando -txindex o especificar el bloque en el que la transacción se incluye manualmente \(por blockhash\).

 **Argumentos:**

 1. "txids" \(cadena\) Una matriz json de txids para filtrar

 \[ "txid" \(string\) Hash de transacción.

 ,...

 \]

 2. "blockhash" \(cadena, opcional\) Si se especifica, busca txid en el bloque con este hash

 **Resultado:**

 "data" \(cadena\) Una cadena que es una información serializada, codificada en hexadecimal para la prueba.

*  Gettxoutsetinfo: Devuelve estadísticas sobre el conjunto de salida de transacciones no gastadas. NOTA: esta llamada puede demorar un poco

 **Resultado:**

 {

   "height": n, \(numérico\) La altura del bloque actual \(índice\)

   "bestblock": "hex", \(cadena\) el mejor hexadecimal hash de bloque

   "transactions": n, \(numérico\) El número de transacciones

   "txouts": n, \(numérico\) El número de transacciones de salida

   "bogosize": n, \(numérico\) Una métrica sin sentido para el tamaño del conjunto UTXO

   "hash\_serialized\_2": "hash", \(cadena\) El hash serializado

   "disk\_size": n, \(numérico\) El tamaño estimado de la cadena en el disco

   "total\_amount": x.xxx \(numérico\) La cantidad total

 }

 **Ejemplos:**

 &gt; nix-cli gettxoutsetinfo

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "gettxoutsetinfo", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/

*  preciousblock "blockhash": Trata un bloque como si fuera recibido antes que otros con el mismo trabajo. Una llamada posterior de bloque precioso puede anular el efecto de una anterior. Los efectos de preciousblock no se retienen en los reinicios

 **Argumentos:**

 1. "blockhash" \(cadena, requerida\) el hash del bloque para marcar como precioso

 **Ejemplos:**

 &gt; nix-cli preciousblock "blockhash"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "preciousblock", "params": \["blockhash"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

 pruneblockchain

 **Argumentos:**

1.  "height" \(numérico, requerido\) La altura del bloque para podar hasta. Se puede establecer a una altura discreta, o una marca de tiempo de Unix para podar bloques cuyo tiempo de bloque es al menos 2 horas mayor que la marca de tiempo proporcionada.

 **Resultado:**

 n \(numérico\) Altura del último bloque podado.

 **Ejemplos:**

 &gt; nix-cli pruneblockchain 1000

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "pruneblockchain", "params": \[1000\]}' -H 'contenido -type: text / plain; ' http://127.0.0.1:8332/

*  savemempool: Vuelca el mempool al disco

 **Ejemplos:**

 &gt; nix-cli savemempool

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "savemempool", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/

*  verifychain \(checklevel nblocks\): Verifica la base de datos de la cadena de bloques.

 **Argumentos:**

1.  “checklevel” \(numérico, opcional, 0-4, predeterminado = 3\) Cuán exhaustiva es la verificación del bloque.
2.  “nblocks” \(numérico, opcional, predeterminado = 6, 0 = todos\) El número de bloques para verificar.

 **Resultado:**

 true \| false \(booleano\) Verificado o no.

 **Ejemplos:**

 &gt; nix-cli verifychain

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "verificarchain", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/

*  verify "proof": Verifica que una prueba apunta a una transacción en un bloque, devolviendo la transacción a la que se compromete y arrojando un error RPC si el bloque no está en nuestra mejor cadena

 **Argumentos:**

 1. "proof" \(cadena, requerida\) La prueba codificada en hexadecimal generada por gettxoutproof

 **Resultado:**

 \["txid"\] \(matriz, cadenas\) El txid \(s\) al que se compromete la prueba, o matriz vacía si la prueba no es válida

## Control

*  getmemoryinfo \("mode"\): Devuelve un objeto que contiene información sobre el uso de la memoria

 **Argumentos:**

 1. "mode" determina qué tipo de información se devuelve. Este argumento es opcional, el modo predeterminado es "estadísticas".

 - "stats" devuelve estadísticas generales sobre el uso de memoria en el demonio.

 - "mallocinfo" devuelve una cadena XML que describe el estado de almacenamiento dinámico de bajo nivel \(solo disponible si se compila con glibc 2.10+\).

 **Resultado \(modo "estadísticas"\):**

 {"blocked": {\(objeto json\) Información sobre el administrador de memoria bloqueado

   "used": xxxxx, \(numérico\) Número de bytes utilizados

   "free": xxxxx, \(numérico\) Número de bytes disponibles en las arenas actuales

   "total": xxxxxxx, \(numérico\) Número total de bytes gestionados

   "blocked": xxxxxx, \(numérico\) Cantidad de bytes que se bloquearon correctamente. Si este número es menor que el total, las páginas de bloqueo fallaron en algún momento y los datos clave podrían intercambiarse al disco.

   "chunks\_used": xxxxx, \(numérico\) Número de fragmentos asignados

   "chunks\_free": xxxxx, \(numérico\) Número de fragmentos no utilizados

   }

 }

 **Resultado \(modo "mallocinfo"\):**

 "&lt;malloc version =" 1 "&gt; ..."

 **Ejemplos:**

 &gt; nix-cli getmemoryinfo

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getmemoryinfo", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/

*  help \("command"\): Enumera todos los comandos u obtén ayuda para un comando específico.

 **Argumentos:**

 1. "command" \(cadena, opcional\) El comando para obtener ayuda sobre

 **Resultado:**

 "texto" \(cadena\) El texto de ayuda

*  logging \(&lt;include&gt; &lt;exclude&gt;\): Obtiene y establece la configuración de registro. Cuando se llama sin argumento, devuelve la lista de categorías con el estado que actualmente se está depurando o no. Cuando se llama con argumentos, agrega o elimina categorías del registro de depuración y devuelve las listas anteriores. Los argumentos se evalúan en orden "incluir", "excluir". Si un artículo está incluido y excluido, terminará siendo excluido. Las categorías de registro válidas son: net, tor, mempool, http, bench, zmq, db, rpc, Estimatefee, addrman, selectcoins, reindex, cmpctblock, rand, podar, proxy, mempoolrej, libevent, coindb, qt, leveldb

 Además, los siguientes están disponibles como nombres de categoría con significados especiales:

  - "all", "1": representan todas las categorías de registro.

  - "none", "0": incluso si se especifican otras categorías de registro, ignórelas todas.

 **Argumentos:**

 1. "include" \(matriz de cadenas, opcional\) Una matriz json de categorías para agregar registro de depuración

 \[

   "category" \(cadena\) la categoría de registro válida

   , ...

 \]

 2. "exclude" \(matriz de cadenas, opcional\) Una matriz json de categorías para eliminar el registro de depuración

 \[

   "category" \(cadena\) la categoría de registro válida

   , ...

 \]

 **Resultado:**

 {\(object json donde las claves son las categorías de registro y los valores indican su estado

   "category": 0 \| 1, \(numérico\) si la depuración se registra o no. 0: inactivo, 1: activo

   ...

 }

 **Ejemplos:**

 &gt; registro de nix-cli "\[\" all \ "\]" "\[\" http \ "\]"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "logging", "params": \[\["all"\], "\[ libevent\] "\]} '-H' content-type: text / plain; ' http://127.0.0.1:8332/

*  stop: Detener el servidor NIX
*  Uptime: Devuelve el tiempo de actividad total del servidor

 **Resultado:**

 ttt \(numérico\) El número de segundos que el servidor ha estado funcionando

 **Ejemplos:**

 &gt; nix-cli uptime

 &gt;curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "uptime", "params": \[\]}' -H 'content- type: text / plain; 'http://127.0.0.1:8332/uptime

  
		@page { size: 8.5in 11in; margin: 0.79in }  
		p { margin-bottom: 0.1in; direction: ltr; line-height: 115%; text-align: left; orphans: 2; widows: 2; background: transparent }  
		a:link { color: \#0563c1; text-decoration: underline }  
		a:visited { color: \#800000; so-language: zxx; text-decoration: underline }  
	

##  **Generando**

*  generate &lt;nblocks&gt; \(maxtries\): Mina hasta nblocks blocks inmediatamente \(antes de que la llamada RPC regrese\) a una dirección en la billetera

 **Argumentos:**

1.  “nblocks” \(numérico, requerido\) Cuántos bloques se generan inmediatamente.
2.  “maxtries” \(numérico, opcional\) Cuántas iteraciones intentar \(por defecto = 1000000\).

 **Resultado:**

 \[blockhashes\] \(array\) hashes de bloques generados

 Ejemplos:

 Genera 11 bloques

 &gt; nix-cli generate 11

*  generatetoaddress &lt;nblocks&gt; &lt;address&gt; \(maxtries\): Mina bloques inmediatamente a una dirección específica \(antes de que regrese la llamada RPC\)

 **Argumentos:**

 1. “nblocks” \(numérico, requerido\) Cuántos bloques se generan inmediatamente.

 2. “address” \(cadena, requerida\) La dirección a la que enviar el nix recién generado.

 3. “maxtries” \(numérico, opcional\) Cuántas iteraciones intentar \(por defecto = 1000000\).

 **Resultado:**

 \[blockhashes\] \(array\) hashes de bloques generados

 Ejemplos:

 Generar 11 bloques para myaddress

 &gt; nix-cli generatetoaddress 11 "myaddress"

  
		@page { size: 8.5in 11in; margin: 0.79in }  
		p { margin-bottom: 0.1in; direction: ltr; line-height: 115%; text-align: left; orphans: 2; widows: 2; background: transparent }  
		a:link { color: \#0563c1; text-decoration: underline }  
		a:visited { color: \#800000; so-language: zxx; text-decoration: underline }  
	

 **Minería**

*  getblocktemplate \(TemplateRequest\): Si los parámetros de solicitud incluyen una clave de 'modo', que se usa para seleccionar explícitamente entre la solicitud de 'plantilla' predeterminada o una 'propuesta'. Devuelve los datos necesarios para construir un bloque para trabajar

 Para la especificación completa, vea los BIP 22, 23, 9 y 145:

  https://github.com/bitcoin/bips/blob/master/bip-0022.mediawiki

  https://github.com/bitcoin/bips/blob/master/bip-0023.mediawiki

  https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki\#getblocktemplate\_changes

  https://github.com/bitcoin/bips/blob/master/bip-0145.mediawiki

 **Argumentos:**

 1. template\_request \(objeto json, opcional\) Un objeto json en la siguiente especificación

 {

   "mode": "template" \(cadena, opcional\) Debe configurarse en "plantilla", "propuesta" \(ver BIP 23\) u omitirse

   "capabilities": \[\(matriz, opcional\) Una lista de cadenas

   "support" \(cadena\) del lado del cliente, 'longpoll', 'coinbasetxn', 'coinbasevalue', 'proposition', 'serverlist', 'workid'

   , ...

   \],

     "rules": \[\(matriz, opcional\) Una lista de cadenas

     "support" \(cadena\) del lado del cliente compatible con la implementación de Softfork

     , ...

   \]

 }

 **Resultado:**

 {

   "version": n, \(numérico\) La versión de bloque preferida

   "rules": \["nombre de regla", ...\], \(matriz de cadenas\) reglas de bloque específicas que se deben aplicar "vbavailable" : { \(json object\) set of pending, supported versionbit \(BIP 9\) softfork deployments

 "rules name": número de bit \(numérico\) identifica el número de bit como indicando aceptación y disponibilidad para la regla de horquilla suave nombrada

   , ...

 },

   "vbrequired": n, máscara de bits \(numérica\) de bits de versión que el servidor requiere establecer en envíos

   "previousblockhash": "xxxx", \(cadena\) El hash del bloque más alto actual

   "transactions": \[\(matriz\) contenido de transacciones que no son coinbase que deben incluirse en el siguiente bloque

   {

     "data": "xxxx", datos de transacción \(cadena\) codificados en hexadecimal \(byte por byte\)

     "txid": "xxxx", identificador de transacción \(cadena\) codificado en hexadecimal little endian

     "hash": "xxxx", \(cadena\) hash codificado en hexadecimal little endian \(incluidos los datos de testigos\)

     "depend": \[\(matriz\) matriz de números

     n transacciones \(numéricas\) antes de esta \(por índice basado en 1 en la lista de 'transacciones'\) que deben estar presentes en el bloque final si este es

     , ...

   \],

   "fee": n, diferencia \(numérica\) en el valor entre las entradas y salidas de la transacción \(en satoshis\); para las transacciones de coinbase, este es un Número negativo del total de tarifas de bloque recaudadas \(es decir, sin incluir el subsidio de bloque\); Si la clave no está presente, se desconoce la tarifa y los clientes NO DEBEN asumir que no hay una

   "sigops": n, costo total \(numérico\) de SigOps, tal como se cuenta a los fines de los límites de bloque; Si la clave no está presente, se desconoce el costo de sigop y los clientes NO DEBEN asumir que es cero

   "ponderating": n, ponderación total \(numérica\) de la transacción, contada para fines de límites de bloque

   "mandatory": verdadero \| falso \(booleano\) si se proporciona y verdadero, esta transacción debe estar en el bloque final

   }

   , ...

   \],

   "coinbaseaux": {\(objeto json\) datos que deben incluirse en el script Script de la base de monedas "flags": se debe ignorar el nombre de la clave "xx" \(cadena\) y se debe incluir el valor en scriptSig

   },

   "coinbasevalue": n, entrada máxima \(numérica\) permitida para la transacción de coinbase, incluida la adjudicación de generación y las tarifas de transacción \(en satoshis\)

   "coinbasetxn": {...}, \(objeto json\) información para la transacción coinbase

   "target": "xxxx", \(string\) El objetivo hash

   "mintime": xxx, \(numérico\) La marca de tiempo mínima apropiada para el siguiente tiempo de bloque en segundos desde la época \(1 de enero de 1970 GMT\)

   "mutable": \[\(matriz de cadena\) lista de formas en que se puede cambiar la plantilla de bloque

   "value" \(cadena\) Una forma en que se puede cambiar la plantilla de bloque, p. 'tiempo', 'transacciones', 'prevblock'

   , ...

   \],

   "noncerange": "00000000ffffffff", \(cadena\) Un rango de nonces válidos

   "sigoplimit": n, límite \(numérico\) de sigops en bloques

   "sizelimit": n, límite \(numérico\) del tamaño del bloque

   "weight limit": n, límite \(numérico\) del peso del bloque

   "curtime": ttt, \(numérico\) marca de tiempo actual en segundos desde la época \(1 de enero de 1970 GMT\)

   "bits": "xxxxxxxx", \(cadena\) objetivo comprimido del siguiente bloque

   "height": n \(numérico\) La altura del siguiente bloque

   "ghostnode": {\(objeto json\) requiere un beneficiario de ghostnode que debe incluirse en el siguiente bloque

   "payee": "xxxx", \(cadena\) dirección del beneficiario

   "script": "xxxx", \(cadena\) beneficiario scriptPubKey

   "ammount": n \(numérico\) monto requerido para pagar

 }, "ghostnode\_payments\_started": verdadero \| falso, \(booleano\) verdadero, si se iniciaron los pagos de ghostnode

 }

 **Ejemplos:**

 &gt; nix-cli getblocktemplate

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getblocktemplate", "params": \[\]}' -H 'content- type: text / plain; 'http://127.0.0.1:8332/

*  getmininginfo: Devuelve un objeto json que contiene información relacionada con la minería

 **Resultado:**

 {

 "blocks": nnn, \(numérico\) El bloque actual

 "currentblockweight": nnn, \(numérico\) El último peso del bloque

 "currentblocktx": nnn, \(numérico\) La última manipulación de bloque

 "dificult": xxx.xxxxx \(numérico\) La dificultad actual

 "networkhashps": nnn, \(numérico\) Los hashes de red por segundo

 "pooledtx": n \(numérico\) El tamaño del mempool

 "chain": "xxxx", \(cadena\) nombre de red actual como se define en BIP70 \(main, test, regtest\)

 "warnings": "..." \(cadena\) cualquier red y advertencias de blockchain

 "errors": "..." \(cadena\) DEPRECATED. Igual que las advertencias. Solo se muestra cuando nixd se inicia con -deprecatedrpc = getmininginfo

 }

 **Ejemplos:**

 &gt; nix-cli getmininginfo

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmininginfo", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  getnetworkhashps \(nblocks high\): Devuelve los hashes de red estimados por segundo en función de los últimos n bloques. Pase \[bloques\] para anular el número de bloques, -1 especifica desde el último cambio de dificultad. Pase \[altura\] para estimar la velocidad de la red en el momento en que se encontró un determinado bloque

 **Argumentos:**

 1. “nblocks” \(numérico, opcional, predeterminado = 120\) El número de bloques, o -1 para bloques desde el último cambio de dificultad.

 2. “height” \(numérico, opcional, predeterminado = -1\) Para estimar en el momento de la altura dada.

 **Resultado:**

 x \(numeric\) Hashes por segundo estimado

 **Ejemplos:**

 &gt; nix-cli getnetworkhashps

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getnetworkhashps", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/

*  prioitisetransaction &lt;txid&gt; &lt;dummy value&gt; &lt;delta fee&gt;: Acepta la transacción en bloques minados con una prioridad más alta \(o más baja\)

 **Argumentos:**

1.  "txid" \(cadena, requerida\) La identificación de la transacción.
2.  Compatibilidad de API ficticia \(numérica, opcional\) para API anteriores. Debe ser cero o nulo. OBSOLETO. Para compatibilidad hacia adelante, use argumentos con nombre y omita este parámetro.

 3. “fee\_delta” \(numérico, requerido\) El valor de la tarifa \(en satoshis\) para sumar \(o restar, si es negativo\). La tarifa no se paga realmente, solo el algoritmo para seleccionar transacciones en un bloque considera la transacción ya que habría pagado una tarifa más alta \(o más baja\).

 **Resultado:**

 true \(booleano\) Devuelve verdadero

 **Ejemplos:**

 &gt; nix-cli priorisetransaction "txid" 0.0 10000

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "priorisetransaction", "params": \["txid", 0.0, 10000\] } '-H' content type: text / plain; ' http://127.0.0.1:8332/

*  submitblock "hexdata" \("dummy"\): Intenta enviar un nuevo bloque a la red. Ver https://en.bitcoin.it/wiki/BIP\_0022 para la especificación completa

 **Argumentos:**

1.  "hexdata" \(cadena, requerida\) los datos del bloque codificado en hexadecimal para enviar
2.  valor ficticio "ficticio" \(opcional\), para compatibilidad con BIP22. Este valor es ignorado.

 **Ejemplos:**

 &gt; nix-cli submitblock "mydata"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "submitblock", "params": \["mydata"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

## **Mnemonic**

*  mnemonic new\|decode\|addchecksum\|dumpwords\|listlanguages
*  mnemonic new \( "password" language nBytesEntropy bip44 \): Genera una nueva clave extendida y contraseña mnemónica, puede estar en blanco, idioma en blanco predeterminado, inglés \| francés \| japonés \| español \| chino\_s \| chino\_t \| italiano \| coreano, inglés predeterminado nBytesEntropy, 16 -&gt; 64, predeterminado 32 bip44, verdadero \| falso, predeterminado verdadero
*  mnemonic decode "password" "mnemonic" \( bip44 \): Decodificación mnemónica bip44, verdadero \| falso, predeterminado verdadero mnemónico addchecksum "mnemónico" Agregue palabras de suma de verificación a mnemónico. El número final de palabras en mnemotécnico debe ser divisible por tres
*  mnemonic dumpwords \( "language" \): Imprimir lista de palabras. idioma, inglés predeterminado
*  mnemonic listlanguages: ​​Imprime la lista de idiomas admitidos

##  **Red**

*  addnode "node" "add \| remove \| entry": Intenta agregar o eliminar un nodo de la lista addnode. O intente una conexión a un nodo una vez. Los nodos agregados usando addnode \(o -connect\) están protegidos de DoS disconnection and are not required to be full nodes/support SegWit as other outbound peers are \(though such peers will not be synced from\).

 **Argumentos:**

1.  "node" \(cadena, requerido\) El nodo \(ver getpeerinfo para nodos\).
2.  "command" \(cadena, requerido\) 'agregar' para agregar un nodo a la lista, 'eliminar' para eliminar un nodo de la lista, 'onetry' para intentar una conexión al nodo una vez.

 **Ejemplos:**

 &gt; nix-cli addnote "192.168.0.6:8333" "onetry"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "addnode", "params": \["192.168.0.6:8333", "onetry"\]} '-H' tipo de contenido: text / plain; ' http://127.0.0.1:8332/

*  clearbanned Borra todas las IP prohibidas

 **Ejemplos:**

 &gt; nix-cli clearbanned

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "clearbanned", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/

*  disconnectnode "\[dirección\]" \[nodeid\]: Se desconecta inmediatamente del nodo par especificado. Estrictamente se puede proporcionar uno de 'dirección' y 'nodoid' para identificar el nodo. Para desconectarse por nodeid, establezca 'address' en la cadena vacía o llame usando solo el argumento llamado 'nodeid'

 **Argumentos:**

 1. "address" \(cadena, opcional\) La dirección IP / puerto del nodo

 2. "nodeid" \(número, opcional\) La ID del nodo \(vea getpeerinfo para las ID del nodo\)

 **Ejemplos:**

 &gt; nix-cli disconnectnode "192.168.0.6:8333"

 &gt; nix-cli disconnectnode "" 1

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "disconnectnode", "params": \["192.168.0.6:8333"\] } '-H' tipo de contenido: text / plain; ' http://127.0.0.1:8332/&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "disconnectnode", "params": \["", 1\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  getaddednodeinfo \("node"\): Devuelve información sobre el nodo agregado dado o todos los nodos agregados \(tenga en cuenta que los nodos de un solo intento no se enumeran aquí\)

 **Argumentos:**

 1. "node" \(cadena, opcional\) Si se proporciona, devuelva información sobre este nodo específico; de lo contrario, se devolverán todos los nodos.

 **Resultado:**

 \[

   {

     "addnode": "192.168.0.201", \(cadena\) La dirección IP o nombre del nodo \(como se proporciona a addnode\)

     "conected": verdadero \| falso, \(booleano\) Si está conectado

     "addresses": \[\(lista de objetos\) Solo cuando está conectado = verdadero

     {

       "address": "192.168.0.201:8333", \(cadena\) La IP del servidor nix y el puerto al que estamos conectados

       "conected": conexión "saliente" \(cadena\), entrante o saliente

     }

   \]

   }

   , ...

 \]

 **Ejemplos:**

 &gt; nix-cli getaddednodeinfo "192.168.0.201"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getaddednodeinfo", "params": \["192.168.0.201"\]}' -H 'tipo de contenido: texto / sin formato;' http://127.0.0.1:8332/

*  getconnectioncount: Devuelve el número de conexiones a otros nodos.

 **Resultado:**

 n \(numérico\) El recuento de conexiones

 **Ejemplos:**

 &gt; nix-cli getconnectioncount

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method":

 "getconnectioncount", "params": \[\]}' -H 'content- tipo: texto / sin formato; ' http://127.0.0.1:8332/

*  getnettotals: Devuelve información sobre el tráfico de red, incluidos los bytes de entrada, los bytes de salida y la hora actual

 **Resultado:**

 {

   "totalbytesrecv": n, \(numérico\) Total de bytes recibidos

   "totalbytessent": n, \(numérico\) Total de bytes enviados

   "timemillis": t, \(numérico\) Tiempo UNIX actual en milisegundos

   "uploadtarget":

   {

     "timeframe": n, \(numérico\) Longitud del marco temporal de medición en segundos

     "target": n, \(numérico\) Target en bytes

     "target\_reached": verdadero \| falso, \(booleano\) Verdadero si se alcanza el objetivo

     "serve\_historical\_blocks": verdadero \| falso, \(booleano\) Verdadero si sirve bloques históricos

     "bytes\_izquierda\_en\_ciclo": t, \(numéricos\) Bytes restantes en el ciclo de tiempo actual

     "time\_left\_in\_cycle": t \(numérico\) Segundos restantes en el ciclo de tiempo actual

   }

 }

 **Ejemplos:**

 &gt; nix-cli getnettotals

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getnettotals", "params": \[\]}' -H 'content- tipo: texto / sin formato; ' http://127.0.0.1:8332/

*  getnetworkinfo: Devuelve un objeto que contiene información de varios estados con respecto a las redes P2P.

 **Resultado:**

 {

   "version": xxxxx, \(numérico\) la versión del servidor

   "subversion": "/Satoshi:x.x.x/", \(cadena\) la cadena de subversión del servidor

   "protocolversion": xxxxx, \(numérico\) la versión del protocolo

   "local services": "xxxxxxxxxxxxxxxx", \(cadena\) los servicios que ofrecemos a la red

   "localrelay": verdadero \| falso, \(bool\) verdadero si se solicita la retransmisión de transacción a los pares

   "timeoffset": xxxxx, \(numérico\) el desplazamiento de tiempo

   "conections": xxxxx, \(numérico\) el número de conexiones

   "networkactive": verdadero \| falso, \(bool\) si la red p2p está habilitada

   "networks": \[\(matriz\) información por red

   {

     "name": "xxx", red \(cadena\) \(ipv4, ipv6 o cebolla\)

     "unlimited": verdadero \| falso, \(booleano\) ¿la red está limitada usando -onlynet?

     "reachable": verdadero \| falso, \(booleano\) ¿es accesible la red?

     "proxy": "host: puerto" \(cadena\) el proxy que se utiliza para esta red, o está vacío si no hay ninguno

     "proxy\_randomize\_credentials": verdadero \| falso, \(cadena\) Si se utilizan credenciales aleatorias

   }

   , ...

   \],

   "relayfee": x.xxxxxxxx, tarifa de retransmisión mínima \(numérica\) para transacciones en NIX / kB

   "incremental fee": x.xxxxxxxx, incremento de tarifa mínima \(numérica\) para limitación de mempool o reemplazo de BIP 125 en NIX / kB

   "localaddresses": \[\(matriz\) lista de direcciones locales

   {

     "address": "xxxx", \(cadena\) dirección de red

     "port": xxx, puerto de red \(numérico\)

     "score": puntuación relativa xxx \(numérica\)

   } ,...

 \]

   "warnings": "..." \(cadena\) cualquier red y advertencias de blockchain

 }

 **Ejemplos:**

 &gt; nix-cli getnetworkinfo

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getnetworkinfo", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/

*  getpeerinfo: Devuelve datos sobre cada nodo de red conectado como una matriz json de objetos

 **Resultado:**

 \[

   {

     "id": n, \(numérico\) Índice de pares

     "addr": "host: puerto", \(cadena\) La dirección IP y el puerto del par

     "addrbind": "ip: puerto", \(cadena\) Dirección de enlace de la conexión al par

     "addrlocal": "ip: puerto", \(cadena\) Dirección local según lo informado por el par

     "services": "xxxxxxxxxxxxxxxx", \(cadena\) Los servicios ofrecidos

     "relaytxes": true \| false, \(boolean\) Si el par nos ha pedido que le enviemos transacciones

     "lastsend": ttt, \(numérico\) El tiempo en segundos desde la época \(1 de enero de 1970 GMT\) del último envío

     "lastrecv": ttt, \(numérico\) El tiempo en segundos desde la época \(1 de enero de 1970 GMT\) de la última recepción

     "bytessent": n, \(numérico\) El total de bytes enviados

     "bytesrecv": n, \(numérico\) El total de bytes recibidos

     "conntime": ttt, \(numérico\) El tiempo de conexión en segundos desde la época \(1 de enero de 1970 GMT\)

     "timeoffset": ttt, \(numérico\) El desplazamiento de tiempo en segundos "pingtime": n, \(numeric\) ping time \(if available\)

 "minping": n, tiempo de ping mínimo \(numérico\) observado \(si lo hay\)

     "pingwait": n, espera de ping \(numérico\) \(si no es cero\)

     "versión": v, \(numérico\) La versión del mismo nivel, como 70001

     "subver": "/Satoshi:0.8.5/", \(cadena\) La versión de la cadena

     "entry": verdadero \| falso, \(booleano\) Entrante \(verdadero\) o Saliente \(falso\)

     "addnode": verdadero \| falso, \(booleano\) Si la conexión se debió a addnode / -connect o si era una conexión automática / entrante

     "beginheight": n, \(numérico\) La altura inicial \(bloque\) del par

     "banscore": n, \(numérico\) El puntaje de prohibición

     "synced\_headers": n, \(numérico\) El último encabezado que tenemos en común con este par

     "synced\_blocks": n, \(numérico\) El último bloque que tenemos en común con este par

     "inglight": \[

       n, \(numérico\) Las alturas de los bloques que estamos pidiendo actualmente a este compañero

       ...

     \],

     "whitelisted": true \| false, \(boolean\) Si el par está en la lista blanca

     "bytessent\_per\_msg": {

     "addr": n, \(numérico\) El total de bytes enviados agregados por tipo de mensaje

     ...

     },

     "bytesrecv\_per\_msg": {

     "addr": n, \(numérico\) El total de bytes recibidos agregados por tipo de mensaje

     ...

     }

   }

   , ...\]

 **Ejemplos:**

 &gt; nix-cli getpeerinfo

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getpeerinfo", "params": \[\]}' -H 'content- type text / plain; ' http://127.0.0.1:8332/

*  listbanned: Lista todas las IP / subredes prohibidas

 **Ejemplos:**

 &gt; nix-cli listbanned

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "listbanned", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/

*  ping: Solicita que se envíe un ping a todos los demás nodos, para medir el tiempo de ping. Los resultados proporcionados en los campos getpeerinfo, pingtime y pingwait son segundos decimales. El comando Ping se maneja en la cola con todos los otros comandos, por lo que mide el procesamiento del trabajo acumulado, no solo el ping de red

 **Ejemplos:**

 &gt; ping nix-cli

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "ping", "params": \[\]}' -H 'content- tipo: texto / sin formato; ' http://127.0.0.1:8332/

*  setban "subnet" "add\|remove" \(bantime\) \(absolute\): Intenta agregar o eliminar una IP / subred de la lista prohibida.

 **Argumentos:**

1.  "subred" \(cadena, requerida\) La IP / subred \(consulte getpeerinfo para nodos IP\) con una máscara de red opcional \(el valor predeterminado es / 32 = IP única\)
2.  "comando" \(cadena, requerido\) 'agregar' para agregar una IP / Subred a la lista, 'eliminar' para eliminar una IP / Subred de la lista
3.  tiempo "bantime" \(numérico, opcional\) en segundos cuánto tiempo \(o hasta cuando se establece \[absoluto\]\) la IP está prohibida \(0 o vacío significa usar el tiempo predeterminado de 24h que también puede sobrescribirse con el tiempo -bant argumento de inicio\)
4.  "absoluto" \(booleano, opcional\) Si se establece, el tiempo de bantime debe ser una marca de tiempo absoluta en segundos desde la época \(1 de enero de 1970 GMT\)

 **Ejemplos:**

 &gt; setban nix-cli "192.168.0.6" "add" 86400

 &gt; setban nix-cli "192.168.0.0/24" "agregar"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "setban", "params": \["192.168.0.6", "add ", 86400\]} '-H' tipo de contenido: text / plain; ' http://127.0.0.1:8332/

*  setnetworkactive true \| false: Deshabilita / habilita toda la actividad de la red p2p.

 **Argumentos:**

 1. "status" \(booleano, requerido\) verdadero para habilitar la creación de redes, falso para deshabilitar

## **Transacciones Raw**

*  combinerawtransaction \["hexstring", ...\]: Combine múltiples transacciones parcialmente firmadas en una sola transacción. La transacción combinada puede ser otra transacción parcialmente firmada o una transacción totalmente firmada

 **Argumentos:**

 1. "txs" \(cadena\) Una matriz json de cadenas hexadecimales de transacciones parcialmente firmadas

 \[

   "hexstring" \(cadena\) Un hash de transacción

   , ...

 \]

 **Resultado:**

 "hex" \(cadena\) La transacción sin formato codificada en hexadecimal con firma \(s\)

 **Ejemplos:**

 &gt; nix-cli combinerawtransaction \["myhex1", "myhex2", "myhex3"\]

*  createrawtransaction \[{"txid":"id","vout":n},...\] {"address":amount,"data":"hex",...} \(locktime\) \(replaceable\): Cree una transacción gastando las entradas dadas y creando nuevas salidas. Las salidas pueden ser direcciones o datos. Devuelve la transacción sin formato codificada en hexadecimal. Tenga en cuenta que las entradas de la transacción no están firmadas y no se almacenan en la billetera ni se transmiten a la red

 **Argumentos:**

 1. "entries" \(matriz, requerida\) Una matriz json de objetos json

 \[

   {

     "txid": "id", \(string, obligatorio\) El ID de la transacción

     "vout": n, \(numérico, requerido\) El número de salida

     "secuences": n \(numérico, opcional\) El número de secuencia

   }

   , ...

 \]

 2. "exits" \(objeto, requerido\) un objeto json con salidas

 {

   "addresses": x.xxx, \(numérico o cadena, requerido\) La clave es la dirección nix, el valor numérico \(puede ser una cadena\) es la cantidad NIX

   "data": "hex" \(cadena, requerida\) La clave es "data", el valor es datos codificados en hexadecimal

   , ...

 }

 3. tiempo de bloqueo \(numérico, opcional, predeterminado = 0\) Tiempo de bloqueo sin procesar. El valor distinto de 0 también activa las entradas de tiempo de bloqueo

 4. reemplazable \(booleano, opcional, predeterminado = falso\) Marca esta transacción como BIP125 reemplazable. Permite que esta transacción sea reemplazada por una transacción con tarifas más altas. Si se proporciona, es un error si los números de secuencia explícitos son incompatibles.

 **Resultado:**

 "transaction" \(cadena\) cadena hexadecimal de la transacción

 **Ejemplos:**

 &gt; nix-cli createrawtransaction "\[{\"txid\":\"myid\",\"vout\":0}\]" "{\"address\":0.01}"

 &gt; nix-cli createrawtransaction "\[{\"txid\":\"myid\",\"vout\":0}\]" "{\"data\":\"00010203\"}"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createrawtransaction", "params": \["\[{\"txid\":\"myid\",\"vout\":0}\]", "{\"address\":0.01}"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "createrawtransaction", "params": \["\[{\"txid\":\"myid\",\"vout\":0}\]", "{\"data\":\"00010203\"}"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  decoderawtransaction "hexstring" \(iswitness\): Devuelve un objeto JSON que representa la transacción serializada y codificada en hexadecimal

 **Argumentos:**

 1. "hexachain" \(cadena, requerida\) La cadena hexadecimal de transacción

 2. “iswitness” \(boolean, opcional\) Si la transacción hexadecimal es una transacción de testigo serializada. Si su testigo no está presente, se utilizarán pruebas heurísticas en la decodificación.

 **Resultado:**

 {

   "txid": "id", \(string\) El ID de la transacción

   "hash": "id", \(cadena\) El hash de la transacción \(difiere de txid para transacciones de testigos\)

   "size": n, \(numérico\) El tamaño de la transacción

   "vsize": n, \(numérico\) El tamaño de la transacción virtual \(difiere del tamaño de las transacciones de testigos\)

   "version": n, \(numérico\) La versión

   "locktime": ttt, \(numérico\) El tiempo de bloqueo

   "vin": \[\(matriz de objetos json\)

   {

     "txid": "id", \(string\) El ID de la transacción

     "vout": n, \(numérico\) El número de salida

     "scriptSig": {\(objeto json\) El script

     "asm": "asm", \(cadena\) asm

     "hex": "hex" \(cadena\) hexadecimal

   },

   "txinwitness": \["hex", ...\] \(matriz de cadena\) datos de testigo codificados en hexadecimal \(si los hay\)

   "secuence": n \(numérico\) El número de secuencia del script

 }

 , ...

 \],

 "vout": \[\(matriz de objetos json\)

 {

   "value": x.xxx, \(numérico\) El valor en NIX

   "n": n, índice \(numérico\)

   "scriptPubKey": {\(objeto json\)

   "asm": "asm", \(string\) el asm

   "hex": "hex", \(cadena\) el hex

   "reqSigs": n, \(numérico\) Los signos requeridos

   "type": "pubkeyhash", \(string\) El tipo, por ejemplo, 'pubkeyhash'

   "addresses": \[\(matriz json de cadena\)

   "12tvKAXCxZjSmdNbao16dKXC8tRWfcF5oc" \(cadena\) dirección nix

   , ...

   \]

   }

 }

 , ...

 \],

 }

 **Ejemplos:**

 &gt; nix-cli decoderawtransaction "hexstring"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "decoderawtransaction", "params": \["hexstring"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  decodescript "hexstring": Decodifica un script codificado en hexadecimal

 **Argumentos:**

 1. "hexstring" \(cadena\) el script codificado hexadecimal

 **Resultado:**

 {

   "asm": "asm", clave pública de secuencia de comandos

   "hex": "hex", clave pública codificada en hexadecimal \(cadena\)

   "type": "type", \(string\) El tipo de salida

   "reqSigs": n, \(numérico\) Las firmas requeridas

   "addresses": \[\(matriz json de cadena\)

   "address" \(cadena\) dirección nix

   , ...

   \],

   "p2sh", "dirección" \(cadena\) dirección del script P2SH que envuelve este script de canje \(no se devuelve si el script ya es un P2SH\).

 }

 **Ejemplos:**

 &gt; nix-cli decodescript "hexstring"&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "decodescript", "params": \["hexstring"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  fundrawtransaction "hexstring" \(iswitness options\): Agregar entradas a una transacción hasta que tenga suficiente valor para cumplir con su valor de salida. Esto no modificará las entradas existentes y agregará como máximo una salida de cambio a las salidas. No se modificarán las salidas existentes a menos que se especifique "subtractFeeFromOutputs". Tenga en cuenta que las entradas que se firmaron pueden tener que renunciar después de la finalización ya que se han agregado las entradas / salidas

 Las entradas agregadas no se firmarán, use signrawtransaction para eso.

 Tenga en cuenta que todas las entradas existentes deben tener su transacción de salida anterior en la billetera.

 Tenga en cuenta que todas las entradas seleccionadas deben ser de forma estándar y los scripts P2SH deben estar en la billetera usando importaddress o addmultisigaddress \(para calcular las tarifas\).

 Puede ver si este es el caso marcando el campo "solucionable" en la salida de lista no utilizada.

 Solo las versiones pay-to-pubkey, multisig y P2SH de las mismas son compatibles actualmente solo con reloj

 **Argumentos:**

 1. "hexstring" \(cadena, requerida\) La cadena hexadecimal de la transacción sin procesar

 2. “options”\(objeto, opcional\)

 {

   "changeAddress" \(cadena, opcional, dirección de grupo predeterminada\) La dirección nix para recibir el cambio "changePosition" \(numérico, opcional, aleatorio predeterminado\) El índice de la salida de cambio

   "change\_type" \(cadena, opcional\) El tipo de salida a utilizar. Solo es válido si no se especifica changeAddress. Las opciones son "heredado", "p2sh-segwit" y "bech32". El valor predeterminado se establece por -changetype.

   "includeWatching" \(booleano, opcional, falso predeterminado\) También seleccione entradas que son solo de observación

   "lockUnspents" \(booleano, opcional, falso predeterminado\) Bloquea las salidas no gastadas seleccionadas

   "feeRate" \(numérico, opcional, predeterminado no establecido: hace que la billetera determine la tarifa\) Establezca una tarifa de tarifa específica en NIX / kB

   "subtractFeeFromOutputs" \(matriz, opcional\) Una matriz json de enteros. La tarifa se deducirá igualmente de la cantidad de cada salida especificada. Las salidas se especifican por su índice de base cero, antes de agregar cualquier salida de cambio. Esos destinatarios recibirán menos nix de lo que ingresas en su campo de monto correspondiente. Si no se especifica ninguna salida aquí, el remitente paga la tarifa.

   \[vout\_index, ...\]

   "reemplazable" \(booleano, opcional\) Marca esta transacción como BIP125 reemplazable. Permite que esta transacción sea reemplazada por una transacción con tarifas más altas

   "conf\_target" \(numérico, opcional\) Objetivo de confirmación \(en bloques\)

   "estimate\_mode" \(cadena, opcional, predeterminado = DESACTIVAR\) El modo de estimación de tarifa debe ser uno de:

 "INESTABLE""ECONOMICAL"

 "CONSERVATIVE"

 }

 Para compatibilidad con versiones anteriores: pasar un verdadero en lugar de un objeto dará como resultado {"includeWatching": verdadero}

       3. iswitness \(boolean, opcional\) Si la transacción hexadecimal es una transacción de testigo serializada

 Si su testigo no está presente, se utilizarán pruebas heurísticas en la decodificación.

 **Resultado:**

 {

   "hex": "value", \(cadena\) La transacción sin procesar resultante \(cadena codificada en hexadecimal\)

   "fee": n, tarifa \(numérica\) en NIX que paga la transacción resultante

   "changepos": n \(numérico\) La posición de la salida de cambio agregada, o -1

 }

 **Ejemplos:**

 Crear una transacción sin entradas:

 &gt; nix-cli createrawtransaction "\[\]" "{\" myaddress \ ": 0.01}"

 Agregue suficientes entradas sin signo para cumplir con el valor de salida:

 &gt; nix-cli fundrawtransaction "rawtransactionhex"

 Firma la transacción:

 &gt; nix-cli signrawtransaction "fundingtransactionhex"

 Envía la transacción

 &gt; nix-cli sendrawtransaction "firmadotransacciónhex"

*  getrawtransaction "txid" \("blockhash" detailed\)

 **NOTA:** Por defecto, esta función solo funciona para transacciones mempool. Si la opción -txindex está habilitada, también funciona para transacciones de blockchain. Si se conoce el bloque que contiene la transacción, se puede proporcionar su hash incluso para los nodos sin -txindex. Tenga en cuenta que si se proporciona un blockhash, solo se buscará ese bloque y si la transacción está en el mempool u otros bloques, o si este nodo no tiene el bloque dado disponible, la transacción no se encontrará.

 DEPRECATED: por ahora, también funciona para transacciones con salidas no gastadas.

 Devuelve los datos sin procesar de la transacción.Si verbose es 'verdadero', devuelve un objeto con información sobre 'txid'.

 Si detailed es 'falso' u omitido, devuelve una cadena que es serializada, datos codificados en hexadecimal para 'txid'.

 **Argumentos:**

1.  "txid" \(cadena, requerida\) La identificación de la transacción
2.  “detailed” \(bool, opcional, predeterminado = falso\) Si es falso, devuelve una cadena, de lo contrario devuelve un objeto json
3.  "blockhash" \(cadena, opcional\) El bloque en el que buscar la transacción

 **Resultado \(si detallado no se establece o se establece en falso\):**

 "data" \(cadena\) Los datos codificados en hexadecimal serializados para 'txid'

 **Resultado \(si detallado se establece en verdadero\):**

 {

   "in\_active\_chain": b, \(bool\) Si el bloque especificado está en la cadena activa o no \(solo presente con explicit "blockhash" argument\)

 "hex": "data", \(string\) Los datos serializados, codificados en hexadecimal para 'txid'

   "txid": "id", \(string\) El id de la transacción \(igual que el proporcionado\)

   "hash": "id", \(cadena\) El hash de la transacción \(difiere de txid para transacciones de testigos\)

   "size": n, \(numérico\) El tamaño de la transacción serializada

   "vsize": n, \(numérico\) El tamaño de la transacción virtual \(difiere del tamaño de las transacciones de testigos\)

   "version": n, \(numérico\) La versión

   "locktime": ttt, \(numérico\) El tiempo de bloqueo

   "vin": \[\(matriz de objetos json\)

   {

     "txid": "id", \(string\) El ID de la transacción

     "vout": n, \(numérico\)

     "scriptSig": {\(objeto json\) El script

     "asm": "asm", \(cadena\) asm

     "hex": "hex" \(cadena\) hexadecimal

   },

   "secuence": n \(numérico\) El número de secuencia del script

   "txinwitness": \["hex", ...\] \(matriz de cadena\) datos de testigo codificados en hexadecimal \(si los hay\)

 }

 , ...

 \],

 "vout": \[\(matriz de objetos json\)

 {

   "value": x.xxx, \(numérico\) El valor en NIX

   "n": n, índice \(numérico\)

   "scriptPubKey": {\(objeto json\)

   "asm": "asm", \(string\) el asm

   "hex": "hex", \(cadena\) el hex

   "reqSigs": n, \(numérico\) Los signos requeridos

   "type": "pubkeyhash", \(string\) El tipo, por ejemplo, 'pubkeyhash'

   "addresses": \[\(matriz json de cadena\) "address" \(string\) nix address

 , ...

   \]

   }

 }

 , ...

 \],

 "blockhash": "hash", \(cadena\) el hash de bloque

 "confirmations": n, \(numérico\) Las confirmaciones

 "time": ttt, \(numérico\) El tiempo de transacción en segundos desde la época \(1 de enero de 1970 GMT\)

 "blocktime": ttt \(numérico\) El tiempo de bloque en segundos desde la época \(1 de enero de 1970 GMT\)

 }

 **Ejemplos:**

 &gt; nix-cli getrawtransaction "mytxid"

 &gt; nix-cli getrawtransaction "mytxid" verdadero

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getrawtransaction", "params": \["mytxid", true\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

 &gt; nix-cli getrawtransaction "mytxid" false "myblockhash"

 &gt; nix-cli getrawtransaction "mytxid" verdadero "myblockhash"

*  sendrawtransaction "hexstring" \(allowhighfees\): Envía la transacción sin procesar \(serializada, codificada en hexadecimal\) al nodo local y a la red. También vea createrawtransaction y signrawtransaction llamadas

 **Argumentos:**

 1. "hexstring" \(cadena, requerida\) La cadena hexadecimal de la transacción sin procesar\)

 2. “allowhighfees” \(boolean, opcional, default = false\) Permitir tarifas altas

 **Resultado:**

 "hex" \(cadena\) El hash de transacción en hexadecimal

 **Ejemplos:**

 Crear una transacción:

 &gt; nix-cli createrawtransaction "\[{\" txid \ ": \" mytxid \ ", \" vout \ ": 0}\]" "{\" myaddress \ ": 0.01}"

 Firme la transacción y recupere el hex:

 &gt; nix-cli signrawtransaction "myhex"

 Enviar la transacción \(hexadecimal firmado\):

 &gt; nix-cli sendrawtransaction "firmadohex"

 Como una llamada json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "sendrawtransaction", "params": \["ignedhex "\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  signrawtransaction "hexstring" \(\[{{"txid": "id", "vout": n, "scriptPubKey": "hex", "redeemScript": "hex"}, ...\] \["privatekey1", ... \] sighashtype\) Firma entradas para transacciones sin procesar \(serializadas, codificadas en hexadecimal\).

 El segundo argumento opcional \(puede ser nulo\) es una matriz de salidas de transacciones anteriores de las que depende esta transacción pero que aún no pueden estar en la cadena de bloques.

 El tercer argumento opcional \(puede ser nulo\) es una matriz de claves privadas codificadas en base58 que, si se dan, serán las únicas claves utilizadas para firmar la transacción.

 Requiere que la frase de contraseña de billetera se configure con la llamada de frase de contraseña de billetera.

 **Argumentos:**

 1. "hexachain" \(cadena, requerida\) La cadena hexadecimal de transacción

 2. "prevtxs" \(cadena, opcional\) Una matriz json de salidas de transacciones dependientes anteriores

 \[\(matriz json de objetos json, o 'nulo' si no se proporciona ninguno\)

 {

   "txid": "id", \(string, obligatorio\) El ID de la transacción

   "vout": n, \(numérico, requerido\) El número de salida "scriptPubKey": "hex", \(string, required\) script key

 "redeemScript": "hexadecimal", \(cadena, requerido para P2SH o P2WSH\) canjear script

   "ammount": valor \(numérico, requerido\) El monto gastado

 }

 , ...

 \]

 3. "privkeys" \(cadena, opcional\) Una matriz json de claves privadas codificadas en base58 para firmar

 \[\(matriz json de cadenas, o 'nulo' si no se proporciona ninguno\)

 "privatekey" \(cadena\) clave privada en codificación base58

 , ...

 \]

 4. "sighashtype" \(cadena, opcional, predeterminado = TODOS\) El tipo de hash de firma. Debe ser uno de

 "ALL"

 "NONE"

 "SINGLE"

 "ALL\|ANYONECANPAY"

 "NONE\|ANYONECANPAY"

 "SINGLE\|ANYONECANPAY"

 **Resultado:**

 {

   "hex": "value", \(cadena\) La transacción sin formato codificada en hexadecimal con firma \(s\)

   "complete": verdadero \| falso, \(booleano\) Si la transacción tiene un conjunto completo de firmas

   "errors": \[\(matriz de objetos json\) Errores de verificación de script \(si hay alguno\)

   {

     "txid": "hash", \(string\) El hash de la transacción anterior referenciada

     "vout": n, \(numérico\) El índice de la salida a gastado y utilizado como entrada "scriptSig" : "hex", \(string\) The hex-encoded signature script

 "secuencie": n, número de secuencia de comandos \(numérico\)

     "error": "text" \(cadena\) Error de verificación o firma relacionado con la entrada

   }

   , ...

   \]

 }

 **Ejemplos:**

 &gt; nix-cli signrawtransaction "myhex"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "signrawtransaction", "params": \["myhex"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

## Util

*  createmultisig nrequired \["key", ...\]: Crea una dirección de firma múltiple con n firma de m claves requeridas. Devuelve un objeto json con la dirección y canjeaScript. ADVERTENCIA DE DEPRECACIÓN: El uso de direcciones con createmultisig está en desuso. Los clientes deben hacer la transición para usar addmultisigaddress para crear direcciones multigrado con direcciones conocidas para la billetera antes de actualizar a v0.17. Para usar la funcionalidad obsoleta, inicie nixd con -deprecatedrpc = createmultisig

 **Argumentos:**

 1. “nrequired” \(numérico, requerido\) El número de firmas requeridas de las n claves o direcciones.

 2. "keys" \(cadena, requerida\) Una matriz json de claves públicas codificadas en hexadecimal

 \[

   "keys" \(cadena\) La clave pública codificada en hexadecimal

   , ...

 \]

 **Resultado:**

 {

   "address": "multisigaddress", \(string\) El valor de la nueva dirección multisig.

   "redeemScript": "script" \(cadena\) El valor de cadena de la secuencia de comandos de canje codificada en hexadecimal.

 }

 **Ejemplos:**

 Crear una dirección multigrado a partir de 2 claves públicas:

 &gt; nix-cli createmultisig 2 "\[\" 03789ed0bb717d88f7d321a368d905e7430207ebbd82bd342cf11ae157a7ace5fd \ ", \" 03dbc6764b8884a92e871274b87583e6d5c2a588193e3a6173 "

 Como una llamada json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "createmultisig", "params": \[2, "\[\" 03789ed0bb717d88f7d321a368d905e7430207ebbd82bd1575ff11ae152 ", \" 03dbc6764b8884a92e871274b87583e6d5c2a58819473e17e107ef3f6aa5a61626 \ "\]"\]} '-H' content-type: text / plain; ' http://127.0.0.1:8332

 Estimación de &lt;nblocks&gt; DEPRECATED. Utilice Estimaciones SmartFfee para estimaciones más inteligentes. Estima la tarifa aproximada por kilobyte necesaria para que una transacción comience la confirmación dentro de los bloques nblocks. Utiliza el tamaño de transacción virtual de la transacción como se define en BIP 141 \(los datos de testigo se descuentan\).

 **Argumentos:**

 1. “nblocks” \(numérico, requerido\)

 **Resultado:**

 n \(numérico\) tarifa estimada por kilobyte.

 Se devuelve un valor negativo si no se han observado suficientes transacciones y bloques para hacer una estimación.

 -1 siempre se devuelve para nblocks == 1 ya que es imposible calcular una tarifa que sea lo suficientemente alta como para ser incluida de manera confiable en el siguiente bloque.

 Ejemplo:

 &gt; nix-cli estimatefee 6

*  estimatesmartfee &lt;conf\_target&gt; \("estimate\_mode"\): Estima la tarifa aproximada por kilobyte necesaria para que una transacción comience la confirmación dentro de los bloques conf\_target si es posible y devuelve el número de bloques para los cuales la estimación es válida. Utiliza el tamaño de transacción virtual como se define en BIP 141 \(los datos de testigos se descuentan\)

 **Argumentos:**

 1. “conf\_target” \(numérico\) Objetivo de confirmación en bloques \(1 - 1008\)

 2. "estimate\_mode" \(cadena, opcional, predeterminado = CONSERVADOR\) El modo de estimación de tarifa. Si se debe devolver una estimación más conservadora que también satisfaga una historia más larga. Una estimación conservadora potencialmente devuelve una tarifa más alta y es más probable que sea suficiente para el objetivo deseado, pero no es tan sensible a las caídas a corto plazo en el mercado de tarifas prevaleciente. Debe ser uno de:

 "UNSET" \(defaults to CONSERVATIVE\)

 "ECONOMICAL"

 "CONSERVATIVE"

 **Resultado:**

 {

   "fee": x.x, tasa de tarifa estimada \(numérica, opcional\) en NIX / kB

   "errors": \[str ...\] \(matriz de cadenas json, opcional\) Errores encontrados durante el procesamiento

   "blocks": n número de bloque \(numérico\) donde se encontró la estimación

 }

 El objetivo de solicitud se fijará entre 2 y la estimación de tarifa de objetivo más alta puede regresar en función de cuánto tiempo ha estado funcionando. Se devuelve un error si no se han observado suficientes transacciones y bloques para hacer una estimación de cualquier número de bloques.

 **Ejemplo:**

 &gt; estimaciones de nix-cli smartfee ​​6

*  signmessagewithprivkey "privkey" "message": Firme un mensaje con la clave privada de una dirección

 **Argumentos:**

 1. "privkey" \(cadena, requerida\) La clave privada con la que firmar el mensaje.

 2. "message" \(cadena, requerido\) El mensaje para crear una firma.

 **Resultado:**

 "firma" \(cadena\) La firma del mensaje codificado en base 64

 **Ejemplos:**

 Crea la firma:

 &gt; nix-cli signmessagewithprivkey "privkey" "mi mensaje"

 Verificar la firma:

 &gt;nix-cli verfifymessage "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "firma" "mi mensaje"

 Como json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "signmessagewithprivkey", "params": \["privkey", "mi mensaje" \]} '-H' tipo de contenido: text / plain; ' http://127.0.0.1:8332/

*  validateaddress "address": Devuelve información sobre la dirección nix dada

 **Argumentos:**

 1. "address" \(cadena, requerida\) La dirección nix para validar

 **Resultado:**

 {

   "isvalid": true \| false, \(boolean\) Si la dirección es válida o no. Si no, esta es la única propiedad devuelta.

   "address": "address", \(string\) La dirección nix validada

   "scriptPubKey": "hex", \(string\) El scriptPubKey codificado en hexadecimal generado por la dirección

   "ismine": verdadero \| falso, \(booleano\) Si la dirección es suya o no

   "iswatchonly": true \| false, \(boolean\) Si la dirección es watchonly

   "isscript": verdadero \| falso, \(booleano, opcional\) Si la dirección es P2SH o P2WSH. No incluido para tipos de testigos desconocidos.

   "iswitness": verdadero \| falso, \(booleano\) Si la dirección es P2WPKH, P2WSH o una versión de testigo desconocida

 "witness\_version": versión \(número, opcional\) Para todos los tipos de salida de testigo, proporciona el número de versión.

 "witness\_program": "hex" \(cadena, opcional\) Para todos los tipos de salida de testigo, proporciona el hash de script o clave presente en la dirección.

   "script": "type" \(cadena, opcional\) El tipo de script de salida. Solo si "isscript" es verdadero y se conoce el redeemscript. Tipos posibles: no estándar, pubkey, pubkeyhash, scripthash, multisig, nulldata, witness\_v0\_keyhash, witness\_v0\_scripthash, witness\_unknown

   "hex": "hex", \(cadena, opcional\) El canje de la dirección P2SH o P2WSH

   "addresses" \(cadena, opcional\) Matriz de direcciones asociadas con el canje de texto conocido \(solo si "iswitness" es falso\). Este campo es reemplazado por el campo "pubkeys" y la dirección dentro de "incrusted".

   \[

     "talk to"

     , ...

   \]

   "pubkeys" \(cadena, opcional\) Matriz de pubkeys asociados con el canje de texto conocido \(solo si "script" es "multisig"\)

   \[

     "pubkey"

     , ...

   \]

   "sigsrequired": xxxxx \(numérico, opcional\) Número de firmas necesarias para gastar la salida multigrado \(solo si "script" es "multigrado"\)

   "pubkey": "publickeyhex", \(cadena, opcional\) El valor hexadecimal de la clave pública sin formato, para direcciones de clave única \(posiblemente incrustadas en P2SH o P2WSH\)

   "incrusted": {...}, \(objeto, opcional\) información sobre la dirección incrustada en P2SH o P2WSH, si es relevante y conocida. Incluye todos los campos de salida de validateaddress para la dirección incrustada, excepto "isvalid", metadata \("timestamp", "hdkeypath", "hdmasterkeyid"\) y la relación con la billetera \("ismine", "iswatchonly", "account"\).

   "is comprimed": verdadero \| falso, \(booleano\) Si la dirección está comprimida

   "account": "cuenta" \(cadena\) DEPRECATED. La cuenta asociada con la dirección, "" es la cuenta predeterminada

   "timeframe": marca de tiempo, \(número, opcional\) El tiempo de creación de la clave si está disponible en segundos since epoch \(Jan 1 1970 GMT\)

 "hdkeypath": "keypath" \(cadena, opcional\) La ruta de acceso HD si la llave es HD y está disponible

   "hdmasterkeyid": "&lt;hash160&gt;" \(cadena, opcional\) El Hash160 del HD master pubkey

 }

 **Ejemplos:**

 &gt; nix-cli validateaddress "1PSSGeFHDnKNxiEyFrD1wcEaHr9hrQDDWc"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "validateaddress", "params": \["1PSSGeFHDnKNxiEyFrD1wcEaHr9hrQDDWc"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

 verifique el mensaje "dirección" "firma" "mensaje" Verifique un mensaje firmado

 **Argumentos:**

1.  "address" \(cadena, requerida\) La dirección nix a usar para la firma.
2.  "firm" \(cadena, requerida\) La firma provista por el firmante en la codificación base 64 \(ver mensaje de firma\).
3.  "message" \(cadena, requerido\) El mensaje que se firmó.

 **Resultado:**

 true \| false \(booleano\) Si la firma se verifica o no.

 **Ejemplos:**

 Desbloquee la billetera por 30 segundos:

 &gt; nix-cli walletpassphrase "mypassphrase" 30

 Crea la firma&gt; nix-cli signmessage "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "my message"

 Verificar la firma:

 &gt; mensaje de verificación nix-cli "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "firma" "mi mensaje"

 Como json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "verifiedmessage", "params": \["1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX", "signature", "my message"\]} '-H' content-type: text / plain; ' http://127.0.0.1:8332/

## **Billetera**

*  abandontransaction "txid": Marcar la transacción en la billetera &lt;txid&gt; como abandonada. Esto marcará esta transacción y todos sus descendientes en la billetera como abandonados, lo que permitirá que sus entradas sean respetadas. Se puede usar para reemplazar transacciones "atascadas" o desalojadas. Solo funciona en transacciones que no están incluidas en un bloque y que actualmente no están en el mempool. No tiene efecto en las transacciones que ya están en conflicto o abandonadas

 **Argumentos:**

1.  "txid" \(cadena, requerida\) La identificación de la transacción

 Ejemplos:

 &gt; nix-cli abandontransaction "1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "abandontransaction", "params": \["1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5f" b&gt; 'content-type: text / plain;' http://127.0.0.1:8332/

*  Abortrescan: Detiene el escaneo actual de la billetera activado por una llamada RPC, p. por una llamada importprivkey

 **Ejemplos:**

 Importar una clave privada:

 &gt; nix-cli importprivkey "mykey"

 Abortar la billetera en ejecución:

 &gt; nix-cli abortrescan

 Como una llamada JSON-RPC:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "abortrescan", "params": \[\]}' -H 'content- tipe: text / plain; ' http://127.0.0.1:8332/

*  addmultisigaddress &lt;nrequired&gt; \["key",...\] \( "account" "address\_type" \): Agregue una dirección de firma múltiple que se requiera para firmar a la billetera. Requiere una nueva copia de seguridad de la billetera. Cada clave es una dirección NIX o clave pública codificada en hexadecimal. Esta funcionalidad solo está diseñada para usarse con direcciones que no sean de vigilancia. Consulte \`importaddress\` para ver solo el soporte de la dirección p2sh. Si se especifica 'cuenta' \(DEPRECADA\), asigne la dirección a esa cuenta

 **Argumentos:**

1.  “nrequired” \(numérico, requerido\) El número de firmas requeridas de las n claves o direcciones.
2.  "keys" \(cadena, requerida\) Una matriz json de direcciones nix o claves públicas codificadas en hexadecimal.

 \[

 "dirección" \(cadena\) dirección nix o clave pública codificada en hexadecimal

 ...

 \]

1.  "account" \(cadena, opcional\) DEPRECADO. Una cuenta para asignar las direcciones.
2.  "address\_type" \(cadena, opcional\) El tipo de dirección a utilizar. Las opciones son "heredado", "p2sh-segwit" y "bech32". El valor predeterminado lo establece -addresstype.

 **Resultado:**

 {

 "address": "multisigaddress", \(string\) El valor de la nueva dirección multisig.

 "redeemScript": "script" \(cadena\) El valor de cadena de la secuencia de comandos de canje codificada en hexadecimal.

 }

 Resultado \(DEPRECATED. Para ver este resultado en v0.16 en su lugar, inicie nixd con -deprecatedrpc = addmultisigaddress\). Los clientes deben realizar la transición a la nueva API de salida antes de actualizar a v0.17.

 "address" \(cadena\) Una dirección nix asociada con las teclas.

 **Ejemplos:**

 Agregue una dirección multigrado de 2 direcciones

 &gt; nix-cli addmultisigaddress 2 addresses

 &gt; nix-cli addmultisigaddress 2"\[\"16sSauSf5pF2UkUwvKGq4qjNRzBZYqgEL5\",\"171sgjn4YtPu27adkKGrdDwzRTxnRkBfKV\"\]"

 As json rpc call

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "addmultisigaddress", "params": \[2, "\[\"16sSauSf5pF2UkUwvKGq4qjNRzBZYqgEL5\",\"171sgjn4YtPu27adkKGrdDwzRTxnRkBfKV\"\]"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  backupwallet "destination": Copia de manera segura el archivo de billetera actual al destino, que puede ser un directorio o una ruta con nombre de archivo

 **Argumentos:**

 1. "destiny" \(cadena\) El directorio o archivo de destino

 **Ejemplos:**

 &gt; nix-cli backupwallet "backup.dat"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "backupwallet", "params": \["backup.dat"\]}' -H 'tipo de contenido: texto / sin formato;' http://127.0.0.1:8332/

*  bumpfee "txid" \(options\): Topa la tarifa de una transacción T opt-in-RBF, reemplazándola por una nueva transacción B. Una transacción RBF opt-in con el txid dado debe estar en la billetera. El comando pagará la tarifa adicional al disminuir \(o tal vez eliminar\) su salida de cambio. Si la salida de cambio no es lo suficientemente grande como para cubrir la tarifa aumentada, el comando fallará en lugar de agregar nuevas entradas para compensar. \(Una implementación futura podría mejorar esto\). El comando fallará si la billetera o el mempool contienen una transacción que gasta una de las salidas de T.

 De manera predeterminada, la nueva tarifa se calculará automáticamente utilizando Estimación de tarifa. El usuario puede especificar un objetivo de confirmación para la estimación.

 Alternativamente, el usuario puede especificar totalFee, o usar RPC settxfee para establecer una tarifa más alta. Como mínimo, la nueva tarifa debe ser lo suficientemente alta como para pagar una nueva tarifa de retransmisión adicional \(tarifa incremental devuelta por getnetworkinfo\) para ingresar al mempool del nodo.

 **Argumentos:**

 1. “txid” \(cadena, requerido\) El txid a ser golpeado.

 2. “options” \(objeto, opcional\).

 {

   "confTarget" \(numérico, opcional\) Objetivo de confirmación \(en bloques\)

   "totalFee" \(numérico, opcional\) Tarifa total \(NO tarifa\) a pagar, en satoshis. En casos excepcionales, la tarifa real pagada puede ser ligeramente más alta que la tarifa total especificada si la salida de cambio tx tiene que eliminarse porque está demasiado cerca del umbral de polvo.

 "reemplazable" \(booleano, opcional, predeterminado verdadero\) Si la nueva transacción aún debe marcarse como reemplazable bip-125. Si es verdadero, los números de secuencia en la transacción no se modificarán del original. Si es falso, cualquier número de secuencia de entrada en la transacción original que fuera inferior a 0xfffffffe se incrementará a 0xfffffffe, por lo que la nueva transacción no será reemplazable explícitamente por bip-125 \(aunque puede ser reemplazable en la práctica, por ejemplo, si tiene antepasados ​​no confirmados que son reemplazables\)

 "estimate\_mode" \(cadena, opcional, predeterminado = DESACTIVAR\) El modo de estimación de tarifa debe ser uno de:

   "UNSET"

   "ECONOMIC"

   "CONSERVATIVE"

 }

 **Resultado:**

 {

   "txid": "value", \(cadena\) El id de la nueva transacción

   "origfee": n, tarifa \(numérica\) de la transacción reemplazada

   "fee": n, tarifa \(numérica\) de la nueva transacción

   "errors": \[str ...\] \(matriz de cadenas json\) Errores encontrados durante el procesamiento \(puede estar vacío\)

 }

 **Ejemplos:**

 Aumente la tarifa, obtenga el txid de la nueva transacción

*  nix-cli bumpfee &lt;txid&gt;dumpprivkey "address": Revela la clave privada correspondiente a 'dirección'. Entonces importprivkey se puede usar con esta salida

 **Argumentos:**

 1. "address" \(cadena, requerida\) La dirección nix para la clave privada

 **Resultado:**

 "key" \(cadena\) La clave privada

 **Ejemplos:**

 &gt; nix-cli dumpprivkey "myaddress"

 &gt; nix-cli importprivkey "mykey"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "dumpprivkey", "params": \["myaddress"\]}--H 'content-type: text / plain;' http://127.0.0.1:8332/

*  dumpwalletprivatekeys "filename": Vuelca todas las claves de billetera en un formato legible para humanos en un archivo del lado del servidor. Esto no permite sobrescribir archivos existentes

 Los scripts importados se incluyen en el archivo de volcado, pero importwallet no puede agregar automáticamente las direcciones BIP173 correspondientes, etc.

 Tenga en cuenta que si su billetera contiene claves que no se derivan de su semilla HD \(por ejemplo, claves importadas\), estas no se cubren solo haciendo una copia de seguridad de la semilla en sí, y también deben respaldarse \(por ejemplo, asegúrese de hacer una copia de seguridad de todo el archivo de volcado\).

 **Argumentos:**

 1. "filename" \(cadena, requerido\) El nombre de archivo con ruta \(ya sea absoluta o relativa a nixd\)

 **Resultado:**

 {\(object json\)

   "filename": {\(string\) El nombre del archivo con la ruta absoluta completa}

 Ejemplos:

 &gt; nix-cli dumpwallet "prueba"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "dumpwallet", "params": \["test"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  encryptwallet "passphrase": Cifra la billetera con 'contraseña'. Esto es por primera vez encriptación. Después de esto, cualquier llamada que interactúe con claves privadas como el envío o la firma requerirá que se establezca la frase de contraseña antes de realizar estas llamadas. Use la llamada walletpassphrase para esto, y luego la llamada walletlock. Si la billetera ya está encriptada, use la llamada walletpassphrasechange

 Tenga en cuenta que esto apagará el servidor.

 **Argumentos:**

 1. "keyphrasse" \(cadena\) La frase de contraseña para cifrar la billetera. Debe tener al menos 1 carácter, pero debe ser largo.

 **Ejemplos:**

 Cifra tu billetera:

 &gt; nix-cli encryptwallet "mi frase de contraseña"

 Ahora configure la frase de contraseña para usar la billetera, como para firmar o enviar nix:

 &gt; nix-cli walletpassphrase "mi frase de contraseña"

 Ahora podemos hacer algo como firmar:

 &gt; nix-cli signmessage "dirección" "mensaje de prueba"

 Ahora bloquee la billetera nuevamente quitando la frase de contraseña:

 &gt; wallet nix-cli

 Como una llamada json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "encryptwallet", "params": \["mi frase de paso"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  getaccount "address" DEPRECATED: Devuelve la cuenta asociada con la dirección dada

 **Argumentos:**

 1. "address" \(cadena, requerida\) La dirección nix para la búsqueda de cuentas.

 **Resultado:**

 "account name" \(cadena\) la dirección de la cuenta

 **Ejemplos:**

 &gt; nix-cli getaccount "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getaccount", "params": \["1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  getaccountaddress "account" DEPRECATED: Devuelve la dirección NIX actual para recibir pagos a esta cuenta

 **Argumentos:**

1.  "account" \(cadena, requerida\) El nombre de la cuenta para la dirección. También se puede establecer en la cadena vacía "" para representar la cuenta predeterminada. La cuenta no necesita existir, se creará y se creará una nueva dirección si no hay una cuenta con el nombre de pila.

 **Resultado:**

 "address" \(string\) La dirección nix de la cuenta

 **Ejemplos:**

 &gt; nix-cli getaccountaddress

 &gt; nix-cli getaccountaddress ""

 &gt; nix-cli getaccountaddress "myaccount"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getaccountaddress", "params": \["myaccount"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  getalladdresses: Obtenga todas las direcciones de envío
*  getbalance \("account" minconf include\_watchonly\): Si no se especifica la cuenta, devuelve el saldo total disponible del servidor. El saldo disponible es lo que la billetera considera actualmente gastable y, por lo tanto, se ve afectado por opciones que limitan la capacidad de gasto, como -spendzeroconfchange. Si se especifica cuenta \(DEPRECATED\), devuelve el saldo en la cuenta.

 Tenga en cuenta que la cuenta "" no es lo mismo que omitir el parámetro. El total del servidor puede ser diferente al saldo en la "" cuenta predeterminada.

 **Argumentos:**

 1. "account" \(cadena, opcional\) DEPRECADO. La cadena de la cuenta se puede dar como un nombre de cuenta específico para encontrar el saldo asociado con las claves de billetera en una cuenta con nombre, o como la cadena vacía \(""\) para encontrar el saldo asociado con las claves de billetera que no están en ninguna cuenta con nombre, o como " \* "para encontrar el saldo asociado con todas las claves de billetera, independientemente de la cuenta. Cuando se especifica esta opción, calcula el saldo de una manera diferente a la que no se especifica, y que puede contar los gastos dos veces cuando hay transacciones pendientes en conflicto \(como las creadas por el comando bumpfee\), lo que resulta temporalmente bajo o incluso saldos negativos En general, el cálculo del saldo de la cuenta no se considera confiable y ha resultado en resultados confusos, por lo que se recomienda evitar pasar este argumento.

 2. “minconf” \(numérico, opcional, predeterminado = 1\) Solo incluya transacciones confirmadas al menos tantas veces.

 3. “include\_watchonly” \(bool, opcional, default = false\) También incluye saldo en direcciones de solo vigilancia \(ver 'importaddress'\)

 **Resultado:**

 monto \(numérico\) El monto total en NIX recibido para esta cuenta.

 **Ejemplos:**

 La cantidad total en la billetera con 1 o más confirmaciones:

 &gt; equilibry de nix-cli

 La cantidad total en la billetera al menos 6 bloques confirmados:

 &gt; equilibry de nix-cli "\*" 6

 Como una llamada json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getbalance", "params": \["\*", 6\]}' -H 'tipo de contenido: texto / sin formato;' http://127.0.0.1:8332/

*  getcoldstakinginfo: Devuelve un objeto que contiene información relacionada con el replanteo en frío

 **Resultado:**

 {

   "enabled": true \| false, \(boolean\) Si se carga o no una dirección de replanteo válida en esta billetera.

   "coldstaking\_address" \(cadena\) La dirección de la dirección coldstaking\_dress actual.

   "coin\_in\_stakeable\_script" \(numérico\) Cantidad actual de monedas en los scripts que esta cartera puede apostar.

 "coin\_in\_coldstakeable\_script" \(numérico\) Cantidad actual de monedas en los scripts apostables por la billetera con la dirección de replanteo en frío.

   "percent\_in\_coldstakeable\_script" \(numérico\) Porcentaje de moneda en scripts apilables en frío.

   "current\_staking" \(numérico\) Cantidad de moneda estimada por esta billetera actualmente en juego.

 }

 **Ejemplos:**

 &gt; nix-cli getcoldstakinginfo

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getcoldstakinginfo", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/

*  getfeeforamount "quantity" "address": Devuelve la tarifa necesaria para la cantidad necesaria para enviar

 **Argumentos:**

 1. "ammount" \(int, requerido\) El monto que desea para el cálculo de la tarifa.

 2. "address" \(cadena, requerida\) La dirección a la que desea enviar para el cálculo de la tarifa.

 **Resultado:**

 "fee" \(cadena de tarifa json\)

 **Ejemplos:**

 &gt; nix-cli getfeeforamount "400" "ZM72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd"

*  getleasestakinglist: Obtenga una lista de los contratos actuales de LPoS en la billetera. Requiere que la frase de contraseña de billetera se configure con la llamada de frase de contraseña de billetera
*  getnewaddress \("account" "tipe\_address"\): Devuelve una nueva dirección NIX para recibir pagos. Si se especifica 'cuenta' \(DEPRECADO\), se agrega a la libreta de direcciones para que los pagos recibidos con la dirección se acrediten a 'cuenta'

 **Argumentos:**

 1. "account" \(cadena, opcional\) DEPRECADO. El nombre de la cuenta para la dirección que se vinculará. Si no se proporciona, se usa la cuenta predeterminada "". También se puede establecer en la cadena vacía "" para representar la cuenta predeterminada. La cuenta no necesita existir, se creará si no hay una cuenta con el nombre de pila.

 2. "address\_type" \(cadena, opcional\) El tipo de dirección a utilizar. Las opciones son "ghostnode", "p2sh-segwit \(predeterminado\)" y "bech32". El valor predeterminado lo establece -addresstype.

 **Resultado:**

 "address" \(string\) La nueva dirección nix

 **Ejemplos:**

 &gt; nix-cli getnewaddress

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getnewaddress", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/

*  getrawchangeaddress \("address\_type"\): Devuelve una nueva dirección NIX para recibir el cambio. Esto es para usar con transacciones sin procesar, NO para uso normal

 **Argumentos:**

 1. "address\_type" \(cadena, opcional\) El tipo de dirección a utilizar. Las opciones son "heredado", "p2sh-segwit" y "bech32". El valor predeterminado se establece por -changetype.

 **Resultado:**

 "address" \(cadena\) La dirección

 **Ejemplos:**

 &gt; nix-cli getrawchangeaddress

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getrawchangeaddress", "params": \[\]}' -H 'content- tipo: texto / sin formato; ' http://127.0.0.1:8332/

*  getreceivedbyaccount "account" \(minconf\) DEPRECATED. Devuelve la cantidad total recibida por las direcciones con &lt;cuenta&gt; en transacciones con al menos \[minconf\] confirmaciones.

 **Argumentos:**

 1. "account" \(cadena, requerida\) La cuenta seleccionada, puede ser la cuenta predeterminada usando "".

 2. “minconf” \(numérico, opcional, predeterminado = 1\) Solo incluya transacciones confirmadas al menos tantas veces.

 **Resultado:**

 monto \(numérico\) El monto total en NIX recibido para esta cuenta.

 **Ejemplos:**

 Cantidad recibida por la cuenta predeterminada con al menos 1 confirmación:

 &gt; nix-cli getreceivedbyaccount ""

 Monto recibido en la cuenta de tabby incluyendo montos no confirmados con cero confirmaciones:

 &gt; nix-cli getreceivedbyaccount "tabby" 0

 La cantidad con al menos 6 confirmaciones:

 &gt; nix-cli getreceivedbyaccount "tabby" 6

 Como una llamada json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getreceivedbyaccount", "params": \["tabby", 6\]}' -H 'tipo de contenido: texto / sin formato;' http://127.0.0.1:8332/

*  getreceivedbyaddress "address" \(minconf\): Devuelve la cantidad total recibida por la dirección dada en transacciones con al menos confirmaciones de minconf

 **Argumentos:**

 1. "address" \(cadena, requerida\) La dirección nix para transacciones.

 2. “minconf” \(numérico, opcional, predeterminado = 1\) Solo incluya transacciones confirmadas al menos tantas veces.

 **Resultado:**

 monto \(numérico\) El monto total en NIX recibido en esta dirección.

 **Ejemplos:**

 El importe de las transacciones con al menos 1 confirmación:

 &gt; nix-cli getreceivedbyaddress "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX"

 La cantidad que incluye transacciones no confirmadas, cero confirmaciones:

 &gt; nix-cli getreceivedbyaddress "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" 0

 La cantidad con al menos 6 confirmaciones:

 &gt; nix-cli getreceivedbyaddress "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" 6As a json rpc call

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getreceivedbyaddress", "params": \["1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX", 6\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  getstakingaverage: Obtenga el monto promedio de participación en la última muestra de 500 bloques
*  Getstakinginfo: Devuelve un objeto que contiene información relacionada con el replanteo

 **Resultado:**

 {

   "enabled": verdadero \| falso, \(booleano\) si el replanteo está habilitado o no en esta billetera

   "staking": verdadero \| falso, \(booleano\) si esta billetera está replanteándose o no

   "errors": "..." \(cadena\) cualquier mensaje de error

   "percentyearreward": xxxxxxx, porcentaje de recompensa de apuesta actual \(numérico\)

   "Money offer": xxxxxxx, \(numérico\) la cantidad total de NIX en la red

   "reserve": xxxxxxx, \(numérico\) la cantidad total de NIX en la red

   "walletdonationpercent": xxxxxxx, porcentaje \(numérico\) establecido por el usuario de la recompensa de bloque cedida al desarrollo

   "currentblocksize": nnn, \(numérico\) el último tamaño de bloque en bytes

   "currentblockweight": nnn, \(numérico\) el último peso del bloque

   "currentblocktx": nnn, \(numérico\) el número de transacciones en el último bloque

   "pooledtx": n \(numérico\) el número de transacciones en el mempool

   "dificult": xxx.xxxxx \(numérico\) la dificultad actual

   "lastsearchtime": xxxxxxx \(numérico\) la última vez que esta billetera buscó un coinstake

   "weight": xxxxxxx \(numérico\) el peso actual de esta cartera

   "netstakeweight": xxxxxxx \(numérico\) el peso de la apuesta actual de la red

   "timeframe": tiempo estimado xxxxxxx \(numérico\) para la próxima apuesta

 }

 **Ejemplos:**

 &gt; nix-cli getstakinginfo

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getstakinginfo", "params": \[\]}' -H 'content-type: text / plain; ' http://127.0.0.1:8332/gettransaction "txid" \(include\_watchonly\) Obtener información específica sobre la cuestión en billetera &lt;txid&gt;

 **Argumentos:**

 1. "txid" \(cadena, requerida\) La identificación de la amenaza

 2. "include\_watchonly" \(bool, opcional, por defecto = false\) Si incluimos direcciones de solo vigilancia en el cálculo del saldo y los detalles \[\]

 **Resultado:**

 {

 “ammount": x.xxx, \(numérico\) El monto de la variación en NIX

 "fee": x.xxx, \(numérico\) El monto de la tarifa en NIX. Esto es negativo y solo está disponible para la categoría de 'envío' de transacciones.

 "confirmations": n, \(numérico\) El número de confirmaciones

 "blockhash": "hash", \(cadena\) El hash de bloque

 "blockindex": xx, \(numérico\) El índice de la modificación en el bloque que lo incluye

 "blocktime": ttt, \(numérico\) El tiempo en segundos desde la época \(1 de enero de 1970 GMT\)

 "txid": "transactionid", \(cadena\) El ID de la manipulación.

 "time": ttt, \(numérico\) El tiempo de tránsito en segundos desde la época \(1 de enero de 1970 GMT\)

 "timereceived": ttt, \(numérico\) El tiempo recibido en segundos desde la época \(1 de enero de 1970 GMT\)

 "bip125-reemplazable": "sí \| no \| desconocido", \(cadena\) Si esta podría ser reemplazada debido a BIP125 \(reemplazo por tarifa\); puede ser desconocido para transacciones no confirmadas que no están en el mempool

 "details": \[

 {

 "account": "nombre de cuenta", \(cadena\) DEPRECATED. El nombre de cuenta involucrado en la modificación puede ser "" para la cuenta predeterminada.

 "address": "address", \(string\) La dirección nix involucrada en la manipulación

 "category": "enviar \| recibir", \(cadena\) La categoría, ya sea 'enviar' o 'recibir'

 "ammount": x.xxx, \(numérico\) La cantidad en NIX

 "label": "label", \(cadena\) Un comentario para la dirección / cambios, si corresponde

 "vout": n, \(numérico\) el valor de vout

 "tarifa": x.xxx, \(numérico\) El monto de la tarifa en NIX. Esto es negativo y solo está disponible para la categoría de 'envío' de transacciones.

     "abandoneds": xxx \(bool\) 'verdadero' si la transacción ha sido abandonada \(las entradas son confiables\). Solo disponible para la categoría 'enviar' de transacciones.

   }

   , ...

   \],

   "hex": "data" \(cadena\) Datos sin procesar para la transacción

 }

 **Ejemplos:**

 &gt; nix-cli gettransaction "1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d"

 &gt; nix-cli gettransaction "1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5fbf5d48d" verdadero

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "gettransaction", "params": \["1075db55d416d3ca199f55b6084e2115b9345e16c5cf302fc80e9d5f" b&gt; 'content-type: text / plain;' http://127.0.0.1:8332/

*  getunconfirmedbalance: Devuelve el saldo total no confirmado del servidor
*  getwalletinfo: Devuelve un objeto que contiene información variada sobre el estado de la billetera

 **Resultado:**

 {

   "walletname": xxxxx, \(string\) el nombre de la billetera

   "walletversion": xxxxx, \(numérico\) la versión de billetera

   "balance": xxxxxxx, \(numérico\) el saldo total confirmado de la billetera en NIX

   "unconfirmed\_balance": xxx, \(numérico\) el saldo total no confirmado de la billetera en NIX

 "inmature\_balance": xxxxxx, \(numérico\) el saldo inmaduro total de la billetera en NIX

   "txcount": xxxxxxx, \(numérico\) el número total de transacciones en la billetera

   "keypoololdest": xxxxxx, \(numérico\) la marca de tiempo \(segundos desde la época Unix\) de la clave pregenerada más antigua en el conjunto de claves

   "keypoolsize": xxxx, \(numérico\) cuántas claves nuevas se generan previamente \(solo cuenta las claves externas\)

   "keypoolsize\_hd\_internal": xxxx, \(numérico\) cuántas claves nuevas se generan previamente para uso interno \(se utilizan para salidas de cambio, solo aparece si la billetera está utilizando esta función; de lo contrario, se utilizan claves externas\)

   "unlocked\_until": ttt, \(numérico\) la marca de tiempo en segundos desde la época \(medianoche del 1 de enero de 1970 GMT\) que la billetera está desbloqueada para transferencias, o 0 si la billetera está bloqueada

   "paytxfee": x.xxxx, \(numérico\) la configuración de la tarifa de transacción, establecida en NIX / kB

   "hdmasterkeyid": "&lt;hash160&gt;" \(cadena, opcional\) el Hash160 del HD master pubkey \(solo presente cuando HD está habilitado\)

 }

 **Ejemplos:**

 &gt; nix-cli getwalletinfo

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getwalletinfo", "params": \[\]}' -H 'content- tipo: texto / sin formato; ' http://127.0.0.1:8332/

*  importaddress "address" \("label" rescan p2sh\) Agrega un script \(en hexadecimal\) o una dirección que se puede ver como si estuviera en su billetera pero no se puede usar para gastar. Requiere una nueva copia de seguridad de la billetera

 **Argumentos:**

 1. "script" \(cadena, requerida\) El script codificado en hexadecimal \(o dirección\)

 2. "label" \(cadena, opcional, por defecto = ""\) Una etiqueta opcional

 3. “rescan” \(booleano, opcional, predeterminado = verdadero\) Vuelva a escanear la billetera para transacciones

 4. p2sh \(booleano, opcional, predeterminado = falso\) Agregue también la versión P2SH del script

 **Nota:** Esta llamada puede tardar minutos en completarse si el reescaneo es verdadero, durante ese tiempo, otras llamadas de RPC pueden informar que la dirección importada existe pero las transacciones relacionadas aún faltan, lo que lleva a saldos incorrectos / falsos temporalmente y salidas no gastadas hasta que se completa el reescaneo. Si tiene la clave pública completa, debe llamar a importpubkey en lugar de esto.

 **Nota:** Si importa una secuencia de comandos sin formato no estándar en forma hexadecimal, las salidas que se le envíen serán tratadas como un cambio y no se mostrarán en muchos RPC.

 **Ejemplos:**

 Importar un script con reescaneo:

 &gt; nix-cli importaddress "myscript"

 Importar usando una etiqueta sin volver a escanear:

 &gt; nix-cli importaddress "myscript" "testing" false

 Como una llamada JSON-RPC:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "importaddress", "params": \["myscript", "testing", false\]} '-H' content-type: text / plain; ' http://127.0.0.1:8332/

*  importmulti "submits" \("options"\): Importar direcciones / secuencias de comandos \(con claves privadas o públicas, canjear secuencia de comandos \(P2SH\)\), volver a escanear todas las direcciones en un solo disparo \(la nueva exploración se puede desactivar mediante las opciones\). Requiere una nueva copia de seguridad de billetera

 **Argumentos:**

 1. solicitudes \(matriz, requeridas\) Datos a importar

 \[\(matriz de objetos json\)

 {

   "scriptPubKey": "&lt;script&gt;" \| {"address": "&lt;address&gt;"}, \(string / json, obligatorio\) Tipo de scriptPubKey \(string para script, json para dirección\)

   "timestamp": marca de tiempo \| "ahora", \(entero / cadena, requerido\) Tiempo de creación de la clave en segundos desde la época \(1 de enero de 1970 GMT\), o la cadena "ahora" para sustituir el tiempo de blockchain sincronizado actual. La marca de tiempo de la clave más antigua determinará qué tan atrás deben comenzar los escaneos de blockchain para las transacciones de billetera que faltan. "ahora" se puede especificar para omitir el escaneo, para claves que se sabe que nunca se han usado, y 0 se puede especificar para escanear toda la cadena de bloques. Se analizarán los bloques hasta 2 horas antes del tiempo de creación de la clave más temprana de todas las claves importadas por la llamada importmulti.

   "redeemscript": "&lt;script&gt;", \(cadena, opcional\) Permitido solo si el scriptPubKey es una dirección P2SH o un script P2SH scriptPubKey

   "pubkeys": \["&lt;pubKey&gt;", ...\], \(array, opcional\) Matriz de cadenas que dan pubkeys que deben aparecer en la salida o redeemscript

 "keys": \["&lt;key&gt;", ...\], \(array, opcional\) Matriz de cadenas que dan claves privadas cuyas claves públicas correspondientes deben aparecer en la salida o redeemscript

 "interno": &lt;verdadero&gt;, \(booleano, opcional, predeterminado: falso\) Indicando si las salidas coincidentes deben tratarse como pagos no entrantes

 "watchonly": &lt;true&gt;, \(boolean, opcional, predeterminado: false\) Indica si las salidas coincidentes deben considerarse observadas incluso cuando no son gastables, solo se permiten si las claves están vacías

 "label": &lt;label&gt;, \(string, opcional, default: ''\) Etiqueta para asignar a la dirección \(también conocido como nombre de cuenta, por ahora\), solo se permite con internal = false

 }

 ...

 \]

 2. options \(json, opcional\)

 {

 "rescan": &lt;false&gt;, \(boolean, opcional, predeterminado: verdadero\) Indicando si debe volver a escanear la cadena de bloques después de todas las importaciones

 }

 **Nota:** Esta llamada puede tardar minutos en completarse si el reescaneo es verdadero, durante ese tiempo, otras llamadas de RPC pueden informar que las claves, direcciones o scripts importados existen, pero aún faltan transacciones relacionadas.

 **Ejemplos:**

 &gt; nix-cli importmulti '\[{"scriptPubKey": {"address": "&lt;my address&gt;"}, "timestamp": 1455191478}, {"scriptPubKey": {"address": "&lt;my 2nd address&gt;"} , "label": "example 2", "timestamp": 1455191480}\] '

 &gt; nix-cli importmulti '\[{"scriptPubKey": {"address": "&lt;my address&gt;"}, "timestamp": 1455191478}\]' '{"rescan": false}'

 La respuesta es una matriz con el mismo tamaño que la entrada que tiene el resultado de ejecución:

 \[{"éxito": verdadero}, {"éxito": falso, "error": {"código": -1, "mensaje": "Error interno del servidor"}}, ...\]

*  importprivkey "privkey" \("label"\): \(reescanear\) Agrega una clave privada \(tal como la devuelve dumpprivkey\) a su billetera. Requiere una nueva copia de seguridad de la billetera

 **Argumentos:**

 1. "privkey" \(cadena, requerida\) La clave privada \(ver dumpprivkey\)

 2. "label" \(cadena, opcional, por defecto = ""\) Una etiqueta opcional

 3. “rescan” \(booleano, opcional, predeterminado = verdadero\) Vuelva a escanear la billetera para transacciones

 **Nota:** esta llamada puede tardar minutos en completarse si el reescaneo es verdadero, durante ese tiempo, otras llamadas rpc pueden informar que la clave importada existe pero las transacciones relacionadas aún faltan, lo que lleva a saldos temporalmente incorrectos / falsos y salidas no gastadas hasta que se completa el reescaneo.

 **Ejemplos:**

 Volcar una clave privada:

 &gt; nix-cli dumpprivkey "myaddress"

 Importa la clave privada con reescaneo:

 &gt; nix-cli importprivkey "mykey"

 Importar usando una etiqueta y sin volver a escanear:

 &gt; nix-cli importprivkey "mykey" "prueba" falso

 Importar usando la etiqueta en blanco predeterminada y sin volver a escanear:

 &gt; nix-cli importprivkey "mykey" "" false

 Como una llamada JSON-RPC:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "importprivkey", "params": \["mykey", "testing", false\]} '-H' content-type text / plain; ' http://127.0.0.1:8332/

*  importprunedfunds: Importa fondos sin volver a escanear. La dirección o secuencia de comandos correspondiente se debe incluir previamente en la billetera. Dirigido a billeteras podadas. El usuario final es responsable de importar transacciones adicionales que luego gastan los resultados importados o vuelven a explorar después del punto en la cadena de bloques en que se incluye la transacción

 **Argumentos:**

 1. "rawtransaction" \(cadena, requerida\) Una transacción sin procesar en hexadecimal que financia una dirección ya existente en wallet

 2. "txoutproof" \(cadena, requerida\) La salida hexadecimal de gettxoutproof que contiene la transacción

*  importpubkey "pubkey" \("label" rescan\): agrega una clave pública \(en hexadecimal\) que se puede ver como si estuviera en su billetera pero no se puede usar para gastar. Requiere una nueva copia de seguridad de la billetera

 **Argumentos:**

 1. "pubkey" \(cadena, requerida\) La clave pública codificada en hexadecimal

 2. "label" \(cadena, opcional, por defecto = ""\) Una etiqueta opcional

 3. “rescan” \(booleano, opcional, predeterminado = verdadero\) Vuelva a escanear la billetera para transacciones

 **Nota:** Esta llamada puede tardar minutos en completarse si el reescaneo es verdadero, durante ese tiempo, otras llamadas rpc pueden informar que existe la clave pública importada pero las transacciones relacionadas aún faltan, lo que lleva a saldos temporalmente incorrectos / falsos y salidas no gastadas hasta que se completa el reescaneo.

 **Ejemplos:**

 Importar una clave pública con reescanear:

 &gt; nix-cli importpubkey "mypubkey"

 Importar usando una etiqueta sin volver a escanear:

 &gt; nix-cli importpubkey "mypubkey" "testing" false

 Como una llamada JSON-RPC:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "importpubkey", "params": \["mypubkey", "testing", false\]} '-H' content-type: text / plain; ' http://127.0.0.1:8332/

*  importwallet "filename": Importa claves de un archivo de volcado de billetera \(ver dumpwallet\). Requiere una nueva copia de seguridad de billetera para incluir claves importadas

 **Argumentos:**

 1. "filename" \(cadena, requerido\) El archivo de billeteraExamples:

 Volcar la billetera:

 &gt; nix-cli dumpwallet "prueba"

 Importar la billetera:

 &gt; nix-cli importwallet "prueba"

 Importar utilizando la llamada json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "importwallet", "params": \["test"\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  keypoolrefill \(newsize\): Rellena el conjunto de claves. Requiere que la frase de contraseña de billetera se configure con la llamada de frase de contraseña de billetera

 **Argumentos:**

 1. “newsize” \(numérico, opcional, predeterminado = 100\) El nuevo tamaño del conjunto de claves

 **Ejemplos:**

 &gt; nix-cli keypoolrefill

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "keypoolrefill", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/

 cantidad de "dirección" de asignación de arrendamiento \("comentario" "comentario\_a" restar tarifa del monto reemplazable conf\_target "estimación\_modo"\) Arrenda una cantidad de nix a una determinada dirección para apostar. Requiere que la frase de contraseña de billetera se configure con la llamada de frase de contraseña de billetera.

 **Argumentos:**

 1. "lease address" \(cadena, requerida\) La dirección nix a la que se arriendan las apuestas.

 2. “ammount" \(numérico o cadena, requerido\) El monto en NIX para enviar. eg 0.1

 3. "fee percentage" \(numérico, opcional\) El porcentaje para permitir que el delegador tome. ej. 11.9 \(11.9%\)

 4. "reward address of the lease percentage" \(cadena, opcional\) La dirección nix para forzar la participación en las tarifas de arrendamiento.

 5. "comment" \(cadena, opcional\) Un comentario utilizado para almacenar para qué sirve la transacción. Esto no es parte de la transacción, solo se guarda en su billetera.

 6. "comment\_to" \(cadena, opcional\) Un comentario para almacenar el nombre de la persona u organización a la que está enviando la transacción. Esto no es parte de la transacción, solo se guarda en su billetera.7. subtractfeefromamount \(boolean, optional, default=false\) The fee will be deducted from the amount being sent. The recipient will receive less nix than you enter in the amount field.

 8. “reemplazable” \(booleano, opcional\) Permitir que esta transacción sea reemplazada por una transacción con tarifas más altas a través de BIP 125

 9. “conf\_target” \(numérico, opcional\) Objetivo de confirmación \(en bloques\)

 10. "estimar\_modo" \(cadena, opcional, predeterminado = DESACTIVADO\) El modo de estimación de tarifa debe ser uno de:

  "UNSET"

  "ECONOMIC"

  "CONSERVATIVE"

 **Resultado:**

 "txid" \(cadena\) El ID de la transacción.

 **Ejemplos:**

 &gt; nix-cli leasestaking "Nf72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 150

 &gt; nix-cli leasestaking "Nf72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 150 11.9 "NG72Sfpbz1BLpXFHz9m3CdqATR44JDaydd"

*  listaccounts \(minconf include\_watchonly\) DEPRECATED: Devuelve el objeto que tiene nombres de cuenta como claves, saldos de cuenta como valores

 **Argumentos:**

 1. “minconf” \(numérico, opcional, predeterminado = 1\) Solo incluya transacciones con al menos esta cantidad de confirmaciones

 2. “include\_watchonly” \(bool, opcional, default = false\) Incluye saldos en direcciones de solo vigilancia \(ver 'importaddress'\)

 **Resultado:**

 {\(object json donde las claves son nombres de cuenta y los valores son saldos numéricos

   "account": x.xxx, \(numérico\) El nombre de la propiedad es el nombre de la cuenta y el valor es el saldo total de la cuenta. ...

 }

 **Ejemplos:**

 Enumere los saldos de las cuentas donde haya al menos 1 confirmación:

 &gt; nix-cli listaccounts

 Lista de saldos de cuenta, incluidas las transacciones de confirmación cero:

 &gt; nix-cli listaccounts 0

 Lista de saldos de cuenta para 6 o más confirmaciones:

 &gt; nix-cli listaccounts 6

 Como json rpc call:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "listaccounts", "params": \[6\]}' -H 'content -type: text / plain; ' http://127.0.0.1:8332/

*  listaddressgroupings: Enumera grupos de direcciones a las que se ha hecho pública su propiedad común mediante el uso común como entradas o como el cambio resultante en transacciones pasadas

 **Resultado:**

 \[

   \[

     \[

       "address", \(string\) El monto de la dirección nix, \(numérico\) El monto en NIX

       "address" \(cadena, opcional\) DEPRECADO. La cuenta

     \]

     , ...

   \]

   , ...

 \]

 **Ejemplos:**

 &gt; nix-cli listaddressgroupings&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listaddressgroupings", "params": \[\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  listlockunspent: Devuelve la lista de salidas temporalmente inutilizables. Vea la llamada lockunspent para bloquear y desbloquear transacciones para gastos

 **Resultado:**

 \[

   {

     "txid": "transactionid", \(string\) El ID de la transacción bloqueado

     "vout": n \(numérico\) El valor de vout

   }

   , ...

 \]

 **Ejemplos:**

 Listar las transacciones no gastadas:

 &gt; nix-cli listunspent

 Bloquear una transacción no gastada:

 &gt; nix-cli lockunspent false "\[{\" txid \ ": \" a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0 \ ", \" vout \ ": 1}\]"

 Listar las transacciones bloqueadas:

 &gt; nix-cli listlockunspent

 Desbloquee la transacción nuevamente:

 &gt; nix-cli lockunspent true "\[{\" txid \ ": \" a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0 \ ", \" vout \ ": 1}\]"

 Como una llamada json rpc

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "listlockunspent", "params": \[\]}' -H 'content- type: text / plain; ' http://127.0.0.1:8332/listreceivedbyaccount \(minconf include\_empty include\_watchonly\) DEPRECATED. List balances by account.

 **Argumentos:**

 1. “minconf” \(numérico, opcional, predeterminado = 1\) El número mínimo de confirmaciones antes de que se incluyan los pagos.

 2. “include\_empty” \(bool, opcional, predeterminado = falso\) Si se incluyen las cuentas que no han recibido ningún pago.

 3. “include\_watchonly” \(bool, opcional, default = false\) Si se incluyen direcciones de solo vigilancia \(ver 'importaddress'\).

 **Resultado:**

 \[

   {

     "implicaWatchonly": verdadero, \(bool\) Solo se devuelve si las direcciones importadas estaban involucradas en la transacción

     "account": "nombre de cuenta", \(cadena\) El nombre de cuenta de la cuenta receptora

     "ammount": x.xxx, \(numérico\) El monto total recibido por las direcciones con esta cuenta

     "confirmations": n, \(numérico\) El número de confirmaciones de la transacción más reciente incluida

     "label": "label" \(cadena\) Un comentario para la dirección / transacción, si corresponde

   }

   , ...

 \]

 **Ejemplos:**

 &gt; nix-cli listreceivedbyaccount

 &gt; nix-cli listreceivedbyaccount 6 verdadero

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "listreceivedbyaccount", "params": \[6, true, true\]}' -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  listreceivedbyaddress \(minconf include\_empty include\_watchonly\): Lista de saldos por dirección de recepción

 **Argumentos:**

 1. “minconf” \(numérico, opcional, predeterminado = 1\) El número mínimo de confirmaciones antes de que se incluyan los pagos.

 2. “include\_empty” \(bool, opcional, predeterminado = falso\) Si se incluyen direcciones que no han recibido ningún pago.

 3. “include\_watchonly” \(bool, opcional, default = false\) Si se incluyen direcciones de solo vigilancia \(ver 'importaddress'\).

 **Resultado:**

 \[

   {

     "implicaWatchonly": verdadero, \(bool\) Solo se devuelve si las direcciones importadas estaban involucradas en la transacción

     "address": "dirección de recepción", \(cadena\) La dirección de recepción

     "account": "accountname", \(string\) DEPRECATED. La cuenta de la dirección de recepción. La cuenta predeterminada es "".

     "quantity": x.xxx, \(numérico\) La cantidad total en NIX recibida por la dirección

     "confirmatopns": n, \(numérico\) El número de confirmaciones de la transacción más reciente incluida

     "label": "label", \(string\) Un comentario para la dirección / transacción, si corresponde

     "txids": \[

     n, \(numérico\) Los identificadores de las transacciones recibidas con la dirección

     ...

   \]

 }

 , ...

 \]

 **Ejemplos:**

 &gt; lista nix-cli recibida por dirección

 &gt; nix-cli listreceivedbyaddress 6 true

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method":"listreceivedbyaddress", "params": \[6, true, true\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  listsinceblock \("blockhash" target\_confirmations include\_watchonly include\_removed\): Obtenga todas las transacciones en bloques desde el bloque \[blockhash\], o todas las transacciones si se omiten. Si "blockhash" ya no es parte de la cadena principal, se incluyen las transacciones desde el punto de bifurcación en adelante

 Además, si se establece include\_removed, las transacciones que afectan a la billetera que se eliminaron se devuelven en la matriz "eliminada".

 **Argumentos:**

 1. "blockhash" \(cadena, opcional\) El hash de bloque para enumerar transacciones desde

 2. “target\_confirmations”: \(numérico, opcional, predeterminado = 1\) Devuelve el hash del enésimo bloque de la cadena principal. p.ej. 1 significaría el mejor hash de bloque. Nota: esto no se usa como filtro, sino que solo afecta \[lastblock\] en el valor de retorno

 3. “include\_watchonly”: \(bool, opcional, default = false\) Incluye transacciones a direcciones de solo vigilancia \(ver 'importaddress'\)

 4. “include\_removed”: \(bool, opcional, default = true\) Muestra las transacciones que se eliminaron debido a una reorganización en la matriz "eliminada"

 \(no se garantiza que funcione en nodos podados\)

 **Resultado:**

 {

   "transactions": \[

   "account": "nombre de cuenta", \(cadena\) DEPRECATED. El nombre de cuenta asociado con la transacción. Será "" para la cuenta predeterminada.

   "address": "address", \(string\) La dirección nix de la transacción. No está presente para las transacciones de movimiento \(categoría = movimiento\).

   "category": "enviar \| recibir", \(cadena\) La categoría de transacción. 'enviar' tiene cantidades negativas, 'recibir' tiene cantidades positivas.

   "ammount": x.xxx, \(numérico\) La cantidad en NIX. Esto es negativo para la categoría 'enviar' y para la categoría 'mover' para movimientos salientes. Es positivo para la categoría 'recibir' y para la categoría 'mover' para fondos entrantes.

   "vout": n, \(numérico\) el valor de vout

 "fees": x.xxx, \(numérico\) El monto de la tarifa en NIX. Esto es negativo y solo está disponible para la categoría de 'envío' de transacciones.

   "confirmations": n, \(numérico\) El número de confirmaciones para la transacción. Disponible para la categoría de transacciones "enviar" y "recibir". Cuando es &lt;0, significa que la transacción entró en conflicto hace muchos bloques.

   "blockhash": "hashvalue", \(string\) El hash de bloque que contiene la transacción. Disponible para la categoría de transacciones "enviar" y "recibir".

   "blockindex": n, \(numérico\) El índice de la transacción en el bloque que lo incluye. Disponible para la categoría de transacciones "enviar" y "recibir".

   "blocktime": xxx, \(numérico\) El tiempo de bloqueo en segundos desde la época \(1 de enero de 1970 GMT\).

   "txid": "transactionid", \(cadena\) El ID de la transacción. Disponible para la categoría de transacciones "enviar" y "recibir".

   "time": xxx, \(numérico\) El tiempo de transacción en segundos desde la época \(1 de enero de 1970 GMT\).

   "timereceived": xxx, \(numérico\) El tiempo recibido en segundos desde la época \(1 de enero de 1970 GMT\). Disponible para la categoría de transacciones "enviar" y "recibir".

   "bip125-reemplazable": "sí \| no \| desconocido", \(cadena\) Si esta transacción podría ser reemplazada debido a BIP125 \(reemplazo por tarifa\); puede ser desconocido para transacciones no confirmadas que no están en el mempool

   "abandonados": xxx, \(bool\) 'verdadero' si la transacción ha sido abandonada \(las entradas son confiables\). Solo disponible para la categoría 'enviar' de transacciones.

   "comment": "...", \(string\) Si un comentario está asociado con la transacción.

   "label": "label" \(cadena\) Un comentario para la dirección / transacción, si corresponde

   "a": "...", \(cadena\) Si un comentario a está asociado con la transacción.

   \],

   "eliminado": \[

   &lt;estructura es la misma que "transacciones" arriba, solo presente si include\_removed = true&gt;

 **Nota:** las transacciones que se leyeron en la cadena activa aparecerán tal cual en esta matriz y, por lo tanto, pueden tener un recuento de confirmación positivo.

   \],

  "lastblock": "lastblockhash" \(cadena\) El hash del bloque \(target\_confirmations-1\) del mejor bloque de la cadena principal. Por lo general, esto se usa para retroalimentar las listas desde el bloque la próxima vez que lo llame. Por lo tanto, generalmente usaría un target\_confirmations de say 6, por lo que se le volverá a notificar continuamente de las transacciones hasta que hayan alcanzado 6 confirmaciones más las nuevas

 }

 **Ejemplos:**

 &gt; nix-cli listsinceblock

 &gt; nix-cli listsinceblock "000000000000000bacf66f7497b7dc45ef753ee9a7d38571037cdb1a57f663ad" 6

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "listsinceblock", "params": \["000000000000000bacf66f7497b7dc45ef753ee9a7d38571037cdb1a57f66}} -H 'content-type: text / plain;' http://127.0.0.1:8332/

*  listtransactions \("account" account tame include\_watchonly\): Devuelve hasta 'contar' las transacciones más recientes omitiendo las primeras 'de' transacciones para la cuenta 'cuenta'

 **Argumentos:**

 1. "account" \(cadena, opcional\) DEPRECADO. El nombre de la cuenta. Debiera ser "\*".

 2. “count” \(numérico, opcional, predeterminado = 10\) El número de transacciones a devolver

 3. “miss” \(numérico, opcional, predeterminado = 0\) El número de transacciones a omitir

 4. “include\_watchonly” \(bool, opcional, default = false\) Incluye transacciones a direcciones de solo vigilancia \(ver 'importaddress'\)

 **Resultado:**

 \[

   {

     "account": "nombre de cuenta", \(cadena\) DEPRECATED. El nombre de cuenta asociado con la transacción. Será "" para la cuenta predeterminada.

     "address": "address", \(string\) La dirección nix de la transacción. No está presente para las transacciones de movimiento \(categoría = movimiento\).

     "category": "enviar \| recibir \| mover", \(cadena\) La categoría de transacción. 'mover' es una transacción local \(fuera de blockchain\) entre cuentas, y no está asociada con una dirección, ID de transacción o bloque. Las transacciones 'enviar' y 'recibir' están asociadas con una dirección, id de transacción y detalles de bloque.

 "quantity": x.xxx, \(numérico\) La cantidad en NIX. Esto es negativo para la categoría 'enviar' y para la categoría 'mover' para movimientos salientes. Es positivo para la categoría 'recibir' y para la categoría 'mover' para fondos entrantes.

     "label": "label", \(string\) Un comentario para la dirección / transacción, si corresponde

     "vout": n, \(numérico\) el valor de vout

     "tarifa": x.xxx, \(numérico\) El monto de la tarifa en NIX. Esto es negativo y solo está disponible para la categoría de 'envío' de transacciones.

     "confirmations": n, \(numérico\) El número de confirmaciones para la transacción. Disponible para la categoría de transacciones "enviar" y "recibir". Las confirmaciones negativas indican que la transacción entra en conflicto con la cadena de bloques.

     "confiable": xxx, \(bool\) Si consideramos que los resultados de esta transacción no confirmada son seguros para gastar.

     "blockhash": "hashvalue", \(string\) El hash de bloque que contiene la transacción. Disponible para la categoría de transacciones "enviar" y "recibir".

     "blockindex": n, \(numérico\) El índice de la transacción en el bloque que lo incluye. Disponible para la categoría de transacciones "enviar" y "recibir".

     "blocktime": xxx, \(numérico\) El tiempo de bloqueo en segundos desde la época \(1 de enero de 1970 GMT\).

     "txid": "transactionid", \(cadena\) El ID de la transacción. Disponible para la categoría de transacciones "enviar" y "recibir".

     "time": xxx, \(numérico\) El tiempo de transacción en segundos desde la época \(medianoche del 1 de enero de 1970 GMT\).

     "timereceived": xxx, \(numérico\) El tiempo recibido en segundos desde la época \(medianoche del 1 de enero de 1970 GMT\). Disponible para la categoría de transacciones "enviar" y "recibir".

     "comment": "...", \(string\) Si un comentario está asociado con la transacción.

     "otheraccount": "nombre de cuenta", \(string\) DEPRECATED. Para la categoría de transacciones "mover", la cuenta de la que provienen los fondos \(para recibir fondos, montos positivos\), o a la que se destina \(para enviar fondos, montos negativos\).

     "bip125-reemplazable": "sí \| no \| desconocido", \(cadena\) Si esta transacción podría ser reemplazada debido a BIP125 \(reemplazo por tarifa\); puede ser desconocido para transacciones no confirmadas que no están en el mempool

     "abandoneds": xxx \(bool\) 'verdadero' si la transacción ha sido abandonada \(las entradas son confiables\). Solo disponible para la categoría 'enviar' de transacciones.

   }

 \]

 **Ejemplos:**

 Enumere las 10 transacciones más recientes en los sistemas:

 &gt; nix-cli listtransactions

 Lista de transacciones de 100 a 120:

 &gt; nix-cli listtransactions "\*" 20100

 Como una llamada json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "listtransactions", "params": \["\*", 20, 100\] } '-H' tipo de contenido: text / plain; ' http://127.0.0.1:8332/

*  listunspent \(minconf maxconf \["addresses", ...\] \[include\_unsafe\] \[query\_options\]\) Devuelve una matriz de salidas de transacciones no gastadas con confirmaciones entre minconf y maxconf \(inclusive\). Opcionalmente, filtre para incluir solo txouts pagados a direcciones específicas

 **Argumentos:**

 1. “minconf” \(numérico, opcional, predeterminado = 1\) Las confirmaciones mínimas para filtrar

 2. “maxconf” \(numérico, opcional, predeterminado = 9999999\) Las confirmaciones máximas para filtrar

 3. "addresses" \(cadena\) Una matriz json de direcciones nix para filtrar

 \[

   "address" \(cadena\) dirección nix

   , ...

 \]

 4. “include\_unsafe” \(bool, opcional, default = true\) Incluye salidas que no son seguras para gastar Vea la descripción del atributo "safe" a continuación.

 5. “query\_options” \(json, opcional\) JSON con opciones de consulta

 {

   "minimumAmount" \(numérico o cadena, predeterminado = 0\) Valor mínimo de cada UTXO en NIX

 "maximumAmount" \(numérico o cadena, predeterminado = ilimitado\) Valor máximo de cada UTXO en NIX

  "maximumCount" \(numérico o cadena, predeterminado = ilimitado\) Número máximo de UTXO

  "minimumSumAmount" \(numérico o cadena, predeterminado = ilimitado\) Valor de suma mínima de todos los UTXO en NIX

 }

 **Resultado:**

 \[\(matriz de objeto json\)

   {

     "txid": "txid", \(cadena\) el ID de la transacción

     "vout": n, \(numérico\) el valor de vout

     "address": "address", \(string\) la dirección nix

     "account": "cuenta", \(string\) DEPRECATED. La cuenta asociada o "" para la cuenta predeterminada

     "scriptPubKey": "clave", \(cadena\) la clave del script

     "ammount": x.xxx, \(numérico\) la cantidad de salida de la transacción en NIX

     "confirmations": n, \(numérico\) El número de confirmaciones

     "redeemScript": n \(cadena\) El canje de Script si scriptPubKey es P2SH

     "gastable": xxx, \(bool\) Si tenemos las claves privadas para gastar esta salida

     "solucionable": xxx, \(bool\) Si sabemos cómo gastar esta salida, ignorando la falta de claves

     "safe": xxx \(bool\) Si esta salida se considera segura para gastar. Las transacciones no confirmadas de claves externas y las transacciones de reemplazo no confirmadas se consideran inseguras y no son elegibles para gastar en transacciones de recaudación de fondos y direcciones de envío.

   }

   , ...

 \]

 **Ejemplos:**

 &gt; nix-cli listunspent

 &gt; nix-cli listunspent 6 9999999 "\[\" 1PGFqEzfmQch1gKD3ra4k18PNj3tTUUSqg \ ", \" 1LtvqCaApEdUGFkpKMM4MstjcaL4dKg8SP \ "\]"&gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listunspent", "params": \[6, 9999999 "\[\"1PGFqEzfmQch1gKD3ra4k18PNj3tTUUSqg\",\"1LtvqCaApEdUGFkpKMM4MstjcaL4dKg8SP\"\]"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

 &gt; nix-cli listunspent 6 9999999 '\[\]' true '{ "minimumAmount": 0.005 }'

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "listunspent", "params": \[6, 9999999, \[\] , true, { "minimumAmount": 0.005 } \] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  listwallets Devuelve una lista de billeteras cargadas actualmente. Para obtener información completa sobre la billetera, use "getwalletinfo"

 **Resultado:**

 \[\(matriz de cadenas json\)

   "walletname" \(cadena\) el nombre de la billetera

   ...

 \]

 **Ejemplos:**

 &gt; wallets nix-cli

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "listwallets", "params": \[\]}' -H 'content- tipo: texto / sin formato; ' http://127.0.0.1:8332/

*  lockunspent unlock \(\[{"txid": "txid", "vout": n}, ...\]\) Actualiza la lista de salidas temporalmente no transferibles. Bloquear temporalmente \(desbloquear = falso\) o desbloquear \(desbloquear = verdadero\) salidas de transacciones especificadas. Si no se especifican salidas de transacciones al desbloquear, todas las salidas de transacciones bloqueadas actuales se desbloquean. Una salida de transacción bloqueada no se elegirá mediante la selección automática de monedas, al gastar nix. Los bloqueos se almacenan solo en la memoria. Los nodos comienzan con cero salidas bloqueadas, y la lista de salidas bloqueadas siempre se borra \(en virtud de la salida del proceso\) cuando un nodo se detiene o falla. Vea también la lista de llamadas no gastadas

 **Argumentos:**

 1. “unlock” \(boolean, required\) Whether to unlock \(true\) or lock \(false\) the specified transactions

 2. "transactions" \(string, optional\) A json array of objects. Each object the txid \(string\) vout \(numeric\)

 \[ \(json array of json objects\)

 {

     "txid": "id", \(string\) El ID de la transacción

     "vout": n \(numérico\) El número de salida

   }

   , ...

 \]

 **Resultado:**

 true \| false \(booleano\) Si el comando fue exitoso o no

 **Ejemplos:**

 Listar las transacciones no gastadas

 &gt; nix-cli listunspent

 Bloquear una transacción no gastada

 &gt; nix-cli lockunspent false "\[{\" txid \ ": \" a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0 \ ", \" vout \ ": 1}\]"

 Listar las transacciones bloqueadas:

 &gt; nix-cli listlockunspent

 Desbloquee la transacción nuevamente:

 &gt; nix-cli lockunspent true "\[{\" txid \ ": \" a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0 \ ", \" vout \ ": 1}\]"

 Como una llamada json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "lockunspent", "params": \[false, "\[\[\ \ txid \ ": \" a08e6907dbbd3d809776dbfc5d82e371b764ed838b5655e72f463568df1aadf0 \ ", \" vout \ ": 1}\]"\]} '-H' content-type: text / plain; ' http://127.0.0.1:8332/manageaddressbook "action" "address" \("label" "purpose"\) Manage the address book.

 **Argumentos:**

 1. "action" \(string, required\) 'add / edit / del / info / newsend' La acción a realizar.

 2. "address" \(cadena, requerida\) La dirección a afectar.

 3. "tag" \(cadena, opcional\) Etiqueta opcional.

 4. "purpose" \(cadena, opcional\) Etiqueta de propósito opcional.

*  mover "fromaccount" "toaccount" cantidad \(minconf "comentario"\) DEPRECATED: Mueva una cantidad específica de una cuenta en su billetera a otra

 **Argumentos:**

 1. "fromaccount" \(cadena, requerida\) El nombre de la cuenta para mover fondos. Puede ser la cuenta predeterminada con "".

 2. "toaccount" \(cadena, requerida\) El nombre de la cuenta a la que mover los fondos. Puede ser la cuenta predeterminada con "".

 3. “quantity”\(numérica\) Cantidad de NIX para mover entre cuentas.

 4. \(ficticio\) \(numérico, opcional\) Ignorado. Restos de compatibilidad con versiones anteriores.

 5. "comentario" \(cadena, opcional\) Un comentario opcional, almacenado solo en la billetera.

 **Resultado:**

 true \| false \(booleano\) verdadero si tiene éxito.

 **Ejemplos:**

 Mueva 0.01 NIX de la cuenta predeterminada a la cuenta denominada tabby:

 &gt; movement nix-cli "" "tabby" 0.01

 Mueve 0.01 NIX timotei a akiko con un comentario y los fondos tienen 6 confirmaciones:

 &gt; movement nix-cli "timotei" "akiko" 0.01 6 "¡feliz cumpleaños!"

 Como una llamada json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "move", "params": \["timotei", "akiko", 0.01, 6, "¡feliz cumpleaños!"\]} '-H' content-type: text / plain; ' http://127.0.0.1:8332/

*  removeprunedfunds: "txid" Elimina la transacción especificada de la billetera. Destinado a su uso con billeteras podadas y como acompañante para importar fondos podados. Esto afectará los saldos de billetera

 **Argumentos:**

 1. "txid" \(cadena, requerida\) La identificación codificada en hexadecimal de la transacción que está eliminando

 **Ejemplos:**

 &gt; nix-cli removeprunedfunds "a8d0c0184dde994a09ec054286f1ce581bebf46446a512166eae7628734ea0a5"

 Como una llamada JSON-RPC

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "removeprunedfunds", "params": \["a8d0c0184dde994a09ec054286f1ce581bebf46446a512166ea05e5" 'content-type: text / plain;' http://127.0.0.1:8332/

*  rescanblockchain \("start\_height"\) \("stop\_height"\): Vuelva a explorar la cadena de bloques local para transacciones relacionadas con la billetera

 **Argumentos:**

 1. Altura de bloque "start\_height" \(numérico, opcional\) donde debe comenzar el reescaneo

 2. "stop\_height" \(numérico, opcional\) la altura del último bloque que debe escanearse

 **Resultado:**

 {

   "start\_height" \(numérico\) La altura del bloque donde ha comenzado el reescaneo. Si se omite, el reescaneo comenzó desde el bloque de génesis.

   "stop\_height" \(numérico\) La altura del último bloque reescaneado. Si se omite, el reescaneo se detuvo en la punta de la cadena.

 }

 **Ejemplos:**

 &gt; nix-cli rescanblockchain 100000 120000

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "rescanblockchain", "params": \[100000, 120000\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

 p, li { white-space: pre-wrap; }

*  reservebalance reserve \(ammount\) Reserve es verdadero o falso para activar o desactivar la reserva de saldo. La cantidad es real y se redondea a centavo. Establecer el monto de reserva que no participa en la protección de la red. Si no se proporcionan parámetros, se imprime la configuración actual. La billetera debe estar desbloqueada para modificar
*  sendfrom "fromaccount" "toaddress" amount \(minconf "comment" "comment\_to"\) DEPRECATED \(use sendtoaddress\): Envió una cantidad desde una cuenta a una dirección nix. Requiere que la frase de contraseña de billetera se configure con la llamada de frase de contraseña de billetera

 **Argumentos:**

 1. "fromaccount" \(cadena, requerida\) El nombre de la cuenta desde la que se envían los fondos. Puede ser la cuenta predeterminada con "". La especificación de una cuenta no influye en la selección de monedas, pero sí asocia la transacción recién creada con la cuenta, por lo que el cálculo del saldo de la cuenta y el historial de transacciones pueden reflejar el gasto.

 2. "toaddress" \(cadena, requerida\) La dirección nix a la que enviar fondos.

 3. “ammount” \(numérico o cadena, requerido\) El monto en NIX \(la tarifa de transacción se agrega en la parte superior\).

 4. “minconf” \(numérico, opcional, predeterminado = 1\) Utilice solo fondos con al menos esta cantidad de confirmaciones.

 5. "comment" \(cadena, opcional\) Un comentario utilizado para almacenar para qué sirve la transacción. Esto no es parte de la transacción, solo se guarda en su billetera.

 6. "comment\_to" \(cadena, opcional\) Un comentario opcional para almacenar el nombre de la persona u organización a la que está enviando la transacción. Esto no es parte de la transacción, solo se guarda en su billetera.

 **Resultado:**

 "txid" \(cadena\) El ID de la transacción.

 **Ejemplos:**

 Enviar 0.01 NIX desde la cuenta predeterminada a la dirección, debe tener al menos 1 confirmación:

 &gt; envío nix-cli desde "" "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.01

 Envíe 0.01 de la cuenta tabby a la dirección indicada, los fondos deben tener al menos 6 confirmaciones:

 &gt; send nix-cli de "tabby" "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.01 6 "donación" "sella el puesto avanzado"As a json rpc call

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "sendfrom", "params": \["tabby", "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd", 0.01, 6, "donation", "seans outpost"\] }' -H 'content-type: text/plain;' http://127.0.0.1:8332/

*  sendmany "fromaccount" {"address": cantidad, ...} \(minconf "comentario" \["address", ...\] reemplazable conf\_target "Estimate\_mode"\) Enviar varias veces. Las cantidades son números de coma flotante de doble precisión. Requiere que la frase de contraseña de billetera se configure con la llamada de frase de contraseña de billetera

 **Argumentos:**

 1. "fromaccount" \(cadena, requerida\) DEPRECATED. La cuenta desde donde enviar los fondos. Debe ser "" para la cuenta predeterminada

 2. "quantities" \(cadena, requerida\) Un objeto json con direcciones y cantidades

 {

   "address": cantidad \(numérica o cadena\) La dirección nix es la clave, la cantidad numérica \(puede ser cadena\) en NIX es el valor

   , ...

 }

 3. “minconf” \(numérico, opcional, predeterminado = 1\) Utilice solo el saldo confirmado al menos esto muchas veces.

 4. "comment" \(cadena, opcional\) Un comentario

 5. “subtractfeefrom” \(matriz, opcional\) Una matriz json con direcciones. La tarifa se deducirá igualmente del monto de cada dirección seleccionada. Esos destinatarios recibirán menos nix de lo que ingresas en su campo de monto correspondiente. Si no se especifican direcciones aquí, el remitente paga la tarifa.

   \[

     "address" \(cadena\) Restar tarifa de esta dirección

     , ...

   \]

 6. “reemplazable” \(booleano, opcional\) Permitir que esta transacción sea reemplazada por una transacción con tarifas más altas a través de BIP 125

 7. “conf\_target” \(numérico, opcional\) Objetivo de confirmación \(en bloques\)

 8. "estimar\_modo" \(cadena, opcional, predeterminado = DESACTIVADO\) El modo de estimación de tarifa debe ser uno de:

 "UNSET"

 "ECONOMICAL"

 "CONSERVATIVE"

 **Resultado:**

 "txid" \(cadena\) La identificación de la transacción para el envío. Solo se crea 1 transacción independientemente del número de direcciones.

 **Ejemplos:**

 Envíe dos cantidades a dos direcciones diferentes:

 &gt; nix-cli sendmany "" "{\" 1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX \ ": 0.01, \" 1353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz \ ": 0.02}"

 Envíe dos cantidades a dos direcciones diferentes configurando la confirmación y el comentario:

 &gt; nix-cli sendmany "" "{\" 1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX \ ": 0.01, \" 1353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz \ ": 0.02}" 6 "prueba"

 Envíe dos cantidades a dos direcciones diferentes, reste la tarifa de la cantidad:

 &gt; Sendmany nix-cli "" "{\" 1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX \ ": 0,01, \" 1353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz \ ": 0,02}" 1 "" "\[\" 1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX \ "\ "1353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz \"\]"

 Como una llamada json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "sendmany", "params": \["", {"1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX": 0.01, "1353tsE8YMTA4EuV7dgUXGjNFf9KpVvKHz": 0.02}, 6, "testing"\]} '-H' content-type: text / plain; ' http://127.0.0.1:8332/

*  sendtoaddress "address" ammount \("coment" "coment\_a" subtractfeefromammount replaceable conf\_target "estimate\_mode"\): Enviar una cantidad a una dirección determinada. Requiere que la frase de contraseña de billetera se configure con la llamada de frase de contraseña de billetera.

 **Argumentos:**

 1. "address" \(cadena, requerida\) La dirección nix a la que enviar.

 2. "ammount" \(numérico o cadena, requerido\) El monto en NIX para enviar. eg 0.1

 3. "comment" \(cadena, opcional\) Un comentario utilizado para almacenar para qué sirve la transacción. Esto no es parte de la transacción, solo se guarda en su billetera.

 4. "comment\_to" \(cadena, opcional\) Un comentario para almacenar el nombre de la persona u organización a la que está enviando la transacción. Esto no es parte de la transacción, solo se guarda en su billetera.

 5. “subtractfeefromamount” \(boolean, opcional, default = false\) La tarifa se deducirá de la cantidad que se envía. El destinatario recibirá menos nix de lo que ingresa en el campo de cantidad.

 6. “reemplazable” \(booleano, opcional\) Permitir que esta transacción sea reemplazada por una transacción con tarifas más altas a través de BIP 125

 7. “conf\_target” \(numérico, opcional\) Objetivo de confirmación \(en bloques\)

 8. "estimar\_modo" \(cadena, opcional, predeterminado = DESACTIVADO\) El modo de estimación de tarifa debe ser uno de:

  "UNSTIL"

  "ECONOMIC"

  "CONSERVATIVE"

 **Resultado:**

 "txid" \(cadena\) El ID de la transacción.

 **Ejemplos:**

 &gt; nix-cli sendtoaddress "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.1

 &gt; nix-cli sendtoaddress "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.1 "donación" "establece avanzada"

 &gt; nix-cli sendtoaddress "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 0.1 "" "" verdadero

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "sendtoaddress", "params": \["1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd", 0.1, "donate"," establece el puesto avanzado "\]} '-H' content-type: text / plain; ' http://127.0.0.1:8332/

*  setaccount "address" "account" DEPRECATED: Establece la cuenta asociada con la dirección dada

 **Argumentos:**

       1. "address" \(cadena, requerida\) La dirección nix que se asociará con una cuenta.

      2. "account" \(cadena, requerida\) La cuenta a la que se asigna la dirección.

 **Ejemplos:**

 &gt; cuenta seta nix-cli "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "tabby"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "setaccount", "params": \["1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX", "tabby"\] } '-H' content-type: text / plain; ' http://127.0.0.1:8332/

*  settxfee &lt;amount&gt;: Establezca la tarifa de transacción por kB. Sobrescribe el parámetro paytxfee

 **Argumentos:**

 1. “fee” \(numérico o cadena, requerido\) La tarifa de transacción en NIX / kB

 **Resultado:**

 true \| false \(booleano\) Devuelve verdadero si tiene éxito

 **Ejemplos:**

 &gt; nix-cli settxfee 0.00001

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "settxfee", "params": \[0.00001\]}' -H 'contenido -type: text / plain; ' http://127.0.0.1:8332/

*  signmessage "address" "message": Firme un mensaje con la clave privada de una dirección

 Requiere que la frase de contraseña de billetera se configure con la llamada de frase de contraseña de billetera.

 **Argumentos:**

 1. "address " \(cadena, requerida\) La dirección nix a usar para la clave privada.

 2. "message" \(cadena, requerido\) El mensaje para crear una firma.

 **Resultado:**

 "firm" \(cadena\) La firma del mensaje codificado en base 64

 **Ejemplos:**

 Desbloquee la billetera por 30 segundos:

 nix-cli walletpassphrase "mypassphrase" 30

 Crea la firma:

 veriffymessage nix-cli "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "mi mensaje"

 Verificar la firma:

 &gt; verifymessage nix-cli "1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX" "firma" "mi mensaje"

 Como json rpc:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "signmessage", "params": \["1D1ZrZNe3JUo7ZycKEYQQiQAWd9y54F4XX", "my message" \]} '-H' content-type: text / plain; ' http://127.0.0.1:8332/

*  walletlock: Elimina la clave de cifrado de la billetera de la memoria, bloqueando la billetera. Después de llamar a este método, deberá volver a llamar a walletpassphrase antes de poder llamar a cualquier método que requiera que la billetera esté desbloqueada

 **Ejemplos:**

 Establezca la frase de contraseña durante 2 minutos para realizar una transacción:

 &gt; nix-cli walletpassphrase "mi frase de contraseña" 120

 Realizar un envío \(requiere conjunto de frase de contraseña\):

 &gt; nix-cli sendtoaddress "1M72Sfpbz1BPpXFHz9m3CdqATR44Jvaydd" 1.0

 Borre la frase de contraseña ya que hemos terminado antes de que pasen 2 minutos:

 &gt; wallet nix-cli

 Como json rpc call:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "walletlock", "params": \[\]}' -H 'content- tipo: texto / sin formato; ' http://127.0.0.1:8332/

*  walletpassphrase &lt;passphrase&gt; &lt;timeout&gt; \[stakingonly\]: Almacena la clave de descifrado de billetera en la memoria durante segundos de 'tiempo de espera'. Esto es necesario antes de realizar transacciones relacionadas con claves privadas como enviar NIX

 **Argumentos:**

 1. "passphrase" \(cadena, requerida\) La frase de contraseña de la billetera

 2. “timestamp” \(numérico, requerido\) El tiempo para mantener la clave de descifrado en segundos. Limitado a un máximo de 1073741824 \(2 ^ 30\) segundos. Cualquier valor superior a 1073741824 segundos se establecerá en 1073741824 segundos.

 3. “stakingonly” \(bool, opcional\) Si es verdadero, las funciones de envío están deshabilitadas.

 **Nota:** La emisión del comando walletpassphrase mientras la billetera ya está desbloqueada establecerá un nuevo tiempo de desbloqueo que anula el anterior. Si \[stakingonly\] es verdadero y &lt;timeout&gt; es 0, la billetera permanecerá desbloqueada para el replanteo hasta que se vuelva a bloquear manualmente.

 **Ejemplos:**

 Desbloquee la billetera por 60 segundos:

 &gt; nix-cli walletpassphrase "mi frase de contraseña" 60

 Bloquee la billetera nuevamente \(antes de 60 segundos\):

 &gt; wallet nix-cli

 Desbloquee la billetera para apostar:

 &gt; nix-cli walletpassphrase "mi frase de contraseña" 0 verdadero

 Como json rpc call:

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "walletpassphrase", "params": \["mi frase de paso", 60\] } '-H' content-type: text / plain; ' http://127.0.0.1:8332/

*  walletpassphrasecambiar "oldpassphrase" "newpassphrase": Cambia la contraseña de wallet de 'oldpassphrase' a 'newpassphrase'

 **Argumentos:**

 1. "oldpassphrase" \(cadena\) La frase de contraseña actual

 2. "newpassphrase" \(cadena\) La nueva frase de contraseña

 **Ejemplos:**

 &gt; nix-cli walletpassphrasechange "old one" "new one"

 &gt; curl --user myusername --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "walletpassphrasechange", "params": \["old", "new one "\]} '-H' content-type: text / plain; ' [http://127.0.0.1:8332/](http://127.0.0.1:8332/)

