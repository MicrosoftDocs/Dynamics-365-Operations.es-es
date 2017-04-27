---
title: "Hojas de gestión de costes"
description: "La configuración de la hoja de gestión de costes implica dos objetivos. En primer lugar, se define el formato para la visualización de la información de coste de los bienes vendidos acerca de un artículo fabricado o un pedido de producción. La visualización con formato se denomina &quot;hoja de gestión de costes&quot;. En segundo lugar, se define la base del cálculo de los costes indirectos. La configuración de la hoja de gestión de costes se basa en la característica de grupo de costes para la visualización de información y para las fórmulas de cálculo de costes indirectos. En este artículo se describen los dos objetivos de la configuración de la hoja de gestión de costes:"
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CostSheetDesigner
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53201
ms.assetid: e7d72b43-3892-49ae-8821-9eede3f4d24a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9d3f356b62d272fef7d0f131c9e29605f1be5c6b
ms.lasthandoff: 03/29/2017


---

# <a name="costing-sheets"></a>Hojas de gestión de costes

[!include[banner](../includes/banner.md)]


La configuración de la hoja de gestión de costes implica dos objetivos. En primer lugar, se define el formato para la visualización de la información de coste de los bienes vendidos acerca de un artículo fabricado o un pedido de producción. La visualización con formato se denomina "hoja de gestión de costes". En segundo lugar, se define la base del cálculo de los costes indirectos. La configuración de la hoja de gestión de costes se basa en la característica de grupo de costes para la visualización de información y para las fórmulas de cálculo de costes indirectos. En este artículo se describen los dos objetivos de la configuración de la hoja de gestión de costes: 

Una hoja de gestión de costes es la visualización con formato de la información acerca del coste de los bienes vendidos para un artículo fabricado o un pedido de producción. Cuando configure una hoja de gestión de costes, defina el formato de la información y defina también la base para calcular los costes indirectos. La configuración de la hoja de gestión de costes se basa en las características de grupo de costes para la visualización de información y para las fórmulas que se usan para calcular el coste indirecto. Aquí se encuentra más información acerca de los dos objetivos de la configuración de la hoja de gestión de costes:
-   **Definir el formato de la hoja de gestión de costes.** El formato definido por el usuario de una hoja de gestión de costes identifica la segmentación de los costes que contienen el coste de los bienes vendidos de un artículo fabricado. Por ejemplo, la información de coste de los bienes vendidos de un artículo se podría segmentar en materiales, mano de obra y gastos generales según grupos de costes. Estos grupos de coste se asignarán a los artículos, las categorías de costes de las operaciones de enrutamiento y las fórmulas de cálculo de costes indirectos. El formato de la hoja de gestión de costes suele requerir totales inmediatos cuando se hayan definido varios grupos de costes. Por ejemplo, varios grupos de costes relacionados con el material se pueden agregar. La definición de un formato de hoja de gestión de costes es opcional, pero su definición es obligatoria cuando se calculan costes indirectos.
-   **Definir la base del cálculo de los costes indirectos.** Los costes indirectos reflejan los gastos generales de fabricación asociados a la producción de un artículo fabricado. Una fórmula de cálculo de costes indirectos se puede expresar como un suplemento o como una cuota. Un suplemento representa un porcentaje de un valor, mientras que una cuota representa un importe por hora para una operación de enrutamiento. Un grupo de costes define la base de la fórmula de cálculo como, por ejemplo, un suplemento del 100 por cien para un grupo de costes de mano de obra o una cuota por hora de 50,00 USD para un grupo de costes de máquinas. Si desea definir una fórmula de cálculo y su base de grupo de costes, la configuración de la hoja de gestión de costes requiere que identifique el grupo de costes que representa los gastos generales y que seleccione si desea usar un método de suplemento o de cuota.

Las fórmulas de cálculo se deben especificar como un registro de costes. Este consta de una versión de gestión de costes, un porcentaje de suplemento o un importe de cuota, la base del grupo de costes, un estado y una fecha de vigencia. La primera vez que se especifica un registro de coste, presenta un estado **Pendiente** y una fecha de vigencia. Al activar el registro de costes, se actualiza el estado para que el registro sea el registro actualmente activo y la fecha de vigencia se actualiza a la fecha de activación. En el registro de costes también se puede especificar un sitio para la fórmula de cálculo específica del sitio. Como alternativa, puede dejar en blanco el campo **Sitio** para indicar que la fórmula de cálculo es una fórmula para toda la empresa. De manera opcional, el registro de costes puede constar de un artículo o un grupo de artículos especificados cuando la fórmula de cálculo se ha marcado como fórmula por artículo. 

Los registros de costes actualmente activos para las fórmulas de cálculo de costes indirectos se usan para estimar los costes del pedido de producción. También se usan para calcular los costes reales relacionados con el consumo real de tiempo y materiales. Los registros de costes pendientes se usan en los cálculos de lista de materiales (L. MAT.) para una fecha futura. 

Dos directivas de bloqueo para una versión de gestión de costes determinan si los costes pendientes se pueden mantener y si el coste pendiente se puede iniciar. Use estas directivas para permitir el mantenimiento de datos y, a continuación, bloquearlo para los datos de costes de una versión de gestión de costes. 

Después de definir el formato de hoja de gestión de costes y los cálculos para los costes indirectos, deberá realizar un paso individual para validar y guardar la información. La hoja de gestión de costes representa un formato para toda la empresa que muestra de manera coherente la información sobre costes de los bienes vendidos. 

La hoja de gestión de costes se muestra como parte de la página **Calcular coste del artículo**. La hoja de gestión de costes se puede mostrar para el registro de costes calculados de un artículo fabricado en la página **Precio de artículo** o, para un registro de cálculo específico de un pedido, en la página **Resultados del cálculo de L. MAT.**. También se puede mostrar como parte de la página **Cálculo de precio** para un pedido de producción.






