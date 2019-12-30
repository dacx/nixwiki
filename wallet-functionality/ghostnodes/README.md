# Ghostnodes

NIX Ghostnodes son una parte fundamental de la capa de protocolo NIX y son responsables de procesar y validar las transacciones de privacidad, así como de aprobar y cumplir los protocolos de cadena cruzada. Todos los elementos de contratos inteligentes que requieren un procesamiento de privacidad autónomo dependen de NIX Ghostnodes para cumplir con esas solicitudes.

Ejecutar un Ghostnode requiere una garantía de 40,000 NIX y se recompensa de las siguientes maneras:

1.  Recompensas de bloque: un porcentaje de nuevas recompensas de bloque se paga a Ghostnodes mediante un método serializado que recorre la lista de nodos activos.
2.  Ghosting NIX: cuando un usuario fantasma sus monedas, ya sea para las suyas o para la Bóveda fantasma de otro usuario, se cobra una tarifa de 0.25%.
3.  Transacciones privadas de bóveda a bóveda: los usuarios que mueven NIX fantasma de bóveda a bóveda \(transacciones de privacidad completas del remitente y del receptor\) incurren en una tarifa de tarifa plana de .1.

Las tarifas de transacción de privacidad se agrupan y luego se dividen cada 720 bocks \(~ 24 horas\) entre todos los Ghostnodes activos.

