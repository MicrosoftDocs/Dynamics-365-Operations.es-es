---
title: Actualización de la planificación presupuestaria
description: Existen diferencias significativas en el plan presupuestario entre Microsoft Dynamics AX 2012 y Dynamics 365 Finance. Algunas funciones no se actualizaron y por tanto requieren una reconfiguración. Este tema explica qué debe volver a configurarse y también describe las nuevas características que deben tenerse en cuenta una vez que la actualización se haya completado.
author: ryansandness
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 272923
ms.assetid: 17cdfe74-bdfd-466a-9bdd-c12583f250c7
ms.search.region: Global
ms.author: ryansand
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 1c62771170212039112c777e55d45a0d88d2f49d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681007"
---
# <a name="upgrade-budget-planning"></a>Actualización de la planificación presupuestaria

[!include [banner](../includes/banner.md)]

Existen diferencias significativas en el plan presupuestario entre Microsoft Dynamics AX 2012 y Dynamics 365 Finance. Algunas funciones no se actualizaron y por tanto requieren una reconfiguración. Este tema explica qué debe volver a configurarse y también describe las nuevas características que deben tenerse en cuenta una vez que la actualización se haya completado.  

El plan presupuestario de Finance tiene muchos mejoras que no estaban disponibles en Dynamics AX 2012. Este tema explica los cambios que los clientes que realizan una actualización deben llevar a cabo. También indica las nuevas características que se deben tener en cuenta durante el proceso de actualización. Debido a la extensión de los cambios, no se podrá abrir ningún plan de presupuesto existente hasta que no se hayan llevado a cabo los cambios descritos en este tema. Sin embargo, en principio los informes deben seguir funcionando y no se requerirá efectuar ningún cambio adicional.

## <a name="overview-of-changes"></a>Visión general de los cambios
Se han introducido muchos cambios importantes en la gestión presupuestaria de Finance and Operations. Estos cambios tienen por objeto facilitar la configuración de la planificación presupuestaria y hacer que sea más reutilizable, a fin de reducir el mantenimiento y la configuración año tras año. Las siguientes áreas de AX 2012 ya no existen en Finance:

-   Plantillas del plan presupuestario (configuración de la planificación presupuestaria)
-   Carpetas del plan presupuestario (configuración de la planificación presupuestaria)
-   Restricciones de escenario (configuración de la planificación presupuestaria)
-   Plantillas para reglas y plantillas de la etapa de planificación presupuestaria (proceso de planificación presupuestaria)
-   Campos de matriz de las plantillas de hoja de cálculo
-   Asistente para plantilla de plan presupuestario de Microsoft Excel

Algunos conceptos nuevos no se pueden actualizar directamente desde la funcionalidad anterior. Por lo tanto, debe ejecutar operaciones de reconfiguración para estos conceptos nuevos. Las secciones siguientes describen los conceptos que han sustituido a los elementos de la lista anterior.

### <a name="columns"></a>Columnas

Las columnas son un nuevo concepto que reemplazan a partes de la plantilla de Excel y también a campos de matriz. Las columnas pueden representar un período, un mes, un trimestre, un año o todo el tiempo. La referencia de tiempo es dinámica. Señala a un período o un año relativo en referencia al proceso presupuestario. Por ejemplo, una columna **Enero de año anterior** hace referencia el período fiscal 1 del año -1. Una columna es un elemento específico de un escenario del plan presupuestario, como valores reales o solicitud de presupuesto.

### <a name="layouts"></a>Diseños

Los diseños son un nuevo concepto que reemplaza a la plantilla de Excel. Los diseños contienen las columnas que definen qué datos de valores reales o del presupuesto y qué períodos se deben mostrar. Los diseños también se comparten entre el cliente y el complemento de Excel. Por lo tanto, la experiencia de usuario cuando especifica o ve datos en el cliente de Finance and Operations es mejor que la experiencia de usuario en AX 2012. Para especificar datos en un cliente de Finance, ya no tiene que limitarse a ver un solo escenario y entrar en él en una vista de la transacción. En su lugar, una vista de comparación le permite ver y especificar fácilmente los importes de varios períodos y cuentas al mismo tiempo. Los diseños también pueden definirse de modo que pueda especificar y ver divisas, comentarios y otros datos opcionales. Los diseños también le permiten definir las dimensiones contables y las descripciones de la dimensión que se deben mostrar. Los diseños también integran restricciones de escenario para definir qué columnas de una plantilla se pueden editar y qué columnas deben estar disponibles en Excel. Tras definir un diseño, se genera una plantilla para él. Esta plantilla, a su vez, crea la plantilla de Excel correspondiente. Puede editar la plantilla de Excel para que integre más fórmulas y formato y, a continuación puede cargarla de nuevo. Los diseños se asignan a continuación a cada regla de la etapa en la página **Proceso de planificación presupuestaria**. Por lo tanto, los diseños substituyen a las plantillas, que se asignaban y usaban de la misma manera.

