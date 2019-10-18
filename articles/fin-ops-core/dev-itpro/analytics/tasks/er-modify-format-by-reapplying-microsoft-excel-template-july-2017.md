---
title: Modificar formatos al aplicar de nuevo plantillas de Excel
description: Para completar estos pasos en este procedimiento, primero debe completar el procedimiento - Diseñar una configuración de ER para generar informes en formato OPENXML”.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 73f2c10d7462c4b52a2b36dd5f221593707d2f4f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184678"
---
# <a name="modify-formats-by-reapplying-excel-templates"></a>Modificar formatos al aplicar de nuevo plantillas de Excel

[!include [task guide banner](../../includes/task-guide-banner.md)]

Para completar estos pasos en este procedimiento, primero debe completar el procedimiento - Diseñar una configuración de ER para generar informes en formato OPENXML”.

Este procedimiento explica cómo modificar una configuración de formado del informe electrónico (ER) aplicando de nuevo una plantilla de Microsoft Excel que ha sido modificada. En este procedimiento, importará una plantilla modificade de Excel a la configuración de formato ER que ha sido creado por la empresa de ejemplo, Litware, Inc. y después generar documentos electrónicos. Este procedimiento se ha creado para los usuarios con los roles de Administrador del sistema o Desarrollador de informes electrónicos asignados. Estos pasos se pueden completar mediante el conjunto de datos de GBSI. Antes de empezar, descargue y guarde el archivo, SampleVendPaymWsReport2.xlsx, que se muestra en el tema de Ayuda, modifique el formato electrónico del informe reaplicando una plantilla de Excel (modify-electronic-reporting-format-reapply-excel-template/).

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como Activo. Si no ve a este proveedor de configuración, complete los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".  

## <a name="select-the-er-format"></a>Seleccionar formato del ER
1. Haga clic en Configuraciones de informes.
2. En el árbol, expanda "Modelo de pago".
3. En el árbol, seleccione "Modelo de pago\Informe de hoja de cálculo de muestra".
4. Haga clic en Archivos adjuntos.
    * Tenga en cuenta que el archivo de Excel SampleVendPaymWsReport.xlsx se usa actualmente como plantilla para el procesamiento del diario de pagos.   
5. Haga clic en Abrir.
    * Haga clic en Abrir para explorar el diseño de la plantilla de Excel.  
    * Revisar la plantilla. Tenga en cuenta que actualmente incluye los detalles siguientes para cada línea de pago: número de cuenta de proveedor, nombre del proveedor, banco, número de ruta, número de cuenta, débito, crédito y divisa. Para este ejemplo, deseamos ampliar esta lista agregando los detalles acerca de la fecha de pago.   
6. Cierre la página.

## <a name="reapply-a-new-excel-template-to-er-format"></a>Volver a aplicar una nueva plantilla de Excel al formato del ER
1. Haga clic en Diseñador.
    * Abra la versión de borrador del formato de ER para su edición.  
2. En el panel de acciones, haga clic en Importar.
3. Haga clic en Actualización desde Excel.
    * Haga clic en la “Actualizar plantilla" y seleccione el archivo SampleVendPaymWsReport2.xlsx.  
    * Haga clic Actualizar plantilla y busque el archivo descargado anteriormente SampleVendPaymWsReport2.xlsx.  
4. Haga clic en Aceptar
    * Se aplica la plantilla de SampleVendPaymWsReport2.xlsx. La estructura del formato del ER se sincroniza con el contenido de la plantilla, cuyos artículos se agregan al formato del ER. Cualquier elemento existente en el formato del ER que no se incluyan en la plantilla se quita de la definición del formato.  
5. En el árbol, seleccione "Excel".
    * Tenga en cuenta que el campo Plantilla ahora contiene una referencia a la nueva plantilla.   
6. Haga clic en Archivos adjuntos.
7. Haga clic en Abrir.
    * Haga clic en Abrir para explorar el diseño de la plantilla de Excel modificada.  
    * Revisar la plantilla. Tenga en cuenta que ahora incluye una línea para la fecha de pago.   
8. Cierre la página.
9. En el árbol, expanda "Excel".
10. En el árbol, expanda 'Excel\PaymLines'.
11. En el árbol, seleccione "Excel\LíneasPago\FechaPago".
    * Tenga en cuenta que el formato del ER ahora contiene un elemento más. Se han agregado una celda, PaymDate, a la plantilla de Excel.  
12. Haga clic en la ficha Asignación.
13. En el árbol , expanda "modelo".
14. En el árbol, expanda modelo\Pagos.
15. En el árbol, seleccione modelo\Pagos\Fecha de la transacción(TransactionDate).
16. Haga clic en Enlazar.
    * Especifique qué datos se agregan a la nueva celda en el tiempo de ejecución.  
17. Haga clic en Guardar.
18. Cierre la página.

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a>Habilitar la versión de borrador modificada del formato del ER para su uso en el procesamiento del diario de pagos
1. En el panel de acciones, haga clic en Configuraciones.
2. Haga clic en Parámetros de usuario.
3. Seleccione Sí en el campo Parámetros de ejecución.
4. Haga clic en Aceptar
5. Haga clic en Editar.
6. Seleccione Sí en el campo Borrador de ejecución.

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a>Usar la versión de borrador modificada del formato del ER para el procesamiento del diario de pagos
    * Revise la hoja de cálculo creada, incluido el nuevo detalle de líneas de pago – fecha de pago.  

