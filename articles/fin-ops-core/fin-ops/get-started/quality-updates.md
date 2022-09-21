---
title: Actualizaciones de calidad proactivas
description: Este artículo proporciona información sobre la entrega proactiva de actualizaciones de calidad.
author: rashmansur
ms.date: 09/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 985800aad3711a1b28613f0f82585b4d592cdf58
ms.sourcegitcommit: de989037d83393bea013cd58c061159765305b4f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473615"
---
# <a name="proactive-quality-updates"></a>Actualizaciones de calidad proactivas

[!include[banner](../includes/banner.md)]

En los últimos años, Microsoft ha hecho un progreso continuo en lo que llamamos [One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md). La premisa de One Version es simple: cuanto más cerca estemos de tener a todos los clientes con la misma versión de software, mayor será la calidad que podamos ofrecer. Encontramos y solucionamos problemas una vez, y ponemos esas soluciones en manos de más clientes con mayor rapidez.

Esta premisa se ve confirmada por los resultados: menor número de incidentes en todos nuestros productos. Cuando los clientes no tienen la misma versión, vemos constantemente que se ven afectados por problemas para los que ya hay una solución disponible. Ya hemos hecho un gran progreso con Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations y Dynamics 365 Commerce, y gracias a los recientes avances técnicos, ahora es posible dar el siguiente paso. La siguiente información establece lo que vamos a hacer, lo que ya hemos hecho para preparar el escenario y cómo y cuándo presentaremos las nuevas capacidades sin interrupciones.

## <a name="focus-on-quality-updates"></a>Centrarse en actualizaciones de calidad

Actualmente proporcionamos siete [actualizaciones de servicio](public-preview-releases.md) por año. Por ejemplo, la versión 10.0.29 es una actualización de servicio. Hasta hace poco, había ocho actualizaciones por año. Sin embargo, eliminamos una actualización en respuesta a los comentarios de los clientes que revelaron el deseo de evitar cambios cerca del final del año calendario.

No cambiaremos la cadencia de las actualizaciones del servicio. En cambio, nuestro próximo paso adelante en el viaje de One Version se centra en *actualizaciones de calidad*. Las actualizaciones de calidad son compilaciones acumulativas de revisiones. No incluyen nuevas características. En un momento dado, toda nuestra comunidad de clientes se reparte entre las tres o cuatro actualizaciones de servicio más recientes. Sin embargo, para cualquier actualización de servicio dada, se pueden usar docenas de versiones de actualización de calidad diferentes dentro del grupo, según las fechas en que las personas implementaron. En nuestro próximo paso, transmitiremos de manera proactiva actualizaciones de calidad. Ya usamos este modelo para nuestras aplicaciones basadas en Dataverse y han visto los resultados esperados de calidad mejorada y disminución de incidentes de soporte.

Por supuesto, una reducción de defectos podría reducir o eliminar por completo la necesidad de actualizaciones de calidad. Tenemos múltiples iniciativas en marcha para reducir los defectos que requieren actualizaciones de calidad. Incluso cuando las cargas útiles se reducen en la actualización de calidad, la coherencia en la base de clientes mejorará la capacidad de soporte, obtendrá mejoras para los clientes más rápidamente y reducirá la frecuencia con la que los clientes encuentran problemas para los que ya existen soluciones.

## <a name="making-proactive-distribution-possible"></a>Haciendo posible la distribución proactiva

Ya se han implementado múltiples avances que permiten la entrega proactiva de actualizaciones de calidad:

- **Actualización de tiempo de inactividad casi nulo** – Para impulsar entornos más frecuentes, es esencial que se reduzca el impacto en la disponibilidad del entorno para preservar los acuerdos de nivel de servicio (SLA) de Dynamics 365. La actualización con tiempo de inactividad casi nulo se introdujo originalmente para ayudar a mejorar la aplicación mensual de parches del sistema operativo mediante el uso de una conmutación por error del clúster para activar la imagen actualizada con una interrupción mínima. El mecanismo para aplicar actualizaciones se está mejorando para que sea aún menos disruptivo y cubrirá tanto la aplicación de parches del sistema operativo como la implementación de actualizaciones de calidad.

    En el caso de los usuarios interactivos, es posible que se interrumpa una sesión activa y el reintento irá al entorno ahora actualizado. Con la introducción de la [programación por lotes basada en prioridades](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), que ahora está disponible de forma opcional, la programación y el procesamiento por lotes se recuperan y se reanudan inmediatamente después de la actualización. La programación por lotes basada en prioridades estará disponible para los clientes antes de que comiencen a participar en la distribución proactiva de actualizaciones de calidad para sus entornos de producción.

