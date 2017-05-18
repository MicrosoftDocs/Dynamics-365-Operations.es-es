---
title: "Visión general de la administración de transporte"
description: "Este tema ofrece una visión general de la funcionalidad de Administración de transporte en Microsoft Dynamics 365 for Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 233468799f040fec982622961640c815c32c5266
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="transportation-management-overview"></a>Visión general de la administración de transporte

[!include[banner](../includes/banner.md)]


Este tema ofrece una visión general de la funcionalidad de Administración de transporte en Microsoft Dynamics 365 for Operations.

La Administración de transporte le permite gestionar el transporte de su empresa e identificar soluciones de proveedor y de ruta para los pedidos de entrada y salida. Por ejemplo, puede identificar la ruta más rápida o la tarifa menos cara para un envío. En la tabla siguiente se describen los escenarios principales para usar la Administración de transporte en Microsoft Dynamics 365 for Operations.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Situación</th>
<th>Cómo puede ayudar la Administración de transporte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Use proveedores de logística externos para las actividades de transporte.</td>
<td>Use la gestión de transporte para el transporte de entrada y/o salida.</td>
</tr>
<tr class="even">
<td>La propia flota de la empresa está disponible para entrega o recogida, y los gastos de entrega se aplican a los clientes.</td>
<td>Para los procesos de salida, puede usar la Administración de transporte para determinar los gastos de transporte y pasarlos a los clientes. Sin embargo, no es necesario el proceso de conciliación de facturas de transportista.</td>
</tr>
<tr class="odd">
<td>La propia flota de la empresa está disponible para entrega o recogida, pero los gastos de entrega no se aplican a los clientes, ya que los precios de productos incluyen el transporte.</td>
<td>No se requiere gran parte la funcionalidad de la gestión de transporte. Sin embargo, puede usar la Administración de transporte para determinar los índices de transporte y ajustar el precio de ventas en consecuencia.</td>
</tr>
<tr class="even">
<td>Otra entidad jurídica de la misma empresa proporciona el servicio de logística.</td>
<td><ul>
<li>Puede usar la Administración de transporte tratando la otra entidad jurídica como cualquier otro transportista de envío. No puede automatizar las transacciones económicas entre entidades jurídicas. Por tanto, debe gestionar estas transacciones manualmente (por ejemplo, creando un pedido de compra).</li>
<li>En la entidad jurídica que proporciona servicios de logística, se puede usar la Administración de transporte para determinar los índices de transporte.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-dynamics-365-for-operations"></a>Planificación del transporte en Dynamics 365 for Operations
En la Administración de transporte, la planificación del transporte se puede basar en órdenes o en los envíos que se crean a partir de esos pedidos. Los envíos siempre existen en algún punto específico pero no son necesarios para la planificación de transporte. Los pedidos de transferencia forman parte del escenario de salida y se pueden planificar junto con los pedidos de ventas. 

![Cargar dibujo](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a>Transporte de entrada
Cuando pide artículos a un proveedor, y los artículos se deben entregarse a su almacén, puede que desee organizar el transporte de los artículos usted mismo. Puede usar Dynamics 365 for Operations para planificar el transporte y la recepción de la carga de entrada. En la siguiente ilustración se muestra el flujo del proceso empresarial para planificar el transporte de una carga de entrada. 

![Flujo del proceso empresarial para el transporte de la carga de entrada](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a>Transporte de salida
Puede planificar y procesar una carga de salida para enviar artículos específicos del almacén de una empresa a un cliente. Puede usar Dynamics 365 for Operations para planificar el transporte y el envío de una carga de salida. En la siguiente ilustración se muestra el flujo del proceso empresarial para planificar y procesar las cargas de salida para su envío. 

![Planificación y procesamiento de cargas de salida](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a>Planificación de carga
Dynamics 365 for Operations proporciona una estrategia de planificación de carga que se denomina Estrategia de planificación de la carga basada en volumen. Esta estrategia le permite usar los valores máximos que se especifican para la altura y el peso de la plantilla de carga o bien, puede reemplazar los ajustes especificando valores nuevos. Para usar esta estrategia, selecciónela en el campo **Estrategia de creación de carga** en la ficha desplegable **Programa de instalación** de la página **Banco de trabajo de creación de carga**. Además, puede agregar sus propias estrategias de creación de carga creando una nueva clase en el árbol de objetos de aplicación (AOT).




