---
title: "Agregar análisis a espacios de trabajo mediante Power BI Embedded"
description: "Este tema muestra cómo insertar un informe de Power BI en la ficha Análisis de un espacio de trabajo."
author: tjvass
manager: AnnBe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: robinr
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.intro: Platform update 8
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 9ee81bbdd22fed4ef6ea97080fe1f6b3d82bcaf5
ms.openlocfilehash: ee95c3d79f7f401c767b9bc8415b21369c14478b
ms.contentlocale: es-es
ms.lasthandoff: 11/06/2017

---

# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a>Agregar análisis a espacios de trabajo mediante Power BI Embedded

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Esta función se admite en Dynamics 365 for Finance and Operations (versión 7.2 y posteriores).

# <a name="introduction"></a>Introducción
Este tema muestra cómo insertar un informe de Microsoft Power BI en la ficha **Análisis** de un espacio de trabajo. Para el ejemplo que se da aquí, extenderemos el espacio de trabajo **Administración de reserva** en la aplicación de administración de flota para insertar un espacio de trabajo analítico en una pestaña **Análisis** .

# <a name="prerequisites"></a>Requisitos previos
+ Obtenga acceso a un entorno del desarrollador de software que ejecute la actualización de plataforma 8 o posterior.
+ Informe analítico (archivo .pbix) que se ha creado usando Microsoft Power BI Desktop, y que tiene un modelo de datos originario de la base de datos del almacén de entidades.

# <a name="overview"></a>Información general
Si extiende un espacio de trabajo de la aplicación existente o presenta un nuevo espacio de trabajo propio, puede usar las visualizaciones analíticas incrustadas para entregar visualizaciones profundas e interactivas de los datos de la empresa. El proceso para agregar una ficha de espacio de trabajo analítico tiene cuatro pasos.

1. Agregue un archivo .pbix como recurso de Dynamics 365.
2. Defina una ficha del espacio de trabajo analítico.
3. Inserte el recurso .pbix en la ficha del espacio de trabajo.
4. Opcional: Agregue extensiones para personalizar la vista.

> [!NOTE]
> Para obtener más información sobre cómo crear informes analíticos, consulte [Introducción a Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/). Esta página es muy buena para obtener información que ayude a crear soluciones de informes analíticos interesantes.

