---
title: "Gestionar el trabajo de subcontratación en la producción"
description: "Este tema explica cómo las operaciones subcontratadas se administran en Microsoft Dynamics 365 para las operaciones. Es decir explica cómo las operaciones de producción asignadas a un recurso son administradas por un proveedor."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 79430358bebd93fd96f1169d22737d3537dbfc08
ms.lasthandoff: 03/31/2017


---

# <a name="manage-subcontracting-work-in-production"></a>Gestionar el trabajo de subcontratación en la producción

Este tema explica cómo las operaciones subcontratadas se administran en Microsoft Dynamics 365 para las operaciones. Es decir explica cómo las operaciones de producción asignadas a un recurso son administradas por un proveedor.

En [procesos de producción production-process-overview.md] (), el trabajo se puede realizar por los recursos que son propiedad o administrados mediante los proveedores. Normalmente, se usan los recursos del proveedor para nivelar el exceso de la demanda periódica que excede la capacidad disponible de los recursos propios de una empresa. El proveedor también puede proporcionar el poder específico [capacidades de recursos resource-capabilities.md] () o a recursos para un precio más bajo.  

En función de los recursos de proveedor que se usan en un proceso de producción, ruta a [] () routes-operations.md a menudo tiene requisitos logísticos adicionales, ya que el material y los productos semiterminados se deben primero transportar al sitio de proveedor. Al resultado de la operación subcontratada se debe cualquiera transportar a la ubicación que se asigna a la siguiente operación o un almacén del producto terminado.  

Al subcontratar operaciones o actividades se usan, éstos afectan a todas las etapas de operaciones, de la definición de las operaciones necesarias en la producción, la gestión de costes, la previsión, la planificación, y programar, la administración de logística para el material, los productos semiterminados, y los productos terminados. Finalmente, estos recursos requieren sus propios procesos para ver y el control de costes.  

Para los recursos internos, un índice de coste fijo se asigna normalmente un período. Por el contrario, el coste de recursos subcontratados se basa en el precio de adquisición de servicio relacionado. Definen como otro producto, y se usan al servicio para controlar la adquisición y para comprar los procesos para una operación subcontratada dada.  

Actualmente, no hay explícito concepto de productos semiterminados en Microsoft Dynamics 365 para las operaciones. Para un pedido de producción que requiere más de una operación para transformar las materias primas en un producto terminado, el producto terminado se registra al inventario sólo en la última operación. Los productos semiterminados que la producción anterior de las operaciones se considera en el trabajo en curso (WIP), sólo ellas no se envían ni se siguen en el inventario. Aunque puede dividir las rutas y las listas de materiales (BOMs) en unidades más pequeñas mejoras, varios de este planteamiento el número de productos, MAT, y que las rutas que se tratan.  

Existen dos métodos para modelar el trabajo de subcontratación para las operaciones de producción. Estos métodos difieren del modo en que el proceso de subcontratación puede ser de modelos, la manera en que los productos semiterminados están representados en el proceso, y de la configuración del control de costes se gestiona.

