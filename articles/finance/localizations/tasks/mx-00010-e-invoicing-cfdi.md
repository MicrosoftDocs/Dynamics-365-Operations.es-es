---
title: Facturación electrónica de CFDI
description: Este tema le muestra cómo crear y registrar una factura de cliente como una factura electrónica usando el método CFDI.
author: sndray
ms.date: 08/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxGroupLookup, InventLocationIdLookup, SalesEditLines, EInvoiceCFDIJournal_AR
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9ff97f7ecee4439c09ffc32cc853005a8508146
ms.sourcegitcommit: f1ef61ee3d731f68e11a5bebc154ed33a7b8eda5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2021
ms.locfileid: "7383811"
---
# <a name="e-invoicing-cfdi"></a>Facturación electrónica de CFDI

[!include [banner](../../includes/banner.md)]

Este tema le muestra cómo crear y registrar una factura de cliente como una factura electrónica usando el método CFDI. Puede crear y registrar varios pedidos de ventas como facturas electrónicas y enviar los archivos .pdf y .xml como archivos adjuntos a los clientes. Esta tarea solo se puede completar si está registrado en una entidad jurídica con dirección principal en México. Esta tarea usa la empresa de demostración MXMF.

> [!NOTE] 
> Las facturas de clientes que se crean utilizando un diario de contabilidad general no se incluyen entre las facturas electrónicas de CFDI-Clientes que se encuentran en **Clientes** \> **Consultas e informes**\>**CFDI (facturas electrónicas)**.

1. Vaya a **Clientes** \> **Pedidos** \> **Todos los pedidos de venta** y seleccione **Nuevo**.
2. En el campo **Cuenta de cliente**, seleccione un valor. A continuación seleccione **Aceptar**.
3. En la nueva fila, en el campo **Número de artículo**, seleccione un valor. En el campo **Precio unitario**, introduzca un valor.
4. En la sección **Detalles de línea**, en la ficha **Configuración**, en el campo **Grupo de impuestos sobre las ventas**, seleccione un valor. En el campo **Grupos de impuestos de artículos**, seleccione un valor.
6. En la ficha **Producto**, en el campo **Almacén**, seleccione un valor. A continuación seleccione **Aceptar**.
7. En el campo **Número de aduana**, introduzca el número del documento de aduanas generado al importar el artículo.
8. En el campo **Fecha de aduana**, seleccione la fecha en la que se importó el artículo.
9. En el campo **Nombre de aduana**, escriba el nombre de la autoridad de aduanas del país o región del que se importó el artículo.

    > [!NOTE]
    > Si escribe valores en los campos **Número de aduana**, **Fecha de aduana** y **Nombre de aduana**, no podrá escribir un valor en el campo **Número de propiedad**.

10. En el campo **Precio unitario**, introduzca un valor.
11. Amplíe la sección **Encabezado de pedido de ventas** y, a continuación, en el panel de acciones, seleccione **Venta**\> **Confirmar pedido de ventas**.
12. Seleccione **Aceptar** y, a continuación, vuelva a seleccionar **Aceptar**.
13. En el Panel de acciones, seleccione **Factura**.
14. En la sección **Parámetros**, revise los parámetros antes de registrar la factura del cliente. A continuación seleccione **Aceptar**.

    La factura de cliente se registra y se programa en un procesamiento de lote concreto para emitir facturas electrónicas (CFDI).

16. Seleccione **Aceptar**.
17. Vaya a **Clientes** \> **Facturas** \> **Facturas electrónicas** \> **Proceso de exportar/importar factura electrónica** y seleccione **Aceptar**.

    - Este trabajo por lotes inicia la conexión con los servicios web PAC para obtener la aprobación o la cancelación de una factura electrónica (CFDI). La tarea en el lote se puede ejecutar manualmente o se puede programar para un período de tiempo específico.
    - Tras seleccionar **Aceptar**, la validación y la firma digital se recuperarán de PAC. Si se aprueba la factura electrónica, PAC envía el mensaje XML de respuesta y el estado de la factura electrónica se actualizará para su aprobación. Se envía un mensaje de correo electrónico automáticamente al cliente con el archivo XML y PDF adjunto. Los controles deslizantes **Enviar correo** y **Enviar archivo de informe: PDF** se deben establecer en **Sí** en la página de **parámetros de factura electrónica**. Si no, puede enviar por correo electrónico o imprimir el informe PDF basándose en la solicitud del cliente mediante el menú **Consultar e informar > CFDI (facturas electrónicas)**.

18. Vaya a **Clientes** \> **Consultas e informes** \> **CFDI (facturas electrónicas)** y seleccione la factura electrónica que desee revisar.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
