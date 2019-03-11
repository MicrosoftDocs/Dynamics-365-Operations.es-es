---
title: Novedades y cambios en Dynamics 365 for Talent Core HR (1 de octubre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 97820cd25ece48dc0b8045d9ba509d0971ca5aad
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "306081"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-1-2018"></a>Novedades y cambios en Dynamics 365 for Talent Core HR (1 de octubre de 2018)

[!include [banner](includes/banner.md)]

**Compilación 8.1.1035.0**

Este tema describe las características que son nuevas o que se han cambiado en Core HR.

## <a name="turn-off-electronic-payment-validation"></a>Desactiva la validación de pagos electrónicos

La validación de la información de los pagos electrónicos se produce si se definen desembolsos para depósitos directos a través del espacio de trabajo **Autoservicio para empleados** (ESS) o directamente en el formulario del empleado. Esta opción le da la flexibilidad para quitar esa validación si no necesita las comprobaciones de validación para los valores de importes y del importe restante. Esta función es útil si se está integrando con un sistema de nóminas externo con diferentes requisitos.

## <a name="manager-self-service---add-goals-for-team-members-through-the-team-performance-goals-tile"></a>Autoservicio de administrador - Agregar objetivos para los miembros del equipo a través del mosaico de objetivos de rendimiento de equipo

Antes de esta versión, los administradores podían agregar objetivos a sus empleados individualmente con los objetivos de rendimiento asociados a cada empleado. Con esta actualización, los administradores pueden tener acceso al mosaico **Objetivos de rendimiento de equipo** y crear nuevos objetivos seleccionando cualquiera de sus informes directos.

## <a name="manager-self-service---add-reviews-for-team-members-through-the-team-performance-reviews-tile"></a>Autoservicio de administrador - Agregar revisiones para los miembros del equipo a través del mosaico de revisiones de rendimiento de equipo

Antes de esta versión, los administradores podían agregar revisiones a sus empleados individualmente con los objetivos de revisión asociados a cada empleado. Con esta actualización, los administradores pueden tener acceso al mosaico **Revisiones de rendimiento de equipo** y crear nuevas revisiones seleccionando cualquiera de sus informes directos.

## <a name="configure-proration-options-by-leave-plan"></a>Configure las opciones de prorrateo en función el plan de licencia

Las organizaciones conceden tiempo libre de manera diferente basándose en cuándo los empleados se unen y dejan la empresa. Para algunas organizaciones, se concede a los empleados su asignación completa en su fecha de inicio mientras que otras prorratean la prima. Las nuevas opciones se proporcionan en esta versión para elegir cómo prorratear las primas y las acumulaciones para los empleados que se unen o dejan una organización. Las opciones incluyen: Prorrateo, Acumulación completa y Ninguna acumulación.

## <a name="other-changes"></a>Otros cambios

-   Entidad de empleado actualizada - Ahora **Personal** se puede actualizar usando el complemento de Excel/administración de datos.

-   Cambio de seguridad para permitir la eliminación de los botones **Eliminar** y **Desactivar** en el autoservicio del empleado para la información de pagos.

## <a name="known-issue"></a>Problema conocido

-   **Problema:** Al agregar nuevos archivos adjuntos a un trabajador, los botones **Nuevo** y **Editar** se atenúan. **Solución alternativa:** Antes de abrir la página de los datos adjuntos, asegúrese de que los cuadros informativos de la página **Trabajador** estén cerrados. Si se cierran los cuadros informativos cuando la página **Trabajador** se carga, los botones **Datos adjuntos** se habilitan. (Este problema se corregirá en la siguiente actualización de la plataforma).
