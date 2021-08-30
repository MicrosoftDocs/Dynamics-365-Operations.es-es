---
title: Configurar revisores de gastos
description: Este tema describe cómo utilizar los revisores de gastos para seleccionar dinámicamente al usuario al que se asigna una tarea de flujo de trabajo, aprobación o decisión manual.
author: rachel-profitt
ms.date: 06/25/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2021-06-24
ms.openlocfilehash: ceb0a60ccf3d1c989d8663e933faaa5e430d314695e20990c9086cd1b8325ff1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773736"
---
# <a name="configure-expenditure-reviewers"></a>Configurar revisores de gastos
[!include[banner](../includes/banner.md)]

Puede especificar revisores de gastos dinámicos para dirigir los gastos de revisión según el usuario asignado a un rol del proyecto o a la dimensión financiera donde se cobran los gastos. El proceso del flujo de trabajo usa el rol de proyecto especificado o el propietario de la dimensión financiera para determinar a quién se debe enrutar el gasto.

Puede definir una o varias configuraciones de revisor de gastos y, a continuación, seleccionar una cuando cree un flujo de trabajo. Puede configurar los valores del revisor de gastos para cada entidad jurídica de su organización. Una vez definidas las configuraciones del revisor de gastos, asigne la configuración. Los revisores de gastos pueden asignarse a tareas de flujo de trabajo, aprobaciones y decisiones manuales.

> [!NOTE]
> Aunque los revisores de gastos no son obligatorios, pueden ayudar a simplificar la configuración de su flujo de trabajo. Por ejemplo, no tiene que crear una decisión condicional para verificar cada dimensión de centro de costo y luego crear otro elemento para asignar la aprobación o tarea a un usuario o grupos de usuarios específicos. En su lugar, puede configurar el propietario de la dimensión del centro de costos y utilizar un revisor de gastos para seleccionar dinámicamente al usuario correcto. De esta forma, cuando cambia la propiedad o la asignación de los centros de coste, solo tiene que actualizar el campo **Dueño** de la dimensión financiera.

## <a name="types-of-expenditure-reviewers"></a>Tipos de revisores de gastos

No todos los flujos de trabajo apoyan el concepto de revisores de gastos. De forma predeterminada, puede configurar revisores de gastos para solicitudes de compra, órdenes de compra, facturas de proveedores e informes de gastos. Cada uno de estos tipos de flujo de trabajo requiere que configure los revisores de gastos en una página separada que es específica para la función y el módulo. Para cada documento admitido, los revisores de gastos se pueden usar con flujos de trabajo a nivel de encabezado o flujos de trabajo a nivel de línea.

La siguiente tabla muestra dónde debe ir para configurar un revisor de gastos para cada documento admitido.

| Documento | Ruta de navegación |
|----------|-----------------|
| Informes de gastos | Administración de gastos \> Configuración \> Políticas \> Revisores de gastos |
| Pedidos de compra | Adquisiciones y abastecimiento \> Configuración \> Políticas \> Revisores de gastos de órdenes de compra |
| Solicitudes de compra | Adquisiciones y abastecimiento \> Configuración \> Políticas \> Revisores de gastos de solicitudes de compra |
| Facturas de proveedores | Proveedores \> Configuración de directivas \> Revisores de gastos de facturas de proveedor |

## <a name="expenditure-reviewer-assignments"></a>Asignaciones de revisor de gastos

Hay dos tipos de asignación disponibles para cada revisor de gastos: *distribuciones de proyectos* y *distribuciones de la organización*. Para la distribución de un proyecto, puede seleccionar entre autoridades del proyecto y dimensiones financieras. Para una distribución de organización, puede seleccionar dimensiones financieras.

Las autoridades del proyecto incluyen el director del proyecto, el controlador del proyecto y el director de ventas del proyecto. Defina estas autoridades directamente en su proyecto, seleccionando un trabajador en los campos correspondientes.

Las dimensiones financieras están controladas por las estructuras contables de cada entidad jurídica. Para cada entidad jurídica, puede seleccionar qué dimensiones financieras se utilizarán con el revisor de gastos. Las dimensiones pueden provenir del proyecto (en este caso, seleccione las dimensiones en la pestaña **Distribuciones de proyectos**) o el documento (en este caso, seleccione las dimensiones en la ficha **Distribuciones de organización**). En el campo **Dueño** en la página **Valores de dimensiones financieras**, puede seleccionar el trabajador para cada dimensión financiera.

