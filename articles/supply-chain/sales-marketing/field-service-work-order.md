---
title: Sincronizar pedidos de trabajo en Field Service con pedidos de ventas en Supply Chain Management
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar pedidos de trabajo en Field Service con los pedidos de ventas en Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: d8051e21c731213e2d74ab6eeb80c239ca9932e6
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528932"
---
# <a name="synchronize-work-orders-in-field-service-to-sales-orders-in-supply-chain-management"></a>Sincronizar pedidos de trabajo en Field Service con pedidos de ventas en Supply Chain Management

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar pedidos de trabajo en Dynamics 365 Field Service a pedidos de ventas en Dynamics 365 Supply Chain Management.

[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)


## <a name="templates-and-tasks"></a>Plantillas y tareas

Las siguientes plantillas y las tareas subyacentes que se usan para ejecutar la sincronización de pedidos de trabajo en Field Service con los pedidos de ventas en Supply Chain Management.

### <a name="names-of-the-templates-in-data-integration"></a>Nombres de las plantillas en la integración de datos

La plantilla **Pedidos de trabajo a los pedidos de ventas (Field Service to Supply Chain Management)** se usa para ejecutar la sincronización.

### <a name="names-of-the-tasks-in-the-data-integration-project"></a>Nombres de las tareas en el proyecto de integración de datos

- WorkOrderHeader
- WorkOrderServiceLineEstimate
- WorkOrderServiceLineUsed
- WorkOrderProductLineEstimate
- WorkOrderProductLineUsed

Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los encabezados y líneas del pedido:

- Productos de Field Service (Supply Chain Management a Field Service)
- Cuentas (Sales a Supply Chain Management) - Direct

## <a name="entity-set"></a>Conjunto de entidades

| **Field Service** | **Gestión de la cadena de abastecimiento** |
|-------------------------|-------------------------|
| msdyn_workorders        | Encabezado de pedidos de ventas de CDS |
| msdyn_workorderservices | Líneas de pedido de ventas de CDS   |
| msdyn_workorderproducts | Líneas de pedido de ventas de CDS   |

## <a name="entity-flow"></a>Flujo de la entidad

Los pedidos de trabajo se crean en Field Service. Si los pedidos de trabajo incluyen solo productos mantenidos externamente y si el valor de **Estado de la orden de trabajo** difiere de **Abierto - no programado** y **Cerrado – Cancelado**, las órdenes de trabajo se pueden sincronizar con Supply Chain Management mediante un proyecto de integración de datos de Common Data Service. Las actualizaciones en los pedidos de trabajo se sincronizarán como pedidos de ventas en Supply Chain Management. Estas actualizaciones incluyen información acerca del tipo y el estado de origen.

## <a name="estimated-versus-used"></a>Estimado versus utilizado

En Field Service, los productos y servicios en pedidos de trabajo tienen tanto valores **Estimado** como valores **Utilizado** para las cantidades e importes. Sin embargo, en Supply Chain Management, los pedidos de ventas no tienen el mismo concepto de valores **Estimado** y **Utilizado**. Para admitir la asignación de producto que utiliza la cantidad prevista en el pedido de ventas en Supply Chain Management, pero mantener la cantidad utilizada que debe ser consumida y facturada, dos conjuntos de tareas sincronizan los productos y servicios en la orden de trabajo. Un conjunto de tareas es por valores **Estimado** y el otro conjunto de tareas es por valores **Utilizado**.

Este comportamiento habilita las situaciones en las que los valores estimados se utilizan para la asignación o la reserva en Supply Chain Management, mientras que los valores utilizados se usan para el consumo y facturar.

### <a name="estimated"></a>Estimada

Para la sincronización de las líneas de productos, se utilizan los valores **Estimado** cuando el valor **Estado de línea** es **Estimado**, la opción **Asignado** se establece en **Sí** y el valor **Estado del sistema** no es **Cerrado – enviado**.

Para la sincronización de las líneas de servicios, se utilizan los valores **Estimado** cuando el valor **Estado de línea** es **Estimado** y el valor del **Estado del sistema** no es **Cerrado – enviado**.

### <a name="used"></a>Utilizado

Los valores **Utilizado** se usan para el consumo y facturar. En estos casos, se sincronizan los valores **Utilizado**.

La tabla siguiente proporciona una visión general de las distintas combinaciones para las líneas de productos.

