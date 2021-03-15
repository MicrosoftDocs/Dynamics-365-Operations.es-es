---
title: 'Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 5: Modificación y ejecución del formato)'
description: Este tema describe cómo configurar un formato de informes electrónicos (ER) para utilizar archivos de administración de documentos (adjuntos) en la salida de informes electrónicos. (Parte 5)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f96189163d5ecac47ade9f713b3fd689e41352d0
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092497"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a>Informe electrónico Usar archivos de gestión de documentos en las salidas de formato (Parte 5: Modificación y ejecución del formato)

[!include [banner](../../includes/banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema, o a un rol de desarrollador de informes electrónicos, puede configurar un formato de informe electrónico (ER) para usar archivos de gestión de documentos (adjuntos) en formato ER. Estos pasos se pueden llevar a cabo en la empresa DEMF.

Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Uso de gestión de documentos en formatos de salida (Parte 4: Ejecutar un formato)”.

Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a>Modifique el formato para rellenar los adjuntos y generar mensajes en formato binario
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, expanda el “Modelo de factura del cliente”.
3. En el árbol, expanda el “Modelo de factura de cliente\Modelo de factura de cliente (cliente)”.
4. En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)\Mensaje de ejemplo de factura electrónica”.
5. Haga clic en Diseñador.
    * Se rellenará el mensaje de la factura en un formato generado como archivo XML con codificación UNICODE.  
6. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
7. En el árbol, seleccione Común\Archivo.
8. En el campo Nombre, introduzca "Mensaje Xml".
    * Mensaje Xml  
9. En el campo Codificación, escriba "UTF-8".
    * UTF-8  
10. Haga clic en Aceptar
    * Configurar el formato de salida como archivo comprimido.  
11. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
12. En el árbol, seleccione "Common\Folder".
13. En el campo Nombre, introduzca "Formato de salida comprimido".
    * Código postal generado  
14. Haga clic en Aceptar
15. En el árbol, seleccione "Formato de salida comprimido".
    * Agregue adjuntos al archivo comprimido generado como archivos con nombres originales y extensiones.  
16. Haga clic en Agregar para abrir el cuadro desplegable.
17. En el árbol, seleccione Común\Archivo.
18. En el campo Nombre, introduzca "Archivo adjunto".
    * Archivo adjunto  
19. Haga clic en Aceptar
20. En el árbol, seleccione "Formato de salida comprimido\Archivo adjunto".
21. Haga clic en Agregar para abrir el cuadro desplegable.
22. En el árbol, seleccione 'Text\Base64'.
23. Haga clic en Aceptar

## <a name="map-new-format-elements-to-data-model"></a>Asigne nuevos elementos de formato al modelo de datos
1. Haga clic en la ficha Asignación.
2. En el árbol , expanda "modelo".
3. En el árbol, expanda el “model\Invoice attachments".
4. En el árbol, seleccione “Formato de salida adjunto\Archivo adjunto\Base64”.
5. En el árbol, seleccione “model\Invoice attachments\File content".
6. Haga clic en Enlazar.
7. En el árbol, seleccione "Formato de salida comprimido\Archivo adjunto".
8. Haga clic en Editar nombre de archivo.
9. En el árbol , expanda "modelo".
10. En el árbol, expanda el “model\Invoice attachments".
11. En el árbol, seleccione “model\Facturar adjuntos\Nombre de archivo”.
12. Haga clic en Agregar origen de datos.
13. Haga clic en Guardar.
14. Cierre la página.
15. En el árbol, seleccione “model\Invoice attachments”.
16. Haga clic en Enlazar.
17. Haga clic en Guardar.
18. Cierre la página.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Ejecute el informe diseñado para la factura seleccionada
1. Haga clic en Ejecutar.
2. Expanda los Registros para incluir la sección ().
3. Haga clic en Filtro.
4. Seleccione la fila del diario de facturas de Cliente y el campo de Pedido de ventas.
5. En el campo Criterios, En el campo de criterios “Pedido de ventas”, introduzca el número de pedido 000148.
    * 000148  
6. Haga clic en Aceptar.
7. Haga clic en Aceptar.
    * Revise la salida generada. Tenga en cuenta que, además del mensaje de factura en formato XML, se ha creado un archivo único para cada adjunto. Los archivos adjuntos se rellenan con el formato de salida comprimido en formato binario.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]