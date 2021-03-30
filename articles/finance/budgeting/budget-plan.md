---
title: Planificación presupuestaria
description: El objetivo de este laboratorio es proporcionar una visita guiada de las actualizaciones de funcionalidades de Microsoft Dynamics 365 Finance en el área de planificación presupuestaria. El objetivo de este laboratorio es presentar un ejemplo de configuración rápida del módulo de planificación presupuestaria y mostrar cómo se puede llevar a cabo la planificación presupuestaria con esta configuración.
author: ShylaThompson
manager: AnnBe
ms.date: 06/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 10763
ms.assetid: 0f2ba752-1f6d-4f28-b9e9-b2e97d10b6d1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 05de2748b0cf7a2b09618aee5c41c8c797f2b3d3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210418"
---
# <a name="budget-planning"></a>Planificación presupuestaria

[!include [banner](../includes/banner.md)]

El objetivo de este laboratorio es proporcionar una visita guiada de las actualizaciones de funcionalidades de Microsoft Dynamics 365 Finance en el área de planificación presupuestaria. El objetivo de este laboratorio es presentar un ejemplo de configuración rápida del módulo de planificación presupuestaria y mostrar cómo se puede llevar a cabo la planificación presupuestaria con esta configuración.  Este laboratorio se centrará específicamente en los siguientes procesos empresariales o tareas:
- Creación de una jerarquía organizativa para planificación presupuestaria y configuración de la seguridad del usuario
- Definición de escenarios de planes presupuestarios, columnas de planes presupuestarios, diseños y plantillas de Excel
- Creación y activación del proceso de planificación presupuestaria
- Creación de documentos del plan presupuestario insertando datos reales desde contabilidad general
- Uso de asignaciones para ajustar datos de documentos de plan presupuestario
- Edición de datos de documentos de plan presupuestario en Excel 

<a name="prerequisites"></a>Requisitos previos 
------------------

Para este tutorial, deberá tener acceso al entorno de Microsoft Dynamics 365 Finance con datos de demostración de Contoso, y se aprovisionará como administrador en la instancia. No use el modo de explorador privado para este laboratorio; cierre sesión de cualquier otra cuenta en el explorador si lo necesita e inicie sesión con las credenciales de administrador. Al iniciar sesión, **DEBE** activar la casilla "Mantener la sesión iniciada". Esto crea una cookie persistente que la aplicación Excel necesita actualmente. Si inicia sesión en la aplicación con un explorador distinto de IE, le pedirá que inicie sesión dentro de la aplicación Excel. Al hacer clic en "Iniciar sesión" en la aplicación Excel, se abrirá una ventana emergente de IE y al iniciar sesión **DEBE** activar la casilla "Mantener la sesión iniciada". Si al hacer clic en "Iniciar sesión” en la aplicación Excel no parece hacer nada, debe borrar la caché de cookies de IE.

## <a name="scenario-overview"></a>**Visión general del escenario**
Julia funciona como director de finanzas en Contoso Entertainment Systems en Alemania (DEMF). Conforme se acerca el AF2016, necesita trabajar en la configuración del presupuesto de la empresa durante el próximo año. La preparación del presupuesto se parece a lo siguiente:

1.  Julia usa los importes de los valores reales del año anterior como punto de partida para crear el presupuesto.
2.  En función de los valores reales del año anterior, crea estimaciones para 12 meses del próximo año.
3.  Julie revisa el presupuesto con el director financiero. Una vez que ha hecho esto, realiza los ajustes necesarios para el plan presupuestario y finaliza la preparación del presupuesto.

El esquema de configuración de la planificación presupuestaria para el escenario tiene el siguiente aspecto:

![Esquema de configuración de planificación presupuestaria](./media/screenshot1-300x152.png)

Julia usa la siguiente plantilla de Excel para preparar el presupuesto:

[![Plantilla de Excel](./media/screenshot2-1024x352.png)](./media/screenshot2.png)