### <a name="budget-planning-processes"></a>Procesos de planificación presupuestaria

Los procesos de planificación presupuestaria son básicamente los mismos que en AX 2012. El cambio más significativo ha sido la sustitución de plantillas por los diseños. Si algunos procesos se completaron previamente en AX 2012, los procesos se actualizan a un estado de en curso para poder realizar los cambios. Debe asignar los diseños que necesitará para cada regla de la etapa para determinar qué escenarios y qué períodos de tiempo aparecen cuando el plan se abre en el cliente. Los diseños también determinan qué plantilla de Excel se abre fuera de Dynamic 365 Finance de modo que pueda ver el presupuesto. **Estructura contable predeterminada** es un nuevo campo obligatorio en el proceso de planificación presupuestaria. Para cada proceso de planificación presupuestaria, asigne la estructura contable principal que se debe usar para la gestión presupuestaria.

### <a name="attachments"></a>Archivos adjuntos

En AX 2012, los documentos de la justificación se guardaban en una carpeta de archivos adjuntos. No se actualiza ningún documento de justificación anterior. Ahora los documentos de justificación se almacenan en la base de datos. Si esta información debe guardarse en la versión actualizada, puede cargar los documentos de justificación finales de cada plan como un archivo adjunto usando el botón **Justificación** del panel de acciones. En AX 2012, las hojas de cálculo de Excel de cada plan presupuestario se creaban a partir de la plantilla. En Finance, todos los planes abren una copia del diseño. Sin embargo, no se guardan los cambios en el archivo de Excel. Las fórmulas o la información de soporte que se emplearon por cada plan se deben agregar mediante comentarios, un documento de justificación, o algún otro proceso suplementario.

## <a name="configuring-an-upgraded-environment-from-ax-2012"></a>Configuración de un entorno actualizado desde AX 2012
Para ayudarlo a determinar cómo configurar el sistema actualizado, el siguiente ejemplo usa un proceso presupuestario actualizado a partir de datos de demostración de AX 2012. Se crearon datos de configuración predeterminados para las columnas para ayudar con el proceso de actualización. Puede actualizar o eliminar este datos predeterminados si no cumplen sus requisitos de configuración. **Nota:** Hay nuevos campos obligatorios que no estarán establecidos en el sistema. Si se queda bloqueado en una página, como la página **Configuración de planificación presupuestaria**, y no puede salir de ella, puede cerrar el explorador y después volver a abrirlo en una página diferente para especificar los detalles en el orden correcto. Existen campos obligatorios que todavía no están establecidos. Por lo tanto, se pueden producir problemas hasta que no se haya configurado todo y no se hayan establecido todos los campos obligatorios. Este tema explica cómo establecer estos campos, según convenga. Estos son algunos campos obligatorios:

-   Página **Proceso de planificación presupuestaria**: campo **Estructura contable predeterminada**
-   Página **Proceso de planificación presupuestaria**: campo **Diseño** en la ficha desplegable **Reglas y diseños de fase de planificación presupuestaria**

### <a name="define-columns-and-layouts"></a>Definición de columnas y diseños

1. En la página **Configuración de planificación de presupuesto**, haga clic en la pestaña **Columnas**. Como parte de la actualización, las nuevas columnas se crean automáticamente en función de las líneas del plan del presupuesto. Las columnas ahora usan fechas dinámicas, donde la hora y el año se compensan desde el ejercicio que se define en el proceso de planificación presupuestaria. **Nota:** Por motivos de rendimiento durante la actualización, se presupone que todos los ciclos presupuestarios representan años naturales y no ejercicios. Si utiliza ejercicios, debe hacer ediciones para asignar correctamente las columnas al ejercicio. Por ejemplo, los elementos siguientes existían en AX 2012:
   -   Situaciones del plan presupuestario: reales, línea base, solicitud de presupuesto, presupuesto aprobado
   -   Líneas del plan presupuestario para todas las situaciones en 2017, y valores reales para 2017 y 2016

   Se crearán las columnas siguientes en Finance and Operations:

   | Nombre columna    | Situación del plan presupuestario | Período de tiempo de columna | Contrapartida anual |
   |----------------|----------------------|--------------------|-------------|
   | Escenario enero 1 | Reales              | 1                  | 0           |
   | Escenario enero 2 | Línea base             | 1                  | 0           |
   | Escenario enero 3 | Solicitud de presupuesto       | 1                  | 0           |
   | Escenario enero 4 | Presupuesto aprobado      | 1                  | 0           |
   | Escenario enero 5 | Reales              | 1                  | -1          |
   | Escenario febrero 1 | Reales              | 1                  | 0           |
   | ...            | ...                  | ...                | ...         |

   En este ejemplo, se crea una columna denominada **Escenario enero 1** para los datos de transacción más recientes del plan presupuestario que se encuentran en las transacciones que existen en enero. Una columna similar se crea para cada escenario que tenga datos. Una vez que existan columnas para todos los períodos de ese mismo año, se crean columnas para los años anteriores.
