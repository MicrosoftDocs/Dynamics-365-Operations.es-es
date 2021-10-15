---
title: Acumulación de costes de proyectos en recibos de compra
description: Este tema describe cómo los costes de proyecto acumulados de recibos de compra se pueden controlar en Microsoft Dynamics 365 Finance.
author: sunfzam
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: roschlom
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7ae2f57e0104a30492363f1576962d36a2a1b04b
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2021
ms.locfileid: "7595239"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a>Acumulación de costes de proyectos en recibos de compra

[!include [banner](../includes/banner.md)]

Este tema describe cómo los costes de proyecto acumulados de recibos de compra se pueden controlar en Microsoft Dynamics 365 Finance. 

Las facturas para un proyecto suelen llegar después de prestar los bienes y servicios, lo cual puede tener un impacto significativo impacto en los indicadores de rendimiento clave (KPI) del proyecto. Es importante poder controlar estas transacciones mediante informes financieros y del proyecto.

En el siguiente supuesto de ejemplo se muestra esto. 

Contoso Consulting ha iniciado un nuevo proyecto de implementación en la nube. Se crea un pedido de compra para comprar un equipo para el proyecto. El equipo costará 1500 $ y los servicios de instalación costarán 150 $. El proveedor ha entregado e instalado el equipo, pero Contoso Consulting aún no ha recibido la factura. El director del proyecto desea ver la acumulación de costes de proyecto de 1650 $ antes de que se entregue la factura. Este coste también se debe reflejar en los informes financieros de final de mes de la empresa. 

El coste acumulado tiene que registrarse en el nivel financiero y en el nivel del proyecto a efectos de notificación. La actualización financiera de la recepción del producto se puede controlar para las categorías de artículo y compras. 

Para los artículos, en la página **Parámetros de proveedores**, seleccione la opción **Publicar recepciones de producto en la contabilidad**.
[![Página de parámetros de proveedores.](./media/accruals1-1024x409.png)](./media/accruals1.png) 

Para las categorías de compras, en la página **Regla de directivas de categorías**, seleccione Directivas de **compra** y luego seleccione **Acumular gasto de compra en recepción** para cada categoría de compras.
[![Página Regla de directivas de categorías.](./media/accruals2-1024x569.png)](./media/accruals2.png) 

Las cuentas **Gasto de compra no facturado** y **Acumulación de compras** en **Configuración del registro** se utilizarán cuando se registren los asientos relacionados con la recepción de producto.

Con esta mismo escenario, vea cómo el registro de una recepción de producto afectará a la contabilidad general y la información del proyecto. 

**Paso 1:** Crear y confirmar un nuevo pedido de compra para el proyecto para registrar la compra de un equipo de 1500 $ y de unos servicios de instalación de 150 $.
[![Crear un pedido de compra nuevo.](./media/accruals4-1024x497.png)](./media/accruals4.png) 

Cuando se confirma el pedido de compra, se crean las transacciones para el gasto comprometido para el proyecto. 
[![Transacciones creadas.](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> Las transacciones para el gasto comprometido tendrán el campo **Origen de transacción** establecido en **Pedido de compra**. La creación y confirmación de un pedido de compra no crea transacciones para un proyecto. 

**Paso 2:** Se registran los bienes y servicios entregados y una recepción de producto. 

El registro de una recepción de producto generará y registrará un asiento en la contabilidad. El asiento cargará los gastos de compra, la cuenta no facturada y la cuenta de acumulación de abono de compras. 
[![Transacciones de asiento.](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> El registro de una recepción de producto utilizará la configuración de registro para las categorías de compras y productos, y no la configuración de registro para las categorías de proyecto. Para reflejar correctamente el impacto financiero de las acumulaciones de compras, esta configuración tiene que estar alineada. 

Es posible asignar categorías de compras a las categorías de proyecto en la página **Categoría de compras**.
[![Página de categoría de compras.](./media/accruals7-1024x390.png)](./media/accruals7.png)

**Paso 3:** Crear un borrador de factura de proveedor 

Registrar un recibo de producto no afecta a la información del proyecto. Como solución alternativa, podría generar un borrador de factura de proveedor justo después de registrar la recepción de compra. Vaya a la página **Pedido de compra** &gt; **ficha Factura** &gt; **Generar** &gt; **Factura**. Esto crea un documento de factura pendiente que actualiza la información de proyecto. 

Crear un borrador de factura de proveedor generará transacción de proyectos pendientes. 
[![Transacciones de proyecto pendientes.](./media/accruals8-1024x225.png)](./media/accruals8.png) 

En la página **Gasto comprometido**, los registros creados en el paso 1 se cerrarán y se crearán nuevos registros para reflejar el compromiso de coste procedente de la factura de proveedor pendiente. El campo **Origen de transacción** para el gasto comprometido se enviará a **Factura de proveedor**.
[![Página de gastos comprometidos.](./media/accruals9-1024x200.png)](./media/accruals9.png)

La factura de proveedor seguirá en estado de pendiente hasta que llegue la factura de proveedor real.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
