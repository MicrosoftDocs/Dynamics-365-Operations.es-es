---
title: Dónde se usó el artículo
description: En este tema se explica cómo obtener una visión general de dónde se usa un artículo en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 511108e689c10e27a42253d95b02e5394f9eb713
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652365"
---
# <a name="item-where-used"></a>Dónde se usó el artículo

[!include [banner](../../includes/banner.md)]

 

Puede realizar un cálculo para que un artículo específico para obtener una visión general de dónde se ha utilizado el artículo en Administración de activos. Los resultados muestran el contexto en el que el artículo se ha utilizado durante su ciclo de vida. La página **Dónde se usó el artículo** se puede abrir desde el menú principal de Administración de activos y también puede tener acceso a la misma desde las siguientes páginas:

- [L. MAT. de activos](../objects/object-BOM.md)

- [Recambios en los valores predeterminados de tipos de activo](../setup-for-objects/object-types.md)

- [Previsión de artículos en la previsión de valores predeterminados de tipos de trabajo de mantenimiento](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [Previsión de mantenimiento de orden de trabajo](../work-orders/maintenance-forecasts.md)

- [Solicitud de compra de orden de trabajo](../work-orders/procurement.md)

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