2. Cambie los nombres y descripciones de las columnas, y cualquier otro detalle, manualmente en el cliente o haciendo actualizaciones masivas con el complemento de Excel que selecciona la entidad de datos de las columnas del plan presupuestario. Todos los filtros que anteriormente se establecían para campos de la matriz ahora se establecen dentro de las columnas.
3. Cree un diseño de plan presupuestario nuevo. Un diseño apunta a varias columnas para definir la vista que aparece en Excel y el cliente. El diseño primero requiere que especifique un conjunto de dimensiones contables para determinar qué dimensiones financieras se pueden especificar. Después de especificar el conjunto de dimensiones, haga clic en **Descripciones** para seleccionar las descripciones de dimensiones que se incluirán en el diseño.
4. En la ficha desplegable **Elementos de diseño**, haga clic en **Agregar** para agregar metadatos para cada fila, como una divisa, un comentario, o una clase de presupuesto que determine las filas de ingresos frente a las de gastos. A continuación, agregue columnas para el período de tiempo, además de situaciones adecuadas para esta etapa y ciclo presupuestarios. Puede realizar estos cambios manualmente en el cliente o con el complemento de Excel que selecciona la entidad de los datos de los elementos de diseño del plan presupuestario.
5. Para cada elemento de diseño, seleccione si la columna debe ser editable, y si la columna debe mostrarse también en el libro de Excel para este diseño. **Nota:** Para nuestros planes históricos, puede que desee tener un diseño que muestre 12 columnas mensuales para todas las situaciones del plan presupuestario para dicho proceso.

### <a name="update-budget-planning-processes-to-use-the-appropriate-layout-for-each-budget-stage"></a>Actualice los procesos de planificación presupuestaria para que usen el diseño adecuado para cada etapa del presupuesto

1.  En la página **Proceso de planificación presupuestaria**, seleccione el proceso que quiera configurar.
2.  En el Panel de acciones, haga clic en **Editar**.
3.  Especifique la estructura contable predeterminada del proceso presupuestario. **Estructura contable predeterminada** es un campo obligatorio nuevo que debe establecerse.
4.  En la ficha desplegable **Reglas y diseños de fase de planificación presupuestaria**, en el campo **Diseño**, seleccione un diseño configurado previamente, y que sea adecuado para esta etapa.
5.  Continúe seleccionando el mismo diseño o diseños diferentes para las distintas etapas de planificación presupuestaria y, a continuación, guarde los cambios.

## <a name="additional-features-to-consider-in-your-budgeting-process"></a>Funciones adicionales que debe tener en cuenta en el proceso presupuestario
### <a name="budget-planning-workspace"></a>Espacio de trabajo de planificación presupuestaria

Esta espacio de trabajo se ha diseñado para el propietario del presupuesto y los colaboradores individuales del presupuesto. Tiene vínculos con todos los documentos del presupuesto que requieran su atención. También tiene informes e indicadores de rendimiento clave (KPI) para el proceso presupuestario. El administrador de presupuesto puede definir el proceso de planificación presupuestaria actual para todos los usuarios en la página **Parámetros presupuestarios**. En la pestaña **Configuración de espacio de trabajo**, la ficha desplegable **Planificación presupuestaria** contiene un campo donde podrá seleccionar el proceso de planificación presupuestaria.

### <a name="alternate-layouts"></a>Diseños alternativos

Los diseños alternativos son una nueva función que le permite ver planes en diseños distintos. Uno o más diseños se pueden proporcionar como opciones. Puede ver un plan presupuestario con un diseño mensual o trimestral. Los diseños alternativos se definen en la ficha desplegable **Reglas y diseños de fase de planificación presupuestaria** en la página **Proceso de planificación presupuestaria**.

