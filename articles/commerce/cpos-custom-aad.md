---
title: Configurar CPOS para usar una aplicación de Azure AD personalizada
description: Este artículo explica cómo configurar Cloud POS (CPOS) para usar una aplicación Azure Active Directory (Azure AD) personalizada.
author: boycez
ms.date: 11/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 5e4ff797410e1e94869cc37684e7622ec0d97842
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746270"
---
# <a name="configure-cpos-to-use-a-custom-azure-ad-app"></a>Configurar CPOS para usar una aplicación de Azure AD personalizada

[!include [banner](includes/banner.md)]

Por defecto, Cloud POS (CPOS) en Microsoft Dynamics 365 Commerce apunta a una aplicación de Microsoft propia registrada en Azure Active Directory (Azure AD). Por lo tanto, puede utilizar CPOS sin tener que realizar ningún cambio en Azure AD. Sin embargo, es posible que desee apuntar su instancia de CPOS a unaaplicación de Azure AD personalizada que usted controla. Este artículo explica cómo configurar CPOS para usar una aplicación Azure AD personalizada.

## <a name="set-up-a-custom-retail-server-app-in-azure-ad"></a>Configure una aplicación de servidor minorista personalizada en Azure AD

Para crear y configurar una aplicación de servidor minorista personalizada en Azure AD, sigue estos pasos.

