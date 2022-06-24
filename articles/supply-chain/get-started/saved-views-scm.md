---
title: Vistas estándar guardadas para Supply Chain Management
description: Este artículo describe las vistas guardadas estándar que están disponibles y explica cómo habilitarlas.
author: kamaybac
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 92ff2dfc9cd8b742a7b086e540bd2c527833254d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887584"
---
# <a name="standard-saved-views-for-supply-chain-management"></a>Vistas estándar guardadas para Supply Chain Management

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management incluye varias vistas guardadas que puede habilitar y usar según sea necesario. Algunas de estas vistas guardadas estándar están optimizadas y nombradas para una función o tarea específica (por ejemplo, "Control de calidad" o "Recepción"). Otras están optimizadas para que incluyan solo los campos y configuraciones que las estadísticas de uso de Microsoft indican que los clientes usan con mayor frecuencia. Estas vistas guardadas normalmente se denominan vistas *simplificadas*. Este artículo describe las vistas guardadas estándar que están disponibles y explica cómo habilitarlas y personalizarlas.

Para obtener detalles completos sobre cómo trabajar con vistas guardadas, incluidas las vistas guardadas estándar, después de habilitarlas, consulte[ Vistas guardadas](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="customizing-the-standard-saved-views"></a>Personalizar las vistas guardadas estándar

Puede personalizar las vistas guardadas estándar, al igual que puede personalizar sus propias vistas guardadas. Sin embargo, cuando personaliza una vista guardada estándar, le recomendamos encarecidamente que guarde su versión personalizada con un nombre nuevo. De lo contrario, sus personalizaciones podrían sobrescribirse cuando actualice Supply Chain Management.

Para obtener más información sobre cómo personalizar y cambiar el nombre de las vistas guardadas, consulte[ Vistas guardadas](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="available-saved-views-and-how-to-enable-them"></a>Vistas guardadas disponibles y cómo habilitarlas

Para utilizar cualquier vista guardada, independientemente de si utilizará las vistas guardadas estándar, debe activar la característica *Vistas guardadas* en [Administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (a partir de la versión 10.0.21, esta característica está activada de forma predeterminada).

Las secciones restantes de este artículo proporcionan tablas que describen las vistas guardadas estándar que están disponibles actualmente para cada módulo relevante. Cada tabla muestra el nombre de cada vista guardada, la página donde puede encontrarla y una descripción de la misma. Cada tabla también muestra el nombre de la función que incluye la vista guardada. Para ver una vista guardada estándar en su sistema, debe activar la función especificada en[ Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). A partir de la versión 10.0.25, todas las vistas enumeradas están activadas de forma predeterminada.

## <a name="saved-views-for-the-inventory-management-module"></a>Vistas guardadas para el módulo de gestión de inventario

La siguiente tabla describe las vistas guardadas disponibles para el módulo de gestión de inventario.

| Página | Nombre de vista | Ver la descripción | Nombre de característica |
|---|---|---|---|
| Lista disponible | Operaciones financieras | Esta vista simplificada le permite concentrarse en la información financiera mientras administra el inventario disponible. | Vistas guardadas para Gestión del inventario<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Lista disponible | Control de calidad | Esta vista simplificada le permite concentrarse en el control de calidad mientras administra el inventario disponible. | Vistas guardadas para Gestión del inventario<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Lista disponible | Recepción | Esta vista simplificada le permite concentrarse en las operaciones de recepción mientras administra el inventario disponible. | Vistas guardadas para Gestión del inventario<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Lista disponible | Envío | Esta vista simplificada le permite concentrarse en las operaciones de envío mientras administra el inventario disponible. | Vistas guardadas para Gestión del inventario<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Transacciones | Simplificado | Esta vista simplificada le permite revisar el estado del inventario sin distraerse con la información financiera y otros campos que se utilizan con menos frecuencia. | Vistas guardadas para Gestión del inventario<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Pedidos de transferencia | Envío | Esta vista simplificada le permite concentrarse en las operaciones de envío mientras administra los pedidos de transferencias. | Vistas guardadas para Gestión del inventario<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Pedidos de transferencia | Recepción | Esta vista simplificada le permite concentrarse en las operaciones de recepción mientras administra los pedidos de transferencias. | Vistas guardadas para Gestión del inventario<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Pedidos de transferencia | Control de calidad | Esta vista simplificada le permite concentrarse en las operaciones de control de calidad mientras administra los pedidos de transferencias. | Vistas guardadas para Gestión del inventario<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Pedidos de transferencia | Operaciones financieras | Esta vista simplificada le permite concentrarse en la información financiera mientras administra los pedidos de transferencias. | Vistas guardadas para Gestión del inventario<br><br>(Activado por defecto a partir de la versión 10.0.21) |

## <a name="saved-views-for-the-master-planning-module"></a>Vistas guardadas para el módulo de planificación maestra

La siguiente tabla describe las vistas guardadas disponibles para el módulo de planificación maestra.

| Página | Nombre de vista | Ver la descripción | Nombre de característica |
|---|---|---|---|
| Pedidos planificados: página de detalles del pedido planificado | Simplificada | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia para trabajar con los detalles de un solo pedido planificado. De esta manera, proporciona una descripción general más rápida y un proceso de trabajo simplificado. | Vistas guardadas para pedidos planificados<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Pedidos planificados: página de lista de pedidos planificados | Simplificado | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia para trabajar con la lista de pedidos planificados. De esta manera, proporciona una descripción general más rápida y un proceso de trabajo simplificado. | Vistas guardadas para pedidos planificados<br><br>(Activado por defecto a partir de la versión 10.0.25) |

## <a name="saved-views-for-the-procurement-and-sourcing-module"></a>Vistas guardadas para el módulo Adquisiciones y abastecimiento

La siguiente tabla describe las vistas guardadas disponibles para el módulo Adquisiciones y abastecimiento.

| Página | Nombre de vista | Ver la descripción | Nombre de característica |
|---|---|---|---|
| Detalles del pedido de compra | Creación de pedidos | Esta vista simplificada está optimizada para crear nuevos pedidos de compra. | Vistas guardadas para pedidos de compra<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Detalles del pedido de compra | Administración de inventario | Esta vista simplificada está optimizada para realizar actividades relacionadas con el inventario, como hacer un seguimiento del inventario que se ha recibido, recibir inventario, verificar los requisitos netos y ajustar las cantidades de los pedidos. | Vistas guardadas para pedidos de compra<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Detalles del pedido de compra | Administración financiera | Esta vista simplificada está optimizada para realizar actividades relacionadas con las finanzas, como facturación y verificación de precios, totales y cargos. | Vistas guardadas para pedidos de compra<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Detalles del pedido de compra | Aprobación de pedido | Esta vista simplificada está optimizada para aprobar pedidos de compra. | Vistas guardadas para pedidos de compra<br><br>(Activado por defecto a partir de la versión 10.0.25) |

## <a name="saved-views-for-the-product-information-management-module"></a>Vistas guardadas para el módulo de gestión de información del producto

La siguiente tabla describe las vistas guardadas disponibles para el módulo de gestión de información del producto.

| Página | Nombre de vista | Ver la descripción | Nombre de característica |
|---|---|---|---|
| Lista de productos lanzados | Creación de producto | Vista de página simplificada que solo incluye los campos que se usan con más frecuencia al crear productos. | Vistas guardadas para productos emitidos<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Detalles de producto emitido | Creación de producto | Vista de página simplificada que solo incluye los campos que se usan con más frecuencia al crear productos. | Vistas guardadas para productos emitidos<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Detalles de producto emitido | Administración de información de logística | Vista de página simplificada que solo incluye los campos que se usan con más frecuencia al administrar información de logística de productos. | Vistas guardadas para productos emitidos<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Detalles de producto emitido | Administración de información de compra | Vista de página simplificada que solo incluye los campos que se usan con más frecuencia al administrar información de compra de productos. | Vistas guardadas para productos emitidos<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Detalles de producto emitido | Administración de información de ventas | Vista de página simplificada que solo incluye los campos que se usan con más frecuencia al administrar información relacionada con ventas de productos. | Vistas guardadas para productos emitidos<br><br>(Activado por defecto a partir de la versión 10.0.21) |

## <a name="saved-views-for-the-production-control-module"></a>Vistas guardadas para el módulo Control de producción

La siguiente tabla describe las vistas guardadas disponibles para el módulo Control de producción.

| Página | Nombre de vista | Ver la descripción | Nombre de característica |
|---|---|---|---|
| Página de L.MAT de pedido de producción | Simplificada | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia. De esta manera, proporciona una descripción general más rápida y un proceso de trabajo simplificado. | Vistas guardadas para el control de producción<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Página de detalles del pedido de producción | Simplificado | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia. De esta manera, proporciona una descripción general más rápida y un proceso de trabajo simplificado. | Vistas guardadas para el control de producción<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Página de listas de selección de órdenes de producción | Simplificado | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia. De esta manera, proporciona una descripción general más rápida y un proceso de trabajo simplificado. | Vistas guardadas para el control de producción<br><br>(Activado por defecto a partir de la versión 10.0.21) |
| Página de lista de pedidos de producción | Simplificado | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia. De esta manera, proporciona una descripción general más rápida y un proceso de trabajo simplificado. | Vistas guardadas para el control de producción<br><br>(Activado por defecto a partir de la versión 10.0.21) |

## <a name="saved-views-for-the-sales-and-marketing-module"></a>Vistas guardadas para el módulo de marketing y Sales

La siguiente tabla describe las vistas guardadas disponibles para el módulo Adquisiciones y Sales.

| Página | Nombre de vista | Ver la descripción | Nombre de característica |
|---|---|---|---|
| Diario del albarán | Revisión del diario | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia para revisar los diarios de albarán. | Vistas guardadas para ventas y marketing<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Pedido de ventas | Creación de pedido | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia para crear pedidos de ventas. | Vistas guardadas para ventas y marketing<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Pedido de ventas | Revisión del pedido | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia para revisar pedidos de ventas. | Vistas guardadas para ventas y marketing<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Presupuesto de ventas | Creación de presupuesto | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia para crear presupuestos. | Vistas guardadas para ventas y marketing<br><br>(Activado por defecto a partir de la versión 10.0.25) |

## <a name="saved-views-for-the-warehouse-management-module"></a>Vistas guardadas para el módulo de gestión de almacén

La siguiente tabla describe las vistas guardadas disponibles para el módulo de gestión de almacén.

| Página | Nombre de vista | Ver la descripción | Nombre de característica |
|---|---|---|---|
| Todas las cargas | Procesamiento de entrada | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia para procesar cargas de entrada. | Vistas guardadas para procesamiento de carga<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Todas las cargas | Procesamiento saliente | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia para procesar cargas de salida. | Vistas guardadas para procesamiento de carga<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Todos los envíos | Procesamiento entrante | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia para procesar envíos de entrada. | Vistas guardadas para procesamiento de envíos<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Todos los envíos | Procesamiento saliente | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia para procesar envíos de salida. | Vistas guardadas para procesamiento de envíos<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Todas las oleadas | Simplificado | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia. De esta manera, proporciona una descripción general más rápida y un proceso de trabajo simplificado. | Vista guardada para procesamiento de oleadas<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Área de trabajo de planificación de la carga | Simplificado | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia. De esta manera, proporciona una descripción general más rápida y un proceso de trabajo simplificado. | Vista guardada para el área de trabajo de planificación de la carga<br><br>(Activado por defecto a partir de la versión 10.0.25) |
| Detalles del trabajo | Simplificado | Esta vista simplificada incluye solo los campos que se utilizan con más frecuencia. De esta manera, proporciona una descripción general más rápida y un proceso de trabajo simplificado. | Vista guardada para la página de detalles del trabajo<br><br>(Activado por defecto a partir de la versión 10.0.25) |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]