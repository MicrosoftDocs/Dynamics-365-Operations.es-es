---
title: Migración a la Optimización de planificación para la planificación maestra
description: Este artículo proporciona información sobre el nuevo motor de planificación maestro, Planning Optimization y sobre la migración desde el motor existente.
author: t-benebo
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2020-11-05
ms.dyn365.ops.version: ''
ms.openlocfilehash: a94b424ad1a454feecede8a7b037171b2984504f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846110"
---
# <a name="migration-to-planning-optimization-for-master-planning"></a>Migración a la Optimización de planificación para la planificación maestra

[!include [banner](../includes/banner.md)]

El motor de planificación maestro incorporado está programado para quedar obsoleto (en desuso). Está siendo reemplazado por el complemento de optimización de planificación para Microsoft Dynamics 365 Supply Chain Management. Este artículo proporciona información sobre el impacto en las implementaciones nuevas y existentes. Incluye información sobre las acciones necesarias.

Optimización de planificación permite que los cálculos de planificación maestra se realicen fuera de Supply Chain Management y su base de datos Azure SQL. Los beneficios que están asociados con Optimización de la planificación incluyen un rendimiento mejorado y un impacto minimizado en la base de datos SQL durante las ejecuciones de la planificación maestra. Como las ejecuciones rápidas de la planificación se pueden realizar incluso durante las horas de oficina, los planificadores puedan inmediatamente reaccionar a los cambios de la demanda o configuración de parámetros.

Para obtener más información sobre la Optimización de la planificación, consulte [Visión general de la Optimización de la planificación](planning-optimization/planning-optimization-overview.md).

## <a name="obsolescence-of-the-existing-master-planning-engine"></a>Obsolescencia del motor de planificación maestra existente

Microsoft está en proceso de hacer obsoleto el motor de planificación integrado en favor de la optimización de la planificación. Este cambio afecta a todos los entornos de nube. Las instalaciones locales no se ven afectadas. En la versión 10.0.16 y posteriores, recibirá un mensaje de error si ejecuta la planificación maestra incorporada sin generar órdenes de producción planificadas. Sin embargo, la ejecución de la planificación maestra se completará con éxito a pesar del mensaje de error.

Para obtener más información sobre la obsolescencia del motor de planificación integrado, consulte los anuncios en [Funciones eliminadas o obsoletas en Dynamics 365 Supply Chain Management](../get-started/removed-deprecated-features-scm-updates.md).

## <a name="migration-messages-and-exceptions"></a>Migración, mensajes y excepciones

Los propietarios de entornos existentes que ejecutan el motor de planificación maestro incorporado sin generar órdenes de producción planificadas recibirán un correo electrónico que proporciona detalles sobre el proceso de excepción. Le recomendamos que trabaje con un socio para evaluar y planificar la migración a Planning Optimization.

Como se ha mencionado, en la versión 10.0.16 y posteriores, recibirá un mensaje de error si ejecuta la planificación maestra incorporada sin generar órdenes de producción planificadas. Este mensaje de error incluye orientación sobre la migración e instrucciones para solicitar una excepción.

### <a name="new-deployments"></a>Nuevas implementaciones

Planning Optimization debe considerarse el motor de planificación maestro predeterminado para todas las nuevas implementaciones en la nube. En general, la Optimización de la planificación debe utilizarse para todas las implementaciones nuevas que no generan órdenes de producción planificadas durante la planificación maestra. Si una nueva implementación depende de la funcionalidad que Planning Optimization no admite actualmente, puede solicitar una excepción para poder seguir utilizando el motor de planificación maestro integrado.

### <a name="existing-deployments"></a>Implementaciones existentes

Los propietarios de implementaciones existentes basadas en la nube que dependen de la planificación maestra deben planificar la migración a Optimización de la planificación. Si la implementación depende de la funcionalidad que Planning Optimization no admite actualmente, puede solicitar una excepción para poder seguir utilizando el motor de planificación maestro integrado.

Para los entornos que actualmente utilizan procesos de planificación maestra que se están volviendo obsoletos, Microsoft enviará un correo electrónico al administrador del entorno. Este correo electrónico proporcionará información sobre las acciones necesarias para migrar o solicitar una excepción.

## <a name="the-exception-process"></a>El proceso de excepciones

Puede solicitar una excepción si debe continuar utilizando el motor de planificación maestro integrado porque sus procesos comerciales dependen en gran medida de al menos una función que no está implementada actualmente en Planning Optimization. Para obtener una lista de las funciones disponibles, consulte [Análisis de ajuste de optimización de planificación](planning-optimization/planning-optimization-fit-analysis.md).

Actualmente, las excepciones para la migración a Optimización de la planificación solo son pertinentes si su proceso de planificación maestra no incluye la producción (es decir, las órdenes de producción planificadas generadas por la planificación maestra) y necesita el motor de planificación maestra incorporado más allá de la versión 10.0.15.

Una vez que las funciones necesarias estén disponibles, Microsoft proporcionará un período de gracia hasta que expire la excepción. Se informará al administrador del entorno cuando las funciones necesarias estén disponibles y haya comenzado el período de gracia.