- **Horas oscuras** – Las horas oscuras se definen para cada región de Azure, y se producirán actualizaciones de tiempo de inactividad casi nulo durante el período de la hora oscura.

## <a name="the-proactive-update-process"></a>El proceso de actualización proactiva

La implementación de actualizaciones de calidad proactivas seguirá un proceso de implementación seguro (SDP). Los detalles del SDP evolucionarán, pero las actualizaciones de calidad se implementarán inicialmente en entornos de espacio aislado. El proceso comenzará con entornos que opten por una implementación temprana. A medida que aumente el porcentaje de sandboxes implementados con éxito, comenzará la implementación en entornos de producción. Una vez más, el proceso comenzará con entornos que opten por una implementación temprana. Los sistemas de escucha monitorearán la telemetría del sistema y los incidentes de Livesite, y detendrán el lanzamiento de una versión específica si se detecta alguna regresión. Los clientes aún podrán obtener las actualizaciones de calidad antes de la implementación proactiva si así lo desean.

Los datos de administración de versiones actuales muestran que menos del 3 por ciento de las regresiones se introducen en actualizaciones de calidad. Con un mayor enfoque en la eliminación de la regresión y un SDP mejorado, el impacto potencial de las regresiones será dramáticamente menor que las ganancias de calidad que se logran al implementar correcciones más rápidamente para los clientes en general.

## <a name="process-changes"></a>Procesar cambios

Se está implementando un conjunto de cambios de proceso antes de la activación de la implementación proactiva de actualizaciones de calidad:

- **Esquema** – Las herramientas garantizarán que las compilaciones de actualizaciones de calidad incluyan solo los cambios de esquema que se pueden aplicar mientras el servicio está en línea. Este enfoque ayudará a preservar la capacidad de aplicar la actualización con un tiempo de inactividad casi nulo.
- **Mayor escrutinio de cambios** – Actualmente, ya existe un paso de proceso adicional para aprobar los cambios para su inclusión en una actualización de calidad. El escrutinio en el paso adicional se incrementará para ayudar a reducir el potencial de regresiones. No se permiten cambios importantes en las actualizaciones de calidad, y el mayor escrutinio de cambios ayudará a garantizar que cumplamos este objetivo.
- **Visibilidad** – Enviaremos notificaciones por correo electrónico y Lifecycle Services (LCS) para las próximas actualizaciones de calidad proactivas. Además, los equipos de soporte y los líderes de incidentes tendrán visibilidad de dónde se implementaron de manera proactiva las actualizaciones de calidad.
- **Versión alternativa** – La división en tramos se utilizará para agrupar todos los cambios en una actualización de calidad proactiva. Si se requiere un respaldo después de una implementación proactiva, se puede hacer a través del sistema de tramos.
- **Designación de sincronización de sandbox** – Menos del 20 por ciento de los clientes de hoy en día tienen múltiples sandboxes y mantienen un sandbox implementado donde la versión coincide con la producción, para ayudar con la resolución de problemas. Si un cliente está usando un espacio aislado para probar una versión más nueva que su producción, ese espacio aislado recibirá actualizaciones de calidad para la versión más nueva.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>¿Cuál es la hoja de ruta de implementación para las actualizaciones de calidad?

Se espera que la distribución de actualizaciones de calidad proactivas para entornos sandbox comience a fines de septiembre u octubre de 2022 para los clientes de la nube pública de Azure. Los entornos de prueba también comenzarán a recibir una implementación de actualización proactiva en ese momento. En septiembre, se enviará una notificación a cada cliente para informarles sobre el horario previsto para sus entornos. Solo se permitirán excepciones al proceso de distribución actualizado proactivo para los clientes regulados por la FDA. Todavía estamos trabajando en cómo se gestionarán los entornos regulados y los clientes de nube soberanos y gubernamentales.