## <a name="exercise-1-configuration"></a>Ejercicio 1: Configuración

### <a name="task-1-create-organizational-hierarchy"></a>**Tarea 1: Crear una jerarquía organizativa**
Como todo el proceso presupuestario se produce en el departamento de finanzas, Julie necesita crear una jerarquía organizativa muy simple, que conste solo del departamento de finanzas. 

1.1. Navegue hasta las jerarquías organizativas (Administración de la organización &gt; Organizaciones &gt; Jerarquías organizativas) y haga clic en el botón Nuevo.

![Jerarquías organizativas](./media/screenshot3.png) 

1.2. Escriba el nombre de la jerarquía organizativa en el cuadro Nombre y haga clic en el botón Asignar propósito.

1.3. Seleccione el propósito de planificación presupuestaria, haga clic en Agregar y asigne la jerarquía organizativa recién creada. 

[![Asignar propósito](./media/screenshot5.png)](./media/screenshot5.png)

1.4. Repita el paso anterior para el propósito organizativo de seguridad. Cierre el formulario cuando termine.

1.5. En el formulario Jerarquías organizativas, haga clic en Ver. Haga clic en Editar en el Diseñador de jerarquías y cree una jerarquía haciendo clic en Insertar.

[![Insertar](./media/screenshot7.png)](./media/screenshot7.png) 

1.6. Seleccione el departamento de finanzas para la jerarquía de presupuesto. 

[![Finanzas](./media/screenshot8.png)](./media/screenshot8.png)

1.7. Cuando haya acabado, haga clic en Publicar y Cerrar. Seleccione 1/1/2015 como fecha de vigencia para la publicación de la jerarquía.

[![Fecha desde](./media/screenshot9.png)](./media/screenshot9.png)

### <a name="task-2-configure-user-security"></a>Tarea 2: Configurar seguridad de usuario
La planificación presupuestaria usa directivas especiales de seguridad para configurar el acceso a los datos de planes presupuestarios. Julia necesita darse acceso a los planes presupuestarios de finanzas a ella misma. 

2.1. Pase al contexto de entidad jurídica de DEMF. 


2.2. Navegue hasta Gestión presupuestaria &gt; Configurar &gt; Planificación presupuestaria &gt; Configuración de planificación presupuestaria. En la pestaña Parámetros, establezca el valor de Modelo de seguridad en Basado en organizaciones de seguridad. 

[![Parámetros](./media/screenshot11.png)](./media/screenshot11.png) 

2.3. Navegue hasta Administración del sistema &gt; Usuarios &gt; Usuarios. Dele al usuario administrador (Julia Funderburk) el rol de Administrador presupuestario. 

[![Administrador presupuestario](./media/screenshot12.png)](./media/screenshot12.png) 

2.4. Seleccione el rol de usuario y haga clic en Asignar organizaciones. 

[![Asignar organizaciones](./media/screenshot13.png)](./media/screenshot13.png)

2.5. Seleccione "Conceder acceso a organizaciones específicas". Seleccione la jerarquía organizativa creada en el primer paso. Seleccione el nodo Finanzas y haga clic en el botón Conceder con subordinados. 

***¡Importante!** _ _Asegúrese de que se encuentra en el contexto de la entidad jurídica de DEMF cuando realice esta tarea, ya que la seguridad organizativa se aplica por entidad jurídica* 

### <a name="task-3-create-scenarios"></a>Tarea 3: Crear escenarios
3.1. Navegue hasta Gestión presupuestaria&gt;Configurar &gt; Planificación presupuestaria &gt; Configuración de planificación presupuestaria. En la página Situaciones observe los escenarios que vamos a usar más en este laboratorio: Reales del año anterior y Presupuestado. 

*Nota: Puede crear nuevos escenarios para este ejercicio si lo desea y usarlos en su lugar.* 

