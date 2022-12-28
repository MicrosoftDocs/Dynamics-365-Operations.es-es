---
title: Actualizaciones de calidad proactivas
description: Este artículo proporciona información sobre la entrega proactiva de actualizaciones de calidad.
author: rashmansur
ms.date: 11/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 7d8de017c54a13a9935d74d33a57813922c9f823
ms.sourcegitcommit: 8aee31d6dffabe13969dd5b9de4e0bf95f53e67e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887140"
---
# <a name="proactive-quality-updates"></a>Actualizaciones de calidad proactivas

[!include[banner](../includes/banner.md)]

En los últimos años, Microsoft ha hecho un progreso continuo en lo que llamamos [One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md). La premisa de One Version es simple: cuanto más cerca estemos de tener a todos los clientes con la misma versión de software, mayor será la calidad que podamos ofrecer. Encontramos y solucionamos problemas una vez, y ponemos esas soluciones en manos de más clientes con mayor rapidez.

Esta premisa se ve confirmada por los resultados: menor número de incidentes en todos nuestros productos. Cuando los clientes no tienen la misma versión, vemos constantemente que se ven afectados por problemas para los que ya hay una solución disponible. Ya hemos hecho un gran progreso con Dynamics 365 Finance, Dynamics 365 Supply Chain, Dynamics 365 Project Operations y Dynamics 365 Commerce, y gracias a los recientes avances técnicos, ahora es posible dar el siguiente paso. La siguiente información establece lo que vamos a hacer, lo que ya hemos hecho para preparar el escenario y cómo y cuándo presentaremos las nuevas capacidades sin interrupciones.

## <a name="what-you-need-to-know"></a>Lo que necesita saber

