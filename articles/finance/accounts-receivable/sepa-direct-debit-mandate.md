---
title: Configurar orden de domiciliación bancaria SEPA
description: Una domiciliación bancaria SEPA (Zona Única de Pagos en Euros) permite a un acreedor cobrar fondos de la cuenta bancaria de un cliente, siempre y cuando el cliente haya firmado una orden y se la haya entregado al acreedor.
author: ShivamPandey-msft
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0bea974750a6ac62d8ddeea5d9d4457f4846cb79
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891649"
---
# <a name="set-up-sepa-direct-debit-mandate"></a>Configurar orden de domiciliación bancaria SEPA

[!include [banner](../includes/banner.md)]

Una domiciliación bancaria SEPA (Zona Única de Pagos en Euros) permite a un acreedor cobrar fondos de la cuenta bancaria de un cliente, siempre y cuando el cliente haya firmado una orden y se la haya entregado al acreedor. La orden que el cliente firma autoriza el acreedor a cobrar un pago y da instrucciones al banco del cliente para pagar el cobro. Este artículo está organizado para mostrar el proceso de configuración de órdenes de domiciliación bancaria SEPA.

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

Recursos adicionales

[Visión general de las domiciliaciones SEPA](sepa-direct-debit-overview.md) 

[Crear una orden de domiciliación bancaria para un cliente](tasks/create-direct-debit-mandate-customer.md) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