[![Nuevos escenarios](./media/screenshot15.png)](./media/screenshot15.png) 

*Nota: como Julia no está usando el proceso de aprobación formal para la preparación del presupuesto, omitiremos la configuración de etapas Flujos de trabajo, Etapas y Flujo de trabajo en este laboratorio y usaremos la configuración existente para el flujo de trabajo Aprobación automática. Consulte el apéndice para esta configuración de flujo de trabajo.*

### <a name="task-4-create-budget-plan-columns"></a>Tarea 4: Crear columnas del plan presupuestario
Las columnas del plan presupuestario son las columnas monetarias o basadas en cantidad que se pueden usar en el diseño del documento de plan presupuestario. En nuestro ejemplo necesitamos crear una columna para Reales del año anterior y 12 columnas para representar cada mes en un año presupuestado. Para crear columnas, basta con hacer clic en el botón Agregar y rellenar los valores o mediante Entidad de datos. En este laboratorio usaremos Entidad de datos para rellenar los valores. 

4.1. En Gestión presupuestaria&gt;Configurar &gt; Planificación presupuestaria &gt; Configuración de planificación presupuestaria, abra la página Columnas. Haga clic en el botón de Office de la esquina superior derecha del formulario y seleccione Columnas (sin filtrar). 

[![Columnas sin filtrar](./media/screenshot16.png)](./media/screenshot16.png) 

4.2. El sistema abrirá un libro de Excel para usarlo para rellenar los valores. Si se le solicita, haga clic en la opción para habilitar la edición y confiar en esta aplicación. 

4.3. Necesitaremos más columnas para rellenar los valores. Haga clic en Diseño en el panel derecho para agregar las columnas a la cuadrícula. 

[![Diseño](./media/screenshot19.png)](./media/screenshot19.png) 

4.4. Haga clic en el botón de lápiz junto a PlanColumns para ver las columnas disponibles para agregarlas a la cuadrícula. 

[![Editar](./media/screenshot20.png)](./media/screenshot20.png) 

4.5. Haga doble clic en cada campo disponible para agregarlo a los campos seleccionados y haga clic en Actualizar. 

4.6. En la tabla de Excel agregue todas las columnas que se deben crear. Use la característica Autorrellenar de Excel para agregar líneas rápidamente. Asegúrese de que las líneas se agregan como parte de la tabla (al usar el desplazamiento vertical, debe poder ver encabezados de columna en la parte superior de la cuadrícula). 

4.7. Vuelva a la aplicación y actualice la página. Los valores publicados aparecerán. 

[![Actualización](./media/screenshot23.png)](./media/screenshot23.png)

### <a name="task-5-create-budget-plan-document-layouts-and-templates"></a>Tarea 5: Crear plantillas y diseños de documentos de plan presupuestario
El diseño define el aspecto que tendrá la cuadrícula de líneas de documento del plan presupuestario cuando el usuario abra el documento del plan presupuestario. También es posible cambiar el diseño para el documento del plan presupuestario para ver los mismos datos en distintos ángulos. Ahora, como tiene columnas definidas para usarlas con nuestro documento de plan presupuestario, Julia necesita crear un diseño de documento de plan presupuestario, que sería similar a la tabla de Excel que usa para crear datos de presupuesto (consulte la sección Visión general del escenario en este laboratorio) 

5.1. En Gestión presupuestaria&gt;Configurar &gt; Planificación presupuestaria &gt; Configuración de planificación presupuestaria, abra la página Diseños. Cree un nuevo diseño de la entrada de presupuesto mensual:

-   Seleccione el conjunto de dimensiones de MA+BU para incluir cuentas principales y unidades de negocio en el diseño.
-   Muestre todas las columnas del plan de presupuesto creadas en el paso anterior en la sección Elementos. Haga todo excepto Reales del año anterior editable.
-   Haga clic en el botón Descripciones para seleccionar qué dimensiones financieras deben mostrar Descripciones en la cuadrícula.