Durante el próximo período de seis meses, aumentaremos gradualmente el porcentaje de entornos de espacio aislado que reciben actualizaciones proactivas, hasta que se incluyan todos los entornos designados y se avance hacia la actualización de los entornos de producción. A lo largo del período, realizaremos un seguimiento para garantizar que el proceso de implementación sea fluido y que estemos alcanzando nuestro objetivo de cargas útiles no disruptivas.

Debido a que los clientes recibirán regularmente cargas útiles más pequeñas, esperamos que el proceso de mantenerse al día sea más simple. Ajustaremos la frecuencia de implementación de actualizaciones a medida que demostremos la capacidad de ejecutar el proceso sin interrupciones. Este proceso ya está funcionando eficazmente para nuestra plataforma y aplicaciones de Dataverse, y está entregando las mejoras anticipadas en la calidad del servicio. Estamos ansiosos por dar el mismo paso adelante para las aplicaciones de finanzas y operaciones.

## <a name="when-will-quality-updates-start-for-production-environments"></a>¿Cuándo comenzarán las actualizaciones de calidad para los entornos de producción?
En este momento, las actualizaciones de calidad solo están dirigidas a entornos aislados. Las actualizaciones de los entornos de producción comenzarán después de noviembre de 2022.

## <a name="what-is-the-schedule-for-sandbox-quality-updates"></a>¿Cuál es el calendario para las actualizaciones de calidad de espacio aislado?
Para obtener información sobre las horas de oscuridad para cada región, consulte [¿Cuál es el calendario para las actualizaciones de calidad proactivas?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-is-the-schedule-for-proactive-quality-updates).

## <a name="how-are-the-dark-hours-handled-for-customers-that-have-one-finance-and-operations-apps-instance-but-are-active-in-multiple-time-zones"></a>¿Cómo se gestionan las horas oscuras para los clientes que tienen una instancia de aplicaciones de finanzas y operaciones pero están activos en varias zonas horarias? 
No hay horarios especiales fuera de las horas oscuras donde existe una instancia de aplicaciones de finanzas y operaciones, ya que planeamos implementar actualizaciones de calidad de una manera mínimamente disruptiva con [nZDT](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-does-near-zero-downtime-maintenance-mean).

## <a name="how-will-microsoft-ensure-the-quality-of-these-updates"></a>¿Cómo garantizará Microsoft la calidad de estas actualizaciones?
Microsoft se esfuerza por mantener la canalización de lanzamiento lo suficientemente eficiente como para entregar pequeñas cargas útiles para mantener bajo el costo de validación. Cada corrección en una actualización de calidad pasa por un proceso de implementación riguroso y seguro que ayuda a mejorar la calidad y la confiabilidad, reduciendo así el impacto en el cliente. La implementación se llevará a cabo por etapas en entornos de espacio aislado primero, seguida de producción. Las implementaciones por etapas permiten una supervisión adecuada para determinar si una implementación posterior es segura. Detendremos la implementación si se detectan problemas con cada grupo de clientes implementado y nos aseguraremos de que cada paso de la implementación tenga tiempo suficiente para que surjan los problemas. Para cada próxima actualización de calidad, brindaremos visibilidad del calendario a través de actualizaciones de documentación pública y correos electrónicos, para que los clientes puedan planificar con anticipación.

## <a name="can-customers-delay-reschedule-or-pause-a-quality-update"></a>¿Pueden los clientes retrasar, reprogramar o pausar una actualización de calidad?
N. º El principal objetivo de las actualizaciones de calidad es garantizar que aspectos fundamentales como la seguridad, la privacidad, la confiabilidad, la disponibilidad y el rendimiento mejoren continuamente para nuestros clientes. Al retrasar o pausar una actualización, la seguridad, la disponibilidad y la confiabilidad estarán en riesgo.

