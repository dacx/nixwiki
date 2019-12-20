# Protocolo Fantasma

El protocolo NIX Ghost es un conjunto de elementos de privacidad cuidadosamente seleccionados, reunidos para brindar a los usuarios y desarrolladores las opciones que necesitan para garantizar no solo transacciones de monedas fungibles, sino también la privacidad de la red y la transmisión.

## Protocolo Sigma

Desarrollado por el equipo de [ZCoin](https://zcoin.io/), Sigma es un protocolo a prueba de conocimiento cero que esencialmente permite a los usuarios quemar y luego volver a emitir \(o acuñar\) monedas públicas sin historial adjunto. Sigma mejora sobre el Protocolo Zerocoin utilizado anteriormente al no requerir una "ceremonia de instalación" confiable de ningún tipo y disminuye significativamente el tamaño de la transacción permitiendo una mayor escala.

 El concepto subyacente detallado para Sigma se puede encontrar [aquí](https://eprint.iacr.org/2014/764.pdf).

## **Paquetes Clave de Compromiso**

Usados ​​solos, los CKP \(conocidos como "Ghost Keys"\) permiten a los usuarios destruir NIX públicos y enviarlos a una Bóveda de fantasmas, ya sea que pertenezcan a ellos mismos o a otro usuario. Cuando se usa en combinación con NIX previamente fantasma, se logran transacciones completas sin dirección.

 Depósitos anónimos de Pedersen: puede encontrar el documento sobre los paquetes de claves de compromiso [aquí](https://nixplatform.io/wp-content/uploads/2018/10/Commitment_Key_Packs_v1-0-1.pdf).

## **Red de Anonimato TOR**

TOR, también conocido como The Onion Router, proporciona una serie de relés de red cifrados y que cambian aleatoriamente, lo que hace que el análisis de tráfico sea casi imposible. Para los observadores externos, una persona que usa TOR protege no solo su dirección IP de origen, sino también su destino.

 Más información en [https://www.torproject.org](https://www.torproject.org/)

## **Transmisión de Transporte de Dandelion++**

Con Dandelion ++, una transacción se transmite primero a un par seleccionado al azar mediante una conexión cifrada. Este par luego hace lo mismo y se repite hasta que se haya logrado un número aleatorio de saltos similares. Esto forma lo que se conoce como la fase "madre". La fase "fluff" se activa mediante la cual la transacción se envía a todos los pares conectados de la manera habitual, propagándose rápidamente por toda la red.

 La información detallada se puede encontrar [aquí](https://arxiv.org/pdf/1805.11060.pdf).

