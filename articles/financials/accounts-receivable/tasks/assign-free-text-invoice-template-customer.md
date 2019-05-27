---
title: Asignación de una plantilla de factura de texto libre a un cliente
description: Esta tarea muestra cómo asignar una plantilla de factura de texto libre a un cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 317b3bd4c1f395987ef3dbbd268c40be5c688320
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568992"
---
# <a name="assign-free-text-invoice-template-to-a-customer"></a>Asignación de una plantilla de factura de texto libre a un cliente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta tarea muestra cómo asignar una plantilla de factura de texto libre a un cliente. Esta tarea utiliza la empresa de demostración USMF y se va a utilizar para el usuario responsable de gestionar y de procesar facturas de cuentas por cobrar.

1. Vaya a Clientes > Clientes > Todos los clientes.
2. En la lista, busque y seleccione el registro deseado.
3. En el panel de acciones, haga clic en Factura.
4. Haga clic en Facturas periódicas.
    * Use esta página para asignar plantillas de factura de texto libre a clientes y especificar la frecuencia con la que se enviarán facturas al cliente.  
5. Haga clic en Nuevo para asignar una plantilla nueva al cliente.
6. Seleccione la plantilla de factura de texto libre que desee asignar al cliente.
7. En la lista, busque y seleccione el registro deseado.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. Escriba la fecha en que se generará la primera factura.
    * Especifique una fecha final periódica.  
    * Seleccione alguna de las siguientes opciones: No hay fecha final: las facturas se generarán de manera indefinida hasta que se elimine la plantilla de la cuenta del cliente.  Fecha de finalización de la facturación: seleccione esta opción y escriba la última fecha en la que se puede generar la factura.  
    * El importe acumulativo máximo tras el cual dejarán de generarse facturas.  
    * Especifique el importe acumulado máximo que se puede alcanzar mediante la plantilla seleccionada. Por ejemplo, si especifica 1.000,00 y genera facturas mensuales por 100,00 cada una, la generación de facturas se detendrá al generarse la décima factura.  
    * Genere facturas periódicas mediante los valores predeterminados de la plantilla de factura de texto libre o la cuenta de cliente.  
    * Seleccione si se debe usar la plantilla de factura de servicios o la cuenta de cliente para determinar los valores predeterminados del idioma, el perfil de contabilización, el grupo de impuestos, el grupo de impuestos de artículos, el código de lista, el país o región de la entrega, la divisa, las condiciones de pago, la forma de pago, la especificación del pago, la programación del pago, el descuento por pronto pago, las dimensiones financieras y el resguardo de la transferencia del giro bancario cuando se crean las facturas.  
10. Seleccione el patrón de repetición.
    * Diariamente: seleccione esta opción y especifique el número de días en el campo Por. Por ejemplo, si escribe 15, se generará una factura cada 15 días para este cliente.  Semanal: seleccione esta opción y especifique el número de semanas en el campo Por. Por ejemplo, si escribe 2, se generará una factura cada dos semanas para este cliente.  Mensual: seleccione esta opción y especifique el número de meses en el campo Por. Por ejemplo, si escribe 6, se generará una factura cada seis meses para este cliente.  Anual: seleccione esta opción y especifique el número de años en el campo Por. Por ejemplo, si escribe 2, se generará una factura cada dos años para este cliente.  
11. En el campo Por, especifique un número.

