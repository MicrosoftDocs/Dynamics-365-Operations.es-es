---
title: Módulos y páginas de gestión de cuentas
description: Este artículo cubre los módulos y las páginas de gestión de cuentas en Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 2db9a1218802234297e9d027691e5887d6a5c808
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274465"
---
# <a name="account-management-pages-and-modules"></a>Módulos y páginas de gestión de cuentas

[!include [banner](includes/banner.md)]

Este artículo cubre los módulos y las páginas de gestión de cuentas en Microsoft Dynamics 365 Commerce.

La gestión de cuentas hace referencia a un grupo de páginas que se usa para gestionar la información relacionada con cuentas del usuario en Dynamics 365 Commerce. Las páginas de la gestión de cuentas incluyen la página de aterrizaje de la gestión de cuentas, la página de perfil de usuario, la página de la dirección del usuario, la página del historial de pedidos, la página de detalles de pedidos, la página de fidelización y la página de la lista de deseos.

### <a name="account-management-landing-page"></a>Página de aterrizaje de gestión de cuentas

La página de aterrizaje de la gestión de cuentas utiliza los siguientes módulos:

- **Contenedor**: todos los módulos de página de aterrizaje de administración de cuentas deben colocarse dentro de un contenedor. 
- **Ventana de bienvenida de cuenta**: este módulo se usa para proporcionar un mensaje de bienvenida en la página de administración de cuentas. Incluye propiedades para el encabezado.
- **Ventana genérica de cuenta**: este módulo se puede utilizar para proporcionar encabezados y vínculos a páginas de administración de cuentas, como las páginas "Historial de pedidos" o "Mi perfil". El módulo de ventana genérica se puede utilizar para configurar una ventana para cualquier página. En Fabrikam, este módulo se utiliza para los vínculos de página "Historial de pedidos" y "Mi perfil" en la página de aterrizaje de administración de cuentas.
- **Ventana de lista de deseos de cuenta**: este módulo se utiliza para proporcionar un resumen de los artículos de la lista de deseos del cliente. Por ejemplo, es posible que indique “Tiene 10 artículos en su lista de deseos.” Incluye las propiedades del encabezado y el vínculo "Ver detalles". El vínculo "Ver detalles" se debe configurar para redirigir a la página de la lista de deseos. 
- **Ventana de dirección de la cuenta**: este módulo se utiliza para proporcionar un resumen de las direcciones del usuario. Por ejemplo, es posible que indique “Tiene 2 direcciones agregadas a su cuenta”. Incluye las propiedades del encabezado y el vínculo "Ver detalles". El vínculo "Ver detalles" se debe configurar para redirigir a la página de dirección del usuario.
- **Ventana de fidelización de cuenta**: este módulo se usa para mostrar información del programa de fidelización y vincularla. El mosaico tiene dos estados: un estado muestra vínculos para unirse a un programa de fidelización si el usuario aún no es miembro. El otro estado muestra vínculos para ver la página de detalles de fidelización cuando el usuario ya es miembro. Las propiedades incluyen el encabezado, el vínculo "Registrarse" y el vínculo "Ver fidelización". El vínculo "Ver fidelización" se debe configurar para redirigir a la página de fidelización. El vínculo “Registrarse” se debe configurar para redirigir a una página donde los usuarios puedan unirse al programa de fidelización. 

### <a name="order-history-page"></a>Página de historial de pedidos

La página de historial de pedidos utiliza el módulo del historial de pedidos para mostrar todos los pedidos recientes que el usuario ha realizado.

### <a name="order-details-page"></a>Página de detalles del pedido

La página de detalles de pedido proporciona información detallada para cada pedido y se obtiene acceso a ella desde la página de historial de pedidos. Usa el módulo de detalles de pedido, que requiere que el id. de ventas o el id. de transacción recupere los detalles del pedido.

### <a name="my-profile-page"></a>Página Mi perfil

La página Mi perfil muestra los detalles del perfil de la cuenta del usuario mediante el módulo de perfil de la cuenta. La página muestra la dirección de correo electrónico asociada con la cuenta del usuario, así como las preferencias configuradas para la cuenta. Si configura atributos de cliente personalizados, una sección de "Información adicional" también mostrará esos atributos. Los usuarios pueden editar su nombre, preferencias o información adicional (si está disponible).

### <a name="user-address-page"></a>Página de la dirección de correo electrónico del usuario

La página de la dirección del usuario muestra la lista de direcciones que están asociadas a la cuenta del usuario. El usuario proporcionó estas direcciones durante la finalización de la compra o las agregó directamente en esta página. El módulo de la dirección de usuario se utiliza para agregar y editar direcciones, establecer la dirección principal y representar las direcciones existentes en la página.

### <a name="wish-list-page"></a>Página de lista de deseos

La página de lista de deseos muestra los artículos que se han agregado a la lista de deseos del cliente. Usa el módulo de la lista de deseos para representar artículos de la lista de deseos.

### <a name="loyalty-page"></a>Página de fidelización

La página de fidelización permite a los clientes ver sus detalles de fidelización si ya son miembros del programa de fidelización. También pueden ver los puntos que han obtenido y canjeado en transacciones recientes. La página usa el módulo de detalles de fidelización para mostrar los detalles de fidelización. 

Para unirse al programa de fidelización, se puede crear una página de marketing con módulos de registro y términos de fidelización. Si el usuario no es miembro de un programa de fidelización, estos módulos le permitirán registrarse.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
