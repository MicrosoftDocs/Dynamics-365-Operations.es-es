---
title: MX-00010 Facturación electrónica de CFDI
description: Esta tarea le muestra cómo crear y registrar una factura de cliente como una factura electrónica usando el método CFDI.
author: sndray
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxGroupLookup, InventLocationIdLookup, SalesEditLines,  EInvoiceCFDIJournal_AR
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92a6c66ed18350212dd5a070c9673ad2eb503aba
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852625"
---
# <a name="mx-00010-e-invoicing-cfdi"></a>MX-00010 Facturación electrónica de CFDI

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta tarea le muestra cómo crear y registrar una factura de cliente como una factura electrónica usando el método CFDI. Puede crear y registrar varios pedidos de ventas como facturas electrónicas y enviar los archivos .pdf y .xml como archivos adjuntos a los clientes. Esta tarea solo se puede completar si está registrado en una entidad jurídica con dirección principal en México. Esta tarea usa la empresa de demostración MXMF.

1. Vaya a Clientes > Pedidos > Todos los pedidos de venta.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en Aceptar
7. En la lista, marque la fila seleccionada.
8. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
9. En la lista, haga clic en el vínculo de la fila seleccionada.
10. En el campo Precio unitario, escriba un número.
11. Expanda o contraiga la sección Detalles de línea.
12. Haga clic en la ficha Configurar.
13. En el campo Grupo de impuestos, haga clic en el botón desplegable para abrir la búsqueda.
14. En la lista, haga clic en el vínculo de la fila seleccionada.
15. En el campo Grupo de impuestos de artículos, haga clic en el botón desplegable para abrir la búsqueda.
16. En la lista, busque y seleccione el registro deseado.
17. En la lista, haga clic en el vínculo de la fila seleccionada.
18. Haga clic en la ficha Producto.
19. En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.
20. En la lista, busque y seleccione el registro deseado.
21. En la lista, haga clic en el vínculo de la fila seleccionada.
22. Haga clic en Aceptar
23. En el campo Aduana, escriba un valor.
    * Introduzca el número del documento de aduanas que se generó cuando se importó el artículo.  
24. En el campo Fecha de aduana, especifique una fecha.
    * Seleccione la fecha en la que se importó el artículo.  
25. En el campo Nombre de aduana, escriba un valor.
    * Escriba el nombre de la autoridad de aduanas del país o región de donde se importó el artículo.  Si escribe valores en los campos Número de aduana, Fecha de aduana y Nombre de aduana, no podrá escribir un valor en el campo Número de propiedad.  
26. En el campo Precio unitario, escriba un número.
27. Expanda o contraiga la sección Encabezado de pedido de ventas.
28. En el panel de acciones, haga clic en Vender.
29. Haga clic en Confirmar pedido de ventas.
30. Haga clic en Aceptar
31. Haga clic en Aceptar
32. En el panel de acciones, haga clic en Factura.
33. Haga clic en Factura.
34. Expanda la sección Parámetros para revisar los parámetros antes del registro.
35. Haga clic en Aceptar
    * Tras presionar Aceptar, la factura de cliente se registra y se programa en un procesamiento de lote concreto para emitir facturas electrónicas (CFDI).  
36. Haga clic en Aceptar
37. Vaya a Clientes > Facturas > Facturas electrónicas > Proceso de exportar/importar factura electrónica.
38. Haga clic en Aceptar
    * Este trabajo por lotes inicia la conexión con los servicios web PAC para obtener la aprobación o la cancelación de una factura electrónica (CFDI). La tarea en el lote se puede ejecutar manualmente o se puede programar para un período de tiempo específico.      Tras presionar Aceptar, la validación y la firma digital se recuperarán de PAC. Si se aprueba la factura electrónica, PAC envía el mensaje XML de respuesta y el estado de la factura electrónica se actualizará para su aprobación. Se envía un mensaje de correo electrónico automáticamente al cliente con el archivo XML y PDF adjunto. Los controles deslizantes Enviar correo y Enviar archivo de informe: PDF se deben establecer en "Sí" en la página de parámetros de factura electrónica. Si no, puede enviar por correo electrónico o imprimir el informe PDF basándose en la solicitud del cliente mediante el menú Consultar e informar > CFDI (facturas electrónicas).  
39. Vaya a Clientes > Consultas e informes > CFDI (facturas electrónicas).
40. En la lista, haga clic en la factura electrónica que revisar.

