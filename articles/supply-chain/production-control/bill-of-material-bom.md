---
title: Listas de materiales y fórmulas
description: Este tema proporciona información acerca de las listas de materiales y las fórmulas, que son una parte fundamental de la definición de productos y variantes de producto.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, EcoResProductProcessManufacturingWorkspace, ProdBOM, ProdJournalTransBOM, ProdBOMCurrent, PmfBOMDesignerEditCoBy, ProdJournalPickingListLineSummary, ProdBOMOverview, PmfCoReqPlanning, EcoResProductProdTypeFormulaNoActiveFormulaFormPart, EcoResItemsMissingActiveRouteVersionFormPart, EcoResItemsProdTypeBOMExpiringBOMFormPart, BOMDesignerBOMVersion, BOMExpandPurch, BOMChangeLine, BOMExpandSales, EcoResItemsProdTypeBOMExpiringRouteFormPart, EngChgEcmBomDesigner, EngChgEcmProductBOMItemIdLookup, EngChgEcmProductBOMConsistOf, EngChgEcmBOMCopyDialog, EngChgEcmBomDesignerEditBom, BOMDesignerFilterDialog, BOMDesignerFilterDialog, BOMPartOf, BOMSetupReportFinish, EcoResItemsMissingActiveBOMVersionFormPart, BOMIdLookup, EcoResProductProdTypeFormulaNoActiveRouteFormPart, BOMExpandPurchRFQ, EngChgCaseRouteTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19331
ms.assetid: c19b437a-2de2-4728-9477-2bcb0c2b1f5e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c9d261d5a458732f807c32042a0b3ed975104c8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246438"
---
# <a name="bills-of-materials-and-formulas"></a>Listas de materiales y fórmulas

[!include [banner](../includes/banner.md)]

Este tema proporciona información acerca de las listas de materiales y las fórmulas, que son una parte fundamental de la definición de productos y variantes de producto. Las listas de materiales y las fórmulas especifican los materiales o componentes necesarios para un producto específico. Las fórmulas también especifican los coproductos o productos derivados que se reciben en un contexto específico de la producción. 

<a name="bills-of-materials"></a>Listas de materiales
------------------

Una lista de materiales (L. MAT) define los componentes necesarios para producir un producto. Los componentes pueden ser materias primas, productos semiterminados o ingredientes. En algunos casos, se puede hacer referencia a los servicios en una L. MAT. Sin embargo, las L. MAT describen normalmente los *recursos materiales* que son necesarios.  

Cuando se combina con una ruta o un flujo de producción que describe las operaciones y los recursos necesarios para crear un producto, la L. MAT. forma la base para calcular el coste estimado del producto.  

Una lista de materiales es una entidad individual que se describe con la siguiente información:

-   Id. de BOM
-   Nombre de L. MAT
-   Las líneas de L. MAT que describen los componentes y los ingredientes
-   Las versiones de L. MAT, que definen el producto y el período para el que se puede usar la L. MAT.

Una sola L. MAT describe un nivel único que se identifica con un id. único. Los componentes pueden tener sus propias L. MAT a las que hacen referencia las versiones de L. MAT. Puede mostrar y editar la jerarquía completa de las L. MAT para un producto específico en el diseñador de L. MAT.

### <a name="formulas-co-products-and-by-products"></a>Fórmulas, coproductos y productos derivados

Una fórmula es un subtipo de L. MAT. que se suele usar para la fabricación en procesos. Además de los componentes y los ingredientes, una fórmula describe coproductos y productos derivados. En la versión real, la definición de coproductos y productos derivados para la fórmula requiere la versión de fórmula. Una fórmula se define normalmente para un producto terminado específico (una fórmula o un artículo de planificación) definida en la versión de fórmula.

### <a name="boms-in-the-product-lifecycle"></a>L. MAT en el ciclo de vida del producto

En el ciclo de vida del producto, se pueden crear muchos tipos de L. MAT por varios motivos:

-   **Bocetos/L. MAT de borrador**: este L. MAT proporciona una estimación de borrador de los materiales necesarios en una primera fase de diseño y le ayuda a realizar un cálculo aproximado del coste y de los atributos del producto estimados. Esta L. MAT no se suele usar en la planificación de recursos empresariales (ERP).
-   **L. MAT de ingeniería**: esta L. MAT se suele usar al diseñar los productos que se basan en carteras de productos existentes. Las L. MAT de ingeniería se estructuran para simplificar el proceso de diseño y agrupar los productos complejos en módulos de ingeniería. Para los productos simples, puede que sea posible diseñar L. MAT para el proceso de producción real. Sin embargo, para otros productos, la L. MAT de ingeniería se debe convertir en una L. MAT de producción real. Las L. MAT de ingeniería se suelen representar con fantasmas en la jerarquía de L. MAT. Aunque las L. MAT de ingeniería se pueden usar para la planificación y ejecución de las operaciones de fabricación, este enfoque puede dar lugar a ineficacias, especialmente en operaciones repetitivas donde se crean muchos pedidos.
-   **L. MAT. de planificación**: esta L. MAT se usa para realizar la planificación de requisitos de materiales. La demanda de componentes e ingredientes se calcula en función de la demanda de los productos terminados. Como L. MAT de gestión de costes, las L. MAT de planificación pueden representar una combinación específica de material que se usa en un período.
-   **L. MAT de producción**: esta es la L. MAT real que se usa para una producción concreta. Una L. MAT de producción debe tener en cuenta los recursos reales que se usan para producir el producto. Cuando se crea un pedido de producción, un pedido de lote o un kanban, los múltiples niveles de L. MAT que están representados por fantasmas se contraen en un nivel y se distribuyen por las operaciones para el pedido.
-   **L. MAT de gestión de costes**: esta L. MAT se usa para calcular el coste estimado de un producto. Por ejemplo, puede usar una L. MAT de gestión de costes cuando se use el coste estándar o se calcule el coste planificado estimado de un producto determinado. Las L. MAT de gestión de costes pueden hacer referencia a una combinación específica de materiales y recursos que se espera que se usará. Por tanto, puede usar la L. MAT de gestión de costes para crear un coste estimado representativo para un período y ayudar a evitar las desviaciones con el tiempo.

Los tipos de listas de materiales que se usan realmente en una implementación dependen de la implementación, además de los requisitos y escenarios empresariales. En implementaciones simples, una L. MAT de planificación, una L. MAT de producción y una L. MAT de gestión de costes se pueden modelar como una L. MAT. En los entornos con cambios frecuentes de ingeniería y varias rutas alternativas, probablemente se requerirá un conjunto mayor de tipos de L. MAT.

### <a name="approval-of-boms-and-formulas"></a>Aprobación de L. MAT y fórmulas

Cada L. MAT y fórmulas se pueden aprobar o desaprobar por separado. Normalmente, la aprobación de una L. MAT o fórmulas se produce cuando se aprueba la primera versión de L. MAT pertinente. Sin embargo, en algunos escenarios empresariales, estas aprobaciones pueden ser diferentes fases del proceso y pueden implicar a distintos propietarios del proceso.  

Tenga en cuenta que, si se desaprueba una L. MAT, también se desaprobarán todas las versiones de L. MAT relacionadas.

## <a name="bom-and-formula-versions"></a>Versiones de L. MAT y fórmulas
Para relacionar una L. MAT o una fórmula específica con una variante del producto que se puede producir, debe crear una versión de L. MAT o fórmulas. La validez de las versiones de L. MAT y fórmulas se pueden restringir por período, cantidad, sitio, dimensiones de producto específicas y otros criterios. Las versiones de fórmulas tienen atributos importantes adicionales, como las definiciones de producción, coproductos y productos derivados, y las instrucciones de distribución de costes para la fórmula.

### <a name="approval-of-bom-and-formula-versions"></a>Aprobación de las versiones de L. MAT y fórmulas

Para que una versión de L. MAT se pueda utilizar en el proceso de planificación o fabricación, debe estar aprobada. Cuando se aprueba una versión de L. MAT, también se puede aprobar la L. MAT relacionada, en función de la selección del usuario y de los derechos de autenticación. Tenga en cuenta que una versión de L. MAT solo se puede aprobar si se aprueba la propia L. MAT relacionada.

### <a name="activation-of-the-default-bom-or-formula-version"></a>Activación de la versión de L. MAT. o fórmula predeterminada

