---
title: 'Informe electrónico Archivos de gestión de documentos en las salidas de formato (Parte 2: Extensión del modelo de datos)'
description: Este tema describe cómo configurar un formato de informes electrónicos (ER) para utilizar archivos de administración de documentos (adjuntos) en la salida de informes electrónicos. (Parte 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cd06cdfd9bae57577c2e3ec97848e319b197f41
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092600"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a>Informe electrónico Archivos de gestión de documentos en las salidas de formato (Parte 2: Extensión del modelo de datos)

[!include [banner](../../includes/banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un informe electrónico (ER) para usar los archivos de gestión de documentos (adjuntos) en formato ER. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar los pasos de la guía de tareas “ER Uso de los archivos de gestión de documentos en formatos de salida (Parte 1: Preparar el modelo de datos)”.

Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a>Extienda el modelo de datos para mostrar los archivos de gestión de documentos
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Configuraciones de informes.
3. En el árbol, expanda el “Modelo de factura del cliente”.
4. En el árbol, seleccione “Modelo de factura de cliente\Modelo de factura de cliente (importación)”.
5. Haga clic en Diseñador.
6. En el árbol, seleccione “Modelo de factura (InvoiceCustomer)”.
    * Extenderemos este modelo de datos para exponer en él archivos que se hayan adjuntado a un pedido de ventas relacionado con una factura procesada electrónicamente.  
7. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
8. En el campo Nombre, introduzca "Facturar adjuntos".
    * Facturar adjuntos  
9. En el campo Tipo de artículo, seleccione Lista de registros.
10. Haga clic en Agregar.
11. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
12. En el campo Nombre, introduzca "Contenido de archivo".
    * Contenido del archivo  
13. En el campo Tipo de artículo, seleccione "Contenedor".
14. Haga clic en Agregar.
15. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
16. En el campo Nombre, introduzca "Nombre de archivo".
    * Nombre de archivo  
17. En el campo Tipo de artículo, seleccione Cadena.
18. Haga clic en Agregar.

## <a name="map-new-data-model-elements-to-data-sources"></a>Asigne nuevos elementos de modelo de datos a orígenes de datos
1. Haga clic en Asignar modelo a origen de datos.
2. Use el Filtro rápido para filtrar el campo Definición con un valor de 'InvoiceCustomer'.
    * InvoiceCustomer  
    * Asignaremos nuevos elementos del modelo a los orígenes de datos adecuados.  
3. Haga clic en Diseñador.
4. En el árbol, seleccione “Facturar adjuntos”.
5. En el árbol, expanda “Facturar adjuntos”.
6. En el árbol, seleccione “Facturar adjuntos\Nombre de archivo”.
7. Haga clic en Editar.
8. En el campo Fórmula, introduzca "CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'  
9. Haga clic en Guardar.
10. Cierre la página.
11. En el árbol, seleccione “Facturar adjuntos\Contenido de archivo”.
12. Haga clic en Editar.
13. En el campo Fórmula, introduzca 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'  
14. Haga clic en Guardar.
15. Cierre la página.
16. En el árbol, seleccione “Facturar adjuntos”.
17. Haga clic en Editar.
18. En el campo Fórmula, introduzca 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'  
19. Haga clic en Guardar.
20. Cierre la página.
21. Haga clic en Guardar.
22. Cierre la página.
23. Cierre la página.
24. Cierre la página.
25. Haga clic en Cambiar estado.
26. Haga clic en Completar.
27. Haga clic en Aceptar