- Las actualizaciones de calidad proactivas (PQU) se aplican mensualmente.
- Se permiten excepciones para las actualizaciones de calidad proactivas para los clientes que están regulados solo por la Administración de Drogas y Alimentos de los EE. UU. (FDA).
- Las actualizaciones de calidad proactivas nunca degradarán el entorno ni actualizarán automáticamente de una versión de actualización del servicio a otra. 
- Microsoft está determinando cómo se administrarán las actualizaciones de calidad proactivas para entornos regulados y para clientes de nube soberanos y gubernamentales.
- Las notificaciones relacionadas con las actualizaciones de calidad proactivas se publican en el [Centro de mensajes de Microsoft 365](https://admin.microsoft.com/AdminPortal/).
- Cinco días antes de que se aplique una actualización de calidad proactiva a un entorno, se notifica a los clientes que se realizará la actualización.
- Los clientes no pueden cancelar ni posponer las actualizaciones de calidad proactivas.
- Las actualizaciones de calidad proactivas se instalan durante la [ventana de mantenimiento planificado](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows) del período específco de la región.
- Las actualizaciones de calidad están diseñadas para tener un bajo riesgo de problemas o regresiones, y esto es compatible con los datos de Microsoft.
- Microsoft recomienda realizar pruebas específicas para problemas específicos o revisiones específicas relacionadas con una actualización de calidad proactiva.
- TODOS los sandboxes, excepto aquellos que tienen una excepción con límite de tiempo debido a razones reglamentarias, se incorporarán antes del 7 de enero de 2023.
- La incorporación de producción para las actualizaciones de calidad proactiva comenzará a partir del 21 de enero de 2023. 
- La incorporación de producción solo comenzará para los proyectos de Lifecycle Services que tienen sandbox(es) incorporados y que hasta ahora reciben actualizaciones de calidad proactivas con una cadencia regular para todas las versiones de actualización de servicio admitidas. Esto solo se aplica a entornos de clientes a los que no se les ha proporcionado ninguna excepción debido a razones reglamentarias o legales.
- Para obtener un cronograma completo de actualizaciones de calidad proactivas para entornos de sandbox y producción en el transcurso de 2023, consulte a continuación.
- Cada actualización de servicio tiene al menos un tren de lanzamiento de PQU en curso o programado para comenzar. Una vez que sus entornos estén incorporados al proceso de PQU, puede recibir una actualización de calidad proactiva programada previamente en todos ellos cuando pase a una actualización de servicio de versión más nueva. Consulte el cronograma para determinar cuándo se programa una PQU para una actualización de servicio si planea actualizar a una versión más reciente de actualización de servicio. 

> [!Note]
> Los sandboxes y los entornos de producción de prueba de rendimiento estándar (nivel 4), prueba de rendimiento premium (nivel 5) recibirán PQU los fines de semana. 

## <a name="focus-on-quality-updates"></a>Centrarse en actualizaciones de calidad

Actualmente proporcionamos siete [actualizaciones de servicio](public-preview-releases.md) por año. Por ejemplo, la versión 10.0.29 es una actualización de servicio. Hasta hace poco, había ocho actualizaciones por año. Sin embargo, eliminamos una actualización en respuesta a los comentarios de los clientes que revelaron el deseo de evitar cambios cerca del final del año calendario.

No cambiaremos la cadencia de las actualizaciones del servicio. En cambio, nuestro próximo paso adelante en el viaje de One Version se centra en *actualizaciones de calidad*. Las actualizaciones de calidad son compilaciones acumulativas de revisiones. No incluyen nuevas características. En un momento dado, toda nuestra comunidad de clientes se reparte entre las tres o cuatro actualizaciones de servicio más recientes. Sin embargo, para cualquier actualización de servicio dada, se pueden usar docenas de versiones de actualización de calidad diferentes dentro del grupo, según las fechas en que las personas implementaron. En nuestro próximo paso, transmitiremos de manera proactiva actualizaciones de calidad. Ya usamos este modelo para nuestras aplicaciones basadas en Dataverse y han visto los resultados esperados de calidad mejorada y disminución de incidentes de soporte.

Por supuesto, una reducción de defectos podría reducir o eliminar por completo la necesidad de actualizaciones de calidad. Tenemos múltiples iniciativas en marcha para reducir los defectos que requieren actualizaciones de calidad. Incluso cuando las cargas útiles se reducen en la actualización de calidad, la coherencia en la base de clientes mejorará la capacidad de soporte, obtendrá mejoras para los clientes más rápidamente y reducirá la frecuencia con la que los clientes encuentran problemas para los que ya existen soluciones.

## <a name="making-proactive-distribution-possible"></a>Haciendo posible la distribución proactiva

Ya se han implementado múltiples avances que permiten la entrega proactiva de actualizaciones de calidad:

- **Actualización de tiempo de inactividad casi nulo** – Para impulsar entornos más frecuentes, es esencial que se reduzca el impacto en la disponibilidad del entorno para preservar los acuerdos de nivel de servicio (SLA) de Dynamics 365. La actualización con tiempo de inactividad casi nulo se introdujo originalmente para ayudar a mejorar la aplicación mensual de parches del sistema operativo mediante el uso de una conmutación por error del clúster para activar la imagen actualizada con una interrupción mínima. El mecanismo para aplicar actualizaciones se está mejorando para que sea aún menos disruptivo y cubrirá tanto la aplicación de parches del sistema operativo como la implementación de actualizaciones de calidad.

    En el caso de los usuarios interactivos, es posible que se interrumpa una sesión activa y el reintento irá al entorno ahora actualizado. Con la introducción de la [programación por lotes basada en prioridades](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), la programación y el procesamiento por lotes se recuperan y se reanudan inmediatamente después de la actualización. La programación por lotes basada en prioridades estará disponible para los clientes antes de que comiencen a participar en la distribución proactiva de actualizaciones de calidad para sus entornos de producción.

- **Horas oscuras** – Las horas oscuras se definen para cada región de Azure, y se producirán actualizaciones de tiempo de inactividad casi nulo durante el período de la hora oscura.

## <a name="the-proactive-update-process"></a>El proceso de actualización proactiva

La implementación de actualizaciones de calidad proactivas seguirá un proceso de implementación seguro (SDP). Los detalles del SDP evolucionarán, pero las actualizaciones de calidad se implementarán inicialmente en entornos de espacio aislado. A medida que aumente el porcentaje de sandboxes implementados con éxito, comenzará la implementación en entornos de producción. Los sistemas de escucha monitorearán la telemetría del sistema y los incidentes de Livesite, y detendrán el lanzamiento de una versión específica si se detecta alguna regresión. Los clientes aún podrán obtener las actualizaciones de calidad antes de la implementación proactiva si así lo desean.

Los datos de administración de versiones actuales muestran que menos del 3 por ciento de las regresiones se introducen en actualizaciones de calidad. Con un mayor enfoque en la eliminación de la regresión y un SDP mejorado, el impacto potencial de las regresiones será dramáticamente menor que las ganancias de calidad que se logran al implementar correcciones más rápidamente para los clientes en general.

## <a name="process-changes"></a>Procesar cambios

Se está implementando un conjunto de cambios de proceso antes de la activación de la implementación proactiva de actualizaciones de calidad:

- **Esquema** – Las herramientas garantizarán que las compilaciones de actualizaciones de calidad incluyan solo los cambios de esquema que se pueden aplicar mientras el servicio está en línea. Este enfoque ayudará a preservar la capacidad de aplicar la actualización con un tiempo de inactividad casi nulo.
- **Mayor escrutinio de cambios** – Actualmente, ya existe un paso de proceso adicional para aprobar los cambios para su inclusión en una actualización de calidad. El escrutinio en el paso adicional se incrementará para ayudar a reducir el potencial de regresiones. No se permiten cambios importantes en las actualizaciones de calidad, y el mayor escrutinio de cambios ayudará a garantizar que cumplamos este objetivo.
- **Visibilidad** - Se enviarán notificaciones a través del centro de administración, Lifecycle Services y otros canales disponibles para las próximas actualizaciones de calidad proactivas. Además, los equipos de soporte y los líderes de incidentes tendrán visibilidad de dónde se implementaron de manera proactiva las actualizaciones de calidad.

    > [!NOTE]
    > El equipo de comunicaciones de Microsoft está investigando una degradación continua de las herramientas de correo electrónico que impide la entrega de notificaciones por correo electrónico. Por favor continúe monitoreando el Centro de mensajes de Microsoft 365 para mensajes relacionados con la incorporación y notificación.

- **Fail Safe a través de tramos** – La distribución en tramos se utilizará para proteger los cambios de código cuando corresponda en una corrección de errores de actualización de calidad o usar la función existente de distribución en tramos relevante para la corrección. Si se requiere una reserva o desactivar un cambio después de una implementación proactiva, se puede hacer a través del sistema de tramos para evitar más fallas.
- **Designación de sincronización de sandbox**: la actualización escalonada a un sandbox aislado de elección junto con la producción no es compatible en este momento. Todos los entornos sandbox de nivel 2 y nivel 3 recibirán actualizaciones proactivas al menos 7 días antes del entorno de producción en un proyecto de Lifecycle Services. De nuevo, esto solo se aplica a entornos de clientes a los que no se les ha proporcionado ninguna excepción debido a razones reglamentarias o legales.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>¿Cuál es la hoja de ruta de implementación para las actualizaciones de calidad?

La distribución de actualizaciones de calidad proactivas para entornos sandbox comenzó en septiembre de 2022 para los clientes de la nube pública de Azure. Para el 1 de enero de 2023, completaremos la incorporación del 99 % de los sandbox a actualizaciones de calidad proactivas.

Solo se permiten excepciones al proceso de distribución actualizado proactivo para los clientes regulados por la FDA. Todavía estamos trabajando en cómo se gestionarán los entornos regulados y los clientes de nube soberanos y gubernamentales. 

Debido a que los clientes recibirán regularmente cargas útiles más pequeñas, esperamos que el proceso de mantenerse al día sea más simple. Ajustaremos la frecuencia de implementación de actualizaciones a medida que demostremos la capacidad de ejecutar el proceso sin interrupciones. Este proceso ya está funcionando eficazmente para nuestra plataforma y aplicaciones de Dataverse, y está entregando las mejoras anticipadas en la calidad del servicio. Estamos dando el mismo paso adelante para las aplicaciones de finanzas y operaciones.


## <a name="when-will-quality-updates-start-for-production-environments"></a>¿Cuándo comenzarán las actualizaciones de calidad para los entornos de producción?
Durante los primeros meses de 2023, a partir del 15 de enero, comenzaremos a incorporar entornos de producción para actualizaciones proactivas y aumentaremos gradualmente el porcentaje de entornos de producción que reciben actualizaciones proactivas. Solo nos enfocaremos en un entorno de producción en un proyecto de Lifecycle Services que ya tenga los entornos sandbox integrados para recibir actualizaciones proactivas. Antes de una actualización, los clientes con los entornos de producción que se están incorporando recibirán una notificación a través del centro de mensajes o el banner de Lifecycle Services. Para obtener un cronograma completo de actualizaciones de calidad proactivas para entornos de sandbox y producción en el transcurso de 2023, consulte a continuación.

## <a name="what-is-the-schedule-for-sandbox-proactive-quality-updates"></a>¿Cuál es la programación para las actualizaciones de calidad proactivas de espacio aislado?
Para obtener información sobre las horas de oscuridad para cada región, consulte [¿Cuáles son las ventanas de mantenimiento planeado por región?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).

### <a name="proactive-quality-update-release-10029"></a><a name="schedule"></a> Versión de actualización de calidad proactiva: 10.0.29
**Versión de la aplicación: 10.0.1326.70**  
**Correspondiente último artículo de KB: 750332**

| Estación | Regiones | Programación completa | Próxima programación de espacio aislado|
|---|---|---|---|
| Estación 1 | Centro de Canadá, este de Canadá, centro de Francia, centro de la India, este de Noruega, oeste de Suiza | 14 de octubre al 17 de octubre de 2022, 2 de noviembre al 5 de noviembre de 2022, 13 de noviembre al 16 de noviembre de 2022, 5 de diciembre al 8 de diciembre de 2022 | Del 2 al 5 de enero de 2023 |
| Estación 2 | Sur de Francia, sur de la India, oeste de Noruega, norte de Suiza, norte de Sudáfrica, este de Australia, sur de Reino Unido, norte de EAU, este de Japón, sudeste de Australia, sudeste de Asia | 15 de octubre al 18 de octubre de 2022, 2 de noviembre al 5 de noviembre de 2022, 13 de noviembre al 16 de noviembre de 2022, 5 de diciembre al 8 de diciembre de 2022 | Del 2 al 5 de enero de 2023 |
| Estación 3 | Este de Asia, oeste de Reino Unido, oeste de Japón, sur de Brasil, oeste de Europa, este de EE. UU., centro de EAU | 16 de octubre al 19 de octubre de 2022, 2 de noviembre al 5 de noviembre de 2022, 13 de noviembre al 16 de noviembre de 2022, 5 de diciembre al 8 de diciembre de 2022 | Del 2 al 5 de enero de 2023 |
| Estación 4 | Norte de Europa, centro de EE. UU., oeste de EE. UU. | 17 de octubre al 20 de octubre de 2022, 2 de noviembre al 5 de noviembre de 2022, 15 de noviembre al 18 de noviembre de 2022, 5 de diciembre al 8 de diciembre de 2022 | Del 2 al 5 de enero de 2023 |
| Estación 5 | DoD, Government Community Cloud (GCC), China | Sin programar | Sin programar |

### <a name="proactive-quality-update-release-10030"></a><a name="schedule"></a> Versión de actualización de calidad proactiva: 10.0.30
**Versión de la aplicación: 10.0.1362.77**
**Correspondiente último artículo de KB: 767597**

| Estación | Regiones | Programación completa | Próxima programación de espacio aislado |
|---|---|---|---|
| Estación 1 | Centro de Canadá, este de Canadá, centro de Francia, centro de la India, este de Noruega, oeste de Suiza | 1 de diciembre al 4 de diciembre de 2022 |  13 de diciembre al 16 de diciembre de 2022 | 
| Estación 2 | Sur de Francia, sur de la India, oeste de Noruega, norte de Suiza, norte de Sudáfrica, este de Australia, sur de Reino Unido, norte de EAU, este de Japón, sudeste de Australia, sudeste de Asia | 2 de diciembre al 5 de diciembre de 2022 |  13 de diciembre al 16 de diciembre de 2022 | 
| Estación 3 | Este de Asia, oeste de Reino Unido, oeste de Japón, sur de Brasil, norte de Europa, este de EE. UU., centro de EAU | 3 de diciembre al 6 de diciembre de 2022 |  13 de diciembre al 16 de diciembre de 2022 | 
| Estación 4 | Oeste de Europa, centro de EE. UU., oeste de EE. UU. | 4 de diciembre al 7 de diciembre de 2022 |  13 de diciembre al 16 de diciembre de 2022 | 
| Estación 5 | DoD, Government Community Cloud (GCC), China | Sin programar | Sin programar |

### <a name="proactive-quality-update-calendar-year-2023-schedule"></a><a name="schedule"></a> Calendario proactivo de actualización de calidad calendario año 2023

#### <a name="stations-to-region-mapping"></a><a name="Stations-Regions"></a> Mapeo de estaciones a regiones

| Estaciones | Regiones |
|---|---|
| Estación 1 | Por determinar |
| Estación 2 | Centro de Canadá, este de Canadá, centro de Francia, centro de la India, este de Noruega, oeste de Suiza |
| Estación 3 | Sur de Francia, sur de la India, oeste de Noruega, norte de Suiza, norte de Sudáfrica, este de Australia, sur de Reino Unido, norte de EAU, este de Japón, sudeste de Australia, sudeste de Asia |
| Estación 4 | Este de Asia, oeste de Reino Unido, oeste de Japón, sur de Brasil, norte de Europa, este de EE. UU., centro de EAU |
| Estación 5 | Oeste de Europa, centro de EE. UU., oeste de EE. UU. |
| Estación 6 | DoD, Government Community Cloud (GCC), China |


> [!IMPORTANT]
> Este es un calendario de alto nivel para el año 2023. Para obtener un cronograma más concreto, consulte el ejemplo a continuación para la versión 2 del 10.0.30 de enero. El horario exacto y la versión de la aplicación se actualizarán 7 días antes del inicio de un tren de actualización de calidad.

> [!Note]
> Solo los entornos de producción integrados recibirán la actualización para el tren 10.0.30 Release-2, los entornos integrados recibirán una comunicación explícita.

| Tren de actualización de calidad | Corte de versión | Duración del tren |
|---|---|---|
| Versión 10.0.30-2 | 16 de diciembre de 2022 | Del 2 al 29 de enero de 2023 |
| Versión 10.0.30-3 | 13 de enero de 2023 | 30 de enero-25 de febrero de 2023 |
| Versión 10.0.30-4 | 24 de febrero de 2023 | 6 de marzo - 8 de abril de 2023 |
| Versión 10.0.31-1 | 3 de febrero de 2023 | 13 de febrero de 2023 al 18 de marzo de 2023|
| Versión 10.0.31-2 | 3 de marzo de 2023 | 13 de marzo - 15 de abril de 2023|
| Versión 10.0.31-3 | 14 de abril de 2023 | 24 de abril de 2023 al 27 de mayo de 2023|
| Versión 10.0.32-1 | 31 de marzo de 2023 | 10 de abril de 2023 al 13 de mayo de 2023|
| Versión 10.0.32-2 | 28 de abril de 2023 | 8 de mayo de 2023 al 10 de junio de 2023|
| Versión 10.0.32-3 | 26 de mayo de 2023 | 5 de junio de 2023 al 8 de julio de 2023|
| Versión 10.0.33-1 | 28 de abril de 2023 | 8 de mayo de 2023 al 10 de junio de 2023|
| Versión 10.0.33-2 | 26 de mayo de 2023 | 5 de junio de 2023 al 8 de julio de 2023|
| Versión 10.0.33-3 | 14 de julio de 2023 | 24 de julio de 2023-26 de agosto de 2023|
| Versión 10.0.34-1 | 23 de junio de 2023 | 3 de julio de 2023-5 de agosto de 2023|
| Versión 10.0.34-2 | 21 de julio de 2023 | 31 de julio-2 de septiembre de 2023|
| Versión 10.0.34-3 | 1 de septiembre de 2023 | Del 11 de septiembre al 14 de octubre de 2023|
| Versión 10.0.35-1 | 28 de julio de 2023 | 7 de agosto - 9 de septiembre de 2023|
| Versión 10.0.35-2 | 25 de agosto de 2023 | Del 4 de septiembre al 7 de octubre de 2023|
| Versión 10.0.35-3 | 20 de octubre de 2023 | 30 de octubre de 2023-16 de diciembre de 2023|
| Versión 10.0.36-1 | 29 de septiembre de 2023 | 9 de octubre de 2023-11 de noviembre de 2023|
| Versión 10.0.36-2 | 27 de octubre de 2023 | 6 de noviembre de 2023-16 de diciembre de 2023|
| Versión 10.0.36-3 | 12 de enero de 2024 | 22 de enero de 2023-24 de febrero de 2024|
| Versión 10.0.37-1 | 3 de noviembre de 2023 | 13 de noviembre de 2023 al 6 de enero de 2024|
| Versión 10.0.37-2 | 30 de diciembre de 2023 | 8 de enero-10 de febrero de 2024|
| Versión 10.0.37-3 | 27 de enero de 2024 | 5 de febrero de 2024 al 9 de marzo de 2024|
| Versión 10.0.37-4 | 23 de febrero de 2024 | 4 de marzo - 6 de abril de 2024|

### <a name="proactive-quality-update-upcoming-10030-release-2-train-schedule"></a><a name="schedule"></a> Programación de tren de actualización de calidad proactiva próxima versión 10.0.30-2
**Versión de la aplicación: 10.0.1362.99**

| Estaciones | Próxima programación de espacio aislado | Programación de producción próxima |
|---|---|---|
| Estación 1 | No disponible | No disponible |
| Estación 2 | Del 2 al 5 de enero de 2023 | Del 21 al 22 de enero de 2023 |
| Estación 3 | Del 3 al 6 de enero de 2023 | Del 28 al 29 de enero de 2023 |
| Estación 4 | Del 9 al 12 de enero de 2023 | No disponible |
| Estación 5 | Del 16 al 19 de enero de 2023 | No disponible |
| Estación 6 | No disponible | No disponible |

> [!IMPORTANT] 
> Con cinco días de anticipación, Microsoft actualizará la programación anterior y enviará una notificación al conjunto de entornos que están programados para recibir estas actualizaciones de calidad. La programación anterior se aplica solo a los entornos que han sido notificados sobre una próxima actualización. Para obtener información sobre las horas de oscuridad para cada región, consulte [¿Cuáles son las ventanas de mantenimiento planeado por región?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).
>
> Para cada grupo de regiones, o *estación*, donde actualmente está programada la implementación de una actualización de calidad, la programación muestra un rango de cuatro días. Las actualizaciones de calidad comenzarán solo con entornos de espacio aislado. Después, a medida que aumente el porcentaje de sandboxes implementados con éxito, comenzará la implementación en entornos de producción con notificaciones avanzadas a los clientes.
> 
> Las actualizaciones de calidad siempre se producirán de forma continua, lo que nos permite apuntar a un conjunto de entornos por programación y completar todos los conjuntos al final del cuarto día para una estación. Sin embargo, esto no significa que una actualización del entorno durará cuatro días. Simplemente significa que no podemos predeterminar qué conjunto de entornos se actualizará en un día determinado dentro del rango de cuatro días. Todas las actualizaciones se realizarán durante las horas de oscuridad, con un tiempo de inactividad casi nulo. Las actualizaciones finalizarán definitivamente dentro de la ventana de la hora oscura de una región determinada.

## <a name="how-are-the-dark-hours-handled-for-customers-that-have-one-finance-and-operations-apps-instance-but-are-active-in-multiple-time-zones"></a>¿Cómo se gestionan las horas oscuras para los clientes que tienen una instancia de aplicaciones de finanzas y operaciones pero están activos en varias zonas horarias? 
No hay horarios especiales fuera de las horas oscuras donde existe una instancia de aplicaciones de finanzas y operaciones, ya que planeamos implementar actualizaciones de calidad de una manera mínimamente disruptiva con [nZDT](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-does-near-zero-downtime-maintenance-mean).

## <a name="what-is-the-current-rollout-cadence-for-proactive-quality-updates"></a>¿Cuál es la frecuencia actual de implementaciones para las actualizaciones de calidad proactivas?
Actualmente, las actualizaciones de calidad proactivas (PQU) se envían una vez al mes para cada versión admitida de una actualización de servicio. Solo se envía una actualización por mes para determinados entornos de espacio aislado, a menos que los clientes cambien a una nueva versión de actualización del servicio. En ese caso, pueden obtener una PQU preprogramada como parte de un tren existente para la actualización del nuevo servicio. Una vez que se complete el lanzamiento mundial en 2023, la frecuencia de estas actualizaciones aumentará. Siempre recibirá un aviso con al menos un mes de antelación cada vez que haya un cambio en la cadencia de envío.

## <a name="how-will-microsoft-ensure-the-quality-of-these-updates"></a>¿Cómo garantizará Microsoft la calidad de estas actualizaciones?
Microsoft se esfuerza por mantener la canalización de lanzamiento lo suficientemente eficiente como para entregar pequeñas cargas útiles para mantener bajo el costo de validación. Cada corrección en una actualización de calidad pasa por un proceso de implementación riguroso y seguro que ayuda a mejorar la calidad y la confiabilidad, reduciendo así el impacto en el cliente. La implementación se llevará a cabo por etapas en entornos de espacio aislado primero, seguida de producción. Las implementaciones por etapas permiten una supervisión adecuada para determinar si una implementación posterior es segura. Detendremos la implementación si se detectan problemas con cada grupo de clientes implementado y nos aseguraremos de que cada paso de la implementación tenga tiempo suficiente para que surjan los problemas. Para cada próxima actualización de calidad, brindaremos visibilidad del calendario a través de actualizaciones de documentación pública y correos electrónicos, para que los clientes puedan planificar con anticipación.

## <a name="can-customers-delay-reschedule-or-pause-a-quality-update"></a>¿Pueden los clientes retrasar, reprogramar o pausar una actualización de calidad?
N. º El principal objetivo de las actualizaciones de calidad es garantizar que aspectos fundamentales como la seguridad, la privacidad, la confiabilidad, la disponibilidad y el rendimiento mejoren continuamente para nuestros clientes. Al retrasar o pausar una actualización, la seguridad, la disponibilidad y la confiabilidad estarán en riesgo.

## <a name="how-do-i-know-what-set-of-changes-went-into-a-quality-update-payload"></a>¿Cómo sé qué conjunto de cambios que se incluyeron en una carga útil de actualización de calidad?
Siga estos pasos para identificar la lista de cambios que se incluyen en una carga útil de actualización de calidad. 

Use el tren de actualización de calidad 10.0.28 y la versión de la aplicación relacionada 10.0.1265.89.

1. En Lifecycle Services, abra la página **Detalles del entorno** para su espacio aislado. 
2. En la sección **Actualizaciones disponibles**, seleccione **Ver actualización** para la última compilación de actualización de calidad. 
3. Exporte la compilación a un CSV o archivo de Microsoft Excel.
4. En el archivo exportado, filtre y seleccione la **Versión de compilación** que es menor o igual que el número de compilación 10.0.1265.89. Ahora debería poder ver la carga útil delta.
 
> [!NOTE]
> La exportación a un archivo CSV o Excel debe realizarse antes de que se actualice el entorno. De lo contrario, puede usar un entorno con una configuración similar que no tenga instalada la actualización y seguir los pasos anteriores.

[![Ejemplo de entorno con actualización de calidad.](./media/how-to-get-kb-list-pqu.png)](./media/how-to-get-kb-list-pqu.png)

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>¿Cuál es el proceso si se encuentra un problema crítico después de una actualización de calidad?
Un problema crítico o regresión es uno o más eventos que generalmente hacen que varios clientes tengan una experiencia degradada con uno o más de nuestros servicios. Estos problemas pueden causar tiempo de inactividad no planificado, incluida la falta de disponibilidad, la degradación del rendimiento y la interferencia con la gestión del servicio. Si hay un impacto amplio en el cliente debido a dichas regresiones, detendremos el lanzamiento de una actualización de calidad hasta que podamos comunicarnos y solucionar el problema. Por lo general, la próxima actualización de calidad tendrá la solución necesaria para reanudar la implementación.

Si el entorno de un solo cliente se ve afectado, contacte con el soporte de Microsoft para abrir una incidencia. Según la justificación, detendremos la implementación de la actualización de calidad en todos los demás entornos de ese proyecto hasta que se mitigue el problema.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lifecycle-services"></a>¿Pueden los clientes aplicar manualmente las actualizaciones de revisión de Lifecycle Services?
Sí. Para garantizar la paridad continua con el funcionamiento de las revisiones, las actualizaciones de revisiones aún se pueden aplicar a los entornos de los clientes en Lifecycle Services. Sin embargo, es importante tener en cuenta que las revisiones que se implementan como parte de una actualización de calidad pasan por el SDP estándar antes de que se implemente la actualización. Esto reduce el riesgo de regresiones debido a una mayor calidad. Le recomendamos que elija una actualización de calidad en lugar de aplicar revisiones manualmente para aumentar la confiabilidad.

## <a name="can-customers-proactively-install-a-quality-update-build-ahead-of-the-schedule"></a>¿Pueden los clientes instalar de forma proactiva una actualización de calidad antes de lo previsto?
Sí. Puede instalar una actualización de calidad de forma proactiva. Microsoft omitirá la actualización si la versión de compilación actual del entorno es igual o superior a la actualización de calidad en cuestión.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Si un entorno tiene una próxima actualización de servicio mensual programada dentro de una semana, ¿seguirá recibiendo actualizaciones de calidad?
- Las actualizaciones de calidad no se aplican a entornos de producto si hay una actualización de servicio inminente programada dentro de una semana a partir de la fecha programada para la actualización de calidad.
- Si un entorno de espacio aislado tiene una versión de compilación igual o superior a la actualización de calidad inminente, se omitirá.
- Si un entorno de producción tiene una versión de compilación igual o superior a la actualización de calidad inminente, se omitirá.
- Si un espacio aislado tiene la misma versión de compilación o una superior debido a una actualización de calidad o una actualización manual de la producción, la producción seguirá recibiendo la versión programada de la actualización mensual del servicio. Si no desea que el entorno de producción programado se actualice a la versión de actualización del servicio, puede pausar la actualización del servicio desde Lifecycle Services. 
- Le recomendamos que utilice la última versión de actualización de calidad para probar sus cambios para una próxima actualización de servicio para una mejor estabilidad y resultados.

## <a name="if-an-environment-has-an-upcoming-scheduled-action-and-a-scheduled-quality-update-in-the-same-maintenance-window-will-it-still-receive-the-quality-update"></a>Si un entorno tiene una próxima acción programada y una actualización de calidad programada en la misma ventana de mantenimiento, ¿seguirá recibiendo la actualización de calidad?
Si hay algún conflicto con una acción preprogramada, por ejemplo, una restauración a un momento dado (PITR), la actualización de calidad se reprogramará para la próxima ventana de mantenimiento disponible dentro de la ventana de cuatro días. Para obtener más detalles sobre la programación, consulte [¿Cuál es el calendario para las actualizaciones de calidad proactivas?](#schedule). 

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>¿Se puede devolver un entorno a su estado anterior si hay problemas después de aplicar una actualización de calidad?
Después de aplicar una actualización de calidad, no hay reversión bajo ninguna circunstancia. Solo hay opciones de reenvío de parches disponibles para mitigar los problemas.

## <a name="what-about-fda-regulation-and-gxp"></a>¿Qué pasa con la regulación FDA y GxP?
El plan para clientes sujetos a la validación y regulación de la FDA aún está en evolución. Espere más actualizaciones en este espacio pronto. Por ahora, todos estos clientes están exentos de actualizaciones de calidad. Para asegurarse de que un cliente cumpla con las regulaciones de la FDA, visite [Oferta GxP de Microsoft Azure](/azure/compliance/offerings/offering-gxp).

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>¿Qué versiones de actualizaciones de servicio son compatibles con estas actualizaciones de calidad?
Los clientes de todas las versiones compatibles con las actualizaciones de servicio son aptos para las actualizaciones de calidad. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retail-sdk"></a>Las implementaciones de aplicaciones de finanzas y operaciones con componentes minoristas generalmente requieren trabajo adicional además de tener que volver a implementar MPOS. ¿Cómo afectarán estas actualizaciones de calidad al Retail SDK? 
Como la naturaleza de la revisión en sí no cambia en la carga útil de las actualizaciones de calidad, no anticipamos ningún impacto adicional específicamente relacionado con los componentes minoristas en este momento.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che"></a>¿Hay algún impacto en los entornos alojados en la nube (CHE)? 
Los entornos CHE están fuera del alcance de las actualizaciones de calidad porque están fuera del alcance de Microsoft.

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>¿Hay algún problema de integración con Microsoft Dataverse? 
No hay problemas de integración conocidos para las actualizaciones de calidad con Dataverse.

