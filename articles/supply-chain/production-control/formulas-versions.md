---
title: "Fórmulas y versiones de fórmula"
description: "Este tema proporciona información sobre fórmulas y versiones de fórmula. Una fórmula define el material, los ingredientes y los resultados de un proceso determinado en la fabricación de procesos. Las fórmulas se utilizan para planificar y generar productos en la fabricación de procesos."
author: cvocph
manager: AnnBe
ms.date: 09/12/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4475695b1a00213ab7e3b5060fd38cc71883d2bd
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="formulas-and-formula-versions"></a>Fórmulas y versiones de fórmula

[!include[banner](../includes/banner.md)]

Una fórmula define el material, los ingredientes y los resultados de un proceso determinado en la fabricación de procesos. Junto con la ruta correspondiente, la fórmula define la totalidad del proceso en la fabricación de procesos. Las fórmulas se utilizan para planificar y generar productos en la fabricación de procesos.

Una fórmula consta de los ingredientes y las cantidades necesarias para producir una cantidad específica de un producto de fórmula. En función de la tarea que realice, puede tener acceso a la funcionalidad de la fórmula desde el inventario y la administración de almacenes o la administración de la información del producto.

## <a name="formulas-and-formula-lines"></a>Fórmulas y líneas de fórmula
Una fórmula consta de una o más líneas de fórmula que identifican los ingredientes o productos que integran dicha fórmula. Una línea de fórmula puede incluir los productos de la lista de materiales (BOM), los productos de peso capturado, los productos de compra, los coproductos u otros productos derivados. Puesto que algunos artículos se usan en diversos productos, un artículo puede aparecer en más de una fórmula.

Un ejemplo de una fórmula es la fórmula que se usa en una receta de galletas de chocolate. Los ingredientes de esta fórmula usan varias líneas como, por ejemplo, harina, azúcar, huevos, mantequilla y trozos de chocolate. La fórmula de las galletas de chocolate contiene los ingredientes que normalmente se usan en otras fórmulas. A medida que se producen las galletas de chocolate, es posible que haya sobras como migas o algunas galletas que se hayan hecho demasiado o hayan quedado crudas. Estos artículos se pueden configurar como los coproductos o productos derivados, según las operaciones de producción.

Al crear una línea de fórmula, puede usar el tipo de línea para indicar de qué manera debe gestionar el sistema esa línea cuando realice planificaciones maestras o pedidos en lote. Cada tipo de línea proporciona un resultado diferente. En la siguiente tabla se describen los tipos de línea que se pueden seleccionar. 

| Tipo de línea     | Descripción  |
|---------------|--------------|
| Artículo          | Seleccione **Artículo** cuando este sea materia prima o un artículo parcialmente terminado que haya sido seleccionado del inventario, o bien si el artículo es un servicio. |
| Fantasma       | Seleccione **Fantasma** cuando desee expandir los productos de fórmula de nivel inferior que estén incluidos en las líneas de fórmula. Al realizar la estimación del pedido de lote y expandir los productos de fórmula, los artículos de componentes se enumeran como líneas de fórmula en el pedido de lote. Además, las rutas correspondientes se agregan a la ruta de producción. Los productos de fórmula se expanden con la configuración actual. Cuando se usa el tipo de línea **Fantasma**, puede gestionar la producción y las configuraciones de medida que se producen en distintos niveles de la fórmula. Si selecciona **Fantasma** para un producto de la ficha desplegable **Ingeniero** de la página **Detalles del producto emitido** y luego usa este producto en una fórmula, el tipo de línea de la línea de fórmula cambia a **Fantasma**. No puede seleccionar **Fantasma** en un artículo con peso capturado o en artículos donde el tipo de producción sea **Coproducto**, **Producto derivado** o **Artículo de planificación**. |
| Suministro asegurado | Seleccione **Suministro asegurado** para crear un pedido de lote, un pedido de producción, un kanban, un pedido de transferencia o un pedido de compra del ingrediente que contiene la línea de fórmula. El orden relacionado se determina en función de la configuración de pedido predeterminada y el tipo de producción del ingrediente, y se crea cuando se estima el pedido de lote. Las cantidades necesarias de ingredientes se reservarán automáticamente para el pedido de lote. |
| Proveedor        | Seleccione **Proveedor** si el proceso de producción usa un subcontratista y si desea crear una subproducción o pedido de compra para el subcontratista. El servicio o trabajo que realice el subcontratista deberá crearse mediante un producto de fórmula o artículo de servicio. Puede vincular el artículo al artículo principal como la línea de fórmula. La ruta deberá incluir la operación asignada al recurso de operaciones del subcontratista. Esta operación se vincula a la línea de fórmula mediante el campo **Número de operación** . |

