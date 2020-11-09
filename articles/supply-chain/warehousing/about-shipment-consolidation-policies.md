---
title: Directivas de consolidación de envíos
description: Este tema proporciona una descripción general de la funcionalidad que proporciona una configuración flexible de las directivas de consolidación de envíos.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationError, WHSShipConsolidationSetShipment, WHSShipConsolidationPolicySelect, WHSShipPlanningListPage, TMSCarrierGroup, WHSShipConsolidationTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 1f2e1bcd220f0cd94fb1515e42fd3f8250c1c621
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016364"
---
# <a name="shipment-consolidation-policies"></a>Directivas de consolidación de envíos

El proceso de consolidación de envíos que utiliza directivas de consolidación de envíos permite la consolidación automatizada de envíos durante la liberación automática y manual al almacén. La consolidación automática que estaba disponible antes de que se introdujera esta función tenía campos codificados y se basaba en el campo **Consolidar el envío en el despacho al almacén** que se estableció para un almacén.

Las directivas de consolidación de envíos se utilizan para la siguiente funcionalidad:

- El trabajo por lotes automatizado de despacho al almacén
- El comando **Despacho al almacén** en un pedido de ventas o pedido de transferencia
- La página dedicada **Despachar al almacén**
- El comando **Despachar al alamacén** en la página **Área de trabajo de planificación de la carga**
- La consolidación manual de envíos en las páginas **Consolidar envíos** y **Banco de trabajo de consolidación de envíos**

Antes de que se introdujeran las directivas de consolidación de envíos, la función de consolidación existía como una configuración a nivel de almacén. Todos los pedidos para todos los clientes de un único almacén se trataban como si tuvieran los mismos requisitos de consolidación. Las directivas de consolidación de envíos agregan soporte para escenarios donde diferentes organizaciones tienen diferentes requisitos para la consolidación de envíos.

Las consultas se utilizan para identificar la directiva de consolidación de envíos que se aplica, y luego un conjunto de campos editables determina cómo se agrupan las líneas de carga a nivel de envío. (Este patrón se asemeja al patrón que siguen las plantillas de oleada). Además, se ha añadido a cada directiva uan opción **Consolidar con envíos existentes**. Cuando esta opción está activada, el procedimiento *Despachar al almacén* busca envíos para consolidación buscando entre los envíos existentes que se crearon según la misma directiva de consolidación. En este caso, el sistema seleccionará un envío o carga existente en lugar de crear uno nuevo. Sin embargo, el sistema solo se consolidará con envíos existentes que tengan un estado de *Abierto* ; los envíos que pertenecen a un lanzamiento de oleada con un estado de *Liberado* o superior no se considerarán como objetivos para la consolidación.

Cuando las directivas de consolidación de envíos están disponibles, la opción **Consolidar el envío al despachar al almacén** que anteriormente estaba disponible en la página de configuración **Almacenes** queda oculta. Para ayudarle a realizar la transición a la nueva función de consolidación de envíos, una función en la página **Directivas de consolidación de envíos** crea una directiva predeterminada que incluye automáticamente la configuración anterior para los almacenes existentes. Después de crear esa directiva predeterminada, la opción **Consolidar el envío en el despacho al almacén** de la página de opciones **Almacenes** ya no se considerará.

Puedes usar la página **Despachar al almacén** para anular manualmente la directiva de consolidación aplicable de la misma manera que puede anular las directivas de cumplimiento.

Puede usar el comando **Despachar \> Despachar al almacén** en la página **Banco de trabajo de planificación de la carga** para crear cargas salientes que se basan en pedidos de ventas y líneas de órdenes de transferencia antes de realizar el despacho al almacén. Estas cargas utilizan la misma lógica de consolidación que se introdujo junto con la consolidación de las directivas de envío.

Puede usar la página **Banco de trabajo de consolidación de envíos** para consolidar los envíos existentes que aún no se han confirmado pero que ya se han despachado al almacén. Esta funcionalidad admite escenarios en los que el proceso de liberación automatizada, que tiene su propia consolidación de envío, se ejecuta varias veces al día, pero se identifican manualmente posibles consolidaciones adicionales antes de que se complete el envío a los transportistas durante el proceso de confirmación. Esta funcionalidad le permite consolidar los envíos salientes que se crean a partir de pedidos de ventas o líneas de órdenes de transferencia en cualquier momento después de que los envíos se despachan al almacén, pero antes de que se confirmen.

