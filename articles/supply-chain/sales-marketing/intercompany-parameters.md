---
title: Parámetros de empresas vinculadas
description: Este artículo explica los parámetros de empresas vinculadas
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7a9b921c7db47fe99981438932e5587f9a18f018
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850536"
---
# <a name="intercompany-parameters"></a>Parámetros de empresas vinculadas

[!include [banner](../../includes/banner.md)]

En una organización de empresas vinculadas, puede configurar los parámetros que determinen la forma en la se van a llevar a cabo las relaciones comerciales entre entidades jurídicas diferentes. Estos parámetros estarán determinados por los campos que seleccione. Puede seleccionar combinaciones diferentes para reflejar distintos escenarios comerciales.

Los siguientes dos ejemplos describen escenarios de organizaciones de empresas vinculadas, una con dos niveles y una con tres niveles.

## <a name="example-1-two-level-intercompany-chain"></a>Ejemplo 1: cadena de empresas vinculadas de nivel 2

La organización de empresas vinculadas incluye las entidades jurídicas siguientes:

- Entidad jurídica A: vende a clientes externos, pero no tiene existencias. Esta entidad jurídica compra a la entidad jurídica B.
- Entidad jurídica B: vende solo a la entidad jurídica A.

Ambas entidades jurídicas pueden vender y comprar entre ellas.

En este ejemplo, el precio del pedido de ventas original, dirigido al cliente externo, se basa siempre en el precio de ventas. El precio del pedido de ventas de empresas vinculadas y el pedido de compra de empresas vinculadas se controla mediante el precio de transferencia o ventas interno del pedido de ventas de empresas vinculadas en la entidad jurídica B.

La información de la cabecera del pedido se controla desde el pedido de ventas original al cliente externo. No se sincroniza ningún cambio del pedido de ventas de empresas vinculadas con el pedido de ventas original.

En la entidad jurídica A, en la página **Empresas vinculadas** para proveedores, seleccione **Directivas de pedidos de compra**. Seleccione los siguientes campos en el campo de grupo **Pedido de venta original (entrega directa)**:

- **Imprimir albarán automáticamente**
- **Registrar factura automáticamente**
- **Imprimir factura automáticamente**

En el grupo de campos **Pedido de compra de empresas vinculadas (entrega directa)**, seleccione el siguiente campo:

- **Registrar factura automáticamente**

En el grupo **Pedido de ventas original <-> Pedido de compra de empresas vinculadas**, seleccione los siguientes campos:

- **Información del cliente**
- **Número RMA**

En el grupo de campos **Pedido de compra de empresas vinculadas <-> Pedido de ventas de empresas vinculadas**, seleccione los siguientes campos:

- **Información del cliente**
- **Número RMA**
- **Número de lote**
- **Número de serie**

En la entidad jurídica B, en la página **Empresas vinculadas** para clientes, seleccione **Directivas de pedidos de venta**. Seleccione los siguientes campos en el campo de grupo **Creación de pedido de ventas de empresas vinculadas**:

- **Numeración de pedidos de ventas**: **Empresa + número original**
- **Permitir actualización de resumen de documentos para los clientes originales**

En el grupo de campos **Precios de pedidos de ventas de empresas vinculadas**, seleccione los siguientes campos:

- **Búsqueda de precio y descuento**
- **Permitir la edición de precio**
- **Permitir edición de descuento**

En el grupo de campos **Pedido de ventas de empresas vinculadas \> Pedido de compras de empresas vinculadas**, seleccione los siguientes campos:

- **Número de lote**
- **Número de serie**

## <a name="example-2-three-level-intercompany-chain"></a>Ejemplo 2: cadena de empresas vinculadas de nivel 3

La organización de empresas vinculadas incluye las entidades jurídicas siguientes:

- Entidad jurídica A: entidad jurídica que vende a los clientes externos y compra a la entidad jurídica B.
- Entidad jurídica B: entidad jurídica de distribución o producción que no puede entregar productos y que compra a la entidad jurídica C.
- Entidad jurídica C: una entidad jurídica de distribución o producción que envía productos a la entidad jurídica B.

El precio de transferencia interno entre las entidades jurídicas B y C se encuentra en el coste de la entidad legal vendedora al inicio de la cadena. Está también en el coste de la entidad jurídica A, que vende a los clientes externos. No obstante, el precio del pedido de ventas original para el cliente externo siempre se basa en el precio de ventas.