[![Descripciones](./media/screenshot24.png)](./media/screenshot24.png) 

En función de la definición del diseño del plan presupuestario, podemos crear una plantilla de Excel que se usará como manera alternativa de editar los datos de presupuesto. Como la plantilla de Excel tiene que coincidir con la definición de diseño del plan presupuestario, no podrá editar el diseño del plan presupuestario tras la generación de la plantilla de Excel; por tanto, esta tarea se debe realizar una vez que se definen todos los componentes de diseño. 

5.2. Para el diseño creado en el paso 5.1, haga clic en el botón Plantilla &gt; Generar. Confirme el mensaje de advertencia. Para ver la plantilla, haga clic en Plantilla &gt; Ver. 

*Nota: asegúrese de seleccionar "Guardar como" y seleccione el lugar en el que se debe almacenar la plantilla para editarla. Si el usuario selecciona "Abrir" en el diálogo sin guardar, los cambios realizados en el archivo no se conservarán cuando se cierre el archivo.* 
[![Vista de la plantilla](./media/screenshot25.png)](./media/screenshot25.png) 

5.3. &lt; Paso opcional&gt; Modifique la plantilla de Excel para que sea más sencilla para el usuario; agregue fórmulas totales, campos de encabezado, formato, etc. Guarde los cambios y cargue el archivo en el diseño del plan presupuestario haciendo clic en Diseño &gt; Cargar. 


### <a name="task-6-create-a-budget-planning-process"></a>Tarea 6: Crear un proceso de planificación presupuestaria
Julia necesita crear y activar un nuevo proceso de planificación presupuestaria combinando toda la configuración anterior para empezar a introducir planes presupuestarios. El proceso de planificación presupuestaria define qué organizaciones presupuestarias, flujo de trabajo, diseños y plantillas se usarán para crear planes presupuestarios. 

6.1. Navegue hasta Gestión presupuestaria &gt; Configuración &gt; Planificación presupuestaria &gt; Proceso de planificación presupuestaria y cree un registro nuevo.

-   Proceso de planificación presupuestaria – Gestión presupuestaria DEMF AF2016
-   Ciclo presupuestario – AF2016
-   Libro mayor – DEMF
-   Estructura contable predeterminada – Fabricación P&G
-   Jerarquía organizativa – seleccionar la jerarquía creada al principio del laboratorio
-   Flujo de trabajo de planificación presupuestaria – asignar flujo de trabajo de Aprobación automática para el departamento de finanzas
-   En reglas y plantillas de la etapa de planificación presupuestaria, para cada etapa de planificación presupuestaria del flujo de trabajo seleccione si se permite la adición y modificación de línea y qué diseño se debe usar de manera predeterminada

*Nota: Puede crear diseños de documentos adicionales y asignarlos para que estén disponibles en la etapa de flujo de trabajo de planificación presupuestaria haciendo clic en el botón Diseños alternativos.* 

[![Diseños alternativos](./media/screenshot27.png)](./media/screenshot27.png) 

6.2. Seleccione Acciones &gt; Activar para activar este flujo de trabajo de planificación presupuestaria. 

[![Activar](./media/screenshot28.png)](./media/screenshot28.png)

## <a name="exercise-2-process-simulation"></a>Ejercicio 2: Simulación del proceso

### <a name="task-7-generate-initial-data-for-budget-plan-from-general-ledger"></a>Tarea 7: Generar datos iniciales para el plan presupuestario desde Contabilidad general
7.1. Navegue hasta Gestión presupuestaria &gt; Periódico &gt; Generar plan presupuestario a partir de contabilidad general. Rellene los parámetros de proceso periódicos y haga clic en Generar. 

7.2. Navegue hasta Gestión presupuestaria &gt; Planes presupuestarios para encontrar un plan presupuestario creado por el proceso de generación. 

