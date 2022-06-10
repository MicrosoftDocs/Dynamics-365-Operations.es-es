---
title: Registro de costes indirectos
description: Este tema explica cómo registrar costes indirectos, crear grupos de costes y agregar nodos a la hoja de cálculo de costes para costes indirectos.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CostSheetDesigner, BOMCostGroup, ProjCategory, CostingVersion, CostSheetCalculationFactor
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: d7f4753f69d83d172993e1c9b04be2220fdf253f
ms.sourcegitcommit: 1ea145dc606e243c7f51d91a5c0dd9e385bbda4a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "8804632"
---
# <a name="indirect-cost-posting"></a>Registro de costes indirectos

Los costes indirectos son costes que no están directamente relacionados con ninguna actividad individual en el proceso de producción. Los ejemplos incluyen los costes administrativos, como los salarios de los empleados, los costes del departamento de contabilidad y los costes generales, como el alquiler, los servicios públicos y los costes de maquinaria.

## <a name="calculating-indirect-costs"></a>Cálculo de costes indirectos

Microsoft Dynamics 365 Finance no tiene una forma automatizada de calcular la tasa de costes indirectos. Debe determinar sus costes indirectos, crear códigos de costes indirectos y mantener la tasa para cada coste indirecto en la hoja de cálculo de costes.

El proceso exacto que se utiliza para calcular los costes indirectos puede variar ligeramente de una empresa a otra. Sin embargo, en general, el proceso consta de los siguientes pasos básicos:

1. Cree una lista de costes indirectos a reconocer en la producción. Esta lista puede incluir alquileres, gastos administrativos, honorarios contables y honorarios legales. No debe incluir costes de materias primas ni costes de mano de obra que se reconozcan en las rutas de producción.
2. Sume todos los costes indirectos. Puede agrupar tipos similares de costes indirectos o mantenerlos separados. Cada coste indirecto que se configura puede tener diferentes cuentas principales que se usan para contabilizar en contabilidad general.
3. Compare los costes indirectos con un factor, que también se conoce como la base de absorción. El factor puede ser cualquier cosa que elija. A continuación aparecen algunos ejemplos habituales:

    - Ingresos
    - Cantidad total que se produce
    - Tiempo de preparación
    - Tiempo de ejecución

    Puede seleccionar el período para el que desea calcular sus costes indirectos, como mensual, trimestral o anual. La suma de sus costes indirectos y la suma de su factor deben corresponder a la misma cantidad de tiempo. La siguiente fórmula se utiliza para calcular la tasa de costes indirectos:

    *Tasa de coste indirecto* = *Gastos totales de costes indirectos* &divide; *Factor total*

4. Crear grupos de costes indirectos
5. Configure la hoja de gestión de costes con tus tarifas.
6. Mantenga el coste de sus costes indirectos en la versión de gestión de costes.

> [!NOTE]
> Puede usar el módulo **Contabilidad de costes** para acumular costes y determinar sus gastos generales de diferentes fuentes, como producción, proyectos y contabilidad general. Para obtener más información, consulte [Contabilidad de costes](/cost-accounting/cost-accounting-home-page.md).

> [!IMPORTANT]
> Diferentes establecimientos reguladores han publicado guías sobre los tipos de costes que se pueden incluir como costes indirectos o generales en el coste de sus productos terminados. Antes de comenzar a configurar los costes indirectos, le recomendamos que consulte con su contable y lea las regulaciones locales para asegurarse de cumplir.

## <a name="create-cost-groups-for-indirect-costs"></a>Crear grupos de costes para costes indirectos

Debe crear al menos un grupo de costes para usarlo para los costes indirectos. No hay límite para la cantidad de grupos de costes que puede usar. Considere cómo calcula sus costes y si existen diferentes tarifas para diferentes tipos de costes. Por ejemplo, su organización fabrica productos alimenticios. Algunas materias primas y productos terminados son productos secos y tienen un coste indirecto de almacenamiento. Otras materias primas y productos terminados se refrigeran y tienen un coste indirecto más alto. En este caso, es posible que desee crear dos grupos de costes: **Generales de material seco** y **Generales de material refrigerado**.

Para crear un grupo de costes para costes indirectos, siga estos pasos.

1. Vaya a **Control de producción &gt; Configuración &gt; Rutas &gt; Grupos de rutas**.
2. Seleccione **Nuevo** para crear un grupo.
3. En el campo **Grupo de costes**, introduzca un nombre exclusivo para el grupo de costes, como **MATOVH**.
4. En el campo **Nombre**, introduzca una descripción para el grupo de costes, como **Generales de materiales**.
5. En el campo **Tipo de grupo de costes**, seleccione **Indirecto**.
6. Opcional: En el campo **Comportamiento**, seleccione **Coste fijo** o **Coste variable**.

