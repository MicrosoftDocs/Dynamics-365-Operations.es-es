---
title: Configurar un canal de centro de llamadas
description: En este tema se describe cómo crear un nuevo canal de centro de llamadas en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b25626dafc07d576699ceba3cc9ca691db45cb9f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997759"
---
# <a name="set-up-a-call-center-channel"></a>Configurar un canal de centro de llamadas


[!include [banner](includes/banner.md)]

En este tema se describe cómo crear un nuevo canal de centro de llamadas en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general


En Dynamics 365 Commerce, un centro de llamadas es un tipo de canal de Commerce que se puede definir en la aplicación. La definición de un canal para las entidades de su centro de llamadas permite que el sistema vincule datos específicos y valores predeterminados de procesamiento de pedidos a los pedidos de ventas. Si bien una empresa puede definir múltiples canales de centro de llamadas en Commerce, es importante tener en cuenta que un usuario individual solo puede estar vinculado a un canal de centro de llamadas. 

Antes de crear un nuevo canal de centro de llamadas, asegúrese de haber completado los [Requisitos previos de configuración de canales](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Crear y configurar un nuevo canal de centro de llamadas

Para crear y configurar un nuevo centro de llamadas, siga estos pasos.

1. En el panel de navegación vaya a **Retail y Commerce \> Canales \> Centros de llamadas \> Todos los centros de llamadas**.
1. En el panel Acciones, seleccione **Nueva**.
1. En el campo **Nombre**, escriba un nombre para el nuevo canal.
1. Seleccione la **Entidad jurídica** apropiada en la lista desplegable.
1. Seleccione la ubicación de **Almacén** apropiada en la lista desplegable. Esta ubicación se usará como predeterminada en los pedidos de ventas creados para este canal del centro de llamadas, a menos que se hayan definido otros valores predeterminados a nivel del cliente o artículo.
1. En el campo **Cliente predeterminado**, especifique un cliente predeterminado válido. Estos datos se utilizan para ayudar a completar automáticamente los valores predeterminados cuando se crean nuevos registros de clientes. Al crear pedidos de centro de llamadas, no es aconsejable crear pedidos para el cliente predeterminado.
1. En el campo **Perfil de notificación por correo electrónico**, proporcione un perfil de notificación de correo electrónico válido. A medida que se crean y procesan los pedidos del centro de llamadas, el perfil de notificación por correo electrónico se utiliza para activar alertas automáticas por correo electrónico a los clientes con información sobre el estado de sus pedidos.
1. Proporcione un código de información de **Anulación del precio**. Puede que tenga que crear antes un código de información para esto. Este código de información proporciona el conjunto de códigos de motivo que se le pedirá al usuario que elija cuando use la funcionalidad de anulación de precios en un pedido de centro de llamadas.
1. Proporcionar un código de información de **Código de retención**. Puede que tenga que crear antes un código de información para esto. Este código de información proporciona el conjunto opcional de códigos de motivo que se le pedirá al usuario que elija cuando coloque un pedido en espera.
1. Proporcione un código de información de **Crédito**. Puede que tenga que crear antes un código de información para esto. Este código de información proporciona el conjunto de códigos de motivo entre los que el usuario puede elegir cuando usa la funcionalidad de crédito de pedido del centro de llamadas para dar reembolsos misceláneos al cliente por razones de servicio al cliente.
1. Opcional: configure las dimensiones financieras en la ficha desplegable **Dimensiones financieras**. Las dimensiones introducidas aquí serán predeterminadas en cualquier pedido de ventas creado en este canal del centro de llamadas.
1. Haga clic en **Guardar**.

La siguiente imagen muestra la creación de un nuevo canal de centro de llamadas.

![Nuevo canal de centro de llamadas](media/channel-setup-callcenter-1.png)

La siguiente imagen muestra un ejemplo de canal de centro de llamadas.

![Ejemplo de canal de centro de llamadas](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Configuración de canal adicional

Las tareas adicionales requeridas para la configuración del canal de centro de llamadas incluyen: configuración de métodos de pago y modos de entrega.

La siguiente imagen muestra las opciones de configuración de **Modos de entrega** y **Métodos de pago** en la pestaña **Configurar**.

![Acciones adicionales de configuración de canales de centro de llamadas](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>Configurar métodos de pago

Para configurar métodos de pago, siga estos pasos para cada tipo de pago admitido en este canal. Los usuarios deberán seleccionar entre los métodos de pago predefinidos para vincularlos al canal del centro de llamadas. Antes de configurar sus métodos de pago del centro de llamadas, primero configure sus métodos de pago maestros en **Retail y Commerce \> Configuración del canal \> Formas de pago \> Formas de pago**.

1. En el panel Acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Métodos de pago**.
1. En el panel Acciones, seleccione **Nueva**.
1. En el panel de navegación, seleccione un método de pago de los pagos predefinidos disponibles.
1. Configure opciones de configuración adicionales según sea necesario para el tipo de pago. Para tarjetas de crédito, tarjetas de regalo o tarjetas de fidelidad, se requiere una configuración adicional seleccionando la característica **Configuración de la tarjeta**. 
1. Configure las cuentas de contabilidad adecuadas para el tipo de pago en la sección **Destino**.
1. En el panel Acciones, haga clic en **Guardar**.

En la imagen siguiente se muestra un ejemplo de método de pago en efectivo.

![Ejemplo de métodos de pago](media/channel-setup-callcenter-payments.png)

### <a name="set-up-modes-of-delivery"></a>Configurar modos de entrega

Para ver los modos de entrega configurados, seleccione **Modos de entrega** en la pestaña **Configurar** del **panel Acciones**.  

Para cambiar o agregar un modo de entrega que se asociará al canal del centro de llamadas, siga estos pasos.

1. Desde el formulario de modos de entrega del centro de llamadas, seleccione **Administrar modos de entrega**
1. En el panel Acciones, seleccione **Nuevo** para crear un nuevo modo de entrega o seleccionar un modo existente.
1. En la sección **Canales comerciales**, haga clic en **Agregar línea** para agregar el canal del centro de llamadas. Agregar canales utilizando nodos de organización en lugar de agregar cada canal individualmente puede simplificar la adición de canales.
1. Asegúrese de que el modo de entrega se haya configurado con datos en la ficha desplegable **Productos** y la ficha desplegable **Direcciones**. Si no hay productos o direcciones de entrega válidas para el modo de entrega, elegirlo durante la entrada del pedido dará como resultado errores.
1. Después de realizar cualquier cambio en el modo de centro de llamadas de las configuraciones de entrega, el trabajo **Procesar modos de entrega** debe ejecutarse para explotar la matriz de cambio. Este trabajo se puede encontrar en **Retail y Commerce \> Retail y Commerce TI \> Procesar modos de entrega**.

En la imagen siguiente se muestra un ejemplo de mode de entrega.

![Configurar modos de entrega](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a>Configurar usuarios de canal

Para crear un pedido de ventas que esté vinculado al canal del centro de llamadas desde Commerce Headquarters, el usuario que cree el pedido de ventas debe estar vinculado al canal del centro de llamadas. El usuario no puede vincular manualmente un pedido de ventas creado en Commerce Headquarters al canal del centro de llamadas. El vínculo es sistemático y se basa en el usuario y la relación del usuario con el canal del centro de llamadas. Un usuario solo puede estar vinculado a un canal del centro de llamadas.

1. En el panel Acciones, seleccione la pestaña **Canal** y, a continuación, seleccione **Usuarios de canal**.
1. En el panel Acciones, seleccione **Nueva**.
1. Elige un **ID de usuario** ya existente de la lista de selección desplegable para vincular a este usuario al canal del centro de llamadas

Tras completar la configuración del usuario de canal y el usuario crea un pedido de ventas nuevo en Commerce Headquarters, el pedido de ventas estará vinculado a su canal de centro de llamadas asociado. Cualquier configuración para este canal se aplicará sistemáticamente al pedido de ventas. Un usuario puede confirmar a qué canal del centro de llamadas está vinculado el pedido de ventas al ver la referencia del nombre del canal en el encabezado del pedido de ventas.


### <a name="set-up-price-groups"></a>Configurar grupos de precios

Los grupos de precios son opcionales, pero si se usan, pueden controlar qué precios de venta se ofrecerán a los clientes que realicen pedidos en el canal del centro de llamadas. Si no se ha configurado un grupo de precios para el cliente, o si los grupos de precios de catálogo no se están aplicando al pedido de cliente (utilizando el **ID del código fuente** en el encabezado del pedido del centro de llamadas), luego el grupo de precios del canal se utiliza para localizar los precios de los artículos. Si no se encuentra un grupo de precios en el canal del centro de llamadas, se utilizan los precios maestros de artículos predeterminados. 

Para configurar un grupo de precios, haga lo siguiente.

1. En el panel Acciones, haga clic en la pestaña **Canal** y, a continuación, seleccione **Grupos de precios**.
1. En el panel Acciones, haga clic en **Nuevo**.
1. Seleccione un **Grupo de precios minoristas** de la lista de selección desplegable.

## <a name="additional-resources"></a>Recursos adicionales

[Requisitos previos de configuración del canal](channels-prerequisites.md)

[Funcionalidad de ventas del centro de llamadas](call-center-functionality.md)

[Configurar opciones de procesamiento de pedidos de centro de llamadas](set-up-order-processing-options.md)

[Catálogos del centro de llamadas](call-center-catalogs.md)

[Configurar y trabajar con alertas de fraude](set-up-fraud-alerts.md)

[Configurar programas de continuidad para centros de llamadas](set-up-continuity-program.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]