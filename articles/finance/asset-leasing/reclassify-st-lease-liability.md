---
title: Reclasificar la parte a corto plazo de un pasivo por arrendamiento
description: Este tema explica cómo crear un movimiento de diario mensual para reclasificar una parte del pasivo por arrendamiento como a corto plazo.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7d98d66b5fe9d32a86eb75d937fedfdca6773ac4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823104"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a>Reclasificar la parte a corto plazo de un pasivo por arrendamiento

[!include [banner](../includes/banner.md)]

Este tema explica cómo crear un movimiento de diario mensual para reclasificar una parte del pasivo por arrendamiento como a corto plazo. Cuando la programación que se selecciona en el proceso por lotes es **Reclasificación del pasivo por arrendamiento a corto plazo**, se crea un movimiento de diario. Esta entrada se utiliza para contabilizar la parte actual del pasivo por arrendamiento el último día del mes. Al mismo tiempo, se registra una entrada de reversión a partir del primer día del mes siguiente.

La parte a corto plazo del pasivo por arrendamiento se muestra en el programa de amortización de pasivos. Cuando se registra el movimiento del diario, la columna **Diario de reclasificación de pasivos creado** está disponible y el id. de diario también se completa en la programación.

Para crear y contabilizar el movimiento de diario de reclasificación de pasivos a corto plazo, siga estos pasos.

1. Vaya a **Arrendamiento de activos \> Periódico \> Creación de diario de lotes**.
2. En el cuadro de diálogo **Creación de diario de lotes**, en el campo **Seleccionar programación**, seleccione **Reclasificación del pasivo por arrendamiento a corto plazo**.
3. En el campo **Grupo de arrendamientos**, seleccione un grupo de arrendamientos. Alternativamente, en el campo **Id. del libro**, seleccione el id. del libro.
4. Active el parámetro **Registrar**. Alternativamente, si la entrada debe crearse pero no publicarse, deje este parámetro desactivado.
5. Seleccione **Aceptar**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