# <a name="add-a-pbix-file-as-a-resource"></a>Agregue un archivo .pbix como recurso
Antes de empezar, debe crear u obtener el informe de Power BI que insertará en el espacio de trabajo. Para obtener más información sobre cómo crear informes analíticos, consulte [Introducción a Power BI Desktop](https://powerbi.microsoft.com/en-us/documentation/powerbi-desktop-getting-started/).
 
Siga estos pasos para agregar un archivo .pbix como artefacto del proyecto de Visual Studio.

1. Cree un nuevo proyecto en el modelo adecuado.
2. En Explorador de soluciones, seleccione el proyecto, haga clic con el botón secundario y, a continuación, seleccione **Agregar** > **Nuevo artículo**.
3. En el cuadro de diálogo **Agregar nuevo artículo** , en **Artefactos de operaciones**, seleccione la plantilla **Recurso**.
4. Escriba un nombre que se usará para hacer referencia al informe en metadatos X++, y después haga clic en **Agregar**.

    ![Cuadro de diálogo Agregar nuevo artículo](media/analytical-workspace-add.png)

5. Busque el archivo .pbix que contiene la definición del informe analítico y, a continuación haga clic en **Abrir**.

    ![Seleccione un cuadro de diálogo del archivo de recursos](media/analytical-workspace-select-resource.png)
  
Ahora que ha agregado el archivo .pbix como recurso de Dynamics 365, puede insertar los informes en los espacios de trabajo y agregar vínculos directos mediante elementos de menú.

# <a name="add-a-tab-control-to-an-application-workspace"></a>Agregar un control de la ficha a un espacio de trabajo de la aplicación
En este ejemplo, extenderemos el espacio de trabajo **Administración de reserva** en el modelo de administración de flota agregando la pestaña **Análisis** a la definición del formulario **FMClerkWorkspace** .
 
La ilustración siguiente muestra qué parece el formulario **FMClerkWorkspace** en el diseñador en Microsoft Visual Studio.

![Formulario FMClerkWorkspace antes de los cambios](media/analytical-workspace-definition-before.png)

Siga estos pasos para extender la definición del formulario para el espacio de trabajo **Administración de reserva**.

1. Abra el diseñador de formularios para ampliar la definición de diseño.
2. En la definición de diseño, seleccione el elemento superior que tiene la etiqueta **Diseño | Patrón: Operacional en espacio de trabajo**.
3. Haga clic con el botón secundario y, a continuación seleccione **Nuevo** > **Ficha** para agregar un nuevo control que se llama **FormTabControl1**.
4. En el diseñador del formulario, seleccione **FormTabControl1**.
5. Haga clic con el botón secundario y, a continuación seleccione **Página de nueva pestaña** para agregar una nueva página de pestaña.
6. Cambie el nombre de la página de ficha por un nombre con significado, como por ejemplo **Espacio de trabajo**.
7. En el diseñador del formulario, seleccione **FormTabControl1**.
8. Haga clic con el botón secundario del mouse y seleccione **Página de nueva pestaña**.
9. Cambie el nombre de la página de ficha por un nombre con significado, como por ejemplo **Análisis**.
10. En el diseñador de formularios, seleccione **Análisis (página de pestaña)**.
11. Establezca la propiedad **Leyenda** en **Análisis**.
12. Haga clic con el botón secundario en el control y, a continuación seleccione **Nuevo** > **Grupo** para agregar un nuevo control de grupo del formulario.
13. Cambie el nombre del grupo de formulario por un nombre con significado, como por ejemplo **powerBIReportGroup**.
14. En el diseñador de formularios, seleccione **PanoramaBody (ficha)**, y después arrastre el control a la pestaña **Espacio de trabajo** .
15. En la definición de diseño, seleccione el elemento superior que tiene la etiqueta **Diseño | Patrón: Operacional en espacio de trabajo**.
16. Haga clic con el botón secundario del mouse y seleccione **Quitar patrón**.
17. Vuelva a hacer clic con el botón secundario, y después seleccione **Agregar patrón** > **Espacio de trabajo tabulado**.
18. Realice una compilación para comprobar los cambios.
 
La ilustración siguiente muestra el aspecto del diseño después de aplicar estos cambios.

![FMClerkWorkspace después de los cambios](media/analytical-workspace-definition-after.png)

Ahora que ha agregado los controles de formulario que se usarán para insertar el informe del espacio de trabajo, debe definir el tamaño del control principal de modo que aloje el diseño. De forma predeterminada, la página **Panel de los filtros** y la página **Ficha** serán visibles en el informe. Sin embargo, puede cambiar la visibilidad de estos controles según corresponda para el consumidor de destino del informe.
 
> [!NOTE]
> Para los espacios de trabajo incrustados se recomienda usar extensiones para ocultar las páginas **Panel de los filtros** y **Ficha** para tener en cuenta la coherencia.
 
Ha terminado la tarea de ampliar la definición del formulario de solicitud. Para obtener más información sobre cómo usar extensiones para personalizaciones, consulte [Personalización: superposiciones y extensiones](../extensibility/customization-overlayering-extensions.md).

# <a name="add-x-business-logic-to-embed-a-viewer-control"></a>Agregue la lógica de negocios X++ para insertar un control del visor
Siga estos pasos para agregar la lógica de negocios que inicializa el control del visor de informes que está insertado en el espacio de trabajo **Administración de reserva**.

1. Abra el diseñador de formularios **FMClerkWorkspace** para ampliar la definición de diseño.
2. Presione F7 para obtener acceso al código que subyace a la definición del código.
3. Agregue el código X++ siguiente.

    ```
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;     
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                FMPBIWorkspaceController controller = new FMPBIWorkspaceController();
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
    }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. Realice una compilación para comprobar los cambios.

Ha terminado la tarea de agregar la lógica de negocios para inicializar el control del visor del informe incrustado. La ilustración siguiente muestra el aspecto del espacio de trabajo después de aplicar estos cambios.

![Informe insertado en el espacio de trabajo](media/analytical-workspace-final.png)

> [!NOTE]
> Puede obtener acceso a la vista operativa existente mediante las fichas del espacio de trabajo de debajo del título de la página.

# <a name="reference"></a>Referencia

## <a name="pbireporthelperinitializereportcontrol-method"></a>Método de PBIReportHelper.initializeReportControl
Esta sección proporciona información sobre la clase de auxiliar que se utiliza para insertar un informe de Power BI (recurso .pbix) en un control de grupo del formulario.

### <a name="syntax"></a>Sintaxis
```
public static void initializeReportControl(
     str                 _resourceName,
     FormGroupControl    _formGroupControl,
     str                 _defaultPageName = '',
     boolean             _showFilterPane = false,
     boolean             _showNavPane = false,
     List                _defaultFilters = new List(Types::Class))
```

### <a name="parameters"></a>Parámetros

| Nombre | Descripción |
|---|---|
| resourceName | El nombre del recurso .pbix. |
| formGroupControl | El control de grupo de formulario al que se aplica el control del informe de Power BI. |
| defaultPageName | El nombre de la página predeterminada. |
| showFilterPane | Un valor booleano que indica si el panel de filtros se debe mostrar (**true**) u ocultar (**false**). |
| showNavPane | Un valor booleano que indica si el panel de navegación se debe mostrar (**true**) u ocultar (**false**). |
| defaultFilters | Los filtros predeterminados del informe de Power BI. |

