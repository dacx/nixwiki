---
description: Contribuyendo a NIX Core
---

# Colabora en NIX

El proyecto NIX Core opera un modelo de contribuyente abierto en el que cualquiera puede contribuir al desarrollo en forma de revisión por pares, pruebas y parches. Este documento explica el proceso práctico y las pautas para contribuir.

En primer lugar, en términos de estructura, no existe un concepto particular de "desarrolladores principales" en el sentido de personas privilegiadas. El código abierto a menudo gira naturalmente en torno a la meritocracia, donde los contribuyentes a largo plazo obtienen más confianza de la comunidad de desarrolladores. Sin embargo, es necesaria cierta jerarquía para fines prácticos. Como tal, hay "mantenedores" del repositorio que son responsables de fusionar las solicitudes de extracción, así como un "mantenedor principal" que es responsable del ciclo de lanzamiento, la fusión general, la moderación y el nombramiento de los mantenedores.

### **Flujo de trabajo del colaborador**

La base de código se mantiene utilizando el "flujo de trabajo del contribuyente" donde todos, sin excepción, contribuyen con propuestas de parches mediante "solicitudes de extracción". Esto facilita la contribución social, las pruebas fáciles y la revisión por pares.

Para contribuir con un parche, el flujo de trabajo es el siguiente:

1. Repositorio del Fork  
2. Crear rama de tema  
3. Confirmar parches

