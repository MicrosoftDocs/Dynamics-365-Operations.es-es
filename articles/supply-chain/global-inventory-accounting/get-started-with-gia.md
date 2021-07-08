---
title: Introducción a la contabilidad de inventario global
description: Este tema describe cómo comenzar con la Contabilidad de inventario global.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 59f9db309312bbbc88b4fa47c12c4c02f09e7c6d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301707"
---
# <a name="get-started-with-global-inventory-accounting"></a><span data-ttu-id="30752-103">Introducción a la contabilidad de inventario global</span><span class="sxs-lookup"><span data-stu-id="30752-103">Get started with Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="30752-104">La contabilidad de inventario global permite realizar múltiples contabilidades de inventarios en los libros de contabilidad de inventario global que ha configurado.</span><span class="sxs-lookup"><span data-stu-id="30752-104">Global Inventory Accounting lets you do multiple inventory accountings in the Global Inventory Accounting ledgers that you've set up.</span></span> <span data-ttu-id="30752-105">Debe asociar cada libro de contabilidad de inventario global a una *convención*.</span><span class="sxs-lookup"><span data-stu-id="30752-105">You must associate each Global Inventory Accounting ledger with a *convention*.</span></span> <span data-ttu-id="30752-106">Una convención es una colección de los siguientes tipos de directivas contables:</span><span class="sxs-lookup"><span data-stu-id="30752-106">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="30752-107">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="30752-107">Cost object</span></span>
- <span data-ttu-id="30752-108">Base de medida de entrada</span><span class="sxs-lookup"><span data-stu-id="30752-108">Input measurement basis</span></span>
- <span data-ttu-id="30752-109">Suposición de flujo de costes</span><span class="sxs-lookup"><span data-stu-id="30752-109">Cost flow assumption</span></span>
- <span data-ttu-id="30752-110">Elemento de coste</span><span class="sxs-lookup"><span data-stu-id="30752-110">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="30752-111">Incluso después de haber activado la contabilidad de inventario global, aún puede hacer contabilidad de inventario en Microsoft Dynamics 365 Supply Chain Management como siempre.</span><span class="sxs-lookup"><span data-stu-id="30752-111">Even after you turn on Global Inventory Accounting, you can still do inventory accounting in Microsoft Dynamics 365 Supply Chain Management in the usual way.</span></span>

<span data-ttu-id="30752-112">La contabilidad de inventario global es un complemento.</span><span class="sxs-lookup"><span data-stu-id="30752-112">Global Inventory Accounting is an add-in.</span></span> <span data-ttu-id="30752-113">Para que sus funciones estén disponibles, debe instalarlo desde Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="30752-113">To make its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="30752-114">Puede elegir evaluarlo en un entorno de prueba antes de activarlo para entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="30752-114">You can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="30752-115">Actualmente, la contabilidad de inventario global no admite todas las funciones de administración de costos que están integradas en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="30752-115">Global Inventory Accounting doesn't currently support all the cost management features that are built into Supply Chain Management.</span></span> <span data-ttu-id="30752-116">Por lo tanto, es importante que evalúe si el conjunto de funciones que están disponibles actualmente cumplirá sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="30752-116">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a><span data-ttu-id="30752-117">Cómo obtener la vista previa pública de Contabilidad de inventario global</span><span class="sxs-lookup"><span data-stu-id="30752-117">How to get the Global Inventory Accounting public preview</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30752-118">Para utilizar la contabilidad de inventario global, debe tener un entorno de alta disponibilidad habilitado para LCS (no un entorno OneBox).</span><span class="sxs-lookup"><span data-stu-id="30752-118">To use Global Inventory Accounting, you must have an LCS-enabled high-availability environment (not a OneBox environment).</span></span> <span data-ttu-id="30752-119">Además, debe ejecutar Supply Chain Management versión 10.0.19 o posterior.</span><span class="sxs-lookup"><span data-stu-id="30752-119">Additionally, you must be running Supply Chain Management version 10.0.19 or later.</span></span>

