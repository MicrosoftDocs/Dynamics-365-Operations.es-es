---
title: "Conciliación de facturas y pedidos de compra de empresas vinculadas"
description: "La entidad jurídica de compra que está involucrada en una transacción de negocios entre empresas vinculadas puede estar configurada para usar la conciliación de facturas de proveedores. En este caso, los requisitos de registro para el negocio entre empresas vinculadas y la conciliación de facturas de proveedores deben ser cumplidos antes de que las facturas de proveedor de empresas vinculadas se puedan registrar."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchLineMatchingPolicy
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3101
ms.assetid: 9c7c2e44-45f8-4325-b6de-a09fe790f9cf
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 45d0b24ed0a79176803a6efefc216f7e30fec86c
ms.lasthandoff: 03/31/2017


---

# <a name="invoice-matching-and-intercompany-purchase-orders"></a>Conciliación de facturas y pedidos de compra de empresas vinculadas

[!include[banner](../includes/banner.md)]


La entidad jurídica de compra que está involucrada en una transacción de negocios entre empresas vinculadas puede estar configurada para usar la conciliación de facturas de proveedores. En este caso, los requisitos de registro para el negocio entre empresas vinculadas y la conciliación de facturas de proveedores deben ser cumplidos antes de que las facturas de proveedor de empresas vinculadas se puedan registrar.

Los ejemplos de este tema usan la configuración siguiente para el negocio entre empresas vinculadas:
-   Fabrikam Purchase es la entidad jurídica de compra.
-   Fabrikam Sales es la entidad jurídica vendedora.
-   El cliente 4020 pertenece a la empresa Fabrikam Ventas.
-   El proveedor 3024 pertenece a la empresa Fabrikam Compras.
-   En Fabrikam Purchase, la información de empresas vinculadas se especifica para el proveedor 3024. Fabrikam Sales se especifica como la empresa del cliente, y se especifica el cliente 4020 como la cuenta de cliente que corresponde a la entidad jurídica de Fabrikam Purchase.
-   En Fabrikam Sales, la información de empresas vinculadas se especifica para el cliente 4020. Fabrikam Sales se especifica como la empresa del proveedor, y se especifica el cliente 3024 como la cuenta de proveedor que corresponde a la entidad jurídica de Fabrikam Sales.

En los ejemplos que se muestran a continuación se utiliza la siguiente configuración de conciliación de facturas de proveedores para Fabrikam Purchase:
-   En la página Parámetros de proveedores, la opción Habilitar validación de conciliación de facturas está seleccionada.
-   En la página Parámetros de proveedores, la opción Registrar factura con discrepancias está establecida en Requerir aprobación.
-   El porcentaje de tolerancia de precio para la entidad jurídica es 2 por ciento.

## <a name="example-price-matching-and-intercompany-trade"></a>Ejemplo: la conciliación de precio y el negocio entre empresas vinculadas
Los importes netos para la factura de proveedor de empresas vinculadas y la factura de cliente de empresa vinculada deben ser iguales. Este requisito anula la aprobación de conciliación de facturas o los porcentajes de tolerancia de precios aplicables. Por ejemplo, puede seguir estos pasos.
1.  En Fabrikam Purchase, crea el pedido de ventas SO888 del cliente 4020. Se crea automáticamente el pedido de compra ICPO222 de empresas vinculadas para el proveedor 3024 en Fabrikam Purchase y el pedido de ventas ICSO888 en Fabrikam Sales.
2.  En Fabrikan Sales, registra la recepción de artículos y el albarán. El estado de ICSO888 cambia a Entregado. El estado de ICPO222 cambia a Recibido.
3.  En Fabrikan Sales, actualiza una factura para ICSO888. El precio unitario es 0,45, y se actualizan 100 artículos.
4.  Crea una factura para ICPO222 en Fabrikam Purchase. Modifica el precio unitario accidentalmente de 45,00 a 54,00. Se muestra un icono que indica que el precio excede la tolerancia de precio permitida de 2 por ciento.
5.  En la página Detalles de coincidencia de factura, seleccione la opción para aprobar el registro con discrepancias de conciliación. En la página Factura de proveedor, haga clic en Aceptar. Si la factura de proveedor no era una factura de proveedor de empresas vinculadas, el registro se realizará correctamente. Sin embargo, dado que está trabajando con una factura de proveedor de empresas vinculadas, el registro no se finaliza correctamente. Para el negocio entre empresas vinculadas, los totales de la factura del pedido de ventas de empresas vinculadas deben ser iguales a los totales de la factura del pedido de compra de empresas vinculadas correspondiente. Para solucionar este problema, debe corregir el precio neto de la factura cambiando el precio neto de nuevo al importe predeterminado, 45,00.

## <a name="example-quantity-matching-with-intercompany-trade"></a>Ejemplo: conciliación de cantidades con negocio entre empresas vinculadas
Las cantidades de los pedidos de compra y los pedidos de ventas de empresas vinculadas deben ser equivalentes. Este requisito anula la aprobación aplicable a la conciliación de facturas. En el ejemplo que se muestra a continuación se utiliza la siguiente configuración adicional para negocios de empresas vinculadas:
-   En Fabrikam Purchase, la directiva de acción del pedido de compra para el proveedor 3024 se configura para registrar automáticamente la factura de cliente original y la factura de proveedor de empresas vinculadas.

En el ejemplo que se muestra a continuación se utiliza la siguiente configuración adicional de conciliación de facturas de proveedores para Fabrikam Purchase:
-   En la página Grupos de modelos de artículo para el grupo de modelos utilizado por el artículo B-R14, la opción Recepción de requisitos está seleccionada.
-   La cantidad disponible del artículo B-R14 es 0.

Por ejemplo, puede seguir estos pasos.
1.  En Fabrikam Purchase, cree el pedido de ventas SO999 del cliente 4020. El orden contiene un artículo de línea: 100 baterías (artículo B-R14) a un precio unitario de 1,00 por cada uno. Se crea automáticamente el pedido de compra ICPO333 de empresas vinculadas para el proveedor 3024 en Fabrikam Purchase y el pedido de ventas ICSO999 en Fabrikam Sales.
2.  En Fabrikan Sales, actualiza una factura para ICSO999. El registro no se finaliza correctamente, ya que el artículo no se encuentra en existencias y todavía no se ha recibido. Por lo tanto, la Información financiera no puede actualizarse.
3.  Registra la recepción de artículos y el albarán de ICSO999 en Fabrikam Sales. Una recepción de producto para ICPO333 se registra automáticamente en Fabrikam Purchase. La cantidad recibida del artículo B-R14 en Fabrikam Purchase cambia a 100.
4.  En Fabrikan Sales, actualiza una factura para ICSO999. El registro se realiza correctamente en ambas entidades jurídicas. La cantidad adquirida del artículo B-R14 en Fabrikam Purchase cambia a 100.






