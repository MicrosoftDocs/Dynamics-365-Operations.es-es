---
title: "Visión general de la planificación presupuestaria"
description: "En este artículo se introduce la plantificación presupuestaria y contiene información que le ayudará a configurar la planificación presupuestaria y los procesos de planificación presupuestaria."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17251
ms.assetid: a2e06633-a800-4840-a962-88fed8462104
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 55553e9a791201b2707d2d9e98385e549d8417f6
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="budget-planning-overview"></a>Visión general de la planificación presupuestaria

[!include[banner](../includes/banner.md)]


En este artículo se introduce la plantificación presupuestaria y contiene información que le ayudará a configurar la planificación presupuestaria y los procesos de planificación presupuestaria.

<a name="overview-of-budget-planning"></a>Visión general de la planificación presupuestaria
---------------------------

La planificación presupuestaria se realiza cuando se preparan los presupuestos que una organización implementará. Una organización puede configurar la planificación presupuestaria y, a continuación, configurar procesos de planificación presupuestaria para cumplir sus directivas, procedimientos y requisitos para la preparación de presupuestos. 

Cuando comprenda los conceptos y la terminología que se usan en Microsoft Dynamics 365 for Operations, le será más sencillo implementar la planificación presupuestaria en su organización.

### <a name="key-terms"></a>Términos clave

-   **Procesos de planificación presupuestaria**: los procesos de planificación presupuestaria determinan cómo se pueden actualizar, enrutar, revisar y aprobar los planes presupuestarios en la jerarquía organizativa presupuestaria. Un proceso de planificación presupuestaria está vinculado a un ciclo presupuestario y una organización mediante una entidad jurídica.
-   **Planes presupuestarios**: los planes presupuestarios contienen los datos de presupuesto para un ciclo de presupuesto. Puede tener varios planes presupuestarios que se usan para distintos fines. Por ejemplo, los planes presupuestarios se pueden usar para crear importes presupuestarios para diferentes unidades organizativas, o pueden ayudarle a realizar comparaciones y a tomar decisiones informadas.
-   **Escenarios del plan presupuestario**: los escenarios del plan de presupuesto definen categorías de datos para planes presupuestarios. Los escenarios del plan presupuestarios se definen para admitir clases monetarias y otras clases de unidad de medida, como cantidad. Los ejemplos de escenarios monetarios del plan presupuestario incluyen el año anterior del departamento y las solicitudes de departamento. Entre los ejemplos de escenarios del plan presupuestario que usan cantidades se incluyen las llamadas de soporte del año pasado y el recuento equivalente de jornada completa (FTE).
-   **Etapas de planificación presupuestaria**: las etapas de planificación presupuestaria definen los pasos que un plan presupuestario sigue desde su inicio a la aprobación final. Las etapas de planificación presupuestaria se organizan en flujos de trabajo de planificación presupuestaria.
-   **Flujos de trabajo de planificación presupuestaria**: los flujos de trabajo de planificación presupuestaria constan de etapas de planificación presupuestaria y las definen. Los flujos de trabajo de planificación presupuestaria se asocian a flujos de trabajo presupuestarios. Los flujos de trabajo de gestión presupuestaria son los procesos automatizados y manuales que mueven planes presupuestarios por las etapas de planificación presupuestaria.

[![Terminología de planificación presupuestaria](./media/budgetplanning-terms-1024x504.png)](./media/budgetplanning-terms.png)

### <a name="common-tasks"></a>Tareas comunes

Puede utilizar la planificación presupuestaria para realizar las tareas siguientes:

-   Crear planes presupuestarios para definir los ingresos y gastos previstos para un ciclo presupuestario.
-   Analizar y actualizar los planes presupuestarios para varios escenarios.
-   Enrutar automáticamente los planes presupuestarios, junto con las hojas de cálculo, los documentos de justificación y otros datos adjuntos, para su revisión y aprobación.
-   Consolidar varios planes presupuestarios de un nivel inferior de la organización en un único plan presupuestario principal de un nivel superior de la organización. También puede desarrollar un único plan presupuestario en un nivel superior de la organización y asignar el presupuesto a niveles inferiores de la organización.

La planificación presupuestaria se integra con otros módulos de Microsoft Dynamics 365 for Operations. Por tanto, puede incorporar la información de presupuestos anteriores, gastos reales, activos fijos y recursos humanos. Dado que la planificación presupuestaria también se integra con Microsoft Excel y Microsoft Word, puede usar estos programas para trabajar con los datos de planificación presupuestaria. Por ejemplo, un administrador de presupuestos puede exportar la solicitud de presupuesto de un departamento desde un escenario de plan presupuestario en una hoja de cálculo de Excel. Los datos se pueden analizar, actualizar y asignar en la hoja de cálculo y, a continuación, publicar de nuevo en las líneas del plan presupuestario.