## <a name="configure-the-costing-sheet-for-indirect-costs"></a>Configurar la hoja de cálculo de costes indirectos

Después de haber creado uno o más grupos de costes, puede configurar su hoja de costes con costes indirectos y definir su cálculo. Es posible que desee agrupar los costes indirectos en la hoja de cálculo de costes. Para agrupar costes indirectos, puede crear un encabezado opcional en la hoja de costes. Debe crear al menos un nodo para cada grupo de costes en la hoja de cálculo de costes. Para cada grupo de costes para costes indirectos, puede agregar uno más cálculos de costes indirectos.

### <a name="indirect-cost-node-types"></a>Tipos de nodos de costes indirectos

Esta sección describe los diferentes tipos de nodos para costes indirectos.

#### <a name="surcharge"></a>Suplemento

**Suplemento** es uno de los tipos más comunes de costes indirectos. Calcula un porcentaje del coste a partir de una base de absorción de costes en el pedido de producción. Defina la base de absorción seleccionando los grupos de costes que están vinculados a sus componentes de tiempo o material en la hoja de cálculo de costes.

Por ejemplo, se puede agregar un suplemento del 3 por ciento al coste de producción de todas las materias primas en un pedido de producción.

#### <a name="rate"></a>Tarifa

Un coste indirecto del tipo **Tasa** se usa para agregar una cantidad fija de coste al pedido de producción a partir de una base de absorción de costes en el pedido de producción. La tasa se puede basar en uno de los tres subtipos:

- **Proceso**: la tasa se basa en el tiempo de ejecución en la ruta.
- **Configuración**: la tasa se basa en el tiempo de configuración en la ruta.
- **Cantidad**: la tasa se basa en la cantidad que se produce.

Defina la base de absorción seleccionando los grupos de costes que están vinculados a los componentes de tiempo o material en la hoja de cálculo de costes.

Por ejemplo, se agrega una cantidad fija de 2,00 dólares estadounidenses (USD) a cada pedido de producción, según el tiempo de ejecución en la ruta para el grupo de costes de mano de obra en su hoja de cálculo de costes.

#### <a name="output-unit-based"></a>Basado en unidad de salida

Un coste indirecto del tipo **Basade en unidad de salida** tipo se calcula multiplicando la cantidad que se especifica en la ficha desplegable **Tasa** por el subtipo seleccionado. Puede seleccionar la cantidad, el peso o el volumen del producto terminado como multiplicador del coste indirecto.

Por ejemplo, use la cantidad para calcular 1,50 USD de depreciación de la máquina por cada cantidad que se produce. Como otro ejemplo, utilice el volumen para calcular 2,00 USD de costes de refrigeración para el volumen de espacio que ocupan los productos terminados en sus unidades de refrigeración.

#### <a name="input-unit-based"></a>Basado en unidad de entrada

Un coste indirecto del tipo **Basaado en unidad de entrada** se calcula multiplicando la cantidad de materias primas que se consumen en un pedido de producción por una cantidad. Puede usar el peso o el volumen de las entradas en el pedido de producción para calcular el total. Puede limitar el cálculo a un subconjunto de materiales seleccionando uno o más grupos de costes en la ficha desplegable **Base de absorción** de la hoja de costes.

Por ejemplo, utilice el volumen de entradas para un grupo de costes específico que está vinculado a productos refrigerados para agregar 1,00 USD al pedido de producción.

### <a name="create-a-total-node-for-indirect-costs-in-the-costing-sheet"></a>Crear un nodo total para costes indirectos en la hoja de cálculo de costes

Para crear un nodo total para costes indirectos en la hoja de cálculo de costes, siga estos pasos.

1. Vaya a **Gestión de costes &gt; Configuración de políticas de contabilidad de costes indirectos &gt; Hoja de gestión de costes**.
2. En el árbol, seleccione un nodo que represente el coste de los bienes que se han fabricado.
3. Seleccione **Nuevo** para crear un nodo.
4. En el campo **Seleccionar tipo de nodo**, seleccione **Total**.
5. En el campo **Código**, introduzca un id. único para el nodo, como **Gastos generales de producción**.
6. Seleccione la casilla **Encabezado**.
7. Seleccione la casilla **Total**.
8. Seleccione **Aceptar**.

### <a name="create-an-indirect-cost-group-node-in-the-costing-sheet"></a>Crear un nodo de grupo de costes indirectos en la hoja de cálculo de costes

