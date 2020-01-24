---
title: Novedades y cambios en Dynamics 365 Talent - Core HR (8 de octubre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/07/2018
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
ms.search.validFrom: 2018-10-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 30c148a1bf27a221c1d4feacbe89cabfc412872c
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897359"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-8-2018"></a>Novedades y cambios en Dynamics 365 Talent - Core HR (8 de octubre de 2018)

**Compilación 8.1.1050.0**

Este tema describe las características que son nuevas o que se han cambiado en Core HR.

## <a name="allow-other-dates-to-be-used-on-leave-tier-basis-leave-management"></a>Permitir que otras fechas se utilicen en la base de nivel de la licencia (Administración de la licencia)

Al conceder una licencia a los empleados, la función del nivel de baja determina cuánto tiempo de licencia acumula el empleado. Actualmente, estos niveles se basan en la fecha inicial del empleado y la fecha de antigüedad. En algunos casos, las organizaciones necesitan que estos niveles se basen en otras fechas, como la fecha del aniversario o la fecha original de contratación. Estas fechas ya se utilizan en el plan de la licencia para determinar cuándo se producen acumulaciones, se ha agregado la capacidad para que se usen estas mismas fechas si un empleado está inscrito en un plan para determinar el importe de acumulación. 

## <a name="other-changes"></a>Otros cambios
Se han incluido diversas correcciones en esta versión.

## <a name="known-issue"></a>Problema conocido

**Problema:** Al agregar nuevos archivos adjuntos a un trabajador, los botones **Nuevo** y **Editar** se atenúan. **Solución alternativa:** Antes de abrir la página de los datos adjuntos, asegúrese de que los cuadros informativos de la página **Trabajador** estén cerrados. Si se cierran los cuadros informativos cuando la página **Trabajador** se carga, los botones de datos adjuntos se habilitan. (Este problema se corregirá en la siguiente actualización de la plataforma).
