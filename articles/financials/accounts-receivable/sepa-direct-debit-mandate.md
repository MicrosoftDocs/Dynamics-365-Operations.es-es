---
title: "Configurar un orden de domiciliación de débito directo SEPA"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8b50c2d585c7e0bcd8dc15aa70446cd7346ad33c
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-sepa-direct-debit-mandate"></a>Configurar un orden de domiciliación de débito directo SEPA

[!include[banner](../includes/banner.md)]




Una domiciliación bancaria SEPA (Zona Única de Pagos en Euros) permite a un acreedor cobrar fondos de la cuenta bancaria de un cliente, siempre y cuando el cliente haya firmado una orden y se la haya entregado al acreedor. La orden que el cliente firma autoriza el acreedor a cobrar un pago y da instrucciones al banco del cliente para pagar el cobro. Este tema está organizado para mostrar el proceso de configuración de órdenes de domiciliación bancaria SEPA.

## <a name="prerequisites"></a>Requisitos previos
La tabla siguiente muestra los requisitos previos que deben cumplirse antes de comenzar.

| Categoría       | Requisito previo                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| País o región | La dirección principal de la entidad jurídica debe estar en los países/regiones siguientes: Alemania, Austria, Bélgica, España, Francia, Italia o los Países Bajos. |

1. Configure una secuencia numérica para las órdenes de domiciliación bancaria. Cada orden de domiciliación bancaria debe tener un número único. Use la página **Secuencias numéricas** para crear una secuencia numérica para las órdenes de domiciliación. Usará este identificador para asignar la secuencia numérica en el sistema de órdenes de domiciliación en la página **Parámetros de clientes**.

2. Configurar los parámetros de clientes para las órdenes de domiciliación. Use la página **Parámetros de clientes** para configurar los parámetros para los pedidos de débito directo. Para configurar los parámetros, en la pestaña **Domiciliación bancaria**, cambie los parámetros predeterminados como sea necesario. A continuación, en la pestaña **Secuencias numéricas**, actualice el campo **Id. de orden de domiciliación bancaria** con la secuencia numérica configurada anteriormente.

3. Configurar un método de pago para las órdenes de domiciliación. Debe configurar un método de pago para las órdenes de domiciliación. Este método de pago se usa para realizar consultas de facturas para las que desee generar pagos por domiciliación. Use la página **Formas de pago** para configurar el método de pago. Para configurar un método de pago para las órdenes de domiciliación bancaria, debe seguir estos pasos adicionales para un método de pago:

-   En el campo **Tipo de pago**, seleccione **Pago electrónico**.
-   Opcional: si espera que cada uno de los clientes tenga varias órdenes, en el campo **Período**, seleccione **Factura**. Se crea un pago independiente para cada factura y cada pago usa la orden que se especifica para la factura.
-   Seleccione la opción **Requerir orden** para crear pagos con órdenes de domiciliación bancaria. La opción **Requerir orden** solo está disponible si selecciona **Pago electrónico** en el campo **Tipo de pago**.

Ver también

[Resumen de domiciliación bancaria](sepa-direct-debit-overview.md) 

[Crear una orden de domiciliación bancaria para un cliente](tasks/create-direct-debit-mandate-customer.md) 


