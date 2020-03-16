---
title: Funcionalidad de cuadrícula
description: Este tema describe varias características potentes del control de cuadrícula. La nueva función de cuadrícula debe estar habilitada para tener acceso a estas capacidades.
author: jasongre
manager: AnnBe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7136edba828bf97b6e0c8d2a698b884640d680e5
ms.sourcegitcommit: 880f617d1d6e95eccbed762c7ea04398553c2ec0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036274"
---
# <a name="grid-capabilities"></a>Funcionalidad de cuadrícula

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

El nuevo control de cuadrícula proporciona una serie de capacidades útiles y potentes que se pueden utilizar para mejorar la productividad del usuario, construir vistas más interesantes de sus datos y obtener información significativa sobre sus datos. Este artículo cubrirá las siguientes capacidades: 

-  Cálculo de los totales
-  Agrupar datos
-  Escribir por delante del sistema
-  Evaluar expresiones matemáticas 

## <a name="calculating-totals"></a>Cálculo de los totales
En las aplicaciones de Finance and Operations, los usuarios tienen la capacidad de ver los totales en la parte inferior de las columnas numéricas en las cuadrículas. Estos totales se muestran en una sección de pie de página en la parte inferior de la cuadrícula. 

### <a name="showing-the-grid-footer"></a>Mostrar el pie de página de la cuadrícula
Hay un área de pie de página en la parte inferior de cada cuadrícula tabular en las aplicaciones Finance and Operations. El pie de página puede mostrar información valiosa relacionada con los datos que aparecen en la cuadrícula. Algunos ejemplos de esta información son:

- El número de filas seleccionadas en la tabla (cuando se selecciona más de un registro)
- Totales generales en la parte inferior de las columnas numéricas configuradas
- El número de filas del conjunto de datos 

Este pie de página está oculto de forma predeterminada, pero se puede activar fácilmente. Para mostrar el pie de página de una cuadrícula, haga clic con el botón derecho en el encabezado de una columna en la cuadrícula y seleccione la opción **Mostrar pie de página**. Una vez que el pie de página se ha activado para una cuadrícula en particular, esa configuración se recordará hasta que el usuario opte por ocultar el pie de página, lo que se puede hacer haciendo clic derecho en el encabezado de una columna y seleccionando **Ocultar pie de página**.  Tenga en cuenta que se espera que la acción **Mostrar pie de página/Ocultar pie de página** se reubique en una actualización futura. 

### <a name="specifying-columns-with-totals"></a>Especificar columnas con totales
Actualmente, no se configurarán columnas para mostrar totales por defecto. En cambio, esto se considera una actividad de configuración única, similar a ajustar el ancho de las columnas en las cuadrículas. Una vez que especifique que desea ver los totales de una columna, esa configuración se recordará la próxima vez que visite la página.  

Hay dos formas de configurar una columna para mostrar un total: 

- Haga clic con el botón derecho en la columna para la que quiere ver un total y después seleccione **Totalizar esta columna**. Esta acción hace que ocurran tres eventos:

    1. El pie de página se hace visible. 
    2. Se guardará su preferencia para ver un total en esta columna. 
    3. Se iniciará un cálculo de totales para esta columna y cualquier otra que haya configurado previamente para ver los totales. El tiempo que se requiere para mostrar un total depende del tamaño del conjunto de datos que está totalizando.

- Después de que el pie de página esté visible, seleccione **Mostrar total** en el área de pie de página en la parte inferior de la columna para la que desea ver un total. Si no hay columnas configuradas, el botón **Mostrar total** estará disponible para todas las columnas numéricas. 

    Una vez que haya al menos una columna configurada para los totales, los botones **Mostrar total** solo estarán disponibles al pasar el ratón o al enfocar. La acción de seleccionar **Mostrar total** solo guarda su preferencia para ver un total en esta columna, de modo que la preferencia se aplique durante futuras visitas a la página. En el pie de página, este estado se indica mediante un guión que aparece en la columna. (Alternativamente, si el conjunto de datos es lo suficientemente pequeño, se muestra un total de inmediato).