[![Plan presupuestario](./media/screenshot30.png)](./media/screenshot30.png) 

7.3. Abra detalles del documento haciendo clic en el hipervínculo Número de documento. El plan presupuestario se muestra tal y como se define en el diseño creado durante este laboratorio. 

[![Visualización del plan presupuestario](./media/screenshot31.png)](./media/screenshot31.png)

### <a name="task-8-create-current-year-budget-based-on-previous-year-actuals"></a>Tarea 8: Crear presupuesto de año actual en función de los valores reales del año anterior
Los métodos de asignación se pueden usar en el plan presupuestario para copiar información con facilidad para planes presupuestarios desde un escenario a otro/distribuirlos entre períodos/asignarlos a dimensiones. Usaremos asignaciones para crear el presupuesto del año actual a partir de los valores reales del año anterior. 

8.1. Seleccione todas las líneas de la cuadrícula de documento del plan presupuestario y haga clic en Asignar presupuesto. 

[![Todas las líneas](./media/screenshot32.png)](./media/screenshot32.png) 

8.2. Seleccione el método de asignación, la clave de período, los escenarios de origen y destino y haga clic en Asignar. 

[![Asignar](./media/screenshot33.png)](./media/screenshot33.png)

Los importes reales del año anterior se copiarán en el presupuesto del año actual y los asignará entre períodos con la clave de período de curva de ventas. 

[![Curva de ventas](./media/screenshot34.png)](./media/screenshot34.png)

### <a name="task-9-adjust-budget-plan-document-using-excel-and-finalize-the-document"></a>Tarea 9: Ajustar documento de plan presupuestario con Excel y finalizar el documento
9.1. Haga clic en el botón Hoja de cálculo para abrir el contenido del documento en Excel.

9.2. Cuando se abra el libro de Excel, ajuste los números en el documento del plan presupuestario y haga clic en el botón Publicar.

9.3. Vuelva al documento del plan presupuestario. Haga clic en Flujo de trabajo &gt; Enviar para aprobar automáticamente el documento.

[![Aprobación automática](./media/screenshot37.png)](./media/screenshot37.png) 

Una vez que se completa el flujo de trabajo, la etapa de documento de plan presupuestario cambia a Aprobado. [![Aprobados](./media/screenshot38.png)](./media/screenshot38.png)

## <a name="appendix"></a>Apéndice

### <a name="auto-approve-workflow-configuration"></a>Aprobar automáticamente la configuración del flujo de trabajo

A. Gestión presupuestaria &gt; Configuración &gt; Planificación presupuestaria &gt; Flujos de trabajo presupuestario. Crea un nuevo flujo de trabajo mediante flujos de trabajo de planificación de presupuesto de plantillas:

[![Crear un flujo de trabajo nuevo](./media/screenshot39.png)](./media/screenshot39.png)

Este flujo de trabajo solo contendrá una tarea, Realizar transición de etapa del plan presupuestario. 

[![Realizar transición de etapa del plan presupuestario](./media/screenshot40.png)](./media/screenshot40.png) 

Guarde y active el flujo de trabajo. 

B. Navegue hasta Gestión presupuestaria &gt; Configurar &gt; Planificación presupuestaria &gt; Configuración de planificación presupuestaria. En la pestaña Etapas, cree 2 etapas: Inicial y Enviado. 

[![Inicial y enviado](./media/screenshot41.png)](./media/screenshot41.png)

C. Navegue hasta Gestión presupuestaria &gt; Configurar &gt; Planificación presupuestaria &gt; Configuración de planificación presupuestaria. En la pestaña Etapas de flujo de trabajo, asocia el flujo de trabajo Aprobación automática creado en el paso A con las etapas Inicial y Enviado.

[![Gestión y planificación presupuestarias](./media/screenshot42.png)](./media/screenshot42.png)  





[!INCLUDE[footer-include](../../includes/footer-banner.md)]