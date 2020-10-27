---
title: Trabajar con fragmentos
description: Este tema describe por qué, cuándo y cómo usar fragmentos en Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b3e3299388190f03e761591a0c23164b705db9e8
ms.sourcegitcommit: f16db76c1c235dfa445b50614bcee9219782d6dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2020
ms.locfileid: "3961667"
---
# <a name="work-with-fragments"></a>Trabajar con fragmentos 

[!include [banner](includes/banner.md)]

Este tema describe por qué, cuándo y cómo usar fragmentos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Los fragmentos permiten una experiencia de creación centralizada para configuraciones de módulos que se deben volver a utilizar en el sitio. Por ejemplo, los encabezados, los pies de página y los banners a menudo se configuran como fragmentos, ya que se comparten entre muchas páginas. Puede pensar en fragmentos como páginas web en miniatura que se pueden insertar en otras páginas del sitio. Los fragmentos tienen su propio ciclo de vida. Es decir, se crean, se hace referencia a ellas, se actualizan y se eliminan como entidades independientes en las herramientas de creación.

Una vez que se configuran los fragmentos, se pueden usar en cualquier lugar donde se puedan usar los módulos en su estructura de sitio. Se puede hacer referencia a fragmentos en páginas, diseños, plantillas y otros fragmentos.

> [!NOTE]
> Los fragmentos se pueden anidar hasta en siete niveles de profundidad dentro de otros fragmentos.

Por ejemplo, si desea promocionar un evento de temporada en muchas páginas de nuestro sitio, puede usar un fragmento. El primer paso en el proceso de crear un fragmento nuevo es seleccionar el tipo de módulo desde el que deseas empezar. Para este ejemplo, puede crear el fragmento desde un módulo de elemento principal.

> [!NOTE]
> Los fragmentos se pueden crear desde cualquier tipo de módulo.

A continuación puede configurar el fragmento de elemento principal con su contenido promocional específico. También puede localizarlo según sea necesario. El nuevo fragmento de elemento principal independiente se puede consumir a continuación como módulo preconfigurado a través del sitio. Puede agregarlo fácilmente a plantillas, a páginas específicas o a otros fragmentos que pueden contener módulos de elementos principales.

Todos los lugares donde se agrega el fragmento son referencias al fragmento de elemento principal central de héroe que ha creado. Si publica cambios en el fragmento, estos cambios se reflejan inmediatamente en todos los lugares donde se hace referencia al fragmento en el sitio. Por lo tanto, los fragmentos ofrecen una manera potente y eficaz de volver a usar y administrar centralmente las configuraciones de módulo en un sitio. Al usarlos de manera eficaz, pueden aumentar significativamente la agilidad y ayudar a reducir el coste que está asociado a la administración del contenido del sitio.

La ilustración siguiente muestra cómo se pueden usar los fragmentos para centralizar la creación de las configuraciones de módulo compartidas en un sitio de comercio electrónico.

