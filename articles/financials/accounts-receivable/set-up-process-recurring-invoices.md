---
title: "Configurar y procesar facturas periódicas"
description: "Este artículo explica cómo configurar y procesar las facturas periódicas. Puede usar facturas periódicas si debe factura a los clientes por el mismo importe periódicamente."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5c5fbe1791161b8d06cd1539b1717ba8690a8e05
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-and-process-recurring-invoices"></a>Configurar y procesar facturas periódicas

[!INCLUDE [banner](../includes/banner.md)]

Este artículo explica cómo configurar y procesar las facturas periódicas. Puede usar facturas periódicas si debe factura a los clientes por el mismo importe periódicamente.

<a name="create-a-recurring-free-text-invoice-template"></a>Crear una plantilla de factura de servicios recurrente
---------------------------------------------

Para facturar a los clientes por los mismos servicios periódicamente, debe definir una plantilla de factura de servicios que se puede volver a usar para crear las facturas. Esta plantilla contiene la siguiente información:

-   Información de encabezado, como grupos de impuestos, condiciones de pago y el método de pago
-   Información de línea, como la descripción del servicio, las cuentas de ingresos, el precio unitario y el importe de la factura
-   Gastos de envío o gestión
-   Distribuciones contables junto con la información de dimensión financiera, como centros de costes y unidades de negocio

De hecho, crea una factura completa y la guarda como plantilla. Puede configurar las plantillas con la página **Facturas periódicas**.

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a>Asignar una plantilla de factura de servicios a un cliente y especificar los detalles de periodicidad
Después de crear la plantilla, debe asignar la plantilla a los clientes que desea facturar. Además, debe especificar cuándo y con qué frecuencia se usará la factura. Puede asignar las plantillas en la pestaña **Factura** de la página **Clientes**. Agregue la plantilla a la lista y actualizar la siguiente información:

-   La fecha inicial y, opcionalmente, la fecha final de la facturación periódica
-   La frecuencia de facturación periódica (por ejemplo, cada día o una vez al mes)
-   El importe de facturación máximo (si se requiere esta información)

Un cliente puede tener varias plantillas con diferentes frecuencias.

## <a name="generate-the-recurring-invoices"></a>Generar las facturas periódicas
En la página **Facturas periódicas**, hay una tarea que procesa las plantillas de facturas periódicas. Especifique la fecha de la factura y la plantilla desde la que desea generar las facturas. Las facturas se generarán y se le asignarán un número de id. de periodicidad único para cada grupo de facturas que se procese.
Registrar facturas de servicios periódicas
---------------------------------

Después de que se generen las facturas periódicas, los identificadores de periodicidad de factura aparecen en una tarea de registro en la página **Facturas periódicas**. Para ver todas las facturas para un id. de periodicidad, haga clic en el vínculo. Durante su revisión de las facturas para el id. de periodicidad, puede eliminar facturas individuales. La configuración de la periodicidad del cliente se restablecerá para esa plantilla, para que se pueda volver a generar posteriormente. Puede registrar una, muchas o todas las facturas para un id. de periodicidad. Si se habilitan los flujos de trabajo, debe hacer clic en **Enviar** para poder registrar las facturas.
Imprimir facturas de servicios periódicas
----------------------------------

Después de registrar las facturas periódicas, puede imprimir las facturas desde la página de lista de facturas de servicios. Puede imprimir las facturas seleccionadas o puede seleccionar un intervalo de facturas para imprimirlas.




