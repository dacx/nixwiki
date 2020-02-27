# 1-Way Ghosting

El procedimiento de enviar monedas a un Ghost Vault \(ya sea la suya o la de otra persona\) se llama "efecto fantasma", que esencialmente quema las monedas y permite al usuario volver a emitirlas más tarde como monedas públicas sin historial adjunto. Las monedas guardadas en la Bóveda Fantasma permanecen privadas. La tarifa por la creación de imágenes fantasma de su NIX es del 0.25%, pagada con NIX que cotiza en bolsa \(no se resta de su NIX fantasma\).

Esta característica fue la primera implementación de transacción de privacidad de NIX y no ofrece privacidad del remitente y del receptor al mismo tiempo. Si su transacción requiere ambos, use el efecto [2-Way Ghosting](https://wiki.nixplatform.io/home/v/espanol/wallet-functionality/ghost-vault/2-way-ghosting).

Actualmente, Ghost Vault solo está disponible en las billeteras QT y GUI, con soporte de billetera móvil, planificado para su lanzamiento posterior.

{% hint style="success" %}
**SUGERENCIA:** cuanto más tiempo tenga su NIX fantasma en su Vault y cuanto más NIX fantasma haya en total en la red, más fuerte será su privacidad.
{% endhint %}

## QT Wallet Ghost Vault

Para comenzar, abra su billetera nix-qt y haga clic en el botón "Ghost Vault" y asegúrese de estar mirando la pestaña "Ghost NIX to Vault".

![Haga Click en el bot&#xF3;n &quot;Ghost Vault&quot; en la parte superior, seguido de la pesta&#xF1;a &quot;Ghost NIX to Vault&quot;.](../../.gitbook/assets/qt-ghost-vault.png)

### **Enviando a tu propio Ghost Vault**

De forma predeterminada, su NIX estará en su propia Ghost Vault. Los observadores externos no podrán decir que aún mantiene la posesión.

![Sending NIX to your own Ghost Vault](../../.gitbook/assets/qt-ghost-to-self.png)

### **Ghosting para otros usuarios de Ghost Vault**

Si prefiere enviar su NIX público a una billetera diferente, desmarque la casilla "Ghost to Myself" y pegue la clave fantasma de los destinatarios.

![Sending NIX to somebody else&apos;s Ghost Vault](../../.gitbook/assets/qt-ghost-to-other.png)

{% hint style="info" %}
**NOTA:** Las cantidades fraccionarias actualmente solo están disponibles en incrementos de .1.
{% endhint %}

Su NIX fantasma se mostrará como: no confirmado, mientras todavía está en el grupo de memoria esperando ser agregado a la cadena de bloques. Una vez que se agregan a la cadena de bloques, se mostrarán como Ghosted.

Los ejemplos anteriores de cómo 1-Way Ghosting privatizará la transacción:

![Receiving address is privatized](../../.gitbook/assets/explorer-1-way-ghosting.png)

### **Un-Ghosting a la billetera de otro usuario**

En los casos en que solo desee privatizar su dirección de envío, puede retirar fondos de su Bóveda fantasma a una dirección pública del receptor. Este método se realiza desde la pestaña "Un-Ghost NIX from Vault", y no hay ningún cargo por este tipo de transacción.

![Un-Ghosting to another users wallet](../../.gitbook/assets/qt-unghost-to-other.png)

![Sending address is privatized](../../.gitbook/assets/explorer-unghost.png)

## **UI Wallet Ghost Vault**

La billetera GUI actualmente solo admite agregar fondos a su propia Ghost Vault, y se puede hacer de 2 maneras.

### **Desde la pantalla de resumen**

En la pantalla Descripción general, busque el cuadro "Ghost Vault" y haga click en el botón "Depositar".

![](../../.gitbook/assets/ui-overviewghoststart.png)

![Ingrese el monto junto con su contrase&#xF1;a y haga click en &quot;Depositar en el Vault&#x201D;.](../../.gitbook/assets/ui-overviewghostdeposit.png)

![](../../.gitbook/assets/ui-overviewghostingsuccess.png)

### **Desde el menú de Ghost Vault**

Seleccione "Ghost Vault" en el menú en el lado izquierdo de la billetera UI y haga clic en "Deposit from walet".

![Haz click en &quot;Deposit from wallet&quot; dentro de Ghost Vault.](../../.gitbook/assets/ui-ghostvaultdeposit.png)

![Ingrese el monto junto con su contrase&#xF1;a y haga clic en &quot;Depositar en el Vault&quot;.](../../.gitbook/assets/ui-ghostvaultghosting.png)

![](../../.gitbook/assets/ui-ghostvaultghostingsuccess.png)