## <a name="configuring-budget-planning"></a>Configuración de la planificación presupuestaria
La página **Configuración de planificación presupuestaria** contiene la mayoría de los parámetros que se necesitan para configurar la planificación presupuestaria. Las siguientes secciones describen algunos factores clave que debe tener en cuenta conforme configura la planificación presupuestaria. Después de completar la configuración, configure los procesos de planificación presupuestaria.

### <a name="create-a-budget-planning-schema"></a>Crear un esquema de planificación presupuestaria

El primer paso opcional pero muy recomendable es crear un esquema que muestre el procedimiento de la organización para formular un presupuesto. Puede usar cualquier método que desee para crear este esquema. El ejemplo siguiente muestra un ejemplo genérico, donde se crean los flujos de trabajo de planificación presupuestaria independientes para distintos niveles de la organización. Las etapas se definen dentro de cada flujo de trabajo y se asignan escenarios específicos a cada etapa para mantener los datos del presupuesto. Las tareas se realizan para mover los datos de una etapa a la siguiente. Por ejemplo, se pueden asignar o agregar importes a diferentes cuentas, aprobaciones y otras revisiones. En este ejemplo, el texto en cursiva indica un escenario que no es editable durante la etapa, o datos que son históricos o que se han aprobado en una etapa anterior y que por tanto no se deben cambiar. 

[![Esquema genérico de planificación presupuestaria](./media/budgetplanninggenericschema-300x145.png)](./media/budgetplanninggenericschema.png) 

En el siguiente ejemplo, la sede corporativa calcula los importes de línea base de presupuesto iniciales y los distribuye a los departamentos de ventas. Los departamentos de ventas calculan y devuelven su previsión a las sedes, donde el director de presupuestos agrega y ajusta la previsión. Finalmente, el director de presupuestos envía importes de presupuesto ajustados al director financiero para revisión, ajustes finales y aprobación. 

[![Ejemplo de esquema de planificación presupuestaria](./media/budgetplanningexampleschema-300x145.png)](./media/budgetplanningexampleschema.png)

###  <a name="organization-hierarchy-for-budget-planning"></a>Jerarquía organizativa para planificación presupuestaria

En la página **Jerarquía organizativa**, puede designar una jerarquía organizativa como jerarquía de planificación presupuestaria para cada proceso de planificación presupuestaria. La jerarquía de planificación presupuestaria no tiene que coincidir con la jerarquía organizativa estándar que se usa para otros propósitos. Dado que esta jerarquía se usa para agregar y distribuir datos, puede que desee que tenga otra estructura. En el esquema de ejemplo, los departamentos de ventas se encuentran en un nivel de sede que incluye departamentos de finanzas y presupuesto. Esta estructura se diferencia probablemente de la estructura que se usa para gestionar operaciones para los departamentos de ventas. Solo una jerarquía de organización se puede asignar a cada proceso de planificación presupuestaria. 

Para obtener más información acerca de las jerarquías organizativas, consulte [Organizaciones y las jerarquías organizativas](/dynamics365/operations/organization-administration/organizations-organizational-hierarchies).

### <a name="user-security"></a>Seguridad de usuario

La planificación presupuestaria puede seguir uno de los dos modelos de seguridad para definir permisos de usuario. Para especificar el modelo de seguridad, se establece un parámetro de planificación presupuestaria en la página **Configuración de planificación presupuestaria**.

### <a name="budget-planning-workflows-stages"></a>Etapas de flujos de trabajo de planificación presupuestaria

Los flujos de trabajo de planificación presupuestaria se usan junto con los Flujos de trabajo presupuestarios para administrar la configuración y la evolución de los planes presupuestarios.

Un flujo de trabajo de planificación presupuestaria consiste en un conjunto ordenado de etapas por las que se mueve un plan presupuestario. Cada flujo de trabajo de planificación presupuestaria se asocia a un flujo de trabajo presupuestario. Los flujos de trabajo presupuestarios son uno de los tipos de flujo de trabajo que se usan en Microsoft Dynamics 365 for Operations. El flujo de trabajo presupuestario enruta los planes presupuestarios, junto con las hojas de cálculo, las justificaciones y los datos adjuntos, a la organización para su revisión y aprobación. 

