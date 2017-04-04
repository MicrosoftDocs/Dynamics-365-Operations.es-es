---
title: "Acumulación de coste de proyecto en recepciones de compra"
description: "Este tema describe cómo los costes de proyecto acumulan de recepciones de compra se pueden seguir en Microsoft Dynamics 365 para las operaciones."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 27a0a71095dce46c0119b32a92f8c4dce0f42e43
ms.lasthandoff: 03/31/2017


---

# <a name="project-cost-accrual-on-purchase-receipts"></a>Acumulación de coste de proyecto en recepciones de compra

Este tema describe cómo los costes de proyecto acumulan de recepciones de compra se pueden seguir en Microsoft Dynamics 365 para las operaciones. 

Las facturas para un proyecto se convierten a menudo más adelante que se entregan los bienes y servicios, que pueden tener un significativo impacto en los indicadores clave de rendimiento (KPIs) del proyecto. A importante poder realizar estas transacciones financieras y en informes de proyecto.

La escenario siguiente ejemplo muestra de este. 

Asesoría de Contoso ha iniciado un nuevo proyecto de implementación de la nube. Se creará un pedido de compra de comprar un equipo para el proyecto. El equipo costará $1500 y servicios desde la instalación costarán $150. El proveedor ha entregado y ha instalado el equipo, pero la factura aún no ha alcanzado consultar de Contoso. El director de proyecto desea ver la acumulación de coste de proyecto de $1650 antes de la factura que obtenga entregado. Este coste también se debe reflejarse en los informes financieros de final de mes de la empresa. 

El coste acumulado es necesario registrar en el nivel financiero y el nivel de proyecto a efectos de notificación. En Dynamics 365 para las operaciones, la actualización financiera de la recepción de producto se puede seguir para el artículo y las categorías de compras. 

Para los artículos, ** en los parámetros de proveedores ** la página, seleccione ** Enviar recepciones de producto en la contabilidad ** la opción.
![accruals1 [] (. /media/accruals1-1024x409.png])(. /media/accruals1.png) 

Para las categorías de compras, en ** regla de directivas de categoría ** la página, ** comprando ** directivas seleccionar y, a continuación ** acumula los gastos de compra en Recepción ** para cada categoría de compras.
![accruals2 [] (. /media/accruals2-1024x569.png])(. /media/accruals2.png) 

** Gastos de la compra no facturados y ** ** acumulación de compras ** las cuentas en ** configuración de registro ** se usarán cuando se registran los asientos relacionados con la recepción de producto.
![accruals3 [] (. /media/accruals3-1024x429.png])(. /media/accruals3.png) 

Con esta misma situación, consulte déjenos cómo registrar una recepción de producto impactará la contabilidad general y la información de proyecto. 

** Paso 1: ** Cree y confirme un nuevo pedido de compra del proyecto registrar la compra de un equipo para $1500 y los servicios de la instalación para $150.
![accruals4 [] (. /media/accruals4-1024x497.png])(. /media/accruals4.png) 

Cuando se confirma el pedido de compra, las transacciones para el gasto comprometido se crean para el proyecto. 
![accruals5 [] (. /media/accruals5-1024x219.png])(. /media/accruals5.png) 

> [!NOTE]
> Las transacciones para el gasto comprometido tendrán ** origen de la transacción ** el conjunto de campos ** pedido de compra **. Creación y confirmando un pedido de compra no crea transacciones para un proyecto. 

** Paso 2: ** Los bienes y servicios obtienen entregado y se registra una recepción de producto. 

Enviar una recepción de producto generará y registrará un asiento en la contabilidad. El asiento cargará los gastos de compra, la cuenta no facturada, y la cuenta de acumulación de compras de crédito. 
![accruals6 [] (. /media/accruals6-1024x214.png])(. /media/accruals6.png)

> [!NOTE]
> Enviando una recepción de producto utilizará la configuración de registro para las categorías de compras y productos, y no la configuración de registro para las categorías de proyecto. Para correctamente reflejar el impacto financiero de las provisiones de la compra, esta configuración es necesario alineada. 

Es posible asignar categorías de compras a las categorías de proyecto en ** categoría de compras ** la página.
![accruals7 [] (. /media/accruals7-1024x390.png])(. /media/accruals7.png)

** Paso 3: ** Crear una factura de proveedor de borrador. 

En Dynamics 365 para las operaciones, registrar una recepción de producto no afecta a la información del proyecto. Como solución alternativa, podría generar una factura de proveedor de borrador FLSA después de registrar la recepción de compra. Ir ** pedido de compra ** a la página &gt; ** ficha Factura ** &gt; ** generan ** &gt; ** ** factura. Esto crea un documento de factura pendiente actualizar la información de proyecto. 

Crear una factura de proveedor de borrador generará pendientes transacciones de proyecto. 
![accruals8 [] (. /media/accruals8-1024x225.png])(. /media/accruals8.png) 

En ** gasto comprometido ** la página, los registros creados en el paso 1 serán cerrados y los nuevos registros se crearán para reflejar el compromiso de coste que proceden de la factura de proveedor pendientes. ** Origen de la transacción ** el campo para el gasto comprometido se establecerá ** factura de proveedor **.
![accruals9 [] (. /media/accruals9-1024x200.png])(. /media/accruals9.png)

Seguirá mantiene la factura de proveedor con estado pendiente hasta que llegue la factura de proveedor real.


