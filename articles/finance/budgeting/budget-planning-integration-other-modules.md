---
title: Integración de planificación presupuestaria con otros módulos
description: Se pueden generar planes presupuestarios desde diversos recursos diferentes. Los elementos básicos del proceso periódico son iguales para todos los recursos.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 64443
ms.assetid: f9a94db5-906c-404a-9ca5-91528d67c490
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7456d0c6a9114fae71aff7b4070d86090e2c7c9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447729"
---
# <a name="budget-planning-integration-with-other-modules"></a>Integración de planificación presupuestaria con otros módulos

[!include [banner](../includes/banner.md)]

 Se pueden generar planes presupuestarios desde diversos recursos diferentes. Los elementos básicos del proceso periódico son iguales para todos los recursos. 



<a name="periodic-processes-for-generating-budget-plans"></a>Procesos periódicos para generar planes presupuestarios
----------------------------------------------

Se pueden generar planes presupuestarios desde los recursos siguientes:

-   Transacciones de contabilidad general
-   Activos fijos
-   Puestos de previsión
-   Previsiones de proyectos
-   Previsiones de suministro
-   Previsiones de la demanda
-   Entradas de registro presupuestario
-   Otros planes presupuestarios

Los elementos básicos del proceso periódico son iguales para todos los procesos. Las pestañas le permiten definir el origen de los datos, los atributos de destino (plan presupuestario) y opciones para ejecutar el proceso en segundo plano como un proceso por lotes. En secciones posteriores de este artículo se describen los elementos que no sean evidentes en cada proceso.

### <a name="actions"></a>Acciones 

Para cada proceso de generación, hay tres acciones disponibles:

-   **Crear un nuevo plan presupuestario** crea un nuevo plan con los atributos que están seleccionados en la sección **Destino**. Estos atributos no tienen que ser exclusivos. Por lo tanto, dos planes pueden tener el mismo nombre y otros valores.
-   **Sustituir el escenario del plan presupuestario existente** elimina todos los datos en el plan presupuestario de destino en el escenario seleccionado del plan presupuestario y crea nuevas líneas que usan los datos de origen seleccionados.
-   **Actualizar el escenario del plan presupuestario existente y anexar nuevos datos** actualiza las líneas existentes en el plan de destino que coinciden con las líneas de origen y agrega nuevas líneas para los nuevos datos. La conciliación se basa en la cuenta contable, la fecha, la clase de presupuesto y otros campos. Por ejemplo, al generar planes presupuestarios de puestos de previsión, el número de posición es un campo importante. Todas las líneas con un número de posición que coincida con el número de posición de origen se sustituyen por las nuevas líneas de origen.

### <a name="source"></a>Origen

Para todos los procesos, la pestaña **Origen** la ficha le permite filtrar los datos mediante el botón **Filtro**. De forma predeterminada, los campos específicos se agregan al filtro para cada proceso. Por ejemplo, para el proceso **Generar el plan presupuestario desde contabilidad general**, las categoría **Cuenta contable** y **Cuenta principal** están disponibles y aparecen en la página de la generación. Cualquier campo que agregue al filtro también se agrega a la página, junto con los criterios que se agreguen.

### <a name="target"></a>Destino

La opción **Histórico** en la pestaña **Destino** le permite usar las fechas de los datos de origen como la fecha de vigencia en el plan presupuestario. Normalmente, la fecha de vigencia debe situarse dentro del ciclo presupuestario del plan. Cuando establece la opción **Histórico** en **Sí**, la fecha (incluso el año) del origen se utiliza, de manera que pueda usar los últimos datos como base para la comparación. No puede modificar datos históricos en el plan presupuestario, y el plan se establece en un estado del flujo de trabajo aprobado. Sin embargo, puede restablecer el estado si otros escenarios en el plan requieren cambios.

El campo **Agregar total por** en la parte superior de la página también determina la fecha que se usa. Este campo realiza un total de los importes y establece opcionalmente la fecha de vigencia al primer día del ejercicio o período fiscal. 

Muchos de los campos de la pestaña <strong>Destino</strong> pasan a ser editables o de sólo lectura, en función de la acción que seleccione. Cuando cambia de crear un nuevo plan presupuestario a actualizar un plan existente, el campo **Nombre del plan presupuestario** pasa a estar disponible, y los campos relacionados con la selección de un plan existente están disponibles. En las pestañas **Destino** y **Origen**, el campo **Libro mayor** nunca está disponible porque el valor está determinado por el proceso seleccionado de planificación presupuestaria. 

El campo **Clase de presupuesto** permite establecer las líneas del plan presupuestario como transacciones de gastos o transacciones de ingresos. Normalmente, las transacciones de ingresos son créditos en una cuenta contable y por tanto se almacenan como importes negativos. Normalmente, estas transacciones también aparecen como importes negativos en el plan presupuestario. Sin embargo, si se agrega la clase de presupuesto como un campo en el diseño del plan, los ingresos aparecerán como importes positivos.