Cree el flujo de trabajo de planificación presupuestaria en la sección **Etapas de flujo de trabajo** de la página **Configuración de planificación presupuestaria**. Ahí, puede seleccionar las etapas y el flujo de trabajo de presupuesto que se usarán, y también configurar opciones adicionales. 

Una buena práctica es crear un flujo de trabajo de planificación presupuestaria para cada nivel de una jerarquía de presupuesto. A continuación, asigna un flujo de trabajo de presupuesto que contenga elementos que correspondientes a las etapas del flujo de trabajo de planificación presupuestaria. En el esquema de ejemplo que aparece anteriormente en este artículo, se crearía un flujo de trabajo de planificación presupuestaria para los departamento de ventas y otro, para las sedes. Un flujo de trabajo de presupuesto mueve los planes de presupuesto por las etapas. 

Cree el flujo de trabajo de presupuesto para la planificación presupuestaria en la página **Flujos de trabajo presupuestarios**. El proceso es similar al proceso para crear otros flujos de trabajo en Microsoft Dynamics 365 for Operations. En la ilustración siguiente se muestra un ejemplo de un flujo de trabajo de sedes. 

[![Flujo de trabajo de presupuesto para la planificación presupuestaria](./media/budgetingworkflowforbudgetplanning-300x300.png)](./media/budgetingworkflowforbudgetplanning.png) 

El flujo de trabajo incluye elementos para asignación a departamentos de ventas y agregación de sus envíos, revisión por el director de presupuestos, aprobación por el director financiero y transiciones de etapa entre cada etapa. 

Asigne el flujo de trabajo de presupuesto a cada flujo de trabajo de planificación presupuestaria en la sección **Etapas de flujo de trabajo** de la página **Configuración de planificación presupuestaria**.

### <a name="parameters-scenarios-and-stages"></a>Parámetros, escenarios y etapas

La configuración inicial de la página **Configuración de planificación presupuestaria** le permite crear algunos componentes básicos para pasos de configuración posteriores:

-   **Parámetros**: los parámetros definen las reglas de seguridad que desea aplicar a los planes presupuestarios y las dimensiones financieras predeterminadas que se deben usar cuando los usuarios exploran los importes de escenario del plan presupuestario.
-   **Escenarios**: los escenarios abarcan las categorías de datos que desea para los planes presupuestarios. Los escenarios del plan presupuestarios se definen para admitir clases monetarias y otras clases de unidad de medida, como cantidad. En un plan presupuestario, los escenarios representan una versión de los datos de planificación presupuestaria. Los ejemplos de escenarios monetarios del plan presupuestario incluyen las ventas del año anterior y los contratos firmados. Entre los ejemplos de escenarios que usan cantidades se incluyen el número de llamadas de ventas y el recuento equivalente de jornada completa (FTE).
-   **Etapas**: las etapas definen los pasos que un plan presupuestario sigue desde su inicio a la aprobación final. Entre los ejemplos de las etapas de planificación presupuestaria se incluyen la acumulación de sede, la revisión del director financiero y la final.

### <a name="allocation-schedules"></a>Programaciones de asignación

En la planificación presupuestaria, puede asignar los importes o las cantidades de líneas del plan presupuestario de un escenario a otro, o incluso al mismo escenario. Por ejemplo, puede asignar al mismo escenario si desea aplicar cambios a las dimensiones financieras o las fechas de los importes en dicho escenario. Una asignación se puede realizar dentro de un plan presupuestario o a partir de un plan presupuestario a otro. 

Las programaciones de asignación asignan automáticamente líneas del plan presupuestario durante el procesamiento de flujo de trabajo. Puede realizar asignaciones mediante cualquiera de los métodos siguientes en la lista **Método de asignación**:

-   **Asignar en períodos**: use una clave de asignación de período para asignar las líneas del plan presupuestario desde el escenario del plan presupuestario de origen a través de los períodos del escenario de destino. **Nota**: Antes de poder asignar en períodos, debe configurar las claves de asignación por período en la página ****Categorías de asignación por períodos****.
-   **Asignar a dimensiones**: las líneas del plan presupuestario se asignan desde el escenario del plan presupuestario de origen a través de las dimensiones financieras del escenario de destino. **Nota**: Para poder asignar a las dimensiones, debe configurar condiciones de asignación del presupuesto en la página ****Condiciones de asignación del presupuesto****.
-   **Agregado**: las líneas del plan presupuestario se agregan desde el escenario del plan presupuestario de origen de los planes presupuestario asociados al escenario de destino del plan presupuestario principal.
-   **Distribuir**: las líneas del plan presupuestario se distribuyen desde el escenario del plan presupuestario de origen del plan presupuestario principal al escenario de destino de los planes presupuestarios asociados.
-   **Usar reglas de asignación contable**: las líneas del plan presupuestario se distribuyen del escenario del plan presupuestario de origen al escenario de destino, basándose en la regla de asignación contable seleccionada.
-   **Copiar del plan presupuestario**: puede seleccionar otro plan presupuestario para usarlo como el origen de la asignación.

