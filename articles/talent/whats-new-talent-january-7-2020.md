---
title: Novedades y cambios en Dynamics 365 Talent (7 de enero de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
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
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462478"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a>Novedades y cambios en Dynamics 365 Talent (7 de enero de 2020)

Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2697. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a>No se pueden eliminar los trabajadores que no tienen registros de empleo - (386157)

Este cambio agrega una opción de eliminación en el formulario **Trabajadores sin empleo**. Los trabajadores aparecen en este formulario cuando no existen empleos futuros, activos o históricos para el trabajador. En esta versión, la eliminación solo está habilitada para los administradores del sistema. Sin embargo, en la versión de la próxima semana, la seguridad se actualizará para permitir que todos los usuarios con el rol de asistente de Recursos Humanos eliminen a los empleados sin empleo. También puede realizar estos cambios manualmente siguiendo los siguientes pasos.

1. Vaya a **Configuración de seguridad**.
2. En la pestaña **Privilegios**, filtre la lista **Privilegios** para **Mantener trabajadores**.
3. En la columna **Referencias**, seleccione **Elementos del menú de visualización**.
4. En **Elementos del menú de visualización**, seleccione **HcmWOrkersWithoutEmployment**.
5. Selecciona el permiso **Eliminar** para Conceder.
6. Seleccione la pestaña **Objetos sin publicar**.
7. Seleccione **Publicar todo**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]