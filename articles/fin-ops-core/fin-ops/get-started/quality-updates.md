---
title: Actualizaciones de calidad proactivas
description: Este artículo proporciona información sobre la entrega proactiva de actualizaciones de calidad.
author: rashmansur
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9d81cb15e9a127e7bea7ad9b5e0f50a1ee543f71
ms.sourcegitcommit: 78e85ad49634cd31459fdb7325cb273352bf1501
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9338148"
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
- **Designación de sincronización de sandbox** – Menos del 20 por ciento de los clientes de hoy en día tienen múltiples sandboxes y mantienen un sandbox implementado donde la versión coincide con la producción, para ayudar con la resolución de problemas. En un futuro cercano, presentaremos la capacidad para que los clientes especifiquen un entorno de espacio aislado que no debería recibir la implementación de la actualización de calidad proactiva junto con otros espacios aislados, sino que debería recibirla más tarde, junto con el entorno de producción. Tenga en cuenta que si un cliente está usando un sandbox para probar una versión más nueva que su producción, ese sandbox recibirá actualizaciones de calidad para la versión más nueva.
- 
## <a name="when-will-proactive-quality-updates-start"></a>¿Cuándo comenzarán las actualizaciones proactivas de calidad?

Se espera que la distribución de actualizaciones de calidad proactivas para entornos sandbox comience a fines de septiembre u octubre de 2022 para los clientes de la nube pública de Azure. Los entornos de prueba también comenzarán a recibir una implementación de actualización proactiva en ese momento. En septiembre, se enviará una notificación a cada cliente para informarles sobre el horario previsto para sus entornos. Solo se permitirán excepciones al proceso de distribución actualizado proactivo para los clientes regulados por la FDA. Todavía estamos trabajando en cómo se gestionarán los entornos regulados y los clientes de nube soberanos y gubernamentales.

Durante el próximo período de seis meses, aumentaremos gradualmente el porcentaje de entornos de espacio aislado que reciben actualizaciones proactivas, hasta que se incluyan todos los entornos designados y se avance hacia la actualización de los entornos de producción. A lo largo del período, realizaremos un seguimiento para garantizar que el proceso de implementación sea fluido y que estemos alcanzando nuestro objetivo de cargas útiles no disruptivas.

Debido a que los clientes recibirán regularmente cargas útiles más pequeñas, esperamos que el proceso de mantenerse al día sea más simple. Ajustaremos la frecuencia de implementación de actualizaciones a medida que demostremos la capacidad de ejecutar el proceso sin interrupciones. Este proceso ya está funcionando eficazmente para nuestra plataforma y aplicaciones de Dataverse, y está entregando las mejoras anticipadas en la calidad del servicio. Estamos ansiosos por dar el mismo paso adelante para las aplicaciones de finanzas y operaciones.