El precio en todos los pedidos de ventas de empresas vinculadas y pedidos de compra de empresas vinculadas se controla en el pedido de ventas de empresas vinculadas. Se controla al inicio de la cadena. Por lo tanto, la entidad jurídica C que vende a la entidad jurídica B, controla el precio. El precio del pedido de ventas de empresas vinculadas se basa en el precio de transferencia o de ventas internas que establezca la entidad jurídica C.

La información de la cabecera del pedido se controla desde el pedido de ventas original al cliente externo. No se sincroniza ningún cambio de los pedidos de empresas vinculadas con el pedido de ventas original.

Se deben seleccionar los siguientes parámetros:

En la entidad jurídica A, en la página **Empresas vinculadas** para proveedores, seleccione **Directivas de pedidos de compra**. Seleccione los siguientes campos en el campo de grupo **Pedido de venta original (entrega directa)**:

- **Imprimir albarán automáticamente**
- **Registrar factura automáticamente**
- **Imprimir factura automáticamente**

En el grupo de campos **Pedido de compra de empresas vinculadas (entrega directa)**, seleccione el siguiente campo:

- **Registrar factura automáticamente**

En el grupo de campos **Pedido de ventas original <-> Pedido de compra de empresas vinculadas**, seleccione los siguientes campos:

- **Información del cliente**
- **Número RMA**

En el grupo de campos **Pedido de compra de empresas vinculadas <-> Pedido de ventas de empresas vinculadas**, seleccione los siguientes campos:

- **Información del cliente**
- **Número RMA**
- **Número de lote**
- **Número de serie**

En la entidad jurídica B, en la página **Empresas vinculadas** para clientes, seleccione **Directivas de pedidos de venta**. Seleccione los siguientes campos en el campo de grupo **Creación de pedido de ventas de empresas vinculadas**:

- **Numeración de pedidos de ventas**: **Empresa + número original**
- **Permitir actualización de resumen de documentos para los clientes originales**

En el grupo de campos **Pedido de ventas de empresas vinculadas \> Pedido de compras de empresas vinculadas**, seleccione los siguientes campos:

- **Número de lote**
- **Número de serie**

En el grupo de campos **Publicación de factura de cliente de empresas vinculadas**, seleccione los siguientes campos:

- **Precio unitario igual a precio de coste**
- **Iniciar el registro de facturas de cliente originales**

En la entidad jurídica B, en la página **Empresas vinculadas** para proveedores, seleccione **Directivas de pedidos de compra**. Seleccione los siguientes campos en el campo de grupo **Pedido de venta original (entrega directa)**:

- **Imprimir albarán automáticamente**
- **Registrar factura automáticamente**
- **Imprimir factura automáticamente**

En el grupo de campos **Pedido de compra de empresas vinculadas (entrega directa)**, seleccione el siguiente campo:

- **Registrar factura automáticamente**

En el grupo de campos **Pedido de ventas original <-> Pedido de compra de empresas vinculadas**, seleccione los siguientes campos:

- **Información del cliente**
- **Número RMA**
- **Precio y descuento**

En el grupo de campos **Pedido de compra de empresas vinculadas <-> Pedido de ventas de empresas vinculadas**, seleccione los siguientes campos:

- **Información del cliente**
- **Número RMA**
- **Número de lote**
- **Número de serie**

En la entidad jurídica C, en la página **Empresas vinculadas** para clientes, seleccione **Directivas de pedidos de venta**. Seleccione los siguientes campos en el campo de grupo **Creación de pedido de ventas de empresas vinculadas**:

- **Numeración de órdenes de venta**: **Código de secuencia numérica**
- **Permitir actualización de resumen de documentos para los clientes originales**

En el grupo de campos **Precios de pedidos de ventas de empresas vinculadas**, seleccione el campo siguiente:

- **Búsqueda de precio y descuento**

En el grupo de campos **Publicación de factura de cliente de empresas vinculadas**, seleccione los siguientes campos:

- **Precio unitario igual a precio de coste**
- **Iniciar el registro de facturas de cliente originales**

En el grupo de campos **Pedido de ventas de empresas vinculadas <-> Pedido de compras de empresas vinculadas**, seleccione los siguientes campos:

- **Número de lote**
- **Número de serie**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
