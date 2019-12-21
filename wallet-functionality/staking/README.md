---
description: Descripción general de NIX
---

# Staking

La red NIX comenzó originalmente como una cadena de bloques de prueba de trabajo lyra2rev2. En el bloque 53,000, el método de consenso cambió a Prueba de participación. Para permitir este cambio de consenso, fue necesario un hard fork. Este cambio en el protocolo no crea una nueva moneda, sino que actualiza la red. A medida que la red madura, las recompensas de participación aumentarán de acuerdo con el [Programa de Inflación](https://wiki.nixplatform.io/home/v/espanol/getting-started/network-and-coin-specs#inflation-schedule).

El staking permite a los usuarios obtener ingresos pasivos en función de sus tenencias al agregar nuevos bloques a la cadena sin la necesidad de hardware costoso y especializado, como mineros ASIC o GPU, que a menudo requieren acceso a bajos costos de electricidad para ser rentables. En cambio, las posibilidades de crear un nuevo bloque están correlacionadas con la cantidad de monedas que poseen y están apostando activamente.

El propietario puede realizar el replanteo directamente o puede arrendar sus monedas a un [comerciante](https://nixplatform.io/marketplace) para que las replantee en su nombre utilizando lo que se denomina un ["contrato de prueba de arrendamiento" o contrato LPoS](https://wiki.nixplatform.io/home/v/espanol/wallet-functionality/staking/lpos-client). Los usuarios también pueden utilizar contratos LPoS para apostar en frío sus propias monedas en un entorno mucho más seguro. Es importante tener en cuenta que cuando se utiliza un contrato LPoS, el propietario de las monedas mantiene el control total de sus tenencias y puede cancelar el contrato en cualquier momento. El comerciante no tiene la capacidad de mover, gastar ni hacer nada con monedas contratadas que no sean acciones que estén directamente relacionadas con el replanteo, como crear nuevos bloques y [establecer umbrales de división/combinación](https://wiki.nixplatform.io/home/v/espanol/advanced-wallet-functions/command-line-options#wallet-staking-options).

Para apostar, las monedas deben estar en una dirección que comience con "N" o "nix1". Además, la billetera debe estar encriptada y desbloqueada para el replanteo, sincronizada con la red y permanecer abierta y en funcionamiento. A partir del bloque \#115,921, todas las salidas de transacciones no gastadas \(UTXO\) requieren 200 confirmaciones para estar disponibles para el replanteo. Esto también se aplica a las monedas que han obtenido una recompensa por apostar con éxito y crear un nuevo bloque en la cadena.

Actualmente solo se puede hacer staking de NIX públicamente, sin embargo, se planea poder hacer staking de [NIX fantasma](https://wiki.nixplatform.io/home/v/espanol/wallet-functionality/ghost-vault).



