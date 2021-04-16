---
title: Configurar un inquilino B2C en Commerce
description: En este tema se describe cómo configurar los inquilinos de empresa a consumidor (B2C) de Azure Active Directory (Azure AD) para la autenticación del sitio del usuario en Dynamics 365 Commerce.
author: BrianShook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: f062f40c9eb883d02c4a0ee06c797ed1b0b22665
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794004"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Configurar un inquilino B2C en Commerce

[!include [banner](includes/banner.md)]

En este tema se describe cómo configurar los inquilinos de empresa a consumidor (B2C) de Azure Active Directory (Azure AD) para la autenticación del sitio del usuario en Dynamics 365 Commerce.

Dynamics 365 Commerce usa Azure AD B2C para admitir credenciales de usuario y flujos de autenticación. Un usuario puede registrarse, iniciar sesión y restablecer su contraseña a través de estos flujos. Azure AD B2C almacena información confidencial de autenticación de usuarios, como el nombre de usuario y la contraseña. El registro de usuario en el inquilino B2C almacenará un registro de cuenta local de B2C o un registro de proveedor de identidad social de B2C. Estos registros de B2C se vincularán de nuevo con el registro del cliente en el entorno de Commerce.

> [!WARNING] 
> Azure AD B2C retirará los flujos de usuarios antiguos (heredados) antes del 1 de agosto de 2021. Por lo tanto, debe planear migrar sus flujos de usuarios a la nueva versión recomendada. La nueva versión proporciona paridad de funciones y nuevas funciones. La biblioteca de módulos para Commerce versión 10.0.15 o superior debe usarse con los flujos de usuarios B2C recomendados. Para obtener más información, vea [Flujos de usuario en Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/user-flow-overview).
 
 > [!NOTE]
 > Los entornos de evaluación de comercio vienen con un inquilino de Azure AD B2C cargado previamente con fines de demostración. Cargar su propio inquilino Azure AD B2C con los pasos a continuación no es necesario para entornos de evaluación.

## <a name="create-or-link-to-an-existing-aad-b2c-tenant-in-the-azure-portal"></a>Crear o vincular un inquilino de AAD B2C existente en el portal de Azure