La página **Ärea de trabajo de consolidación de envíos** funciona como el área de trabajo de construcción de carga, donde puede evaluar varios envíos al mismo tiempo y asignar un pedido no consolidado a un envío específico. Puede aplicar plantillas de consolidación de envíos para evaluar las consolidaciones propuestas varias veces y confirmarlas. Algunas reglas se implementan para evitar la consolidación no autorizada y para advertirle sobre posibles errores.

## <a name="overview-of-new-functionality"></a>Descripción general de la nueva funcionalidad

Esta sección describe las páginas, comandos y funciones que se cambian o agregan cuando activa y usa la función *Directivas de consolidación de envíos*.

### <a name="shipment-consolidation-policies-page"></a>Página de directivas de consolidación de envíos

Las directivas se diferencian por tipo de orden de trabajo. El tipo **Ordenes de venta** representaenvío de _Órdenes de venta_ y el tipo **Órdenes de transferencia** representa envíos con _Problema de transferencia_.

Cada directiva de consolidación de envíos tiene una consulta que define cuándo se aplica y un número de secuencia que determina el orden de ejecución. La consolidación se aplica para cada combinación única de los campos seleccionados. Un parámetro adicional que se proporciona se utiliza para la consolidación con envíos existentes (abiertos). Las directivas se evalúan y aplican cada vez que se crea un nuevo envío (antes del procesamiento de oleada).

Si a una directiva le faltan campos obligatorios, o si incluye campos prohibidos, la directiva se marca como no válida en la sección **Seleccionados**. Las listas de campos obligatorios y prohibidos están codificadas y pueden ampliarse.

La lista siguiente muestra los campos obligatorios. Debido a que los envíos siempre se dividen en función de estos campos, no puede agrupar varios envíos que tengan valores diferentes para estos campos.

- Para pedidos de ventas:

    - **Número de cuenta:** _WHSShipmentTable.AccountNum_
    - **Destinatario de la entrega:** _WHSShipmentTable.DeliveryName_
    - **Dirección postal (RecId):** _WHSShipmentTable.DeliveryPostalAddress_
    - **Almacén:** _WHSShipmentTable.InventLocationId_

- Para pedidos de transferencia:

    - **Del almacén:** _InventTransferTable.InventLocationIdFrom_
    - **Al almacén:** _InventTransferTable.InventLocationIdTo_

Los siguientes campos no están disponibles para todos los tipos de documentos. Estos campos no son visibles en la interfaz de usuario (UI) y no pueden usarse para la consolidación.

- **Id. del envío:** _WHSShipmentTable.ShipmentId_
- **Estado:** _WHSShipmentTable.ShipmentStatus_
- **Directiva de consolidación de envío:** _WHSShipmentTable.ShipConsolidationPolicyName_
- **Tipo de transacción de trabajo:** _WHSShipmentTable.WorkTransType_
- **Id. de oleada:** _WHSShipmentTable.WaveId_
- **Id. de carga:** _WHSShipmentTable.LoadId_
- **Id. del envío:** _WHSLoadLine.ShipmentId_
- **Id. de carga:** _WHSLoadLine.LoadId_

De manera predeterminada, cuando se crea una directiva, el conjunto de campos obligatorios se utiliza como campos de consolidación. Sin embargo, puede modificar la lista utilizando los botones de flecha izquierda y flecha derecha. (El proceso se asemeja al proceso para seleccionar métodos en plantillas de oleada).

Los valores que los usuarios seleccionen para estos campos se usarán para todos los envíos recién creados, o se agregarán a los envíos existentes durante la consolidación con esos envíos. Cuando dos envíos tienen el mismo valor para un campo seleccionado para la consolidación de esos envíos, los envíos se consolidan. El mismo principio se aplica a todos los campos de consolidación posteriores seleccionados. Si los valores difieren, el segundo envío se descarta y se seleccionará para un nuevo envío. El proceso de consolidación automatizado consiste en crear todas las combinaciones únicas de valores para los campos de consolidación de envío y luego asignar un envío a la combinación relevante.

Los campos no seleccionados se ignoran durante el proceso de consolidación. Si dos envíos tienen valores diferentes para un campo no seleccionado, el campo se borra (es decir, se establece en blanco). Si ambos envíos tienen el mismo valor para un campo no seleccionado, el campo se rellena.