### <a name="generation-rules"></a>Reglas de generación

Tres campos proporciona funciones adicionales: **Factor**, **Mínimo** y **Regla de** **redondeo**. 

El valor del campo **Factor** se multiplica por el importe de origen para establecer el importe en el plan presupuestario. Luego podrá realizar ajustes al crear líneas de plan presupuestario. Por ejemplo, puede especificar **1,03** para un aumento del 3 por ciento. El factor debe ser un número entero positivo. 

El campo **Mínimo** permite establecer el umbral del importe para crear una línea del plan presupuestario. Si el importe de origen es inferior a este número, la línea del plan presupuestario no se crea. Un valor de **0,00** permite todos los importes pero no limita las líneas a los importes positivos. (Ningún valor limita las línea a importes positivos. Los importes negativos siempre se incluyen y representan normalmente entradas de crédito).

El campo **Regla de redondeo** permite establecer la precisión de las líneas del plan presupuestario que se crean. Puede redondear los importes al 1,00, 10,00, 100,00, etc., de divisa más cercano.

## <a name="notes-for-specific-processes"></a>Notas para procesos específicos
### <a name="generate-budget-plan-from-general-ledger"></a>Generar plan presupuestario a partir de contabilidad general

Al crear un plan presupuestario de datos de contabilidad general, debe definir el campo **Agregar total por** a **Ejercicio** si la opción **Histórico** está establecida en **No**. Los períodos y las fechas del origen pueden no coincidir con los períodos de fechas en el destino. Dado que el proceso no tiene ninguna forma fiable de asignar estos valores, debe limitar el proceso al primero de año. 

En el destino, el campo **Clase de presupuesto** se establece en **Gastos** o **Ingresos**. Esta configuración se usa para seleccionar el atributo **Tipo de presupuesto** para las líneas que se creen, cuando la cuenta principal en una línea no es de tipo **Ingresos** o **Gastos**.

### <a name="generate-budget-plan-from-fixed-assets"></a>Generar un plan presupuestario a partir de activos fijos

El proceso **Generación del plan presupuestario de activos fijos** no tiene ninguna opción para agregar por período o día. Tampoco hay opción para definir el plan como histórico. Puede usar este proceso periódico para incluir las transacciones previstas para los activos fijos en la planificación presupuestaria.

### <a name="generate-budget-plan-from-forecast-positions"></a>Generar plan presupuestario a partir de posiciones de previsión

El proceso **Generación del plan presupuestario de posiciones de previsión** asigna la posición de previsión de origen a la línea del plan presupuestario. Puede ver la posición al agregar la posición de previsión como una fila en el diseño del plan presupuestario o mediante la consulta **Líneas del plan presupuestario**. Si no desea que la posición de previsión se asigne a líneas del plan presupuestario, establezca la opción **Incluir posición en la línea del plan presupuestario** en **No**.

Las líneas en el plan presupuestario se agregarán por cuenta contable y posición. Sin embargo, puede excluir el número de posición, de modo que las líneas se agreguen solo por cuenta contable. En la pestaña **Destino**, establezca la opción **Incluir posición en el plan presupuestario** en **No**.

En el campo **Escenario de FTE del plan presupuestario**, puede seleccionar un escenario para incluir el número de equivalentes a jornada completa (FTE) en el plan presupuestario. Este campo está limitado a los escenarios de tipo de cantidad que se incluyen en el diseño del plan presupuestario de destino. Si selecciona un escenario de FTE, también debe seleccionar una cuenta principal de FTE. Esta cuenta se usa para crear las líneas del plan presupuestario de la cantidad. 

El proceso de planificación presupuestaria y el escenario de del plan presupuestario seleccionados en el origen establecen el proceso y el escenario de planificación presupuestaria del escenario de destino. Dado que estos atributos se asignan a posiciones de previsión, deben coincidir con el plan presupuestario. Por tanto, estos atributos no se pueden modificar en el destino.

### <a name="generate-budget-plan-from-project-forecasts"></a>Generar plan presupuestario a partir de previsiones de proyecto

El proceso **Generación del plan presupuestario de previsiones de proyecto** como el proceso **Generación del plan presupuestario de posiciones de previsiones**, tiene una opción para incluir las cantidades de proyecto (horas, gastos y artículos) en un escenario de cantidad. Los dos procesos también tienen filtros similares para las columnas del diseño del plan presupuestario. 