## <a name="how-can-one-know-the-set-of-changes-that-went-into-a-quality-update-payload"></a>¿Cómo se puede saber el conjunto de cambios que se incluyeron en una carga útil de actualización de calidad?
Podrá ver todos los artículos de KB en una versión de actualización de calidad en la página **Detalles del entorno** en LCS, navegando a la sección **Actualización de calidad**. 

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>¿Cuál es el proceso si se encuentra un problema crítico después de una actualización de calidad?
Un problema crítico o regresión es uno o más eventos que generalmente hacen que varios clientes tengan una experiencia degradada con uno o más de nuestros servicios. Estos problemas pueden causar tiempo de inactividad no planificado, incluida la falta de disponibilidad, la degradación del rendimiento y la interferencia con la gestión del servicio. Si hay un impacto amplio en el cliente debido a dichas regresiones, detendremos el lanzamiento de una actualización de calidad hasta que podamos comunicarnos y solucionar el problema. Por lo general, la próxima actualización de calidad tendrá la solución necesaria para reanudar la implementación.

Si el entorno de un solo cliente se ve afectado, contacte con el soporte de Microsoft para abrir una incidencia. Según la justificación, detendremos la implementación de la actualización de calidad en todos los demás entornos de ese proyecto hasta que se mitigue el problema.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lcs"></a>¿Pueden los clientes aplicar manualmente las actualizaciones de revisión de LCS?
Sí. Para garantizar la paridad continua con el funcionamiento de las revisiones, las actualizaciones de revisiones aún se pueden aplicar a los entornos de los clientes en LCS. Sin embargo, es importante tener en cuenta que las revisiones que se implementan como parte de una actualización de calidad pasan por el SDP estándar antes de que se implemente la actualización. Esto reduce el riesgo de regresiones debido a una mayor calidad. Le recomendamos que elija una actualización de calidad en lugar de aplicar revisiones manualmente para aumentar la confiabilidad.

## <a name="can-customers-self-install-a-quality-update-build-by-themselves-ahead-of-the-schedule"></a>¿Pueden los clientes autoinstalar una actualización de calidad antes de lo previsto?
Sí. Puede instalar una actualización de calidad de forma proactiva. Microsoft omitirá la actualización si la versión de compilación actual del entorno es igual o superior a la actualización de calidad en cuestión.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Si un entorno tiene una próxima actualización de servicio mensual programada dentro de una semana, ¿seguirá recibiendo actualizaciones de calidad?
- Las actualizaciones de calidad no se aplican si hay una actualización de servicio inminente programada dentro de una semana a partir de la fecha programada para la actualización de calidad.
- Si un entorno de espacio aislado tiene una versión de compilación igual o superior a la actualización de calidad inminente, se omitirá.
- Si un entorno de producción tiene una versión de compilación igual o superior a la actualización de calidad inminente, se omitirá.
- Si un espacio aislado tiene la misma versión de compilación o una superior debido a una actualización de calidad o una actualización manual de la producción, la producción seguirá recibiendo la versión programada de la actualización mensual del servicio. Si no desea que el entorno de producción programado se actualice a la versión de actualización del servicio, puede pausar la actualización del servicio desde LCS. 
- Le recomendamos que utilice la última versión de actualización de calidad para probar sus cambios para una próxima actualización de servicio para una mejor estabilidad y resultados.

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>¿Se puede devolver un entorno a su estado anterior si hay problemas después de aplicar una actualización de calidad?
Después de aplicar una actualización de calidad, no hay reversión bajo ninguna circunstancia. Solo hay opciones de reenvío de parches disponibles para mitigar los problemas.

## <a name="what-about-fda-regulation-and-gpx"></a>¿Qué pasa con la regulación FDA y GPX?
El plan para clientes sujetos a la validación y regulación de la FDA aún está en evolución. Espere más actualizaciones en este espacio pronto. Por ahora, todos estos clientes están exentos de actualizaciones de calidad.

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>¿Qué versiones de actualizaciones de servicio son compatibles con estas actualizaciones de calidad?
Los clientes con versiones anteriores a N-2 no recibirán actualizaciones de calidad. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retailsdk"></a>Las implementaciones de aplicaciones de finanzas y operaciones con componentes minoristas generalmente requieren trabajo adicional además de tener que volver a implementar MPOS. ¿Cómo afectarán estas actualizaciones de calidad al RetailSDK? 
Como la naturaleza de las revisiones en sí no cambia en la carga útil de las actualizaciones de calidad, no anticipamos ningún impacto adicional en este momento específicamente relacionado con los componentes minoristas.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che-"></a>¿Hay algún impacto en los entornos alojados en la nube (CHE)? ? 
N. º

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>¿Hay algún problema de integración con Microsoft Dataverse? 
N. º