| Estado del sistema <br>(Field Service) | Línea de estado <br>(Field Service) | Asignado <br>(Field Service) |Valor sincronizado <br>(Supply Chain Management) |
|--------------------|-------------|-----------|---------------------------------|
| Abrir: programado   | Estimada   | Sí       | Estimada                       |
| Abrir: programado   | Estimada   | N.º        | Utilizado                            |
| Abrir: programado   | Utilizado        | Sí       | Utilizado                            |
| Abrir: programado   | Utilizado        | N.º        | Utilizado                            |
| Abrir: en proceso | Estimada   | Sí       | Estimada                       |
| Abrir: en proceso | Estimada   | N.º        | Utilizado                            |
| Abrir: en proceso | Utilizado        | Sí       | Utilizado                            |
| Abrir: en proceso | Utilizado        | N.º        | Utilizado                            |
| Abrir: completado   | Estimada   | Sí       | Estimada                       |
| Abrir: completado   | Estimada   | N.º        | Utilizado                            |
| Abrir: completado   | Utilizado        | Sí       | Utilizado                            |
| Abrir: completado   | Utilizado        | N.º        | Utilizado                            |
| Cerrado: registrado    | Estimada   | Sí       | Utilizado                            |
| Cerrado: registrado    | Estimada   | N.º        | Utilizado                            |
| Cerrado: registrado    | Utilizado        | Sí       | Utilizado                            |
| Cerrado: registrado    | Utilizado        | N.º        | Utilizado                            |

La tabla siguiente proporciona una visión general de las distintas combinaciones para las líneas de servicios.

| Estado del sistema <br>(Field Service) | Línea de estado <br>(Field Service) | Valor sincronizado <br>(Supply Chain Management) |
|--------------------|-------------|-----------|
| Abrir: programado   | Estimada   | Estimada |
| Abrir: programado   | Usado        | Utilizado      |
| Abrir: en proceso | Estimada   | Estimada |
| Abrir: en proceso | Utilizado        | Utilizado      |
| Abrir: completado   | Estimada   | Estimada |
| Abrir: completado   | Utilizado        | Utilizado      |
| Cerrado: registrado    | Estimada   | Utilizado      |
| Cerrado: registrado    | Utilizado        | Utilizado      |

La sincronización de valores **Estimado** versus **Utilizado** se administra mediante los dos conjuntos de tareas para las líneas de productos y las líneas de servicio. Los filtros predefinidos activan la tarea correcta y asignación subyacente ayuda a garantizar que los valores correctos para **Esperado** versus **Utilizado** se sincronizan.

### <a name="example"></a>Ejemplo

1. Un pedido de trabajo se crea y se programa en Field Service.

    El valor **Estado del sistema** es **Abierto – programado**.

    - **Línea de productos:** Cant estimada = 5ea, Cant utilizada = 0ea, estado de línea = Estimado, Asignado = No
    - **Línea de servicio:** Cant estimada = 2h, Cant utilizada = 0h, Estado de línea = Estimado

    En este ejemplo, el valor del producto **Cant utilizada** **0** (cero) y el valor **Cant estimada** del servicio **2h** se sincronizan de Supply Chain Management.

2. Los productos se asignan en Field Service.

    El valor **Estado del sistema** es **Abierto – programado**.

    - **Línea de productos:** Cant estimada = 5ea, Cant utilizada = 0ea, estado de línea = Estimado, Asignado = Yes
    - **Línea de servicio:** Cant estimada = 2h, Cant utilizada = 0h, Estado de línea = Estimado

    En este ejemplo, el valor del producto **Cant estimada** de **5ea** y el valor **Cant estimada** del servicio de **2h** se sincronizan de Supply Chain Management.

3. El técnico de servicio comienza a trabajar en el pedido de trabajo y registra el uso de material. 6.

    El valor **Estado del sistema** es **Abierto – en progreso**.

    - **Línea de productos:** Cant estimada = 5ea, Cant utilizada = 6ea, estado de línea = Usado, Asignado = Yes
    - **Línea de servicio:** Cant estimada = 2h, Cant utilizada = 0h, Estado de línea = Estimado

    En este ejemplo, el valor del producto **Cant utilizada** **6** y el valor **Cant estimada** del servicio **2h** se sincronizan de Supply Chain Management.

4. El técnico de servicio completa el pedido de trabajo y registra el tiempo empleado de 1,5 horas.

    El valor **Estado del sistema** es **Abierto – Completado**.

    - **Línea de productos:** Cant estimada = 5ea, Cant utilizada = 6ea, estado de línea = Usado, Asignado = Yes
    - **Línea de servicio:** Cant estimada = 2h, Cant utilizada = 1,5h, Estado de línea = Utilizado

    En este ejemplo, el valor del producto **Cant utilizada** de **6** y el valor **Cant utilizada** del servicio de **1,5h** se sincronizan en Supply Chain Management.

