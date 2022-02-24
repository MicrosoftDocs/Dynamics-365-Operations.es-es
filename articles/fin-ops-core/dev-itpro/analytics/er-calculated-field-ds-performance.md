---
title: Mejorar el rendimiento de las soluciones de ER agregando orígenes de datos de CAMPO CALCULADO parametrizados
description: Este tema explica cómo puede ayudar a mejorar el rendimiento de las soluciones de generación de informes electrónicos (ER) agregando orígenes de datos de CAMPO CALCULADO parametrizados.
author: NickSelin
manager: AnnBe
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 940b696a06fb46bcd0557f059327cd4340448137
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681289"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a>Mejorar el rendimiento de las soluciones de ER agregando orígenes de datos de CAMPO CALCULADO parametrizados

[!include [banner](../includes/banner.md)]

Este tema explica cómo puede realizar [seguimientos de rendimiento](trace-execution-er-troubleshoot-perf.md) de formatos de [Informes electrónicos (ER)](general-electronic-reporting.md) que se ejecutan y luego utilizan la información de esos seguimientos para ayudar a mejorar el rendimiento mediante la configuración de orígenes de datos de **Campo calculado** parametrizados.

Como parte del proceso de diseño de las configuraciones de informes electrónicos (ER) para generar documentos electrónicos empresariales, se define el método que se usa para recuperar datos de la aplicación y para introducirlos en el resultado generado. Al diseñar un origen de datos de ER parametrizado del tipo de **Campo calculado**, puede reducir la cantidad de llamadas a la base de datos y reducir significativamente el tiempo y el coste que implica recopilar los detalles de la ejecución del formato ER.

## <a name="prerequisites"></a>Requisitos previos

- Para completar los ejemplos de este tema, debe tener acceso a uno de los siguientes [roles](../sysadmin/tasks/assign-users-security-roles.md):

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

