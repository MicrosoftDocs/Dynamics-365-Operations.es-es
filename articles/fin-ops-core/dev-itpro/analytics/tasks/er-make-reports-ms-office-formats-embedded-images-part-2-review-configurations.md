---
title: Revisar configuraciones para generar informes en los formatos de Office que tengan imágenes incrustadas
description: 'Este tema describe cómo diseñar las configuraciones de los informes para generar documentos electrónicos que contienen imágenes insertadas. (Parte 1: configurar parámetros).'
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3eee6300350dd96c34f2eab44704d1895e6171ff
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093654"
---
# <a name="review-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Revisar configuraciones para generar informes en los formatos de Office que tengan imágenes incrustadas

[!include [banner](../../includes/banner.md)]

Para completar estos pasos, primero debe completar los pasos de la guía de tareas "ER crea informes en los formatos de MS Office con imágenes incrustadas (Parte 1: Configurar parámetros)”.

Este procedimiento muestra cómo diseñar las configuraciones de informes electrónicos (ER) para generar documentos electrónicos que contienen imágenes incrustadas en Microsoft Excel y Microsoft Word. En este ejemplo, revisará configuraciones de ER creadas para una empresa de ejemplo Litware, Inc. 

Este procedimiento se ha creado para los usuarios con los roles de Administrador del sistema o Desarrollador de informes electrónicos asignados. Los pasos se pueden completar mediante el conjunto de datos de USMF.


## <a name="review-the-imported-data-model"></a>Revise el modelo de datos importado
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, seleccione "Modelo para cheques".
3. Haga clic en Diseñador.
    * Este modelo se ha diseñado para representar los cheques de pago desde el punto de vista de la empresa y la asignación de este modelo para los orígenes de datos de la aplicación. Revise este modelo según diseñador de las operaciones de ER. Tenga en cuenta los atributos de elementos de modelo que se están presentes: estructura, nombre, descripción, tipo de datos, etc.   
4. En el árbol, expanda "raíz".
5. En el árbol, seleccione "raíz\cheques".
6. En el árbol, expanda "raíz\cheques".
7. En el árbol, expanda "raíz\cheques\atributos".
8. En el árbol, expanda el "raíz\pagador".
9. En el árbol, seleccione "raíz\ejecutarprueba".
10. En el árbol, seleccione "raíz\diseño".
    * El artículo del diseño de este modelo representa los detalles del diseño de formulario del cheque de impresión para la cuenta bancaria seleccionada. También incluye dos nodos del tipo de datos Contenedor para guardar imágenes.   
11. En el árbol, expanda el "raíz\diseño".
12. En el árbol, seleccione "raíz\diseño\logotipo empresa".
13. En el árbol, expanda "raíz\diseño\logotipo empresa".
14. En el árbol, seleccione "raíz\diseño\logotipo de empresa\imagen".
15. En el árbol, seleccione "raíz\diseño\logotipo de empresa\impreso".
16. En el árbol, seleccine "raíz\diseño\firma".
17. En el árbol, expanda "raíz\diseño\firma".
18. En el árbol, seleccione "raíz\diseño\firma\imagen".
19. En el árbol, seleccione "raíz\diseño\firma\impreso".
    * Tenga en cuenta que dos elementos del modelo de datos de imagen están enlazados a los campos de las tablas que contienen las imágenes de logotipo de la empresa y la firma de la persona autorizada en formato binario.  
20. En el árbol, expanda "raíz\diseño\marca de agua".
21. Haga clic en Asignar modelo a origen de datos.
22. Haga clic en Diseñador.
23. En el árbol, expanda "chequesseleccionados".
24. En el árbol, expanda "Diseño".
25. En el árbol, expanda "diseño\logotipo de empresa".
26. En el árbol, expanda "Diseño\firma".
27. En el árbol, expanda "diseño\marca de agua".
28. Active "Mostrar detalles".
    * Tenga en cuenta que el elemento del modelo de datos de los cheques está enlazado a la tabla TmpChequePrintout que, en el tiempo de ejecución, contendrá los registros para los cheques que el usuario ha seleccionado para imprimir.   
29. Cierre la página.
30. Cierre la página.
31. Cierre la página.

## <a name="review-the-imported-format"></a>Revisar el formato importado
1. En el árbol, expanda "Modelo para cheques".
2. En el árbol, seleccione "Modelo para cheques\Formato de impresión de cheques".
3. Haga clic en Diseñador.
4. Haga clic en Archivos adjuntos.
5. Haga clic en Abrir.
    * Abra la plantilla del informe adjunta en Excel.  
    * Revise la plantilla de Excel del informe vinculado que se usará para imprimir los cheques. La plantilla contiene dos cheques por página y está diseñado para imprimir los cheques para el formulario preimpreso. Tenga en cuenta que dos imágenes en blanco están incrustadas. Estas imágenes en blanco son para el logotipo de la empresa y la firma de la persona que autoriza el pago. Compruebe que las imágenes se denominan CompLogo y SignatureImage, respectivamente, en Excel.   
6. Cierre la página.
7. En el árbol, expanda "Informe".
8. En el árbol, expanda "Informe\LíneasdeCheque".
9. En el árbol, seleccione "Informe\LíneasdeCheque\LogoEmpr".
10. Active "Mostrar detalles".
    * Tenga en cuenta que el elemento de la celda de formato "CompLogo" representa el elemento de Excel que se usa para rellenar la imagen del logotipo de la empresa en el informe. Este elemento de formato está enlazado al elemento del modelo de datos de la imagen que, en el tiempo de ejecución, contiene una imagen del logotipo de la empresa en formato binario.   
11. Haga clic en la ficha Asignación.
12. Haga clic en Editar habilitado.
    * Tenga en cuenta que puede crear el elemento de la celda del formato de "CompLogo" para que no pueda volver a habilitarse. En este caso, el elemento de imagen de Excel asociado ocultará un logotipo de la empresa en el informe generado. Si la expresión habilitado devuelve TRUE y el enlace definido no recibe imagen alguna, el elemento de imagen de Excel asociado mostrará una imagen que se ha guardado en la plantilla de Excel.   
13. Cierre la página.
14. En el árbol, expanda "etiquetas: Contenedor".
    * Algunas etiquetas que se muestran en el formulario preimpreso del cheque se incluirán en el informe cuando se haya creado para hacer pruebas. Sin embargo, dichas etiquetas no se imprimirán durante la impresión real, porque el formulario preimpreso las incluye ya.  
15. Cierre la página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]