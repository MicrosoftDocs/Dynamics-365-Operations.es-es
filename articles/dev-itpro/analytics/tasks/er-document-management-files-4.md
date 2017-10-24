--- 
title: "Ejecutar el formato para usar archivos de administración de documentos en las salidas de formato para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 419c3e305dfdd7d8612340b4a8e8e54e13c6362b
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a>Ejecutar el formato para usar archivos de administración de documentos en las salidas de formato para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER. Estos pasos se pueden llevar a cabo en la empresa DEMF.

Para completar estos pasos, primero debe completar los pasos en el procedimiento "ER Uso de archivos de gestión de documentos en formatos de salida (Parte 3: crear formato)”.

Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a>Agregue los adjuntos necesarios para el pedido de ventas de una única factura
1. Vaya a Clientes > Facturas > Facturas de cliente abiertas.
2. Use el filtro rápido para buscar registros. Por ejemplo, filtre el campo Factura con un valor de "CIV-000148".
    * CIV-000148  
3. Haga clic para seguir el enlace de la factura seleccionada.
    * CIV-000148  
4. Haga clic para seguir el enlace en el campo Pedido de compra.
    * 000148  
5. En las Líneas o el campo de cabecera, seleccione la opción de Cabecera.
    * Seleccione el Encabezado para indicar que éste será el destino para agregar los adjuntos.  
6. Haga clic en Vincular.
    * Agregue algunos archivos como adjuntos para este pedido de ventas. Use los archivos de los tipos de documento admitidos por la gestión de documentos (con las extensiones de archivo DOCX, DPF, XML, JPG., etc.). Examinar y seleccionar los archivos que se adjuntarán y que serán procesados con la factura relacionada en el mensaje electrónico de ER.  
7. Haga clic en Nuevo.
8. Haga clic en Archivo.
9. Haga clic en Nuevo.
10. Haga clic en Archivo.
11. Cierre la página.
12. Cierre la página.
13. Cierre la página.
14. Cierre la página.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Ejecute el informe diseñado para la factura seleccionada
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, expanda el “Modelo de factura del cliente”.
3. En el árbol, expanda el “Modelo de factura de cliente\Modelo de factura de cliente (cliente)”.
4. En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)\Mensaje de ejemplo de factura electrónica”.
5. Haga clic en Ejecutar.
6. Expanda los Registros para incluir la sección ().
7. Haga clic en Filtro.
8. Seleccione la fila del diario de facturas de Cliente y el campo de Pedido de ventas.
9. En campo Criterios, introduzca '000148'.
    * En los criterios del campo “Pedido de ventas”, introduzca el número de pedido 000148.  
10. Haga clic en Aceptar
11. Haga clic en Aceptar
    * Revise la salida generada. Tenga en cuenta que se ha creado un nodo XML por cada adjunto. El contenido del adjunto se rellena al archivo de salida XML en formato de texto MIME (base64).  