- La empresa debe establecerse en **DEMF**.
- Siga los pasos del [Apéndice 1](#appendix1) de este tema para descargar los componentes de la solución ER de Microsoft de ejemplo que se requieren para completar los ejemplos de este tema.
- Siga los pasos en el [Apéndice 2](#appendix2) de este tema para configurar el conjunto mínimo de parámetros de ER que se requiere para usar el marco de ER para ayudar a mejorar el rendimiento de la solución de Microsoft ER de ejemplo.

## <a name="import-the-sample-er-solution"></a>Importar la solución de ER de ejemplo

Supongamos que debe diseñar una nueva solución de ER para generar un nuevo informe que muestra las transacciones de proveedor. Actualmente, puede buscar las transacciones de un proveedor seleccionado en la página **Transacciones de proveedor** (vaya **Proveedores** \> **Proveedores** \> **Todos los proveedores**, seleccione un proveedor y, a continuación, en el panel de acciones, en la pestaña **Proveedor**, en el grupo **Transacciones**, seleccione **Transacciones**). Sin embargo, desea tener todas las transacciones de proveedor juntas en un documento electrónico en formato XML. Esta solución consistirá en varias configuraciones de ER que contienen el modelo de datos requeridos, la asignación modelo, y los componentes del formato.

El primer paso es importar la solución ER de ejemplo para generar un informe de transacciones del proveedor.

1. Iniciar sesión en la instancia de Microsoft Dynamics 365 Finance que se ha aprovisionado para su empresa.
2. En este tema, usted creará y modificará las configuraciones de ER necesarias para la empresa de ejemplo, **Litware, Inc.** Asegúrese de que este proveedor de configuración se han agregado a la instancia de Finance y se marca como activo. Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. En el espacio de trabajo **Informe electrónico**, seleccione el mosaico **Configuraciones de informes** .
4. En la página **Configuraciones** importe las configuraciones de ER que ha descargado como requisito previo en el Finance, en el orden siguiente: modelo de datos, asignación modelo, formato. Para cada configuración, siga estos pasos:

    1. En el panel Acción, seleccione **Exchange** \> **Cargar del archivo XML**.
    2. Seleccione **Exploración** y seleccione seleccionar el archivo adecuado para la configuración de ER en formato XML.
    3. Seleccione **Aceptar**.

![Configuraciones importadas en la página Configuraciones](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a>Revisar la solución de ER de ejemplo

### <a name="review-the-model-mapping"></a>Revisar la asignación de modelo

1. En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo de mejora del rendimiento** y seleccione **Asignación de mejora del rendimiento**.
2. En el panel de acciones, haga clic en **Diseñador**.
3. En la página **Asignación de modelo a origen de datos** en el Panel acciones, seleccione **Diseñador**.

    Esta distribución del modelo de ER está diseñada para hacer lo siguiente:

    - Obtener la lista de transacciones de proveedores que están almacenadas en la tabla VendTrans (origen de datos **Trans**).
    - Para cada transacción, obtenga, de la tabla VendTable, el registro de un proveedor para el que se registró la transacción (origen de datos **\#Vend**).

    > [!NOTE]
    > Los orígenes de datos **\#Vend** están configurados para obtener el registro de proveedor correspondiente mediante el uso de la relación existente de muchos a uno **\@.'\>Relations'.VendTable\_AccountNum**.

    La distribución de modelo en esta configuración implementa el modelo de datos base de todos los formatos ER creados para este modelo y ejecutados en Finance. Por lo tanto, el contenido de los orígenes de datos **Trans** se expone para los formatos de ER como orígenes de datos **modelo** abstractos.

    ![Origen de datos Trans en la página del diseñador de asignación de modelo](media/er-calculated-field-ds-performance-mapping-1.png)

4. Cierre la página **Diseñador de distribución del modelo**.
5. Cierre la página **Asignación de modelo a origen de datos**.

### <a name="review-format"></a>Formato de revisión

1. En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo de mejora del rendimiento** y seleccione **Formato de mejora del rendimiento**.
2. En el panel de acciones, haga clic en **Diseñador**.
3. En la página **Diseñador de formato**, en la pestaña **Asignación**, seleccione **Expander/Contraer**.
4. Expanda los elementos **Modelo**, **Datos,** y **Transacción**.

    Este formato ER está diseñado para generar un informe de transacciones de proveedores en formato XML.

    ![Formatear orígenes de datos y vínculos configurados de elementos de formato en la página del diseñador de formato](media/er-calculated-field-ds-performance-format.png)

5. Cierre la página **Diseñador de formato**.

## <a name="run-the-sample-er-solution-to-trace-execution"></a>Ejecute la solución de ER de ejemplo para realizar un seguimiento de la ejecución

Supongamos que haya terminado de diseñar de la primera versión de la solución de ER. Ahora desea probar la solución en su instancia de Finance and Operations y analizar el rendimiento de la ejecución.

### <a name="turn-on-the-er-performance-trace"></a>Activar el seguimiento del rendimiento de ER

1. Seleccione la compañía **DEMF**.
2. Siga los pasos en [Activar el seguimiento de rendimiento de ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) para generar un seguimiento de rendimiento mientras se ejecuta un formato ER.

    ![Cuadro de diálogo parámetros de usuario](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a>Ejecutar formato del ER

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuración, seleccione el elemento **Formato de mejora del rendimiento**.
3. En el panel de acciones, haga clic en **Ejecutar**.

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a>Utilizar el seguimiento de rendimiento para analizar el rendimiento de la asignación de modelos

1. En la página **Configuraciones**, en el árbol de configuración, seleccione el elemento **Asignación de mejora del rendimiento**.
2. En el panel de acciones, haga clic en **Diseñador**.
3. En la página **Asignaciones de modelo** en el Panel acciones, seleccione **Diseñador**.
4. En la página **Diseñador de distribución del modelo**, en el panel de acciones seleccione **Seguimiento del rendimiento**.
5. Seleccione el seguimiento más reciente que se generó y luego seleccione **Aceptar**.

La nueva información está ahora disponible para algunos artículos de orígenes de datos de la asignación del modelo actual:

- El tiempo real empleado que se usó para obtener datos mediante el origen de datos
- El mismo tiempo expresado como un porcentaje de tiempo total que se ha dedicado a ejecutar toda la distribución del modelo

![Detalles del tiempo de ejecución en la página del diseñador de asignación de modelos](./media/er-calculated-field-ds-performance-mapping-2.png)

La cuadrícula **Estadísticas de rendimiento** muestra que el origen de datos **Trans** llama a la tabla VendTrans una vez. El valor **\[265\]\[Q: 265\]** del origen de datos **Trans** indica que se han obtenido 265 transacciones de proveedores de la tabla de la aplicación y se han devuelto al modelo de datos.

Los **Estadísticas de rendimiento** también muestran que la asignación de modelos actual duplica las solicitudes de la base de datos mientras que el origen de datos **\#Vend** se ejecuta. Es se produce por los siguientes motivos:

- La tabla de proveedores se llama dos veces para cada una de las 265 transacciones de proveedores iteradas, para un total de 530 llamadas:

    - Se realiza una llamada para especificar el número de cuenta del proveedor.
    - Se realiza una llamada para especificar el nombre del proveedor.

- Se llama a la tabla de proveedores para cada transacción de proveedor iterada, aunque las transacciones obtenidas se hayan registrado solo para cinco proveedores. De las 530 llamadas, 525 son duplicadas. La siguiente ilustración muestra el mensaje que recibe sobre llamadas duplicadas (solicitudes de base de datos).

![Mensaje sobre solicitudes duplicadas a la base de datos en la página de diseñador de la distribución del modelo](./media/er-calculated-field-ds-performance-mapping-2a.png)

Del tiempo total de ejecución de la asignación de modelos (aproximadamente ocho segundos), observe que más del 80 por ciento (aproximadamente seis segundos) se ha dedicado a recuperar valores de la tabla de aplicación VendTable. Ese porcentaje es demasiado grande para dos atributos de cinco proveedores, en comparación con el volumen de información de la tabla de aplicaciones de VendTrans.

Para reducir la cantidad de llamadas que se realizan para obtener los detalles del proveedor para cada transacción y mejorar el rendimiento de la asignación de modelos puede usar el almacenamiento en caché para el origen de datos **\#Vend**.

> [!NOTE]
> El origen de datos **Trans\\\#Vend** se almacenará en caché en el ámbito de la transacción actual del origen de datos **Trans** en tiempo de ejecución.

Al almacenar en caché el origen de datos **\#Vend**, reduce el número de llamadas duplicadas de 525 a 260, pero no elimina por completo la duplicación. Para eliminar por completo la duplicación, puede configurar un nuevo origen de datos parametrizado del tipo de **Campo calculado**.

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Mejorar la distribución del de modelo según la información de seguimiento de la ejecución

### <a name="change-the-logic-of-the-model-mapping"></a>Modificar la lógica de la distribución del modelo

Siga estos pasos para utilizar el almacenamiento en caché y un origen de datos del tipo de **Campo calculado**, para ayudar a prevenir llamadas duplicadas a la base de datos.

1. En la página **Configuraciones**, en el árbol de configuración, seleccione el elemento **Asignación de mejora del rendimiento**.
2. En el panel de acciones, haga clic en **Diseñador**.
3. En la página **Asignaciones de modelo** en el Panel acciones, seleccione **Diseñador**.
4. En la página **Diseñador de asignación de modelos**, siga estos pasos para agregar un origen de datos del tipo **Registros de tabla** para acceder a los registros en la tabla de aplicación VendTable:

    1. En el panel **Tipos de origen de datos**, expanda **Dynamics 365 for Operations** y seleccione **Registros de tabla**.
    2. Seleccione **Agregar raíz**.
    3. En el cuadro de diálogo desplegable, en el campo **Nombre**, escriba **Vend**.
    4. En el campo **Tabla**, escriba **VendTable**.
    5. Seleccione **Aceptar**.

5. Puede parametrizar llamadas a orígenes de datos del tipo de **Campo calculado** solo si esos orígenes de datos residen en un contenedor. Por lo tanto, siga estos pasos para agregar una fuente de datos del tipo **Contenedor vacío** para contener un nuevo origen de datos parametrizado del tipo **Campo calculado**:

    1. En el panel **Tipos de origen de datos**, expanda **General** y seleccione **Vaciar contenedor**.
    2. Seleccione **Agregar raíz**.
    3. En el cuadro de diálogo desplegable, en el campo **Nombre**, escriba **Box**.
    3. Seleccione **Aceptar**.

    ![Origen de datos Box en la página del diseñador de asignación de modelo](./media/er-calculated-field-ds-performance-mapping-3.png)

6. Siga estos pasos para agregar un origen de datos parametrizado del tipo **Campo calculado**:

    1. En el panel **Origen de datos**, seleccione **Box**.
    2. En el panel **Tipos de origen de datos**, expanda **Funciones**, y seleccione **Campo calculado**.
    3. Seleccione **Agregar**.
    4. En el cuadro de diálogo desplegable, en el campo **Nombre**, escriba **Vend**.
    5. Seleccione **Editar fórmula**.
    6. En la página **Diseñador de fórmulas**, seleccione **Parámetros** para especificar los parámetros que deben proporcionarse cuando se llama a este origen de datos.
    7. En el cuadro de diálogo **Parámetros**, seleccione los **Nuevo**.
    8. En el campo **Nombre**, escriba **parmVendAccNumber**.
    9. En el campo **Tipo**, seleccione **Cadena**.
    10. Seleccione **Aceptar**.
    11. En el campo **Fórmula**, especifique **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.
    12. Seleccione **Guardar** y cierre la página **Diseñador de fórmula**.
    13. Seleccione **Aceptar** para agregar el nuevo origen de datos.

7. Siga estos pasos para marcar el origen de datos agregado como almacenada en caché durante la ejecución:

    1. En el panel **Orígenes de datos**, seleccione **Box\\Vend**.
    2. Seleccione **Memoria caché**.

    > [!NOTE]
    > El origen de datos **Box\\Vend** se almacenará en caché en el ámbito de las transacciones de todos los proveedores del origen de datos **Trans** en tiempo de ejecución.

8. Siga estos pasos para actualizar el origen de datos anidado **Trans\\\#Vend** para que utilice el origen de datos **Box\\Vend**:

    1. En el panel **Orígenes de datos**, expanda **Trans**.
    2. Selecciona el origen de datos **Trans\\\#Vend** y luego seleccione **Editar** \> **Editar fórmula**.
    3. En la página **Diseñador de fórmulas**, en el campo **Fórmula**, especifique **Box.Vend (\@.AccountNum)**.
    4. Seleccione **Guardar** y después, cierre la página **Diseñador de fórmulas**.
    5. Seleccione **Aceptar** para completar sus cambios en el origen de datos seleccionado.

9. Seleccione **Guardar**.

    ![Origen de datos Vend en la página del diseñador de asignación de modelo](./media/er-calculated-field-ds-performance-mapping-4.png)

10. Cierre la página **Diseñador de distribución del modelo**.
11. Cierre la página **Distribuciones del modelo**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Complete la versión modificada de la distribución del modelo de ER

1. En la página **Configuraciones**, en la ficha desplegable **Versiones**, seleccione la versión **1.2** de la configuración del **Seguimiento de la mejora del rendimiento**.
2. Seleccione **Cambiar estado** \> **Completar** y luego seleccione **Aceptar**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Ejecute la solución modificada de ER para realizar un seguimiento de la ejecución

Repita los pasos de la sección anterior [Ejecutar formato del ER](#run-format) en este tema para generar un nuevo seguimiento del rendimiento.

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a>Utilizar el seguimiento de rendimiento para analizar los ajustes en la asignación de modelos 

1. En la página **Configuraciones**, en el árbol de configuración, seleccione el elemento **Asignación de mejora del rendimiento**.
2. En el panel de acciones, haga clic en **Diseñador**.
3. En la página **Asignaciones de modelo** en el Panel acciones, seleccione **Diseñador**.
4. En la página **Diseñador de distribución del modelo**, en el panel de acciones seleccione **Seguimiento del rendimiento**.
5. Seleccione el seguimiento más reciente que se generó y luego seleccione **Aceptar**.

Observe que los ajustes que realizó en la distribución de modelo han eliminado las consultas duplicadas en la base de datos. El número de llamadas a las tablas de base de datos y de orígenes de datos para esta distribución de modelo también se ha reducido.

![Realizar un seguimiento de la información en la página del diseñador de asignación de modelo 1](./media/er-calculated-field-ds-performance-mapping-5.png)

El tiempo total de ejecución se ha reducido unas 20 veces (de unos 8 segundos a unos 400 milisegundos). Por lo tanto, el rendimiento de la solución completa de ER ha mejorado.

![Realizar un seguimiento de la información en la página del diseñador de asignación de modelo 2](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a>Apéndice 1: Descargar los componentes de la solución Microsoft ER de ejemplo

Debe descargar y también almacenar los siguientes archivos y guardarlos localmente.

| Archivo                                        | Contenido |
|---------------------------------------------|---------|
| Mejora del rendimiento model.version.1     | [Configuración del modelo datos de ER de ejemplo](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Mejora del rendimiento mapping.version.1.1 | [Configuración del modelo de mapeado de ER de ejemplo](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Mejora del rendimiento format.version.1.1  | [Configuración de formato de ER de ejemplo](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a>Apéndice 2: Configurar el marco ER

Antes de que pueda comenzar a utilizar el marco de ER para mejorar el rendimiento de la solución de Microsoft ER de ejemplo, debe configurar el conjunto mínimo de parámetros de ER.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Configurar los parámetros de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.
3. En la página **Parámetros de informes electrónicos**, en la pestaña **General**, establezca la opción **Habilitar modo de diseño** en **Sí**.
4. En la pestaña **Adjuntos**, establezca los parámetros siguientes:

    - En el campo **Configuraciones**, seleccione el tipo **Archivo** para el **DEMF** de la empresa.
    - En los campos **Archivo de trabajo**, **Temporal**, **Base** y **Otros**, seleccione el tipo **Archivo**.

Para obtener más información sobre cómo configurar los parámetros de ER, consulte [Configurar el marco de ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Activar un proveedor de configuración de ER

Cada configuración de ER que se agrega está marcada como propiedad de un proveedor de configuración de ER. El proveedor de configuración de ER que se activa en el espacio de trabajo **Informes electrónicos** se utiliza para este propósito. Por lo tanto, debe activar un proveedor de configuración de ER en el espacio de trabajo **Informes electrónicos** antes de comenzar a agregar o editar configuraciones de ER.

> [!NOTE]
> Solo el propietario de una configuración de ER puede editarla. Por lo tanto, antes de poder editar una configuración de ER, se debe activar el proveedor de configuración ER apropiado en el espacio de trabajo **Informes electrónicos**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Revise la lista de proveedores de configuración de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.
3. En la página **Tabla de proveedor de configuración**, cada registro de proveedor tiene un nombre y URL únicos. Revise el contenido de esta página. Si un registro para **Litware, Inc.** ya existe, omita el siguiente procedimiento, [Agregar un nuevo proveedor de configuración de ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Añada una nueva configuración para el proveedor de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.
3. En la página **Proveedores de configuración**, seleccione **Nuevo**.
4. En el campo **Nombre**, introduzca **Litware, Inc.**
5. En el campo **Dirección de Internet**, introduzca `https://www.litware.com`.
6. Seleccione **Guardar**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Activar un proveedor de configuración de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Litware, Inc.** y luego seleccione **Establecer activo**.

Para obtener más información sobre proveedores de configuración de ER, consulte [Crear proveedores de la configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos](general-electronic-reporting.md)
- [Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md)
- [Admita las llamadas con parámetros de los orígenes de datos de ER del tipo de campo calculado](er-calculated-field-type.md)
