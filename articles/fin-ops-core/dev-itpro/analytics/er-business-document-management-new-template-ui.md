---
title: Interfaz de usuario estilo Microsoft Office en la Administración de documentos empresariales (contiene video)
description: Este tema explica cómo usar la nueva interfaz de usuario de documentos en la función de Administración de documentos empresariales del marco de informes electrónicos (ER).
author: v-anamir
ms.date: 04/12/2021
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
ms.openlocfilehash: b0c481e73daf74803d3582e4089e76dcd383e8a4
ms.sourcegitcommit: ef0dd4245fc499907ffe00e2a32f59a6cd96e45d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/18/2021
ms.locfileid: "7937565"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Interfaz de usuario estilo Microsoft Office en la Administración de documentos empresariales

[!include [banner](../includes/banner.md)]

La gestión de documentos empresariales aprovecha el marco de ER y permite a los usuarios empresariales editar plantillas de documentos empresariales mediante el servicio de Microsoft 365 o la aplicación de escritorio de Microsoft Office apropiada. Las ediciones pueden incluir cambios de diseño o nuevas implementaciones, o los usuarios pueden agregar marcadores de posición para incluir datos adicionales sin tener que cambiar el código fuente. Para obtener más información sobre cómo trabajar con la gestión de documentos empresariales, vea [Resumen de gestión de documentos comerciales](er-business-document-management.md).

La nueva interfaz de usuario (UI) es más clara y más cómoda de usar. El área **Documento empresarial** muestra solo las plantillas que están disponibles para el proveedor actual. En la interfaz de usuario anterior, la pestaña **Plantilla** incluía todas las plantillas que estaban disponibles para cualquier proveedor. También mostraba todas las plantillas que fueron creadas y editadas por cualquier usuario que tuviera el mismo rol.

Puede usar el botón **Nuevo documento** para crear y editar una plantilla en una configuración de formato de informes electrónicos (ER) proporcionada por otro proveedor. En el ejemplo de este tema, el proveedor es Microsoft. Alternativamente, puede crear una plantilla cargando su propia plantilla en formato Excel.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

