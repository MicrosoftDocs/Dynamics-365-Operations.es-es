---
title: Medidas de activo
description: En este tema se explica cómo crear tipos de medidas de activo en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bc6b9e944a7ecf6b769a8e3c2f9b1fbafaa60734
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626117"
---
# <a name="counters"></a>Contadores

[!include [banner](../../includes/banner.md)]

En este tema se explica cómo crear tipos de contadores en Administración de activos. Los tipos de contadores se usan para realizar registros de contadores en activos, por ejemplo, sobre el número de horas de producción, o la cantidad producida en el activo. Los tipos de activos están relacionados con los tipos de contadores. Esto significa que solo se puede usar un contador en un activo si el contador está configurado en el tipo de activo que se utiliza en el activo.

Para poder realizar registros de contadores en activos, debe crear primero los tipos de contador que desea usar en **Contadores**. A continuación, puede crear registros de contador en activos en **Contadores**. 

Los contadores se pueden usar en los planes de mantenimiento. Una línea de plan de mantenimiento puede ser de tipo "Contador" (relacionada, por ejemplo, con el número de horas de producción o la cantidad producida). 

Un registro del contador se puede actualizar manual o automáticamente en función de las horas de producción o la cantidad producida. Se puede configurar un contador para utilizar uno de los tres métodos de actualización (se seleccionan en el campo **Actualización** de **Contadores**):
  
- Manual: debe registrar manualmente los valores del contador.  
- Horas de producción: el contador se actualiza automáticamente en función del número de horas de producción.  
- Cantidad de producción: el contador se actualiza automáticamente en función de la cantidad producida.  

>[!NOTE]
>Si se utiliza la cantidad producida, *todos* los artículos registrados se incluyen en el registro del contador, tanto la cantidad sin errores como la cantidad con errores. Si es necesario, siempre es posible realizar registros manuales de contadores.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Crear tipos de contador para registros de contador de activo

1. Seleccione **Administración de activos** > **Configuración** > **Tipos de activos** > **Contadores**.
2. Seleccione **Nuevo** para crear un nuevo tipo de contador.
3. Inserte un identificador en el campo **Contador**, y un nombre de contador en el campo **Nombre**.
4. En la ficha desplegable **General**, seleccione una unidad de contador en el campo **Unidad**.
5. En el campo **Actualización**, seleccione el método de actualización que desea utilizar para el contador.
6. Seleccione "Sí" en el botón de alternancia **Heredar valores de contador** si los activos secundarios de una estructura de activo deben heredar automáticamente los registros de contador realizados en el activo principal.
7. En el campo **Agregado total**, seleccione el método de suma que se debe usar para un contador que use este tipo de contador. "Suma" es la selección estándar que se usa para sumar continuamente los valores registrado y el valor total. Se puede usar "Promedio" si un contador está configurado para supervisar un umbral (por ejemplo, de temperatura, vibraciones o desgaste de un activo). 
8. En el campo **Desviación por arriba**, inserte el nivel superior en porcentaje para validar si los registros de contador manuales se encuentran dentro de un intervalo esperado. La validación se basa en un aumento lineal de los registros de contador existentes.
9. En el campo **Desviación por debajo**, inserte el nivel inferior en porcentaje para validar si los registros de contador manuales se encuentran dentro de un intervalo esperado. La validación se basa en un disminución lineal de los registros de contador existentes.
10. En el campo **Tipo**, seleccione el tipo de mensaje (información, advertencia, error) que se debe mostrar si se producen desviaciones fuera del intervalo definido al crear registros de contador manuales.
11. En la ficha desplegable **Tipos de activos**, agregue los tipos de activos que deben poder usar el contador.
12. En la ficha desplegable **Contadores de activo relacionados**, agregue el contador que desea que se actualice automáticamente cuando se actualice este contador.


>[!NOTE]
>Un contador relacionado se actualiza automáticamente si el contador relacionado tiene el tipo de activo con el que está relacionado en la configuración del contador. Por ejemplo: puede configurar un contador para "Horas de producción" y agregar el tipo de activo "Motor de camión". Cuando se actualiza ese contador también se actualiza un contador relacionado, "Aceite", con los mismos valores del contador. La configuración de **Contadores** incluye la configuración de "Horas". Además, en el contador "Aceite", el tipo de activo "Motor de camión" debe agregarse a la ficha desplegable **Tipos de activos** para garantizar la relación del contador. En las capturas de pantalla siguientes puede ver un ejemplo de configuración de los contadores "Horas" y "Aceite".

Al agregar tipos de activo a un tipo de contador en **Contadores**, ese contador se agrega automáticamente a los tipos de activos en la ficha desplegable **Contadores** de [Tipos de activos](../setup-for-objects/object-types.md).

![Figura 1](media/071-setup-for-objects.png)

