---
title: Editar guías y plantillas de incorporación en Dynamics 365 Talent - Onboard
description: Este tema explica cómo agregar actividades y otra información a las guías y las plantillas de incorporación en Microsoft Dynamics 365 Talent - Onboard.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7803c7cd2c58b8544d2c8dd711c295d6882f9fca
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010807"
---
# <a name="edit-onboarding-guides-and-templates"></a>Editar guías y plantillas de incorporación

[!include [banner](includes/banner.md)]

Después de crear una guía o una plantilla de incorporación en Microsoft Dynamics 365 Talent: Onboard, debes agregar una introducción, actividades, contactos, y recursos. Onboard le permite incluir el contenido de gran riqueza en sus guías de incorporación, incluidos:

- Vídeos de YouTube
- Presentaciones de Microsoft Sway
- Aplicaciones de Microsoft PowerApps
- Vídeos de Microsoft Stream
- Formularios de Microsoft Forms
- Iframes que contienen contenido Web

## <a name="edit-introductions-or-activities-imported-from-a-template"></a>Editar introducciones o actividades importadas desde una plantilla

Si crea una guía de incorporación a partir de una plantilla, o si importa actividades desde una plantilla a otra, observará un botón **Bloquear** en las actividades importadas. Se denominan *actividades administradas*.

