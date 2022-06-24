---
title: Plantillas de planificación presupuestaria para Excel
description: Este artículo describe cómo crear plantillas de Microsoft Excel que se puedan utilizar con planes presupuestarios.
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: kfend
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6bc190a48d0212e24c5bd72255ed6b6b3caf942c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872510"
---
# <a name="budget-planning-templates-for-excel"></a>Plantillas de planificación presupuestaria para Excel

[!include [banner](../includes/banner.md)]

Este artículo describe cómo crear plantillas de Microsoft Excel que se puedan utilizar con planes presupuestarios.

Este artículo muestra cómo crear plantillas de Excel que se usarán con planes presupuestarios mediante el conjunto de datos de demostración estándar y el inicio de sesión de usuario Admin. Para obtener más información sobre la planificación presupuestaria, consulte [Visión general de la planificación presupuestaria](budget-planning-overview-configuration.md). También puede seguir el tutorial [Planificación presupuestaria](budget-plan.md) para aprender los principios básicos de la configuración y el uso de módulos.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Generación de una hoja de cálculo mediante el diseño del documento de plan presupuestario

Los documentos de plan presupuestario se pueden ver y editar mediante uno o varios diseños. Cada diseño puede tener una plantilla de documento de plan presupuestario asociada para ver y editar los datos del plan presupuestario en una hoja de cálculo de Excel. En este artículo, una plantilla de documento de plan presupuestario se generará empleando una configuración de diseño existente. 

1. Abra la **Lista de planes presupuestarios** (**Gestión presupuestaria** &gt; **Planes presupuestarios**). 
2. Haga clic en **Nuevo** para crear un documento de plan presupuestario. 

   [![Lista de planes presupuestarios.](./media/bpt11-1024x552.png)](./media/bpt11.png) 

3. Emplee la opción de línea **Agregar** para agregar líneas. Haga clic en **Diseños** para ver la configuración del diseño de documento de plan presupuestario. 

   [![Agregar planes presupuestarios.](./media/bpt2-1024x274.png)](./media/bpt2.png) 

Puede revisar la configuración de diseño y ajustarla según sea necesario. 
1. Vaya a **Plantilla** &gt; **Generar** para crear un archivo de Excel para este diseño. 
2. Después de que se cree la plantilla, vaya a **Plantilla** &gt; **Ver** para abrir y revisar la plantilla de documento de plan presupuestario. Puede guardar el archivo de Excel en la unidad local. 

[![Guardar como.](./media/bpt3-1024x545.png)](./media/bpt3.png)

> [!NOTE] 
> El diseño de documento del plan presupuestario no se puede editar después de asociarle una plantilla de Excel. Para modificar el diseño, elimine el archivo de plantilla de Excel asociado y regenérelo. Esto es necesario para mantener sincronizados los campos del diseño y la hoja de cálculo. 

La plantilla de Excel contendrá todos los elementos del diseño de documento de plan presupuestario en los que la columna **Disponible en la hoja de cálculo** se haya definido como Verdadero. Los elementos superpuestos no están permitidos en la plantilla de Excel. Por ejemplo, si el diseño contiene las columnas Solicitud de primer trimestre, Solicitud de segundo trimestre, Solicitud de tercer trimestre y Solicitud de cuarto trimestre y una columna con el total de las solicitudes que representa una suma de las 4 columnas trimestrales, solo las columnas trimestrales o la columna total estarán disponibles para su empleo en la plantilla de Excel. El archivo de Excel no puede actualizar las columnas superpuestas durante la actualización porque los datos de la tabla pueden quedar obsoletos e inexactos.

> [!NOTE] 
> Para evitar posibles problemas con la visualización y edición de los datos del plan presupuestario con Excel, el mismo usuario se debe registrar en Microsoft Dynamics 365 Finance y el conector de datos del complemento de Office para Microsoft Dynamics.

## <a name="add-a-header-to-budget-plan-document-template"></a>Agregar un encabezado a la plantilla de documento de plan presupuestario
Para agregar información de encabezado, seleccione la fila superior en el archivo de Excel e inserte las filas vacías. Haga clic en **Diseño** en el **Conector de datos** para agregar campos de cabecera al archivo de Excel.

En la pestaña **Diseño** haga clic en los campos **Agregar** y seleccione **BudgetPlanHeader** como origen de datos de entidad.

Coloque el cursor en la ubicación deseada del archivo de Excel. Haga clic en **Agregar etiqueta** para agregar la etiqueta de campo a la ubicación seleccionada. Seleccione **Agregar valor** para agregar el campo de valor al lugar seleccionado. Haga clic en **Listo** para cerrar el diseñador.

## <a name="select-add-valuemediabpt7png"></a>[![Seleccionar Agregar valor.](./media/bpt7.png)](./media/bpt7.png)

## <a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Agregue una columna calculada a la tabla de plantillas de documento de plan presupuestario

A continuación, las columnas calculadas se agregará a la plantilla de documento de plan presupuestario generada. Una columna **Total de la solicitud** que suma las columnas Solicitud de primer trimestre: Solicitud de cuarto trimestre y una columna **Ajuste** que recalcula la columna **Total de la solicitud** con un factor predefinido.