El vídeo [Crear un nuevo documento comercial utilizando la gestión de documentos comerciales](https://youtu.be/gAIYl-mM_pw) (mostrado arriba) está incluido en la [lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Poner a disposición la nueva interfaz de usuario de documentos en la gestión de documentos empresariales

Para comenzar a utilizar la nueva interfaz de usuario de documentos en la gestión de documentos empresariales, debe activar la característica **Experiencia de interfaz de usuario similar a oficina para la gestión de documentos empresariales** en el espacio de trabajo **Administración de características**.

Siga estos pasos para activar esta función para todas las entidades jurídicas.

1. En el espacio de trabajo **Administración de características**, en la pestaña **Todo**, seleccione la característica **Experiencia de IU similar a oficina para la gestión de documentos empresariales** en la lista.
2. Seleccione **Habilitar ahora** para activar la característica seleccionada.
3. Actualice la página para obtener acceso a la característica nueva.

## <a name="edit-templates-that-are-owned-by-other-providers"></a>Editar plantillas propiedad de otros proveedores

1. En el espacio de trabajo de **Gestión de documentos empresariales**, seleccione **Nuevo documento**.

    ![Espacio de trabajo de la gestión de documentos empresariales.](./media/BDM_overview_new_template1.png)

2. En la pestaña **Seleccionar**, seleccione el documento para usar como plantilla y luego seleccione **Crear documento**.

    ![Cuadro de diálogo Documentos empresariales.](./media/BDM_overview_new_template2.png)

3. En el nuevo cuadro de diálogo, en el campo **Título**, cambie el título según lo requiera. El texto del título se usa para asignar un nombre a la nueva configuración del formato de ER que se crea automáticamente. La versión del borrador de esta configuración (**Copia de informe FTI de cliente (GER)**) incluirá la plantilla editada y se usará para ejecutar este formato de ER para el usuario actual. La plantilla original no modificada de la configuración del formato básico de ER se usará para ejecutar este formato de ER para los otros usuarios.
4. En el campo **Nombre**, cambie el nombre de la primera revisión de la plantilla editable que se creará automáticamente.
5. En el campo **Comentario**, actualice los comentarios para la revisión de la plantilla editable que se creará automáticamente.
6. Seleccione **Aceptar** para confirmar el inicio del proceso de edición.

    ![Cuadro de diálogo Creación de documentos.](./media/BDM_overview_new_template3.png)

El botón **Nuevo documento** se usa para crear y editar una plantilla en una configuración de formato ER proporcionada por otro proveedor. En el ejemplo, el proveedor es Microsoft. Cuando seleccione **Nuevo documento**, verá todas las plantillas que poseen los proveedores actuales y otros proveedores. Después de seleccionar la plantilla, se abrirá para editarla. La plantilla editada se almacenará en una nueva configuración del formato de ER que se genera automáticamente.

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a>Cargue una plantilla que use un formato de Excel existente
Siga estos pasos para proporcionar la información requerida antes de cargar una plantilla.

1. En el espacio de trabajo de **Gestión de documentos empresariales**, seleccione **Nuevo documento**.

    ![Espacio de trabajo de la gestión de documentos empresariales.](./media/BDM_overview_new_template1.png)
    
2. En la página **Crear una nueva plantilla**, en la pestaña **Subir**, en la pestaña **Plantilla**, seleccione **Navegar** para buscar y seleccionar el archivo de Excel que desea utilizar como plantilla. En la sección **Plantilla**, los campos **Título** y **Descripción** se completan automáticamente. Especifican el nombre y la descripción de la nueva configuración de formato ER que se crea automáticamente. Si es necesario, puede editar estos campos.
3. En la sección **Tipo de Documento**, en el campo **Nombre**, especifique el tipo de documento comercial. Este valor se utilizará para buscar la fuente de datos correcta (es decir, la configuración del modelo ER).

    ![Pestaña Plantilla.](./media/BDM_overview_new_UI_import_21.jpg)

4. En la pestaña **Fuente de datos**, en la ficha desplegable **Filtro**, seleccione **Aplicar filtro**. En la sección **Fuente de datos**, el campo **Nombre** se rellena automáticamente o puede seleccionar manualmente un valor. Puede utilizar el filtro para buscar el nombre de fuente de datos adecuado por nombre, descripción, código de país o región y tipo de documento comercial.

    ![Pestaña Origen de datos.](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > La ficha desplegable **Filtro** se utiliza para buscar la fuente de datos correcta (es decir, la configuración del modelo ER). Puede editar todos los campos de filtro para encontrar la fuente de datos más adecuada para el documento que está cargando.
    > 
    > Las condiciones de la ficha desplegable **Filtro** se utilizan como condiciones **O**.
    
5. En la pestaña **Asignación**, seleccione **Detectar automáticamente**. El campo **Definición raíz** se rellena automáticamente, o puede seleccionar manualmente un valor. Esta pestaña muestra el mapeo final para los elementos de la plantilla y el modelo.

    ![Pestaña Asignación.](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > La asignación en la sección **Estructura de la plantilla** utiliza la coincidencia completa de las etiquetas o descripciones en la fuente de datos en el idioma del usuario y en el nombre de la celda en la plantilla.

6. Seleccione **Crear documento** para confirmar que desea crear una plantilla e iniciar el proceso de edición.

Para más información, vea [Resumen de gestión de documentos empresariales](er-business-document-management.md).

Si no hay un proveedor de informes electrónicos, puede crear uno. Si no hay un proveedor activo, puede seleccionar activar uno.

- Para crear un proveedor, cambie el nombre del proveedor en el campo **Nombre**, actualice la dirección de Internet del nuevo proveedor en el campo **Dirección de Internet** y seleccione **Aceptar** para confirmar.

    ![Crear nuevo proveedor en BDM.](./media/bdm_create_provider.png)
    
- Para activar el proveedor existente, elija el nombre del proveedor en el campo **Proveedor de configuración** y seleccione **Aceptar** para configurar el proveedor como activo.

    ![Activar proveedor en BDM.](./media/bdm_choose_provider.png)

> [!NOTE]
> Cada plantilla BDM hace referencia al proveedor como autor de la configuración. Es por eso que se requiere un proveedor activo para la plantilla.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
