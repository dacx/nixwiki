---
description: Cómo configurar y cancelar un contrato LPoS
---

# Cliente LPoS

Puede utilizar la pantalla 'Crear contrato' de LPoS para crear contratos inteligentes de Cold Staking y Leased Proof of Stake que operan de manera no confiable hasta que decida cancelar el contrato.

 Esto significa que cualquier propietario de una moneda puede arrendar sus derechos de staking a cualquier comerciante de staking de terceros \(que puede cobrar una tarifa por sus servicios\) para recibir recompensas de staking sin tener que preocuparse por los aspectos técnicos de mantener una billetera abierta, actualizada y desbloqueada para el staking. Dichos proveedores de servicios LPoS se pueden encontrar en el [mercado NIX](https://nixplatform.io/marketplace).

Como se mencionó, hay 2 formas de usar este contrato inteligente:

**Staking en frío independiente:** después de configurar una [billetera de staking en frío LPoS](https://wiki.nixplatform.io/home/v/espanol/wallet-functionality/staking/lpos-server) , simplemente apunte la dirección 'Arrendamiento a' a una dirección generada por la billetera de su servidor, especifique la cantidad que desea apostar y haga clic en 'Enviar NIX'. Se le pedirá que ingrese su contraseña de cifrado si se configura una.

**Uso de un comerciante de LPoS:** cada comerciante proporcionará toda la información necesaria que necesitará para crear un contrato con ellos. **Si no ingresa correctamente la información proporcionada por los comerciantes, su contrato no podrá apostar y ganar recompensas.**

## **Billetera QT**

### **Crear un Contrato**

Haga clic en la pestaña LPoS en la parte superior de la billetera QT para encontrar la pantalla "Crear contrato". Aquí, puede completar la información requerida para arrendar sus monedas a otra billetera o proveedor.

![Pantalla &#x201C;Create LPoS smart-contracts&#x201D;.](../../.gitbook/assets/qt-create-lpos-contract.png)

**`Lease to:`** Define la dirección externa permitida para apostar las monedas. Esta dirección es suministrada por el comerciante.

**`Contract Label:`** una etiqueta de visualización para una identificación más fácil en la pestaña 'Contratos activos'.

**`Amount:`** la cantidad de NIX que desea apostar. Las cantidades siguen las selecciones de control de monedas si están habilitadas

**`Fee Percent:`** cantidad de participación de recompensa asignada al comerciante de arrendamiento. Esta información es proporcionada por el comerciante. Si la tarifa es mayor que cero, marque la casilla "Habilitar pago de tarifa" para ingresar el porcentaje apropiado.

**`Reward Address:`** la dirección del comerciante para su parte de la recompensa de participación cuando su contrato se apuesta con éxito. Esta dirección es suministrada por el comerciante.

**`Owner Address:`** \(optional\) Allows you to specify a local address where your leased coins will be held. Creating multiple contracts with the same owner address allows merchants/cold staking services to combine contracts until a minimum number of coins are reached using the stakecombinethreshold=&lt;n&gt; configuration option \(default is 5000 coins\).

### **Cancelar un contrato**

Primero, navegue a la pestaña "Contratos activos" desde la pantalla LPoS.

![Pesta&#xF1;a &#x201C;Active Contracts&#x201D; de LPoS](../../.gitbook/assets/qt-lpos-active-contracts.png)

{% hint style="info" %}
**NOTA:** Los contratos activos que han alcanzado una apuesta recientemente no se mostrarán hasta que esas monedas hayan madurado \(201 confirmaciones\).
{% endhint %}

Para cancelar un contrato activo, simplemente selecciónelo y luego haga clic derecho.

![](../../.gitbook/assets/qt-lpos-cancel-contract.png)

## Billetera UI

### **Crear un contrato**

Primero, haga clic en "Staking" en el menú de la izquierda, luego "Leased Staking" seguido de "NEW LEASING CONTRACTS".

![](../../.gitbook/assets/ui-lpos-composite.png)

![Nueva pantalla de contrato de arrendamiento.](../../.gitbook/assets/ui-lpos-setup.png)

**`LPoS provider details:`**  se puede configurar a lo que desee.

**`Address that coins will be leased to for staking:`** Define la dirección externa permitida para apostar las monedas. Esta dirección es suministrada por el comerciante.

**`Contract description:`** se puede configurar a lo que desee.

**`LPoS provider's fee:`** Cantidad de participación de recompensa asignada al comerciante de arrendamiento. Esta información es proporcionada por el comerciante.

**`Address for LPoS provider's fee:`** La dirección del comerciante para su parte de la recompensa de la apuesta cuando su contrato tiene éxito. Esta dirección es suministrada por el comerciante.

### **Cancelar un contrato**

En la parte inferior de la ventana de Staking arrendado, encontrará la lista de contratos activos. Aquí, puede ver los detalles y cancelar cualquiera de sus contratos de LPoS.

![](../../.gitbook/assets/ui-lpos-contracts.png)

{% hint style="info" %}
 **NOTA:** Los contratos activos que han alcanzado un staking recientemente no se mostrarán hasta que esas monedas hayan madurado \(201 confirmaciones\).
{% endhint %}

