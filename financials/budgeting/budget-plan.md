---
title: "Planificación presupuestaria"
description: "El objetivo de esta práctica es proporcionar una vista dirigida de Microsoft Dynamics 365 para las actualizaciones de la funcionalidad de las operaciones en el área de planificación de presupuesto. El objetivo de este laboratorio es presentar un ejemplo de configuración rápida del módulo de planificación presupuestaria y mostrar cómo se puede llevar a cabo la planificación presupuestaria con esta configuración.  Esta práctica se centrará específicamente en los procesos de negocio o las siguientes tareas - )que crean la jerarquía organizativa para proceso de planificación que crea y que activa de seguridad del usuario de planificación y de configuración de Presupuesto - definiendo escenarios de plan del presupuesto, columnas del plan del presupuesto, formatos y plantillas de Excel del presupuesto - creando el documento del plan del presupuesto en actuals extrayendo de la contabilidad general - mediante asignaciones en los datos del documento de plan del presupuesto de ajuste - datos del documento del plan del presupuesto de edición en Excel"
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 81b44aa7af3a05ebc28963f406fab98bfbbb340d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning"></a>Planificación presupuestaria

El objetivo de esta práctica es proporcionar una vista dirigida de Microsoft Dynamics 365 para las actualizaciones de la funcionalidad de las operaciones en el área de planificación de presupuesto. El objetivo de este laboratorio es presentar un ejemplo de configuración rápida del módulo de planificación presupuestaria y mostrar cómo se puede llevar a cabo la planificación presupuestaria con esta configuración.  Esta práctica se centrará específicamente en los procesos de negocio o las siguientes tareas - )que crean la jerarquía organizativa para proceso de planificación que crea y que activa de seguridad del usuario de planificación y de configuración de Presupuesto - definiendo escenarios de plan del presupuesto, columnas del plan del presupuesto, formatos y plantillas de Excel del presupuesto - creando el documento del plan del presupuesto en actuals extrayendo de la contabilidad general - mediante asignaciones en los datos del documento de plan del presupuesto de ajuste - datos del documento del plan del presupuesto de edición en Excel 

<a name="prerequisites"></a>Requisitos previos 
------------------

Para este tutorial, deberá tener acceso a Dynamics 365 del entorno de las operaciones con datos de prueba de Contoso, y se aprovisione como administrador en la instancia. No use en privado el modo de explorador para esta práctica - firme salida de cualquier otra cuenta en el explorador si es necesario y en firme con Dynamics 365 para los credenciales de administrador de las operaciones. Al firmar en Dynamics 365 para las operaciones, se DEBA ** ** comprueba “me mantiene en firmado” casilla de verificación. Esto crea una cookie persistente que la aplicación Excel necesita actualmente. Si el iniciar sesión a Dynamics 365 para las operaciones mediante un explorador distinto de IE, se le solicitará que iniciar sesión dentro de la aplicación de Excel. Al hacer clic en "Iniciar sesión" en la aplicación Excel, se abrirá una ventana emergente de IE y al iniciar sesión **DEBE** activar la casilla "Mantener la sesión iniciada". Si al hacer clic en "Iniciar sesión” en la aplicación Excel no parece hacer nada, debe borrar la caché de cookies de IE.

## <a name="scenario-overview"></a>**Scenario overview**
Julia funciona como director de finanzas en Contoso Entertainment Systems en Alemania (DEMF). Conforme se acerca el AF2016, necesita trabajar en la configuración del presupuesto de la empresa durante el próximo año. La preparación del presupuesto se parece a lo siguiente:

1.  Julia usa los importes de los valores reales del año anterior como punto de partida para crear el presupuesto.
2.  En función de los valores reales del año anterior, crea estimaciones para 12 meses del próximo año.
3.  Julie revisa el presupuesto con el director financiero. Una vez que ha hecho esto, realiza los ajustes necesarios para el plan presupuestario y finaliza la preparación del presupuesto.

Presupueste el esquema de la configuración de planificación para las tendrá una apariencia del escenario siguiente modo:

![Tiro de 1 Pantalla](./media/screenshot1-300x152.png)

Julie utiliza la plantilla de Excel siguiente para preparar el presupuesto:

[![](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

<a name="exercise-1-configuration"></a>Ejercicio 1: Configuración
=========================

## <a name="task-1-create-organizational-hierarchy"></a>** Tarea 1: Crear la jerarquía organizativa **
Como todo el proceso presupuestario se produce en el departamento de finanzas, Julie necesita crear una jerarquía organizativa muy simple, que conste solo del departamento de finanzas. 1.1. Vaya a las jerarquías organizativas (jerarquías organizativas de las organizaciones &gt; de administración &gt; de la organización) y haga clic en el botón

![Tiro de 3 Pantalla](./media/screenshot3.png) 

1.2. Escriba el nombre para la jerarquía organizativa y haga clic en el propósito de la asignación del botón

![Screenshot4 [] (. captura de 4.png /media/screen])(. captura de 4.png /media/screen) 

1.3. El propósito de planificación seleccione de presupuesto, haga clic en el botón agregar y asignar jerarquía organizativa recién creada: 

![Screenshot5 [] (. captura de 5.png /media/screen])(. captura de 5.png /media/screen)

1.4. Repita el paso anterior para el propósito organizativo de seguridad. Cierre el formulario cuando termine.

![Screenshot6 [] (. captura de 6.png /media/screen])(. captura de 6.png /media/screen)

1.5. En el formulario Jerarquías organizativas, haga clic en el botón Ver. Haga clic en Editar en el Diseñador de jerarquías y cree una jerarquía haciendo clic en el botón Insertar.

![Screenshot7 [] (. captura de 7.png /media/screen])(. captura de 7.png /media/screen) 

1.6. Seleccione el departamento de finanzas para la jerarquía de presupuesto. 

![Screenshot8 [] (. captura de 8.png /media/screen])(. captura de 8.png /media/screen)

1.7. Cuando haya acabado, haga clic en el botón Publicar y cerrar. Seleccione 1/1/2015 como fecha de vigencia para la publicación de la jerarquía.

![Screenshot9 [] (. captura de 9.png /media/screen])(. captura de 9.png /media/screen)

## <a name="task-2-configure-user-security"></a>Tarea 2: Configurar seguridad de usuario
La planificación presupuestaria usa directivas especiales de seguridad para configurar el acceso a los datos de planes presupuestarios. Julia necesita darse acceso a los planes presupuestarios de finanzas a ella misma. 2.1. Cambiar el contexto de la entidad jurídica de DEMF:![Screenshot10 [] (. captura de 10.png /media/screen])(. captura 10.png) de 2.2 /media/screen. Vaya a la &gt; gestión presupuestaria la configuración &gt; de instalación de planificación &gt; de presupuesto de planificación de presupuesto. En ficha de los parámetros, establezca el valor del modelo de seguridad en función de las organizaciones de seguridad![Screenshot11 [] (. captura de 11.png /media/screen])(. captura 11.png) de 2.3 /media/screen. Vaya a los usuarios de los usuarios &gt; de administración &gt; del sistema. Dele al usuario administrador (Julia Funderburk) el rol de Administrador presupuestario. ![Screenshot12 [] (. captura de 12.png /media/screen])(. captura 12.png) de 2.4 /media/screen. Organizaciones de asignación del rol de usuario y haga clic en la selección de![Screenshot13 [] (. captura de 13.png /media/screen])(. captura 13.png) de 2.5 /media/screen. Seleccione "Conceder acceso a organizaciones específicas". Seleccione la jerarquía organizativa creada en el primer paso. Esta Seleccionar el nodo de las finanzas y haga clic en la concesión con el *** del botón de los hijos importante! *** * – Asegúrese de que esté en contexto de la entidad jurídica de DEMF al realizar esta tarea, como seguridad de organización se aplica por el entity* legal![Screenshot14 [] (. captura de 14.png /media/screen])(. captura de 14.png /media/screen)

## <a name="task-3-create-scenarios"></a>Tarea 3: Crear escenarios
3.1. Vaya a la configuración&gt;&gt; de planificación de presupuesto &gt; de planificación de presupuesto de BudgetingSetup. En la página Situaciones observe los escenarios que vamos a usar más en este laboratorio: Reales del año anterior y Presupuestado. *Nota: Puede crear nuevos escenarios para este ejercicio si lo desea y usarlos en su lugar.* ![Screenshot15 [] (. captura de 15.png /media/screen])(. *Note de captura de 15.png /media/screen): Julie ya que no usa el proceso de aprobación formal para la preparación de presupuesto, omitir las etapas de flujos de trabajo, las etapas y el flujo de trabajo configuradas en esta práctica y utilizaremos la configuración existente para el automática permite aprobar el flujo de trabajo. Consulte el apéndice para este flujo de trabajo configuration.*

## <a name="task-4-create-budget-plan-columns"></a>Tarea 4: Crear columnas del plan presupuestario
Las columnas del plan presupuestario son las columnas monetarias o basadas en cantidad que se pueden usar en el diseño del documento de plan presupuestario. En nuestro ejemplo necesitamos crear una columna para Reales del año anterior y 12 columnas para representar cada mes en un año presupuestado. Para crear columnas, basta con hacer clic en el botón Agregar y rellenar los valores o mediante Entidad de datos. En este laboratorio usaremos Entidad de datos para rellenar los valores. 4.1. En presupuesto&gt;&gt; de planificación de presupuesto &gt; de BudgetingSetup planificados la página de las columnas abierto de la configuración. Botón de la oficina del clic en la esquina superior derecha de las columnas del formulario y de selección (sin filtrar![) [] (Screenshot16. captura de 16.png /media/screen])(. captura 16.png) de 4.2 /media/screen. El sistema abrir el libro de Excel para usarlo para rellenar los valores. Si se le solicite, haga clic en para habilitar la edición y para confiar esta aplicación![Screenshot18 [] (. captura de 18.png /media/screen])(. captura 18.png) [Screenshot17![/media/screen] de (. captura de 17.png /media/screen])(. captura 17.png) de 4.3 /media/screen. Necesitaremos más columnas completar los valores. Haga clic en el diseño del panel del lado derecho para agregar columnas a la cuadrícula:![Screenshot19 [] (. captura de 19.png /media/screen])(. captura 19.png) de 4.4 /media/screen. Haga clic en bajo botón de lápiz situado junto a PlanColumns para ver columnas disponibles para agregar a la cuadrícula![Screenshot20 [] (. captura de 20.png /media/screen])(. captura 20.png) de 4.5 /media/screen. Haga doble clic en cada campo disponible para agregarlas a los campos seleccionados y haga clic en la actualización Screenshot21![[] (. captura de 21.png /media/screen])(. captura 21.png) de 4.6 /media/screen. En la tabla de Excel agregue todas las columnas que se deben crear. Use la característica Autorrellenar de Excel para agregar líneas rápidamente. Asegúrese de que las líneas estén agregadas como parte de la tabla (al utilizar el desplazamiento vertical, debe tener acceso encabezados de columna en la parte superior de la cuadrícula)![Screenshot22 [] (. captura de 22.png /media/screen])(. captura 22.png) de 4.7 /media/screen. Vuelva a Dynamics 365 para las operaciones y actualizar la página. Los valores publicarán aparecerán en Dynamics 365 para las operaciones. ![Screenshot23 [] (. captura de 23.png /media/screen])(. captura de 23.png /media/screen)

## <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Tarea 5: Crear plantillas y diseños de documentos de plan presupuestario
El diseño define el aspecto que tendrá la cuadrícula de líneas de documento del plan presupuestario cuando el usuario abra el documento del plan presupuestario. También es posible cambiar el diseño para el documento del plan presupuestario para ver los mismos datos en distintos ángulos. Ahora, como tiene columnas definidas para usarlas con nuestro documento de plan presupuestario, Julia necesita crear un diseño de documento de plan presupuestario, que sería similar a la tabla de Excel que usa para crear datos de presupuesto (consulte la sección Visión general del escenario en este laboratorio) 5.1. En página&gt;&gt; abierto de los diseños &gt; de la configuración de planificación de presupuesto de planificación de presupuesto de BudgetingSetup. Cree un nuevo diseño de la entrada de presupuesto mensual:

-   Seleccione el conjunto de dimensiones de MA+BU para incluir cuentas principales y unidades de negocio en el diseño.
-   Muestre todas las columnas del plan de presupuesto creadas en el paso anterior en la sección Elementos. Haga todo excepto Reales del año anterior editable.
-   Haga clic en el botón Descripciones para seleccionar qué dimensiones financieras deben mostrar Descripciones en la cuadrícula.

![Screenshot24 [] (. captura de 24.png /media/screen])(. /media/screen tiró) 24.png basado en la definición del diseño del plan de presupuesto que podemos crear una plantilla de Excel que se utilizará como una forma alternativa para editar los datos presupuestarios. Como la plantilla de Excel tiene que coincidir con la definición de diseño del plan presupuestario, no podrá editar el diseño del plan presupuestario tras la generación de la plantilla de Excel; por tanto, esta tarea se debe realizar una vez que se definen todos los componentes de diseño. 5.2. Para creado el diseño de los 5.1. el paso, plantilla del &gt; botón genera. Confirme el mensaje de advertencia. Para ver la plantilla, haga clic en Vista &gt; de la plantilla. *Note: Asegúrese de a la “seleccione Guardar como” y seleccione el lugar en el que la plantilla se debe almacenar para editarla. Si el usuario selecciona “Abrir” en el diálogo, sin guardar los cambios realizados al archivo no se retenidos cuando el archivo es closed.* ![Screenshot25 [] (. captura de 25.png /media/screen])(. captura 25.png) de 5.3 /media/screen. &lt; El paso opcional&gt; modifica la plantilla de Excel para crear más parece que convivial – agregar las fórmulas totales, campos de cabecera, los formato, etc. guarde los cambios y cargan el archivo para la gestión presupuestaria el diseño del plan haciendo clic en la carga &gt; de diseño![Screenshot26 [] (. captura de 26.png /media/screen])(. captura de 26.png /media/screen)

## <a name="task-6-create-a-budget-planning-process"></a>Tarea 6: Crear un proceso de planificación presupuestaria
Julia necesita crear y activar un nuevo proceso de planificación presupuestaria combinando toda la configuración anterior para empezar a introducir planes presupuestarios. El proceso de planificación presupuestaria define qué organizaciones presupuestarias, flujo de trabajo, diseños y plantillas se usarán para crear planes presupuestarios. 6.1. Vaya a la &gt; gestión presupuestaria proceso &gt; de planificación de configuración del presupuesto &gt; de planificación de presupuesto y cree un registro nuevo.

-   Proceso de planificación presupuestaria – Gestión presupuestaria DEMF AF2016
-   Ciclo presupuestario – AF2016
-   Libro mayor – DEMF
-   Estructura contable predeterminada – Fabricación P&G
-   Jerarquía organizativa – seleccionar la jerarquía creada al principio del laboratorio
-   Flujo de trabajo de planificación presupuestaria – asignar flujo de trabajo de Aprobación automática para el departamento de finanzas
-   En reglas y plantillas de la etapa de planificación presupuestaria, para cada etapa de planificación presupuestaria del flujo de trabajo seleccione si se permite la adición y modificación de línea y qué diseño se debe usar de manera predeterminada

*Nota: Puede crear diseños de documentos adicionales y asignarlos para que estén disponibles en la etapa de flujo de trabajo de planificación presupuestaria haciendo clic en el botón Diseños alternativos.* ![Screenshot27 [] (. captura de 27.png /media/screen])(. captura 27.png) de 6.2 /media/screen. Las acciones seleccionar &gt; activadas para activar el flujo de trabajo de planificación de presupuesto![Screenshot28 [] (. captura de 28.png /media/screen])(. captura de 28.png /media/screen)

<a name="exercise-2-process-simulation"></a>Ejercicio 2: Simulación del proceso
==============================

## <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Tarea 7: Generar datos iniciales para el plan presupuestario desde Contabilidad general
7.1. Desplácese al presupuesto &gt; periódico &gt; generan plan del presupuesto de contabilidad general. Rellene los parámetros de proceso periódicos y haga clic en el botón Generar. ![Screenshot29 [] (. captura de 29.png /media/screen])(. captura 29.png) de 7.2 /media/screen. Vaya a los planes &gt; de presupuesto para encontrar un plan del presupuesto creado por el proceso campos. ![Screenshot30 [] (. captura de 30.png /media/screen])(. captura 30.png) de 7.3 /media/screen. Abra detalles del documento haciendo clic en el hipervínculo Número de documento. El plan de presupuesto se muestra como se define en el diseño creado durante esta práctica![Screenshot31 [] (. captura de 31.png /media/screen])(. captura de 31.png /media/screen)

## <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Tarea 8: Crear presupuesto de año actual en función de los valores reales del año anterior
Los métodos de asignación se pueden usar en el plan presupuestario para copiar información con facilidad para planes presupuestarios desde un escenario a otro/distribuirlos entre períodos/asignarlos a dimensiones. Usaremos asignaciones para crear el presupuesto del año actual a partir de los valores reales del año anterior. 8.1. Seleccionar todas las líneas de la cuadrícula del documento de plan del presupuesto y el hacer clic en un botón asigna el presupuesto Screenshot32![[] (. captura de 32.png /media/screen])(. captura 32.png) de 8.2 /media/screen. Seleccione el método de asignación, clave de período, origen y los escenarios y haga clic en de destino asignan 

![Screenshot33 [] (. captura de 33.png /media/screen])(. captura de 33.png /media/screen)

Los importes reales del año anterior se copiarán al presupuesto del año actual y asignarlos a los períodos mediante la clave de período de las curvas de ventas. 

![Screenshot34 [] (. captura de 34.png /media/screen])(. captura de 34.png /media/screen)

## <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Tarea 9: Ajustar documento de plan presupuestario con Excel y finalizar el documento
9.1. Haga clic en la hoja de cálculo del botón en el contenido del documento abiertas en Excel

![Screenshot35 [] (. captura de 35.png /media/screen])(. captura de 35.png /media/screen)

9.2. Cuando se abra el libro de Excel, ajuste los números en el documento del plan presupuestario y haga clic en el botón Publicar.

![Screenshot36 [] (. captura de 36.png /media/screen])(. captura de 36.png /media/screen)

9.3. Devolver al documento de plan del presupuesto en Dynamics 365 para las operaciones. El flujo de trabajo de clic &gt; en Enviar Crear automáticamente para aprobar el documento

![Screenshot37 [] (. captura de 37.png /media/screen])(. captura de 37.png /media/screen) 

Una vez que el flujo de trabajo completado, los cambios de la fase de documento de plan del presupuesto a aprobado. ![Screenshot38 [] (. captura de 38.png /media/screen])(. captura de 38.png /media/screen)

<a name="appendix"></a>Apéndice
========

### <a name="auto-approve-workflow-configuration"></a>Aprobar automáticamente la configuración del flujo de trabajo

A. Los flujos &gt;&gt; de trabajo de Gestión presupuestaria de la configuración de la gestión presupuestaria de &gt; planificación de presupuesto cree un nuevo flujo de trabajo mediante flujos de trabajo de planificación de presupuesto de plantillas:

![Screenshot39 [] (. captura de 39.png /media/screen])(. captura de 39.png /media/screen)

Este flujo de trabajo sólo contendrá una tarea – efectúe el plan del presupuesto de la transición 

![Screenshot40 [] (. captura de 40.png /media/screen])(. captura de 40.png /media/screen) 

Guardar y activar flujo de trabajo. 

B. Vaya a la &gt; gestión presupuestaria la configuración &gt; de instalación de planificación &gt; de presupuesto de planificación de presupuesto. En ficha de las etapas cree 2 – etapas de inicio y enviadas 

![Screenshot41 [] (. captura de 41.png /media/screen])(. captura de 41.png /media/screen)

C. Vaya a la &gt; gestión presupuestaria la configuración &gt; de instalación de planificación &gt; de presupuesto de planificación de presupuesto. En ficha de las etapas del flujo de trabajo asociar el automática del flujo de trabajo permite aprobar creado en el paso de A con la inicial de las etapas y enviado 

![Screenshot42 [] (. captura de 42.png /media/screen])(. captura de 42.png /media/screen)  


