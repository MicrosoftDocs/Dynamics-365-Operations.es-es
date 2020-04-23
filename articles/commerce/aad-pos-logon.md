---
title: Habilitar autenticación Azure Active Directory para el inicio de sesión PDV
description: Este tema explica cómo configurar la experiencia de inicio de sesión para Microsoft Dynamics 365 Commerce punto de venta (PDV) para que use la autenticación Azure Active Directory.
author: boycezhu
manager: annbe
ms.date: 03/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: f030e8382627191dd32d855e15432fc85dca4bbd
ms.sourcegitcommit: 1789a78de1cbeac19d96767812df653a191c67e9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2020
ms.locfileid: "3100389"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a>Habilitar autenticación Azure Active Directory para el inicio de sesión PDV
[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Muchos clientes que usan Microsoft Dynamics 365 Commerce también usan otros Microsoft Cloud Services, y podrían usar Azure Active Directory (Azure AD) para administrar las credenciales de usuario para esos servicios. En esos casos, los clientes pueden querer usar la misam cuenta Azure AD en todas las aplicaciones. Este tema explica cómo configurar la experiencia de inicio de sesión de Commerce punto de venta (PDV) para usar la autenticación Azure AD.

## <a name="configure-azure-ad-authentication"></a>Configurar la autenticación Azure AD

Para hacer que Azure AD esté disponible como método de autenticación para el inicio de sesión PDV para una tienda, debe configurar los ajustes del perfil de funcionalidad de la tienda y luego aplicar esa configuración a los clientes PDV.

Para configurar un perfil de funcionalidad, siga estos pasos.

1. Vaya a **Retail y Commerce** \> **Configuración de canal** \> **Configuración de PDV** \> **Perfiles de PDV** \> **Perfiles de funcionalidad**.
1. Seleccione el perfil de funcionalidad para cambiar.
1. En la ficha desplegable **Funciones**, en la sección **Inicio de sesión del personal de PDV**, cambie el valor del campo **Método de autenticación de inicio de sesión** de **ID de personal y contraseña** a **Azure Active Directory**.

Por defecto, todos los perfiles de funcionalidad usan **ID de personal y contraseña** como el método de autenticación PDV. Por lo tanto, debe cambiar el valor de **Método de autenticación de inicio de sesión** si quiere usar Azure AD. Todas las tiendas minoristas que estén vinculadas al perfil de funcionalidad seleccionado se verán afectadas por este cambio.

Para aplicar la configuración a los clientes PDV, siga estos pasos.

1. Vaya a **Retail y Commerce** \> **TI de Retail y Commerce** \> **Programación de distribución**.
1. Ejecute la programación de distribución **1070** (**Configuración del canal**).

> [!NOTE]
> La autenticación Azure AD requiere una conexión a Internet. No funcionará cuando PDV esté en modo sin conexión.

## <a name="associate-an-azure-ad-account-with-a-worker"></a>Asociar una cuenta Azure AD con un trabajador

Antes de que un trabajador de la tienda pueda usar una cuenta Azure AD para iniciar sesión en la aplicación PDV, la cuenta de Azure AD debe estar asociada con ese trabajador.

Para asociar una cuenta de Azure AD con un trabajador, siga estos pasos.

1. Vaya a **Retail y Commerce** \> **Empleados** \> **Trabajadores**.
1. Abra la página de detalles para un trabajador.
1. En el panel de acciones, en la pestaña **Commerce**, en el grupo **Identidad externa**, seleccione **Asociar identidad existente**.
1. En el cuadro de diálogo **Usar identidad externa existente**, seleccione **Buscar usando correo electrónico**, introduzca una direcciónde correo electrónico Azure AD y luego seleccione **Buscar**.
1. Seleccione la cuenta Azure AD cuenta que se devuelve y luego seleccione **Aceptar**.

Los campos **Alias**, **UPN** y **Sub identificador externo** en la pestaña **Commerce** de la página de detalles del trabajador se rellenarán.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar la funcionalidad de inicio de sesión extendido para MPOS y Cloud POS](extended-logon.md)

[Crear un perfil de funcionalidad comercial](retail-functionality-profile.md)

[Configurar un trabajador](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)