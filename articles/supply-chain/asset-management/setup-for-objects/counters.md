---
title: Medidas de activo
description: En este tema se explica cómo crear tipos de medidas de activo en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c445832a649c4f6a6642036ecab325e8aa2079
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783581"
---
# <a name="asset-measures"></a>Medidas de activo

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En este tema se explica cómo crear tipos de medidas de activo en Administración de activos. Los tipos de medida de activo se usan para realizar registros de medida en activos (por ejemplo, sobre el número de horas de producción, o la cantidad producida en el activo). Los tipos de activo están relacionados con los tipos de medidas de activo. Esto significa que solo se puede usar una medida de activo en un activo si la medida de activo está configurada en el tipo de activo que se utiliza en el activo.

Para poder realizar registros de medida en activos, debe crear primero los tipos de medida de activo que desea usar en **Contadores**. A continuación, puede crear registros de medida para activos en **Medidas de activo**. 

Las medidas de activo se pueden usar en los planes de mantenimiento. Una línea de plan de mantenimiento puede ser de tipo "Contador" (relacionada, por ejemplo, con el número de horas de producción o la cantidad producida). 

Un registro de la medida de activo se puede actualizar manual o automáticamente en función de las horas de producción o la cantidad producida. Se puede configurar una medida de activo para utilizar uno de los tres métodos de actualización (se seleccionan en el campo **Actualización** de **Contadores**):
  
- Manual: debe registrar manualmente los valores de medida de activo.  
- Horas de producción: el contador se actualiza automáticamente en función del número de horas de producción.  
- Cantidad de producción: el contador se actualiza automáticamente en función de la cantidad producida.  

>[!NOTE]
>Si se utiliza la cantidad producida, *todos* los artículos registrados se incluyen en el registro de la medida, tanto la cantidad sin errores como la cantidad con errores. Si es necesario, siempre es posible realizar registros manuales de medidas de activo.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Crear tipos de contador para registros de contador de activo

1. Seleccione **Administración de activos** > **Configuración** > **Tipos de activos** > **Contadores**.
2. Seleccione **Nuevo** para crear un nuevo tipo de medida de activo.
3. Inserte un identificador en el campo **Contador**, y un nombre de contador en el campo **Nombre**.
4. En la ficha desplegable **General**, seleccione una unidad de medida en el campo **Unidad**.
5. En el campo **Actualización**, seleccione el método de actualización que desea utilizar para la medida de activo.
6. Seleccione "Sí" en el botón de alternancia **Heredar valores de contador** si los activos secundarios de una estructura de activo deben heredar automáticamente los registros de medida de activo realizados en el activo principal.
7. En el campo **Agregado total**, seleccione el método de suma que se debe usar para una medida de activo que use este tipo de medida de activo. "Suma" es la selección estándar que se usa para sumar continuamente los valores registrado y el valor total. Se puede usar "Promedio" si una medida de activo está configurada para supervisar un umbral (por ejemplo, de temperatura, vibraciones o desgaste de un activo). 
8. En el campo **Desviación por arriba**, inserte el nivel superior en porcentaje para validar si los registros de medida de activo manuales se encuentran dentro de un intervalo esperado. La validación se basa en un aumento lineal de los registros de medida de activo existentes.
9. En el campo **Desviación por debajo**, inserte el nivel inferior en porcentaje para validar si los registros de medida de activo manuales se encuentran dentro de un intervalo esperado. La validación se basa en una disminución lineal de los registros de medida de activo existentes.
10. En el campo **Tipo**, seleccione el tipo de mensaje (información, advertencia, error) que se debe mostrar si se producen desviaciones fuera del intervalo definido al crear registros de medida de activo manuales.
11. En la ficha desplegable **Tipos de activos**, agregue los tipos de activos que deben poder usar la medida de activo.
12. En la ficha desplegable **Medidas de activo relacionadas**, agregue las medidas de activo que desea que se actualicen automáticamente cuando se actualice esta medida de activo.


>[!NOTE]
>Una medida de activo relacionada se actualiza automáticamente si tiene el tipo de activo con el que está relacionada en la configuración de la medida de activo. Por ejemplo: puede configurar una medida de activo para "Horas de producción" y agregar el tipo de activo "Motor de camión". Cuando se actualiza esa medida de activo también se actualiza un contador relacionado, "Aceite", con los mismos valores de la medida de activo. La configuración de **Contadores** incluye la configuración de "Horas". Además, en la medida de activo "Aceite", el tipo de activo "Motor de camión" debe agregarse a la ficha desplegable **Tipos de activos** para garantizar la relación de la medida de activo. En las capturas de pantalla siguientes puede ver un ejemplo de configuración de las medidas de activo "Horas" y "Aceite".

Al agregar tipos de activo a un tipo de medida de activo en **Contadores**, esa medida de activo se agrega automáticamente a los tipos de activos en la ficha desplegable **Contadores** de [Tipos de activos](../setup-for-objects/object-types.md).

![Figura 1](media/071-setup-for-objects.png)


