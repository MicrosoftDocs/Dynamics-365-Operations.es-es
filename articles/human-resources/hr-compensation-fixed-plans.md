---
title: Actualizar planes de compensación fija
description: La compensación fija hace referencia al sueldo o salario bruto regular de un empleado. Este artículo describe los componentes que deben configurarse para poder crear un plan de compensación fija e inscribir a empleados.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompRefPointSetup, HRMCompEligibility, HRMCompEvent, HRMFixedCompPlanTable, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 15991
ms.assetid: ef8cf992-176c-4c98-9dff-6510e1eb9f1c
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: cc6a639bd593b9a41217a054023a9de82f373c1f
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465783"
---
# <a name="create-a-fixed-compensation-plans"></a>Crear un plan de compensación fija

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

La compensación fija hace referencia al sueldo o salario bruto regular de un empleado. Este artículo describe los componentes que deben configurarse para poder crear un plan de compensación fija e inscribir a empleados.

Los importes de compensación fija se pueden calcular para sus empleados, en función de factores como el rendimiento, la región y los aumentos de presupuesto. Dynamics 365 Human Resources admite tipos de compensación de banda, paso y categoría.

## <a name="fixed-compensation-components"></a>Componentes de compensación fija
### <a name="compensation-levels"></a>Niveles de compensación

Puede usar **niveles de compensación** para establecer la compensación para varios trabajos, para ayudar a garantizar que se paga justamente a los empleados que realizan esos trabajos. En la página **Niveles de compensación**, puede configurar los niveles de compensación necesarios para cada plan de banda, categoría y paso. Use los botones **Arriba** y **Abajo** para colocar los niveles en el orden correcto, según su tipo. Al establecer los niveles de compensación en un trabajo, ayuda a garantizar que se les paga en el mismo nivel a todos los empleados que mantienen un puesto para ese trabajo.

### <a name="reference-points"></a>Puntos de referencia

Los **puntos de referencia** son las columnas de la cuadrícula que definen los intervalos de compensación para cada nivel. El nivel de compensación es la fila de la cuadrícula. Los puntos de referencia típicos para un plan del tipo de categoría son un mínimo, un punto medio y un máximo. Cree los puntos de referencia en la página **Configuraciones de puntos de referencia**.

### <a name="compensation-grids"></a>Cuadrículas de compensación

Después de configurar los niveles y los puntos de referencia, se pueden combinar para crear una **cuadrícula de compensación** En la página **Cuadrículas de compensación**, defina la información sobre la cuadrícula. Por ejemplo, especifique para qué se usa la cuadrícula diseñada, con qué tipo de plan se usará y qué puntos de referencia o columnas se requieren en la cuadrícula. Una vez que haya terminado de especificar esa información, haga clic en **Estructura de compensación** para agregar niveles e importes a la cuadrícula. 

**Sugerencia:** Use la función de **cambios masivos** en la estructura de compensación para establecer importes iniciales, e incrementar después por porcentajes o importes en sus niveles o puntos de referencia.

### <a name="pay-frequencies"></a>Frecuencias de pago

Las **Frecuencias de pagos** se usan para definir cómo se está especificando el salario o el sueldo de un empleado (por ejemplo, 10 $ por hora frente a 50.000 $ al año), y la conversión entre las tarifas por hora, semanales, mensuales (12 meses) y anuales. Por ejemplo, una empresa que usa una semana laboral de 38 horas para sus empleados por hora configura una frecuencia de pago que tiene un índice por hora de 1, un índice semanal de 38, un índice mensual de 164,6666666667 y un índice anual de 1,976. Estas conversiones se usan para calcular los diferentes índices salariales que aparecen en el registro de compensación fija de un empleado.

## <a name="fixed-compensation-plans"></a>Planes de compensación fija
Puede diseñar el plan de compensación fija para combinar todos los componentes que ha configurado. Para crear un plan de compensación fija, abra la página **Planes de compensación fija**. Aquí, puede dar un nombre y una descripción al plan, seleccionar qué tipo de plan es (paso, categoría o banda), seleccione la frecuencia de los pagos que usará para el índice salarial del empleado (importe por hora, importe por año, etc.) y establecer algunas opciones que controlan cómo se procesa la compensación. 

La configuración **Fuera del intervalo de tolerancia** le permite especificar cómo de estricto desea ser acerca de asegurarse de que los importes de compensación se encuentran entre los importes mínimo y máximo. Una tolerancia **Fuerte** requiere esa compensación se encuentre dentro del intervalo definido para un nivel determinado. La tolerancia **Débil** le alerta cuando el importe de compensación se encuentra fuera del intervalo pero le permite continuar. Si establece la tolerancia en **Ninguna**, puede especificar cualquier importe de compensación para un empleado sin recibir mensajes de error o advertencia. 

La configuración **Regla de contratación** le permite especificar si todos los empleados deben recibir el mismo aumento, independientemente de la fecha en que se les contrató (**Regla de contratación** = **Ninguna**), o si los empleados deben recibir un porcentaje de la prima, en función del tiempo en que estuvieron empleados durante el ciclo (**Regla de contratación** = **Porcentaje**). 

