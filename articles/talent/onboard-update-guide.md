---
title: Actualizar guías de incorporación en Dynamics 365 Talent - Onboard
description: Este tema explica cómo actualizar las guías de incorporación en Microsoft Dynamics 365 Talent - Onboard y cómo insertar cambios en las guías existentes.
author: andreabichsel
manager: ''
ms.date: 06/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6175061456a03228043ea13767845cf4b54d6b2e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462518"
---
# <a name="update-onboarding-guides"></a>Actualizar guías de incorporación

[!include [banner](includes/banner.md)]

Si necesita realizar cambios en las guías de incorporación en Microsoft Dynamics 365 Talent: Onboard puede actualizarlas y insertar los cambios, aunque haya registrado ya las guías. Tiene dos opciones para actualizar una guía de incorporación:

- Editar la guía de incorporación directamente, y guardar los cambios.
- Edite la plantilla de incorporación y, a continuación, especificar los cambios en todas las guías de incorporación creadas desde ella.

## <a name="edit-an-onboarding-guide-directly"></a>Editar una guía de incorporación directamente

1. En el menú izquierdo, seleccione **Guías**.
2. Seleccione la guía que se desea editar.
3. Realice todos los cambios deseados, y seleccione el botón **Guardar** (el símbolo de disco).

    ![[Guardar cambios en una guía de incorporación](./media/onboard-save.png)](./media/onboard-save.png)

Onboard automáticamente enviará al nuevo empleado contratado un correo electrónico que indique cuáles son los cambios. Para facilitar la identificación, aparecerá una etiqueta roja indicando **Nuevo** junto a cada cambio.

## <a name="update-multiple-guides-by-editing-the-onboarding-template"></a>Actualizar varias guías editando la plantilla de incorporación

1. En el menú izquierdo, seleccione **Plantillas**.
2. En **Mis plantillas**, seleccione la plantilla que desea editar.
3. Realice todos los cambios deseados, y seleccione el botón **Guardar** (el símbolo de disco).
4. Para insertar los cambios en todas las guías que se basan en la plantilla, seleccione **Insertar estos cambios**.

    ![[Insertar los cambios de una plantilla de incorporación en todas las guías de incorporación creadas desde ella](./media/onboard-push-changes.png)](./media/onboard-push-changes.png)

Los cambios serán visibles para los nuevos empleados contratados que abran las guías de incorporación. Sin embargo, Onboard no enviará avisos de correo electrónico a los nuevos contratados para informarles de que la guía de incorporación ha cambiado. Para facilitar la identificación, aparecerá una etiqueta roja indicando **Nuevo** junto a cada cambio. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]