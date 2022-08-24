---
title: Establecer derechos de administrador para eventos de la vida
description: Este artículo explica cómo configurar derechos de administrador para eventos de vida en Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9deed240977394667cee8b107397267b182d960b
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229916"
---
# <a name="set-administrator-rights-for-life-events"></a>Establecer derechos de administrador para eventos de la vida

[!include [banner](../includes/preview-banner.md)]

Los administradores pueden actualizar las opciones de eventos de vida, según los ajustes de configuración. Sobre la página **Parámetros de recursos humanos**, puede configurar parámetros que permitan a los administradores realizar cambios en las selecciones de planes. También puede restringir completamente que los administradores realicen cambios.

En la página **Parámetros de recursos humanos**, puede configurar restricciones de cambio de plan para planes confirmados y opciones de eventos de vida.

Si se selecciona la opción **Planes confirmados**, los cambios solo se pueden realizar si hay un período de inscripción activo. (Los ejemplos de períodos de inscripción incluyen períodos de inscripción abierta, períodos de inscripción de nuevos empleados y períodos de inscripción de eventos de vida). Si no se selecciona esta opción, se pueden realizar cambios en cualquier momento.

Si **Opciones de eventos de vida** está seleccionada, los cambios de plan durante un evento de vida están restringidos por las opciones de evento de vida que se definen en el tipo de plan. Si esta opción no está seleccionada, las selecciones de planes se pueden cambiar durante un evento de vida.

## <a name="set-plan-change-restrictions"></a>Establecer restricciones de cambio de plan

Sobre la página **Parámetros de recursos humanos**, en la ficha **Gestión de beneficios**, los siguientes campos están disponibles.

| Campo | Description |
|-------|-------------|
| Planes confirmados | Seleccione esta opción si se permiten cambios en un plan solo si hay un período de inscripción activo. Si esta opción no está seleccionada, se pueden realizar cambios en cualquier momento. |
| Opciones de evento de vida | Seleccione esta opción si los cambios de plan durante un evento de vida están restringidos por las opciones de evento de vida que se definen en el tipo de plan. Si esta opción no está seleccionada, las selecciones de planes se pueden cambiar durante un evento de vida. |