En la pestaña **Origen**, hay tres opciones en la sección **Incluir extracto** que determinan qué líneas del plan presupuestario se crean. Estas opciones son iguales que las opciones disponibles al crear asientos de registro presupuestario directamente de previsiones de proyecto. Establezca la opción **Pérdidas y ganancias** en **Sí** para crear líneas para los costes y para los ingresos. Establezca la opción **WIP** en **Sí** para crear entradas de trabajo en curso. Establezca la opción **Asignación de nóminas** en **Sí** para crear líneas para la cuenta de contrapartida de nóminas para transacciones por horas. 

No existe el campo **Clase de presupuesto**, porque la clase de presupuesto (**Gastos** o **Ingresos**) viene determinada por el origen. 

Puede usar los presupuestos de proyecto como un origen seleccionando el modelo de previsión que contiene los importes presupuestarios de proyecto. Recuerde que los presupuestos de proyecto crearán entradas de previsión de proyecto a medida que se aprueban.

Para seleccionar sólo costes o ingresos para las líneas del plan presupuestario, use el filtro para seleccionar <strong>Actualizaciones de presupuesto: tipo de importe = coste</strong>seleccionar. Para seleccionar solo un tipo de previsión, use el filtro para seleccionar <strong>Actualizaciones de presupuesto: tipo de transacción = *xxx</strong>*. 

Solo se puede usar un modelo de previsión para generar un escenario del plan presupuestario. Si ejecuta el proceso para un modelo de previsión y después realiza una actualización e intenta especificar otro modelo, el primer modelo se sobrescribirá si se aplica el mismo proyecto y cuentas contables. Para generar un escenario del plan presupuestario a partir de más de un modelo de previsión, genere en distintos escenarios del plan presupuestario y use las opciones de asignación para agregarlas conjuntamente en otro escenario. 

El proceso **Generación del plan presupuestario de previsiones de proyecto** también asigna el proyecto de origen a la línea del plan presupuestario.

### <a name="generate-budget-plan-from-supply-forecast"></a>Generar plan presupuestario a partir de previsión de suministro

Las opciones de filtro de origen en el proceso **Generación del plan presupuestario de previsión de suministro** han sido modeladas de acuerdo con las opciones en la funcionalidad **Transferencia de presupuesto de compras a libro mayor**, debido a semejanzas entre el proceso y la funcionalidad.

### <a name="generate-budget-plan-from-demand-forecast"></a>Generar plan presupuestario a partir de previsión de la demanda

Para el proceso **Generación del plan presupuestario de previsión de demanda**, puede establecer la opción **Pedido de ventas** en **Sí** para generar líneas de ingresos en el plan presupuestario, establecer **Consumo** en **Sí** para crear líneas de gastos o establecer ambas opciones en **Sí**.

### <a name="generate-budget-plan-from-budget-register-entries"></a>Generar plan presupuestario a partir de las entradas del registro presupuestario

Para el proceso **Generación del plan presupuestario de asientos de registro presupuestario**, el origen debe especificar un submodelo, un código presupuestario y un número de entrada. Es decir, puede crear líneas del plan presupuestario para solo un asiento de registro presupuestario cada vez. Puede usar entradas adicionales en el mismo plan presupuestario si ejecuta el proceso una vez para cada entrada de origen.

### <a name="generate-budget-plan-from-budget-plan"></a>Generar plan presupuestario a partir de un plan presupuestario

Para el proceso **Generación del plan presupuestario de plan presupuestario**, un conjunto adicional de opciones en la pestaña **Destino** le permite asignar nuevas dimensiones financieras. Si se selecciona una dimensión financiera, ese valor se usará para todas las líneas del plan presupuestario. Por lo tanto, puede usar un plan presupuestario como base para otros planes presupuestarios, pero también puede asignar, por ejemplo, un departamento o centro de costediferente a los nuevos planes presupuestarios.

## <a name="looking-back-from-the-budget-plan"></a>Repaso del plan presupuestario
### <a name="budget-plans-by-dimension-set-inquiry"></a>Consulta de planes presupuestarios por conjunto de dimensiones

La consulta **Planes presupuestarios por conjunto de dimensiones** incluye varias opciones que le permiten ejecutar una consulta para ayudar a identificar el origen de los datos del plan presupuestario. 

Seleccione una línea y haga clic en el botón **Líneas del plan presupuestario** para ejecutar la consulta **Líneas del plan presupuestario**. Los resultados se filtran para los valores de dimensión de la línea seleccionada. Puede aplicar parámetros adicionales. 

Use los botones **Previsión de suministro** y **Previsión de demanda** para ejecutar estas consultas. En ambos casos, la consulta busca las líneas de previsión que podrían haber creado las líneas del plan presupuestario. 

Los informes adicionales disponibles incluyen el informe **Posiciones de previsión por plan presupuestario**. Este informe es especialmente útil si se desea determinar si una posición se ha asignado correctamente a los planes presupuestarios.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]