## <a name="sales-order-origin-and-status"></a>Origen y estado del pedido de ventas

### <a name="sales-origin"></a>Origen de la venta

Para realizar un seguimiento de los pedidos de ventas que se originan de pedidos de trabajo, puede crear un origen de ventas en la opción **Asignación de tipo de origen** se establece en **Sí** y el campo **Tipo de origen de ventas** se establece en **Integración de pedidos de trabajo**.

De forma predeterminada, la asignación selecciona el origen de ventas para tipo de origen ventas **Integración de pedidos de trabajo** para todos los pedidos de ventas que se creen de pedidos de trabajo. Este comportamiento puede ser útil cuando trabaja con el pedido de ventas en Supply Chain Management. Debe asegurarse de que los pedidos de ventas que se originan de pedidos de trabajo no estén sincronizados de nuevo Field Service como pedidos de trabajo.

Para obtener más información sobre cómo crear la configuración correcta del origen de ventas en Supply Chain Management, consulte la sección "Condiciones previas y configuración de la asignación" de este tema.

### <a name="status"></a>Estado

Cuando el pedido de ventas se origina desde un pedido de trabajo, el campo **Estado del pedido externo de trabajo** aparece en la pestaña **Configuración** en el encabezado del pedido de ventas. Este campo muestra el estado del sistema de la orden de trabajo en Field Service, para ayudarle a seguir el estado del pedido sincronizado de trabajo de pedidos de ventas en Supply Chain Management. Este campo también puede ayudar al usuario a determinar cuándo el pedido de ventas debe registrarse o facturarse.

El campo **Estado del pedido de trabajo externo** puede tener los siguientes valores:

- Abrir: programado
- Abrir: en proceso
- Abrir: completado
- Cerrado: registrado

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service

Para admitir la integración entre Field Service y Supply Chain Management, la funcionalidad adicional de la solución de CRM Field Service es necesaria. La solución incluye los siguientes cambios.

### <a name="work-order-entity"></a>Entidad de pedido de trabajo

El campo **Solo tiene productos mantenidos externamente** se ha agregado a la entidad **Pedido de trabajo** y aparece en la página. Se utiliza para hacer un seguimiento de si un pedido de trabajo consiste completamente en productos mantenidos externamente. Una orden de trabajo solo contiene productos mantenidos externamente cuando todos los productos relacionados se mantienen en Supply Chain Management. Este campo ayuda a garantizar que los usuarios no sincronizan las órdenes de trabajo que tienen productos desconocidos.

### <a name="work-order-product-entity"></a>Entidad de producto de pedido de trabajo

- El campo **El pedido solo tiene productos mantenidos externamente** se ha agregado a la entidad **Producto de pedido de trabajo** y aparece en la página. Se utiliza para hacer un seguimiento constante de si el producto de la orden de trabajo se mantiene en Supply Chain Management. Este campo ayuda a garantizar que los usuarios no sincronizan los productos de la orden de trabajo que son desconocidos para Supply Chain Management.
- El campo **Estado del sistema de encabezado** se ha agregado a la entidad **Producto de pedido de trabajo** y aparece en la página. Se utiliza para hacer un seguimiento constante del estado del sistema de la orden de trabajo y ayuda a garantizar un filtrado correcto cuando los productos de la orden de trabajo se sincronizan con Supply Chain Management. Cuando los filtros se establecen en las tareas de integración, la información **Estado del sistema del encabezado** también se usa para determinar si los valores estimados o utilizados deben ser sincronizados.
- El campo **Importe de unidades facturada** muestra el importe que se factura por unidad real que se usa. El valor se calcula como el valor **Importe total** dividido por el valor **Cantidad real** . El campo se utiliza para la integración en sistemas que no admiten valores diferentes para la cantidad usada y la cantidad facturada. Este campo no aparece en la interfaz de usuario (UI). 
- El campo **Importe de descuento facturado** se calcula como el valor **Importe de descuento** más el redondeo del cálculo del valor **Importe de la unidad facturada**. Este campo se utiliza para la integración y no aparece en la interfaz de usuario.
- El campo **Cantidad decimal** guarda el valor del campo **Cantidad** como números decimales. Este campo se utiliza para la integración y no aparece en la interfaz de usuario. 
- El valor en los campos **Utilizado** se restablece a **0** (cero) si el valor **Estado de línea** del producto del pedido de trabajo cambia de **Utilizado** a **Estimado**. Este cambio ayuda a evitar situaciones en las que una cantidad usada que se ha especificado incorrectamente se utilizce para sincronización cuando el valor **Estado de línea** es **Estimado** y la opción **Asignado** se establece en **No**.