[![Actividades administradas](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)

Cuando selecciona una actividad administrada, puede ver la plantilla de origen en la parte superior de la actividad.

[![Origen de la actividad administrada](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)

Si modifica una actividad en una plantilla, Onboard insertará los cambios en todas las plantillas y guías no enviadas que se crearon a partir de esa plantilla. Si selecciona una guía no enviada basada en una plantilla que editó y después selecciona la pestaña **Actividades** en la Guía, verá un aviso que la guía ha cambiado. Para rechazar la notificación, seleccione **Aceptar**. 

[![Cambiar notificación](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)

Se verá un punto negro junto a las actividades actualizadas.

[![Actividad cambiada](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)

No puede editar actividades administradas fuera de la plantilla original, a menos que sea para agregar el usuario asignado, la fecha de vencimiento, u otra información en la sección derecha de la actividad.

Si desea editar una actividad administrada, o si no desea que una actividad reciba actualizaciones de la plantilla de donde vino, seleccione el botón **Bloquear** para dicha actividad. El botón **Bloquear** desaparecerá. La actividad ya no será gestionada por plantilla original, y ya no recibirá actualizaciones de esa plantilla. Las actualizaciones que realice en una actividad no afectarán a la plantilla original.

Si elimina una actividad de una guía e introduce cambios de la plantilla de esa guía, la actividad seguirá eliminada en la Guía.

> [!NOTE]
> Los contactos y los recursos no se administran con plantillas. Además, hay secciones que no se gestionan, por lo que si desea agregar o editar una sección de una plantilla, los cambios no se insertarán en ninguna guía o plantilla que utilice esa plantilla.
> 
> Si agrega nuevas actividades a una plantilla, las nuevas actividades se insertan a las guías y las plantillas en función de dicha plantilla, y las nuevas actividades se muestran en la parte superior.

## <a name="import-activities-from-another-template"></a>Importar actividades de otra plantilla

Puede importar actividades de una o varias plantillas en una guía o una plantilla.

1. Seleccione la plantilla o guía que se desea editar.

2. Seleccione la pestaña **Actividades**.

3. Seleccione la pestaña **Importar** en la sección de la derecha.

   [![Importar Actividades](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)

4. Para obtener una vista preliminar de las tareas de una nueva ficha en su explorador, seleccione el botón **Abrir en ficha nueva** en cualquier plantilla.

   [![Importar Actividades](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)

5. Arrastre y suelte la plantilla deseada al lugar de la plantilla de la Guía donde desea que las actividades aparezcan. Continúe editando la guía o plantilla.

Las actividades importadas contendrán un botón **Bloquear**, que indica que esas actividades son administradas por la plantilla desde la que importó. Cuando realiza cambios en la plantilla que importó, dichas actividades se actualizarán en la plantilla desde la que importó. Sin embargo, los cambios no se insertarán automáticamente a ninguna guía creada a partir de la plantilla desde la que importó.

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a>Introducir cambios de una plantilla a otras plantillas o guías

Si modifica una plantilla que contiene actividades que se usan en otras plantillas o guías, debe insertar los cambios si desea que aparezcan en las otras plantillas o guías.

Si no está seguro de si las actividades de la plantilla se utilizan en otras plantillas o guías, seleccione la pestaña **Utilizada en** para ver dónde aparecen las actividades.

   [![Ver donde se usan actividades de guías y plantillas](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)

Para insertar los cambios:

1. Guarda los cambios seleccionando el botón **Guardar**. Si no lo hace, se le solicitará que guarde los cambios en el paso siguiente.

2. Seleccione **Insertar estos cambios**.

   
## <a name="add-or-edit-an-introduction"></a>Agregar o editar una introducción

1. En la pestaña **Introducción**, escriba un título para la guía y un mensaje de apertura. Para utilizar el texto de muestra, seleccione **Usar este mensaje**.

    [![Ficha de presentación en una plantilla de Onboard](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)

2. Use los botones de formato para llamar a un texto según sea necesario, o agregar imágenes o vínculos.
3. Seleccione **Guardar** para guardar el trabajo.

## <a name="add-or-edit-activities"></a>Agregar o Editar actividades

1. En la pestaña **Actividades**, arrastre elementos de la derecha al área de edición.
2. Para organizar la guía en secciones, arrastre el elemento **Nueva sección** al área de edición y escriba un nombre y una descripción opcional para la sección.

    ![[Agregar una nueva sección a un manual o una plantilla de incorporación](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. Para agregar actividades para que el nuevo contratado las complete, arrastre el elemento **Nueva actividad** al área de edición y escriba un nombre y una descripción para la actividad.

    ![[Agregar una nueva actividad a un manual o una plantilla de incorporación](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. Agregue contenido enriquecido a la guía de incorporación:

    - Para agregar un vídeo de YouTube, arrastre el elemento **YouTube** al área de edición, especifique un nombre y una descripción para la actividad, e indique la URL del vídeo de YouTube.
    - Para agregar una presentación o un boletín de Sway, arrastre el elemento **Sway** al área de edición, introduzca un nombre y una descripción de la actividad, y especifique la dirección URL incrustada para la presentación o la hoja de Sway.
    - Para agregar una aplicación de PowerApps, arrastre el elemento **PowerApps** al área de edición, especifique un nombre y una descripción para la actividad, y seleccione la aplicación de PowerApps o especifique el identificador de la aplicación de PowerApps.
    - Para agregar un vídeo de Microsoft Stream, arrastre el elemento **Microsoft Stream** al área de edición, especifique un nombre y una descripción para la actividad, e indique la URL del vídeo de Microsoft Stream.
    - Para agregar un formulario de Microsoft Forms, arrastre el elemento **Microsoft Forms** al área de edición, especifique un nombre y una descripción para la actividad, escriba la dirección URL del formulario de Microsoft Forms y especifique el tamaño del área de visualización.
    - Para agregar un iframe que contenga contenido web, arrastre el elemento de **contenido Web (iframe)** al área de edición, especifique un nombre y una descripción para la actividad, escriba la dirección URL del contenido web y especifique el tamaño del área de visualización.

    ![[Agregar contenido enriquecido a un manual o una plantilla de incorporación](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. Opcional: En el área en la parte derecha de cada actividad, asigne la actividad a una persona o a un rol concretos, agregue una fecha de vencimiento y una persona de contacto, y asígnele un color de categoría. Al asignar una actividad a una persona o rol, una tarea se crea para cada usuario. Esta tarea aparece en el menú **Tareas** en Onboard.

    [![Asignación de una actividad en una guía o una plantilla de incorporación](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)

3. Seleccione **Guardar** para guardar el trabajo.

Para eliminar una actividad o una sección, seleccione el botón **Eliminar** (el símbolo de bote de residuos) en la esquina superior derecha de la actividad o de la sección.

Para reorganizar las actividades y las secciones, arrástrelas a una nueva ubicación.

## <a name="add-or-edit-contacts"></a>Agregar o Editar contactos

Puede agregar personas de contacto que pueden ayudar al nuevo contratado a tener éxito desde el primer día. Estos contactos se pueden reclutadores, compañeros de equipo, compañeros de incorporación, mentores, administraciones, y personal de soporte de TI.

1. En la pestaña **Contactos**, seleccione **Nuevo contacto**.
2. En el cuadro de diálogo **Agregar miembro de equipo**, especifique el nombre o la dirección de correo electrónico de la persona de contacto, especifique una breve descripción que explique cómo la persona de contacto puede ayudar al nuevo contratado, y después seleccione **Agregar**. 

    ![[Agregar contactos enriquecidos a un manual o una plantilla de incorporación](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    Como alternativa, puede seleccionar uno o varios contactos en **Sugerencias**.

3. Seleccione **Guardar** para guardar el trabajo.

Para eliminar un contacto, seleccione el botón **Eliminar** (el símbolo de bote de residuos) a la derecha del contacto.

Para editar un contacto, seleccione el botón **Editar** (el símbolo de lápiz) a la derecha del contacto.

## <a name="add-or-edit-resources"></a>Agregar o Editar recursos

Puede agregar archivos, mapas, y vínculos útiles a la sección **Recursos** de la guía de incorporación.

1. En la pestaña **Recursos**, seleccione **Nuevo recurso**.
2. Siga uno de estos pasos:

    - Para agregar un archivo, seleccione la pestaña **Archivo**, y arrastre el archivo en el área designada. (De forma alternativa, haga clic en cualquier lugar de dicha área para buscar el archivo en su equipo, o seleccione **Examinar OneDrive**). Escriba un nombre para el archivo y, a continuación, seleccione **Agregar**.
    - Para agregar un vínculo, seleccione la pestaña **Vínculo**, especifique un nombre y la dirección del vínculo y, a continuación, seleccione **Agregar**.
    - Para agregar un mapa, seleccione la pestaña **Mapa**, especifique un nombre y la dirección del mapa y, a continuación, seleccione **Agregar**. Onboard incluirá un mapa de la dirección que especifique.

    ![[Agregar un recurso a un manual o una plantilla de incorporación](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. Seleccione **Guardar** para guardar el trabajo.

Para eliminar un recurso, seleccione el botón **Eliminar** (el símbolo de bote de residuos) a la derecha del recurso.

Para editar un contacto, seleccione el botón **Editar** (el símbolo de lápiz) a la derecha del recurso.

## <a name="next-steps"></a>Pasos siguientes

- [Compartir contenido con otros trabajadores](./onboard-share-template.md)
- [Ver el estado de las tareas y los empleados que se incorporan](./onboard-view-status.md)
- [Crear equipos de contratación en Onboard](./onboard-create-team.md)

### <a name="see-also"></a>Consulte también

- [Probar o comprar la aplicación Onboard](https://dynamics.microsoft.com/talent/onboard/)
- [Novedades](./whats-new.md)
- [Notas de la versión](https://docs.microsoft.com/business-applications-release-notes/index)
- [Obtener soporte](./talent-support.md)
