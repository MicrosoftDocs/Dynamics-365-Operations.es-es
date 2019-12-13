---
title: Módulos y páginas de gestión de cuentas
description: Este tema cubre los módulos y las páginas de gestión de cuentas en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3986505a7e0e8d33d5b8ff2c06f493335731a8d9
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785399"
---
# <a name="account-management-pages-and-modules"></a>Módulos y páginas de gestión de cuentas

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema cubre los módulos y las páginas de gestión de cuentas en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

La gestión de cuentas hace referencia a un grupo de páginas que se usa para gestionar la información relacionada con cuentas del usuario en Dynamics 365 Commerce. Las páginas de la gestión de cuentas incluyen la página de aterrizaje de la gestión de cuentas, la página de perfil de usuario, la página de la dirección del usuario, la página del historial de pedidos, la página de detalles de pedidos, la página de fidelización y la página de la lista de deseos.

### <a name="account-management-landing-page"></a>Página de aterrizaje de gestión de cuentas

La página de aterrizaje de la gestión de cuentas utiliza los siguientes módulos:

- **Colocación de contenido**: Este módulo es un módulo de contenedor que contiene todos los módulos de la página de aterrizaje de la gestión de cuentas.
- **Elemento de bienvenida de la cuenta**: Este módulo se utiliza para proporcionar un mensaje de bienvenida en la página de gestión de cuentas. Incluye las propiedades del encabezado y el tamaño del icono. La propiedad **Tamaño de icono** define el ancho del módulo en el módulo de colocación de contenido. Los valores oscilan entre **1** y **12**, donde **12** representa el ancho total del contenedor de colocación de contenido.
- **Elemento de realización de pedidos de cuenta**: Este módulo se utiliza para proporcionar un resumen del número de pedidos que se han realizado por la cuenta del usuario. Incluye las propiedades del encabezado, el tamaño del icono y el vínculo "ver detalles". El vínculo “ver detalles” se debe configurar para redirigir a la página del historial de pedidos.
- **Elemento de colocación del perfil de cuenta**: Este módulo se utiliza para proporcionar un resumen del perfil de usuario. Incluye las propiedades del encabezado, el tamaño del icono y el vínculo "ver detalles". El vínculo “ver detalles” se debe configurar para redirigir a la página del perfil de usuario.
- **Elemento de lista de deseos de cuenta**: Este módulo se utiliza para proporcionar un resumen de los artículos de la lista de deseos del cliente. Por ejemplo, es posible que indique “Tiene 10 artículos en su lista de deseos.” Incluye las propiedades del encabezado, el tamaño del icono y el vínculo "ver detalles". El vínculo “ver detalles” se debe configurar para redirigir a la página de la lista de deseos.
- **Elemento de dirección de la cuenta**: Este módulo se utiliza para proporcionar un resumen de las direcciones del usuario. Por ejemplo, es posible que indique “Tiene 2 direcciones agregadas a su cuenta”. Incluye las propiedades del encabezado, el tamaño del icono y el vínculo "ver detalles". El vínculo “ver detalles” se debe configurar para redirigir a la página de dirección del usuario.
- **Elemento de fidelización de cuenta**: Este módulo se usa para mostrar y vincular a la información del programa de fidelización. Incluye las propiedades del encabezado, el tamaño del icono, el vínculo "ver detalles" y el vínculo "convertirse en un miembro". El vínculo “ver detalles” se debe configurar para redirigir a la página de fidelización. El vínculo “convertirse en un miembro” se debe configurar para redirigir a una página donde los usuarios puedan unirse al programa de fidelización.

### <a name="order-history-page"></a>Página de historial de pedidos

La página de historial de pedidos utiliza el módulo del historial de pedidos para mostrar todos los pedidos recientes que el usuario ha realizado.

### <a name="order-details-page"></a>Página de detalles del pedido

La página de detalles de pedido proporciona información detallada para cada pedido y se obtiene acceso a ella desde la página de historial de pedidos. Usa el módulo de detalles de pedido, que requiere que el id. de ventas o el id. de transacción recupere los detalles del pedido.

### <a name="user-profile-page"></a>Página de perfil de usuario

La página de perfil de usuario muestran los detalles de la cuenta de usuario, como el nombre y la dirección de correo electrónico del usuario. Permite usar el módulo del perfil de usuario. Aunque la dirección de correo electrónico no se pueda quitar, se puede editar.

### <a name="user-address-page"></a>Página de la dirección de correo electrónico del usuario

La página de la dirección del usuario muestra la lista de direcciones que están asociadas a la cuenta del usuario. El usuario proporcionó estas direcciones durante la finalización de la compra o las agregó directamente en esta página. El módulo de la dirección de usuario se utiliza para agregar y editar direcciones, establecer la dirección principal y representar las direcciones existentes en la página.

### <a name="wish-list-page"></a>Página de lista de deseos

La página de lista de deseos muestra los artículos que se han agregado a la lista de deseos del cliente. Usa el módulo de la lista de deseos para representar artículos de la lista de deseos.

### <a name="loyalty-page"></a>Página de fidelización

La página de fidelización permite a los clientes unirse a un programa de fidelización o, si ya son miembros del programa de fidelización, ver sus detalles de programa. También pueden ver los puntos que han obtenido y canjeado en transacciones recientes.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