## <a name="example-1-expenditure-reviewers-based-on-organization-distributions"></a>Ejemplo 1: Revisores de gastos basados en distribuciones de organizaciones

Trabajas para Contoso Appliances, y su organización tiene seis departamentos y 10 centros de costos. Cuando se envía una nueva solicitud de compra, la aprobación debe provenir primero del gerente del departamento y luego del gerente del centro de costos.

Para este ejemplo, configura dos *revisores de gastos de solicitud de compra*:

- Para el primer revisor, usted nombra el departamento y luego selecciona la dimensión financiera **Departamento** en la pestaña **Distribuciones de organización**. 
- Para el segundo revisor, nombra el centro de coste y luego selecciona la dimensión financiera **Centro de coste** en la pestaña **Distribuciones de organización**.

Cuando configura el flujo de trabajo, crea dos pasos de aprobación. El primero es para el departamento y el segundo es para el centro de costos. Para cada elemento de aprobación, selecciona **Partícipe** en el campo **Tipo de asignación** en la pestaña **Basado en roles**, seleccione **Participantes del gasto** en el campo **Tipo de participante** y luego seleccione el participante apropiado en el campo **Partícipe**.

Cuando se crea la solicitud de compra, las dimensiones financieras del departamento y del centro de coste se asignan a las líneas de la solicitud de compra. Cuando se envía el flujo de trabajo, el sistema primero evalúa el departamento en la solicitud de compra y asigna el elemento de aprobación al usuario que está relacionado con el trabajador que seleccionó para el departamento. Después del primer paso de aprobación, el sistema evalúa el segundo paso de aprobación y asigna el segundo elemento de aprobación al usuario que está relacionado con el trabajador que seleccionó para el centro de coste.

## <a name="example-2-expenditure-reviewers-based-on-project-distributions"></a>Ejemplo 2: Revisores de gastos basados en distribuciones de proyectos

Trabaja para la división de servicios de Contoso Appliances. La organización requiere que el gerente de proyecto de cada orden de compra apruebe el gasto. Además, el director del centro de costes del proyecto debe aprobarlo. Las aprobaciones se pueden realizar al mismo tiempo. En cualquier caso, ambos usuarios deben aprobar la orden de compra antes de que el flujo de trabajo pueda continuar.

Para este ejemplo, crea un *revisor de gastos de órdenes de compra* que se llama **PM y centro de coste**. Usted selecciona la casilla de verificación **Gerente de proyecto** y establezca la opción **Dimensión del centro de coste** a **sí** sobre la pestaña **Distribuciones de proyectos** de la página **Revisor de gastos de órdenes de compra**. Como parte de la configuración, debe asegurarse de que el campo **Gerente de proyecto** se establece para todos los proyectos, y que se especifica un propietario para todos los centros de costos en la página **Valores de la dimensión financiera**.

Cuando configura el flujo de trabajo, necesita un elemento de aprobación. Selecciona **Partícipe** en el campo **Tipo de asignación**. Entonces, en la pestaña **Basado en roles**, usted selecciona **Participantes del gasto** en el campo **Tipo de participante** y selecciona el director del proyecto y el centro de costos en el campo **Partícipe**. Para asegurarse de que el flujo de trabajo no pueda continuar hasta que tanto el gerente del proyecto como el propietario del centro de costos aprueben el flujo de trabajo, establezca el campo **Política de finalización** en **Todos los aprobadores**.

Cuando se crea la orden de compra, el campo **Proyecto** debe especificarse. Si no necesita un proyecto para todas sus órdenes de compra, debe agregar una decisión condicional a su flujo de trabajo para verificar un proyecto antes de ejecutar el paso de aprobación. Luego, el sistema evalúa el proyecto que se especifica para la orden de compra y asigna el elemento de aprobación al usuario que está relacionado con el trabajador en el campo **Gerente de proyecto**. Además, el sistema crea una tarea y la asigna al usuario que está relacionado con el trabajador que usted selecciona en el campo **Dueño** para el centro de costo del proyecto. Tenga en cuenta que este ejemplo utiliza el centro de costo del proyecto, no el centro de costo de la orden de compra.

