---
description: 2-Way Ghosting permite privatizar las direcciones de envío y recepción.
---

# 2-Way Ghosting

Esta tecnología nunca antes hecha permite la capacidad de lanzar poderosos contratos inteligentes privados en cadena al tiempo que permite una privacidad sin límites de transacciones a prueba de conocimiento.

Aunque el procedimiento técnico para lograr la privacidad del remitente y el receptor en una transacción es complejo en el backstage, se puede resumir como el envío de monedas de una Bóveda fantasma a otra. Se puede ver una breve descripción técnica en el [Documento técnico del Paquete de claves de compromiso](https://nixplatform.io/wp-content/uploads/2018/10/Commitment_Key_Packs_v1-0-1.pdf). Hay una tarifa de tarifa fija de .1 para estas transacciones de bóveda a bóveda, pagadas por la bóveda fantasma de los remitentes \(no se resta del monto de la transacción\).

El efecto fantasma bidireccional actualmente solo está disponible en QT Wallet. El soporte en otras billeteras estará disponible.

##  **QT Wallet**

Primero debes tener [NIX fantasma en tu Ghost Vault](https://wiki.nixplatform.io/home/wallet-functionality/ghost-vault/1-way-ghosting). \(Replace this link with the Spanish version\) Puede comenzar su transacción Ghost de 2 vías haciendo clic en el botón "Ghost Vault" seguido de la pestaña "Un-Ghost NIX from Vault".

Anule la selección de la casilla de verificación "Un-Ghost to Myself", ingrese la clave fantasma de los destinatarios en el campo de entrada "Un-Ghost To:" e ingrese una cantidad de NIX fantasma para enviar.

![Crear una transacci&#xF3;n 2-Way Ghosting.](../../.gitbook/assets/qt-2-way-ghosting.png)

{% hint style="info" %}
**NOTA:** Las cantidades fraccionarias actualmente solo están disponibles en incrementos de .1.
{% endhint %}

Su transacción Ghost de 2 vías se agregará a la cadena de bloques con las direcciones de envío y recepción privatizadas.

![Both send and receive addresses are privatized on the blockchain](../../.gitbook/assets/explorer-2-way-ghosting.png)