El siguiente diagrama de flujo resume la información proporcionada en este artículo para que pueda averiguar rápidamente si debe solicitar una excepción. Si necesita solicitar una excepción, complete y envíe el [Cuestionario de excepción y migración de Planning Optimization](https://go.microsoft.com/fwlink/?linkid=2144962). El grupo de productos es responsable de evaluar y aprobar cada solicitud de excepción, así que envíe su solicitud directamente al grupo de productos mediante el enlace provisto y no cree un ticket de soporte para ello. Si se rechaza su solicitud, no cree una incidencia de soporte técnico porque el Soporte de Microsoft no puede volver a evaluar ni otorgar excepciones.

![Diagrama de flujo de excepciones.](media/exception-diagram.png "Diagrama de flujo de excepciones")

> [!NOTE]
> Solo puede solicitar una excepción para los inquilinos que actualmente incluyen, o incluirán, un entorno de producción, no solo para los inquilinos con entornos de espacio aislado. Si necesita deshabilitar el error de excepción de Planning Optimization en un entorno de espacio aislado de infraestructura como servicio (IaaS), ejecute la consulta SQL proporcionada en [Entornos de espacio aislado](#faq-sandbox).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="sandbox-environments"></a><a name="faq-sandbox"></a>Entornos de espacio aislado

¿Puedo utilizar la planificación maestra integrada en mi entorno de espacio aislado? ¿Necesito una excepción?

**Responder:** Las excepciones no suelen ser relevantes para los entornos de espacio aislado porque el error de excepción de Planning Optimization no impide que el motor de planificación maestro integrado se ejecute correctamente. Sin embargo, si el mensaje de error le molesta, puede deshabilitarlo en un entorno de espacio aislado de IaaS (no Service Fabric) ejecutando la siguiente consulta en su base de datos:

```sql
-- Insert or update an enabled flight:
DECLARE @flightName NVARCHAR(100) = 'ReqPlanningOptimizationExceptionToggle';
IF NOT EXISTS (SELECT TOP 1 1 FROM SysFlighting WHERE flightName = @flightName)
    INSERT INTO SYSFLIGHTING(FLIGHTNAME,ENABLED, FLIGHTSERVICEID,PARTITION)
    SELECT @flightName, 1, 12719367,RECID FROM DBO.[PARTITIONS];
ELSE
    UPDATE SysFlighting SET enabled = 1, flightServiceId = 12719367 WHERE flightName = @flightName;
```

### <a name="on-premises-environments"></a>Entornos locales

Mi entorno es local. ¿Necesito una excepción?

**Responder:** No. No se requiere una excepción para los entornos locales. Puede seguir utilizando la planificación maestra incorporada. El administrador de su entorno será informado si se requiere alguna acción.

### <a name="production-scenarios"></a>Escenarios de producción

Usamos órdenes de producción planificadas, pero me preocupa lo que sucederá cuando actualicemos a la versión 10.0.16. ¿Debería tomar alguna medida?

**Responder:** No debería preocuparse. Puede seguir utilizando la planificación maestra incorporada en la versión 10.0.16. Sin embargo, le recomendamos que evalúe si la migración a Planning Optimization puede comenzar con la funcionalidad actual. También le recomendamos que se mantenga informado sobre las nuevas funciones.

### <a name="email-from-microsoft"></a>Correo electrónico de Microsoft

Nuestro administrador de entorno recibió un correo electrónico de Microsoft. Este correo electrónico indica que debemos migrar a Planning Optimization o solicitar una excepción. ¿Necesito realizar alguna acción?

**Respuesta:** Sí. Su entorno se verá afectado a menos que siga las instrucciones del correo electrónico. Puede migrar a Planning Optimization en la fecha especificada o solicitar una excepción mediante el enlace del correo electrónico. Este enlace abre un cuestionario. Una vez que haya completado y enviado este cuestionario, recibirá una respuesta por correo electrónico. Aunque este proceso es manual, Microsoft intenta responder dentro de una semana después de que se envía el cuestionario.

### <a name="error-messages"></a>Mensajes de error

Estoy usando la versión 10.0.16 o posterior y recibo el siguiente mensaje de error cuando ejecuto la planificación maestra. ¿Se ha bloqueado la planificación maestra?

> Recibe este mensaje de error porque el motor de planificación maestro integrado se utilizó para escenarios compatibles con Optimización de la planificación. Debe migrar a Optimización de la planificación ahora, ya que la planificación maestra incorporada actual quedará obsoleta. Tenga en cuenta que esta ejecución de planificación maestra se completó correctamente.
>
> En caso de que su migración tenga una fuerte dependencia de las características pendientes, se puede solicitar una excepción al uso continuo del motor de planificación maestro integrado.
>
> Complete el siguiente cuestionario para comenzar y, si es relevante, solicite una excepción de la migración a Optimización de la planificación.

**Responder:** No, la planificación maestra no está bloqueada. Su ejecución de planificación maestra se completó con éxito y puede utilizar el resultado de la forma habitual. Sin embargo, para evitar recibir este mensaje de error durante las futuras ejecuciones de planificación maestra, debe migrar a Optimización de la planificación inmediatamente o solicitar una excepción mediante el enlace del mensaje de error.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
