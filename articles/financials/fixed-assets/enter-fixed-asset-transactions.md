---
title: Opciones de transacciones de activos fijos
description: Este tema describe los diferentes métodos disponibles para crear transacciones de activos fijos.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f08750c369475f9d8be3c723aaf4eb6cf36eb7c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840562"
---
# <a name="fixed-asset-transaction-options"></a>Opciones de transacciones de activos fijos

[!include [banner](../includes/banner.md)]

Este tema describe los diferentes métodos disponibles para crear transacciones de activos fijos.

Puede configurar los activos fijos de la integración con los proveedores, clientes, adquisición y abastecimiento y contabilidad general. También puede transferir los artículos en gestión de inventarios a los activos fijos si desea usar dichos artículos internamente.

## <a name="accounts-payable"></a>Proveedores
Puede especificar transacciones de activos fijos en la página Asiento del diario. Esta página se puede abrir desde la página Diario de facturas. También puede abrir la página Asiento del diario en la página Diario de aprobación de facturas. En el campo Cuenta de contrapartida, seleccione Activos fijos. A continuación, en el campo Cuenta de contrapartida, seleccione un número de activo fijo. En la ficha de Activos fijos, especifique valores en los campos Tipo de transacción y Libro.

## <a name="accounts-receivable"></a>Clientes
Puede especificar transacciones de activos fijos en la página Factura de servicios.  En la página Factura de servicios, en la cuadrícula Líneas de factura, seleccione un artículo de línea. Haga clic en la ficha desplegable Detalles de línea. Especifique el número de activo fijo y el libro para la transacción de cancelación. Para facturas de servicio, el tipo de transacción de activos fijos es siempre Venta.

## <a name="procurement-and-sourcing"></a>Adquisición y abastecimiento
Puede especificar transacciones de activos fijos en la página Pedido de compra. Especifique información adicional necesaria para crear un pedido de compra y, a continuación, haga clic en Aceptar. En la página Pedido de compra, haga clic en la ficha desplegable Detalles de línea. A continuación, en la pestaña Activos fijos, especifique información sobre el activo fijo. 

Para registrar una transacción de adquisición para un activo fijo existente, especifique el número de activo fijo, el libro y el tipo de transacción. El activo fijo no se puede registrar si falta alguno de estos datos. Para registrar una transacción de adquisición para un nuevo activo fijo, seleccione la opción Nuevo activo fijo y, a continuación, seleccione el grupo de activos fijos al que se debe asignar el nuevo activo. No obstante, ninguno de los campos de activo fijo estarán disponibles para una línea si el artículo se encuentra en un grupo de modelos de inventario que usa un modelo de inventario de coste estándar. Además, las opciones que se definen en la página de parámetros Activos fijos determinan si se pueden registrar transacciones de adquisición de los módulos de compra. 

Cuando se usa un pedido de compra o el Inventario en diario de activos fijos para adquirir activos fijos, el valor del inventario se verá afectado.

## <a name="general-ledger"></a>Contabilidad general
Cualquier tipo de transacción de activos fijos se puede registrar en la página Diario general. También puede usar diarios de activos fijos para registrar transacciones de activos fijos.

## <a name="options-for-entering-fixed-asset-transaction-types"></a>Opciones para especificar los tipos de transacción de activos fijos


| Tipo de transacción                    | Módulo                   | Opciones                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| Adquisición, ajuste de adquisición | Activos fijos             | Activos fijos, Inventario a activos fijos   |
|                                     | Contabilidad general           | Diario general                           |
|                                     | Proveedores         | Diario de facturas, Diario de aprobación de facturas |
|                                     | Adquisición y abastecimiento | Pedido de compra                            |
| Depreciación                        | Activos fijos             | Activos fijos                              |
|                                     | Contabilidad general           | Diario general                           |
| Cancelación                            | Activos fijos             | Activos fijos                              |
| ** **                               | Contabilidad general           | Diario general                           |
| ** **                               | Clientes      | Factura de servicios                         |


El valor restante de los períodos de depreciación del activo fijo no se actualiza cuando una línea de diario del tipo de transacción de depreciación se crea o se importa manualmente a través de una entidad de los datos. Este valor se actualiza cuando el proceso de propuesta de depreciación se utiliza para crear la línea de diario.

Para obtener más información, consulte [Integración de activos fijos](fixed-asset-integration.md).
