---
title: Configurar autenticación de servicio a servicio
description: Este artículo describe cómo configurar la autenticación de servicio a servicio en Microsoft Dynamics 365 Commerce para llamar de forma segura a las API de servicio para obtener calificaciones y opiniones.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: e3134d4ddb2e4f3d260e51d49e7399ff84e0d74a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279458"
---
# <a name="configure-service-to-service-authentication"></a>Configurar autenticación de servicio a servicio

[!include [banner](includes/banner.md)]

Este artículo describe cómo configurar la autenticación de servicio a servicio (S2S) en Microsoft Dynamics 365 Commerce para llamar de forma segura a las interfaces de programación de aplicaciones (API) de servicio para obtener calificaciones y opiniones.

Dynamics 365 Commerce ofrece [calificaciones y opiniones](ratings-reviews-overview.md) como una solución omnicanal. Esta solución permite el acceso a las API de servicio desde fuera de Commerce, de modo que se puedan realizar varias tareas. Estas tareas incluyen la importación de calificaciones y opiniones de su sistema externo a Commerce y la exportación de calificaciones y opiniones desde Commerce. Para permitir que Commerce llame de forma segura a las API del servicio de calificaciones y opiniones, primero debe configurar la autenticación S2S completando los procedimientos de este artículo.

## <a name="add-a-new-app-registration"></a>Agregar un nuevo registro de la aplicación

Antes de agregar un nuevo registro de aplicación, debe crear una aplicación utilizando [Azure Portal](https://portal.azure.com). Para registrar una aplicación en Azure Active Directory (Azure AD) y habilitar la autenticación, siga los pasos en [Usar Azure Active Directory con un conector personalizado en Power Automate](/connectors/custom-connectors/azure-active-directory-authentication).

Recopile los siguientes id. de Azure Portal. Necesitará estos id. en los pasos siguientes.

- Id. de la aplicación cliente
- Id. de directorio de cliente (inquilino)

Para agregar un nuevo registro de aplicación en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Inicio \> Revisiones \> Configuración**.
1. En **Autenticación de servicio a servicio (S2S)**, seleccione **Administrar**.

    ![Botón Administrar en la sección Autenticación de servicio a servicio (S2S) en el creador de sitios de Commerce.](media/Ratings-reviews-settings-service-to-service-authentication.png)

1. En el panel **Movimientos de la aplicación S2S** que aparece a la derecha, seleccione **Agregar un nuevo registro de la aplicación S2S**.
1. En el cuadro de diálogo **Agregar movimiento de la aplicación S2S**, especifique la información necesaria. Use los valores del registro de su aplicación de Azure.

    - **Nombre**: introduzca el nombre de su aplicación (por ejemplo, **Fabrikam App**).
    - **Id. de aplicación del cliente**: introduzca el id. de la aplicación (por ejemplo, **00000000-0000-0000-0000-000000000000**).
    - **Id. de directorio (inquilino)**: introduzca el id. del directorio (por ejemplo, **00000000-0000-0000-0000-000000000000**).

    ![Cuadro de diálogo Agregar movimiento de aplicación S2S en el generador de sitios de Commerce.](media/Ratings-reviews-settings-S2S-APP-entry.png)

1. Seleccione **Enviar**. El nombre de su aplicación debería aparecer en la lista en el panel **Movimientos de la aplicación S2S**.
1. Cierre el panel **Movimientos de la aplicación S2S**.
1. Seleccione **Guardar**.

## <a name="edit-an-existing-app-registration"></a>Editar un registro de aplicación existente

Para editar un registro de aplicación existente en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Inicio \> Revisiones \> Configuración**.
1. En **Autenticación de servicio a servicio (S2S)**, seleccione **Administrar**.
1. En el panel **Movimientos de la aplicación S2S**, seleccione el símbolo del lápiz junto al movimiento que desea editar.
1. Actualice los valores en los campos **Nombre**, **Id. de la aplicación del cliente** e **Id. de directorio (inquilino)** según sea necesario.
1. Seleccione **Enviar**.
1. Cierre el panel **Movimientos de la aplicación S2S**.
1. Seleccione **Guardar**.

## <a name="remove-an-existing-app-registration"></a>Eliminar un registro de aplicación existente

Para eliminar un registro de aplicación existente en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Inicio \> Revisiones \> Configuración**.
1. En **Autenticación de servicio a servicio (S2S)**, seleccione **Administrar**.
1. En el panel **Movimientos de la aplicación S2S**, seleccione el símbolo de la papelera junto al movimiento que desea eliminar. El movimiento se elimina de la lista.
1. Cierre el panel **Movimientos de la aplicación S2S**.
1. Seleccione **Guardar**.

## <a name="additional-resources"></a>Recursos adicionales

[Información general de clasificaciones y revisiones](ratings-reviews-overview.md)

[Optar por usar clasificaciones y revisiones de usuario](opt-in-ratings-reviews.md)

[Administrar calificaciones y opiniones](manage-reviews.md)

[Configurar calificaciones y opiniones](configure-ratings-reviews.md)

[Sincronizar clasificaciones de producto](sync-product-ratings.md)

[Habilitar la publicación manual de calificaciones y reseñas por parte de un moderador](manual-publish-rating-reviews.md)

[Importación y exportación de calificaciones y opiniones](import-export-reviews.md)

[P+F de clasificaciones y revisiones](ratings-reviews-faq.md) 
