---
title: Diseñar una nueva solución de informes electrónicos para imprimir etiquetas ZPL
description: En este tema se explica cómo diseñar una nueva solución de informes electrónicos (ER) para imprimir etiquetas del lenguaje de programación Zebra (ZPL).
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 4fb89f4b56ce8189482bf1a86582ef7e3684b15a
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2022
ms.locfileid: "8392972"
---
# <a name="design-a-new-er-solution-to-print-zpl-labels"></a>Diseñar una nueva solución de informes electrónicos para imprimir etiquetas ZPL

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tema explica cómo un usuario con el rol de Administrador del sistema, Desarrollador de informes electrónicos o Consultor funcional de informes electrónicos puede configurar los parámetros del marco de [Informes electrónicos (ER)](general-electronic-reporting.md), diseñar las [configuraciones](general-electronic-reporting.md#Configuration) de ER necesarias para una nueva solución de ER con el fin de acceder a los datos del sistema de Warehouse Management, y generar etiquetas personalizadas de ubicación de almacén en el formato del lenguaje de programación Zebra (ZPL) II. Estos pasos se pueden llevar a cabo en la empresa **USRT**.

## <a name="business-scenario"></a>Escenario empresarial

Usted representa a una empresa que implementó la gestión de almacenes en Microsoft Dynamics 365 Finance. Cada ubicación del almacén debe estar rotulada con una etiqueta autoadhesiva que incluya un código de barras. Los trabajadores del almacén utilizarán lectores de códigos de barras portátiles para escanear los códigos de barras.

Todas las ubicaciones de los almacenes se han etiquetado en el alcance de las actividades previas a la puesta en marcha. Sin embargo, también debe poder imprimir etiquetas de ubicación de almacén a pedido si las etiquetas existentes se dañan o si se reconfiguran las estanterías del almacén. Mediante el uso de la funcionalidad ER lanzada recientemente, puede configurar una nueva solución ER que permite que un supervisor de almacén imprima etiquetas directamente en una impresora térmica de etiquetas.

## <a name="configure-the-er-framework"></a>Configurar el marco ER

Siga los pasos de [Configurar el marco de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar el conjunto mínimo de parámetros de ER. Debe completar esta configuración antes de comenzar a utilizar el marco ER para diseñar una solución nueva de ER.

## <a name="design-a-domain-specific-data-model"></a>Diseñar un modelo de datos específico del dominio

Cree una nueva configuración de ER que contenga un componente de [modelo de datos](er-overview-components.md#data-model-component) para el dominio de Warehouse Management. Este modelo de datos se utilizará más tarde como origen de datos al diseñar un formato de ER para generar etiquetas de ubicación de almacén.

### <a name="import-a-data-model-configuration"></a>Importar una configuración de modelo de datos

Siga estos pasos para importar el modelo de datos necesario desde un archivo XML proporcionado por Microsoft. Alternativamente, puede crear su propio modelo de datos como se describe en la siguiente sección.

1. Descargue el archivo [Warehouse model.version.1.xml](https://download.microsoft.com/download/9/f/1/9f136e9b-bf5f-403a-b089-a2b2ed1da2ba/Warehouse-model.version.1.xml) y guárdelo en su equipo local.
2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. En el espacio de trabajo **Informes electrónico**, seleccione **Configuraciones de informes**.
4. En la página **Configuraciones**, en el panel de acciones, seleccione **Exchange** \> **Cargar desde archivo XML**.
5. Seleccione **Examinar** y, a continuación, busque y seleccione el archivo **Warehouse model.version.1.xml**.
6. Seleccione **Aceptar** para importar la configuración.

![Configuración del modelo de datos importado de ER en la página Configuraciones.](./media/er-design-zpl-labels-imported-model.png)

### <a name="create-a-data-model-configuration"></a>Cree una configuración de modelo de datos

En lugar de importar el archivo de modelo de datos proporcionado por Microsoft, puede crear un modelo de datos desde cero. Para ver un ejemplo que muestra cómo completar esta tarea, consulte [Crear una nueva configuración de modelo de datos](er-quick-start1-new-solution.md#DesignDataModel).

### <a name="review-the-data-model"></a>Revise el modelo de datos

Puede ver una versión editable del modelo de datos configurado en la página **Diseñador de modelos de datos**.

![Estructura del modelo de datos de ER en la página Diseñador de modelos de datos.](./media/er-design-zpl-labels-model.png)

## <a name="design-a-model-mapping-for-the-configured-data-model"></a>Diseñar una asignación de modelo para el modelo de datos configurado

Como usuario con el rol de Desarrollador de informes electrónicos, debe crear una nueva configuración de ER que contenga un componente de [asignación de modelo](er-overview-components.md#model-mapping-component) para el modelo de datos Warehouse. Este componente implementa el modelo de datos configurado para Dynamics 365 Finance, es específico para esa aplicación. Debe configurarlo para especificar los objetos de la aplicación que hay que usar para completar el modelo de datos configurado con los datos de la aplicación en tiempo de ejecución. Para completar esta tarea, debe entender cómo la estructura de datos del dominio empresarial de Warehouse Management se implementa en Finance.

### <a name="import-a-model-mapping-configuration"></a>Importar una configuración de asignación de modelo

Siga estos pasos para importar el modelo de asignación necesario desde un archivo XML proporcionado por Microsoft. Alternativamente, puede crear su propio modelo de asignación como se describe en la siguiente sección.

1. Descargue el archivo [Warehouse model mapping.version.1.1.xml](https://download.microsoft.com/download/1/c/c/1cc94d28-3d90-4ffd-a118-77d6c322904f/Warehouse-model-mapping.version.1.1.xml) y guárdelo en su equipo local.
2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. En el espacio de trabajo **Informes electrónico**, seleccione **Configuraciones de informes**.
4. En la página **Configuraciones**, en el panel de acciones, seleccione **Exchange** \> **Cargar desde archivo XML**.
5. Seleccione **Examinar** y, a continuación, busque y seleccione el archivo **Warehouse model mapping.version.1.1.xml**.
6. Seleccione **Aceptar** para importar la configuración.

![Configuración del modelo de asignación importado de ER en la página Configuraciones.](./media/er-design-zpl-labels-imported-mapping.png)

### <a name="create-a-model-mapping-configuration"></a>Cree una configuración de asignación del modelo

En lugar de importar el archivo de modelo de asignación proporcionado por Microsoft, puede crear un modelo de asignación desde cero. Para ver un ejemplo que muestra cómo completar esta tarea, consulte [Crear una nueva configuración de modelo de asignación](er-quick-start1-new-solution.md#CreateModelMapping).

### <a name="review-the-model-mapping"></a>Revisar la asignación de modelo

Puede ver una versión editable del modelo de asignación configurado en la página **Diseñador de modelos de asignación**.

![Estructura del modelo de asignación de ER en la página Diseñador de modelos de asignación.](./media/er-design-zpl-labels-mapping.png)

## <a name="design-a-format"></a>Diseñar un formato

Como usuario con el rol de Consultor funcional de informes electrónicos, debe crear una nueva configuración de ER que contenga un componente de [formato](er-overview-components.md#format-component). Para configurar este componente, utilizará el código ZPL II para especificar el diseño de la etiqueta de ubicación de su almacén.

### <a name="import-a-format-configuration"></a>Importar un formato de configuración

Siga estos pasos para importar el formato necesario desde un archivo XML proporcionado por Microsoft. Alternativamente, puede crear su propio formato como se describe en la siguiente sección.

1. Descargue el archivo [Warehouse location labels.version.1.1.xml](https://download.microsoft.com/download/5/7/5/5758b551-69a5-45bd-a2b2-21c3db73a6fc/Warehouse-location-labels.version.1.1.xml) y guárdelo en su equipo local.
2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. En el espacio de trabajo **Informes electrónico**, seleccione **Configuraciones de informes**.
4. En la página **Configuraciones**, en el panel de acciones, seleccione **Exchange** \> **Cargar desde archivo XML**.
5. Seleccione **Examinar** y, a continuación, busque y seleccione el archivo **Warehouse location labels.version.1.1.xml**.
6. Seleccione **Aceptar** para importar la configuración.

![Configuración del formato importado de ER en la página Configuraciones.](./media/er-design-zpl-labels-imported-format.png)

### <a name="create-a-format-configuration"></a>Crear una configuración de formato

En lugar de importar el archivo de formato proporcionado por Microsoft, puede crear un formato desde cero. Para ver un ejemplo que muestra cómo completar esta tarea, consulte [Crear una nueva configuración de formato](er-quick-start1-new-solution.md#FormatCreate).

### <a name="review-the-format"></a>Revisar el formato

Puede ver una versión editable del formato configurado en la página **Diseñador de formato**.

![Estructura del formato ER en la página Diseñador de formato.](./media/er-design-zpl-labels-format.png)

El origen de datos `model.Location.Label` de este formato está configurada para generar etiquetas que contienen la siguiente información:

- El título del almacén como texto
- El título del almacén como código de barras
- El título de la ubicación
- Dígitos de control

En la página del **Diseñador de fórmulas** para el origen de datos, la fórmula ER que se utiliza para generar etiquetas incluye una función `CONCATENATE` que combina la información en el diseño deseado.

![Fórmula para el origen de datos en la página del diseñador de fórmulas.](./media/er-design-zpl-labels-review-formula.png)

> [!TIP]
> El diseño de la etiqueta está diseñado para que el título de la ubicación y los dígitos de control estén alineados en el centro de la etiqueta. Sin embargo, ZPL II no admite la alineación central de los códigos de barras. Por lo tanto, la fórmula del origen de datos `model.Location.Warehouse.Alignment` se utiliza para alinear el código de barras en el centro de la etiqueta. Esta fórmula calcula el desplazamiento a la izquierda del código de barras, en función del número de caracteres del título del almacén.

## <a name="prepare-your-environment-for-previewing-generated-labels"></a>Prepare su entorno para obtener una vista previa de las etiquetas generadas

El siguiente ejemplo utiliza una aplicación de emulador de impresora para etiquetas ZPL para mostrar una vista previa de las etiquetas generadas en la pantalla. Para activar esta opción, siga estos pasos.

1. Agrega el destino de ER [Impresora](er-destination-type-print.md) para el formato de ER **Etiqueta de ubicación de almacén** y lo configura para enviar las etiquetas generadas desde Finance al [Agente de enrutamiento de documentos (DRA)](install-document-routing-agent.md).
2. Instale y configure el DRA para enrutar las etiquetas generadas desde Finance a una impresora local a la que se puede acceder desde la estación de trabajo actual.
3. Agregue una impresora local para la estación de trabajo actual y configúrela para pasar las etiquetas generadas desde el DRA a una aplicación de emulación de impresora.
4. Instale una aplicación de emulador de impresora como una extensión del navegador web Chrome y configúrelo para pasar las etiquetas generadas desde una impresora local a un servicio web que procesará las etiquetas generadas y las devolverá al emulador de impresora para obtener una vista previa.

<table>
<tbody>
<tr align="center">
<td>
<p>Finance</p>
<p>Informe ER</p>
<p>Destino de la impresora</p>
</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from Finance to the DRA."></td>
<td>Agente de enrutamiento de documentos</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from the DRA to a local printer."></td>
<td>Impresora local</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from a local printer to a printer emulator."></td>
<td>Emulador de impresora</td>
<td><img src="./media/er-design-zpl-labels-flow2.png" alt="Data flow direction: from a printer emulator to a rendering web service and then back to the printer emulator."></td>
<td>Servicio web de representación</td>
</td>
</tr>
</tbody>
</table>

### <a name="install-and-configure-a-printer-emulator-application"></a>Instalar y configurar una aplicación de emulador de impresora

Agregue una aplicación de emulador de impresora para el motor de renderizado ZPL a su navegador web Chrome. Este ejemplo utiliza el emulador [Impresora Zpl](https://chrome.google.com/webstore/detail/zpl-printer/phoidlklenidapnijkabnfdgmadlcmjo) que se basa en el [Servicio web Labelary ZPL](http://labelary.com/service.html). La aplicación del emulador de impresora pasará las etiquetas generadas en formato ZPL desde una impresora local al servicio web y luego devolverá las etiquetas como archivos PDF o PNG para su vista previa.

1. En la tienda web de Chrome, busque y seleccione la aplicación de emulador de impresora que desea utilizar. Luego seleccione **Añadir a Chrome** para agregarlo a su navegador web Chrome.

    ![Agregar la aplicación de emulador de impresora al navegador web Chrome desde Chrome web store.](./media/er-design-zpl-labels-add-app.png)

2. Seleccione **Ejecutar aplicación** para ejecutar la aplicación de emulador de impresora desde el navegador web Chrome.

    ![Ejecutar la aplicación de emulador de impresora desde el navegador web Chrome.](./media/er-design-zpl-labels-run-app.png)

3. Configurar la aplicación de ejecución:

    1. Apague la aplicación.
    2. En la configuración de la impresora, establezca el host en **127.0.0.1**.
    3. Establezca el puerto en **9100**.

        ![Configuración de la aplicación del emulador de impresora.](./media/er-design-zpl-labels-configure-app.png)

    4. Active la aplicación de nuevo. Debería recibir un mensaje que indica que la impresora se inició en el host y el puerto especificados.

        ![Se volvió a activar la aplicación del emulador de impresora.](./media/er-design-zpl-labels-turn-on-app.png)

> [!NOTE]
> Debido a que la aplicación de emulador de impresora que se usa en este ejemplo se basa en un servicio web para generar etiquetas, asegúrese de que su configuración de seguridad le permita comunicarse con el servicio. De lo contrario, la aplicación no recibirá las etiquetas procesadas y no habrá disponible una vista previa de esas etiquetas.

### <a name="add-and-configure-a-local-printer"></a>Agregar y configurar una impresora local

[Agregue una impresora local nueva](https://support.microsoft.com/windows/install-a-printer-in-windows-10-cc0724cf-793e-3542-d1ff-727e4978638b) que el dispositivo actual pueda usar y configúrela para pasar las etiquetas generadas desde el DRA a una aplicación de emulación de impresora.

1. En Windows, seleccione **Inicio** \> **Ajustes** \> **Dispositivos** \> **Impresoras \& escáneres**.
2. Seleccione **Configuración de impresoras \& escáneres**.
3. Para **Añadir una impresora o un escáner**, seleccione **Añadir dispositivo**.
4. Para **La impresora que quiero no está en la lista**, seleccione **Agregar manualmente**.
5. En el campo **Encuentra una impresora por otros medios**, seleccione **Agregue una impresora local o una impresora de red con configuración manual**.
6. En el campo **Elija un puerto de impresora**, seleccione **Crear un nuevo puerto** y luego siga estos pasos:

    1. En el campo **Tipo de puerto** campo, seleccione **Puerto TCP/IP estándar**.
    2. En el campo **Nombre de host o dirección IP**, introduzca **127.0.0.1**.
    3. En el campo **Nombre de puerto**, escriba **ZPL**.
    4. Espera hasta que la operación **Detección del puerto TCP/IP** se complete.
    5. En el campo **Tipo de dispositivo**, seleccione **Personalizado** y después seleccione **Configuración**.
    6. Asegúrese de que se especifican las siguientes configuraciones de puerto:

        - **Nombre del puerto:** ZPL
        - **Nombre de la impresora o dirección IP:** 127.0.0.1
        - **Protocolo:** Raw
        - **Número de puerto:** 9100

7. En el campo **Instale el controlador de la impresora**, seleccione **Genérico / Solo texto**.
8. En el campo **Nombre de la impresora**, escriba **ZebraPrinter**.

![Adición de una impresora local para el dispositivo actual.](./media/er-design-zpl-labels-configure-printer.png)

### <a name="install-and-configure-the-dra"></a>Instalar y configurar el DRA

Prepare el DRA para pasar las etiquetas generadas desde Finance a la impresora local configurada.

1. [Instalar DRA](install-document-routing-agent.md#install-the-document-routing-agent).
2. [Configurar el DRA](install-document-routing-agent.md#configure-the-document-routing-agent).
3. [Registrar la impresora local](install-document-routing-agent.md#register-network-printers) en DRA.
4. [Activar la impresora local](install-document-routing-agent.md#administer-network-printers) en su entorno de Finance.

![Preparando el DRA para imprimir las etiquetas generadas.](./media/er-design-zpl-labels-configure-dra.png)

### <a name="configure-the-er-destination"></a>Configurar el destino de ER

Prepare el destino de ER para pasar las etiquetas generadas desde Finance a DRA.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Destino de informes electrónicos**.
2. En la página **Destino de informes electrónicos**, en el panel de acciones, seleccione **Nuevo**.
3. En el campo **Referencia**, seleccione **Etiquetas de ubicación de almacén**.
4. En la ficha desplegable **Destino del archivo**, seleccione **Nuevo**.
5. En el campo **Nombre**, especifique **Etiquetas**.
6. En el campo **Nombre de componente de archivo**, seleccione **Informe**.
7. Seleccione **Configuración**.
8. En el cuadro de diálogo **Configuración de destino**, en la pestaña **Impresora**, configure la opción **Habilitado** a **Sí**.
9. En el campo **Nombre de la impresora**, seleccione **ZebraPrinter**.
10. En el campo **Tipo de enrutamiento de documento**, seleccione **ZPL**.
11. Seleccione **Aceptar**.

![Configurar el destino de ER para el formato de etiquetas de ubicación de almacén en la página de destino de informes electrónicos.](./media/er-design-zpl-labels-configure-destination.png)

## <a name="review-warehouse-locations"></a>Revisar las ubicaciones del almacén

1. Vaya a **Warehouse Management** \> **Configurar** \> **Almacén** \> **Ubicaciones**.
2. En la página **Ubicaciones**, filtre para ver solo las ubicaciones que tienen un valor en el campo **Comprobar dígitos**.

![Revisar las ubicaciones de los almacenes en la página Ubicaciones.](./media/er-design-zpl-labels-review-locations.png)

## <a name="print-warehouse-location-labels"></a>Imprimir etiquetas de ubicación de almacén

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo para almacén** y seleccione **Etiquetas de ubicación de almacén**.
3. En el panel de acciones, haga clic en **Ejecutar**.
4. En el cuadro de diálogo **Parámetros del informe electrónico**, en la pestaña **Registros a incluir**, seleccione **Filtrar**.
5. En la pestaña **Rango**, encuentre la fila en la que el campo **Tabla** está establecido en **Ubicaciones** y el campo **Campo** está establecido en **Ubicación**. En el campo **Criterios**, introduzca **LPEnabled**.
6. Seleccione **Aceptar**.
7. Seleccione **Aceptar**. Se genera una etiqueta y se muestra en la página de vista previa en la aplicación del emulador de impresora.

![Revisar una etiqueta generada en la página de vista previa de la aplicación del emulador Zpl Printer.](./media/er-design-zpl-labels-preview-label.png)

## <a name="modify-the-layout-of-a-label"></a>Modificar el diseño de una etiqueta

Puede cambiar el diseño actual de las etiquetas de ubicación de su almacén. El siguiente ejemplo muestra cómo cambiar el diseño para que las etiquetas generadas incluyan un identificador de perfil de ubicación.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. Establezca la opción **Usar destinos para el estado de borrador** [Parámetro de usuario de ER](electronic-reporting-destinations.md#applicability) en **Sí**.
3. En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo para almacén** y seleccione **Etiquetas de ubicación de almacén**.
4. Seleccione **Diseñador**.
5. En la página **Diseñador de formato**, en la pestaña **Asignación**, selección el origen de datos `model.Location.Label`.
6. En el cuadro de diálogo **Propiedades del origen de datos**, seleccione **Editar** \> **Editar fórmula**.
7. En la página **Diseñador de fórmulas**, en el campo **Fórmula**, revise la fórmula ER que se utiliza para generar etiquetas.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^XZ")
    ```

8. Actualice la fórmula para agregar un identificador de perfil de ubicación a las etiquetas generadas.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^CF0,40,40^FO0,240^FB800,1,0,C,0^FD",@.ProfileID,"\&^FS",CrLf,
    "^XZ")
    ```

9. Seleccione **Guardar**.
10. Seleccione **Aceptar**.
11. En el panel de acciones, haga clic en **Ejecutar**.
12. En el cuadro de diálogo **Parámetros del informe electrónico**, en la pestaña **Registros a incluir**, seleccione **Filtrar**.
13. En la pestaña **Rango**, encuentre la fila en la que el campo **Tabla** está establecido en **Ubicaciones** y el campo **Campo** está establecido en **Ubicación**. En el campo **Criterios**, escriba **Bahía**.
14. Seleccione **Aceptar**.
15. Seleccione **Aceptar**. Se genera una etiqueta y se muestra en la página de vista previa en la aplicación del emulador de impresora.

![Revisar una etiqueta generada que incluye un ID de perfil de ubicación en la página de vista previa de la aplicación del emulador de la impresora Zpl.](./media/er-design-zpl-labels-preview-label2.png)

## <a name="encoding"></a>Codificación

> [!NOTE]
> Debe sincronizar la configuración de codificación del componente **Common\\File** del formato ER editable y la configuración adecuada de la etiqueta diseñada. El valor del campo **[Codificación](er-suppress-bom-characters.md)** de los componentes **Common\\File** no debe contradecir un comando ZPL que se utiliza para controlar la codificación de la etiqueta (por ejemplo, el comando `^CI`). ER no valida que estas configuraciones estén sincronizadas.

## <a name="additional-resources"></a>Recursos adicionales

[Destino de la impresora](er-destination-type-print.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
