---
title: Diseñar configuraciones de ER para generar informes en formato Word
description: En los pasos siguientes se explica cómo un usuario con rol de administrador del Sistema o de desarrollador de informes electrónicos puede configurar formatos de informes electrónicos para generar archivos de informes en Microsoft Word.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dc47d44285af4c720d2f450d11fb1004ef461d0f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "362358"
---
# <a name="design-er-configurations-to-generate-reports-in-word-format"></a>Diseñar configuraciones de ER para generar informes en formato Word

[!include [task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de administrador del Sistema o de desarrollador de informes electrónicos puede configurar formatos de informes electrónicos (ER) para generar archivos de informes en Microsoft Word. Estos pasos se pueden llevar a cabo en la empresa GBSI.

Para completar estos pasos, primero debe completar los pasos en la guía de tarea "Crear una configuración de ER para generar informes en formato OPENXML”. Previamente deberá descargar y guardar también las plantillas siguientes localmente para el informe de ejemplo:

- [Plantilla de informe de pago](https://go.microsoft.com/fwlink/?linkid=862266)
- [Plantilla enlazada de informe de pago](https://go.microsoft.com/fwlink/?linkid=862266)


Este procedimiento es para una función que se ha agregado en la versión 1611 de Microsoft Dynamics 365 for Operations.


## <a name="select-the-existing-er-report-configuration"></a>Seleccione la configuración existente del informe ER
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Asegúrese de que el proveedor de la configuración "Litware, Inc." está seleccionado como activo.  
2. Haga clic en Configuraciones de informes.
    * Reutilizaremos la configuración actual de ER que se ha diseñado originalmente para generar la salida de informes en formato de OPENXML.  
3. En el árbol, expanda "Modelo de pago".
4. En el árbol, seleccione "Modelo de pago\Informe de hoja de cálculo de muestra".
5. Haga clic en Diseñador.

## <a name="replace-the-excel-template-with-the-word-template"></a>Sustituya la plantilla de Excel con la plantilla de Word
    * Actualmente, el documento de Excel se utiliza como plantilla para producir un resultado en formato de OPENXML. Importaremos la plantilla del informe en formato de Word.  
1. Haga clic en Archivos adjuntos.
    * Sustituya la plantilla de Excel actual con la plantilla de Word que ha descargado anteriormente, SampleVendPaymDocReport.docx. Tenga en cuenta que esta plantilla solo contiene el diseño del documento que deseamos generar como ER de salida.  
2. Haga clic Eliminar.
3. Haga clic en Sí.
4. Haga clic en Nuevo.
5. Haga clic en Archivo.
6. Haga clic en Examinar. Desplácese y seleccione SampleVendPaymDocReport.docx que ha descargado anteriormente. Haga clic en Aceptar
    * Seleccione la plantilla que ha descargado en el paso anterior.  
7. En el campo Plantilla, especifique o seleccione un valor.

## <a name="extend-the-word-template-by-adding-a-custom-xml-part"></a>Aumente la plantilla de Word agregando una parte del XML personalizado
1. Haga clic en Guardar.
    * Además de almacenar cambios de configuración, la acción Guardar también actualiza la plantilla de Word adjunta. La estructura del formato diseñado se traslada al documento de Word adjunto como una nueva parte del XML personalizado con el nombre “Informe”. Tenga en cuenta que la plantilla de Word adjunta no sólo contiene el diseño del documento que deseamos para generar como salida de ER, sino que también contiene la estructura de datos que el ER rellenará en esta plantilla en el tiempo de ejecución.  
2. Haga clic en Archivos adjuntos.
    * Ahora necesita vincular los elementos de la parte XML personalizada del “Informe” a las partes del documento en Word.  
    * Si está familiarizado con los documentos de Word que se pueden diseñar como formularios que contienen los controles de contenido limitados con elementos de partes de XML personalizado: reproduzca todos los pasos de la subtarea siguiente para crear tal documento. Para obtener más detalles, vea este vínculo: https://support.office.com/en-us/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b?ui=en-US&rs=en-US&ad=US. Si no, omita todos los pasos de la subtarea siguiente.  

## <a name="get-word-with-custom-xml-part-to-do-data-bindings"></a>Consiga Word con la parte XML personalizada para realizar vínculos de datos
    * Abra este documento de Word y haga lo siguiente: Abra la pestaña Desarrollador de Word (personalizar la cinta de opciones si aún no está habilitada).  - Seleccione el panel de asignación XML.  - Seleccione el elemento XML personalizado del “Informe” en la búsqueda.  - Haga la asignación de los artículos de la parte XML seleccionada y de los controles de contenido del documento de Word.  - Guarde el documento de Word actualizado en una unidad local.  

## <a name="upload-the-word-template-with-custom-xml-part-bounded-to-content-controls"></a>Cargue la plantilla de Word con la parte XML personalizada para limitada a los controles de contenido
1. Haga clic Eliminar.
2. Haga clic en Sí.
    * Agregar una plantilla nueva. Si ha completado los pasos de la subtarea anterior, seleccione el documento de Word que ha preparado y guardado en una unidad local. Si no, seleccione la plantilla de MS Word SampleVendPaymDocReportBounded.docx que había descargado anteriormente.  
3. Haga clic en Nuevo.
4. Haga clic en Archivo.
5. Haga clic en Examinar. Desplácese y seleccione el SampleVendPaymDocReportBounded.docx que ha descargado anteriormente. Haga clic en Aceptar
6. En el campo Plantilla, seleccione el documento que ha descargado en el paso anterior.
7. Haga clic en Guardar.
8. Cierre la página.

## <a name="execute-the-format-to-create-word-output"></a>Ejecute el formato para crear una salida en Word
1. En el panel de acciones, haga clic en Configuraciones.
2. Haga clic en Parámetros de usuario.
3. Seleccione Sí en el campo Parámetros de ejecución.
4. Haga clic en Aceptar
5. Haga clic en Editar.
6. Seleccione Sí en el campo Borrador de ejecución.
7. Haga clic en Guardar.
8. Cierre la página.
9. Cierre la página.
10. Vaya a Proveedores > Pagos > Diario de pagos.
11. Haga clic en Líneas.
12. En la lista, active o desactive todas las filas.
13. Haga clic en Estado de pago.
14. Haga clic en Ninguna.
15. Haga clic en Generar pagos.
16. Haga clic en Aceptar
17. Haga clic en Aceptar
    * Analice la salida generada. Tenga en cuenta que la salida creada se presenta en formato de Word y contiene los detalles de los pagos procesados.  

