---
title: Interfaz de usuario estilo Microsoft Office en la Administración de documentos empresariales (contiene video)
description: Este artículo explica cómo usar la nueva interfaz de usuario de documentos en la función de Administración de documentos empresariales del marco de informes electrónicos (ER).
author: v-anamir
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bcc464a17e27393c5904c59b8439de6ca000d57a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892236"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Interfaz de usuario estilo Microsoft Office en la Administración de documentos empresariales

[!include [banner](../includes/banner.md)]

La gestión de documentos empresariales aprovecha el marco de ER y permite a los usuarios empresariales editar plantillas de documentos empresariales mediante el servicio de Microsoft Office 365 o la aplicación de escritorio de Microsoft Office apropiada. Las ediciones pueden incluir cambios de diseño o nuevas implementaciones, o los usuarios pueden agregar marcadores de posición para incluir datos adicionales sin tener que cambiar el código fuente. Para obtener más información sobre cómo trabajar con la gestión de documentos empresariales, vea [Resumen de gestión de documentos comerciales](er-business-document-management.md).

La nueva interfaz de usuario (UI) es más clara y más cómoda de usar. El área **documento comercial** muestra solo las plantillas que son propiedad del actual [proveedor](general-electronic-reporting.md#Provider) [activo](tasks/er-configuration-provider-mark-it-active-2016-11.md) y ubicado en la instancia actual de Dynamics 365 Finance. En la interfaz de usuario anterior, la pestaña **Plantilla** incluía todas las plantillas que estaban disponibles para cualquier proveedor. También mostraba todas las plantillas que fueron creadas y editadas por cualquier usuario que tuviera el mismo rol.

Puedes usar el botón **Nuevo documento** en el espacio de trabajo **Gestión de documentos comerciales** para crear y editar una plantilla en una [configuración](general-electronic-reporting.md#Configuration) de formato de [Reporte electrónico (ER)](general-electronic-reporting.md) proporcionado por otro proveedor y ubicado en la instancia de Finance actual, o para cargar una nueva plantilla desde un libro de Excel. Además, en la versión 10.0.25 y posteriores, puede utilizar el botón **Nuevo documento** para crear y editar una plantilla en una configuración de formato ER que se almacena en el [Repositorio mundial](general-electronic-reporting.md#Repository).

En los ejemplos de este artículo, el proveedor activo es Contoso y lo usa para crear una plantilla basada en una plantilla proporcionada por Microsoft. Alternativamente, puede crear una plantilla cargando su propia plantilla en formato Excel.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWAVQg]

El vídeo [Crear un nuevo documento comercial utilizando la gestión de documentos comerciales](https://youtu.be/gAIYl-mM_pw) (mostrado arriba) está incluido en la [lista de reproducción de Finanzas y operaciones](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Poner a disposición la nueva interfaz de usuario de documentos en la gestión de documentos empresariales

Para comenzar a utilizar la nueva interfaz de usuario de documentos en la gestión de documentos empresariales, debe activar la característica **Experiencia de interfaz de usuario similar a oficina para la gestión de documentos empresariales** en el espacio de trabajo **Administración de características**.

Siga estos pasos para activar esta función para todas las entidades jurídicas.

1. En el espacio de trabajo **Administración de características**, en la pestaña **Todo**, seleccione la característica **Experiencia de IU similar a oficina para la gestión de documentos empresariales** en la lista.
2. Seleccione **Habilitar ahora** para activar la característica seleccionada.
3. Actualice la página para obtener acceso a la característica nueva.

## <a name="add-or-activate-a-provider"></a>Agregar o activar un proveedor de configuración

Cada plantilla de un documento comercial se almacena en una configuración de formato ER que está marcada como propiedad de un proveedor de configuración específico. Cuando crea una nueva plantilla, se crea una nueva configuración de formato ER para contenerla. Por lo tanto, se debe identificar un proveedor para esa configuración. El proveedor activo del marco ER se utiliza para este propósito. Si no hay ningún proveedor en ER, puede crear uno. Si no hay ningún proveedor *activo*, puede activar uno de los proveedores existentes. Se abre un cuadro de diálogo para agregar o activar un proveedor cuando es necesario mientras comienza a agregar una nueva plantilla.

### <a name="add-a-new-provider"></a>Agregar un nuevo proveedor

Para crear un nuevo proveedor, siga estos pasos en el diálogo **Proveedor de configuración**:

1.  Sobre la pestaña **Elegir proveedor de configuración**, en el campo **Nombre**, ingrese el nombre del nuevo proveedor.
2.  En el campo **Dirección de Internet**, escriba la dirección de internet (URL) del nuevo proveedor. 
3.  Seleccione **Aceptar**.

    ![Creación de un nuevo proveedor en Business Document Management.](./media/bdm_create_provider.png)

El proveedor añadido se activará automáticamente.

### <a name="activate-a-provider"></a>Activar un proveedor

Para activar un proveedor, siga estos pasos en el diálogo **Proveedor de configuración**:

1.  Sobre la pestaña **Elegir proveedor de configuración**, en el campo **Proveedor de configuración**, seleccione el proveedor.
2.  Seleccione **Aceptar**.

    ![Activar un proveedor en Business Document Management.](./media/bdm_choose_provider.png)

El proveedor seleccionado se activará.

> [!NOTE]
> Cada plantilla de gestión de documentos comerciales se encuentra en una configuración de formato ER que hace referencia al proveedor como autor de la configuración. Por tanto, se requiere un proveedor activo para cada plantilla.

## <a name="edit-a-template-that-is-owned-by-another-provider"></a>Editar una plantilla propiedad de otro proveedor

Este ejemplo muestra cómo usar el botón **Nuevo documento** en el espacio de trabajo **Gestión de documentos comerciales** para crear y editar una plantilla en una configuración de formato de ER proporcionado por otro proveedor y ubicado en la instancia de Finance actual. En este ejemplo, el proveedor activo es Contoso, que usa la configuración de formato ER proporcionada por Microsoft. Después de seleccionar **Nuevo documento**, la pestaña **Seleccionar** de la página **Crear una nueva plantilla** muestra todas las plantillas de la instancia de Finanzas actual que son propiedad del proveedor actual y de otros proveedores. Seleccionar una plantilla para abrirla. A continuación, puede crear una nueva copia editable de la plantilla. La plantilla editada se almacena en una nueva configuración del formato de ER que se genera automáticamente.

1. En el espacio de trabajo de **Gestión de documentos empresariales**, seleccione **Nuevo documento**.

    ![Espacio de trabajo de la gestión de documentos empresariales.](./media/BDM_overview_new_template1.png)

2. Sobre la página **Crear una nueva plantilla**, en la ficha **Seleccionar**, seleccione el documento que desea usar como plantilla y, a continuación, seleccione **Crear documento**.

    ![Cuadro de diálogo Documentos empresariales.](./media/BDM_overview_new_template2.png)

3. En el nuevo cuadro de diálogo, en el campo **Título**, cambie el título según lo requiera. El texto del título se usa para asignar un nombre a la nueva configuración del formato de ER que se crea automáticamente. La versión del borrador de esta configuración (**Copia de informe FTI de cliente (GER)**) incluirá la plantilla editada y se usará para ejecutar este formato de ER para el usuario actual. La plantilla original no modificada de la configuración del formato básico de ER se usará para ejecutar este formato de ER para los otros usuarios.
4. En el campo **Nombre**, cambie el nombre de la primera revisión de la plantilla editable que se creará automáticamente.
5. En el campo **Comentario**, actualice los comentarios para la revisión de la plantilla editable que se creará automáticamente.
6. Seleccione **Aceptar** para confirmar el inicio del proceso de edición.

    ![Cuadro de diálogo Creación de documentos.](./media/BDM_overview_new_template3.png)

## <a name="upload-a-template-that-uses-an-existing-excel-workbook"></a>Cargue una plantilla que use un libro de Excel existente

Este ejemplo muestra cómo usar el botón **Nuevo documento** en el espacio de trabajo **Gestión de documentos comerciales** para crear y editar una plantilla en una configuración de formato de ER, según el libro de Excel disponible. En este ejemplo, el proveedor activo es Contoso y usted usa las configuraciones de [modelo de datos](er-overview-components.md#data-model-component) de ER y de [asignación de modelos](er-overview-components.md#model-mapping-component) de ER proporcionadas por Microsoft. Después de seleccionar **Nuevo documento**, selecciona la ficha **Subir** en la página **Crear una nueva plantilla**. Allí, puede especificar los detalles de la carga de un libro de Excel. Después de cargar el libro de Excel, se transforma en una plantilla de documento comercial que se abre para su edición. La plantilla editada se almacenará en una nueva configuración del formato de ER que se genera automáticamente.

Siga estos pasos para proporcionar la información requerida antes de cargar una plantilla.

1. En el espacio de trabajo de **Gestión de documentos empresariales**, seleccione **Nuevo documento**.
2. En la página **Crear una nueva plantilla**, en la pestaña **Subir**, en la pestaña **Plantilla**, seleccione **Navegar** para buscar y seleccionar el archivo de Excel que desea utilizar como plantilla. En la sección **Plantilla**, los campos **Título** y **Descripción** se completan automáticamente. Especifican el nombre y la descripción de la nueva configuración de formato ER que se crea automáticamente. Si es necesario, puede editar estos campos.
3. En la sección **Tipo de Documento**, en el campo **Nombre**, especifique el tipo de documento comercial. Este valor se utilizará para buscar la fuente de datos correcta (es decir, la configuración del modelo ER).

    ![Pestaña Plantilla en la pestaña Cargar de la página Crear una nueva plantilla.](./media/BDM_overview_new_UI_import_21.jpg)

4. En la pestaña **Fuente de datos**, en la ficha desplegable **Filtro**, seleccione **Aplicar filtro**. En la sección **Fuente de datos**, el campo **Nombre** se rellena automáticamente o puede seleccionar manualmente un valor. Puede utilizar el filtro para buscar el nombre de fuente de datos adecuado por nombre, descripción, código de país o región y tipo de documento comercial.

    ![Pestaña Origen de datos de la pestaña Cargar de la página Crear una nueva plantilla.](./media/BDM_overview_new_UI_import_31.jpg)

    > [!NOTE]
    > La ficha desplegable **Filtro** se utiliza para buscar la fuente de datos correcta (es decir, la configuración del modelo ER). Puede editar todos los campos de filtro para encontrar la fuente de datos más adecuada para el documento que está cargando.
    > 
    > Las condiciones de la ficha desplegable **Filtro** se utilizan como condiciones **O**.

5. En la pestaña **Asignación**, seleccione **Detectar automáticamente**. El campo **Definición raíz** se rellena automáticamente, o puede seleccionar manualmente un valor. Esta pestaña muestra el mapeo final para los elementos de la plantilla y el modelo.

    ![Pestaña Asignación en la pestaña Cargar de la página Crear una nueva plantilla.](./media/BDM_overview_new_UI_import_41.jpg)

    > [!NOTE]
    > La asignación en la sección **Estructura de la plantilla** utiliza la coincidencia completa de las etiquetas o descripciones en la fuente de datos en el idioma del usuario y en el nombre de la celda en la plantilla.

6. Seleccione **Crear documento** para confirmar que desea crear una plantilla e iniciar el proceso de edición.

Para más información, vea [Resumen de gestión de documentos empresariales](er-business-document-management.md).

## <a name="upload-a-template-from-the-global-repository"></a>Cargar una plantilla desde el repositorio global

Este ejemplo muestra cómo usar el botón **Nuevo documento** en el espacio de trabajo **Gestión de documentos comerciales** para crear y editar una plantilla en una configuración de formato de ER proporcionado por Microsoft y ubicado en el repositorio Global. En este ejemplo, el proveedor activo es Contoso, que usa la configuración de formato ER proporcionada por Microsoft. Después de seleccionar **Nuevo documento**, la pestaña **Importar desde el repositorio global** en la página **Crear una nueva plantilla** muestra todas las plantillas de documentos comerciales que están almacenadas en el repositorio global pero que faltan en la instancia de finanzas actual. Después de seleccionar una plantilla, se importa desde el repositorio global a la instancia de Finanzas actual para crear una nueva copia editable. La plantilla editada se almacena en una nueva configuración del formato de ER que se genera automáticamente.

1. En el espacio de trabajo de **Gestión de documentos empresariales**, seleccione **Nuevo documento**.
2. Sobre la página **Crear una nueva plantilla**, en la ficha **Importar desde repositorio Global**, seleccione el documento que desea usar como plantilla y, a continuación, seleccione **Crear documento**.

    ![Importar desde la pestaña Repositorio global en la página Crear una nueva plantilla.](./media/BDM_overview_new_template22.png)

3. En el cuadro de mensaje, seleccione **Sí** para confirmar que desea importar el documento seleccionado del repositorio global a la instancia de Finanzas actual. Si se le solicita la autorización, siga las instrucciones en pantalla.
4. En el nuevo cuadro de diálogo, en el campo **Título**, cambie el título según lo requiera. El texto del título se usa para asignar un nombre a la nueva configuración del formato de ER que se crea automáticamente. La versión del borrador de esta configuración (**Copia de nota de carta de la colección (Excel)**) incluirá la plantilla editada y se usará para ejecutar este formato de ER para el usuario actual. La plantilla original no modificada de la configuración del formato básico de ER se usará para ejecutar este formato de ER para los otros usuarios.
5. En el campo **Nombre**, cambie el nombre de la primera revisión de la plantilla editable que se creará automáticamente.
6. En el campo **Comentario**, actualice los comentarios para la revisión de la plantilla editable que se creará automáticamente.
7. Seleccione **Aceptar** para confirmar el inicio del proceso de edición.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
