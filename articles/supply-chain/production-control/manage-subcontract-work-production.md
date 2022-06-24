---
title: Gestionar el trabajo de subcontratación en la producción
description: Este artículo explica cómo se administran las operaciones subcontratadas en Dynamics 365 Supply Chain Management. Es decir, explica cómo las operaciones de producción asignadas a un recurso son administradas por un proveedor.
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup, ProdBOMVendorListPagePreviewPane, ProdBOMVendor
audience: Application User
ms.reviewer: kamaybac
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a0021d409f9f4a9b36effbd80a99766812572d5b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863806"
---
# <a name="manage-subcontracting-work-in-production"></a>Gestionar el trabajo de subcontratación en la producción

[!include [banner](../includes/banner.md)]

Este artículo explica cómo se administran las operaciones subcontratadas en Dynamics 365 Supply Chain Management. Es decir, explica cómo las operaciones de producción asignadas a un recurso son administradas por un proveedor.

En [procesos de producción](production-process-overview.md), el trabajo se puede realizar por los recursos propiedad o administrados por los proveedores. Normalmente, se usan los recursos del proveedor para compensar el exceso de la demanda periódico que supera la capacidad disponible de los recursos propios de una empresa. El proveedor también puede proporcionar [capacidades de recursos](resource-capabilities.md) específicas o recursos a un precio más bajo.  

En función de los recursos del proveedor que se usan en un proceso de producción, una [ruta](routes-operations.md) a menudo tiene requisitos logísticos adicionales, ya que el material y los productos semiterminados se deben transportar primero al sitio de proveedor. A continuación, se debe transportar el resultado de la operación subcontratada a la ubicación que se asigna para la siguiente operación o a un almacén de productos terminados.  

Si se emplean operaciones o actividades subcontratadas, estas afectan a todas las etapas de operaciones, desde la definición de las operaciones necesarias en la producción, la gestión de costes, la previsión, la planificación, y la programación, hasta la administración de la logística para el material, los productos semiterminados, y los productos terminados. Finalmente, estos recursos requieren sus propios procesos de contabilidad y control de costes.  

Para los recursos internos, se asigna normalmente un índice de coste fijo para un período. Por el contrario, el coste de los recursos subcontratados se basa en el precio de adquisición del servicio relacionado. El servicio se define como otro producto y se usa para controlar los procesos de adquisición y compra de una operación subcontratada determinada.  

Actualmente, no hay un concepto explícito de productos semiterminados en Supply Chain Management. En un pedido de producción que requiera más de una operación para transformar las materias primas en un producto terminado, el producto terminado se registra en el inventario solo en la última operación. Los productos semiterminados producidos en las operaciones anteriores se contabilizan en trabajo en curso, pero no se registran ni se siguen en el inventario. Aunque puede dividir las rutas y las listas de materiales en varias unidades más pequeñas, este planteamiento aumenta el número de productos, listas de materiales, y rutas que se deben administrar.  

Existen dos métodos para modelar el trabajo de subcontratación para las operaciones de producción. Estos métodos se diferencian en el modo en que el proceso de subcontratación se puede modelar, en la manera en que los productos semiterminados están representados en el proceso y en la forma que se administra el control de costes.

-   Subcontratación de operaciones de ruta en pedidos de producción o pedidos de lote
    -   El producto de servicio debe ser un producto mantenido en existencias y debe formar parte de la lista de materiales.
    -   Este método admite el orden de entrada (FIFO) o el coste estándar.
    -   Los productos semiterminados se representan por el producto de servicio en el proceso.
    -   El control de costes asigna los costes que están asociados con el trabajo subcontratado a los costes de materiales.
-   Subcontratación de actividades de flujo de producción en un flujo de producción lean
    -   El servicio es un producto de servicio no mantenido en existencias y no es parte de la lista de materiales.
    -   Este método usa acuerdos de compra como acuerdos de servicio.
    -   Este método usa contabilización previa de los costes.
    -   Este método permite compras agregadas y asincrónicas. (El flujo de material es independiente del proceso de compra.)
    -   El control de costes asigna el trabajo subcontratado en su propio bloque del análisis de costes.