## <a name="formula-versions"></a>Versiones de fórmula
Cuando se crea una nueva fórmula, debe crear una versión de esa fórmula antes de agregar artículos a las líneas de la fórmula con sus características específicas. Cada fórmula debe tener como mínimo una versión. El botón **Aprobado** de una versión de fórmula estará disponible tras guardar el registro de la versión. Cada registro de la versión de fórmula está asociado con uno o varios coproductos y productos derivados que se pueden generar a medida que cree el producto terminado. Muchos productos se pueden crear a partir de los mismos ingredientes en distintos tamaños de lote, en múltiplos o mediante diferentes rendimientos. Puede crear tantas versiones de una fórmula como necesite.

Para gestionar varias versiones activas de la fórmula, puede usar los intervalos de fechas de vigencia o los campos de cantidad "desde". Solo pueden existir versiones múltiples de la fórmula activa si el intervalo de fechas y la cantidad "desde" no se solapan.

A diferencia de las listas de materiales (donde una lista de materiales a menudo se asocia a varias versiones de la misma), normalmente solo existe una versión de la fórmula por cada fórmula. Recuerde que solo puede activar una versión de fórmula para las dimensiones de cobertura y para la cantidad de un producto determinado. Sin embargo, pueden existir muchas versiones de fórmula por otros motivos y puede seleccionarlas manualmente al crear un pedido de lote.

## <a name="approve-and-activate-formulas-and-formula-versions"></a>Aprobar y activar las fórmulas y las versiones de fórmula
Las fórmulas y las versiones de fórmula se deben aprobar antes de que puedan usarse en la planificación y la producción. Normalmente las fórmulas se activan antes de usarse. Sin embargo, durante la producción puede seleccionar una versión de fórmula aprobada, pero que no esté activa.

Para mantener la fórmula o la versión de la fórmula segura, puede establecer los parámetros **Bloquear edición** y **Bloquear la eliminación de la aprobación** en la página **Parámetros de control de producción**.

Si selecciona **Bloquear edición** y se aprueba la fórmula, no se podrán borrar o editar los campos de las líneas de fórmula. Sin embargo, si quita la aprobación de la fórmula, puede eliminar y modificar las líneas de fórmula. También puede crear nuevas fórmulas y versiones de fórmula.

Si selecciona **Bloquear la eliminación de la aprobación**, no podrá quitar la aprobación de una fórmula o versión de fórmula aprobada. Sin embargo, puede crear nuevas fórmulas y versiones de fórmula y puede quitar la activación de la versión de fórmula.

Puede agregar más niveles de control mediante la funcionalidad de firma electrónica. Cuando un usuario está configurado para solicitar una firma electrónica cuando se apruebe la fórmula, la página **Firma** aparece cuando se activa la fórmula. El usuario debe tener autorización para firmar electrónicamente y el certificado debe ser validado correctamente antes de que el cambio pueda realizarse. Si no se puede autenticar la firma, se deniega la aprobación o supresión de la aprobación y el cambio que inició la aprobación o supresión de la aprobación vuelve a su estado original.

## <a name="use-the-scalable-feature"></a>Usar la característica escalable
La característica escalable solo está disponible si se establecen todos los componentes del artículo en la fórmula en **Consumo variable**. La característica no está disponible si se establecen los componentes del artículo en **Consumo fijo** o **Consumo de pasos**. Al usar la característica escalable, si cambia un ingrediente de la fórmula también ajustará la cantidad de los demás ingredientes seleccionados. También se ajusta el tamaño de la fórmula. Del mismo modo, si cambia el tamaño de la fórmula, la cantidad de todos los ingredientes escalables se cambiará también. Esta característica está diseñada para la creación y mantenimiento de fórmulas. No indica si la cantidad de un ingrediente será aumentada o reducida en un pedido de lote.

## <a name="use-step-consumption"></a>Usar el consumo de pasos
El consumo de pasos elimina la necesidad de especificar una cantidad en la pestaña **Línea de fórmula** de un ingrediente. En su lugar, se configura el consumo de pasos de modo que tenga un valor **Serie inicial** y un valor **Cantidad** . Se selecciona la información del registro del consumo de pasos por serie que cumple con la cantidad especificada en el pedido de lote. El consumo de pasos es útil cuando la tasa de consumo no es lineal con respecto al tamaño del pedido de lote y solo aumenta el requisito cuando se llega a un umbral específico de la cantidad. Para habilitar esta característica en una nueva fórmula, en el grupo **Cálculo del consumo**, cambie la configuración de la fórmula del ingrediente aplicable de **Estándar** a **Paso**. Especifique este método de consumo en la pestaña **Configuración** de la página **Línea de fórmula**.

