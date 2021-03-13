---
title: 'Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 3: Creación del formato)'
description: Este tema describe cómo configurar un formato de informes electrónicos para utilizar archivos de administración de documentos en la salida de informes electrónicos. (Parte 3)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 432cf4c41a7a223ab07b02edf6da7eac9965cff0
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092625"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a>Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 3: Creación del formato)

[!include [banner](../../includes/banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar los pasos en el procedimiento "ER Uso de archivos de gestión de documentos en formatos de salida (Parte 2: Aumentar el modelo de datos)”.

Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.


## <a name="create-a-format-to-process-invoices"></a>Cree un formato para procesar facturas
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Configuraciones de informes.
3. En el árbol, expanda el “Modelo de factura del cliente”.
4. En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)”.
    * Creará un formato para generar mensajes electrónicos con información sobre cualquier archivo que se haya adjuntado a un pedido de ventas relacionado con una factura que se procese electrónicamente.  
5. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
6. En el campo Nuevo, introduzca "Formato basado en el modelo de datos del modelo de factura de Cliente (cliente)”.
7. En el campo Nombre, introduzca “Mensaje de ejemplo de factura electrónica”.
    * Mensaje de ejemplo de factura electrónica  
8. En el campo definición del modelo de Datos, introduzca o seleccione un valor.
    * InvoiceCustomer  
9. Haga clic en Crear configuración.

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a>Diseñe un formato para rellenar los adjuntos y generar un mensaje en formato MIME
1. Haga clic en Diseñador.
2. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
3. En el árbol, seleccione XML\Elemento.
4. En el campo Nombre, introduzca "Factura".
    * Factura  
5. Haga clic en Aceptar
6. Haga clic en Agregar para abrir el cuadro desplegable.
7. En el árbol, seleccione XML\Atributo.
8. En el campo Nombre, introduzca "SalesOrder".
    * SalesOrder  
9. Haga clic en Aceptar
10. Haga clic en Agregar atributos.
11. En el campo Nombre, introduzca "InvoiceNumber".
    * InvoiceNumber  
12. Haga clic en Aceptar
13. Haga clic en Agregar atributos.
14. En el campo Nombre, introduzca 'InvoiceAmount'.
    * InvoiceAmount  
15. Haga clic en Aceptar
16. Haga clic en Agregar para abrir el cuadro desplegable.
17. En el árbol, seleccione XML\Elemento.
18. En el campo Nombre, introduzca "EnclosedDocs".
    * EnclosedDocs  
19. Haga clic en Aceptar
20. En el árbol, seleccione “Invoice\EnclosedDocs”.
21. Haga clic en Agregar elemento.
22. En el campo Nombre, introduzca "Documento".
    * Documento  
23. Haga clic en Aceptar
24. En el árbol, seleccione “Invoice\EnclosedDocs\Document”.
25. Haga clic en Agregar para abrir el cuadro desplegable.
26. En el árbol, seleccione XML\Atributo.
27. En el campo Nombre, introduzca "FileName".
    * FileName  
28. Haga clic en Aceptar
29. Haga clic en Agregar para abrir el cuadro desplegable.
30. En el árbol, seleccione XML\Elemento.
31. En el campo Nombre, introduzca "FileContent".
    * FileContent  
32. Haga clic en Aceptar
33. En el árbol, seleccione “Invoice\EnclosedDocs\Document\FileContent”.
34. Haga clic en Agregar para abrir el cuadro desplegable.
35. En el árbol, seleccione 'Text\Base64'.
36. Haga clic en Aceptar

## <a name="map-format-elements-to-data-model-as-data-source"></a>Asigne elementos de formato al modelo de datos como origen de datos 
1. En el árbol, seleccione “Invoice\SalesOrder”.
2. Haga clic en la ficha Asignación.
3. En el árbol , expanda "modelo".
4. En el árbol, seleccione “model\Sales order number(SalesId)".
5. Haga clic en Enlazar.
6. En el árbol, seleccione “Invoice\InvoiceNumber”.
7. En el árbol, expanda "model\Base invoice(InvoiceBase)".
8. En el árbol, seleccione “model\Base invoice(InvoiceBase)\Invoice number(Id)”.
9. Haga clic en Enlazar.
10. En el árbol, seleccione “Invoice\InvoiceAmount".
11. En el árbol, seleccione “model\Base invoice(InvoiceBase)\Invoice amount(Amount)”.
12. Haga clic en Enlazar.
13. En el árbol, expanda el “model\Invoice attachments".
14. En el árbol, seleccione “model\Invoice attachments\File content".
15. En el árbol, seleccione “Invoice\EnclosedDocs\Document\FileContent\Base64”.
16. Haga clic en Enlazar.
17. En el árbol, seleccione “model\Facturar adjuntos\Nombre de archivo”.
18. En el árbol, seleccione “Invoice\EnclosedDocs\Document\FileName”.
19. Haga clic en Enlazar.
20. En el árbol, seleccione “model\Invoice attachments”.
21. En el árbol, seleccione “Invoice\EnclosedDocs\Document”.
22. Haga clic en Enlazar.
23. Haga clic en Guardar.
24. Cierre la página.

