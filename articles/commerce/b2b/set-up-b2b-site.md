---
title: Configurar un sitio de comercio electrónico B2B
description: Este artículo describe cómo configurar un sitio de comercio electrónico de empresa a empresa (B2B) en Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: 162a8d4b51f10f409b77e1ced4c63c1a69a3b1f2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281134"
---
# <a name="set-up-a-b2b-e-commerce-site"></a>Configurar un sitio de comercio electrónico B2B

[!include [banner](../../includes/banner.md)]

Los sitios de comercio electrónico de empresa a empresa (B2B) proporcionan algunas funciones esenciales que optimizan el flujo de trabajo para un usuario de B2B. Este artículo describe cómo configurar un sitio de comercio electrónico B2B en Microsoft Dynamics 365 Commerce. Recorre la los módulos y las opciones de sitio que hay que configurar para habilitar escenarios específicos de B2B.

## <a name="prerequisites"></a>Requisitos previos

- Para configurar un sitio de comercio electrónico B2B, debe habilitar y configurar características específicas en Commerce headquarters, como se describe en este artículo.
- Las experiencias principales, como el descubrimiento de productos, las páginas de detalles del producto, el carro y el pago, funcionan con los mismos módulos que se utilizan para los sitios de comercio electrónico de empresa a consumidor (B2C). Los autores de sitios deben estar familiarizados con todos los módulos compatibles con Dynamics 365 Commerce. Para obtener más información, consulte [Visión general de la biblioteca de módulos](../starter-kit-overview.md).
- En este artículo se supone que los autores del sitio comprenden los conceptos básicos del generador de sitios, las plantillas, los fragmentos y las páginas de Commerce, de forma que puedan habilitar las características B2B para los sitios de comercio electrónico.

## <a name="site-level-settings"></a>Configuración de nivel de sitio

Puede acceder a la configuración de nivel de sitio en el generador de sitios, en **Configuración del sitio \> Extensiones**. Las dos opciones de configuración de nivel de sitio siguientes se aplican a escenarios B2B:

- **Habilitar pagos de cuenta de cliente**: esta propiedad permite a los usuarios pagar pedidos utilizando cuentas de clientes. Los valores disponibles son **Habilitado para clientes de B2B**, **Habilitado para clientes de B2C**, **Habilitados para todos los clientes** y **Deshabilitados para todos los clientes**. Si el sitio B2B admite cuentas de clientes, debe seleccionar **Habilitados para clientes de B2B**.
- **Habilitar límites de cantidad de pedidos**: esta propiedad permite establecer límites en la cantidad de artículos que se pueden pedir para cada producto o categoría. Los valores disponibles son **Habilitado para clientes de B2B**, **Habilitado para clientes de B2C**, **Habilitados para todos los clientes** y **Deshabilitados para todos los clientes**.

