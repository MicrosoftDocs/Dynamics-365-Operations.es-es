---
title: Informe de resguardo de pago para Europa
description: "Este tema proporciona información sobre los informes de resguardo de pago para Europa."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264604
ms.assetid: 551e047b-4581-4a77-b470-c4f8d395c375
ms.search.region: Belgium, Denmark, Finland, Norway, Switzerland
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: c795466753ca1515790b7961b989aac6e7d63c2c
ms.lasthandoff: 03/31/2017


---

# <a name="payment-slip-report-for-europe"></a>Informe de resguardo de pago para Europa

Este tema proporciona información sobre los informes de resguardo de pago para Europa.

La funcionalidad para informes de resguardo de pago disponible para las entidades jurídicas que tengan su dirección principal en Dinamarca, Bélgica, Noruega, o Suiza Finlandia. El registro de las empresas imprimió a menudo resguardos de pago a las facturas para proporcionar una referencia de pago para su registro y liquidación. El resguardo de pago se puede usar para facturas de proyecto o texto sin formato, cartas de cobro, notas de interés y extractos de cuenta, además de las facturas de ventas y facturas de servicios.

## <a name="set-up-a-creditor-id-number-denmark-only"></a>Configurar un número de identificación de acreedor sólo (Dinamarca)
Siga estos pasos para especificar el número de identificación (ID) de pallet de acreedor de la empresa. Su entidad financiera proporciona este número. Ha utilizado como referencia a los pagos de cliente se reciben a través de las instituciones financieras.

1.  ** Haga clic en Administración de organización ** &gt; ** configuración ** &gt; ** organización ** &gt; ** entidades jurídicas **.
2.  En ** información de cuentas bancarias ** la ficha desplegable, en ** identificador de FI- acreedor ** el campo, escriba su número de identificación de ocho dígitos único del acreedor.
3.  Cierre el formulario para guardar los cambios.

## <a name="set-up-a-payment-slip-attachment-format-for-invoices-interest-notes-collection-letters-and-account-statements"></a>Configuración de un resguardo de pago para facturas, notas de interés, cartas de cobro, y los extractos de cuenta
Siga estos pasos para configurar un formato para los resguardos de pago que acompañan facturas de ventas, facturas de servicios, notas de interés, cartas de cobro, y los extractos de cuenta.

1.  Haga clic en ** clientes ** &gt; ** configuración ** &gt; ** formularios ** &gt; ** el formulario configurar **.
2.  En ** ** factura, en la ficha ** los archivos adjuntos asociados de pago en factura de cliente ** campo, seleccione el formato de resguardo de pago.
3.  En ** factura de servicios, ** ** nota de interés, ** ** carta de cobro **, y ** extracto de cuenta ** las fichas, seleccione un formato de resguardo de pago para cada tipo de documento.
4.  Cierre el formulario para guardar los cambios.

Siga estos pasos para configurar un formato para los resguardos de pago que acompañan facturas de proyecto.

1.  ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** configuración ** &gt; ** formularios ** &gt; ** el formulario configurar **.
2.  En ** los archivos adjuntos asociados de pago ** campo, seleccione el formato de resguardo de pago.

## <a name="assign-a-payment-slip-attachment-format-to-a-customer-account"></a>Asignar un formato de pago del resguardo a una cuenta de cliente
Después de configurar el formato de resguardo de pago para las facturas de ventas, facturas de texto sin formato, notas de interés, cartas de cobro, los extractos de cuenta, y las facturas de proyecto, puede asignar los formatos específicos para un cliente seleccionado.

1.  Haga clic en ** clientes ** &gt; ** común ** &gt; ** clientes ** &gt; ** todos los clientes **.
2.  Cree un nuevo cliente, o seleccione un cliente existente.
3.  En ** factura y entrega ** la ficha desplegable, en ** en una factura de cliente, ** ** en una factura de servicios, ** ** en una nota de interés, ** ** en una carta de cobro, ** ** en una factura de proyecto, ** y ** en un extracto de cuenta ** campos, seleccione el formato para los resguardos de pago que acompañará los documentos de cada tipo que se envían al cliente seleccionado.
4.  Cierre el formulario para guardar los cambios.