<span data-ttu-id="30752-120">Para suscribirse a la vista previa pública de Contabilidad de inventario global, envíe su ID de entorno LCS por correo electrónico al [Equipo de contabilidad de inventario global](mailto:GlobalInventoryAccounting@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="30752-120">To sign up for the Global Inventory Accounting public preview, send your LCS environment ID by email to the [Global Inventory Accounting team](mailto:GlobalInventoryAccounting@service.microsoft.com).</span></span> <span data-ttu-id="30752-121">Una vez que haya sido aprobado para el programa, el equipo le enviará un correo electrónico de seguimiento que contiene una clave beta de Contabilidad de inventario global y los puntos finales de su servicio.</span><span class="sxs-lookup"><span data-stu-id="30752-121">After you're approved for the program, the team will send you a follow-up email that contains a Global Inventory Accounting beta key and your service endpoints.</span></span> <span data-ttu-id="30752-122">Después de recibir la clave beta, puede [instalar el complemento](#install).</span><span class="sxs-lookup"><span data-stu-id="30752-122">After you receive the beta key, you can [install the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="30752-123">Licencias</span><span class="sxs-lookup"><span data-stu-id="30752-123">Licensing</span></span>

<span data-ttu-id="30752-124">La contabilidad de inventario global tiene licencia junto con las funciones estándar de la contabilidad de inventario que están disponibles para Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="30752-124">Global Inventory Accounting is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="30752-125">No tiene que comprar una licencia adicional para usar la contabilidad de inventario global.</span><span class="sxs-lookup"><span data-stu-id="30752-125">You don't have to purchase an additional license to use Global Inventory Accounting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="30752-126">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="30752-126">Prerequisites</span></span>

### <a name="set-up-microsoft-power-platform-integration"></a><span data-ttu-id="30752-127">Configurar la integración de Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="30752-127">Set up Microsoft Power Platform integration</span></span>

<span data-ttu-id="30752-128">Antes de poder habilitar la funcionalidad de complemento, debe integrarse con Microsoft Power Platform siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="30752-128">Before you can enable add-in functionality, you must integrate with Microsoft Power Platform by following these steps.</span></span>

1. <span data-ttu-id="30752-129">Abra el entorno LCS donde desea agregar el servicio.</span><span class="sxs-lookup"><span data-stu-id="30752-129">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="30752-130">Vaya a **Detalles completos**.</span><span class="sxs-lookup"><span data-stu-id="30752-130">Go to **Full details**.</span></span>
1. <span data-ttu-id="30752-131">En la sección **Integración de Power Platform**, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="30752-131">In the **Power Platform Integration** section, select **Setup**.</span></span>
1. <span data-ttu-id="30752-132">En el cuadro de diálogo **Configuración del entorno de Power Platform**, seleccione la casilla de verificación y luego seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="30752-132">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="30752-133">Normalmente, la instalación tarda entre 60 y 90 minutos.</span><span class="sxs-lookup"><span data-stu-id="30752-133">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="30752-134">Después de la instalación del entrorno de Microsoft Power Platform se completa, la página muestra el nombre de su entorno.</span><span class="sxs-lookup"><span data-stu-id="30752-134">After setup of the Microsoft Power Platform environment is completed, the page shows the name of your environment.</span></span> <span data-ttu-id="30752-135">Además, la sección **Integración de Power Platform** muestra la declaración, "La configuración del entorno de Power Platform está completa".</span><span class="sxs-lookup"><span data-stu-id="30752-135">Additionally, the **Power Platform Integration** section shows the statement, "Power Platform environment setup is complete."</span></span> <span data-ttu-id="30752-136">La contabilidad de inventario global no requiere una aplicación de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="30752-136">Global Inventory Accounting doesn't require a dual-write application.</span></span>

<span data-ttu-id="30752-137">Para obtener más información, consulte [Configurar después de la implementación del entorno](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span><span class="sxs-lookup"><span data-stu-id="30752-137">For more information, see [Set up after environment deployment](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span></span>

### <a name="set-up-dataverse"></a><span data-ttu-id="30752-138">Configurar Dataverse</span><span class="sxs-lookup"><span data-stu-id="30752-138">Set up Dataverse</span></span>

<span data-ttu-id="30752-139">Antes de configurar Dataverse, agregue los principios del servicio Contabilidad de inventario global a su inquilino siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="30752-139">Before you set up Dataverse, add the Global Inventory Accounting service principles to your tenant by following these steps.</span></span>

1. <span data-ttu-id="30752-140">Instale el módulo Azure AD para Windows PowerShell v2 como se describe en [Instalar Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="30752-140">Install Azure AD Module for Windows PowerShell v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
1. <span data-ttu-id="30752-141">Ejecute el siguiente comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30752-141">Run the following PowerShell command.</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

<span data-ttu-id="30752-142">A continuación, cree usuarios de la aplicación para la contabilidad de inventario global en Dataverse siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="30752-142">Next, create application users for Global Inventory Accounting in Dataverse by following these steps.</span></span>

1. <span data-ttu-id="30752-143">Abra la URL de su entorno de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="30752-143">Open the URL of your Dataverse environment.</span></span>
1. <span data-ttu-id="30752-144">Ir **Configuración avanzada \> Sistema \> Seguridad \> Usuarios** y cree un usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="30752-144">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="30752-145">Use el campo **Vista** para cambiar la vista de página a *Usuarios de la aplicación*.</span><span class="sxs-lookup"><span data-stu-id="30752-145">Use the **View** field to change the page view to *Application users*.</span></span>
1. <span data-ttu-id="30752-146">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="30752-146">Select **New**.</span></span>
1. <span data-ttu-id="30752-147">Establezca el campo **Id. de aplicación** en *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span><span class="sxs-lookup"><span data-stu-id="30752-147">Set the **Application ID** field to *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span></span>
1. <span data-ttu-id="30752-148">Seleccione **Asignar rol** y luego seleccione *Administrador de sistema*.</span><span class="sxs-lookup"><span data-stu-id="30752-148">Select **Assign Role**, and then select *System Administrator*.</span></span> <span data-ttu-id="30752-149">Si hay un rol que se llama *Usuario de Common Data Service*, selecciónelo también.</span><span class="sxs-lookup"><span data-stu-id="30752-149">If there is a role that is named *Common Data Service User*, select it too.</span></span>
1. <span data-ttu-id="30752-150">Repita los pasos anteriores, pero establezca el campo **Id. de aplicación** en *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span><span class="sxs-lookup"><span data-stu-id="30752-150">Repeat the preceding steps, but set the **Application ID** field to *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span></span>

<span data-ttu-id="30752-151">Para obtener más información, consulte [Crear un usuario de aplicación](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="30752-151">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

<span data-ttu-id="30752-152">Si el idioma predeterminado de su instalación Dataverse no es en inglés, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="30752-152">If the default language of your Dataverse installation isn't English, follow these steps.</span></span>

1. <span data-ttu-id="30752-153">Vaya a **Configuración avanzada \> Administración \> Idiomas**.</span><span class="sxs-lookup"><span data-stu-id="30752-153">Go to **Advanced Setting \> Administration \> Languages**.</span></span>
1. <span data-ttu-id="30752-154">Seleccione *Inglés* (*LanguageCode = 1033*) y seleccione **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="30752-154">Select *English* (*LanguageCode=1033*), and then select **Apply**.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="30752-155">Instalar el complemento</span><span class="sxs-lookup"><span data-stu-id="30752-155">Install the add-in</span></span>

<span data-ttu-id="30752-156">Siga estos pasos para instalar el complemento y poder utilizar la Contabilidad de inventario global.</span><span class="sxs-lookup"><span data-stu-id="30752-156">Follow these steps to install the add-in so that you can use Global Inventory Accounting.</span></span>

1. <span data-ttu-id="30752-157">[Suscríbase](#sign-up) a la vista previa pública de Contabilidad de inventario global.</span><span class="sxs-lookup"><span data-stu-id="30752-157">[Sign up](#sign-up) for the Global Inventory Accounting public preview.</span></span>
1. <span data-ttu-id="30752-158">Inicie sesión en [LCS](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="30752-158">Sign in to [LCS](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="30752-159">Vaya a **Administración de funciones de vista previa**.</span><span class="sxs-lookup"><span data-stu-id="30752-159">Go to **Preview feature management**.</span></span>
1. <span data-ttu-id="30752-160">Seleccione el signo más (**+**).</span><span class="sxs-lookup"><span data-stu-id="30752-160">Select the plus sign (**+**).</span></span>
1. <span data-ttu-id="30752-161">En el campo **Código**, introduzca su clave beta de la contabilidad de inventario global.</span><span class="sxs-lookup"><span data-stu-id="30752-161">In the **Code** field, enter your add-in beta key for Global Inventory Accounting.</span></span> <span data-ttu-id="30752-162">(Debería haber recibido su clave beta por correo electrónico cuando se registró).</span><span class="sxs-lookup"><span data-stu-id="30752-162">(You should have received your beta key by email when you signed up.)</span></span>
1. <span data-ttu-id="30752-163">Seleccione **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="30752-163">Select **Unblock**.</span></span>
1. <span data-ttu-id="30752-164">Abra el entorno LCS donde desea agregar el servicio.</span><span class="sxs-lookup"><span data-stu-id="30752-164">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="30752-165">Vaya a **Detalles completos**.</span><span class="sxs-lookup"><span data-stu-id="30752-165">Go to **Full details**.</span></span>
1. <span data-ttu-id="30752-166">Vaya a **Integración de Power Platform** y seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="30752-166">Go to **Power Platform Integration**, and select **Setup**.</span></span>
1. <span data-ttu-id="30752-167">En el cuadro de diálogo **Configuración del entorno de Power Platform**, seleccione la casilla de verificación y luego seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="30752-167">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="30752-168">Normalmente, la instalación tarda entre 60 y 90 minutos.</span><span class="sxs-lookup"><span data-stu-id="30752-168">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="30752-169">Después de la instalación del entorno de Microsoft Power Platform, en la ficha desplegable **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="30752-169">After setup of the Microsoft Power Platform environment is completed, on the **Environment add-ins** FastTab, select **Install a new add-in**.</span></span>
1. <span data-ttu-id="30752-170">Seleccione **Contabilidad de inventario global**.</span><span class="sxs-lookup"><span data-stu-id="30752-170">Select **Global inventory accounting**.</span></span>
1. <span data-ttu-id="30752-171">Siga la guía de instalación y acepte los términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="30752-171">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="30752-172">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="30752-172">Select **Install**.</span></span>
1. <span data-ttu-id="30752-173">En la ficha desplegable **Complementos de entorno**, debería ver que se está instalando la contabilidad de inventario global.</span><span class="sxs-lookup"><span data-stu-id="30752-173">On the **Environment add-ins** FastTab, you should see that Global Inventory Accounting is being installed.</span></span> <span data-ttu-id="30752-174">Después de unos minutos, el estado debería cambiar de *Instalando* a *Instalado*.</span><span class="sxs-lookup"><span data-stu-id="30752-174">After a few minutes, the status should change from *Installing* to *Installed*.</span></span> <span data-ttu-id="30752-175">(Es posible que tenga que actualizar la página para ver este cambio). En ese momento, la contabilidad de inventario global está lista para usar.</span><span class="sxs-lookup"><span data-stu-id="30752-175">(You might have to refresh the page to see this change.) At that point, Global Inventory Accounting is ready to use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="30752-176">Configuración de la integración</span><span class="sxs-lookup"><span data-stu-id="30752-176">Set up the integration</span></span>

<span data-ttu-id="30752-177">Siga estos pasos para configurar la integración entre la contabilidad de inventario global y Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="30752-177">Follow these steps to set up the integration between Global Inventory Accounting and Supply Chain Management.</span></span>

1. <span data-ttu-id="30752-178">Inicie sesión en de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="30752-178">Sign in to Supply Chain Management.</span></span>
1. <span data-ttu-id="30752-179">Vaya a **Administración del sistema \> Administración de funciones**.</span><span class="sxs-lookup"><span data-stu-id="30752-179">Go to **System administration \> Feature Management**.</span></span>
1. <span data-ttu-id="30752-180">Seleccione **Buscar actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="30752-180">Select **Check for updates**.</span></span>
1. <span data-ttu-id="30752-181">Sobre la pestña **Todas**, busque la característica que se denomina *Contabilidad global de inventarios*.</span><span class="sxs-lookup"><span data-stu-id="30752-181">On the **All** tab, search for the feature that is named *Global inventory accounting*.</span></span>
1. <span data-ttu-id="30752-182">Seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="30752-182">Select **Enable now**.</span></span>
1. <span data-ttu-id="30752-183">Ir **Contabilidad global de inventarios \> Configuración \> Parámetros de contabilidad de inventario global \> Parámetros de integraciones**.</span><span class="sxs-lookup"><span data-stu-id="30752-183">Go to **Global inventory accounting \> Setup \> Global inventory accounting parameters \> Integrations parameters**.</span></span>
1. <span data-ttu-id="30752-184">En los campos **Punto final del servicio de datos** y **Punto final de contabilidad de inventario global**, ingrese las URL del correo electrónico que envió el equipo de Contabilidad de inventario global cuando se registró para la vista previa.</span><span class="sxs-lookup"><span data-stu-id="30752-184">In the **Data service endpoint** and **Global inventory accounting endpoint** fields, enter the URLs from the email that the Global Inventory Accounting team sent when you signed up for the preview.</span></span>

<span data-ttu-id="30752-185">La Contabilidad de inventario global ya está lista para usar.</span><span class="sxs-lookup"><span data-stu-id="30752-185">Global Inventory Accounting is now ready to use.</span></span>