1. Inicie sesión en el [portal de Azure](https://portal.azure.com/).
1. En el menú del portal de Azure, seleccione **Crear un recurso**. Asegúrese de utilizar la suscripción y el directorio que se conectarán con su entorno de Commerce.

    ![Crear un recurso en el portal de Azure](./media/B2CImage_1.png)

1. Vaya a **Identidad \> Azure Active Directory B2C**.
1. Cuando esté en la página **Crear o vincular un inquilino de AAD B2C existente en el portal de Azure**, utilice de las opciones siguientes la que mejor se adapte a las necesidades de su empresa:

    - **Crear un nuevo inquilino de Azure AD B2C**: use esta opción para crear un nuevo inquilino de AAD B2C.
        1. Seleccione **Crear un nuevo inquilino de Azure AD B2C**.
        1. En **Nombre de la organización**, escriba el nombre de la organización.
        1. En **Nombre de dominio inicial**, escriba el nombre de dominio inicial.
        1. En **País o región**, seleccione el país o región.
        1. Seleccione **Crear** para crear el inquilino.

     ![Crear un nuevo inquilino de Azure AD](./media/B2CImage_2.png)

     - **Vincular un inquilino de Azure AD B2C existente a mi suscripción de Azure**: use esta opción si ya tiene un inquilino de Azure AD B2C al que desee vincularse.
        1. Seleccione **Vincular un inquilino de Azure AD B2C existente a mi suscripción de Azure**.
        1. Para **Inquilino de Azure AD B2C**, seleccione el inquilino de B2C apropiado. Si aparece el mensaje "No se encontraron inquilinos B2C válidos" en el cuadro de selección, significa que no tiene ningún inquilino de B2C válido, por lo que deberá crear uno nuevo.
        1. Para **Grupo de recursos**, seleccione **Crear nuevo**. Introduzca un **Nombre** para el grupo de recursos que contendrá el inquilino, seleccione **Ubicación del grupo de recursos** y, a continuación, seleccione **Crear**.

    ![Vincular un inquilino de Azure AD B2C existente a la suscripción de Azure](./media/B2CImage_3.png)

1. Una vez creado el nuevo directorio de Azure AD B2C (puede tardar unos minutos), aparecerá un vínculo al nuevo directorio en el panel de información. Este vínculo le dirigirá a la página "Esto es Azure Active Directory B2C".

    ![Vínculo al nuevo directorio de AAD](./media/B2CImage_4.png)

> [!NOTE]
> Si tiene varias suscripciones en su cuenta de Azure o ha configurado el inquilino de B2C sin vincularlo a una suscripción activa, un encabezado **Solución de problemas** le dirigirá en el proceso de vincular el inquilino a una suscripción. Seleccione el mensaje de solución de problemas y siga las instrucciones para resolver el problema de suscripción.

La siguiente imagen muestra un ejemplo de encabezado **Solución de problemas** de Azure AD B2C.

![Advertencia que indica que el directorio no tiene una suscripción activa](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a>Crear la aplicación B2C

Cuando se haya creado el inquilino de B2C, usted puede crear una aplicación B2C en su nuevo inquilino de Azure AD B2C para interactuar con Commerce.

Para crear la aplicación B2C, siga estos pasos.

1. En Azure Portal, seleccione **Registros de aplicaciones** y luego seleccione **Nuevo registro**.
1. En **Nombre**, introduzca el nombre para darle a esta aplicación Azure AD B2C.
1. En **Tipos de cuenta admitidos**, seleccione **Cuentas en cualquier proveedor de identidad o directorio organizacional (para autenticar usuarios con flujos de usuarios)**.
1. Para **Redirigir URI**, introduzca sus URL de respuesta dedicadas como tipo **Web**. Para obtener información sobre las URL de respuesta y qué formato aplicarles, consulte [Direcciones URL de respuesta](#reply-urls) a continuación.
1. Para **Permisos**, seleccione **Otorgar consentimiento del administrador a los permisos openid y offline_access**.
1. Seleccione **Registrar**.
1. Seleccione la aplicación recién creada y navegue hasta el menú **Autenticación**. Aquí puede agregar más **Redirigir URI** si es necesario (ahora o más tarde). Continúe con el siguiente paso si no lo necesita actualmente.
1. En **Concesión implícita**, seleccione **Tokens de acceso** y **Tokens de identificación** para habilitarlos para la aplicación. Seleccione **Guardar**.
1. Vaya al menú **Visión general** menú de Azure Portal y copie el **ID de aplicación (cliente)**. Anote esta ID para los pasos de configuración posteriores (a la que se hace referencia más adelante como **GUID del cliente**).

Para obtener más información sobre los registros de aplicaciones en Azure AD B2C, consulte [La nueva experiencia de registro de aplicaciones para Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/app-registrations-training-guide)

### <a name="reply-urls"></a>Direcciones URL de respuesta

Las direcciones URL de respuesta son importantes, ya que ofrecen una lista blanca de los dominios de retorno cuando su sitio llama a Azure AD B2C para autenticar a un usuario. Esto posibilita que el usuario autenticado regrese al dominio desde el que inició sesión (el dominio de su sitio). 

En el cuadro **Dirección URL de respuesta** de la pantalla **Azure AD B2C - Aplicaciones \> Nueva aplicación** debe agregar líneas independientes para el dominio de su sitio y (una vez que se haya aprovisionado el entorno) la dirección URL generada por Commerce. Estas direcciones URL siempre deben usar un formato de URL válido y deben ser direcciones URL base únicamente (sin barras diagonales ni rutas). Hay que agregar a las direcciones URL base la cadena ``/_msdyn365/authresp``, como en los siguientes ejemplos.

- ``https://www.fabrikam.com/_msdyn365/authresp`` (El dominio debe coincidir completamente con el dominio de comercio electrónico. Si tiene varios dominios, debe agregar esta URL para cada dominio.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a>Crear directivas de flujo de usuario

Los flujos de usuario son las directivas que Azure AD B2C utiliza para proporcionar experiencias de usuario de inicio de sesión seguro, registro, edición de perfil y restablecimiento de contraseña. Dynamics 365 Commerce utiliza estos flujos para realizar las acciones de directiva a fin de interactuar con el inquilino de Azure AD B2C. Cuando un usuario interactúa con estas directivas, se redirigen al inquilino de Azure AD B2C para realizar las acciones.

Azure AD B2C proporciona tres tipos básicos de flujo de usuario:
- Registro e inicio de sesión
- Edición de perfil
- Contraseña restablecida

Puede optar por usar los flujos de usuario predeterminados proporcionados por Azure AD, que mostrarán una página hospedad en AAD B2C. Como alternativa, puede crear una página HTML para controlar la apariencia de estas experiencias de flujo de usuario. 

Para personalizar las páginas de directiva de usuario con páginas incluidas en Dynamics 365 Commerce, consulte [Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md). Para obtener información adicional, consulte [Personalizar las experiencias de interfaz de usuario en Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Crear una directiva de flujo de usuario registro e inicio de sesión

Para crear una directiva de flujo de usuario de registro e inicio de sesión, siga estos pasos.

1. En el portal de Azure, seleccione **Flujos de usuario (directivas)** en el panel de navegación izquierdo.
1. En la página **Azure AD B2C - Flujos de usuarios (directivas)**, seleccione **Nuevo flujo de usuario**.
1. Seleccione la directiva **Registro e iniciar sesión** y después seleccione la versión **Recomendada**.
1. En **Nombre**, escriba un nombre de directiva. Este nombre se mostrará posteriormente con un prefijo asignado por el portal (por ejemplo, "B2C_1_").
1. En **Proveedores de identidad**, active la casilla de verificación correspondiente.
1. En **Autenticación multifactor**, seleccione la opción adecuada para su empresa. 
1. En **Atributos y devoluciones de usuario**, seleccione opciones para recopilar atributos o notificaciones de devolución, según corresponda. Commerce requiere las siguientes opciones predeterminadas:

    | **Recopilar atributo** | **Notificación de devolución** |
    | ---------------------- | ----------------- |
    | Dirección de correo electrónico          | Direcciones de correo electrónico   |
    | Nombre propio             | Nombre propio        |
    |                        | Proveedor de identidades |
    | Apellido                | Apellido           |
    |                        | ID de objeto del usuario  |

1. Seleccione **Crear**.

La siguiente imagen es un ejemplo de flujo de usuario de registro e inicio de sesión de Azure AD B2C.

![Configuración de la directiva de registro e inicio de sesión](./media/B2CImage_11.png)

La siguiente imagen muestra la opción **Ejecutar flujo de usuario** en el flujo de usuario de registro e inicio de sesión de Azure AD B2C.

![Opción Ejecutar flujo de usuario en flujo de directiva](./media/B2CImage_23.png)
   
### <a name="create-a-profile-editing-user-flow-policy"></a>Crear una directiva de flujo de usuario de edición de perfil

Para crear una directiva de flujo de usuario de edición de perfil, siga estos pasos.

1. En el portal de Azure, seleccione **Flujos de usuario (directivas)** en el panel de navegación izquierdo.
1. En la página **Azure AD B2C - Flujos de usuarios (directivas)**, seleccione **Nuevo flujo de usuario**.
1. Seleccione **Edición de perfil** y luego seleccione la versión **Recomendado**.
1. En **Nombre**, introduzca el flujo de usuario de edición de perfil. Este nombre se mostrará posteriormente con un prefijo asignado por el portal (por ejemplo, "B2C_1_").
1. En **Proveedores de identidad**, seleccione **Inicio de sesión de correo**.
1. En **Atributos de usuario**, active las siguientes casillas:
    - **Direcciones de correo electrónico** (**Notificación de devolución** únicamente)
    - **Nombre propio** (**Recopilar atributo** y **Notificación de devolución**)
    - **Proveedor de identidad** (**Notificación de devolución** únicamente)
    - **Apellido** (**Recopilar atributo** y **Notificación de devolución**)
    - **ID de objeto del usuario** (**Notificación de devolución** únicamente)
1. Seleccione **Crear**.

La siguiente imagen muestra un ejemplo de flujo de usuario de edición de perfil de Azure AD B2C.

![Crear el flujo de usuario de edición de perfil](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Crear una directiva de flujo de usuario de restablecimiento de contraseña

Para crear una directiva de flujo de usuario de restablecimiento de contraseña, siga estos pasos.

1. En el portal de Azure, seleccione **Flujos de usuario (directivas)** en el panel de navegación izquierdo.
1. En la página **Azure AD B2C - Flujos de usuarios (directivas)**, seleccione **Nuevo flujo de usuario**.
1. Seleccione **Restablecer contraseña** y luego seleccione la versión **Recomendado**.
1. En **Nombre**, introduzca un nombre para el flujo de usuario de restablecimiento de contraseña.
1. En **Proveedores de identidad**, seleccione **Restablecer contraseña con dirección de correo electrónico**.
1. Seleccione **Crear**.
1. En **Notificaciones de aplicación**, active las siguientes casillas:
    - **Direcciones de correo electrónico**
    - **Nombre propio**
    - **Apellido**
    - **ID de objeto del usuario**
1. Seleccione **Crear**.

La siguiente imagen muestra dónde se establece **Restablecer contraseña con dirección de correo electrónico** en el flujo de usuario de restablecimiento de contraseña de Azure AD B2C.

![Establezca "Restablecer contraseña con dirección de correo electrónico" en la directiva de restablecimiento de contraseña](./media/B2CImage_13.png)

## <a name="add-social-identity-providers-optional"></a>Agregar proveedores de identidad social (opcional)

Los proveedores de identidad social permiten a los usuarios usar sus cuentas sociales para la autenticación. La adición de autenticación de proveedor de identidad social es opcional en Dynamics 365 Commerce. 

Si no se agrega la autenticación de proveedor de identidad social, los perfiles predeterminados de Azure AD B2C serán los perfiles principales para su base de usuarios. Los usuarios seleccionarán su propio nombre de usuario (su dirección de correo electrónico preferida) y establecerán una contraseña. Azure AD B2C autenticará a los usuarios directamente. 

Si se agrega la autenticación de proveedor de identidad social y un usuario elige uno de los proveedores de identidad social ofrecidos, se sigue creando una entidad en el inquilino de Azure AD B2C. Azure AD B2C autenticará las credenciales del usuario con el proveedor de identidad social.

> [!NOTE]
> El inicio de sesión del proveedor de identidad crea un registro en el inquilino de B2C, pero con un formato diferente al de las cuentas locales, ya que llamará a la referencia del proveedor de identidad social externo para la autenticación. El usuario puede usar la misma dirección de correo electrónico en todos los proveedores de identidad social, lo que significa que el nombre de usuario del correo electrónico utilizado para la autenticación puede no ser exclusivo del inquilino. Azure AD B2C solo exigirá que los usuarios tengan una dirección de correo electrónico única en las cuentas locales de B2C.

Antes de poder agregar un proveedor de identidad social para la autenticación, debe ir al portal del proveedor de identidad y configurar una aplicación de proveedor de identidad como se indica en la documentación de Azure AD B2C. A continuación se proporciona una lista de vínculos a la documentación.

- [Amazon](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (Inquilino único)](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Cuenta Microsoft](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Agregar y configurar un proveedor de identidad social

Para agregar y configurar un proveedor de identidad social, siga estos pasos.  

1. En el portal de Azure, vaya a **Proveedores de identidad**.
1. Seleccione **Agregar**. Aparece la pantalla **Agregar proveedor de identidad**.
1. En **Nombre**, introduzca el nombre que se mostrará a los usuarios en la pantalla de inicio de sesión.
1. En **Tipo de proveedor de identidad**, seleccione un proveedor de identidad de la lista.
1. Seleccione **Aceptar**.
1. Seleccione **Configurar este proveedor de identidad** para acceder a la pantalla **Configurar el proveedor de identidad social**.
1. En **Id. de cliente**, introduzca el identificador de cliente que se obtuvo de la configuración de la aplicación de proveedor de identidad.
1. En **Secreto de cliente**, introduzca el secreto que se obtuvo de la configuración de la aplicación de proveedor de identidad.
1. Adjunte el flujo de usuario para las directivas de inicio de sesión:
1. Vaya a **Azure AD B2C - Flujos de usuarios (directivas) \> {su directiva de inicio de sesión} \> Proveedores de identidad**.
1. Para adjuntar la directiva de flujo de usuario de registro e inicio de sesión, seleccione cada proveedor de identidad que haya configurado para su cuenta. Para probarlos, seleccione **Ejecutar flujo de usuario** para cada proveedor de identidad. Una nueva pestaña mostrará la página de inicio de sesión con el nuevo cuadro de selección del proveedor de identidad.

La siguiente imagen muestra ejemplos de pantallas **Agregar proveedor de identidad** y **Configurar el proveedor de identidad social** en Azure AD B2C.

![Agregar un proveedor de identidad social a su aplicación](./media/B2CImage_14.png)

La siguiente imagen muestra un ejemplo de cómo seleccionar proveedores de identidad en la página **Proveedores de identidad** de Azure AD B2C.

![Seleccionar cada proveedor de identidad social que hay que habilitar para su directiva](./media/B2CImage_16.png)

La siguiente imagen muestra un ejemplo de pantalla de inicio de sesión predeterminada con un botón de inicio de sesión del proveedor de identidad social.

> [!NOTE]
> Si utiliza las páginas personalizadas creadas en Commerce para sus flujos de usuario, los botones para proveedores de identidad social deberán agregarse utilizando las funciones de extensibilidad de la biblioteca del módulo de Commerce. Además, al configurar sus aplicaciones con un proveedor de identidad social específico, en algunos casos la URL o las cadenas de configuración pueden distinguir entre mayúsculas y minúsculas. Consulte las instrucciones de conexión de su proveedor de identidad social para obtener más información.
 
![Ejemplo de pantalla de inicio de sesión predeterminada que muestra el botón de inicio de sesión del proveedor de identidad social](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Actualizar la sede de Commerce con la nueva información de Azure AD B2C

Una vez completados los pasos de aprovisionamiento de Azure AD B2C antes mencionados, la aplicación Azure AD B2C debe registrarse en su entorno de Dynamics 365 Commerce.

Para actualizar la sede con la nueva información de Azure AD B2C, siga estos pasos.

1. En Commerce, vaya a **Parámetros compartidos de Commerce** y seleccione **Proveedores de identidad** en el menú de la izquierda.
1. En **Proveedores de identidad**, haga lo siguiente:
    1. En el cuadro **Emisor**, introduzca la dirección URL del emisor del proveedor de identidad. Para encontrar la dirección URL del emisor, consulte [Obtener dirección URL de emisor](#obtain-issuer-url) a continuación.
    1. En el cuadro **Nombre**, escriba un nombre para el registro de emisor.
    1. En el cuadro **Tipo**, introduzca **Azure AD B2C (id_token)**.
1. En **Partes dependientes**, con el elemento de proveedor de identidad B2C anterior seleccionado, haga lo siguiente:
    1. En el cuadro **Id. de cliente**, introduzca su id. de aplicación B2C. Este identificador se encuentra en el cuadro **Id. de aplicación** de la página de propiedades de la aplicación B2C.
    1. En el cuadro **Tipo**, introduzca **Público**.
    1. En el cuadro **Tipo de usuario**, introduzca **Cliente**.
1. En el panel de acciones, seleccione **Guardar**.
1. En el cuadro de búsqueda de Commerce, busque **Programación de distribución**
1. En el menú de navegación izquierdo de la página **Programaciones de distribución**, seleccione el trabajo **1110 Configuración global**.
1. En el panel de acciones, seleccione **Ejecutar ahora**.

### <a name="obtain-issuer-url"></a>Obtener dirección URL de emisor

Para obtener la dirección URL del emisor de proveedor de identidad, siga estos pasos.
1. En la página Azure AD B2C del portal de Azure, vaya a su flujo de usuario **Registro e inicio de sesión**.
1. Seleccione **Diseños de página** en el menú de navegación de la izquierda, en **Nombre del diseño** seleccione **Página unificada de registro o inicio de sesión** y luego seleccione **Ejecutar el flujo de usuarios**.
1. Asegúrese de que su aplicación esté configurada para su aplicación Azure AD B2C creada anteriormente y luego seleccione el enlace debajo del encabezado **Ejecutar el flujo de usuarios** que incluye ``.../.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``.
1. Se muestra una página de metadatos en la pestaña de su navegador. Copie la URL del emisor del proveedor de identidad (el valor de **"editor"**).
   - Ejemplo: ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.
 
**O**: para construir la misma URL de metadatos manualmente, siga los siguientes pasos.

1. Utilice su directiva y su inquilino de B2C para crear una dirección URL de metadatos con el siguiente formato: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Ejemplo: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.
1. Introduzca la dirección URL de metadatos en la barra de direcciones del explorador.
1. En los metadatos, copie la dirección URL del emisor del proveedor de identidad (el valor de **"emisor"**).
    - Ejemplo: ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Configurar su inquilino de B2C en el generador de sitios de Commerce

Una vez configurado el inquilino de Azure AD B2C, debe configurar el inquilino de B2C en el generador de sitios de Commerce. Los pasos de configuración incluyen recopilar información de la aplicación B2C desde el portal de Azure, introducir esa información de la aplicación B2C en el generador de sitios y, a continuación, asociar la aplicación B2C a su sitio y canal.

### <a name="collect-the-required-application-information"></a>Recopilar la información de aplicación necesaria

Para recopilar la información de la aplicación necesaria, siga estos pasos.

1. En el portal de Azure, vaya a **Inicio \> Azure AD B2C - Aplicaciones**.
1. Seleccione la aplicación y, a continuación, en el panel de navegación izquierdo, seleccione **Propiedades** para obtener los detalles de la aplicación.
1. En el cuadro **Id. de aplicación**, recopile el Id. de la aplicación B2C creada en el inquilino de B2C. Posteriormente, este identificador se introducirá como **GUID de cliente** en el generador de sitios.
1. En **URL de respuesta**, recopile la dirección URL de respuesta.
1. Vaya a **Inicio \> Azure AD B2C - Flujos de usuario (directivas)** y, a continuación, recopile los nombres de cada directiva de flujo de usuario.

La siguiente imagen muestra un ejemplo de la página **Azure AD B2C - Aplicaciones**.

![Ir a la aplicación B2C en el inquilino](./media/B2CImage_19.png)

La siguiente imagen muestra un ejemplo de la página **Propiedades** de una aplicación en Azure AD B2C. 

![Copiar el id. de aplicación desde la página Propiedades de la aplicación B2C](./media/B2CImage_21.png)

La siguiente imagen muestra un ejemplo de directivas de flujo de usuario en la página **Azure AD B2C - Flujos de usuarios (directivas)**.

![Recopilar los nombres de cada flujo de directiva de B2C](./media/B2CImage_22.png)

### <a name="enter-your-aad-b2c-tenant-application-information-into-commerce"></a>Introducir en Commerce la información de su aplicación de inquilino de AAD B2C

Debe introducir los detalles del inquilino de Azure AD B2C en el generador de sitios de Commerce antes de asociar el inquilino de B2C a sus sitios.

Para agregar a Commerce la información de su aplicación de inquilino de AAD B2C, siga estos pasos.

1. Inicie sesión como administrador en el generador de sitios de Commerce para su entorno.
1. En el panel de navegación izquierdo, seleccione el nodo **Configuración de inquilino** para expandirlo.
1. En **Configuración de inquilino**, seleccione **Configuración de B2C**. 
1. En la ventana principal, junto a **Aplicaciones B2C**, seleccione **Administrar**. (Si su inquilino aparece en la lista de aplicaciones B2C, significa que ya lo agregó un administrador. Compruebe que los elementos del paso 6 a continuación correspondan a su aplicación B2C).
1. Seleccione **Agregar aplicación B2C**.
1. Introduzca los siguientes elementos obligatorios en el formulario que se muestra, utilizando los valores del inquilino de B2C y la aplicación B2C. Los campos que no son obligatorios (los que no muestran un asterisco) pueden dejarse en blanco.

    - **Nombre de la aplicación**: el nombre de la aplicación B2C (por ejemplo, "Fabrikam B2C").
    - **Nombre del inquilino**: el nombre de su inquilino B2C (por ejemplo, use "fabrikam" si el dominio aparece como "fabrikam.onmicrosoft.com" para el inquilino B2C). 
    - **Id. de directiva de restablecimiento de contraseña**: el id. de la directiva del flujo de usuario de restablecimiento de contraseña (por ejemplo, "B2C_1_PasswordReset").
    - **Id. de directiva de registro e inicio de sesión**: el id. de la directiva de registro e inicio de sesión (por ejemplo, "B2C_1_signup_signin").
    - **GUID del cliente**: el id. de la aplicación B2C (por ejemplo, "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6").
    - **Id. de directiva de edición de perfil**: el id. de la directiva del flujo de usuario de edición de perfil (por ejemplo, "B2C_1A_ProfileEdit").

1. Seleccione **Aceptar**. Ahora debería ver el nombre de su aplicación B2C en la lista.
1. Seleccione **Guardar** para guardar los cambios.

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Asociar la aplicación B2C a su sitio y canal

> [!WARNING]
> Si su sitio ya está asociado a una aplicación B2C, al cambiar a una aplicación B2C distinta se eliminarán las referencias actuales establecidas para los usuarios que ya se han registrado en este entorno. Si se hace el cambio, las credenciales asociadas con la aplicación B2C asignada actualmente no estarán disponibles para los usuarios. 
> 
> Solo debe actualizar la aplicación B2C si va a configurar la aplicación B2C del canal por primera vez o si tiene la intención de hacer que los usuarios vuelvan a registrarse con nuevas credenciales para este canal con la nueva aplicación B2C. Tenga cuidado al asociar canales a aplicaciones B2C, y asigne nombres claros a las aplicaciones. Si un canal no se asocia a una aplicación B2C en los pasos siguientes, los usuarios que inicien sesión en ese canal del sitio se introducirán en la aplicación B2C que se muestra como **predeterminada** en la lista **Configuración del inquilino \> Configuración de B2C** de aplicaciones B2C.

Para asociar la aplicación B2C a su sitio y canal, siga estos pasos.

1. Vaya a su sitio en el generador de sitios de Commerce.
1. En el panel de navegación izquierdo, seleccione **Valores de configuración del sitio** para expandirlo
1. Bajo **Configuración del sitio**, seleccione **Canales**.
1. En la ventana principal bajo **Canales**, seleccione su canal.
1. En el panel de propiedades del canal a la derecha, seleccione el nombre de su aplicación B2C en el menú desplegable **Seleccionar aplicación B2C**.
1. Seleccione **Cerrar** y, a continuación, seleccione **Guardar y publicar**.

## <a name="additional-b2c-information"></a>Información de B2C adicional

### <a name="customer-migration"></a>Migración de clientes

Si se está planteando la posibilidad de migrar registros de clientes desde una plataforma de proveedor de identidad anterior, trabaje con el equipo de Dynamics 365 Commerce para revisar sus necesidades de migración de clientes.

Para adicional obtener documentación adicional de Azure AD B2C sobre migración de clientes, consulte [Migrar usuarios a Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Directivas personalizadas

Para obtener información adicional sobre la personalización de las interacciones y los flujo de directiva de Azure AD más allá de lo que ofrecen las directivas estándar de B2C, consulte [Directivas personalizadas en Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Administrador secundario

Se puede agregar una cuenta de administrador secundario opcional en la sección **Usuarios** del inquilino de B2C. Puede ser una cuenta directa o una cuenta general. Si necesita compartir una cuenta entre los recursos del equipo, también puede crear una cuenta común. Por la confidencialidad de los datos almacenados en Azure AD B2C, una cuenta común debe supervisarse estrechamente siguiendo los procedimientos de seguridad de la empresa.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Implementar un inquilino nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Asociar un sitio de Dynamics 365 Commerce con un canal en línea](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

[Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-B2C-tenants.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