-   Subcontratación de operaciones de ruta en pedidos de producción o pedidos de lote
    -   El producto de servicio debe ser un producto se mantiene en existencias, y debe formar parte de L. MAT
    -   Este método admite primero en entrar, primero en salir ((FIFO) o coste estándar.
    -   Los productos semiterminados se representan por el producto de servicio en el proceso.
    -   El control de costes asigna los costes que están asociados al trabajo subcontratado a los costes materiales.
-   Subcontratación de actividades de flujo de producción en un flujo de producción lean
    -   El servicio es un producto no se mantiene en existencias de servicio, y no es parte de L. MAT
    -   Este método usa acuerdos de compra como acuerdos de servicio.
    -   Este método usa contabilización previa de los costes.
    -   Este método permite compras agregada y asincrónica. (El flujo de material es independiente del proceso de compra.)
    -   El control de costes asigna el trabajo subcontratado en su propio bloque del análisis de costes.

## <a name="subcontracting-of-route-operations"></a>Subcontratación de operaciones de ruta
Para usar la subcontratación operaciones de ruta para la producción o los pedidos de lote, el producto de servicio que se utiliza para las compras de servicio se debe definir como producto ** ** servicio del tipo. Además, debe tener un grupo de modelos de artículos con ** producto se mantiene en existencias ** de la opción en el conjunto ** directiva de inventario ** ** Sí **. Esta opción define si un producto se consideran como como inventario en recepción de producto (** producto se mantiene en existencias ** = ** Sí **), o si el producto expensed en una cuenta de pérdidas y ganancias (** producto se mantiene en existencias ** = ** ningún **). Aunque este comportamiento podrían ser contradictorio, tiene en el hecho de que sólo los productos que tengan esta directiva crearán las transacciones de inventario que se pueden usar en control de costes para calcular coste planificado y determinar el coste real cuando se termina un pedido de producción.  

Para ser considerados de planificación y el cálculo de costes, el servicio deben agregar a la L. La línea de MAT debe estar ** proveedor ** del tipo, y se debe asignar a la operación de ruta que asignan al servicio. Esta operación de ruta debe tener una gestión de costes y requisito de recurso que señale a un recurso de proveedor ** ** escriba que conecta la operación y el servicio relacionada con la cuenta de proveedor correspondiente.  

Cuando se usa esta configuración, se crea un pedido de compra para el producto correspondiente de servicio, en función de la valoración de un pedido de producción. El pedido de compra de servicio se utiliza como base para las operaciones subcontratadas. El trabajo subcontratado se puede gestionar a través ** trabajo subcontratado ** de la página de lista de control de producción. El trabajo subcontratado se usa para registrar la materia prima y, finalmente, un producto semiterminado al proveedor a fin de la operación. También se usa para recibir el producto resultante de la operación subcontratada en la recepción de artículos, donde el producto de servicios se usa para identificar la llegada de producto semiterminado. Cuando se recibe la línea de pedido de compra, la operación de producción se actualiza como completado.  

Un pedido de producción puede tener muchas operaciones, y cada operación se puede asignar a un proveedor diferente. Por lo tanto, un pedido de producción de un extremo a otro puede activar varios pedidos de compra.

## <a name="subcontracting-of-production-flow-activities"></a>Subcontratación de actividades de flujo de producción
Lean manufacturing [] () lean-manufacturing-overview.md la solución de modelo el trabajo de subcontratación como servicio relacionada con una actividad a [de flujo de producción (http://ax.help.dynamics.com/en/wiki/create-a-production-flow-version/)] (tema de la guía de la tarea). Por lo tanto, hacen referencia a este tipo de subcontratación también como [subcontratación. actividad- basada activity-based-subcontracting.md] () Se han enviado a un tipo de grupo de costes especial, ** contratación de recursos externos ** directa, y los servicios de subcontratación no forman parte de la lista de materiales del producto terminado. Cuando usa la producción ajustada, todas las actividades se definen por kanbans que se pueden estar relacionadas con uno o actividades del flujo de varias la producción. Hasta ahora, esa explicación suena tal como una explicación de pedidos de producción. Sin embargo, mientras que los pedidos de producción deben finalizar siempre con un producto terminado, puede crear kanbans para suministrar un producto semiterminado. No tiene que especificar un nuevo producto y el nivel de L.  

Dado que las reglas kanban pueden ser muy dinámicas, se puede crear un modelo a distintos variantes de fuente para el mismo producto de un flujo de producción. Cuando utilice la subcontratación lean, el flujo de material y el flujo financiero se separan estrictamente. Todo el flujo de material se representa con actividades de kanban. Los pedidos de compra para los productos de servicio y los registros de recepción de dichos servicios se pueden automatizar, en función del estado de los trabajos kanban en el flujo de producción. Los trabajos kanban se pueden iniciar y completar incluso antes de que se crean los pedidos de compra. Los documentos de subcontratación (pedido de compra y recepción de compra de servicio) se pueden agregar por período y servicio. Por lo tanto, el número de documentos y líneas de compra se puede mantener pequeño, incluso en las operaciones muy repetitivos de proveedores proporcionan servicios subcontratados en un flujo de la unidad.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Subcontratación de modelo en un flujo de producción

En a [flujo de producción (Lean] lean-manufacturing-modeling-lean-organization.md), una actividad de proceso se puede definir como subcontratado cuando haya asignado una celda de trabajo (grupo de recursos) que tiene un solo recurso de proveedor. Cuando subcontratan una celda de trabajo, las actividades de proceso relacionadas deben estar vinculados a una línea activa del acuerdo de compra que contiene el artículo de servicio y el precio de servicio. El acuerdo de servicio de la actividad también define el coeficiente de cálculo entre la cantidad de producto de trabajo kanban y la cantidad resultante de servicio. Puede seleccionar si la cantidad de servicio se calcula según el número de trabajos, de la cantidad de producto que se notifica en los trabajos, o de la cantidad total de producto (esta cantidad total incluye productos dado).  

Las actividades de transferencia también se pueden definir como subcontratado. Esta definición implícita aparece cuando se seleccione la parte responsable del envío en la actividad de transferencia. Al seleccionar ** expedidor ** o ** destinatario **, si el almacén correspondiente de origen o destino es un almacén de administrado, la actividad se considera subcontratado. Al seleccionar ** operador **, la actividad está siempre subcontrata. Las actividades de proceso subcontratadas similares, una actividad de transferencia subcontratada se deben conectar a un acuerdo de servicio antes de que el flujo de producción pueda estar activado.

### <a name="backflush-costing"></a>Contabilización previa de los costes

La contabilidad de costes del trabajo subcontratado es completamente integrada en la gestión de costes para la solución de producción ajustada (contabilización previa de los costes). Cuando una recepción de pedido de compra de servicio se registra, o cuando la facturación, aparece el coste del servicio se asigna al flujo de producción. Para la contabilización previa de los costes, la desviación de servicios subcontratados se calcula la compensación de los el bloque de subcontratación de costes estándar de los productos recibidos con las cantidades recibidas facturadas y reales de servicio.

## <a name="material-supply-for-subcontracted-operations"></a>Suministro material para las operaciones subcontratadas
Los productos semiterminados y otro material relacionado se deben transferir a la ubicación donde el trabajo se realiza físicamente. Cuando utilice operaciones y actividades subcontratadas, esta transferencia está relacionado con frecuencia con el transporte adicional a un sitio proveedor- operado. Afectando asignar el material en el MAT a la operación, se subcontratada declarar que los materiales se debe realizar en la ubicación de entrada del grupo de recursos para el recurso asignado. La planificación maestra o el reabastecimiento de Lean continuación aprovisiona material a dicha ubicación.  

Para crear un modelo del inventario que se ubica en un sitio del proveedor, es una práctica recomendada en el sector definir un almacén de administrado. Es fácil definir un almacén de administrado crear un nuevo almacén y al asignar la cuenta de proveedor. Para documentar que los materiales se debe transferir al proveedor antes de que una operación pueda realizarse, debe asignar el almacén de administrado al almacén de entrada del grupo de recursos que posee el recurso.  

Para reabastecer el material en este almacén, puede usar varios estrategias:

-   Transferir pedidos
-   Diarios de transferencias
-   Kanbans de retirada
-   Ejecutar la compra a la ubicación del proveedor

Los productos semiterminados son la excepción a esta regla. Para transferir productos semiterminados, se le limitan a estas opciones:

-   Para la producción y los pedidos de lote, los productos semiterminados se pueden transferir sólo lógicamente mediante el diario de lista de selección ** trabajo subcontratado ** de la página de lista. Este diario creará un documento de notas de entrega que se puede utilizar para transferir la materia prima semielaborada y al proveedor.
-   Para las operaciones subcontratadas en flujos de producción, la transferencia de productos semiterminados es documentada por la recepción de los kanban de retirada o de la producción en la ubicación del proveedor. Para crear una actividad de transferencia explícita, puede finalizar un kanban de la producción con una actividad de transferencia adicional.

** Nota: ** Una ruta de producción para un único pedido de producción no puede realizar varios sitios. Esta regla también se aplica al trabajo subcontratado. Por lo tanto, los almacenes que representan las ubicaciones de materiales tratan se deben definir en el mismo sitio que el de los recursos internos que se usan en la ruta. Aunque los flujos de producción pueden realizar sitios, no puede transportar los productos semiterminados desde un sitio a otro, ya que dicha operación implica un cambio de contexto del coste.  

Normalmente, el almacén de salida y la ubicación de un grupo de recursos subcontratado se asignan directamente al almacén y la ubicación del paso siguiente de la operación en la ruta o el flujo de producción. Esta configuración ayuda a reducir el importe de notificación de trabajo que aparezca u operaciones de transferencia adicionales del número que se deben modeladas.


