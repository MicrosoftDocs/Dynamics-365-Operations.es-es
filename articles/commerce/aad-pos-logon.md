---
title: Configurar la autenticación de Azure Active Directory para el inicio de sesión de PDV
description: Este artículo explica cómo configurar Azure Active Directory como método de autenticación en punto de venta de Microsoft Dynamics 365 Commerce .
author: boycezhu
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 9ef9d79e319b95e6c7f531ed2a5886b3f1e85d27
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277126"
---
# <a name="configure-azure-active-directory-authentication-for-pos-sign-in"></a>Configurar la autenticación de Azure Active Directory para el inicio de sesión de PDV

[!include [banner](includes/banner.md)]

Este artículo explica cómo configurar Azure Active Directory (Azure AD) como método de autenticación en punto de venta (PDV) de Microsoft Dynamics 365 Commerce.

Los minoristas que utilizan Dynamics 365 Commerce junto con otros servicios en la nube de Microsoft, como Microsoft Azure, Microsoft 365 y Microsoft Teams normalmente quieren usar Azure AD para la gestión centralizada de las credenciales de usuario para una experiencia de inicio de sesión segura y sin problemas en todas las aplicaciones. Para usar la autenticación de Azure AD para PDV de Commerce, primero debe configurar Azure AD como método de autenticación en la sede de Commerce.

## <a name="configure-pos-authentication-method"></a>Configurar el método de autenticación de PDV

Para configurar el método de autenticación de PDV en la sede central de Commerce, siga estos pasos.
    
1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad** y seleccione un perfil de funcionalidad a cambiar.
1. En la sección **Inicio de sesión del personal de PDV** de la ficha desplegable **Funciones**, seleccione la opción de método de autenticación que desee de la lista desplegable **Método de autenticación de inicio de sesión**.

    El **Método de autenticación de inicio de sesión** tiene tres opciones:
    
    - **Id. personal y contraseña**: esta opción predeterminada requiere que los usuarios de PDV introduzcan una id. personal y una contraseña para iniciar sesión en el PDV y acceder a la funcionalidad de invalidación del administrador.
    - **Azure AD sin inicio de sesión único**: esta opción requiere que los usuarios de PDV utilicen las credenciales de Azure AD para iniciar sesión en el PDV y acceder a la funcionalidad de invalidación del administrador de acceso. Cuando el cliente PDV se actualiza o se vuelve a abrir, el usuario del PDV debe proporcionar credenciales de Azure AD para iniciar sesión nuevamente.
    - **Azure AD con inicio de sesión único**: cuando se selecciona esta opción, los usuarios de PDV pueden iniciar sesión en PDV en la nube (CPOS) usando credenciales de Azure AD activas que están siendo utilizadas por otras aplicaciones web en el mismo navegador web, o inicie sesión en PDV moderno (MPOS) usando credenciales de Azure AD registradas en Windows. Ambos métodos permiten iniciar sesión sin necesidad de introducir credenciales de Azure AD en la pantalla de inicio de sesión de PDV. Sin embargo, para acceder a la funcionalidad de invalidación del administrador de PDV seguirá siendo necesario iniciar sesión con credenciales de Azure AD.

1. Vaya a **Minorista y comercio > TI de minorista y comercio TI > Programa de distribución** y ejecute el trabajo **1070 (configuración de canal)** para sincronizar la configuración de perfil de funcionalidad más reciente para los clientes PDV.

> [!NOTE]
> - La opción de método de autenticación de **Azure AD sin inicio de sesión único** sustituye a la opción **Azure Active Directory** en Commerce, versión 10.0.18 y anteriores.
> - La autenticación de Azure AD requiere una conexión a Internet activa y no funcionará cuando el PDV esté fuera de línea.

## <a name="associate-azure-ad-accounts-with-pos-users"></a>Asociar cuentas de Azure AD con usuarios de PDV

Para usar Azure AD como método de autenticación PDV, debe asociar cuentas de Azure AD con usuarios de PDV en la sede de Commerce. 

Para asociar cuentas de Azure AD cuentas con usuarios de PDV en la sede de Commerce, siga estos pasos.
    
1. Vaya a **Minorista y comercio > Empleados > Trabajadores** y abra un registro de trabajador.
1. En el panel Acciones, seleccione la pestaña **Commerce** y, en **Identidad externa**, seleccione **Asociar identidad existente**. 
1. En el cuadro de diálogo **Usar identidad externa existente**, seleccione **Buscar usando correo electrónico**, introduzca una direcciónde correo electrónico Azure AD y luego seleccione **Buscar**.
1. Seleccione la cuenta de Azure AD que se devuelve y luego seleccione **Aceptar**.