Deben cumplirse las convenciones de [codificación del proyecto](https://github.com/NixPlatform/NixCore/blob/master/doc/developer-notes.md) en las notas del desarrollador.

En general, los [commits deben ser atómicos](https://en.wikipedia.org/wiki/Atomic_commit#Atomic_commit_convention) y los diffs deben ser fáciles de leer. Por este motivo, no mezcle ninguna corrección de formato o movimientos de código con cambios de código reales.

Los mensajes de confirmación deben ser detallados de manera predeterminada, que consisten en una línea de asunto corta \(50 caracteres como máximo\), una línea en blanco y un texto explicativo detallado como párrafo \(s\) separado, a menos que el título solo se explique por sí mismo \(como "Error tipográfico corregido en init.cpp "\) en cuyo caso una sola línea de título es suficiente. Los mensajes de confirmación deberían ser útiles para las personas que lean su código en el futuro, así que explique el razonamiento de sus decisiones. Más explicaciones aquí.

Si una confirmación particular hace referencia a otro problema, agregue la referencia. Por ejemplo: referencias \#1234 o correcciones \#4321. El uso de las palabras clave de arreglos o cierres hará que el problema correspondiente se cierre cuando la solicitud de extracción se fusione.

Consulte el [manual de Git](https://git-scm.com/doc) para obtener más información sobre Git.

* Empujar los cambios a fork
* Crear solicitud de extracción

El título de la solicitud de extracción debe ir precedido por el componente o área que afecta la solicitud de extracción. Áreas válidas como:

* Consenso para cambios al código crítico de consenso
* Documentos para cambios en la documentación
* Qt para cambios en nix-qt
* Minería por cambios en el código minero
* Net o P2P para cambios en el código de red punto a punto
* RPC / REST / ZMQ para cambios en las API RPC, REST o ZMQ
* Scripts y herramientas para cambios en los scripts y herramientas.
* Pruebas de cambios en las pruebas unitarias nix o pruebas de control de calidad

Trivial solo debe usarse para RP que no cambian el código ejecutable generado. En particular, los refactores \(cambio de argumentos de función y reorganización de código\) y los cambios en el comportamiento no deben marcarse como triviales. Ejemplos de relaciones públicas triviales son los cambios a:

* Comentarios
* Espacio en blanco
* Nombres de variables
* Registro y mensajes
* Utilidades y bibliotecas para cambios en las utilidades y bibliotecas
* Wallet para cambios en el código de la billetera

Ejemplos:

```text
Consensus: Add new opcode for BIP-XXXX OP_CHECKAWESOMESIG
Net: Automatically create hidden service, listen on Tor
Qt: Add feed bump button
Trivial: Fix typo in init.cpp
```

Tenga en cuenta que las traducciones no deben enviarse como solicitudes de extracción, consulte [Proceso de traducción](https://github.com/nixplatform/nix/blob/master/doc/translation_process.md) para obtener más información sobre cómo ayudar con las traducciones.

Si una solicitud de extracción no se considera para fusionarse \(todavía\), prefije el título con \[WIP\] o use [Listas de tareas](https://help.github.com/articles/basic-writing-and-formatting-syntax/#task-lists) en el cuerpo de la solicitud de extracción para indicar que las tareas están pendientes.

El cuerpo de la solicitud de extracción debe contener una descripción suficiente sobre lo que hace el parche junto con cualquier justificación / razonamiento. Debe incluir referencias a cualquier discusión \(por ejemplo, otras entradas o discusiones de listas de correo\).

En esta etapa uno debería esperar comentarios y revisión de otros contribuyentes. Puede agregar más confirmaciones a su solicitud de extracción comprometiéndolas localmente y empujando a su tenedor hasta que haya satisfecho todos los comentarios.

### **Comisiones de aplastamiento**

Si su solicitud de extracción es aceptada para fusionarse, un mantenedor puede solicitarle que elimine o [modifique](https://git-scm.com/docs/git-rebase) sus confirmaciones antes de que se fusionen. El flujo de trabajo básico de aplastamiento se muestra a continuación.

```text
git checkout your_branch_name
git rebase -i HEAD~n
# n is normally the number of commits in the pull
# set commits from 'pick' to 'squash', save and quit
# on the next screen, edit/refine commit messages
# save and quit
git push -f # (force push to GitHub)
```

Si tiene problemas con el aplastamiento \(u otros flujos de trabajo con git\), también puede habilitar "Permitir ediciones de los mantenedores" en la barra lateral derecha de GitHub y solicitar ayuda en la solicitud de extracción.

Abstenerse de crear varias solicitudes de extracción para el mismo cambio. Use la solicitud de extracción que ya está abierta \(o que se creó anteriormente\) para modificar los cambios. Esto preserva la discusión y revisión que sucedió anteriormente para el conjunto de cambios respectivo.

El período de tiempo requerido para la revisión por pares es impredecible y variará de una solicitud de extracción a otra.

### **Filosofía de solicitud de extracción**

 Los parches siempre deben estar enfocados. Por ejemplo, una solicitud de extracción podría agregar una función, corregir un error o refactorizar el código; pero no una mezcla Evite también las solicitudes de extracción súper que intentan hacer demasiado, son demasiado grandes o demasiado complejas, ya que esto dificulta la revisión.

**Caracteristicas**

Al agregar una nueva característica, se debe considerar la deuda técnica a largo plazo y el mantenimiento que esa característica puede requerir después de la inclusión. Antes de proponer una nueva característica que requerirá mantenimiento, considere si está dispuesto a mantenerla \(incluida la corrección de errores\). Si las características quedan huérfanas sin mantenedor en el futuro, el Repository Maintainer puede eliminarlas.

**Refactorización**

La refactorización es una parte necesaria de la evolución de cualquier proyecto de software. Las siguientes pautas cubren la refactorización de solicitudes de extracción para el proyecto.

Hay tres categorías de refactorización, movimientos de solo código, correcciones de estilo de código, refactorización de código. En general, las solicitudes de extracción de refactorización no deben combinar estos tres tipos de actividades para que las solicitudes de extracción de refactorización sean fáciles de revisar y no controvertidas. En todos los casos, la refactorización de los RP no debe cambiar el comportamiento del código dentro de la solicitud de extracción \(los errores deben conservarse tal cual\).

Los encargados del mantenimiento del proyecto apuntan a un cambio rápido en la refactorización de las solicitudes de extracción, por lo que, cuando sea posible, manténgalos cortos, complejos y fáciles de verificar.

Pull solicita que los nuevos contribuyentes no realicen el código. Se requiere un cierto nivel de experiencia para saber a dónde pertenece el código y comprender la ramificación completa \(incluido el esfuerzo de rebase de las solicitudes de extracción abiertas\).

Las solicitudes de extracción triviales o las solicitudes de extracción que refactorizan el código sin beneficios claros pueden ser cerradas inmediatamente por los encargados del mantenimiento para reducir la carga de trabajo innecesaria en la revisión.

### **Proceso de “toma de decisiones”**

Lo siguiente se aplica a los cambios de código en el proyecto NIX Core \(y proyectos relacionados como libsecp256k1\), y no debe confundirse con los cambios generales de consenso del Protocolo de red NIX.

Si una solicitud de extracción se fusiona en NIX Core depende del responsable de la fusión del proyecto y, en última instancia, del líder del proyecto.

Los mantenedores tendrán en cuenta si un parche está en línea con los principios generales del proyecto; cumple con los estándares mínimos para la inclusión; y juzgará el consenso general de los contribuyentes.

En general, todas las solicitudes de extracción deben:

* Tener un caso de uso claro, corrija un error demostrable o sirva al bien mayor del proyecto \(por ejemplo, refactorización para modularización\);
* Estar bien revisado por pares;
* Tener pruebas unitarias y pruebas funcionales cuando sea apropiado;
* Siga las pautas de estilo de código \(C ++, pruebas funcionales\);
* No romper el conjunto de pruebas existente;
* Cuando los errores se corrijan, siempre que sea posible, debe haber pruebas unitarias que demuestren el error y también prueben la solución. Esto ayuda a prevenir la regresión.

Los parches que cambian las reglas de consenso de NIX están mucho más involucrados de lo normal porque afectan a todo el ecosistema y, por lo tanto, deben estar precedidos por extensas discusiones en la lista de correo y tener un BIP numerado. Si bien cada caso será diferente, uno debe estar preparado para gastar más tiempo y esfuerzo que para otros tipos de parches debido a la mayor revisión por pares y los requisitos de creación de consenso.

**Revisión por pares**

Cualquier persona puede participar en una revisión por pares que se expresa mediante comentarios en la solicitud de extracción. Por lo general, los revisores revisarán el código en busca de errores obvios, además de probar el conjunto de parches y opinar sobre los méritos técnicos del parche. Los encargados del mantenimiento del proyecto tienen en cuenta la revisión por pares al determinar si hay consenso para fusionar una solicitud de extracción \(recuerde que las discusiones pueden haberse extendido sobre GitHub, la lista de correo y las discusiones del IRC\). El siguiente lenguaje se utiliza en los comentarios de solicitud de extracción:

* ACK significa "He probado el código y estoy de acuerdo en que debe fusionarse"; NACK means "I disagree this should be merged", and must be accompanied by sound technical justification \(or in certain cases of copyright/patent/licensing issues, legal justification\).
* NACKs sin razonamiento acompañante pueden ser descartados;
* utACK significa "No he probado el código, pero lo he revisado y se ve bien, estoy de acuerdo en que se puede combinar";
* El concepto ACK significa "Estoy de acuerdo con el principio general de esta solicitud de extracción";
* Nit se refiere a problemas triviales, a menudo sin bloqueo.

Los revisores deben incluir el hash de confirmación que revisaron en sus comentarios.

Los encargados del mantenimiento del proyecto se reservan el derecho de sopesar las opiniones de los revisores pares utilizando el juicio del sentido común y también pueden sopesar en función de la meritocracia: aquellos que han demostrado un compromiso y comprensión más profundos hacia el proyecto \(con el tiempo\) o que tienen una clara experiencia en el dominio, naturalmente, pueden tener más peso , como cabría esperar en todos los ámbitos de la vida.

Cuando un conjunto de parches afecta el código crítico de consenso, la barra se establecerá mucho más alto en términos de discusión y requisitos de revisión por pares, teniendo en cuenta que los errores pueden ser muy costosos para la comunidad en general. Esto incluye la refactorización del código crítico de consenso.

Cuando un conjunto de parches propone cambiar el consenso de NIX, debe haber sido discutido extensamente en la lista de correo e IRC, estar acompañado por un BIP ampliamente discutido y tener un consenso técnico generalmente ampliamente percibido de ser un cambio valioso basado en el juicio del mantenedores.

**Encontrar revisores**

Como la mayoría de los revisores son en sí mismos desarrolladores con sus propios proyectos, el proceso de revisión puede ser bastante largo y se requiere cierta paciencia. Si descubre que ha estado esperando una solicitud de extracción para recibir atención durante varios meses, puede haber varias razones para esto, algunas de las cuales puede hacer algo al respecto:

* Puede ser debido a una congelación de funciones debido a un próximo lanzamiento. Durante este tiempo, solo se tienen en cuenta las correcciones de errores. Si su solicitud de extracción es una función nueva, no se priorizará hasta que finalice el lanzamiento. Espera a la liberación.
* Puede deberse a que los cambios que sugiere no son atractivos para las personas. En lugar de críticas y críticas, que requieren esfuerzo y significa que se preocupan lo suficiente como para dedicar tiempo a su contribución, el silencio atronador es una buena señal de aversión generalizada \(leve\) a un cambio dado \(porque las personas no asumen que a otros realmente no les gustará la propuesta\). ¡Pero no te lo tomes como algo personal! En cambio, eche otro vistazo crítico a lo que está sugiriendo y vea si: cambia demasiado, es demasiado amplio, no se adhiere a las notas del desarrollador, es peligroso o inseguro, está mal escrito, etc. Identifique y aborde cualquiera de los Problemas que encuentre. Luego pregunte p. en IRC si alguien pudiera dar su opinión sobre el concepto mismo.
* Puede deberse a que su código es demasiado complejo para todas menos algunas personas. Y esas personas pueden no haberse dado cuenta de que su solicitud de extracción incluso existe. Una excelente manera de encontrar personas calificadas y preocupadas por el código que está tocando es la función Git Blame. Simplemente encuentre a la persona que toca el código que está tocando antes de usted y vea si puede encontrarla y darle un empujón. Sin embargo, no seas incesante sobre los empujones.
* Finalmente, si todo lo demás falla, pregunta en Discord o en otro lugar para que alguien eche un vistazo a tu solicitud de extracción. Si cree que ha estado esperando una cantidad de tiempo excesivamente larga \(mes +\) sin ninguna razón en particular \(algunas líneas cambiaron, etc.\), esto está totalmente bien. Intente devolver el favor cuando alguien más le pida comentarios sobre su código y el universo se equilibre.

### **Política de lanzamiento**

El líder del proyecto es el administrador de versiones para cada versión de NIX Core.

### **Derechos de autor**

Al contribuir a este repositorio, usted acepta licenciar su trabajo bajo la licencia MIT a menos que se especifique lo contrario en contrib/debian/copyright o en la parte superior del archivo. Cualquier trabajo aportado donde usted no sea el autor original debe contener el encabezado de la licencia con el \(los\) autor \(es\) original \(es\) y la fuente.

