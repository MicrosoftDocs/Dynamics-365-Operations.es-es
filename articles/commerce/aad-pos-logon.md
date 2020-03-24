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
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a><span data-ttu-id="6998f-103">Habilitar autenticación Azure Active Directory para el inicio de sesión PDV</span><span class="sxs-lookup"><span data-stu-id="6998f-103">Enable Azure Active Directory authentication for POS sign-in</span></span>
[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="6998f-104">Muchos clientes que usan Microsoft Dynamics 365 Commerce también usan otros Microsoft Cloud Services, y podrían usar Azure Active Directory (Azure AD) para administrar las credenciales de usuario para esos servicios.</span><span class="sxs-lookup"><span data-stu-id="6998f-104">Many customers who use Microsoft Dynamics 365 Commerce also use other Microsoft cloud services, and they might use Azure Active Directory (Azure AD) to manage user credentials for those services.</span></span> <span data-ttu-id="6998f-105">En esos casos, los clientes pueden querer usar la misam cuenta Azure AD en todas las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6998f-105">In those cases, the customers might want to use the same Azure AD account across applications.</span></span> <span data-ttu-id="6998f-106">Este tema explica cómo configurar la experiencia de inicio de sesión de Commerce punto de venta (PDV) para usar la autenticación Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6998f-106">This topic explains how to configure the Commerce point of sale (POS) sign-in experience to use Azure AD authentication.</span></span>

## <a name="configure-azure-ad-authentication"></a><span data-ttu-id="6998f-107">Configurar la autenticación Azure AD</span><span class="sxs-lookup"><span data-stu-id="6998f-107">Configure Azure AD authentication</span></span>

<span data-ttu-id="6998f-108">Para hacer que Azure AD esté disponible como método de autenticación para el inicio de sesión PDV para una tienda, debe configurar los ajustes del perfil de funcionalidad de la tienda y luego aplicar esa configuración a los clientes PDV.</span><span class="sxs-lookup"><span data-stu-id="6998f-108">To make Azure AD available as the authentication method for POS sign-in for a store, you must configure the settings of the store's functionality profile and then apply those setting to POS clients.</span></span>

<span data-ttu-id="6998f-109">Para configurar un perfil de funcionalidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6998f-109">To configure a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="6998f-110">Vaya a **Retail y Commerce** \> **Configuración de canal** \> **Configuración de PDV** \> **Perfiles de PDV** \> **Perfiles de funcionalidad**.</span><span class="sxs-lookup"><span data-stu-id="6998f-110">Go to **Retail and Commerce** \> **Channel setup** \> **POS setup** \> **POS profiles** \> **Functionality profiles**.</span></span>
1. <span data-ttu-id="6998f-111">Seleccione el perfil de funcionalidad para cambiar.</span><span class="sxs-lookup"><span data-stu-id="6998f-111">Select the functionality profile to change.</span></span>
1. <span data-ttu-id="6998f-112">En la ficha desplegable **Funciones**, en la sección **Inicio de sesión del personal de PDV**, cambie el valor del campo **Método de autenticación de inicio de sesión** de **ID de personal y contraseña** a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6998f-112">On the **Functions** FastTab, in the **POS staff logon** section, change the value of the **Logon Authentication Method** field from **Personnel ID and Password** to **Azure Active Directory**.</span></span>

<span data-ttu-id="6998f-113">Por defecto, todos los perfiles de funcionalidad usan **ID de personal y contraseña** como el método de autenticación PDV.</span><span class="sxs-lookup"><span data-stu-id="6998f-113">By default, all functionality profiles use **Personnel ID and Password** as the POS authentication method.</span></span> <span data-ttu-id="6998f-114">Por lo tanto, debe cambiar el valor de **Método de autenticación de inicio de sesión** si quiere usar Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6998f-114">Therefore, you must change the value of the **Logon Authentication Method** field if you want to use Azure AD.</span></span> <span data-ttu-id="6998f-115">Todas las tiendas minoristas que estén vinculadas al perfil de funcionalidad seleccionado se verán afectadas por este cambio.</span><span class="sxs-lookup"><span data-stu-id="6998f-115">Every retail store that is linked to the selected functionality profile will be affected by this change.</span></span>

<span data-ttu-id="6998f-116">Para aplicar la configuración a los clientes PDV, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6998f-116">To apply the settings to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="6998f-117">Vaya a **Retail y Commerce** \> **TI de Retail y Commerce** \> **Programación de distribución**.</span><span class="sxs-lookup"><span data-stu-id="6998f-117">Go to **Retail and Commerce** \> **Retail and Commerce IT** \> **Distribution schedule**.</span></span>
1. <span data-ttu-id="6998f-118">Ejecute la programación de distribución **1070** (**Configuración del canal**).</span><span class="sxs-lookup"><span data-stu-id="6998f-118">Run the **1070** (**Channel configuration**) distribution schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="6998f-119">La autenticación Azure AD requiere una conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="6998f-119">Azure AD authentication requires an internet connection.</span></span> <span data-ttu-id="6998f-120">No funcionará cuando PDV esté en modo sin conexión.</span><span class="sxs-lookup"><span data-stu-id="6998f-120">It won't work when POS is in offline mode.</span></span>

## <a name="associate-an-azure-ad-account-with-a-worker"></a><span data-ttu-id="6998f-121">Asociar una cuenta Azure AD con un trabajador</span><span class="sxs-lookup"><span data-stu-id="6998f-121">Associate an Azure AD account with a worker</span></span>

<span data-ttu-id="6998f-122">Antes de que un trabajador de la tienda pueda usar una cuenta Azure AD para iniciar sesión en la aplicación PDV, la cuenta de Azure AD debe estar asociada con ese trabajador.</span><span class="sxs-lookup"><span data-stu-id="6998f-122">Before a store worker can use an Azure AD account to sign in to the POS application, the Azure AD account must be associated with that worker.</span></span>

<span data-ttu-id="6998f-123">Para asociar una cuenta de Azure AD con un trabajador, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6998f-123">To associate an Azure AD account with a worker, follow these steps.</span></span>

1. <span data-ttu-id="6998f-124">Vaya a **Retail y Commerce** \> **Empleados** \> **Trabajadores**.</span><span class="sxs-lookup"><span data-stu-id="6998f-124">Go to **Retail and Commerce** \> **Employees** \> **Workers**.</span></span>
1. <span data-ttu-id="6998f-125">Abra la página de detalles para un trabajador.</span><span class="sxs-lookup"><span data-stu-id="6998f-125">Open the details page for a worker.</span></span>
1. <span data-ttu-id="6998f-126">En el panel de acciones, en la pestaña **Commerce**, en el grupo **Identidad externa**, seleccione **Asociar identidad existente**.</span><span class="sxs-lookup"><span data-stu-id="6998f-126">On the Action Pane, on the **Commerce** tab, in the **External identity** group, select **Associate existing identity**.</span></span>
1. <span data-ttu-id="6998f-127">En el cuadro de diálogo **Usar identidad externa existente**, seleccione **Buscar usando correo electrónico**, introduzca una direcciónde correo electrónico Azure AD y luego seleccione **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="6998f-127">In the **Use existing external identity** dialog box, select **Search using email**, enter an Azure AD email address, and then select **Search**.</span></span>
1. <span data-ttu-id="6998f-128">Seleccione la cuenta Azure AD cuenta que se devuelve y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6998f-128">Select the Azure AD account that is returned, and then select **OK**.</span></span>

<span data-ttu-id="6998f-129">Los campos **Alias**, **UPN** y **Sub identificador externo** en la pestaña **Commerce** de la página de detalles del trabajador se rellenarán.</span><span class="sxs-lookup"><span data-stu-id="6998f-129">The **Alias**, **UPN**, and **External sub identifier** fields on the **Commerce** tab of the worker's details page will be filled in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6998f-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6998f-130">Additional resources</span></span>

[<span data-ttu-id="6998f-131">Configurar la funcionalidad de inicio de sesión extendido para MPOS y Cloud POS</span><span class="sxs-lookup"><span data-stu-id="6998f-131">Set up extended logon functionality for MPOS and Cloud POS</span></span>](extended-logon.md)

[<span data-ttu-id="6998f-132">Crear un perfil de funcionalidad comercial</span><span class="sxs-lookup"><span data-stu-id="6998f-132">Create a retail functionality profile</span></span>](retail-functionality-profile.md)

[<span data-ttu-id="6998f-133">Configurar un trabajador</span><span class="sxs-lookup"><span data-stu-id="6998f-133">Configure a worker</span></span>](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)
