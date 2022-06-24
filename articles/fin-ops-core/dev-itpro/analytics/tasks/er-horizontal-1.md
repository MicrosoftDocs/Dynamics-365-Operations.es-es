---
title: 'ER Usar los intervalos horizontalmente ensanchables para agregar de forma dinámica columnas en Excel (Parte 1: Diseño de formato)'
description: Este artículo describe cómo configurar un formato de informes electrónicos (ER) para generar informes como archivos de hojas de cálculo OPENXML (Excel). (Parte 1)
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 157a486252d9447c2509fe5e05b02cf1684683fd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886744"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-1---design-format"></a>ER Usar los intervalos horizontalmente ensanchables para agregar de forma dinámica columnas en Excel (Parte 1: Diseño de formato)

[!include [banner](../../includes/banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un formato electrónico (ER) para generar informes mientras que los archivos de las hojas de cálculo de Excel (OPENXML) en los que las columnas necesarias se pueden crear de forma dinámica como intervalos horizontalmente ensanchables. Estos pasos se pueden llevar a cabo en cualquier empresa.

Para completar estos pasos, primero debe completar estas tres guías de tarea:

"ER Creación y activación de un proveedor de configuraciones"

"ER Usar dimensiones financieras como origen de datos (Parte 1: Modelo de datos de diseño)"

"ER Usar dimensiones financieras como origen de datos (Parte 2: Asignación de modelo)"

También debe descargar y guardar una copia local de la plantilla con un informe de ejemplo que se encuentra aquí, [Informe de ejemplo de servicio web de dimensiones financieras](https://download.microsoft.com/download/3/1/3/313e2090-bc0a-421f-bf96-c58da9bc0dea/SampleFinDimWsReport.xlsx).

Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.

## <a name="create-a-new-report-configuration"></a>Cree una nueva configuración del informe.

1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, seleccione `Financial dimensions sample model`.
3. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
4. En el campo Nuevo, escriba `Format based on data model Financial dimensions sample model`.
    * Use el modelo creado por adelantado como el origen de los datos para su nuevo informe.  
5. En el campo Nombre, escriba `Sample report with horizontally expandable ranges`.
    * Informe de ejemplo con intervalos ensanchables horizontalmente   
6. En el campo Descripción, escriba `To make Excel output with dynamically adding columns`,
    * Para generar un resultado en formato Excel con columnas agregadas dinámicamente   
7. En el campo Definición del modelo de datos, seleccione Entrada.
8. Haga clic en Crear configuración.

## <a name="design-the-report-format"></a>Diseñe el formato del informe.

1. Haga clic en Diseñador.
2. Encienda el botón de alternancia `Show details`.
3. En el panel de acciones, haga clic en Importar.
4. Haga clic en Importar desde Excel.
5. Haga clic en Archivos adjuntos.
    * Importe la plantilla del informe. Use el archivo de Excel que haya descargado para ello.  
6. Haga clic en Nuevo.
7. Haga clic en Archivo.
8. Cierre la página.
9. En el campo Plantilla, especifique o seleccione un valor.
    * Seleccione la plantilla descargada.  
10. Haga clic en Aceptar
    * Agregue un nuevo intervalo para crear dinámicamente un resultado en formato Excel con tantas columnas como haya seleccionado (en el formulario del cuadro de diálogo de usuario) para dimensiones financieras. Cada celda para cada columna representará un nombre de una sola dimensión financiera.  
11. Haga clic en Agregar para abrir el cuadro desplegable.
12. En el árbol, seleccione `Excel\Range`.
13. En el campo intervalo de Excel, introduzca `DimNames`.
    * DimNames  
14. En el campo de dirección Réplica, seleccione `Horizontal`.
15. Haga clic en Aceptar.
16. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
17. Haga clic en Subir.
18. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Cell<DimNames>`.
19. Haga clic en Cortar.
20. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
21. Haga clic en Pegar.
22. En el árbol, expanda `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
23. En el árbol, expanda `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`.
24. En el árbol, expanda `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
25. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
    * Agregue un nuevo intervalo para crear dinámicamente un resultado en formato Excel con tantas columnas como haya seleccionado (en el formulario del cuadro de diálogo de usuario) para dimensiones financieras. Cada celda para cada columna representará el valor de una sola dimensión financiera para cada transacción que se notifique.  
26. Haga clic en Agregar Intervalo.
27. En el campo intervalo de Excel, introduzca `DimValues`.
    * DimValues  
28. En el campo de dirección Réplica, seleccione `Horizontal`.
29. Haga clic en Aceptar.
30. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>`.
31. Haga clic en Cortar.
32. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.
33. Haga clic en Pegar.
34. En el árbol, expanda `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.

## <a name="map-format-elements-to-data-sources"></a>Asigne elementos de formato a orígenes de datos

1. Haga clic en la ficha Asignación.
2. En el árbol, expanda `model: Data model Financial dimensions sample model`.
3. En el árbol, expanda `model: Data model Financial dimensions sample model\Journal: Record list`.
4. En el árbol, expanda `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`.
5. En el árbol, expanda `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`.
6. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>`.
7. En el árbol, seleccione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String`.
8. Haga clic en Enlazar.
9. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal`.
10. En el árbol, seleccione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list`.
11. Haga clic en Enlazar.
12. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>`.
13. En el árbol, seleccione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real`.
14. Haga clic en Enlazar.
15. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>`.
16. En el árbol, seleccione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real`.
17. Haga clic en Enlazar.
18. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>`.
19. En el árbol, seleccione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String`.
20. Haga clic en Enlazar.
21. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>`.
22. En el árbol, seleccione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date`.
23. Haga clic en Enlazar.
24. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>`.
25. En el árbol, seleccione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String`.
26. Haga clic en Enlazar.
27. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>`.
28. En el árbol, seleccione `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`.
29. Haga clic en Enlazar.
30. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical`.
31. En el árbol, seleccione `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list`.
32. Haga clic en Enlazar.
33. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>`.
34. En el árbol, seleccione `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String`.
35. Haga clic en Enlazar.
36. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical`.
37. En el árbol, seleccione `model: Data model Financial dimensions sample model\Journal: Record list`.
38. Haga clic en Enlazar.
39. En el árbol, expanda `model: Data model Financial dimensions sample model\Dimensions setting: Record list`.
40. En el árbol, seleccione `model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String`.
41. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>`.
42. Haga clic en Enlazar.
43. En el árbol, seleccione `model: Data model Financial dimensions sample model\Dimensions setting: Record list`.
44. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal`.
45. Haga clic en Enlazar.
46. En el árbol, seleccione `Excel = "SampleFinDimWsReport"\Cell<CompanyName>`.
47. En el árbol, seleccione `model: Data model Financial dimensions sample model\Company: String`.
48. Haga clic en Enlazar.
49. Haga clic en Guardar.
50. Cierre la página.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