Después de los pasos de configuración anteriores, los campos **Alias**, **UPN** y **Subidentificador externo** de la pestaña **Commerce** de la página de detalles del trabajador se rellenarán.

Debe ejecutar el trabajo **1060 (personal)** en **Minorista y comercio> TI de minorista y comercio > Programa de distribución** para sincronizar el último usuario de PDV y los datos de la cuenta de Azure AD con el canal.

> [!NOTE]
> Como práctica recomendada, después de actualizar la información del trabajador, como contraseña, permiso de PDV, cuenta de Azure AD asociada o la libreta de direcciones de los empleados en la sede de Commerce, se recomienda encarecidamente ejecutar el trabajo **1060 (personal)** para sincronizar la información más reciente del trabajador con el canal. De esa forma, el cliente PDV puede obtener los datos correctos para la autenticación del usuario y las comprobaciones de autorización.

## <a name="pos-lock-register-and-sign-out-with-azure-ad-authentication"></a>Registro de bloqueo de PDV y cierre de sesión con autenticación de Azure AD

Lo siguiente ocurre cuando el PDV está configurado para usar el método de autentificación de Azure AD:

- La función **Bloquear registro** no estará disponible en la aplicación PDV. 
- La función **Bloquear automáticamente** se comportará igual que la función **Cerrar sesión automáticamente**.
- Si el usuario de PDV selecciona **Cerrar sesión**, se le pedirá al usuario que inicie sesión con credenciales de Azure AD la próxima vez que se inicie el PDV, independientemente de si el inicio de sesión único está habilitado.

## <a name="manager-override-functionality-with-azure-ad-authentication"></a>Funcionalidad de invalidación del administrador con autenticación Azure AD

Cuando el PDV está configurado para usar autenticación de Azure AD, la función de invalidación del administrador abrirá un cuadro de diálogo que solicita las credenciales de Azure AD de usuario del administrador. Una vez que se aprueba el inicio de sesión del administrador, las credenciales de Azure AD del administrador se eliminarán y las credenciales del usuario anterior de Azure AD se utilizarán para operaciones posteriores de PDV.

> [!NOTE]
> - En las versiones de Commerce 10.0.18 y anteriores, la función de invalidación del administrador no admite Azure AD. Se requiere una id. personal y contraseña de incluso si el PDV está configurado para usar el método de autenticación de Azure AD.
> - Cuando utilice CPOS con el navegador web Safari en un dispositivo Apple iOS, primero debe desactivar **Bloquear emergentes** en la configuración de Safari para que la funcionalidad de invalidación del administrador trabaje con autenticación de Azure AD. 

## <a name="security-best-practices-for-azure-ad-based-pos-authentication-on-shared-devices"></a>Mejores prácticas de seguridad para autenticación en PDV de Azure AD en dispositivos compartidos

Muchos minoristas configuran su entorno de tienda minorista de manera que varios usuarios necesitan acceder a la aplicación PDV desde un dispositivo físico compartido. En ese contexto, si bien el inicio de sesión único proporciona una experiencia de autenticación conveniente y sin problemas, también puede crear una laguna de seguridad en la que el usuario actual del PDV puede no darse cuenta de que se están utilizando las credenciales de otro usuario para realizar transacciones u operaciones en el PDV. Antes de configurar el PDV para utilizar el método de autenticación de Azure AD, se recomienda encarecidamente revisar su política de seguridad y la configuración de inicio de sesión del dispositivo compartido para decidir qué opción es la más adecuada.

- Si su entorno minorista utiliza una cuenta compartida (por ejemplo, una cuenta local) para el inicio de sesión del dispositivo físico, se recomienda utilizar la opción de **Azure AD sin inicio de sesión único**. Esto asegura que cada usuario de PDV proporcione explícitamente las credenciales de Azure AD para iniciar sesión en el PDV.
- Si su entorno minorista requiere que los empleados utilicen sus propias cuentas de Azure AD para iniciar sesión en el PDV y el dispositivo físico que aloja, se recomienda utilizar la opción **Azure AD con inicio de sesión único**.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un trabajador](tasks/worker.md)

[Crear un perfil de funcionalidad comercial](retail-functionality-profile.md)


[Configurar la funcionalidad de inicio de sesión extendido para MPOS y Cloud POS](extended-logon.md)

[Prácticas recomendadas de seguridad para PDV en la nube en entornos compartidos](dev-itpro/secure-retail-cloud-pos.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
