---
title: Utilizar flujos de trabajo para administrar la información sobre los empleados
description: Este artículo explica cómo puede usar los flujos de trabajo para administrar la información de los empleados.
author: twheeloc
ms.date: 11/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: dbbbb0ee807cb65fa4f4f9a29cc4a2b6b045b08c
ms.sourcegitcommit: 2b654e60e2553a5835ab5790db4ccfa58828fae7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750744"
---
# <a name="use-workflows-to-manage-employee-information"></a>Utilizar flujos de trabajo para administrar la información sobre los empleados

[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo explica cómo puede utilizar la capacidad del flujo de trabajo para que Recursos Humanos administre la información sobre los empleados. Por ejemplo, puede asociar un flujo de trabajo a un puesto y configurar un flujo de trabajo de aprobación que se inicia cuando los empleados cambian su registro.

La capacidad del flujo de trabajo para Recursos Humanos proporciona numeroso flujos de trabajo para gestionar actividades de Recursos Humanos. Asimismo, hay numerosas opciones disponibles para que pueda modificar flujos de trabajo específicos y asociarlos a una jerarquía de informes. Los flujos de trabajo están disponibles para ayudar a gestionar cambios a varios tipos de información sobre los empleados. Puede asociar un flujo de trabajo a un puesto. A continuación, si los empleados cambian su registro de empleado, se inicia un flujo de trabajo que requiere aprobación antes de que se guarde la nueva información. Los flujos de trabajo están predefinidos para los siguientes tipos de información para ayudarle a gestionar de manera eficiente los cambios y mantener preciosos los datos de sus empleados:

-   Números de identificación
-   Cursos
-   Formación
-   Imagen
-   Artículos prestados
-   Experiencia profesional
-   Experiencia en proyectos
-   Aptitudes
-   Puestos de confianza
-   Acciones de recursos humanos
-   Registro del curso

Cuando se contrata, transfiere o despide a empleados, el flujo de trabajo puede incluir un proceso de revisión. De esta manera, se puede revisar un documento o se puede definir una acción como parte del flujo de trabajo. Cuando se completa el proceso de revisión, se completa el documento o la acción, y el flujo de trabajo se mueve a un paso de aprobación final.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Asociar un flujo de trabajo a una jerarquía de puestos

Puede asociar un flujo de trabajo con cualquier jerarquía de posición que configure. Se utilizan dos tipos de jerarquía para el enrutamiento del flujo de trabajo: **Gerencial** y **Configurable**.

- Una jerarquía **Gerencial** representa la estructura de informes de la empresa u organización. Para obtener más información sobre este tipo de jerarquía, consulte [Informes a la posición](hr-personnel-positions.md#reports-to-position).
- Una jerarquía **Configurable** representa una matriz o una jerarquía personalizada. Para obtener más información sobre este tipo de jerarquía, consulte [Relaciones](hr-personnel-positions.md#relationships).

### <a name="managerial-hierarchy-example"></a>Ejemplo de jerarquía gerencial

Puede configurar un flujo de trabajo para que cuando un empleado envíe una solicitud de compra de un ordenador nuevo, la solicitud se dirija al gerente del empleado y al gerente de nivel de omisión. Cuando configure el paso del flujo de trabajo, configure el campo **Tipo de asignación** a **Jerarquía**. La pestaña **Tipo de jerarquía** entonces estará disponible. Para este ejemplo, seleccione la jerarquía **Gerencial**.

### <a name="configurable-hierarchy-example"></a>Ejemplo de jerarquía configurable

Si un puesto está asociado a una jerarquía de informes de matriz, puede configurar un flujo de trabajo que distribuye los gastos para un proyecto específico al cliente potencial del proyecto en lugar de al director del empleado En este caso, establezca el campo **Tipo de asignación** en **Jerarquía**. Después, en la pestaña **Tipo de jerarquía**, seleccione **Jerarquía configurable**. Después de configurar el flujo de trabajo, seleccione la jerarquía **Asociado** en la página **Configuración del flujo de trabajo** para seleccionar la jerarquía que debe usarse para el enrutamiento del flujo de trabajo.

> [!IMPORTANT]
> Cuando se envía un documento, una transacción o un registro maestro para la aprobación del flujo de trabajo, la posición principal del remitente se utilizará para determinar a quién se debe enrutar el documento a continuación.

### <a name="hierarchy-setting-in-workflow-parameters"></a>Configuración de jerarquía en los parámetros del flujo de trabajo

1. En la página **Parámetros de flujo de trabajo** vaya a **Enrutamiento de jerarquía**.
2. De forma predeterminada, la opción **Usar jerarquía de posición** se establece en **No**. En este caso, el flujo de trabajo utilizará la posición principal del trabajador cuando navegue por la jerarquía. Establezca la opción para **Sí** para hacer que el flujo de trabajo use el primario del puesto cuando navegue por la jerarquía.

### <a name="additional-example"></a>Ejemplo adicional 

La empleada Grace Sturman tiene dos puestos: consultora y capacitadora. El puesto principal de Grace es capacitadora. Cuando no está capacitando a nuevos empleados, está disponible para trabajos de consultoría. A través de su puesto principal, Grace le reporta a Claire, la directora de recursos humanos. Claire informa a Charlie. Para su puesto de consultora, Grace tiene múltiples relaciones de línea de puntos, según el proyecto.

La empresa de Grace crea reglas de enrutamiento de flujo de trabajo que se basan en una jerarquía **Configurable** (matriz/jerarquías basadas en proyectos). Esta jerarquía utiliza el puesto de consultor de Grace. Si la opción **Usar jerarquía de puestos** está configurada para **No**, cuando se enruta un documento a Grace para su aprobación, el flujo de trabajo observará su puesto principal (entrenador) para determinar dónde se debe enrutar el documento a continuación. En este caso, se enrutará primero a Claire y luego a Charlie. Si la opción está configurada en **Sí** y el flujo de trabajo utiliza una jerarquía **Configurable**, el flujo de trabajo observará el puesto de consultor de Grace y la relación de informes para determinar dónde se debe enrutar el documento a continuación.

### <a name="configure-a-human-resources-workflow"></a>Configurar un flujo de trabajo de las acciones de recursos humanos
Siga estos pasos para configurar un flujo de trabajo básico que se inicia cuando la solicitud de los empleados cambia a su identificación personal.

1.  En la página **Flujos de trabajo de recursos humanos**, seleccione **Nuevo**.
2.  En la lista de flujos de trabajo disponibles, seleccione **Números de identificación**.
3.  Seleccione **Ejecutar** para abrir el diseñador de flujo de trabajo y, a continuación, introduzca su nombre de usuario y contraseña.
4.  Mueva el elemento **Aprobar número de identificación** de la lista de elementos de flujo de trabajo al lienzo de diseñador.
5.  Conecte el elemento de aprobación para **Empezar** y **Finalizar**.
6.  Toque dos veces (o haga doble clic) **Aprobar elemento**, seleccione y mantenga presionado (o haga clic con el botón derecho), y luego seleccione **Propiedades**.
7.  Siga estos pasos para agregar las instrucciones del elemento de trabajo:

    1.  Seleccione **Asignación** y, a continuación, seleccione **Jerarquía** en el tipo de asignación.
    2.  En la selección **Jerarquía**, seleccione **Jerarquía configurable**.
    3.  Agregue una condición de detención y cierre la página.

8.  Complete cualquier instrucciones adicionales.
9.  Seleccione **Guardar y cerrar**. Active el nuevo flujo de trabajo cuando se abra el cuadro de diálogo, y seleccione **Activar**.
10. Vaya a **Recursos Humanos** &gt; **Puestos** &gt; **Tipos de jerarquías de puestos**
11. Seleccione **Matriz**.
12. Agregue el flujo de trabajo **Número de identificación de trabajador** a la lista.

## <a name="additional-resources"></a>Recursos adicionales

[Ver y administrar cambios de dirección](hr-personnel-view-address-changes.md) 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