1. Inicie sesión en el [Centro de administración de Azure Active Directory](https://aad.portal.azure.com) utilizando la cuenta de usuario de Azure AD. La cuenta de usuario no tiene que tener permisos de administrador.
1. Seleccionar **Azure Active Directory**.
1. Seleccione **Registros de aplicaciones** y luego seleccione **Nuevo registro** para abrir el cuadro de diálogo **Registrar una aplicación**.
1. Establezca los campos siguientes:

    - **Nombre**: escriba un nombre personalizado para la aplicación. Por ejemplo, ingrese **Servidor minorista personalizado**.
    - **Tipos de cuenta admitidos** seleccione la opción predeterminada, **Cuentas en este directorio de organización solo (Solo Microsoft - un solo inquilino)**.
    - **URI de redirección**: este campo es opcional. Dejalo en blanco.
    - **Id. de árbol de servicio**: este campo es opcional. Dejalo en blanco.
    
1. Seleccione **Registrar**. Aparece la página de configuración de la aplicación recién registrada.
1. En la sección **Visión general \> Esenciales**, seleccione **Agregar un URI de ID de aplicación** y luego seleccione **Establecer** junto a **URI de ID de aplicación**. Tome nota del valor sugerido y luego seleccione **Guardar** para aceptar ese valor. 
1. Seleccione **Agregar un ámbito** y luego configure los siguientes campos:

    - **Nombre de ámbito** - Especifique un nombre personalizado para el ámbito. Por ejemplo, ingrese **Legacy.Access.Full**.
    - **Quién puede consentir** – Especifique si tanto los administradores como los usuarios o solo los administradores pueden dar su consentimiento, según las políticas de seguridad de su organización.
    - **Nombre para mostrar del consentimiento del administrador** - Introduzca un nombre para mostrar. Por ejemplo, ingrese **Acceder a servidor minorista**.
    - **Descripción de consentimiento de administrador**: escriba una descripción. Por ejemplo, ingrese **Da acceso a API de Retail Server**.

1. Seleccione **Agregar alcance** para completar el proceso de creación del ámbito.

## <a name="set-up-a-custom-cpos-app-in-azure-ad"></a>Configurar una aplicación CPOS en Azure AD

> [!IMPORTANT]
> Si está actualizando una aplicación CPOS personalizada existente de Azure AD que se creó antes de la versión 10.0.21 de Commerce, siga los pasos en [Actualizar una aplicación CPOS personalizada existente de Azure AD creada antes de la versión Commerce 10.0.21](#upgrade-an-existing-custom-cpos-azure-ad-app-created-before-commerce-version-10021).

Para crear y configurar una aplicación CPOS en Azure AD, siga estos pasos.

1. Inicie sesión en el [Centro de administración de Azure Active Directory](https://aad.portal.azure.com) utilizando la cuenta de usuario de Azure AD. La cuenta de usuario no tiene que tener permisos de administrador.
1. Seleccionar **Azure Active Directory**.
1. Seleccione **Registros de aplicaciones** y luego seleccione **Nuevo registro** para abrir el cuadro de diálogo **Registrar una aplicación**.
1. Establezca los campos siguientes:

    - **Nombre**: escriba un nombre para la aplicación. Por ejemplo, ingrese **Punto de venta personalizado en la nube**.
    - **Tipos de cuenta admitidos** seleccione la opción predeterminada, **Cuentas en este directorio de organización solo (Solo Microsoft - un solo inquilino)**.
    - **URI de redirección** - Seleccione **Solicitud de una sola página (SPA)** en la lista desplegable y luego ingrese su CPOS URI.
    - **Id. de árbol de servicio**: este campo es opcional. Dejalo en blanco.

1. Seleccione **Registrar**. Aparece la página de configuración de la aplicación recién registrada.
1. En la sección **Manifiesto**, configure los parámetros **oauth2AllowIdTokenImplicitFlow** y **oauth2AllowImplicitFlow** como **verdadero** y luego seleccione **Guardar**.
1. En la sección **Configuración de fichas**, siga estos pasos para agregar dos reclamos:

    1. Seleccione **Añadir reclamación opcional**. Establezca el campo **Tipo de token** en **Id.** y, a continuación, seleccione la reclamación **sid**. Seleccione **Agregar**.
    1. Seleccione **Añadir reclamación opcional**. Establezca el campo **Tipo de token** en **Acceso** y, a continuación, seleccione la reclamación **sid**. Seleccione **Agregar**.

1. En la sección **Permisos de API**, seleccione **Agregar un permiso**.
1. En la pestaña **API que usa mi organización**, busque la aplicación Retail Server que creó en la sección [Configure una aplicación de servidor minorista personalizada en Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad). Luego seleccione **Agregar permisos**.
1. En la sección **Visión general**, tome nota del valor del campo **ID de la aplicación (cliente)**.

### <a name="upgrade-an-existing-custom-cpos-azure-ad-app-created-before-commerce-version-10021"></a>Actualizar una aplicación CPOS personalizada existente de Azure AD aplicación creada antes de la versión 10.0.21 de Commerce

Para actualizar una aplicación CPOS personalizada existente de Azure AD aplicación creada antes de la versión 10.0.21 de Commerce, siga estos pasos. 

1. Abra su aplicación CPOS personalizada de Azure AD en el Azure Portal.
1. Seleccione la pestaña **Autenticación**.
1. Copie y guarde el URI de redireccionamiento original del tipo **Web** para usarlo más tarde y luego elimínelo.
1. Seleccione **Agregar una plataforma** y luego seleccione **Solicitud de una sola página (SPA)**.
1. Agregue el URI de redirección web original copiado anteriormente a la plataforma SPA.
1. En la sección **Configuración de fichas**, siga estos pasos para agregar dos reclamos:
    1. Seleccione **Añadir reclamación opcional**. Establezca el campo **Tipo de token** en **Id.** y, a continuación, seleccione la reclamación **sid**. Seleccione **Agregar**.
    1. Seleccione **Añadir reclamación opcional**. Establezca el campo **Tipo de token** en **Acceso** y, a continuación, seleccione la reclamación **sid**. Seleccione **Agregar**.

## <a name="update-the-cpos-configuration-file"></a>Actualizar el archivo de configuración de CPOS

Abra el archivo de CPOS config.json y realice las siguientes actualizaciones en él.

1. Reemplace el valor de clave **AADClientId** con el valor **ID de la aplicación (cliente)** de la aplicación CPOS personalizada que creó en la sección [Configurar una aplicación CPOS personalizada en Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
1. Reemplace el valor de clave **AADRetailServerResourceId** con el valor **URI de ID de aplicación** de la aplicación de Retail Server personalizada que creó en la sección [Configurar una aplicación Retail Server personalizada en Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

CPOS utilizará ambos parámetros cuando envíe solicitudes a Azure AD para adquirir un token de seguridad.

## <a name="update-identity-providers-settings-in-commerce-headquarters"></a>Actualizar la configuración de los proveedores de identidad en Commerce headquarters

Luego, debe actualizar la configuración de los proveedores de identidad en Commerce headquarters.

1. En In Commerce Headquarters, abra la página **Parámetros compartidos de Commerce**.
1. En la pestaña **Proveedores de identidad**, en la sección **Proveedores de identidad**, seleccione la fila donde el campo **Tipo** se establezca en **Azure Active Directory** y el campo **Editor** señale al inquilino de Azure AD. Esta configuración declara que trabajará con cuadrículas secundarias que contienen los datos relacionados con el proveedor de identidad que corresponde a su inquilino de Azure AD.
1. En la sección **Partes que confían**, seleccione **Agregar** para agregar una fila.
1. Establezca los campos siguientes:

    - **ClientId** – Introduzca el valor de **Id. de aplicación (cliente)** de la aplicación CPOS personalizada que creó en la sección [Configurar una aplicación CPOS personalizada en Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
    - **Tipo** – Seleccione **Público**.
    - **Tipo de usuario** - Seleccione **Trabajador**.

1. Seleccione la fila que acaba de agregar. La sección **ID de recursos del servidor** bajo la sección **Partes que confían** muestra los ID de la aplicación del servidor minorista a los que puede acceder la aplicación que seleccionó en la cuadrícula **Partes que confían**.
1. En la sección **ID de recursos del servidor**, seleccione **Agregar** para agregar una fila.
1. En el campo **Id. de recurso de servidor**, introduzca el valor **URI de ID de aplicación** de la aplicación de Retail Server personalizada que creó en la sección [Configurar una aplicación Retail Server personalizada en Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

    > [!IMPORTANT]
    > Todos los campos que se mencionan en los pasos anteriores distinguen entre mayúsculas y minúsculas. Los valores que introduzca deben coincidir exactamente con los valores configurados en el centro de administración de Azure AD.

1. Vaya a **TI de Retail y Commerce \> Programación de distribución** y ejecute el trabajo **1110** (**Configuración global**).

Ahora puede activar dispositivos CPOS usando su propia aplicación Azure AD.

## <a name="additional-resources"></a>Recursos adicionales

[Activación de dispositivo de punto de venta (PDV)](dev-itpro/retail-device-activation.md)

[Administrar cuentas de activación y validar dispositivos](set-up-activation-accounts-validate-devices-hq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