### <a name="budget-milestones"></a>Hitos del presupuesto

Como parte del proceso presupuestario, es vital que entienda las fechas y los plazos clave. Ahora puede configurar las fechas de modo que tengan descripciones. Los usuarios del presupuesto verán estas descripciones cuando abran los presupuestos para editar o ver algún elemento que tengan asignado.

### <a name="copy-from-budget-plan-allocation"></a>Copia desde una asignación del plan presupuestario

Un nuevo método de asignación le permite distribuir desde un plan principal a un plan secundario sin tener que pasar por un nivel intermedio de la jerarquía. Este método resulta especialmente útil para los clientes que han creado previamente la dimensión financiera solo para la distribución y las aprobaciones de presupuesto.

### <a name="generating-budget-plans-from-new-budget-sources"></a>Generación de planes presupuestarios a partir de nuevos orígenes del presupuesto

Las opciones siguientes se agregaron como procesos periódicos. Estas opciones le permiten generar un plan presupuestario mediante datos existentes de otro módulo como punto de partida:

-   Generar plan presupuestario a partir de previsiones de la demanda
-   Generar plan presupuestario a partir de previsión de suministro
-   Generar plan presupuestario a partir de proyecto
-   Generar plan presupuestario a partir de registro presupuestario

### <a name="more-complete-tracking-of-amounts"></a>Seguimiento de importes más completo

En AX 2012, la planificación presupuestaria tenía un solo importe del plan que se almacenaba para cada valor. En Finance, se ha ampliado el modelo de datos. Ahora hay el importe de la divisa de contabilidad, divisa de transacción, y divisa de notificación para cada valor. Durante la actualización, estas nuevas columnas se rellenan automáticamente para los datos existentes.

### <a name="do-not-convert-currency-in-aggregation"></a>No convertir divisa en la agregación

Normalmente, cuando un plan secundario se agrega a un nivel principal, los importes se convierten automáticamente de la divisa de transacción a la divisa de contabilidad de la organización. Cuando establece la opción **No convertir divisa en la agregación** en **No**, los importes agregados permanecen en la divisa original. Por lo tanto, esta opción permite ajustes más precisos en los que influyen las fluctuaciones del tipo de cambio.

### <a name="looking-back-from-a-budget-plan-to-other-modules-that-contributed-to-the-budget"></a>Consulta desde un plan presupuestario de otros módulos que contribuyeron al presupuesto

Los planes presupuestarios se pueden generar a partir de previsiones de demanda o de suministro, proyectos y otras áreas. La consulta Planes presupuestarios por conjunto de dimensiones incluye varias opciones que le permiten ejecutar consultas para identificar los datos que fueron el origen del plan presupuestario.

### <a name="overwrite-or-append-to-plan-for-allocation-schedules"></a>Sobrescribir o anexar al plan para las programaciones de asignación

Si hay varios orígenes de importes que deben ser distribuidos, puede especificar que los importes se deben añadir. En este caso, los importes no sustituyen los importes existentes. En su lugar, se anexan a los importes existentes.

### <a name="default-financial-dimension-set-for-budget-planning-configuration"></a>Conjunto predeterminado de dimensiones financieras para la configuración de la planificación presupuestaria

La página **Configuración de planificación presupuestaria** ahora incluye un campo donde puede especificar el conjunto de dimensiones financieras predeterminado. Aunque este campo es un campo opcional, es posible que sea necesario para ciertos consultas. Puede que también sea necesario si desea agrupar o filtrar agrupaciones de informes por conjunto de dimensiones.

### <a name="data-entities"></a>Entidades de datos

Se han agregado varias entidades de datos para habilitar una implementación rápida de la planificación presupuestaria. Las entidades también le permiten realizar muchos cambios con Excel. Por lo tanto, no tiene que crear elementos de uno en uno mediante el cliente. A continuación se indica una lista de las nuevas entidades de datos:

-   Nombre de entidad
-   Parámetros presupuestarios
-   Parámetro de plan presupuestario
-   Situaciones del plan presupuestario
-   Etapas de plan presupuestario
-   Etapa del flujo de trabajo de plan presupuestario
-   Programaciones de asignación del plan presupuestario
-   Asignación de etapas del plan presupuestario
-   Prioridades del plan presupuestario
-   Columnas del plan presupuestario
-   Elementos de diseño de plan presupuestario




