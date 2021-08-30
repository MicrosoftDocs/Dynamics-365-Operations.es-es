---
title: Trabajar con diseños predefinidos
description: En este tema se describe cómo trabajar con diseños preestablecidos en Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0f6effd4dda669041a269d568bd39beda607a2bcc05c65e40bb76c6f1d02cd5e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775321"
---
# <a name="work-with-preset-layouts"></a>Trabajar con diseños predefinidos

[!include [banner](includes/banner.md)]

En este tema se describe cómo trabajar con diseños preestablecidos en Microsoft Dynamics 365 Commerce.

Antes de completar los procedimientos de este tema, asegúrese de leer [Diseños personalizados y preestablecidos](templates-layouts-overview.md#preset-and-custom-layouts). Para una visión general, consulte [Visión general de plantillas y diseños](templates-layouts-overview.md).

## <a name="create-a-new-preset-layout"></a>Creación de un nuevo diseño preestablecido

Existen dos métodos para crear un diseño preestablecido. Puede guardar un diseño personalizado existente como nuevo diseño preestablecido o bien, crear un diseño preestablecido a partir de cero.

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a>Crear un diseño preestablecido de un diseño personalizado existente

Para crear un diseño preestablecido de un diseño personalizado existente, siga estos pasos.

1. Abra una página existente que no use actualmente un diseño preestablecido, y que tiene una estructura de módulo que desee volver a usar para otras páginas del sitio.
1. Seleccione **Editar** para comprobar la página.
1. Seleccione **Guardar como nuevo diseño**. Aparece el cuadro de diálogo **Guardar como nuevo diseño**.
1. Especifique un nombre y una descripción para su diseño preestablecido. Los valores que especifique se mostrarán a otros autores cuando creen páginas nuevas desde su diseño o pasen a él. Por lo tanto, especifique valores que serán útiles para autores de página.
1. Seleccione **Aceptar**.

El diseño preestablecido estará ahora disponible al crear páginas nuevas o seleccionar un diseño diferente para una página en la misma jerarquía de plantilla.

> [!TIP]
> Para ver rápidamente si una página determinada está enlazada actualmente a un diseño preestablecido, seleccione la página en la vista de lista de páginas e inspeccione los metadatos de diseño en el panel de propiedades de la derecha.

### <a name="create-a-new-preset-layout"></a>Creación de un nuevo diseño preestablecido

Para crear un diseño preestablecido a partir de cero, siga estos pasos.

1. En el panel de navegación de la izquierda, seleccione **Diseños**.
1. Seleccione **Nuevo diseño**. Aparece el cuadro de diálogo **Nuevo diseño**.
1. Seleccione la plantilla que se usará para su diseño preestablecido.
1. Especifique un nombre y una descripción para su diseño preestablecido. Los valores que especifique se mostrarán a otros autores cuando creen páginas nuevas desde su diseño o pasen a él. Por lo tanto, especifique valores que serán útiles para autores de página.
1. Seleccione **Aceptar** para crear el nuevo diseño preestablecido y abrir el editor de diseño.
1. En el editor de diseño, agregue y configure módulos mediante el árbol de esquema de la izquierda y el panel de propiedades de la derecha. (El proceso es similar al de agregar y configurar módulos para una plantilla en el editor de plantillas.) La organización de los módulos y cualquier configuración predeterminada bloqueada se convertirá en la configuración de módulo centralizada para las páginas que usan este diseño preestablecido.

## <a name="modify-a-preset-layout"></a>Modificar un diseño preestablecido

Para modificar un diseño preestablecido, siga estos pasos.

1. En el panel de navegación de la izquierda, seleccione **Diseños**.
1. En el editor de diseño, en el árbol de esquema de la izquierda, seleccione el módulo que desea modificar. Luego siga cualquiera de estos pasos:

    - Para subir o bajar un módulo dentro de su elemento principal, seleccione los puntos suspensivos (**...**) para el módulo y, a continuación, seleccione **Subir** o **Bajar**.
    - Para cambiar la configuración predeterminada de un módulo, use el panel de propiedades para especificar valores predeterminados y bloquearlos opcionalmente para todas las páginas en sentido descendente.
    - Para agregar nuevos módulos o fragmentos a los módulos de contenedor, seleccione el botón de puntos suspensivos y después seleccione **Agregar módulo** o **Agregar fragmento**.
    - Para quitar un módulo del diseño, seleccione los puntos suspensivos y, a continuación, seleccione **Eliminar**.

## <a name="change-a-preset-layout-theme"></a>Cambiar un tema de diseño preestablecido

Una práctica típica es establecer un tema predeterminado para todas las páginas que utilicen un diseño preestablecido.

Para establecer o cambiar el tema para todas las páginas secundarias que utilicen su diseño preestablecido, siga estos pasos.

1. En el editor de diseño, en el árbol de esquema de la izquierda, seleccione el módulo de contenedor de páginas. (Normalmente, este módulo es el segundo nodo y se llama **Página predeterminada**.)
1. En el panel de propiedades de la derecha, en el campo **Tema**, seleccione un tema.

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a>Guardar, proteger, obtener una vista previa y publicar un diseño preestablecido

Para guardar y proteger su diseño preestablecido, siga estos pasos.

1. Seleccione **Guardar** en la parte superior del editor de diseño. Los cambios guardados no afectan a las páginas en sentido descendente hasta que se protegen.
1. Seleccione **Finalizar edición**. Sus cambios son ahora detectables para flujos de trabajo en sentido descendente.

Para obtener una vista previa de los cambios, abra una página existente que utilice el diseño preestablecido o cree una nueva página a partir del diseño.

Cuando haya obtenido una vista previa de los cambios para su diseño preestablecido, siga uno de estos pasos para publicar el diseño en el sitio activo:

* Vaya a **Diseños**, seleccione el diseño y, a continuación, **Publicar**.
* Seleccione el nombre del diseño para abrir el editor de diseño y después seleccione **Publicar**.
* Publique una página que haga referencia al diseño sin publicar. El diseño se publicará automáticamente.

> [!WARNING]
> Varias páginas pueden hacer referencia a diseños preestablecidos. Al publicar un diseño preestablecido, tenga en cuenta que puede afectar al diseño de varias páginas.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de plantillas y diseños](templates-layouts-overview.md)

[Trabajar con plantillas](work-with-templates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