## <a name="subcontracting-of-route-operations"></a>Subcontratación de operaciones de ruta
Para usar la subcontratación de operaciones de ruta para los pedidos de producción o de lote, el producto de servicio que se utiliza para las compras de servicio se debe definir como producto del tipo **Servicio**. Además, debe tener un grupo de modelo de artículo con la opción **Producto mantenido en existencias** en **Directiva de inventario** definida en **Sí**. Esta opción define si un producto se contabiliza como inventario en la recepción del producto (**Producto mantenido en existencias** = **Sí**) o si el producto se contabiliza en una cuenta de pérdidas y ganancias (**Producto mantenido en existencias** = **No**). Aunque este comportamiento podría parecer contradictorio, se basa en el hecho de que solo los productos que tengan esta directiva crearán las transacciones de inventario que se pueden usar en el control de costes para calcular el coste planificado y determinar el coste real cuando se termina un pedido de producción.  

Para ser considerado en la planificación y el cálculo de costes, el servicio se debe agregar a la lista de materiales. La línea de L. MAT debe ser del tipo **Proveedor** y se debe asignar a la operación de ruta a la que está asignado el servicio. Esta operación de ruta debe tener un recurso de gestión de costes y un requisito de recurso que hagan referencia a un recurso del tipo **Proveedor** que conecte la operación y el servicio relacionado con la cuenta de proveedor correspondiente.  

Si se usa esta configuración, se crea un pedido de compra para el producto de servicio correspondiente, en función de la estimación de un pedido de producción. El pedido de compra del servicio se utiliza como base para las operaciones subcontratadas. El trabajo subcontratado se puede gestionar a través de la página de lista **Trabajo subcontratado** en el control de producción. El trabajo subcontratado se usa para enviar la materia prima y finalmente un producto semiterminado al proveedor en la preparación de la operación. También se usa para recibir el producto resultante de la operación subcontratada al recibir los artículos, empleándose el producto de servicio para identificar la llegada del producto semiterminado. Cuando se recibe la línea de pedido de compra, la operación de producción se actualiza a completada.  

Un pedido de producción puede tener muchas operaciones, y cada operación se puede asignar a un proveedor diferente. Por lo tanto, un pedido de producción de principio a fin puede activar varios pedidos de compra.

## <a name="subcontracting-of-production-flow-activities"></a>Subcontratación de actividades de flujo de producción
La solución [lean manufacturing](lean-manufacturing-overview.md) modela el trabajo de subcontratación como un servicio relacionado con una actividad de un [flujo de producción](tasks/create-production-flow-version.md) (artículo de la Guía de tareas). Por tanto, a este tipo de subcontratación se lo denomina también [subcontratación basada en actividades.](activity-based-subcontracting.md) Se han introducido un tipo especial de grupo de costes que se denomina **Subcontratación directa** y los servicios de subcontratación ya no son parte de una lista de materiales de productos terminados. Cuando usa la lean manufacturing, todas las actividades se definen por kanbans que pueden estar relacionadas con una o varias actividades del flujo de producción. Hasta ahora, esa explicación es similar a la de los pedidos de producción. Sin embargo, mientras que los pedidos de producción deben finalizar siempre con un producto terminado, puede crear kanbans para suministrar un producto semiterminado. No tiene que especificar un nuevo producto y nivel de lista de materiales.  

Dado que las reglas kanban pueden ser muy dinámicas, se pueden modelar distintas variantes de suministro para el mismo producto de un flujo de producción. Cuando utilice la subcontratación lean, el flujo de material y el flujo financiero se separarán estrictamente. Todo el flujo de material se representa con actividades de kanban. Los pedidos de compra para los productos de servicio y los registros de recepción de dichos servicios se pueden automatizar, en función del estado de los trabajos kanban, en el flujo de producción. Los trabajos kanban se pueden iniciar y completar incluso antes de que se creen los pedidos de compra. Los documentos de subcontratación (pedido de compra y recepción de compra de servicio) se pueden agregar por período y servicio. Por lo tanto, se puede mantener un número reducido de documentos y líneas de compra, incluso en las operaciones muy repetitivas en las que los proveedores proporcionen servicios subcontratados en un flujo unitario.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Modelación de subcontratación en un flujo de producción

