---
title: Facturación electrónica de CFDI
description: Este tema le muestra cómo crear y registrar una factura de cliente como una factura electrónica usando el método CFDI.
author: sndray
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxGroupLookup, InventLocationIdLookup, SalesEditLines,  EInvoiceCFDIJournal_AR
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3d9c3b2cb8ad902b7327a0423277b89a630501f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819532"
---
# <a name="e-invoicing-cfdi"></a>Facturación electrónica de CFDI

[!include [banner](../../includes/banner.md)]

Este tema le muestra cómo crear y registrar una factura de cliente como una factura electrónica usando el método CFDI. Puede crear y registrar varios pedidos de ventas como facturas electrónicas y enviar los archivos .pdf y .xml como archivos adjuntos a los clientes. Esta tarea solo se puede completar si está registrado en una entidad jurídica con dirección principal en México. Esta tarea usa la empresa de demostración MXMF.

1. En el panel de navegación, vaya a **Módulos > Clientes > Pedidos > Todos los pedidos de ventas**.
2. Seleccione **Nuevo**.
3. En el campo **Cuenta de cliente**, seleccione el registro deseado desde el menú desplegable.
4. Seleccione **Aceptar**.
5. En el campo **Código de artículo** de la nueva fila, seleccione la opción deseada desde el menú desplegable.
6. En el campo **Precio unitario**, escriba un número.
7. En la sección **Detalles de línea**, seleccione la pestaña **Configuración**.
8. En el campo **Grupo de impuesto**, seleccione la fila deseada desde el menú desplegable.
9. En el campo **Grupo de impuestos de artículos**, seleccione el registro deseado desde el menú desplegable.
10. Seleccione la pestaña **Producto**.
11. En el campo **Almacén**, seleccione el registro deseado desde el menú desplegable.
12. Seleccione **Aceptar**.
13. En el campo **Número de aduana**, escriba un valor. Introduzca el número del documento de aduanas que se generó cuando se importó el artículo.  
14. En el campo **Fecha de aduana**, especifique una fecha. Seleccione la fecha en la que se importó el artículo.  
15. En el campo **Nombre de aduana**, escriba un valor. Escriba el nombre de la autoridad de aduanas del país o región de donde se importó el artículo. Si escribe valores en los campos **Número de aduana**, **Fecha de aduana** y **Nombre de aduana**, no podrá escribir un valor en el campo **Número de propiedad**.  
16. En el campo **Precio unitario**, escriba un número.
17. Expanda la sección **Encabezado de pedidos de ventas**.
18. En el panel de acciones, seleccione **Vender**.
19. Seleccione **Confirmar pedido de ventas**.
20. Seleccione **Aceptar** y, a continuación, vuelva a seleccionar **Aceptar**.
21. En el Panel de acciones, seleccione **Factura**.
22. Expanda la sección **Parámetros** para revisar los parámetros antes del registro.
23. Seleccione **Aceptar**. Tras presionar **Aceptar**, la factura de cliente se registra y se programa en un procesamiento de lote concreto para emitir facturas electrónicas (CFDI).  
24. Seleccione **Aceptar**.
25. En el panel de navegación, vaya a **Módulos > Clientes > Facturas > Facturas electrónicas > Proceso de exportar/importar factura electrónica**.
26. Seleccione **Aceptar**.
    - Este trabajo por lotes inicia la conexión con los servicios web PAC para obtener la aprobación o la cancelación de una factura electrónica (CFDI). La tarea en el lote se puede ejecutar manualmente o se puede programar para un período de tiempo específico.  
    - Tras seleccionar **Aceptar**, la validación y la firma digital se recuperarán de PAC. Si se aprueba la factura electrónica, PAC envía el mensaje XML de respuesta y el estado de la factura electrónica se actualizará para su aprobación. Se envía un mensaje de correo electrónico automáticamente al cliente con el archivo XML y PDF adjunto. Los controles deslizantes **Enviar correo** y **Enviar archivo de informe: PDF** se deben establecer en **Sí** en la página de **parámetros de factura electrónica**. Si no, puede enviar por correo electrónico o imprimir el informe PDF basándose en la solicitud del cliente mediante el menú **Consultar e informar > CFDI (facturas electrónicas)**.  
27. En el panel de navegación, vaya a **Módulos > Clientes > Consultas e informes > CFDI (facturas electrónicas)**.
28. En la lista, seleccione la factura electrónica que revisar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]