### <a name="work-order-service-entity"></a>Entidad de servicio de pedido de trabajo

- El campo **El pedido solo tiene productos mantenidos externamente** se ha agregado a la entidad **Servicio de pedido de trabajo** y aparece en la página. Se utiliza para hacer un seguimiento constante de si el servicio de la orden de trabajo se mantiene en Supply Chain Management. Este campo ayuda a garantizar que los usuarios no sincronizan los servicios de la orden de trabajo que son desconocidos para Supply Chain Management.
- El campo **Estado del sistema de encabezado** se ha agregado a la entidad **Servicio de pedido de trabajo** y aparece en la página. Se utiliza para hacer un seguimiento constante del estado del sistema de la orden de trabajo y ayuda a garantizar un filtrado correcto cuando los servicios de la orden de trabajo se sincronizan con Supply Chain Management. Cuando los filtros se establecen en las tareas de integración, la información **Estado del sistema del encabezado** también se usa para determinar si los valores estimados o utilizados deben ser sincronizados.
- El campo **Duración en horas** guarda el valor del campo **Duración** después de que el valor se convierta de minutos a horas. Este campo se utiliza para la integración y no aparece en la interfaz de usuario.
- El campo **Duración en horas estimada** guarda el valor del campo **Duración estimada** después de que el valor se convierta de minutos a horas. Este campo se utiliza para la integración y no aparece en la interfaz de usuario.
- El campo **Importe de unidades facturadas** guarda el importe que se factura por unidad real que se usa. El valor se calcula como el valor **Importe total** dividido por el valor **Cantidad real** . Este campo se utiliza para la integración en sistemas que no admiten valores diferentes para la cantidad usada y la cantidad facturada. El campo no aparece en la interfaz de usuario.
- El campo **Importe de descuento facturado** se calcula como el valor **Importe de descuento** más el redondeo del cálculo del valor **Importe de la unidad facturada**. Este campo se utiliza para la integración y no aparece en la interfaz de usuario.
- El campo **Línea de pedido externa** es un número de línea de pedido negativo calculado que se puede usar en sistemas externos donde se combinan líneas de producto de pedidos de trabajo y de servicio. Este campo permite que los productos de pedidos de trabajo que se insertan tengan números de línea positivos y los servicios de pedidos de trabajo tengan números de línea negativos. El valor de este campo se calcula como el valor **Línea de pedido** multiplicado por -1. Este campo no aparece en la interfaz de usuario.
- El valor en los campos **Utilizado** se restablece a **0** (cero) si el valor **Estado de línea** del servicio del pedido de trabajo cambia de **Utilizado** a **Estimado** por alguna razón. Este cambio ayuda a evitar situaciones en las que una cantidad usada que se ha especificado incorrectamente se utilizce para sincronización cuando el valor **Estado de línea** es **Estimado** y el valor **Estado del sistema de encabezado** es **Cerrado – Registrado**.

## <a name="preconditions-and-mapping-setup"></a>Condiciones previas y configuración de asignación

Antes de sincronizar pedidos de trabajo, es importante actualizar la configuración siguiente en los sistemas:

### <a name="setup-in-field-service"></a>Configuración en Field Service

- Asegúrese de que la serie numérica usada para las órdenes de trabajo en Field Service no se superpone con la secuencia numérica que se usa para los pedidos de ventas en Supply Chain Management. De lo contrario, los pedidos de ventas existentes se pueden actualizar incorrectamente en Field Service o Supply Chain Management.
- El campo **Creación de facturas de órdenes de trabajo** se debe establecer en **Nunca**, porque la facturación se hace desde Supply Chain Management. Vaya a **Field Service** \> **Configuración** \> **Administración** \> **Configuración de Field Service** y asegúrese de que el campo **Creación de facturas de pedidos de trabajo** está establecido en **Nunca**.

### <a name="setup-in-supply-chain-management"></a>Configurar Supply Chain Management

