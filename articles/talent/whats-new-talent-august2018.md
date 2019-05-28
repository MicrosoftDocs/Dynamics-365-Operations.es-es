---
title: Novedades y cambios en Dynamics 365 for Talent Core HR (agosto de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 08/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-08-27
ms.dyn365.ops.version: Talent August 2018 update
ms.openlocfilehash: be76f29dc9d38cdf3c2d56120a830acae69937a4
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518994"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-august-2018"></a>Novedades y cambios en Dynamics 365 for Talent Core HR (agosto de 2018)

[!include [banner](includes/banner.md)]

**Compilación 8.1.104**

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 for Talent Core HR.

## <a name="view-expiring-records-in-manager-self-service"></a>Ver registros con fecha de vencimiento en autoservicio de directores

Ahora se pueden ver los registros con fecha de vencimiento en el autoservicio de directores. Las nuevas opciones le permiten configurar qué información estará disponible para que la vean los administradores. Entre estos valores se incluyen:

-   Certificados

-   Números de identificación

-   Períodos de prueba

-   Filtrados

-   Pruebas

Esta función también proporciona la capacidad para especificar el intervalo de días en los que buscar los registros que vencen.

## <a name="configurable-transfer-actions"></a>Acciones configurables de transferencia

Puede configurar por rol las opciones que estarán disponibles durante la entrada de una solicitud de transferencia. Esta característica añade flexibilidad a través de las funciones de una organización.

Por ejemplo, los administradores que solicitan transferencias de empleado pueden no tener acceso para realizar sugerencias o para especificar importes de compensación asociados a la solicitud de transferencia. En este caso, los administradores pueden crear y enviar solicitudes de transferencia pero no se les permite especificar asignaciones de compensación o de la lista de tareas. En esta misma configuración, RR. HH. podrá asignar nuevos valores de compensación así como asignar cualquier lista de comprobación adicional que se completará como resultado de completar la transferencia.

De forma predeterminada, las nuevas opciones de configuración se establecen para no cambiar las capacidades antes de la actualización.

## <a name="leave-and-absence"></a>Bajas y ausencias

Ahora hay campos de fecha adicionales disponibles en licencia y ausencia.

Con esta función puede establecer la base del período de acumulación en el nivel de plan para usar las fechas específicas del empleado. Esto permite usar fechas distintas de la fecha inicial del plan durante el proceso de acumulación de bajas. Las opciones para fechas específicas del empleado incluyen los valores siguientes:

-   Aduana (disponible antes de la actualización)

-   Fecha de aniversario

-   Fecha de contratación original

-   Antigüedad

-   Fecha inicial ajustada del trabajador

-   Primer día de trabajo del trabajador

Cuando está configurado para utilizar una de las fechas específicas de un empleado, el proceso de inscripción utilizará la fecha especificada para calcular los períodos de acumulación. La función del período de acumulación también se muestra en la inscripción del plan del empleado para ayudarle a comprender qué se está utilizando durante el proceso de acumulación.

## <a name="microsoft-word-integration"></a>Integración de Microsoft Word

Las plantillas de documento se han habilitado en todo Core HR. Esta función permite crear cartas e informes basados en las plantillas de Word que cree.

La información adicional sobre esta característica está disponible en [Tutorial de integración de Office](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json).


## <a name="other-fixes"></a>Otras correcciones

Este lanzamiento también incluye varias correcciones de errores, la adición de nuevas entidades, correcciones a las entidades existentes, y cambios de etiquetas localizados.
