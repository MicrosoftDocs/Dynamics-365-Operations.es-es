---
title: "Configurar un orden de domiciliación de débito directo SEPA"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: bb835f8dad16938b56365c7b06d4a0228f9aba66
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-sepa-direct-debit-mandate"></a>Configurar un orden de domiciliación de débito directo SEPA



Una domiciliación bancaria SEPA (Zona Única de Pagos en Euros) permite a un acreedor cobrar fondos de la cuenta bancaria de un cliente, siempre y cuando el cliente haya firmado una orden y se la haya entregado al acreedor. La orden que el cliente firma autoriza el acreedor a cobrar un pago y da instrucciones al banco del cliente para pagar el cobro. Este tema se organiza para mostrar el proceso para realizar pedidos de débito directo de SEPA.

## <a name="prerequisites"></a>Requisitos previos
La tabla siguiente muestra los requisitos previos que deben cumplirse antes de comenzar.

| Categoría       | Requisito previo                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| País o región | La dirección principal de la entidad jurídica debe estar en los países/regiones siguientes: Alemania, Austria, Bélgica, España, Francia, Italia o los Países Bajos. |

1. Configurar una secuencia numérica para los pedidos de débito directo que cada pedido de débito directo debe tener un número único. Use la página **Secuencias numéricas** para crear una secuencia numérica para las órdenes de domiciliación. Usará este identificador para asignar la secuencia numérica en el sistema de órdenes de domiciliación en la página **Parámetros de clientes**.

2. Los parámetros de clientes para los pedidos de débito directo ** usan los parámetros de clientes ** la página para configurar los parámetros para los pedidos de débito directo. Para configurar los parámetros, en ** débito directo ** la ficha, cambie los parámetros predeterminados como sea necesario. A continuación, en ** las secuencias numéricas ** la ficha, actualice ** identificador de la orden de débito directo ** le campo con la secuencia numérica a dicha configuración anterior.

3. Configure una forma de pago para los pedidos de débito directo que debe configurar un método de pago para los pedidos de débito directo. Este método de pago se usa para realizar consultas de facturas para las que desee generar pagos por domiciliación. Use la página **Formas de pago** para configurar el método de pago. Para configurar un método de pago para las órdenes de domiciliación bancaria, debe seguir estos pasos adicionales para un método de pago:

-   En el campo **Tipo de pago**, seleccione **Pago electrónico**.
-   Opcional: Si no espera que cada uno de sus clientes tenga varios pedidos, en ** período ** campo, seleccione ** ** factura. Un pago independiente se creará para cada factura, y cada pago utilizará el orden que se especifica para la factura.
-   Seleccione la opción **Requerir orden** para crear pagos con órdenes de domiciliación bancaria. La opción **Requerir orden** solo está disponible si selecciona **Pago electrónico** en el campo **Tipo de pago**.

Consulte también la [] visión general de débito directo (sepa-direct-debit-overview.md) 