Haga clic en **Diseño** en el **Conector de datos** para agregar columnas a la tabla. Haga clic en **Editar** junto al origen de datos **BudgetPlanWorksheet** para comenzar a agregar columnas.

[![Comenzar a agregar columnas.](./media/bpt8-1024x301.png)](./media/bpt8.png) 

El grupo de campos seleccionado muestra las columnas disponibles en la plantilla. Haga clic en **Fórmula** para agregar una nueva columna. Designe un nombre a la nueva columna y copie la fórmula en el campo **Fórmula**. Haga clic en **Actualizar** para insertar la columna.

[![Agregar y insertar columnas.](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> Para definir la fórmula, cree la fórmula en la hoja de cálculo y, a continuación, cópiela en la ventana **Diseño**. Una tabla enlazada de Finance and Operations normalmente se denominará "AXTable1". Por ejemplo, para sumar las columnas Solicitud de primer trimestre : Solicitud de cuarto trimestre en la hoja de cálculo; la fórmula = AxTable1\[Solicitud primer trimestre\]+AxTable1\[Solicitud segundo trimestre\]+AxTable1\[Solicitud tercer trimestre\]+AxTable1\[Solicitud cuarto trimestre\].

Repita estos pasos para insertar la columna **Ajuste**. Use la fórmula = AxTable1\[Total de la solicitud\]\*$I$1 para esta columna. Esto tomará el valor de la celda I1 y multiplicará los valores de la columna **Total de la solicitud** para calcular los importes de ajuste.

Guarde y cierre el archivo de Excel. En **Diseños** haga clic en clic **Plantilla &gt; Cargar** para cargar la plantilla de Excel guardada que se utilizará para el plan presupuestario. 

[![Cargar plantilla de Excel.](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Cierre el control deslizante **Diseños**. En el documento **Plan presupuestario**, haga clic en **Hoja de cálculo** para ver y editar el documento en Excel. Tenga en cuenta que la plantilla de Excel ajustada se usó para crear esta hoja de cálculo de plan presupuestario y las columnas calculadas están actualizadas con las fórmulas que se definieron en los pasos anteriores. 

[![Ver y editar documento en Excel.](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Trucos para crear plantillas de plan presupuestario
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>¿Puedo agregar y utilizar orígenes de datos adicionales para una plantilla de plan presupuestario?

Sí, puede usar el menú **Diseño** para agregar entidades adicionales a la misma o a otras hojas en la plantilla de Excel. Por ejemplo, puede agregar el origen de datos **BudgetPlanProposedProject** para crear y mantener una lista de proyectos propuestos al mismo tiempo al trabajar con datos del plan presupuestario en Excel. Tenga en cuenta que incluir orígenes de datos de gran volumen puede afectar al rendimiento del libro de Excel. 

Puede usar la opción **Filtro** en **Conector de datos** de agregar los filtros deseados a orígenes de datos adicionales.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>¿Puedo ocultar la opción Diseño en el Conector de datos para otros usuarios?

Sí, abra las opciones del **Conector de datos** para ocultar la opción **Diseño** de otros usuarios.

[![Abrir opciones de conector de datos.](./media/bpt13-1024x565.png)](./media/bpt13.png)

Expanda las opciones de **Conector de datos** y desmarque la casilla de verificación **Habilitar diseño**. Esto ocultará la opción de **Diseño** del **Conector de datos**.

[![Opción de ocultar diseños de conector de datos.](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>¿Puedo evitar que los usuarios cierren accidentalmente el Conector de datos mientras trabajan con los datos?

Es recomendable bloquear la plantilla para evitar que los usuarios la cierren. Para activar el bloqueo, haga clic en **Conector de datos**; en la esquina superior derecha aparece una flecha. 

[![Activar el bloqueo.](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Haga clic en la flecha para un menú adicional. Seleccione **Bloquear**.

### <a name="select-lockmediabpt16png"></a>[![Seleccione Bloquear.](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>¿Puedo usar otras funciones de Excel, como formato de celda, colores, formato condicional y gráficos mis con plantillas del plan presupuestario?

Sí, la mayoría de las capacidades estándar de Excel funcionarán en las plantillas de plan presupuestario. Recomendamos usar la codificación de color para que los usuarios distingan entre las columnas de solo lectura y las editables. El formato condicional se puede usar para resaltar las áreas problemáticas del presupuesto. Los totales de las columnas se pueden mostrar con facilidad mediante las fórmulas estándar de Excel sobre la tabla.

También puede crear y usar las tablas dinámicas y gráficos para agrupaciones adicionales y visualizaciones de los datos presupuestarios. En la ficha **Datos**, en el grupo **Conexiones**, haga clic en **Actualizar todo** y, a continuación, en **Propiedades de conexión**. Haga clic en la pestaña **Uso**. En **Actualización**, seleccione la casilla **Actualizar datos al abrir el archivo**. 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
