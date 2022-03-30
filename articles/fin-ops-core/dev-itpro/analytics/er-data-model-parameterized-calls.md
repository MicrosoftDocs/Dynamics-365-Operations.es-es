---
title: Admite llamadas parametrizadas de modelos de datos ER
description: Este tema explica cómo implementar llamadas parametrizadas de modelos de datos de informes electrónicos (ER).
author: NickSelin
ms.date: 03/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula, ERDataModelDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 968b0769607e9fdbed57c25b727ed44988a92913
ms.sourcegitcommit: 399d0d3f8e2ebb81b6b9d640365ebe182690bab2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "8419476"
---
# <a name="support-parameterized-calls-of-er-data-models"></a>Admite llamadas parametrizadas de modelos de datos ER

[!include [banner](../includes/banner.md)]

Para generar documentos comerciales, configure una solución de [Informes electrónicos (ER)](general-electronic-reporting.md) que contiene los siguientes componentes ER:

- **[Formato](er-overview-components.md#format-component)** – Este componente especifica la estructura de un documento comercial.
- **Asignación de formato** – Este componente controla cómo se completa un documento comercial en tiempo de ejecución.
- **[Asignación de modelos](er-overview-components.md#model-mapping-component)** – Este componente especifica qué extraen los datos de la aplicación en una asignación de formato.
- **[Modelo de datos](er-overview-components.md#data-model-component)** – Este componente pasa información entre componentes individuales.

Cuando ejecuta un formato ER, se ejecuta cada elemento de formato, comenzando desde el elemento de formato raíz. Cada vez que un elemento de formato que se ejecuta contiene un enlace a un [origen de datos](general-electronic-reporting.md#configuring-data-model-mappings-for-outgoing-documents), el origen de datos se ejecuta para entregar los datos esperados y usarlos para completar el elemento de formato. Cuando una fuente de datos del tipo *Modelo*, se llama a la asignación de modelo adecuada para extraer datos de la aplicación, en función de la configuración de asignación de modelo.

Anteriormente, estas llamadas de asignación de modelos no se podían parametrizar para que dependieran de la lógica del formato que se ejecuta. Solo se admitía el siguiente flujo de datos.

<table>
<tbody>
<tr align="center">
<td>
<b>Formato</b><br>
Formato&nbsp;elemento<br>
&nbsp;
</td>
<td>
<i>Enlace</i><br>
&gt;&nbsp;solicitud&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;&lt;
</td>
<td><b>Asignación&nbsp;formato</b><br>
Origen de datos<br>
&nbsp;
</td>
<td>
<i>Modelo&nbsp;datos</i><br>
&gt;&nbsp;solicitud&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;&lt;
</td>
<td>
<b>Asignación&nbsp;modelos</b><br>
Origen&nbsp;de datos<br>
&nbsp;
</td>
<td>
<i>Enlace</i><br>
&gt;&nbsp;solicitud&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;&lt;
</td>
<td>
<b>Tabla</b><br>
Grabar<br>
Campo
</td>
</tr>
</tbody>
</table>

Sin embargo, en la versión 10.0.15 y posteriores, puede configurar campos de modelo de datos a los que solo se puede llamar cuando se proporcionan los valores de los parámetros configurados. Cuando un campo de este tipo se configura y llama desde un componente de formato, los parámetros necesarios deben proporcionarse en un enlace de formato como argumentos de la llamada. En estos casos, los valores de los argumentos se pueden especificar en función de los valores específicos del formato. Por lo tanto, puede utilizar **parametrización dinámica del tiempo de ejecución** para llamadas de modelo de datos para admitir el siguiente flujo de datos.

<table>
<tbody>
<tr align="center">
<td>
<b>Formato</b><br>
Elemento&nbsp;formato&nbsp;1<br>
<br>
Elemento&nbsp;formato&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Enlace</i><br>
&gt;&nbsp;solicitud&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;solicitud&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Asignación&nbsp;formato</b><br>
Origen&nbsp;de datos&nbsp;1<br>
&nbsp;<br>
<b>value2=Func(value1)</b><br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Modelo&nbsp;datos</i><br>
&gt;&nbsp;campo1&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;1&nbsp;&lt;<br>
<b>&gt;&nbsp;campo2(valor2)&nbsp;&gt;</b><br>
&lt;&nbsp;valor&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Asignación&nbsp;modelos</b><br>
Origen&nbsp;de datos&nbsp;1<br>
<br>
Origen&nbsp;de datos&nbsp;2<br>
&nbsp;<br>
&nbsp;
</td>
<td>
<i>Enlace</i><br>
&gt;&nbsp;solicitud&nbsp;1&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;1&nbsp;&lt;<br>
&gt;&nbsp;solicitud&nbsp;2&nbsp;&gt;<br>
&lt;&nbsp;valor&nbsp;3&nbsp;&lt;<br>
&nbsp;
</td>
<td>
<b>Tabla&nbsp;1</b><br>
Registro&nbsp;1<br>
Campo&nbsp;1<br>
<b>Tabla&nbsp;2</b><br>
Registro&nbsp;2<br>
Campo&nbsp;2
</td>
</tr>
</tbody>
</table>

La nueva funcionalidad permite parametrizar la llamada a cualquier campo del modelo de datos del tipo [*Registro*](er-formula-supported-data-types-composite.md#record) o [*Lista de registros*](er-formula-supported-data-types-composite.md#record-list). Los siguientes tipos de datos son compatibles con los parámetros de un campo de modelo de datos:

- [Booleano](er-formula-supported-data-types-primitive.md#boolean)
- [Contenedor](er-formula-supported-data-types-composite.md#container)
- [Fecha](er-formula-supported-data-types-primitive.md#date)
- [Fecha y hora](er-formula-supported-data-types-primitive.md#datetime)
- [GUID](er-formula-supported-data-types-primitive.md#guid)
- [Int64](er-formula-supported-data-types-primitive.md#int64)
- [Entero](er-formula-supported-data-types-primitive.md#integer)
- [Real](er-formula-supported-data-types-primitive.md#real)
- [Cadena](er-formula-supported-data-types-primitive.md#string)

Puede especificar cada parámetro de un campo de modelo de datos para el cual el argumento se puede proporcionar como un valor único del tipo de datos definido y la [*lista*](er-formula-supported-data-types-composite.md#record-list) de tales valores.

> [!NOTE]
> No se admite el valor predeterminado para el parámetro de un campo de modelo de datos. Si agrega un parámetro a un campo en un modelo de datos y la versión de ese modelo de datos ya se lanzó y publicó, debe [volver a basar](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) todas las asignaciones y formatos de modelo correspondientes a la nueva versión de este modelo, porque este cambio de modelo de datos no es compatible con versiones anteriores.

Puede configurar campos de modelos de datos parametrizados para hacer que las llamadas de mapeo de modelos sean específicas del formato. Este enfoque puede ayudarlo a reducir la cantidad de asignaciones de modelos que deben configurarse para muchos formatos de un solo modelo de datos. También puede utilizar este enfoque para mejorar el rendimiento de ejecución de sus formatos y reducir el tiempo necesario para generar documentos comerciales. Para obtener más información acerca de esta característica, complete el ejemplo de este tema.

## <a name="example-use-parameterized-calls-of-er-data-models"></a>Ejemplo: Use llamadas parametrizadas de modelos de datos ER

Los siguientes pasos explican cómo un usuario en el rol de administrador del sistema o desarrollador de informes electrónicos puede diseñar una solución de ER que contenga un modelo de datos, una asignación de modelo y un componente de ER de formato que están configurados para llamar a una asignación de modelo desde un formato proporcionando un argumento para la llamada, cuyo valor se ha calculado en tiempo de ejecución utilizando la fórmula del formato en ejecución. 

Estos pasos se pueden llevar a cabo en la empresa **DEMF**. No se requieren modificaciones de código. 

En este ejemplo, creará las [configuraciones](general-electronic-reporting.md#Configuration) de ER necesarias para la empresa de ejemplo, **Litware, Inc**. Asegúrese de que está disponible el proveedor de la configuración para la empresa de ejemplo **Litware, Inc.** (`http://www.litware.com`) está en la lista del marco de ER y que está como **Activo**. Si este proveedor de configuración no aparece en la lista o si no está marcado como **Activo**, siga los pasos de [Crear un proveedor de configuración y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="business-scenario"></a>Escenario empresarial

Tiene una solución de ER que incluye un formato que puede ejecutar para generar un documento electrónico con fines de auditoría. Este formato contiene transacciones de impuestos que están relacionadas con órdenes de venta y órdenes de compra, y que tienen los detalles requeridos, como la fecha de la transacción y el valor fiscal. A partir del nuevo ejercicio, la estructura de este documento ha cambiado. Ahora debe enviar un documento ampliado que incluya detalles adicionales (nombres) de todas las partes (clientes y proveedores) cuyas transacciones se presentan en los informes generados. Por lo tanto, debe modificar su solución ER para que genere documentos que cumplan con este nuevo requisito.

### <a name="configure-the-er-framework"></a>Configurar el marco ER

Siga los pasos de [Configurar el marco de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar el conjunto mínimo de parámetros de ER. Debe completar esta configuración antes de comenzar a utilizar el marco ER para diseñar una solución nueva de ER.

### <a name="design-a-domain-specific-data-model"></a>Diseñar un modelo de datos específico del dominio

Debe crear una nueva configuración de ER que contenga el componente de modelo de datos requerido. Este modelo de datos se utilizará más tarde como origen de datos al diseñar un formato de ER para generar un informe de auditoría.

Siga estos pasos para importar el modelo de datos necesario desde un archivo XML proporcionado por Microsoft.

1. Descargue el archivo [Sample audit model.version.1.xml](https://download.microsoft.com/download/7/1/9/719b0132-fed7-4c73-8afa-90cac29c2fee/Sample-audit-model.version.1.xml) y guárdelo en su equipo local.
2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. En el espacio de trabajo **Informes electrónico**, seleccione **Configuraciones de informes**.
4. En la página **Configuraciones**, en el panel de acciones, seleccione **Exchange** \> **Cargar desde archivo XML**.
5. Seleccione **Examinar** y, a continuación, busque y seleccione el archivo **Sample audit model.version.1.xml**.
6. Seleccione **Aceptar** para importar la configuración.

    ![Configuración del modelo de datos importado de ER en la página Configuraciones.](./media/er-data-model-parameterized-calls-imported-model.png)

La siguiente ilustración muestra la versión del modelo de datos configurado en la página **Diseñador de modelo de datos**.

![Estructura del modelo de datos de ER en la página Diseñador de modelos de datos.](./media/er-data-model-parameterized-calls-model1.png)

Actualmente, el modelo está diseñado para exponer solo las transacciones fiscales que tienen los detalles requeridos.

### <a name="design-a-model-mapping-for-the-configured-data-model"></a>Diseñar una asignación de modelo para el modelo de datos configurado

Como usuario con el rol de Desarrollador de informes electrónicos, debe crear una nueva configuración de ER que contenga un componente de asignación de modelo para el modelo de datos Sample audit. Este componente implementa el modelo de datos configurado para Microsoft Dynamics 365 Finance, es específico para esa aplicación. Debe configurar el componente de asignación del modelo para especificar los objetos de la aplicación que hay que usar para completar el modelo de datos configurado con los datos de la aplicación en tiempo de ejecución. Para completar esta tarea, debe entender cómo la estructura de datos del dominio empresarial fiscal se implementa en Finance.

Siga estos pasos para importar el modelo de asignación necesario desde un archivo XML proporcionado por Microsoft.

1. Descargue el archivo [Sample audit model mapping.version.1.1.xml](https://download.microsoft.com/download/c/0/3/c03a4673-b1b1-4ef8-96d0-bf96518be6e0/Sample-audit-model-mapping.version.1.1.xml) y guárdelo en su equipo local.
2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. En el espacio de trabajo **Informes electrónico**, seleccione **Configuraciones de informes**.
4. En la página **Configuraciones**, en el panel de acciones, seleccione **Exchange** \> **Cargar desde archivo XML**.
5. Seleccione **Examinar** y, a continuación, busque y seleccione el archivo **Sample audit model mapping.version.1.1.xml**.
6. Seleccione **Aceptar** para importar la configuración.

    ![Configuración del modelo de asignación importado de ER en la página Configuraciones.](./media/er-data-model-parameterized-calls-imported-mapping.png)

La siguiente ilustración muestra la versión editable de la asignación del modelo configurado en la página **Diseñador de asignación de modelo**.

![Estructura del modelo de asignación de ER en la página Diseñador de modelos de asignación.](./media/er-data-model-parameterized-calls-mapping1.png)

Actualmente, la asignación modelo está diseñada para exponer solo las transacciones fiscales que tienen los detalles requeridos. Obtiene esta información de la tabla de aplicación `TaxTrans` usando los orígenes de datos ER configurados `TaxTrans` y`TaxTransFiltered`.

### <a name="design-a-new-format"></a>Diseñar un formato nuevo

Como usuario con el rol de Consultor funcional de informes electrónicos, debe crear una nueva configuración de ER que contenga un componente de formato. Debe configurar el componente de formato para completar los informes generados con transacciones fiscales que tengan todos los detalles requeridos.

Siga estos pasos para importar el formato necesario desde un archivo XML proporcionado por Microsoft.

1. Descargue el archivo [Sample audit format.version.1.1.xml](https://download.microsoft.com/download/e/b/7/eb7e126e-2bb3-4bbb-a735-ffd4c48920b1/Sample-audit-format.version.1.1.xml) y guárdelo en su equipo local.
2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. En el espacio de trabajo **Informes electrónico**, seleccione **Configuraciones de informes**.
4. En la página **Configuraciones**, en el panel de acciones, seleccione **Exchange** \> **Cargar desde archivo XML**.
5. Seleccione **Examinar** y, a continuación, busque y seleccione el archivo **Sample audit format.version.1.1.xml**.
6. Seleccione **Aceptar** para importar la configuración.

    ![Configuración del formato importado de ER en la página Configuraciones.](./media/er-data-model-parameterized-calls-imported-format.png)

La siguiente ilustración muestra la versión editable del formato configurado en la página **Diseñador de formato**.

![Estructura del formato ER en la página Diseñador de formato.](./media/er-data-model-parameterized-calls-format1.png)

El formato ER está configurado para generar un informe como un archivo de texto en formato de valores separados por comas (CSV).

### <a name="run-the-imported-format"></a>Ejecutar el formato importado

1. En la página **Configuraciones**, seleccione la configuración **Ejemplo de formato de auditoría** y, a continuación, en el panel de acciones, seleccione **Ejecutar**.
2. En el cuadro de diálogo **Parámetros del informe electrónico**, en la pestaña **Registros a incluir**, seleccione **Filtrar**.
3. Especifique las condiciones para seleccionar las transacciones de impuestos de los vales **PIV-110000004** y **INV-10000001**.
4. Seleccione **Aceptar**.
5. Seleccione **Aceptar**.
6. Revisar el documento generado que contiene las transacciones fiscales de los comprobantes seleccionados.

    ![Vista previa del documento generado con las transacciones fiscales.](./media/er-data-model-parameterized-calls-output1.png)

### <a name="adjust-the-imported-er-solution"></a>Ajustar la solución de ER importada

De acuerdo con el nuevo requisito, el documento que debe presentar debe contener los nombres de los clientes y proveedores cuyas transacciones se incluyen. Por lo tanto, debe modificar la solución ER importada para que genere un documento que cumpla con este nuevo requisito.

Decida cómo desea implementar las modificaciones necesarias de los componentes de ER importados.

El enfoque obvio es implementar las siguientes modificaciones:

- En su modelo de datos, agregue el nuevo campo del modelo de datos `Transaction.Party.Name` del tipo *Cadena*.
- En la asignación de su modelo, configure el enlace para el nuevo campo del modelo de datos utilizando las relaciones de tabla disponibles para acceder al registro relevante de la tabla de aplicaciones `DirPartyTable` y obtener el valor de campo `Name` de ella.

Aunque este enfoque funcionará, podría causar problemas de rendimiento en la base de datos SQL, porque `TaxTrans` es la tabla de transacciones y, por lo tanto, puede contener un gran volumen de registros. En este caso, el número de llamadas a `DirPartyTable` debe ser igual al número de registros en la tabla `TaxTrans` que puede causar problemas de rendimiento.

Alternativamente, puede implementar las siguientes modificaciones:

- En su modelo de datos, agregue la nueva raíz `Party` y el nuevo campo `Party.Name`.
- En la asignación de su modelo, agregue una nueva fuente de datos que unirá todos los registros de las tablas que se usan en las relaciones de tablas para acceder al registro relevante de la tabla `DirPartyTable` de la aplicación, a partir de la tabla `TaxTrans`.

Aunque este enfoque funcionará, podría causar algunos problemas de consumo de memoria. Incluso cuando un origen de datos [JOIN](er-join-data-sources.md) nuevo se ejecuta como una única solicitud SQL a la base de datos de la aplicación para evitar problemas de rendimiento de la base de datos, el resultado debe recuperarse en la memoria del servidor de la aplicación. Debido a que la cantidad de registros y la cantidad de campos en esos registros será bastante grande, este enfoque podría causar un consumo de memoria muy alto. Incluso podría lanzarse una excepción de tiempo de ejecución por falta de memoria.

Puede implementar las modificaciones cuando un formato en ejecución recopila, en la memoria, los códigos de identificación únicos de clientes y proveedores para todas las transacciones de impuestos que se presentarán en un informe generado. Debido a que solo se deben conservar los códigos únicos, el conjunto final de códigos no será lo suficientemente grande como para afectar el consumo de memoria. Luego, el conjunto de códigos se pasará a la asignación del modelo como el argumento de otra llamada de la fuente de datos del tipo *Modelo*. En función de esa llamada, la asignación del modelo ejecutará una nueva fuente de datos de ER que realiza una única solicitud de SQL a la base de datos de la aplicación para obtener, desde la tabla `DirPartyTable`, registros solo para aquellas partes cuyos códigos se presentan en el conjunto de códigos proporcionado.

### <a name="adjust-the-imported-data-model"></a>Ajustar el modelo de datos importado

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, seleccione **Modelo de auditoría de muestra**.
3. En la ficha desplegable **Versiones**, seleccione la versión **2** que tiene un estado de **[Borrador](general-electronic-reporting.md#component-versioning)**.
4. Seleccione la ficha desplegable **Componentes de la configuración**.
5. Seleccione **Diseñador** para abrir el modelo de datos para editar.
6. En la página **Modelo de datos**, asegúrese de que el campo `Root` se selecciona el campo y, a continuación, seleccione **Nuevo**.
7. En el cuadro de diálogo desplegable, siga estos pasos:

    1. En el grupo del campo **Nuevo nodo como**, seleccione la opción **Elemento secundario de un nodo activo**.
    2. En el campo **Nombre**, especifique **Parte**.
    3. En el campo **Tipo de artículo**, seleccione **Lista de registros**.
    4. Seleccione **Agregar** para terminar de agregar el nuevo campo.

8. Asegúrese de que el campo `Root.Party` esté seleccionado y después, en la pestaña **Nodo**, seleccione **Parámetros**.
9. En el cuadro de diálogo **Parámetros**, siga estos pasos:

    1. En la ficha **Parámetros**, seleccione **Nuevo**.
    2. En el campo **Nombre**, especifique **PartyRefRecId**.
    3. En el campo **Tipo**, seleccione **Int64**.
    4. Seleccione la casilla **Lista**.
    5. Seleccione **Aceptar** para terminar de introducir los parámetros.

    > [!NOTE]
    > Acaba de configurar el campo `Root.Party` del modelo de datos como un campo que se llama cuando se proporciona un valor en el parámetro **PartyRefRecId**. Este valor debe estar presente en la lista de registros que contienen un campo `Value` del tipo de datos *Int64*.

    ![Parámetros del cuadro de diálogo.](./media/er-data-model-parameterized-calls-model2a.png)

10. Asegúrese de que el campo `Root.Party` siga seleccionado y después seleccione **Nuevo**.
11. En el cuadro de diálogo desplegable, siga estos pasos:

    1. En el grupo del campo **Nuevo nodo como**, seleccione la opción **Elemento secundario de un nodo activo**.
    2. En el campo **Nombre**, escriba **Nombre**.
    3. En el campo **Tipo de artículo**, seleccione **Cadena**.
    4. Seleccione **Agregar** para terminar de agregar el nuevo campo.

12. Seleccione **Guardar** y, a continuación, cierre la página **Modelo de datos**.

    ![Estructura del modelo de datos de ER ajustado en la página Diseñador de modelos de datos.](./media/er-data-model-parameterized-calls-model2b.png)

13. En la ficha desplegable **Versiones**, para la versión **2** seleccione **Cambiar Estado** \> **Completar**. A continuación seleccione **Aceptar**.

    > [!NOTE]
    > Sus cambios en el modelo de datos se almacenan en la segunda revisión del **Ejemplo de modelo de auditoría** componente del modelo de datos que se encuentra en la segunda versión del **Ejemplo de modelo de auditoría** configuración de ER.

![Configuración del modelo de datos actualizado de ER en la página Configuraciones.](./media/er-data-model-parameterized-calls-updated-model.png)

### <a name="adjust-the-imported-model-mapping"></a>Ajuste la asignación de modelo importada

1. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de auditoría de muestra**.
2. Seleccione **Asignación del modelo de auditoría de muestra**, y luego, en la ficha desplegable **Versiones**, seleccione la segunda versión de asignación que se basa en la primera versión del modelo de datos (versión **1.2**), y que tiene un estatus de **Borrador**.
3. Seleccione **Cambiar de basee**.
4. En el campo **Versión de destino**, deje la versión **2** del modelo base **Ejemplo de modelo de auditoría**.
5. Seleccione **Aceptar** para reorganizar y alinear la asignación de su modelo con los cambios recientes en el modelo de datos.

    Observe que el número de versión de su mapeo de modelo editable ha cambiado de **1.2** para **2.2** para indicar que actualmente se utiliza como base la segunda versión del modelo.

6. Seleccione **Diseñador**.
7. En la página **Asignación de modelo a origen de datos**, seleccione **Diseñador** para el modelo de asignación actual.
8. Siga estos pasos para agregar una nueva fuente de datos para acceder a la tabla `DirPartyTable` de la aplicación:

    1. En el panel **Tipo de origen de datos**, seleccione **Dynamics 365 for Operations \> Registros de tabla**.
    2. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
    3. En el campo **Nombre**, especifique **PartyTable**.
    4. En el campo **Tabla**, escriba **DirPartyTable**.
    5. Seleccione **Aceptar** para terminar de agregar el nuevo origen de datos de contenedor.

9. Siga estos pasos para agregar una nueva fuente de datos para solicitar registros de `DirPartyTable`, según la lista provista de códigos de identificación de registros:

    1. En el panel **Tipo de origen de datos**, seleccione **General \> Vaciar contenedor**.
    2. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
    3. En el campo **Nombre**, escriba **Datos**.
    4. Seleccione **Aceptar** para terminar de agregar el nuevo origen de datos de contenedor.
    5. En el panel **Fuentes de datos**, seleccione la fuente de datos **Datos**.
    6. En el panel **Tipo de origen de datos**, seleccione **Funciones \> Campo calculado**.
    7. En el panel **Origen de datos**, seleccione **Agregar**.
    8. En el campo **Nombre**, especifique **DirParty**.
    9. Seleccione **Editar fórmula**.
    10. En la página **Diseñador de fórmulas** seleccione **Parámetros**.
    11. En el cuadro de diálogo **Parámetros**, siga estos pasos:

        1. En la ficha **Parámetros**, seleccione **Nuevo**.
        2. En el campo **Nombre**, especifique **DirPartyId**.
        3. En el campo **Tipo**, seleccione **Int64**.
        4. Seleccione la casilla **Lista**.
        5. Seleccione **Aceptar**.

        > [!NOTE]
        > Acaba de configurar este campo calculado para que acepte, en tiempo de ejecución, el argumento de un solo parámetro que está configurado como una lista de registros que tiene un solo campo `Value` del tipo *Int64*.

    12. En el campo **Fórmula**, introduzca la expresión siguiente:

        `FILTER(PartyTable, VALUEINLARGE(PartyTable.RecId, DirPartyId, DirPartyId.Value))`

        > [!NOTE]
        > Acaba de configurar el campo calculado `DirParty` para recuperar solamente registros `DirPartyTable` donde los códigos de identificación del registro están incluidos en la lista `DirPartyId` que se proporciona como argumento cuando se llama el campo `DirParty`.

        ![Fórmula para obtener los nombres de las partes de la tabla de aplicaciones en la página del diseñador de fórmulas.](./media/er-data-model-parameterized-calls-formula1.png)

    13. Seleccione **Guardar** y cierre la página **Diseñador de fórmula**.
    14. Seleccione **Guardar** y luego seleccione **Aceptar** para terminar de agregar la nueva fuente de datos.

10. Siga estos pasos para vincular la nueva fuente de datos al nuevo campo del modelo de datos, de modo que el modelo de datos se utilice para exponer los nombres de las partes:

    1. En el panel **Modelo de datos**, seleccione el campo `Root.Party` del modelo de datos.
    2. En el panel **Modelo de datos**, seleccione **Editar**.
    3. En la página **Diseñador de fórmulas**, en el campo **Fórmula**, introduzca la expresión `Data.DirParty(PartyRefRecId)`.
    4. Seleccione **Guardar** y cierre la página **Diseñador de fórmula**.

        > [!NOTE]
        > Acaba de configurar el enlace para llamar al origen de datos `Data.DirParty` configurado y proporcionar la lista de códigos de identificación de registros que se especificarán en el formato cuando se llama al campo `Root.Party` del modelo de datos.

    5. En el panel **Modelo de datos**, seleccione el campo `Root.Party.Name` del modelo de datos.
    6. En el panel **Modelo de datos**, seleccione **Editar**.
    7. En la página **Diseñador de fórmulas**, en el panel **Origen de datos**, expanda **Datos \> DirParty** y seleccione **Nombre**.
    8. Seleccione **Agregar origen de datos**.
    9. Seleccione **Guardar** y cierre la página **Diseñador de fórmula**.

    ![Estructura del modelo de asignación de ER ajustado en la página Diseñador de modelos de asignación.](./media/er-data-model-parameterized-calls-mapping2.png)

11. Seleccione **Guardar** y cierre la página **Diseñador de asignación de modelo**.
12. Cierre la página **Asignación de modelo a origen de datos**.
13. En la ficha desplegable **Versiones**, para la versión **2.2** seleccione **Cambiar Estado \> Completar**. A continuación seleccione **Aceptar**.

### <a name="adjust-the-imported-format"></a>Ajustar el formato importado

1. En la página **Configuraciones**, seleccione **Formato de auditoría de muestra**.
2. En la ficha desplegable **Versiones**, seleccione la versión **1.2** que tiene un estado de **Borrador**.
3. Seleccione **Cambiar de basee**.
4. En el campo **Versión de destino**, deje la versión **2** del modelo base **Ejemplo de modelo de auditoría**.
5. Seleccione **Aceptar** para reorganizar y alinear su formato con los cambios recientes del modelo de datos.
6. Seleccione **Diseñador**.
7. En la página **Diseñador de formatos**, en el árbol de estructura de formato del panel izquierdo, seleccione **Expandir/Contraer**.
8. Siga estos pasos para agregar un nuevo elemento de formato para recopilar códigos de identificación de registro de las partes cuyas transacciones se presentan en los informes generados.

    1. En el árbol de estructura de formato, seleccione el elemento de secuencia **Report.Row.Trans**.
    2. Seleccione **Agregar**.
    3. En el cuadro de diálogo **Agregar**, seleccione **Origen de datos \> Artículo**.
    4. En el cuadro de diálogo **Propiedades de componente**, en el campo **Nombre**, escriba **Id**.
    5. En el campo **Tipo de datos**, seleccione **Int64**.
    6. Seleccione **Aceptar**.

    > [!NOTE]
    > Un elemento **Fuente de datos \> Artículo** se puede utilizar para realizar cálculos internos y transformaciones de datos solo en el ámbito del formato en ejecución. Por lo tanto, al agregar este elemento de formato, no cambia el contenido de un documento generado.

9. Siga estos pasos para agregar nuevos elementos de formato para ingresar los nombres de las partes en los informes generados:

    1. Selecciona el elemento de secuencia **Report.Row**.
    2. Seleccione **Agregar**.
    3. En el cuadro de diálogo **Agregar**, seleccione **Texto \> Secuencia**.
    4. En el cuadro de diálogo **Propiedades de componente**, en el campo **Nombre**, escriba **Parte**.
    5. Seleccione **Aceptar**.
    6. Selecciona el elemento de secuencia **Report.Row.Party**.
    7. Seleccione **Agregar**.
    8. En el cuadro de diálogo **Agregar**, seleccione **Texto \> Cadena**.
    9. En el cuadro de diálogo **Propiedades de componente**, en el campo **Nombre**, escriba **Nombre**.
    10. Seleccione **Aceptar**.

10. Siga estos pasos para agregar un nuevo origen de datos para recopilar códigos de identificación de registro de las partes cuyas transacciones se presentan en los informes generados:

    1. En la pestaña **Asignación**, seleccione **Agregar raíz**.
    2. En el cuadro de diálogo **Agregar origen de datos**, seleccione **Funciones \> Recopilación de datos**.
    3. En el cuadro de diálogo **Propiedades del origen de datos 'Recopilación de datos'**, en el campo **Nombre**, introduzca **PartyIds**.
    4. En el campo **Tipo de artículo**, seleccione **Int64**.
    5. Seleccione **Aceptar**.

11. Siga estos pasos para agregar un nuevo enlace para recopilar códigos de identificación de registro de las partes cuyas transacciones se presentan en los informes generados:

    1. En el árbol de estructura de formato, seleccione el elemento de artículo de datos **Report.Row.Trans.Id**.
    2. Seleccione **Editar fórmula**.
    3. En la página **Diseñador de fórmulas**, introduzca la expresión `PartyIds.Collect(model.Transaction.Party.RecId)`.
    4. Seleccione **Guardar** y cierre la página **Diseñador de fórmula**.

12. Siga estos pasos para agregar nuevos enlaces para ingresar los nombres de las partes en los informes generados:

    1. En el árbol de estructura de formato, seleccione el elemento de secuencia **Report.Party**.
    2. Seleccione **Editar fórmula**.
    3. En la página **Diseñador de fórmulas**, introduzca la expresión `model.Party(PartyIds.Result)`.
    4. Seleccione **Guardar** y cierre la página **Diseñador de fórmula**.
    5. En el árbol de estructura de formato, seleccione el elemento de secuencia **Report.Party.Name**.
    6. En la pestaña **Asignación**, seleccione el campo `model.Party.Name` del modelo de datos.
    7. Seleccione **Enlazar**.

    ![Estructura del formato ER ajustado en la página Diseñador de formato.](./media/er-data-model-parameterized-calls-format2.png)

13. Seleccione **Guardar** y cierre la página **Diseñador de formato**.
14. Cierre la página **Asignación de modelo a origen de datos**.
15. En la ficha desplegable **Versiones**, para la versión **2.2** seleccione **Cambiar Estado** \> **Completar**. A continuación seleccione **Aceptar**.

### <a name="run-the-adjusted-format"></a>Ejecutar el formato ajustado

1. En la página **Configuraciones**, seleccione **Ejemplo de formato de auditoría** y, a continuación, en el panel de acciones, seleccione **Ejecutar**.
2. En el cuadro de diálogo **Parámetros del informe electrónico**, en la pestaña **Registros a incluir**, seleccione **Filtrar**.
3. Especifique las condiciones para seleccionar las transacciones de impuestos de los vales **PIV-110000004** y **INV-10000001**.
4. Seleccione **Aceptar**.
5. Seleccione **Aceptar**.
6. Revise el documento generado que contiene las transacciones de impuestos de los comprobantes seleccionados y los nombres del cliente y proveedor correspondiente.

    ![Vista previa del documento generado con las transacciones fiscales y nombres de partes.](./media/er-data-model-parameterized-calls-output2.png)

7. Vaya a **Proveedores** \> **Proveedores** \> **Todos los proveedores** y revise los detalles del comprobante **PIV-110000004** seleccionado, incluido el nombre del proveedor.

    ![Revisar los detalles del comprobante de compra en las páginas Todos los proveedores y Diario de facturas.](./media/er-data-model-parameterized-calls-review1.gif)

8. Vaya a **Clientes** \> **Clientes** \> **Todos los clientes** y revise los detalles del comprobante **INV-10000001** seleccionado, incluido el nombre del cliente.

    ![Revisar los detalles del comprobante de venta en las páginas Todos los clientes e Impuesto sobre las ventas registrado.](./media/er-data-model-parameterized-calls-review2.gif)

Para obtener más detalles acerca de esta ejecución de la solución de ER, use el analizador de ER incorporado [seguimiento de rendimiento](trace-execution-er-troubleshoot-perf.md).

## <a name="additional-resources"></a>Recursos adicionales

- [Admita las llamadas con parámetros de los orígenes de datos de ER del tipo de campo calculado](er-calculated-field-type.md)
- [Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md)
- [Utilizar orígenes de datos de RECOPILACIÓN DE DATOS en formatos de informes electrónicos](er-data-collection-data-sources.md)
- [Función ER ValueInLarge](er-functions-logical-valueinlarge.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