> [!NOTE]
> Cuando actualiza a la versión más reciente de la biblioteca de módulos, debe seguir pasos adicionales para asegurarse de que la configuración del sitio descrita anteriormente esté disponible en su entorno. Para obtener más información, consulte [Actualizar el archivo app.settings.json](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="create-business-partner-sign-up-pages"></a>Crear páginas de registro de socios comerciales

Para convertirse en socio comercial, los usuarios deben enviar primero una solicitud de socio comercial. En la página de inicio de B2B estará disponible un vínculo a la página de solicitud de socio comercial para que los usuarios puedan iniciar el proceso. Cuando los usuarios envíen una solicitud de socio comercial, recibirán la confirmación de que la solicitud se ha enviado. 

### <a name="create-a-business-partner-request-page"></a>Crear una página de solicitud de socio comercial

El módulo **Registro de socio** en una página de solicitud de socio comercial se utiliza para iniciar solicitudes de usuarios para convertirse en socios comerciales. Este módulo permite recopilar la información de usuario necesaria para el proceso de registro. Además, el módulo **Dirección de cuenta empresarial** se utiliza para capturar la dirección del usuario.

Para instalar y configurar la página de solicitud de socio comercial en el generador de sitios, siga estos pasos.

1. Crea una plantilla llamada **Registro**. Esta plantilla debe incluir los siguientes módulos:

    - Registro de socio
    - Ruta de navegación
    - Encabezado
    - Pie de página
    - Bloque de contenido
    - Bloque de texto
    - Colección de productos

1. Use la plantilla **Registro** para crear una página llamada **Solicitud de socio comercial**.
1. En la entrada **Encabezado**, agregue el fragmento de encabezado que está preconfigurado con el encabezado del sitio.
1. En la entrada **Pie de página**, agregue el fragmento de pie de página que está preconfigurado con el pie de página del sitio.
1. En la entrada **Principal**, agregue un módulo **Contenedor**. En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**.
1. En la entrada **Contenedor**, agregue un módulo **Ruta de navegación**. En el panel de propiedades del módulo, en **Vínculos**, configure un vínculo a la página de inicio y especifique **Inicio** como texto del vínculo.
1. En la entrada **Contenedor**, agregue un módulo **Registro de socio** bajo el módulo **Ruta de navegación**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Convertirse en socio comercial**.
1. En la entrada **Registro de socio**, agregue un módulo **Dirección de cuenta empresarial**.
1. En la entrada **Contenedor**, agregue un módulo **Bloque de texto** bajo el módulo **Registro de socio**. Aquí puede definir algunos términos y condiciones para el proceso de registro.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.
1. Publique la dirección URL de la página.

### <a name="create-a-business-partner-request-confirmation-page"></a>Crear una página de confirmación de solicitud de socio comercial

Tras el envío de una solicitud de socio comercial, se debe mostrar al usuario una página de confirmación para confirmar el envío. 

Para instalar y configurar la página de confirmación de solicitud en el generador de sitios, siga estos pasos.

1. Use la plantilla **Registro** que creó anteriormente para crear una página llamada **Confirmación de solicitud de socio**.
1. En la entrada **Encabezado**, agregue el fragmento de encabezado que está preconfigurado con el encabezado del sitio.
1. En la entrada **Pie de página**, agregue el fragmento de pie de página que está preconfigurado con el pie de página del sitio.
1. En la entrada **Principal**, agregue un módulo **Contenedor**. En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**.
1. En la entrada **Contenedor**, agregue un módulo **Bloque de contenido**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Solicitud enviada**. En el campo **Texto enriquecido**, escriba **Se ha enviado su solicitud**. En **Vínculos**, configure un vínculo a la página de inicio y especifique **Volver a la compra** como texto del vínculo.
1. Agregue otro módulo **Contenedor** y agréguele un módulo **Colección de productos**.
1. Configure el módulo **Colección de productos** con la lista de recomendaciones o categorías que desea mostrar en la página.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.
1. Publique la dirección URL de la página.

Para agregar un vínculo a la página de confirmación de solicitud en el generador de sitios, siga estos pasos.

1. Vaya a la página **Solicitud de socio comercial** que creó anteriormente y seleccione **Editar**. 
1. Seleccione la entrada del módulo **Registro de socio**. En el panel de propiedades, en **Vínculo a la página de confirmación de registro**, configure el vínculo a la página de solicitud de socio comercial que creó anteriormente. 
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

### <a name="add-a-business-partner-request-link-to-the-home-page"></a>Agregar un vínculo de solicitud de socio comercial a la página de inicio

Una vez creadas las páginas de confirmación de y registro de solicitud de socio comercial, debe hacer que la página de registro sea accesible a través de un vínculo en la página de inicio. Puede completar esta tarea agregando el vínculo a cualquier módulo **Bloque de contenido** en la página de inicio.

Para agregar un vínculo de solicitud de socio comercial a la página de inicio en el generador de sitios, siga estos pasos.

1. Vaya a la página de inicio del sitio y seleccione **Editar**.
1. Seleccione una entrada de módulo **Bloque de contenido**. En el panel de propiedades del módulo, en **Vínculos**, configure un vínculo a la página de solicitud de socio comercial que creó anteriormente y escriba **Regístrese para ser socio comercial** o un texto similar como texto del vínculo. Agregue una imagen según corresponda.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="account-management-landing-page"></a>Página de aterrizaje de gestión de cuentas

La página de aterrizaje de gestión de cuentas incluye toda la información de gestión de cuentas que se requiere para los sitios de comercio electrónico B2B y B2C. Solo los usuarios registrados pueden ver esta página.

Para crear y configurar una página de aterrizaje de gestión de cuentas B2B en el generador de sitios, siga estos pasos.

1. Crea una plantilla llamada **Gestión de cuentas**. Esta plantilla debe incluir los siguientes módulos:

    - Encabezado
    - Pie de página
    - Ruta de navegación
    - Icono de bienvenida de cuenta
    - Icono genérico de cuenta
    - Icono de dirección de cuenta
    - Icono de lista de deseos de cuenta
    - Icono de dirección de cuenta
    - Icono de fidelización de cuenta
    - Icono de saldo de cliente de cuenta
    - Icono de plantillas de pedido de cuenta
    - Usuarios de la organización
    - Lista de organizaciones empresariales
    - Saldo de cuenta de cliente
    - Líneas de plantilla de pedido
    - Lista de plantillas de pedido
    - Icono de factura de cuenta
    - Lista de facturas
    - Detalles de la factura

1. Use la plantilla **Gestión de cuentas** para crear una página llamada **Mi cuenta**.
1. En la entrada **Encabezado**, agregue el fragmento de encabezado que está preconfigurado con el encabezado del sitio.
1. En la entrada **Pie de página**, agregue el fragmento de pie de página que está preconfigurado con el pie de página del sitio.
1. En la entrada **Principal**, agregue un módulo **Contenedor**. En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**. 
1. En la entrada **Contenedor**, agregue un módulo **Ruta de navegación**. En el panel de propiedades del módulo, en **Vínculos**, configure un vínculo a la página de inicio y especifique **Inicio** como texto del vínculo.
1. En la entrada **Contenedor**, agregue un módulo **Icono de bienvenida**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Le damos la bienvenida**.
1. En la entrada **Principal**, agregue otro módulo **Contenedor** (**Contenedor 2**). En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**. Establezca **Elementos secundarios mostrados** en **Dos**. 
1. En la entrada **Contenedor 2**, agregue un módulo **Icono genérico de cuenta**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Mi perfil**. En **Vínculos**, configure un vínculo a la página **Mi perfil**. 
1. En la entrada **Contenedor 2**, agregue otro módulo **Icono genérico de cuenta**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Historial de pedidos**. En **Vínculos**, configure un vínculo a la página del historial de pedidos.
1. En la entrada **Principal**, agregue otro módulo **Contenedor** (**Contenedor 3**). En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**. Establezca **Elementos secundarios mostrados** en **Dos**. 
1. En la entrada **Contenedor 3**, agregue un módulo **Icono de dirección de cuenta**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Mi dirección**. En **Vínculos**, configure un vínculo a la página **Mi dirección**. 
1. En la entrada **Contenedor 3**, agregue un módulo **Icono de lista de deseos de cuenta**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Mi lista de deseos**. En **Vínculos**, configure un vínculo a la página **Mi lista de deseos**.
1. En la entrada **Principal**, agregue otro módulo **Contenedor** (**Contenedor 4**). En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**. Establezca **Elementos secundarios mostrados** en **Dos**. 
1. En la entrada **Contenedor 4**, agregue un módulo **Usuarios de la organización**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Usuarios de la organización**. 
1. En la entrada **Contenedor 4**, agregue un módulo **Icono de saldo de cliente de cuenta**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Crédito de cuenta**. 
1. En la entrada **Principal**, agregue otro módulo **Contenedor** (**Contenedor 5**). En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**. Establezca **Elementos secundarios mostrados** en **Dos**. 
1. En el módulo **Contenedor 5**, agregue un módulo **Icono de plantillas de pedido de cuenta**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Plantillas de pedido**. 
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

> [!NOTE] 
> Algunas de las secciones que agregó en los pasos 13 a 18 no aparecerán en el lienzo "lo que se ve es lo que se verá" (WYSIWIG) en el generador de sitios, ya que requieren una cuenta B2B con una sesión iniciada.

## <a name="create-and-configure-customer-balance-pages-and-modules"></a>Crear y configurar páginas y módulos de saldo de clientes 

Las cuentas de los clientes se pueden utilizar para pagar pedidos. El saldo disponible en una cuenta de cliente se puede ver desde la página de administración de la cuenta de un usuario.

### <a name="create-a-customer-balance-page"></a>Crear una página de saldo de cliente 

Para que los usuarios de B2B que han iniciado sesión puedan ver el saldo de sus clientes, debe crear una página de saldo de cliente. 

Para crear una página de saldo de cliente en el generador de sitios, siga estos pasos.

1. Utilizar la plantilla **Gestión de cuentas** que creó anteriormente para crear una página llamada **Saldo del cliente**.
1. En la entrada **Encabezado**, agregue el fragmento de encabezado que está preconfigurado con el encabezado del sitio.
1. En la entrada **Pie de página**, agregue el fragmento de pie de página que está preconfigurado con el pie de página del sitio.
1. En la entrada **Principal**, agregue otro módulo **Contenedor** (**Contenedor 3**). En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**. Establezca **Elementos secundarios mostrados** en **Dos**.
1. En la entrada **Contenedor**, agregue un módulo **Ruta de navegación**. En el panel de propiedades del módulo, en **Vínculos**, configure un vínculo a la página de aterrizaje de gestión de cuentas y especifique **Mi cuenta** como texto del vínculo.
1. En la entrada **Contenedor**, agregue un módulo **Saldo de cuenta de cliente**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Saldo de cuenta**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.
1. Publique la dirección URL de la página.
1. Vaya a la página de aterrizaje de gestión de cuentas (**Mi cuenta**) que creó anteriormente.
1. En el panel de propiedades del módulo **Icono de saldo de cliente de cuenta**, agregue un vínculo a la página de saldo de cliente. 
1. Guarde y publique la página.

Se ha creado la página de saldo de cliente y los usuarios podrán acceder a ella desde la página de aterrizaje de gestión de cuentas.

### <a name="configure-a-checkout-page-so-that-the-customer-balance-can-be-used-as-a-form-of-payment"></a>Configurar una página de pago para que el saldo del cliente se pueda utilizar como forma de pago

El módulo **Pago de cuenta de cliente** es necesario para permitir que se utilice el saldo del cliente como forma de pago. Este módulo debe agregarse a la página de finalización de pago como una forma de pago. Para obtener información sobre cómo configurar una página de finalización de compra y los módulos necesarios para finalizar compras, incluidos todos los detalles de pago, consulte [Módulo de finalización de compra](../add-checkout-module.md).

Una vez que haya configurado una página de finalización de compra, deberá agregar el módulo **Pago de cuenta de cliente** a la sección de pago y, a continuación, guardar y publicar la página. Los usuarios de B2B podrán iniciar sesión en el sitio de comercio electrónico y aplicar su saldo de cliente disponible a los pedidos durante el pago.

Además, en **Generador de sitios \> Extensiones**, debe asegurarse de que la propiedad **Habilitar pagos de cuenta de cliente** esté establecida en **Habilitado para clientes de B2B**.

## <a name="create-order-template-pages"></a>Crear páginas de plantillas de pedido

Se pueden configurar dos páginas de plantilla de pedido para un sitio de comercio electrónico B2B: una página de lista de plantillas de pedido y una página de líneas de plantilla de pedido.

Una página de lista de plantillas de pedido muestra una lista de todas las plantillas de pedido que están disponibles. Se configura mediante el módulo **Lista de plantillas de pedido**. La página de lista de plantillas de pedido le permite crear o eliminar una plantilla y agregar los artículos de una plantilla al carro.

Una página de líneas de plantilla de pedido muestra los detalles de la plantilla de pedido seleccionada en una página de lista de plantillas de pedido. Se configura mediante el módulo **Líneas de plantilla de pedido**. Cuando un usuario selecciona el nombre de una plantilla en una página de lista de plantillas de pedido, aparece la página de líneas de plantilla de pedido y muestra los detalles de la plantilla. El usuario puede ver y editar los artículos de la plantilla.

### <a name="create-an-order-templates-list-page"></a>Crear una página de lista de plantillas de pedido

Para crear una página de lista de plantillas de pedido en el generador de sitios, siga estos pasos.

1. Use la plantilla **Gestión de cuentas** que creó anteriormente para crear una página llamada **Plantillas de pedido**.
1. En la entrada **Encabezado**, agregue el fragmento de encabezado que está preconfigurado con el encabezado del sitio.
1. En la entrada **Pie de página**, agregue el fragmento de pie de página que está preconfigurado con el pie de página del sitio.
1. En la entrada **Principal**, agregue un módulo **Contenedor**. En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**.
1. En la entrada **Contenedor**, agregue un módulo **Ruta de navegación**. En el panel de propiedades del módulo, en **Vínculos**, configure un vínculo a la página de aterrizaje de gestión de cuentas y especifique **Mi cuenta** como texto del vínculo.
1. En la entrada **Contenedor**, agregue un módulo **Lista de plantillas de pedido**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.
1. Publique la dirección URL de la página.
1. Vaya a la página de aterrizaje de gestión de cuentas (**Mi cuenta**) que creó anteriormente.
1. En el panel de propiedades del módulo **Icono de plantillas de pedidos de cuenta**, en **Vínculos**, configure un vínculo a la página de lista de plantillas de pedido que acaba de crear.
1. Guarde y publique la página.

Se ha creado la página de lista de plantillas de pedido y los usuarios podrán acceder a ella desde la página de aterrizaje de gestión de cuentas.

### <a name="create-an-order-template-lines-page"></a>Crear una página de líneas de plantilla de pedido

Para crear una página de líneas de plantilla de pedido en el generador de sitios, siga estos pasos.

1. Use la plantilla **Gestión de cuentas** que creó anteriormente para crear una página llamada **Líneas de plantilla de pedido**.
1. En la entrada **Encabezado**, agregue el fragmento de encabezado que está preconfigurado con el encabezado del sitio.
1. En la entrada **Pie de página**, agregue el fragmento de pie de página que está preconfigurado con el pie de página del sitio.
1. En la entrada **Principal**, agregue un módulo **Contenedor**. En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**.
1. En la entrada **Contenedor**, agregue un módulo **Ruta de navegación**. En el panel de propiedades del módulo, en **Vínculos**, configure un vínculo a la página de aterrizaje de gestión de cuentas y especifique **Mi cuenta** como texto del vínculo.
1. En la entrada **Contenedor**, agregue un módulo **Líneas de plantilla de pedido**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.
1. Publique la dirección URL de la página.

## <a name="onboard-business-partner-users"></a>Incorporar usuarios socios comerciales

La página de usuarios de la organización permite al administrador de una organización socio comercial incorporar usuarios adicionales de esa organización al sitio de comercio electrónico B2B. Se configura mediante el módulo **Lista de organizaciones empresariales**. Desde la página de usuarios de la organización, un administrador puede agregar o quitar usuarios, definir saldos de cuentas y solicitar extractos para un usuario.

Para crear una página de usuarios de organización en el generador de sitios, siga estos pasos.

1. Use la plantilla **Gestión de cuentas** que creó anteriormente para crear una página llamada **Usuarios de la organización**.
1. En la entrada **Encabezado**, agregue el fragmento de encabezado que está preconfigurado con el encabezado del sitio.
1. En la entrada **Pie de página**, agregue el fragmento de pie de página que está preconfigurado con el pie de página del sitio.
1. En la entrada **Principal**, agregue un módulo **Contenedor**. En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**.
1. En la entrada **Contenedor**, agregue un módulo **Ruta de navegación**. En el panel de propiedades del módulo, en **Vínculos**, configure un vínculo a la página de aterrizaje de gestión de cuentas y especifique **Mi cuenta** como texto del vínculo.
1. En la entrada **Contenedor**, agregue un módulo **Lista de usuarios de la organización**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Usuarios de la organización**.
1. En el panel de propiedades del módulo **Lista de organizaciones empresariales**, habilite las propiedades **Ordenación de tabla** y **Paginación de tabla**. Establezca el recuento de paginación en **5**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.
1. Publique la dirección URL de la página.
1. Vaya a la página de aterrizaje de gestión de cuentas (**Mi cuenta**) que creó anteriormente.
1. En el panel de propiedades del módulo **Icono de usuarios de la organización**, en **Vínculos**, configure un vínculo a la página de usuarios de la organización que acaba de crear. 
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="create-invoice-pages"></a>Crear páginas de factura

Una página de lista de facturas muestra una lista de todas las facturas disponibles. Se configura mediante el módulo **Lista de facturas**. Desde la página de lista de facturas, los usuarios pueden pagar o solicitar facturas. 

Una página de detalles de factura muestra los detalles de la factura seleccionada en una página de lista de facturas. Se configura mediante el módulo **Detalles de factura**. Cuando un usuario selecciona un id. de factura en una página de lista de facturas, aparece la página de detalles de factura que muestra los detalles de la factura.

### <a name="create-an-invoices-list-page"></a>Crear una página de lista de facturas

Para crear una página de lista de facturas en el generador de sitios, siga estos pasos.

1. Use la plantilla **Gestión de cuentas** que creó anteriormente para crear una página llamada **Lista de facturas**.
1. En la entrada **Encabezado**, agregue el fragmento de encabezado que está preconfigurado con el encabezado del sitio.
1. En la entrada **Pie de página**, agregue el fragmento de pie de página que está preconfigurado con el pie de página del sitio.
1. En la entrada **Principal**, agregue un módulo **Contenedor**. En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**.
1. En la entrada **Contenedor**, agregue un módulo **Ruta de navegación**. En el panel de propiedades del módulo, en **Vínculos**, configure un vínculo a la página de aterrizaje de gestión de cuentas y especifique **Mi cuenta** como texto del vínculo.
1. En la entrada **Contenedor**, agregue un módulo **Lista de facturas**. En el panel de propiedades del módulo, en **Encabezado**, escriba **Facturas**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.
1. Publique la dirección URL de la página.
1. Vaya a la página de aterrizaje de gestión de cuentas (**Mi cuenta**) que creó anteriormente.
1. En el panel de propiedades del módulo **Icono de facturas de cuenta**, en **Vínculos**, configure un vínculo a la página de lista de facturas que acaba de crear. 
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

### <a name="create-an-invoice-details-page"></a>Crear una página de detalles de factura

Para crear una página de detalles de facturas en el generador de sitios, siga estos pasos.

1. Use la plantilla **Gestión de cuentas** que creó anteriormente para crear una página llamada **Detalles de factura**.
1. En la entrada **Encabezado**, agregue el fragmento de encabezado que está preconfigurado con el encabezado del sitio.
1. En la entrada **Pie de página**, agregue el fragmento de pie de página que está preconfigurado con el pie de página del sitio.
1. En la entrada **Principal**, agregue un módulo **Contenedor**. En el panel de propiedades del módulo, establezca el valor de **Ancho** en **Rellenar contenedor**.
1. En la entrada **Contenedor**, agregue un módulo **Ruta de navegación**. En el panel de propiedades del módulo, en **Vínculos**, configure un vínculo a la página de aterrizaje de gestión de cuentas y especifique **Mi cuenta** como texto del vínculo. A continuación, configure un vínculo a la página de la lista de facturas y escriba **Listas de facturas** como texto del vínculo.
1. En la entrada **Contenedor**, agregue un módulo **Detalles de factura**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.
1. Publique la dirección URL de la página.

## <a name="add-a-quick-add-module-to-the-cart-page"></a>Agregar un módulo de adición rápida a la página del carrito

El módulo de adición rápida proporciona una manera de agregar rápidamente varios artículos al carrito mediante el uso de los id. de artículo (también conocidos como id. de referencia de almacén \[ SKU\]). El módulo de adición rápida se agrega a la página del carrito de un sitio.

Para agregar un módulo de adición rápida a una página de carrito en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Plantillas** y seleccione la plantilla de página de carrito de su sitio.
1. Seleccione **Editar**.
1. En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Adición rápida** y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y seleccione la página de carrito de su sitio.
1. En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo **Contenedor**, en **Anchura**, seleccione **Rellenar contenedor**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Adición rápida** y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

> [!NOTE] 
> El módulo de adición rápida está disponible a partir de la versión 10.0.17 de Commerce. Si está actualizando desde una versión anterior de Commerce, debe actualizar manualmente el archivo appsettings.json. Para obtener instrucciones, consulte [Actualizaciones del SDK y la biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="add-a-bulk-purchase-module-to-a-product-details-page"></a>Agregar un módulo de compra al por mayor a una página de detalles del producto

El módulo de compra al por mayor en una página de detalles del producto (PDP) ofrece una experiencia basada en una matriz que permite al comprador agregar rápidamente múltiples variantes de un producto al carrito. Cuando un usuario del sitio debe pedir múltiples variantes del mismo producto, esta experiencia elimina la necesidad de seleccionar la combinación de dimensiones del producto, definir la cantidad, agregar la variante al carrito y luego repetir el proceso para otras combinaciones de dimensiones del producto.

Para agregar el módulo de compras al por mayor a un PDP en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Plantillas** y seleccione la plantilla de PDP de su sitio.
1. Seleccione **Editar**.
1. En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo de **Compra al por mayor** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y seleccione la PDP de su sitio.
1. En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo **Contenedor**, en **Anchura**, seleccione **Rellenar contenedor**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo de **Compra al por mayor** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

> [!NOTE] 
> El módulo de compra al por mayor está disponible a partir de la versión 10.0.24 de Commerce. Si está actualizando desde una versión anterior de Commerce, debe actualizar manualmente el archivo appsettings.json. Para obtener instrucciones, consulte [Actualizaciones del SDK y la biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](../starter-kit-overview.md)

[Actualizaciones de SDK y bibliotecas de módulos](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file)

[Información general de creación de páginas](../authoring-home-overview.md)

[Información general de plantillas y diseños](../templates-layouts-overview.md)

[Trabajar con fragmentos](../work-with-fragments.md)

[Agregar una página de sitio nueva](../add-new-page.md)

[Módulo de finalización de compra](../add-checkout-module.md)

[Módulo de bloque de contenido](../add-hero-module.md)

[Módulo de colección de productos](../product-collection-module-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