Los campos de lista de consolidación (es decir, campos que se borrarán si tienen valores diferentes) está codificada. La lista contiene todos los campos que se inicializan desde una línea de pedido de ventas o de pedido de transferencia cuando se crea un nuevo envío. En otras palabras, si un campo no se inicializa desde una línea de pedido de ventas o de pedido de transferencia, se ignora cuando se agregan nuevos datos a un envío existente.

### <a name="release-to-warehouse-page"></a>Página Despachar al almacén

- Un nuevo campo en la cuadrícula inferior muestra la directiva de consolidación aplicada.
- Un nuevo botón le permite seleccionar y/o anular manualmente la directiva de consolidación.

### <a name="release-to-warehouse-command-on-the-load-planning-workbench-page"></a>Comando Despachar al alamacén en la página Área de trabajo de planificación de la carga

- La lógica se ajustó para usar directivas de consolidación aplicadas.
- Los envíos ahora se consolidan solo dentro de una sola carga.

### <a name="consolidate-shipments-page"></a>Página Consolidar envíos

- La búsqueda de envíos similares (es decir, candidatos para la consolidación) se modificó para utilizar los campos seleccionados en la directiva de consolidación de envíos.
- Los campos que tienen valores diferentes en distintos envíos ahora se configuran en blanco. (Anteriormente, se usaban los valores del envío "base" seleccionado).

### <a name="shipment-consolidation-workbench-page"></a>Página Área de trabajo de consolidación de envíos

- La nueva funcionalidad reproduce el proceso de consolidación manual a mayor escala.
- Ahora puede abrir esta página desde el menú **Despachar al almacén** del módulo **Gestion de almacén**.
- El algoritmo analiza los envíos existentes que aún no se han enviado. Luego propone la consolidación, basada en los campos que se seleccionan en las directivas de consolidación.

## <a name="comparison-of-functionality"></a>Comparación de funcionalidad

La siguiente tabla resume cómo funciona la consolidación de envíos cuando no se utilizan las directivas de consolidación de envíos y cuándo se utilizan.

