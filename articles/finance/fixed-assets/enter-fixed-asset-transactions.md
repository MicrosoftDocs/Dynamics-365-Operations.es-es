---
title: Opciones de transacciones de activos fijos
description: Este tema describe los diferentes métodos disponibles para crear transacciones de activos fijos.
author: ShylaThompson
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: roschlom
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f9cd8846688e6b70f3ac2034caa1a9e3015355e
ms.sourcegitcommit: f9b40df70a77136529fbc790325ed657eb203731
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2021
ms.locfileid: "6645381"
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

### <a name="options-for-entering-fixed-asset-transaction-types"></a>Opciones para especificar los tipos de transacción de activos fijos


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

### <a name="transactions-that-require-different-voucher-numbers"></a>Transacciones que requieren números de asiento distintos

Las siguientes transacciones de activos fijos utilizarán diferentes números de asiento:

- Se crea una adquisición adicional en un activo y se calcula la depreciación de "actualización".
- Un activo está dividido.
- Un parámetro para calcular la depreciación al cancelar se habilita y luego el activo se cancela.
- La fecha de servicio de un activo es anterior a la fecha de adquisición. Por lo tanto, se registra un ajuste de depreciación.

> [!NOTE]
> Cuando introduzca transacciones, asegúrese de que todas las transacciones se aplican al mismo activo fijo. Un asiento no se registrará si incluye más de un activo fijo, incluso si el campo **Nuevo asiento** se establece en **Un número de asiento únicamente** en la página **Nombres de diario** en contabilidad general. Si incluye más de un activo fijo en el asiento, recibirá el mensaje "Solo puede haber una transacción de activo fijo por asiento" y no se podrá registrar el asiento.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