En un [flujo de producción lean](lean-manufacturing-modeling-lean-organization.md), una actividad de proceso se puede definir como subcontratada cuando se asigne a una celda de trabajo (grupo de recursos) que tenga un solo recurso de proveedor. Cuando se subcontrata una celda de trabajo, las actividades de proceso relacionadas deben estar vinculadas a una línea del acuerdo de compra activa que contenga el artículo de servicio y el precio del servicio. El acuerdo de servicio de la actividad también define el coeficiente de cálculo entre la cantidad de producto del trabajo kanban y la cantidad del servicio resultante. Puede seleccionar si la cantidad de servicio se calcula según el número de trabajos, la cantidad de producto que se notifica en los trabajos o la cantidad total de producto (esta cantidad total incluye productos dados de baja).  

Las actividades de transferencia también se pueden definir como subcontratadas. Esta definición aparece implícitamente cuando selecciona la parte responsable del envío en la actividad de transferencia. Al seleccionar **Expedidor** o **Destinatario**, si el almacén de origen o destino es un almacén administrado por el proveedor, la actividad se considera subcontratada. Al seleccionar **Transportista**, la actividad está siempre subcontratada. Al igual que las actividades de proceso subcontratadas, una actividad de transferencia subcontratada se debe conectar a un acuerdo de servicio antes de que el flujo de producción se active.

### <a name="backflush-costing"></a>Contabilización previa de los costes

La contabilidad de costes del trabajo subcontratado está completamente integrada en la gestión de costes de la solución de lean manufacturing (contabilización previa de los costes). Cuando se registra un recepción de pedido de compra del servicio o cuando se realiza la facturación, el coste del servicio se asigna al flujo de producción. Para la contabilización previa de los costes, la desviación de servicios subcontratados se calcula compensando el bloque de subcontratación del coste estándar de los productos recibidos con las cantidades del servicio reales recibidas y facturadas.

## <a name="material-supply-for-subcontracted-operations"></a>Suministro material para las operaciones subcontratadas
Los productos semiterminados y demás materiales relacionados se deben transferir a la ubicación donde el trabajo se realiza físicamente. Si utiliza operaciones y actividades subcontratadas, esta transferencia con frecuencia está relacionada con el transporte adicional a un sitio operado por el proveedor. Asignando el material de la lista de materiales a la operación subcontratada, declara que el material se debe almacenar provisionalmente en la ubicación de entrada del grupo de recursos del recurso asignado. La planificación maestra o el reabastecimiento lean suministra material a dicha ubicación.  

Para modelar el inventario que se ubica en un sitio del proveedor, lo mejor es definir un almacén administrado por el proveedor. Es fácil definir un almacén administrado por el proveedor creando un nuevo almacén y asignándole la cuenta de proveedor. Para documentar que el material se debe transferir al proveedor antes de que una operación pueda realizarse, debe asignar el almacén administrado por el proveedor al almacén de entrada del grupo de recursos que posee el recurso.  

Para reabastecer el material en este almacén, puede usar varias estrategias:

-   Transferir pedidos
-   Diarios de transferencias
-   Kanban de retirada
-   Compra directa para la ubicación del proveedor

Los productos semiterminados son la excepción a esta regla. Para transferir productos semiterminados, solo tiene estas opciones:

-   En pedidos de producción y lote, los productos semiterminados solo se pueden transferir lógicamente mediante el diario de lista de selección de la página de lista **Trabajo subcontratado**. Este diario creará un documento de nota de entrega que se puede utilizar para transferir la materia prima semiterminada al proveedor.
-   En las operaciones subcontratadas en flujos de producción, la transferencia de productos semiterminados se documenta al recibir los kanban de retirada o de producción en la ubicación del proveedor. Para modelar una actividad de transferencia explícita, puede finalizar un kanban de producción con una actividad de transferencia adicional.

**Nota:** una ruta de producción para un único pedido de producción no puede atravesar varios sitios. Esta regla también se aplica al trabajo subcontratado. Por lo tanto, los almacenes que representan las ubicaciones de materiales administradas por el proveedor se deben definir en el mismo sitio que los recursos internos que se usan en la ruta. Aunque los flujos de producción pueden atravesar sitios, no pueden transportar los productos semiterminados de un sitio a otro, ya que dicha operación implica un cambio de contexto del coste.  

Normalmente, el almacén y la ubicación de salida de un grupo de recursos subcontratado se asignan directamente al almacén y la ubicación del paso siguiente de la operación en la ruta o el flujo de producción. Esta configuración ayuda a reducir la cantidad de informes de trabajo realizados o el número de operaciones de transferencia adicionales que se deben modelar.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]