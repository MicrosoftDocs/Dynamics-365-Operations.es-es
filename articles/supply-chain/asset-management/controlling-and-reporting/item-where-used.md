---
title: Dónde se usó el artículo
description: En este tema se explica cómo obtener una visión general de dónde se usa un artículo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: db0932c5a52030c1a7f0411163aee120e2173ca0
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021148"
---
# <a name="item-where-used"></a>Dónde se usó el artículo

[!include [banner](../../includes/banner.md)]

 

Puede realizar un cálculo para que un artículo específico para obtener una visión general de dónde se ha utilizado el artículo en Administración de activos. Los resultados muestran el contexto en el que el artículo se ha utilizado durante su ciclo de vida. La página **Dónde se usó el artículo** se puede abrir desde el menú principal de Administración de activos y también puede tener acceso a la misma desde las siguientes páginas:

- [L. MAT de activos](../objects/object-BOM.md)

- [Recambios en los valores predeterminados de tipos de activo](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [Categorías del tipo de trabajo de mantenimiento y tipos de trabajo de mantenimiento, variantes del tipo de trabajo de mantenimiento, comercios de trabajo de mantenimiento y listas de comprobación de mantenimiento](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [Previsión de mantenimiento](../work-orders/maintenance-forecasts.md)

- [Adquisición](../work-orders/procurement.md)

- [Compra de orden de trabajo](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>Realizar un cálculo de dónde se usó un artículo

1. Haga clic en **Administración de activos** > **Consultas** > **Dónde se usó el artículo** o seleccione el botón **Dónde se uso el artículo** en una de las páginas anteriormente mencionadas.

2. En el cuadro de diálogo **Dónde se usó el artículo**, seleccione el artículo para el que desea realizar el cálculo en el campo **Número de artículo**.

3. Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de artículo con respecto a las ubicaciones técnicas. 

    Por ejemplo, si especifica el número "1" en el campo, y tiene una estructura de varios niveles de la ubicación técnica, todas las líneas de artículo para una ubicación técnica se mostrará en el nivel superior. Por lo tanto, la relación o la cantidad en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior. 
    
    Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas de artículo en todos los niveles de la ubicación técnica con el que están relacionadas.

4. En la sección **Incluir**, seleccione "Sí" en los botones de alternar que desea incluir en el cálculo.

5. Haga clic en **Aceptar** para iniciar el cálculo.

6. En la pestaña **Dónde se usó el artículo** seleccione los botones **Agrupar por** para mostrar el nivel de detalle necesario del cálculo. Se resaltarán los botones **Agrupar por** seleccionados. Haga clic en un botón para activarlo o desactivarlo.

7. Si desea mostrar las dimensiones relacionadas con el artículo, haga clic en **Dimensiones de la pantalla** y seleccione las dimensiones que se mostrarán.

## <a name="example"></a>Ejemplo

En la siguiente imagen, verá un ejemplo de un cálculo de dónde se usó el artículo para el número "1000".

![Ejemplo de artículo dónde se usó el cálculo](media/12-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]