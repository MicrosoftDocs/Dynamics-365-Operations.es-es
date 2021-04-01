---
title: Método de asignación de coste total
description: Este tema proporciona directrices para usar la asignación de coste total (TCA). TCA es un método para calcular el coste entre el producto de fórmula principal para un pedido de lote y los coproductos que se definen para la fórmula.
author: AndersGirke
manager: tfehr
ms.date: 04/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, PmfFormulaCoBy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 83852
ms.assetid: 7c14c3e5-9476-4a79-a210-e77fc91cc7fc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c37463bf2f31a900e6f5a8e106b9d58b1fdedcaa
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235541"
---
# <a name="total-cost-allocation-method"></a>Método de asignación de coste total

[!include [banner](../includes/banner.md)]

La asignación de coste total (TCA) es un método para calcular el coste entre el producto de fórmula principal para un pedido de lote y los coproductos que se definen para la fórmula. Este método es dinámico. Calcula el coste como media ponderada entre las cantidades que se notifican como terminadas del producto de fórmula y los coproductos. Cuando se usa el TCA, no es necesario revisar las asignaciones de costes para cada pedido de lote. Si no se usa el TCA, el cálculo de la fórmula usa la funcionalidad existente.

## <a name="using-tca-for-coproducts"></a>Usar el TCA para coproductos
Estas son algunas de las directrices para usar TCA para coproductos:

-   Si establece el control deslizante **Asignación de coste total** en **Sí** para una versión de fórmula, los coproductos deben tener un precio de coste que sea superiora 0 (cero). El valor se puede recuperar de la versión de coste activo para el mismo sitio o para el primer sitio para una fórmula que no sea específica de sitio. Esta condición se valida cuando se aprueba la fórmula.

    -   No es necesario especificar manualmente los porcentajes de asignación de costes para coproductos. En su lugar, el sistema crea automáticamente el porcentaje de asignación de costes como la media de los precios de coste activos de coproductos. 
    -   No es necesario especificar el coste estándar para artículos de coste no estándar que son coproductos. Existen dos tipos de versiones de gestión de costes en el sistema: coste estándar y coste planificado 
    -   Si un artículo no es evaluado por el método de valoración de costes estándar, recomendamos que use un precio de coste activo de la versión de coste planificado. Este precio se usa para la estimación de costes, por ejemplo, el cálculo de L MAT., la estimación de costes de producción, y el precio de reserva del proceso de la evaluación de inventario. 

-   Si establece el control deslizante **Asignación de coste total** en **Sí** para la versión de la fórmula y las siguientes condiciones son verdaderas, el método de asignación de costes es **TCA** y el porcentaje de la asignación de costes no cambia:
    -   Ha agregado coproductos.
    -   Ha usado un método diferente de asignación de costes para los coproductos.
-   Si establece el control deslizante **Asignación de coste total** en **No** para la versión de la fórmula y las siguientes condiciones son verdaderas, el método de asignación de costes se cambia a **Manual** y el porcentaje de la asignación de costes no cambia:
    -   Ha agregado coproductos.
    -   El porcentaje de la asignación de costes es superior a 0 (cero).
-   Para poder realizar correctamente un cálculo de fórmula, debe estimar los porcentajes de la asignación de costes. Puede completar este paso manualmente o mediante la opción **Coste estimado** en la página **Coproductos**. **Nota:** La opción **Coste estimado** solo está disponible cuando el control deslizante **Asignación de coste total** se establece en **Sí** para la versión de la fórmula. Puede ver la asignación esperada si las cantidades de pedido por lotes se notifican como cantidades de conciliación finalizadas que aparecen en la fórmula.
-   Cuando un pedido por lotes se crea manualmente o un pedido planificado por lotes se pone en firme, el valor del control deslizante **Asignación de coste total** para la versión de la fórmula se copia en el pedido por lotes. Sin embargo, puede cambiar esta configuración en el pedido de lote. Si el control deslizante **Asignación de coste total** se establece en **No** para la versión de la fórmula y después se cambia a **Sí** para el pedido de lote, el método de la asignación de costes para cada línea que se establece en **Manual** cambia a **TCA**. Una asignación de costes de **Ninguno** permanece sin cambios. Si el control deslizante **Asignación de coste total** se establece en **Sí** para la versión de la fórmula y después se cambia a **No** para el pedido de lote, el método de la asignación de costes para cada coproducto del tipo **Producción** cambia a **Manual**. Cualquier porcentaje estimado de la asignación de costes permanece sin cambios.
-   La página **Asignación de costes de coproductos** muestra el porcentaje de asignación de costes calculado. Puede abrir esta página desde la página **Pedido de lote**. Esta información es útil cuando los productos y las cantidades que se notifican varían de las cantidades programadas o iniciadas en el pedido de lote. Cuando se completa el coste, estas nuevas asignaciones de porcentaje de TCA se muestran en la página **Asignación de costes de coproductos**.

## <a name="calculating-the-burden-for-byproducts"></a>Cálculo de la carga para productos derivados
El campo **Asignación de costes de productos derivados** de la página **Coproductos** es un campo de enumerador que se usa solo para los productos derivados. Para coproductos, el valor de este campo siempre es **Ninguno**. Para las líneas de productos derivados, este campo determina cómo se agrega el importe de coste para la línea del producto derivado al coste total de la producción. Están disponibles las siguientes opciones:

-   **Ninguno**: No se agrega ningún importe al coste total de la producción para esta línea del producto derivado.
-   **Porcentaje**: El importe del coste se calcula como porcentaje del coste total de las materias primas que se consumen en la producción. Porcentaje usado para el cálculo especificado en el campo.
-   **Por serie**: El importe del coste se calcula como importe por tamaño de lote estándar del pedido de producción. Este importe es independiente de la cantidad notificada en la producción. Importe usado para el cálculo especificado en el campo.
-   **Por cantidad**: El importe del coste se calcula como importe por cantidad notificada del producto de fórmula en la producción. Importe usado para el cálculo especificado en el campo.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]