Una **matriz de intervalo de aprovechamiento** es útil si desea reducir el tiempo necesario para que los empleados alcancen el punto medio de su intervalo, o para aumentar el tiempo necesario para que los empleados alcancen al punto de referencia máximo del intervalo. Por ejemplo, desea dar a los empleados que están en la parte inferior del 25 por ciento del intervalo el 110 por cien de la prima prevista, y darle a los empleados que están en el 25 por ciento superior de su intervalo solo el 80 por ciento de su prima prevista, para evitar que alcance el máximo tan rápidamente. 

Después de definir los conceptos básicos del plan de compensación fija, puede configurar la estructura de compensación para el plan. Haga clic en **Configurar compensación**. Se abre un control deslizante de diálogo que le ofrece tres opciones:

-   Crear una nueva cuadrícula de compensación seleccionando una configuración de punto de referencia y dando un nombre a la cuadrícula.
-   Crear una nueva cuadrícula de compensación realizando una copia de una cuadrícula existente que pueda usar como punto de partida.
-   Usar una cuadrícula de compensación existente que ya se ha definido. Todos los planes de compensación que usan la misma cuadrícula reciben actualizaciones si se modifica esa cuadrícula.

Tras seleccionar una opción, se abrirá la página **Estructura de compensación** y podrá realizar cambios en la nueva cuadrícula de compensación o la cuadrícula de compensación existente.

## <a name="fixed-compensation-enrollment"></a>Inscripción de compensación fija
### <a name="determine-who-is-eligible-for-the-plan"></a>Determinar quién es apto para el plan

El primer paso en la inscripción de empleados en un plan de compensación fija es determinar quién es apto para la compensación que está definida en el plan. Hasta que determine la idoneidad, no podrá asignar el plan a ningún empleado. Para configurar la idoneidad, abra la página **Reglas de idoneidad**. Aquí, crea una nueva regla de idoneidad para su plan de compensación y define los criterios que un empleado debe cumplir para ser apto para un plan. Puede limitar la idoneidad en función del departamento, el sindicato, región de compensación (ubicación ), trabajo, función de trabajo, tipo de trabajo o nivel de compensación. Los empleados solo se pueden inscribir en un plan de compensación si cumplen todas las condiciones que se establecen en la regla de idoneidad. 

**Nota:** Las reglas de idoneidad se utilizan para determinar la idoneidad para planes de compensación tanto fijos como variables. 

La regla de idoneidad considera el valor de campos específicos en los registros Trabajo, Puesto y Empleado para determinar si un empleado es apto para un plan de compensación.

-   En la página **Trabajo**, la regla de idoneidad considera los siguientes campos:
    -   El campo **Trabajo**
    -   En la pestaña **Clasificación de trabajo**, los campos **Función** y **Tipo de trabajo**
    -   En la pestaña **Compensación**, el campo **Nivel**
-   En la página **Puestos**, la regla de idoneidad considera los campos **Departamento** y **Región de compensación**.

La regla de idoneidad también considera los sindicatos asociados al empleado (en la página **Empleados**, en la pestaña **Trabajador**, haga clic en **Información personal** &gt; **Sindicatos**).

### <a name="define-fixed-compensation-actions"></a>Definir acciones de compensación fija

Las **acciones de compensación fija** se utilizan cuando establece o aplica cambios a la compensación fija de un empleado. Las acciones de compensación fija le permiten proporcionar nombres descriptivos para los tipos de acciones que un Director de compensaciones y prestaciones puede realizar. Distintos tipos de acción tienen una lógica especial detrás de ellos, para que se puedan usar en momentos específicos. 

Por ejemplo, cuando la compensación fija se configura para un empleado, solo se pueden usar las acciones que tienen un tipo de **Contratar/Volver a contratar**. En este caso, puede que desee crear tres acciones diferentes del tipo **Contratar/Volver a contratar** y nombrarlas **Contratar**, **Volver a contratar** y **Transferir**. A continuación, tiene una explicación más descriptiva del motivo por el que se dio la compensación fija a un empleado o se cambió.

### <a name="enroll-the-employee"></a>Inscribir al empleado

Ahora puede asignar un empleado a un plan de compensación fija. Abra la página **Empleados** y seleccione el empleado que desea inscribir en el plan de compensación. En el panel de acciones, haga clic en **Compensación** &gt; **Plan fijo**. Ahora puede crear una nueva acción de compensación fija para ese empleado. 

**Nota:** El campo del plan de compensación muestra solo planes para los que un empleado es apto según las reglas de idoneidad que se configuraron para cada plan. Si no se ha configurado ninguna regla de elegibilidad para un plan, ningún empleado será apto para dicho plan. 

El sistema comprueba que el importe de compensación que se especifica para un plan de compensación del tipo de banda o clasificación se encuentra dentro de los puntos de referencia mínimo y máximo para el nivel de compensación proporcionado en el trabajo del empleado. Si el importe de compensación se encuentra fuera del intervalo permitido, se mostrará un mensaje de advertencia o error, en función del nivel de tolerancia que se establece en el plan de compensación fija.



[!INCLUDE[footer-include](../includes/footer-banner.md)]