Para crear un nodo de grupo de costes indirectos en la hoja de cálculo de costes, siga estos pasos.

1. Vaya a **Gestión de costes &gt; Configuración de políticas de contabilidad de costes indirectos &gt; Hoja de gestión de costes**.
2. En el árbol, seleccione el nodo en el que desea crear el coste indirecto. Por ejemplo, seleccione el nodo total para **Gastos generales de producción**.
3. Seleccione **Nuevo** para crear un nodo.
4. En el campo **Seleccionar tipo de nodo**, seleccione **Grupo de coste**.
5. En el campo **Código**, introduzca un id. único para el nodo, como **TRANSP**.
6. En el campo **Descripción**, especifique una breve descripción, como **Generales de transporte**.
7. Seleccione **Aceptar**.
8. En el campo **Grupo de costes**, seleccione el grupo de costes, como **OVH1: gastos generales de transporte**.

### <a name="create-a-surcharge-indirect-cost"></a>Crear un coste indirecto de suplemento

Para crear un coste indirecto de suplemento en la hoja de cálculo de costes, siga estos pasos.

1. Vaya a **Gestión de costes &gt; Configuración de políticas de contabilidad de costes indirectos &gt; Hoja de gestión de costes**.
2. En el árbol, seleccione el grupo de costes indirectos en el que desea crear el coste indirecto. Por ejemplo, seleccione el nodo total para **TRANSP: gastos generales de transporte**.
3. Seleccione **Nuevo** para crear un nodo.
4. En el campo **Seleccionar tipo de nodo**, seleccione **Suplemento**.
5. En el campo **Código**, introduzca un id. único para el nodo, como **Gastos generales de transporte**.
6. Seleccione **Aceptar**.
7. En el campo **Subtipo**, seleccione **Total**.
8. En la ficha desplegable **Base de absorción**, seleccione **Nuevo** para crear un código de coste.
9. En el campo **Código**, seleccione un grupo de costes para usarlo para calcular el suplemento.
10. Opcional: repita los pasos 8 a 9 para cada grupo de costes adicional que desee usar para el cálculo.
11. En la ficha desplegable **Suplemento**, seleccione **Nuevo** para crear una tasa.
12. En el campo **Versión** seleccione la versión de gestión de costes a la que añadir el suplemento.
13. Opcional: en el campo **Sitio**, introduzca un sitio para aplicar el suplemento.
14. En el campo **Porcentaje**, introduzca el porcentaje a calcular en los pedidos de producción de los grupos de costes que se definen en la ficha desplegable **Base de absorción**.
15. En la ficha desplegable **Registros de libros de contabilidad**, seleccione la cuenta principal que se usará para los campos **Coste estimado de costes indirectos consumidos, trabajo en curso**, **Coste estimado de costes indirectos consumidos, trabajo en curso**, **Coste indirecto absorbido** y **Coste de coste indirecto consumido, trabajo en curso**.
16. Opcional: en la ficha desplegable **Dimensiones financieras**, especifique cualquier dimensión financiera para introducir de forma predeterminada en las transacciones cuando se registran en contabilidad general.

El procedimiento anterior muestra cómo crear un coste indirecto del tipo **Suplemento**. Se utilizan pasos similares para crear otros tipos de costes indirectos. Las siguientes secciones describen las diferencias para cada tipo.

#### <a name="rate"></a>Tarifa

- En el paso 4, seleccione **Tasa** en vez de **Suplemento**.
- En el paso 7, seleccione **Proceso**, **Configuración** o **Cantidad**, en lugar de **Total**.
- En el paso 11, utilice la ficha desplegable **Tasa** en lugar de la ficha desplegable **Suplemento**.
- En el paso 14, introduzca una cantidad en el campo **Importe** en lugar de un porcentaje en el campo **Porcentaje**.

#### <a name="output-unit-based"></a>Basado en unidad de salida

- En el paso 4, seleccione **Basado en unidad de salida** en vez de **Suplemento**.
- En el paso 7, seleccione **Cantidad**, **Peso** o **Volumen**, en lugar de **Total**.
- Omita los pasos del 8 al 10.
- En el paso 11, utilice la ficha desplegable **Tasa** en lugar de la ficha desplegable **Suplemento**.

#### <a name="input-unit-based"></a>Basado en unidad de entrada

- En el paso 4, seleccione **Basado en unidad de entrada** en vez de **Suplemento**.
- En el paso 7, seleccione **Peso** o **Volumen**, en lugar de **Total**.
- En el paso 11, utilice la ficha desplegable **Tasa** en lugar de la ficha desplegable **Suplemento**.