| Sin directivas de consolidación de envíos | Con directivas de consolidación de envíos |
|---|----|
| No aplicable | Los envíos de ventas o transferencias seleccionados para la consolidación deben tener la misma directiva de consolidación que el envío que se está creando, o deben asignarse a un envío abierto (cuando la opción **Consolidar con envíos existentes** está activada). |
| El procedimiento *Despachar al almacén* no busca entre envíos existentes para encontrar un envío para la consolidación. Solo los envíos creados por una instancia actual del procedimiento *Liberar al almacén* se utilizan para encontrar un envío para consolidación. | Si la opción **Consolidar con envíos existentes** está activada para una directiva de consolidación que se está utilizando actualmente, el procedimiento *Liberar al almacén* busca entre los envíos existentes que se crearon según la misma directiva de consolidación para encontrar un envío para consolidación. Por lo tanto, si tiene dos directivas, un envío que se está creando según la directiva 2 nunca se consolidará con un envío creado según la directiva 1. |
| No aplicable | Si una lista de campos de directiva de consolidación está vacía, o si no se puede encontrar una directiva, se crea un nuevo envío para cada línea de pedido de ventas o de pedido de transferencia. |
| El siguiente campo de consolidación define la combinación única de valores que se utiliza para consolidar envíos para una *línea de transferencia*. (Los demás campos se ignoran).<ul><li>Número de pedido (OrderNum)</li></ul> | Los siguientes campos de consolidación definen la combinación única de valores que se utiliza para consolidar envíos para una *línea de transferencia*. (Los demás campos se ignoran).<ul><li>Número de pedido (OrderNum)</li><li>Destinatario de entrega (DeliveryName)</li><li>Dirección postal (DeliveryPostalAddress)</li><li>Código de país ISO (CountryRegionISOCode)</li><li>Dirección (Address)</li><li>Sitio (InventSiteId)</li><li>Almacén (InventLocationId)</li><li>Transportista de envío (CarrierCode)</li><li>Servicio de transportista (CarrierServiceCode)</li><li>Modo de entrega (ModeCode)</li><li>Grupo de transporte (CarrierGroupCode)</li><li>Condiciones de entrega (DlvTermId)</li></ul>Estos campos son los únicos campos disponibles y se inicializan cuando se crea un nuevo envío. |
| Los siguientes campos de consolidación definen la combinación única de valores que se utiliza para consolidar envíos para una *línea de ventas*. (Los demás campos se ignoran).<ul><li>Número de pedido (OrderNum)</li><li>Referencia del cliente (CustomerRef)</li><li>Solicitud del cliente (CustomerReq)</li><li>Condiciones de entrega (DlvTermId)</li></ul> | Los siguientes campos de consolidación definen la combinación única de valores que se utiliza para consolidar envíos para una *línea de ventas*. (Los demás campos se ignoran).<ul><li>Número de pedido (OrderNum)</li><li>Número de cuenta (AccountNum)</li><li>Destinatario de entrega (DeliveryName)</li><li>Dirección postal (DeliveryPostalAddress)</li><li>Código de país ISO (CountryRegionISOCode)</li><li>Dirección (Address)</li><li>Sitio (InventSiteId)</li><li>Almacén (InventLocationId)</li><li>Transportista de envío (CarrierCode)</li><li>Servicio de transportista (CarrierServiceCode)</li><li>Modo de entrega (ModeCode)</li><li>Grupo de transporte (CarrierGroupCode)</li><li>ID del corredor (BrokerCode)</li><li>Dirección (LoadDirection)</li><li>Condiciones de entrega (DlvTermId)</li><li>Referencia del cliente (CustomerRef)</li><li>Solicitud del cliente (CustomerReq)</li></ul>Estos campos son los únicos campos disponibles y se inicializan cuando se crea un nuevo envío. |
| No aplicable | Los siguientes campos de consolidación son obligatorios para una *línea de ventas* y no se pueden eliminar:<ul><li>Número de cuenta (AccountNum)</li><li>Destinatario de entrega (DeliveryName)</li><li>Dirección postal (DeliveryPostalAddress)</li><li>Almacén (InventLocationId)</li></ul>Por defecto, estos campos se asignarán cuando se cree una nueva directiva. No se pueden eliminar. |
| El procedimiento *Despacho de cargas al almacén* de la página **Área de trabajo de planificación de la carga** utiliza su propio código separado para crear envíos y oleadas. | Las directivas de consolidación de envío se aplican para determinar qué campos deben evaluarse para la consolidación. Los envíos se consolidan solo dentro de una sola carga. |
| Usted selecciona manualmente **Consolidar envíos** en la página **Todos los envíos** y luego selecciona un envío "base" de destino. El filtro sugerirá cualquier envío existente que tenga valores coincidentes para varios campos clave. | Usted selecciona manualmente **Consolidar envíos** en la página **Todos los envíos** y luego selecciona un envío "base" de destino. El sistema sugerirá otros envíos existentes al hacer coincidir los valores de varios campos clave configurados para las directivas de consolidación de envíos relevantes. |
| Puede usar el comando **Consolidar envíos** en la página **Todos los envíos** para solo un único envío. | La página **Área de trabajo de consolidación de envíos** le ayuda a encontrar un conjunto de envíos que aún no se han enviado. Estos envíos se analizan en función de varios campos clave configurados en sus directivas de consolidación de envíos. Cualquier envío en el que coincidan los valores de estos campos se sugiere para la consolidación.<p>Puede mantener manualmente la consolidación eliminando los envíos de las consolidaciones sugeridas y/o agregándoles envíos. Pueden ocurrir varios tipos de errores, pero puede pasar por alto algunos de ellos.</p> |
| **Nota de diseño:** el procedimiento *Liberación automática de pedidos de ventas al almacén* divide las líneas de ventas en grupos. Cada grupo tiene su propio y único valor **ReleaseToWarehouseId** y se procesa por separado mediante el procedimiento *Despachar al almacén*. Este procedimiento crea un nuevo trabajo independientemente de la configuración de separación de trabajos. | **Nota de diseño:** el procedimiento *Despacho automático de pedidos de ventas al almacén* asigna el mismo valor **ReleaseToWarehouseId** para todas las líneas de ventas que se están procesando. Todas las líneas de ventas las procesa el procedimiento *Despachar al almacén* al mismo tiempo. Para garantizar el comportamiento anterior, debe configurar la separación de trabajos por id. de envío. |

## <a name="additional-resources"></a>Recursos adicionales

- [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md)
