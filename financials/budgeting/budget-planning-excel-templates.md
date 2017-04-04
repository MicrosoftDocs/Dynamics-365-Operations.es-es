---
title: "Plantillas de planificación de presupuesto para Excel"
description: "Este tema describe cómo crear plantillas de Microsoft Excel que se pueden utilizar con planes de presupuesto."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 0e2eb6e7c130f03edbf60a185d397d94b5d61d7d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-templates-for-excel"></a>Plantillas de planificación de presupuesto para Excel

Este tema describe cómo crear plantillas de Microsoft Excel que se pueden utilizar con planes de presupuesto.

Este tema muestra cómo crear plantillas de Excel que se usarán con planes de presupuestos mediante el conjunto de datos estándar de prueba y el inicio de sesión de usuario Admin. Para obtener más información sobre la planificación de presupuesto, consulte [el presupuesto se pondrán información general.] (budget-planning-overview-configuration.md) También puede configurar el presupuesto [101] planificados el budget-plan.md tutorial () para obtener principios de la configuración y el uso de módulo Básico.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Generar una hoja de cálculo mediante diseño de documento del plan del presupuesto
Los documentos del plan de presupuesto se pueden ver y editar mediante uno o varios diseños. Cada diseño puede tener una plantilla de documento asociada del plan del presupuesto para ver y editar los datos del plan del presupuesto en una hoja de cálculo de Excel. En este tema, una plantilla de documento de plan del presupuesto se generó mediante una configuración existente de diseño. Abra ** los planes de presupuesto que aparecen ** (** presupuestaria **&gt; ** los planes de presupuesto **). Haga clic en ** nuevo ** para crear un nuevo documento de plan del presupuesto. ![bpt1 [] (. /media/bpt11-1024x552.png])(. /media/bpt11.png) 

Los ** agregan ** la opción de líneas de agregar líneas. Haga clic en ** diseños ** ver la configuración del diseño de documento de plan del presupuesto. 
![bpt2 [] (. /media/bpt2-1024x274.png])(. /media/bpt2.png) 

Puede revisar la configuración de diseño y ajustarla según sea necesario. Ir ** plantilla ** &gt; ** generan ** crear un archivo de Excel para este diseño. Después de que se cree la plantilla, vaya ** plantilla ** &gt; ** la vista ** abrir y revisar la plantilla de documento de plan del presupuesto. Puede guardar el archivo de Excel con la unidad local. ![bpt3 [] (. /media/bpt3-1024x545.png])(. /media/bpt3.png) 

> [!NOTE] 
> El diseño de documento del plan de presupuesto no se puede editar después de una plantilla de Excel está asociada a ella. Para modificar el diseño, elimine el archivo de plantilla de Excel asociado y regenerelo. Esto es necesario conservar los campos del diseño y la hoja de cálculo sincronizan. 

La plantilla de Excel contendrá todos los artículos de diseño de documento de plan del presupuesto, donde ** disponible de la hoja de cálculo ** la columna se define como Verdadero. Superposición de los artículos no están permitidos en la plantilla de Excel. Por ejemplo, si el diseño contiene columnas de la solicitud Q1, de la solicitud, Q2 de la solicitud Q3, y de la solicitud Q4, y una columna total de la solicitud que representa una suma de las columnas 4 trimestrales, sólo las columnas trimestrales o la columna está disponible total que se use en la plantilla de Excel. El archivo de Excel no puede actualizar superponer columnas durante la actualización porque los datos de la tabla pueden quedar obsoleto y inexactos.

![bpt4 [] (. /media/bpt4-1024x615.png])(. /media/bpt4.png)

> [!NOTE] 
> Para evitar problemas de potencial con datos del plan del presupuesto de la Ver y editar, Excel mediante el mismo usuario se debe registrar en Dynamics 365 para las operaciones y el conector del complemento de los datos de la oficina de Microsoft Dynamics.

## <a name="add-a-header-to-budget-plan-document-template"></a>Agregar un encabezado a la plantilla de documento de plan del presupuesto
Para agregar información de encabezado, seleccione la fila superior en las filas del archivo vacías de Excel y de inserción. Haga clic en diseño ** ** en ** Connector de los datos ** para agregar campos de cabecera al archivo de Excel.

![bpt5 [] (. /media/bpt5-1024x615.png])(. /media/bpt5.png) 

En ** diseño ** la ficha, ** ** el clic ** ** agregue los campos y, a continuación BudgetPlanHeader ** ** como origen de datos de la entidad.

![bpt6 [] (. /media/bpt6-1024x615.png])(. /media/bpt6.png)