### <a name="stage-allocations"></a>Asignaciones de etapa

Las asignaciones de etapa se usan para asignar automáticamente líneas del plan presupuestario durante el procesamiento del flujo de trabajo. Cuando se usan asignaciones de etapa, las líneas del plan presupuestario del escenario de destino se pueden crear y modificar sin intervención del preparador o del revisor del plan presupuestario.

Cuando configura una asignación de etapa, asocia el flujo de trabajo y la etapa de planificación presupuestaria con la programación de asignación. El flujo de trabajo de planificación presupuestaria se debe asociar a un flujo de trabajo de gestión presupuestaria que use la tarea de flujo de trabajo automatizada ****Asignación de etapa de la planificación presupuestaria****. Cuando el flujo de trabajo alcanza la etapa especificada, la asignación se produce automáticamente. Esta tarea automatizada se puede usar para crear líneas de plan presupuestario en un nuevo escenario. 

En el esquema de ejemplo que aparece anteriormente en este artículo, se realiza una asignación para transferir importes de un plan presupuestario y escenario de la etapa de línea base de sedes a otro plan presupuestario y escenarios en la etapa de estimación del departamento de ventas. En la ilustración siguiente se muestra la sección relevante del esquema de ejemplo.

[![Asignación de etapa](./media/stageallocation-204x300.png)](./media/stageallocation.png) 

Además, en el esquema de ejemplo, se realiza una agregación desde los escenarios y los planes presupuestarios de la etapa Enviado del departamento de ventas a un plan principal de la etapa de acumulación de sede. En la ilustración siguiente se muestra la sección relevante del esquema de ejemplo.

[![Agregación](./media/aggregation-109x300.png)](./media/aggregation.png)

### <a name="priorities"></a>Prioridades

De forma opcional, puede usar prioridades del plan presupuestario para definir categorías y objetivos para los planes presupuestarios que ha configurado. También puede usar prioridades para organizar, clasificar y evaluar varios planes presupuestarios. Por ejemplo, puede crear una prioridad de planificación presupuestaria para el estado y la seguridad y, a continuación, evaluar los planes presupuestarios que están asignados a dicha prioridad. También puede asignar un número para clasificar planes presupuestarios a través de todos los planes presupuestarios.

### <a name="columns-and-layouts"></a>Columnas y diseños

Las cifras de presupuesto aparecen en un plan presupuestario en filas y columnas. Debe definir primero las columnas y, a continuación, podrá crear un diseño para definir la presentación de las columnas. 

Para definir una columna, seleccione un escenario del plan presupuestario. Los importes de línea de ese escenario se muestran en el plan presupuestario. Puede seleccionar un período para filtrar el importe y también puede aplicar filtros que se basen en la cuenta contable. 

Cuando defina un diseño, seleccione un conjunto de dimensiones contables para crear las filas del plan presupuestario que desea mostrar y seleccionar las columnas como elementos de diseño. Puede crear varios diseños, de modo que un plan presupuestario muestra los datos que desea en diferentes etapas del proceso de planificación presupuestaria. 

Además de las columnas para los importes presupuestarios, puede definir columnas para el proyecto, el proyecto propuesto, el activo y los campos del activo propuesto del plan presupuestario. También puede definir una columna para posiciones presupuestadas. Esta opción es muy útil cuando debe analizar presupuestos personales. 

Para el esquema de ejemplo, puede que desee crear columnas para escenarios de ventas de PY, contratos y previsión (la siguiente ilustración muestra la sección relevante del esquema). A continuación, podrá separar uno o todos estos escenarios en columnas independientes para cada trimestre del ejercicio, de modo que el director del departamento de ventas pueda especificar de manera precisa los importes de previsión para cada período.

[![Columnas](./media/columns.png)](./media/columns.png) 

También puede designar si cada elemento de diseño (columna) es editable y si está disponible en cualquier plantilla de hoja de cálculo que se cree para ese diseño. Para el esquema de ejemplo, en el diseño que se usa para la etapa Estimación, las columnas de previsión son editables, mientras que las columnas de ventas PY y contratos son de solo lectura.

### <a name="templates"></a>Plantillas