Si comete un error y ya no desea ver un total en una columna en particular, haga clic con el botón derecho en la columna y seleccione **Ocultar total** o seleccione el botón **Ocultar total** en el pie de página de esa columna. Esta preferencia también se guardará para futuras visitas a la página. 

### <a name="calculating-totals"></a>Cálculo de los totales
Cuando llega a una página con el pie de página visible y las columnas ya configuradas para los totales, los totales pueden mostrarse o no en el pie de página. El comportamiento depende del tamaño del conjunto de datos en la página. Si el conjunto de datos es lo suficientemente pequeño, los totales se mostrarán automáticamente, junto con el número de filas en el conjunto de datos. Si hay guiones en el pie de página debajo de las columnas que configuró para los totales, entonces el conjunto de datos es demasiado grande para que el sistema muestre los totales de inmediato, y se necesita una acción explícita para calcular los totales. Para hacer esto, haga clic en el botón **Calcular** en el pie de página, o haga clic con el botón derecho en una columna para la que desea un total y seleccione **Totalizar esta columna**.  

Si el cálculo tarda demasiado, puede cancelar la operación seleccionando el botón **Cancelar**. Sin embargo, a veces, el conjunto de datos será demasiado grande para calcular los totales (un límite impuesto por su organización) y, en su lugar, se le notificará para que filtre más sus datos.

Los totales se actualizarán automáticamente a medida que actualice, elimine o cree filas en el conjunto de datos.  

## <a name="grouping-data"></a>Agrupar datos
Los usuarios comerciales a menudo necesitan realizar análisis de datos ad-hoc. Si bien esto se puede hacer exportando datos a Microsoft Excel y usando tablas dinámicas, la funcionalidad de **Agrupamiento** en cuadrículas tabulares permite a los usuarios organizar sus datos de manera interesante dentro de las aplicaciones de Finance and Operations. Como esta característica extiende la característica **Totales**, **Agrupamiento** también permite obtener información significativa sobre los datos al proporcionar subtotales a nivel de grupo.

Para usar esta función, haga clic con el botón derecho en la columna por la que desea agrupar y seleccione **Agrupar por esta columna**. Esta acción ordenará los datos por la columna seleccionada, agregará un nuevo Grupo por columna al principio de la cuadrícula e insertará "filas de encabezado" al comienzo de cada grupo. Estas filas de encabezado proporcionan la siguiente información sobre cada grupo: 
-  Valor de datos para el grupo 
-  Etiqueta de columna (esta información será especialmente útil después de que se admitan múltiples niveles de agrupación).
-  Número de filas de datos en este grupo
-  Subtotales para cualquier columna configurada para mostrar totales

Con [Vistas guardadas](saved-views.md) habilitado, esta agrupación se puede guardar mediante personalización como parte de una vista para un acceso rápido la próxima vez que visite la página.  

Si selecciona **Agrupar por esta columna** para una columna diferente, la agrupación original será reemplazada, porque solo un nivel de agrupación es compatible con la versión 10.0.9 / Platform update 33.

Para deshacer la agrupación en una cuadrícula, haga clic derecho en la columna de agrupación y seleccione **Desagrupar**.  


## <a name="evaluating-math-expressions"></a>Evaluar expresiones matemáticas
Como un refuerzo de productividad, los usuarios pueden introducir fórmulas matemáticas en celdas numéricas en una cuadrícula. No tienen que hacer el cálculo en una aplicación fuera del sistema. Por ejemplo, si introduce **= 15\*4** y después pulsa la tecla **Tab** para salir del campo, el sistema evaluará la expresión y guardará un valor de **60** para el campo.

Para que el sistema reconozca un valor como una expresión, comience el valor con un signo igual (**=**). Para obtener más detalles sobre los operadores y la sintaxis compatibles, vea [Símbolos matemáticos admitidos](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).  