Designan el cursor a la ubicación deseada en el archivo de Excel. Haga clic en ** agregue la etiqueta ** para agregar la etiqueta de campo a la ubicación seleccionada. Seleccione ** agregue el valor ** para agregar el campo Valor al lugar seleccionado. Haga clic en ** hecho ** para cerrar el diseñador.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>![bpt7 [] (. /media/bpt7.png])(. /media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Agrega una columna calculada a la tabla de la plantilla de documento de plan del presupuesto
--------------------------------------------------------------

A continuación, las columnas calculadas se agregará a la plantilla de documento generada del plan del presupuesto. A ** solicitud total ** columna, que resume la solicitud Q1: Solicitar las columnas Q4, y ** ajuste ** una columna, que actualiza ** solicitud total ** la columna por un factor predefinido.

Haga clic en diseño ** ** en ** Connector de los datos ** para agregar columnas a la tabla. Haga clic en ** edición ** junto BudgetPlanWorksheet ** ** del origen de datos para iniciar columnas de suma.

![bpt8 [] (. /media/bpt8-1024x301.png])(. /media/bpt8.png) 

El grupo de campos seleccionados muestra las columnas disponibles en la plantilla. Haga clic en ** fórmula ** para agregar una nueva columna. Asignación de un nombre a la nueva columna y después pegue la fórmula en ** fórmula ** el campo. Haga clic en ** actualización ** para insertar la columna.

![bpt12 [] (. /media/bpt12-1024x565.png])(. /media/bpt12.png)

> [!NOTE] 
> Para definir la fórmula, crean la fórmula en la hoja de cálculo y, a continuación la copian ** diseño ** a la ventana. Una Dynamics 365 para la tabla enlazada las operaciones normalmente será denominada “AXTable1”. Por ejemplo, resumir la solicitud Q1: Solicitar las columnas Q4 en la hoja de cálculo, la fórmula =\]solicitud Q4 de la solicitud Q3\]\[+AxTable1 de la solicitud +AxTable1 Q2\]\[de la solicitud Q1\]\[+AxTable1 de AxTable1\[.

Repita estos pasos para insertar ** ajuste ** la columna. Use la solicitud\]\*$I$1 de la fórmula = del total de AxTable1\[para esta columna. Esto tomará el valor de la celda I1 multiplicará y los valores de sume ** la solicitud ** la columna para calcular los importes de ajuste.

Guardar y cerrar el archivo de Excel. Vuelva a Dynamics 365 para las operaciones, y en los diseños ** **, haga clic ** carga &gt; de la plantilla ** para cargar la plantilla de Excel guardada que se utilizará para el plan del presupuesto. 

![bpt10 [] (. /media/bpt10-1024x352.png])(. /media/bpt10.png) 

Cierre ** los diseños ** el control deslizante. En ** plan del presupuesto ** el documento, haga clic ** hoja de cálculo ** para ver y editar el documento en Excel. Tenga en cuenta que la plantilla de Excel ajustada se usó para crear esta hoja de cálculo de plan del presupuesto y las columnas calculadas mediante están actualizadas las fórmulas que se definieron en los pasos anteriores. 

![bpt11 [] (. /media/bpt111-1024x431.png])(. /media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Inclinan y engañan para crear plantillas del plan del presupuesto
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>¿Puedo agregar y utilizar orígenes de datos adicionales a una plantilla del plan del presupuesto?

Sí, puede usar ** diseño ** el menú para agregar las entidades adicionales la misma u hojas en la plantilla de Excel. Por ejemplo, puede agregar ** BudgetPlanProposedProject ** el origen de datos para crear y mantener una lista de proyectos propondrán al mismo tiempo al trabajar con datos del plan del presupuesto en Excel. Tenga en cuenta que incluidos orígenes de datos en grandes cantidades puede afectar al rendimiento del libro de Excel. 

Puede usar ** filtro ** la opción en ** Connector de los datos ** de agregar filtros deseados orígenes de datos adicionales.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>¿Puedo ocultar la opción de diseño de Business Connector de datos para otros usuarios?

Sí **, abra Connector de los datos ** las opciones de ocultar ** diseño ** la opción de otros usuarios.

![bpt13 [] (. /media/bpt13-1024x565.png])(. /media/bpt13.png)

Expanda ** opciones de Connector de los datos ** y borre ** permiso diseñar ** la casilla. Esto ocultará ** diseño ** la opción de ** Connector de los datos **.

![bpt14 [] (. /media/bpt14-1024x592.png])(. /media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>¿Puedo evitar que los usuarios cierren accidentalmente Business Connector de los datos mientras ejecuta datos?

Es recomendable bloquear de la plantilla para evitar que los usuarios cierren abrirlo. Para activar el bloqueo, haga clic en ** Connector de los datos **, en la esquina superior derecha que aparece una flecha. 

![bpt15 [] (. /media/bpt15-1024x285.png])(. /media/bpt15.png) 

Hace clic en la flecha para un menú adicional. Seleccione ** bloqueo **.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>![bpt16 [] (. /media/bpt16-1024x614.png])(. /media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>¿Puedo usar otras funciones de Excel, como formato de celda, colores, formato condicional, y gráficos mis con plantillas del plan del presupuesto?

Sí, la mayoría de las capacidades estándar de Excel funcionará en plantillas del plan del presupuesto. Recomendamos mediante la codificación del color para que los usuarios distingan entre las columnas de sólo lectura y puede editar. El formato condicional se puede usar para resaltar las áreas problemáticas de presupuesto. Los totales de la columna se pueden mostrar con facilidad mediante las fórmulas estándar de Excel sobre la tabla.

También puede crear y usar las tablas dinámicas y gráficos para las agrupaciones adicionales y las vistas de los datos del presupuesto. En ** los datos **, en la ficha ** las conexiones ** el grupo, haga clic ** actualizar todos **, y haga clic en ** las propiedades de conexión **. Haga clic en uso ** ** la ficha. En ** actualización **, seleccione ** actualice los datos al abrir el archivo ** la casilla. 

![bpt17 [] (. /media/bpt17-1024x614.png])(. /media/bpt17.png)