La integración de pedidos de trabajo requiere que configure el origen de ventas. El origen de la venta se utiliza para distinguir los pedidos de ventas en Supply Chain Management creados a partir de pedidos de trabajo en Field Service. Cuando un pedido de ventas tiene un origen de ventas del tipo **Integración del pedido de trabajo** aparece en la pestaña **Estado del pedido de trabajo externo** en el encabezado del pedido de ventas. Además, el origen de la venta ayuda a garantizar que los pedidos de ventas creados a partir de órdenes de trabajo en Field Service se filtren durante la sincronización del pedido de ventas de Supply Chain Management a Field Service.

1. Vaya a **Ventas y marketing** \> **Configuración** \> **Pedidos de ventas** \> **Origen de ventas**.
2. Seleccione **Nuevo** para crear un nuevo origen de ventas.
3. En el campo **Origen de ventas**, especifique un nombre para el origen de la venta, como **WorkOrder**.
4. En el campo **Descripción**, especifique una descripción, como **Pedido de trabajo de Field Service**.
5. Seleccione la casilla de verificación **Asignación de tipo de origen**.
6. Establezca el campo **Tipo de origen de ventas** a **Integración del pedido de trabajo**.
7. Seleccione **Guardar**.


### <a name="setup-in-data-integration"></a>Configurar en integración de datos

Asegúrse de que haya una **Tecla de integración** para **msdyn_workorders**
1. Ir a integración de datos
2. Seleccione la ficha **Conjunto de conexión**
3. Seleccione el conjunto de conexión utilizado para la sincronización de pedidos de trabajo
4. Seleccione la ficha **Tecla de integración**
5. Busque msdyn_workorders y compruebe que se haya agregado la clave **msdyn_name (número de pedido del trabajo)**. Si no se muestra, agréguela haciendo clic en **Agregar clave** y en **Guardar** en la parte superior de la página

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderheader"></a>Órdenes de trabajo a pedidos de ventas (Field Service a Supply Chain Management): WorkOrderHeader

Filtro: (msdyn_systemstatus ne 690970005) y (msdyn_systemstatus ne 690970000) y (msdynce_hasexternallymaintainedproductsonly eq true)

[![Asignación de la plantilla en la integración de datos](./media/FSWorkOrder1.png )](./media/FSWorkOrder1.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderservicelineestimate"></a>Órdenes de trabajo a pedidos de ventas (Field Service a Supply Chain Management): WorkOrderServiceLineEstimate

Filtro: (msdynce_headersystemstatus ne 690970005) y (msdynce_headersystemstatus ne 690970000) y (msdynce_orderhasexternalmaintainedproductsonly eq true) and (msdyn_linestatus eq 690970000) y (msdynce_headersystemstatus ne 690970004)

[![Asignación de la plantilla en la integración de datos](./media/FSWorkOrder2.png )](./media/FSWorkOrder2.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderservicelineused"></a>Órdenes de trabajo a pedidos de ventas (Field Service a Supply Chain Management): WorkOrderServiceLineUsed

Filtro: (msdynce_headersystemstatus ne 690970005) y (msdynce_headersystemstatus ne 690970000) y (msdynce_orderhasexternalmaintainedproductsonly eq true) y ((msdyn_linestatus eq 690970001) o (msdynce_headersystemstatus eq 690970004))

[![Asignación de la plantilla en la integración de datos](./media/FSWorkOrder3.png )](./media/FSWorkOrder3.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderproductlineestimate"></a>Órdenes de trabajo a pedidos de ventas (Field Service a Supply Chain Management): WorkOrderProductLineEstimate

Filtro: (msdynce_headersystemstatus ne 690970005) y (msdynce_headersystemstatus ne 690970000) y (msdynce_orderhasexternalmaintainedproductsonly eq true) y (msdyn_linestatus eq 690970000) y (msdynce_headersystemstatus ne 690970004) y (msdyn_allocated eq true)

[![Asignación de la plantilla en la integración de datos](./media/FSWorkOrder4.png )](./media/FSWorkOrder4.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderproductlineused"></a>Órdenes de trabajo a pedidos de ventas (Field Service a Supply Chain Management): WorkOrderProductLineUsed

Filtro: (msdynce_headersystemstatus ne 690970005) y (msdynce_headersystemstatus ne 690970000) y (msdynce_orderhasexternalmaintainedproductsonly eq true) y ((msdyn_linestatus eq 690970001) o (msdynce_headersystemstatus eq 690970004) o (msdyn_allocated ne true))

[![Asignación de la plantilla en la integración de datos](./media/FSWorkOrder5.png )](./media/FSWorkOrder5.png)
