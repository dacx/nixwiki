# Ghost Vault

El NIX Ghost Vault estuvo disponible para su uso a partir del bloque \#53,000, originalmente usando el Protocolo Zerocoin. A partir del bloque \# 232,000, el Protocolo Zerocoin fue reemplazado activamente por Sigma, que reduce significativamente los tamaños de prueba en cadena de 25kb a 1.5kb, reduce las longitudes del paquete de claves de compromiso en un 73% y aumenta significativamente los conjuntos de anonimato al introducir curvas elípticas de 256 bits que sería más o menos equivalente al RSA de 3072 bits en comparación con el RSA de 2048 bits utilizado anteriormente en el Protocolo Zerocoin. El crédito masivo va al equipo de desarrollo de [ZCoin](https://zcoin.io/) por crear [la primera implementación de la base de código criptográfica Sigma](https://twitter.com/zcoinofficial/status/1118819578472206337) y sus desarrollos en estos grupos

NIX Ghost Vault proporciona privacidad para el remitente y/o el receptor al quemar esencialmente las monedas y permitir a los usuarios volver a emitirlas más tarde sin un historial de transacciones adjunto. Ghost Vault se puede utilizar de 4 maneras:

**Privacidad del titular \(1-Way Ghosting\):**  
Al colocar su NIX público en su Ghost Vault, un observador externo no tiene pruebas de que su billetera todavía posea esas monedas.

**Privacidad del remitente \(1-Way Ghosting\):**  
Al enviar su NIX previamente fantasma a una dirección pública del receptor, el destinatario recibe monedas públicas recién acuñadas sin historial adjunto.

**Privacidad del receptor \(1-Way Ghosting\):**  
Para la privacidad exclusiva del receptor, puede crear un fantasma de su NIX público directamente en los destinatarios de Ghost Vault.

**Privacidad del remitente y del receptor \(2-Way Ghosting\):**  
El envío de su NIX previamente fantasma de su Ghost Vault a los destinatarios de Ghost Vault resulta en una transacción pública completa sin dirección.