![Una ilustración que muestra cómo se pueden usar los fragmentos para centralizar la creación de las configuraciones de módulo compartidas en un sitio de comercio electrónico](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a>Crear un fragmento

Puede crear un nuevo fragmento o guardar una configuración de módulo existente como fragmento.

### <a name="save-an-existing-module-configuration-as-a-fragment"></a>Guardar una configuración de módulo existente como fragmento

Para convertir un módulo configurado anteriormente en un fragmento reutilizable, siga estos pasos.

1. Abra una página o una plantilla que contenga el módulo que desea convertir en un fragmento.
1. En el panel de contorno a la izquierda o directamente en el generador de páginas visual, seleccione el módulo configurado previamente.
1. Seleccione los puntos suspensivos (**...**) junto al módulo en el panel de contorno o en la barra de herramientas del módulo en el generador de páginas visual. 
1. Seleccione **Compartir como fragmento de página**. 
1. En el cuadro de diálogo **Guardar como fragmento de página**, especifique un nombre para el fragmento.
1. Seleccione **Aceptar** para guardar la configuración del módulo como fragmento que se pueda agregar a otras páginas.

La siguiente imagen muestra cómo guardar la configuración de un módulo como fragmento.

![Una captura de pantalla de cómo guardar la configuración de un módulo como un fragmento](./media/save-as-fragment.png)

### <a name="create-a-new-fragment"></a>Crear un fragmento nuevo

Para crear un nuevo fragmento, siga estos pasos.

1. En el panel de navegación de la izquierda, seleccione **Fragmentos**.
1. Seleccione **Nuevo fragmento de página**. Aparece un cuadro de diálogo que muestra todos los tipos de módulos disponibles. Como se mencionó anteriormente, los fragmentos se pueden crear a partir de cualquier tipo de módulo.
1. Seleccione un tipo de módulo para su fragmento.

La siguiente imagen muestra dónde crear un nuevo fragmento.

![Una captura de pantalla de dónde crear un nuevo fragmento](./media/fragment-nav-menu.png)

> [!TIP]
> Al seleccionar un tipo de módulo de contenedor genérico, obtiene la máxima flexibilidad cuando tiene que actualizar y configurar el fragmento posteriormente.

## <a name="add-remove-or-edit-fragments-on-a-page"></a>Agregar, eliminar o editar fragmentos en una página

Los siguientes procedimientos describen cómo agregar, quitar y editar fragmentos.

### <a name="add-a-fragment"></a>Agregar un fragmento

Para agregar un fragmento a una página, siga estos pasos.

1. En el panel de esquema de la izquierda o directamente en el generador de páginas visual, seleccione un contenedor o una franja a la que se pueda agregar módulos secundarios.
1. En el panel en línea, seleccione los puntos suspensivos (**...**) junto al nombre del contenedor o la franja.  Alternativamente, si usa el generador de páginas visual, seleccione el símbolo más (**+**).  
1. Seleccione **Agregar fragmento**.

    ![Una captura de pantalla de cómo agregar un fragmento existente a un franja o contenedor](./media/add-fragment.png)
 
    > [!NOTE]
    > Si el contenedor o la franja no admiten nuevos módulos secundarios, la opción **Agregar fragmento** no está disponible.
    
1. En el cuadro de diálogo **Agregar fragmento**, busque y seleccione un fragmento para agregarlo. Si no se muestran fragmentos disponibles, es posible que tenga que crear primero un fragmento de un tipo de módulo que la franja o el contenedor seleccionado admita.
1. Seleccione el fragmento que desee para agregarlo a la franja o al contenedor seleccionado de su página.

    ![Una captura de pantalla de la ventana modal del selector de fragmentos](./media/fragment-picker.png)

> [!NOTE]
> Los módulos que se permiten en un contenedor o una franja se definen por plantilla de la página o las propias definiciones de los módulos.

### <a name="remove-a-fragment"></a>Eliminar un fragmento

Para eliminar un fragmento de una franja o un contenedor de una página, siga estos pasos.

1. En el panel de esquema de la izquierda, seleccione el botón de puntos suspensivos (**...**) que se encuentra junto al fragmento que se va a eliminar y, a continuación, seleccione el símbolo de papelera.  Alternativamente, puede seleccionar el fragmento en el generador de páginas visual y seleccionar el símbolo de la papelera en la barra de herramientas del fragmento.
1. Cuando se le pida confirmar que desea quitar el fragmento, seleccione **Aceptar**.

> [!NOTE]
> Al quitar un fragmento de una página, solo quitará la referencia a él de esa página. **No** elimina el fragmento del sitio. Para eliminar fragmentos del sitio, debe usar la interfaz de usuario (IU) del inspector de fragmentos. Puede eliminar fragmentos de un sitio solo si no se hace referencia a ellos actualmente por ninguna página o plantilla u otros fragmentos.

### <a name="edit-a-fragment"></a>Editar un fragmento

Para editar fragmentos, debe usar la interfaz de usuario del editor de fragmentos. Esta restricción es por diseño. Ayuda garantizar que los autores no confunden el proceso de editar los módulos para una página determinada por el proceso de editar fragmentos que se pueden compartir entre varias páginas.

Para editar un fragmento, siga estos pasos.

1. En el panel de navegación de la izquierda, seleccione **Fragmentos**.
1. En **Fragmentos**, seleccione el fragmento que se editará.
1. Edite la estructura y las propiedades del módulo del fragmento según sea necesario. El proceso es similar al que se usa para editar módulos en la vista del editor de páginas.

También puede editar un fragmento seleccionándolo en una página, en una plantilla o en un fragmento principal y, a continuación, seleccionando **Editar fragmento** en el panel de propiedades de la derecha.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de plantillas y diseños](templates-layouts-overview.md)

[Trabajar con plantillas](work-with-templates.md)

[Trabajar con diseños predefinidos](work-with-layouts.md)

[Trabajar con grupos de publicación](publish-groups.md)