Para establecer una L. MAT o una fórmula específica como la versión de L. MAT o de fórmula predeterminada que se usará por la planificación maestra o que se usará para crear pedidos de producción, debe activar la versión. Cuando se activa una versión, se comprueba la unicidad de la versión para las restricciones dadas (por ejemplo, el período, el sitio o la cantidad). Recibe un mensaje de error si la versión que está intentando activar entra en conflictos con una versión que ya está activa. A continuación, debe desactivar la versión en conflicto o modificar las restricciones de la versión (normalmente el período) para impedir una activación ambigua.

### <a name="product-change-with-case-management"></a>Cambio de producto con administración de casos

El caso de cambio de producto para su aprobación y activación de L. MAT nuevas o cambiadas y versiones de L. MAT proporcionan una manera sencilla de considerar una descripción de las restricciones de la versión de L. MAT. También puede aprobar y activar todas las L. MAT y las fórmulas relacionadas con un cambio específico para una fecha de activación.

### <a name="alternative-bom-versions"></a>Versiones de L. MAT alternativas

A veces, la versión de L. MAT o de fórmula no se debe usar en previsiones, ventas o un producto principal. En este caso, puede seleccionar una L. MAT aprobada específica como parte del requisito (línea de previsión, línea de ventas o línea de L. MAT) si existe una versión de L. MAT o fórmula aprobada para la L. MAT o fórmula alternativas.  

Cuando se crean pedidos planificados, pedidos de producción o kanbans, el planificador o supervisor de planta puede usar cualquier versión de L. MAT aprobada que sea válida en la fecha de producción planificada solicitada para planear o producir un producto específico. La versión de L. MAT que se usa no tiene que estar activada como la versión de L. MAT predeterminada.

## <a name="bom-and-formula-lines"></a>Líneas de L. MAT y fórmulas
Se crea una línea de L. MAT para cada material, servicio o ingrediente. La línea define el consumo previsto de la variante del producto especificada y también define los distintos atributos relacionados con el consumo previsto.  

Las líneas de L. MAT pueden tener los siguientes tipos de líneas: **Artículo**, **Fantasma**, **Suministro asegurado**, **Proveedor**.

### <a name="item"></a>Artículo

Seleccione el tipo de línea **Artículo** para los materiales o servicios que se consumen directamente y que no requieren más expansión o suministro asegurado.

### <a name="phantom"></a>Fantasma

Seleccione el tipo de línea **Fantasma** cuando desee expandir los artículos de L. MAT de nivel inferior incluidos en la línea de la lista de materiales. En la programación maestra, en el cálculo de coste planificado, o en la estimación de un pedido de producción que use líneas de L. MAT del tipo **Fantasma**, la línea de L. MAT principal que hace referencia a una variante del producto que tiene una L. MAT fantasma se reemplaza por los artículos de componentes que se muestran como líneas de L. MAT en dicha L. MAT por la versión de L. MAT activa de dicha variante del producto. Si la variante del producto tiene una ruta activa aplicable, las operaciones de dicha ruta se combinan en la ruta principal.  

Observe que los fantasmas se suelen usar para simplificar el proceso de ingeniería. El uso extensivo de las L. MAT fantasmas en muchos niveles tiene un efecto en el rendimiento, especialmente en escenarios de fabricación altamente repetitivos. Para mejorar el rendimiento, debe evitar jerarquías profundas de fantasmas. En su lugar, use las rutas y las L. MAT. de producción previamente expandidas.

### <a name="pegged-supply"></a>Suministro asegurado

Seleccione el tipo de línea **Suministro asegurado** cuando desee crear una subproducción, un kanban de evento de línea de L. MAT o un pedido de compra directa para cualquier variante del producto a la que la línea de L. MAT haga referencia. Se crea la subproducción, el kanban de evento o el pedido de compra cuando estima el pedido de producción. Las cantidades necesarias de artículos se reservarán automáticamente para el pedido de producción de consumo.

### <a name="vendor"></a>Proveedor

Seleccione el tipo de línea **Proveedor** si el proceso de producción usa un subcontratista y desea que se cree una subproducción o pedido de compra automáticamente para el subcontratista.  

**Nota sobre las operaciones subcontratadas en una L. MAT**: el servicio o trabajo que se realiza por el subcontratista se debe crear como artículo de servicio del que se realiza un seguimiento en el inventario. Debe vincular el artículo de servicio al artículo principal como línea de L. MAT. La ruta deberá incluir la operación asignada al recurso de operaciones del subcontratista.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]