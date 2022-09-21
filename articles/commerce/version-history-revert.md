---
title: Ver el historial de versiones para revertir páginas y fragmentos
description: Este artículo describe cómo ver el historial de versiones de una página o fragmento y volver a una versión anterior en el generador de sitios de Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 06/21/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: c4d78103a3c08ee4052290fccf6750aba7eecf4a
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474109"
---
# <a name="view-version-history-to-revert-pages-and-fragments"></a>Ver el historial de versiones para revertir páginas y fragmentos

[!include [banner](includes/banner.md)]

Este artículo describe cómo ver el historial de versiones de una página o fragmento y volver a una versión anterior en el generador de sitios de Microsoft Dynamics 365 Commerce.

El generador de sitios de Commerce le permite ver el historial de versiones de una página o fragmento y volver a una versión anterior específica de un documento si es necesario. Mientras un documento está abierto, puede seleccionar **Mostrar historial** en la barra de comandos para abrir un cuadro de diálogo **Historial de versiones**, donde la pestaña **Versión** enumera el historial de todas las versiones y guarda las actividades para la página o el fragmento. Luego puede seleccionar una versión anterior del documento en la lista, obtener una vista previa y restaurarla como la versión actual. La pestaña **Actividad** del cuadro de diálogo enumera el historial de actividad completo del documento, incluidos todos los eventos de guardar, publicar y cancelar la publicación.

> [!NOTE]
> Se crea una nueva versión de un documento cada vez que un autor del sitio realiza cambios y luego selecciona **Edición terminada** para el documento 

Para ver el historial de versiones de una página o fragmento y volver a una versión anterior, siga estos pasos.

1. En el generador de sitios, abra la página o el fragmento del que desea ver el historial de versiones.
1. En la barra de comandos, seleccione **Mostrar historial**.

    ![Botón Mostrar historial.](./media/version-history-1.png)

1. En el cuadro de diálogo **Historial de versiones**, en la pestaña **Versión**, seleccione una versión anterior del documento. El panel de propiedades de la derecha muestra una vista previa en miniatura de la versión seleccionada e información sobre quién la modificó y cuándo.

    ![Vista de lista del historial de versiones.](./media/version-history-2.png)

1. Para ver una vista previa completamente procesada de la versión seleccionada del documento, seleccione **Vista previa**. Para cerrar la vista previa y volver al cuadro de diálogo **Historial de versiones**, seleccione **Salir de vista previa**.
1. Para restaurar una versión anterior de un documento, selecciónelo en la lista de la pestaña **Versión** y, a continuación, seleccione **Restaurar**. Aparece un cuadro de mensaje **Restaurar versión \<version number\>** que le solicita que confirme la acción de restauración. 

    ![Botón Restaurar y cuadro de mensaje de confirmación.](./media/version-history-3.png)

1. Para continuar con la acción de restauración, seleccione **Restaurar**. El generador de sitios se actualiza y muestra la versión restaurada de la página o el fragmento.
1. Para publicar la versión restaurada, seleccione **Finalizar edición** y luego seleccione **Publicar**.
