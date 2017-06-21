---
title: Informe de resguardo de pago para Europa
description: "Este tema proporciona información sobre los informes de resguardo de pago para Europa."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 264604
ms.search.region: Belgium, Denmark, Finland, Norway, Switzerland
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: e3fcef720fb38de45ed357e53c1ec6923f72fd63
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="payment-slip-report-for-europe"></a>Informe de resguardo de pago para Europa

[!include[banner](../includes/banner.md)]


Este tema proporciona información sobre los informes de resguardo de pago para Europa.

La funcionalidad de los informes de resguardo de pago está disponible para entidades jurídicas que tengan su domicilio principal en Dinamarca, Bélgica, Noruega, Suiza o Finlandia. Las empresas suelen adjuntar resguardos de pago impresos a las facturas para proporcionar una referencia de pago para su registro y liquidación. El resguardo de pago se puede usar para facturas de proyecto o texto sin formato, cartas de cobro, notas de interés y extractos de cuenta, además de las facturas de ventas y facturas de servicios.

## <a name="set-up-a-creditor-id-number-denmark-only"></a>Configuración de un número de id. de acreedor (solo en Dinamarca)
Siga estos pasos para introducir el número de identificación de acreedor (ID) de su empresa. Este número lo proporciona su institución financiera. Se usa como referencia al recibir pagos de cliente mediante instituciones financieras.

1.  Haga clic en **Administración de la organización** &gt; **Configuración** &gt; **Organización** &gt; **Entidades jurídicas**.
2.  En la ficha desplegable **Información de cuenta bancaria**, en el campo **Id. de acreedor FI**, introduzca su número de ID acreedor exclusivo de ocho dígitos.
3.  Cierre el formulario para guardar los cambios.

## <a name="set-up-a-payment-slip-attachment-format-for-invoices-interest-notes-collection-letters-and-account-statements"></a>Configuración de un formato adjunto de resguardo de pago para facturas, notas de interés, cartas de cobro y extractos de cuenta
Siga estos pasos para configurar el formato de un adjunto de resguardo de pago que acompañe a las facturas de venta, facturas de texto sin formato, notas de interés, cartas de cobro y extractos de cuenta.

1.  Haga clic en **Clientes** &gt; **Configuración** &gt; **Formularios** &gt; **Configuración de formulario**.
2.  Haga clic en la ficha **Factura** y, en el campo **Pago asociado adjunto en la factura de cliente**, seleccione el formato de archivo adjunto de resguardo de pago.
3.  En las fichas **Factura de texto sin formato**, **Nota de interés**, **Carta de cobro** y **Extracto de cuenta**, seleccione un formato de adjunto de resguardo para cada tipo de documento.
4.  Cierre el formulario para guardar los cambios.

Siga estos pasos para configurar un formato para adjuntos de resguardos de pago que acompañan a las facturas del proyecto.

1.  Haga clic en **Gestión de proyectos y contabilidad** &gt; **Configuración** &gt; **Formularios** &gt; **Configuración de formulario**.
2.  En el campo **Pago asociado adjunto**, seleccione el formato del adjunto de resguardo de pago.

## <a name="assign-a-payment-slip-attachment-format-to-a-customer-account"></a>Asignar un formato de adjunto de resguardo de pago a una cuenta de cliente
Después de configurar el formato de adjuntos de resguardo de pago para las facturas de venta, facturas de texto sin formato, notas de interés, cartas de cobro, extractos de cuenta y facturas de proyectos, puede asignar formatos específicos para un cliente seleccionado.

1.  Haga clic en **Clientes** &gt; **Común** &gt; **Clientes** &gt; **Todos los clientes**.
2.  Cree un nuevo cliente o seleccione uno existente.
3.  En la ficha desplegable **Factura y entrega**, en los campos **En factura del cliente**, **En una factora de texto sin formato**, **En una nota de interés**, **En una carta de cobro**, **En una factura de proyecto** y **En un extracto de cuenta**, seleccione el formato para los adjuntos de resguardo de pago que acompañarán a los documentos de cada tipo que se envíen al cliente seleccionado.
4.  Cierre el formulario para guardar los cambios.