En la sección **Diseños** de la página **Configuración de planificación presupuestaria**, también puede generar, ver o cargar plantillas de Excel. Estas plantillas son los libros que se vinculan a cada plan presupuestario para proporcionar funcionalidad adicional de análisis, gráficos y entrada de datos. 

Puede generar, ver o cargar una plantilla para cada diseño. Cuando se genera una plantilla, el diseño se bloquea y no se puede editar. Este bloqueo ayuda a garantizar que el formato de la plantilla coincide con el diseño del plan presupuestario y que incluye los mismos datos. Tras generar una plantilla, se puede ver y editar. Por ejemplo, puede agregar gráficos a la plantilla o personalizar más su aspecto.

> [!NOTE] 
> La plantilla se debe guardar en una ubicación a la que el usuario tiene acceso, para que se pueda cargar en el diseño una vez completada la edición. De esa manera, la plantilla se usará con los planes presupuestarios que usan la configuración.

### <a name="descriptions"></a>Descripciones

Las descripciones que puede asignar en la sección **Diseños** se usan para mostrar el nombre de una dimensión financiera que se incluye en un diseño. Por ejemplo, es posible que una organización pueda desear que se muestre el nombre de la cuenta principal junto al número de la cuenta principal en un plan presupuestario, pero es posible que desee omitir los nombres de las demás dimensiones financieras para evitar que se recargue la visualización.

## <a name="setting-up-budget-planning-processes"></a>Configuración de procesos de planificación presupuestaria

Una vez que haya terminado de configurar la planificación presupuestaria, puede configurar procesos de planificación presupuestaria en la página **Proceso de planificación presupuestaria**. Los procesos de planificación presupuestaria son conjuntos de reglas que determinan cómo se pueden actualizar, enrutar, revisar y aprobar los planes presupuestarios en la jerarquía organizativa presupuestaria. 

Para cada proceso de planificación presupuestaria, seleccione primero un ciclo presupuestario y un libro mayor. Cada proceso de planificación presupuestaria está relacionado solo con un ciclo presupuestario y un libro mayor. A continuación, seleccione la jerarquía organizativa presupuestaria en la ficha desplegable **Id. de administración de proceso de planificación presupuestaria** y asigne un flujo de trabajo de planificación presupuestaria a todos los centros de responsabilidad de la organización que aparecen en la cuadrícula. 

Para asignar o cambiar el flujo de trabajo de planificación presupuestaria de centros de responsabilidad similares, haga clic en **Asignar flujo de trabajo** y, a continuación, seleccione el tipo de organización de destino y el flujo de trabajo de planificación presupuestaria que desea usar. La identificación de flujo de trabajo de gestión presupuestaria que está asociado a cada flujo de trabajo de planificación presupuestaria se agrega a la cuadrícula automáticamente. 

Al definir las reglas de etapa y las plantillas en la ficha desplegable **Reglas y diseños de fase de planificación presupuestaria**, puede definir otro conjunto de reglas y diseños predeterminados para cada etapa de planificación presupuestaria. Por ejemplo, la etapa Estimación del departamento de ventas puede permitir a los usuarios modificar las líneas de un plan presupuestario pero prohibir a los usuarios que agreguen líneas. La etapa Enviado puede dejar a los usuarios ver líneas, pero no agregarlas o modificarlas, porque el trabajo en esa etapa se ha completado y se deben evitar los cambios a los planes presupuestarios. Para seleccionar los diseños disponibles para los planes presupuestarios, haga clic en **Diseños alternativos**. 

Puede seleccionar opcionalmente prioridades de planificación presupuestaria en la ficha desplegable **Restricciones de prioridad del plan presupuestario**. Prioridades que se pueden seleccionar en el plan presupuestario. 

El paso final es la activación del proceso de planificación presupuestaria mediante el menú **Acciones**. No se podrá usar el proceso de planificación presupuestaria hasta que no se haya activado. 

En el menú **Acciones**, también puede crear un proceso nuevo copiando un proceso existente. Esta característica resulta útil para las organizaciones que siguen el mismo flujo de proceso cada ciclo presupuestario, y que realizan pocos cambios o ninguno. 

Otro comando útil en el menú **Acciones** es **Ver estado del proceso presupuestario**. Este comando muestra gráficamente los planes presupuestarios dentro de un proceso, junto con datos relevantes, como el estado del flujo de trabajo de los planes, resúmenes por importe y por unidad, y navegación de un solo clic a los propios planes presupuestarios.

[![Estado del proceso de planificación presupuestaria](./media/budgetplanningprocessstatus-300x171.png)](./media/budgetplanningprocessstatus.png)




