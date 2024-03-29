---
title: Asignar una plantilla de factura de servicios a un cliente
description: Esta tarea muestra cómo asignar una plantilla de factura de texto libre a un cliente.
author: ShivamPandey-msft
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49074c11659ae30fd2decdb93b4721441edff2c5
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780585"
---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Asignar una plantilla de factura de servicios a un cliente

[!include [banner](../../includes/banner.md)]

Esta tarea muestra cómo asignar una plantilla de factura de texto libre a un cliente. Esta tarea utiliza la empresa de demostración USMF y se va a utilizar para el usuario responsable de gestionar y de procesar facturas de cuentas por cobrar.

1. En el **Panel de exploración**, vaya a **Módulos > Clientes > Clientes > Todos los clientes**.
2. En la lista, busque y seleccione el registro deseado.
3. En el **panel de acciones**, haga clic en **Factura**.
4. Haga clic en **Facturas periódicas**. Use esta página para asignar plantillas de factura de texto libre a clientes y especificar la frecuencia con la que se enviarán facturas al cliente.  
5. Haga clic en **Nuevo** para asignar una plantilla nueva al cliente.
6. En el campo **Plantilla**, seleccione la plantilla de la factura de texto libre que desee asignar al cliente.
7. En la lista, busque y seleccione el registro deseado.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. En el campo **Fecha de inicio de la facturación**, especifique la fecha en que se generará la primera factura.
10. En la sección **Fin de periodicidad**, especifique una fecha final recurrente.  
    Seleccione una de las opciones siguientes: 
    - **No hay fecha final**: las facturas se generarán de manera indefinida hasta que se elimine la plantilla de la cuenta del cliente.
    - **Fecha de finalización de la facturación**: seleccione esta opción y escriba la última fecha en la que se puede generar la factura.  
11. En el campo **Importe acumulativo máximo**, especifique el importe acumulado máximo tras el que la generación de facturas se detendrá. Especifique el importe acumulado máximo que se puede alcanzar mediante la plantilla seleccionada. Por ejemplo, si especifica 1.000,00 y genera facturas mensuales por 100,00 cada una, la generación de facturas se detendrá al generarse la décima factura.  
12. En la sección **Generar facturas periódicas mediante los valores predeterminados**, seleccione la plantilla de factura de texto libre o la cuenta de cliente. Seleccione si se debe usar la plantilla de factura de servicios o la cuenta de cliente para determinar los valores predeterminados del idioma, el perfil de contabilización, el grupo de impuestos, el grupo de impuestos de artículos, el código de lista, el país o región de la entrega, la divisa, las condiciones de pago, la forma de pago, la especificación del pago, la programación del pago, el descuento por pronto pago, las dimensiones financieras y el resguardo de la transferencia del giro bancario cuando se crean las facturas.  
13. En el campo **Patrón de periodicidad**, seleccione el patrón de repetición.
    - **Diariamente**: seleccione esta opción y especifique el número de días en el campo Por. Por ejemplo, si escribe 15, se generará una factura cada 15 días para este cliente.
    - **Semanal**: seleccione esta opción y especifique el número de semanas en el campo Por. Por ejemplo, si escribe 2, se generará una factura cada dos semanas para este cliente.
    - **Mensual**: seleccione esta opción y especifique el número de meses en el campo Por. Por ejemplo, si escribe 6, se generará una factura cada seis meses para este cliente.
    - **Anual**: seleccione esta opción y especifique el número de años en el campo Por. Por ejemplo, si escribe 2, se generará una factura cada dos años para este cliente.  
14. En el campo **Por**, especifique un número.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
