---
title: Nivel de servicio y descripción
description: Este tema explica el nivel de servicio y su descripción en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8bb56e5103bd9e18e88c164cd308e55d48e64823
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019388"
---
# <a name="service-level-and-description"></a>Nivel de servicio y descripción

[!include [banner](../../includes/banner.md)]

 

Cuando cree una orden de trabajo, puede que desee definir los niveles de servicio para este y agregarle una descripción general. Puede crear niveles de servicio de la orden de trabajo en la página **Niveles de servicio de la orden de trabajo** y descripciones en la página **Descripción de la orden de trabajo**.

## <a name="create-a-service-level"></a>Crear un nivel de servicio

1. Seleccione **Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Nivel de servicio**.
2. Seleccione **Nuevo**.
3. En el campo **Nivel de servicio**, especifique el nivel de servicio (por ejemplo, un número).
4. Escriba un nombre en el campo **Nombre**.

    En la ficha desplegable **Órdenes de trabajo**, puede definir las fechas y horas esperadas de inicio y finalización. Los campos de esta ficha desplegable definen el periodo durante el cual deben iniciarse y finalizarse las órdenes de trabajo. Se utilizan para órdenes de trabajo que se crean manualmente y órdenes de trabajo que se crean a partir de solicitudes de mantenimiento. 

5. En el campo **Día de inicio**, especifique un número de días para definir el periodo durante el cual debe comenzar la orden de trabajo. El número de días se calcula a partir de la fecha de creación de la orden de trabajo. Por ejemplo, si la orden de trabajo debe comenzar cuando se crea, introduzca **0**. Si la orden de trabajo debe comenzar en el plazo de una semana después de crearla, introduzca **7**.
6. Para establecer una hora de inicio para la orden de trabajo, además de una fecha de inicio, establezca la opción **Establecer hora de inicio** en **Sí**. A continuación, especifique la hora de inicio en el campo **Hora de inicio**. Si establece la opción **No**, se utiliza la hora del día actual.
7. En el campo **Día de finalización**, especifique un número de días para definir el periodo durante el cual debe finalizar la orden de trabajo. El número de días se calcula a partir de la fecha de inicio de la orden de trabajo. Por ejemplo, si la orden de trabajo debe finalizar en el plazo de una semana de su fecha de inicio, introduzca **7**.
8. Para establecer una hora de finalización para la orden de trabajo, además de una fecha de finalización, establezca la opción **Establecer hora de finalización** en **Sí**. A continuación, especifique la hora de finalización en el campo **Hora de finalización**. Si establece la opción **No**, se utiliza la hora del día actual.
9. Seleccione **Guardar**.

![Página de nivel de servicio de órdenes de trabajo](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a>Crear una descripción

1. Seleccione **Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Descripciones**.
2. Seleccione **Nuevo**.
3. En el campo **Descripción**, escriba la descripción.
4. Seleccione **Guardar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]