## <a name="set-up-expenditure-reviewers"></a>Configuración de revisores de gastos

Este ejemplo muestra cómo configurar un revisor de gastos de solicitud de compra. Para configurar otros tipos de revisores de gastos, reemplace la ruta de navegación en el paso 1 con la ruta apropiada de la tabla en la sección [Tipos de revisores de gastos](configure-expenditure-reviewers.md#types-of-expenditure-reviewers) antes en este tema.

1. Vaya a **Adquisiciones y abastecimiento \> Configuración \> Políticas \> Revisores de gastos de solicitudes de compra**.
2. En la página **Revisores de gastos de solicitudes de compra**, seleccione **Nuevo**.
3. En el campo **Nombre**, ingrese un nombre para la configuración del revisor de gastos, como **centro de costos**.
4. En la ficha desplegable **Revisores de gastos por entidad jurídica**, seleccione la entidad jurídica que desee configurar.
5. Para una distribución de proyecto, seleccione la casilla de verificación de cada autoridad de proyecto y seleccione **Sí** para cada dimensión financiera que desee habilitar. 
6. Para una distribución de la organización, en la pestaña **Distribuciones de organización**, seleccione **Sí** para cada dimensión financiera que desee habilitar.
7. Repita los pasos 4 a 6 para cada entidad jurídica adicional.

## <a name="assign-owners-to-financial-dimensions"></a>Asignar propietarios a dimensiones financieras

Para asignar un propietario a una dimensión financiera, siga estos pasos.

1. Vaya a **Contabilidad general \> Plan contable \> Dimensiones \> Dimensiones financieras**.
2. En la lista, seleccione la dimensión financiera a la que asignar propietarios.
3. Seleccione **Valores de dimensión**.
4. Seleccione **Editar** para realizar cambios en los valores de dimensión.
5. En la lista, seleccione el valor de la dimensión a la que asignar un propietario.
6. En el campo **Propietario**, seleccione el equipo al que se va a asignar el valor de dimensión.

## <a name="configure-project-distributions"></a>Configurar distribuciones de proyectos

Para asignar autoridades de proyecto a un proyecto, siga estos pasos.

1. Vaya a **Gestión de proyectos y contabilidad \> Proyectos \> Todos los proyectos**.
2. Seleccione el proyecto al que asignar autoridades.
3. Seleccione **Editar** para realizar cambios en el proyecto.
4. En la ficha desplegable **General**, en la sección **Responsable**, seleccione un trabajador para los campos **Gerente de ventas**, **Gerente de proyecto** y **Controlador de proyecto** según sea necesario.
5. En la ficha desplegable **Dimensiones financieras**, seleccione las dimensiones financieras necesarias para su proyecto.

## <a name="assign-expenditure-reviewers-to-a-workflow-task"></a>Asignación de revisores de gastos a una tarea de flujo de trabajo

Este ejemplo muestra cómo configurar un flujo de trabajo de solicitud de compra para que utilice un revisor de gastos de solicitud de compra. Para configurar otros tipos de flujos de trabajo, la página de flujo de trabajo que debe abrir en el paso 1 puede estar en el módulo **Administración de gastos** o **Cuentas por pagar** en lugar del módulo **Adquisiciones y abastecimiento**.

Para asignar revisores de gastos de solicitud de compra una tarea de flujo de trabajo, siga estos pasos.

1. Vaya a **Adquisición y abastecimiento \> Configuración \> Flujos de trabajo de adquisición y abastecimiento**.
2. Toque dos veces (o haga doble clic) en un flujo de trabajo existente o cree uno nuevo.
3. En el editor de flujo de trabajo, en el panel **Flujo de trabajo**, seleccione la tarea a la que asignar la configuración del revisor de gastos. Luego, en el **Panel de acciones**, en el grupo **Mostrar**, seleccione **Propiedades**.
4. En el panel izquierdo de la página **Propiedades**, seleccione **Asignación**.
5. En la pestaña **Tipo de asignación**, seleccione **Participante**.
6. En la pestaña **Basado en roles**, en el campo **Tipo de participante**, seleccione **Participantes del gasto**. Luego, en el campo **Participante**, seleccione la configuración del revisor de gastos que va a usar para la tarea del flujo de trabajo.
