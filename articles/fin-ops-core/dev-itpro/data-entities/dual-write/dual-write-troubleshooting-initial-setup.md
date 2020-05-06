---
title: Solucionar problemas durante la configuración inicial
description: Este tema proporciona información de solución de problemas que puede ayudarlo a solucionar los problemas que pueden ocurrir durante la configuración inicial de la integración de escritura doble entre aplicaciones Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 76e104c9ebd7db7ebcbaf214e84be6c4353e8a73
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275450"
---
# <a name="troubleshoot-issues-during-initial-setup"></a><span data-ttu-id="b52a4-103">Solucionar problemas durante la configuración inicial</span><span class="sxs-lookup"><span data-stu-id="b52a4-103">Troubleshoot issues during initial setup</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="b52a4-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b52a4-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="b52a4-105">Proporciona información específica que puede ayudarlo a solucionar los problemas que pueden ocurrir durante la configuración inicial de la integración de escritura doble.</span><span class="sxs-lookup"><span data-stu-id="b52a4-105">Specifically, it provides information that can help you fix issues that might occur during the initial setup of dual-write integration.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b52a4-106">Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="b52a4-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="b52a4-107">La sección para cada problema explica si se requiere una función o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="b52a4-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-link-a-finance-and-operations-app-to-common-data-service"></a><span data-ttu-id="b52a4-108">No puede vincular una aplicación Finance and Operations a Common Data Service</span><span class="sxs-lookup"><span data-stu-id="b52a4-108">You can't link a Finance and Operations app to Common Data Service</span></span>

<span data-ttu-id="b52a4-109">**Rol requerido para configurar doble escritura**: Administrador del sistema en aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b52a4-109">**Required role to set up dual-write:** System administrator in Finance and Operations apps and Common Data Service.</span></span>

<span data-ttu-id="b52a4-110">Los errores en la página **Enlace de configuración a Common Data Service** generalmente se deben a problemas de configuración o permisos incompletos.</span><span class="sxs-lookup"><span data-stu-id="b52a4-110">Errors on the **Setup link to Common Data Service** page are usually caused by incomplete setup or permissions issues.</span></span> <span data-ttu-id="b52a4-111">Asegúrese de que toda la compración de estado aprueba en la página **Enlace de configuración a Common Data Service**, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="b52a4-111">Make sure that the whole health check passes on the **Setup link to Common Data Service** page, as shown in the following illustration.</span></span> <span data-ttu-id="b52a4-112">No puede vincular la escritura doble a menos que se apruebe toda la comprobación de estado.</span><span class="sxs-lookup"><span data-stu-id="b52a4-112">You can't link dual-write unless the whole health check passes.</span></span>

![Comprobación de estado exitosa](media/health_check.png)

<span data-ttu-id="b52a4-114">Debe tener credenciales de administrador de inquilinos de Azure AD para vincular los entornos Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b52a4-114">You must have Azure AD tenant admin credentials to link the Finance and Operations and Common Data Service environments.</span></span> <span data-ttu-id="b52a4-115">Después de vincular los entornos, los usuarios pueden iniciar sesión utilizando sus credenciales de cuenta y actualizar un mapa de entidad existente.</span><span class="sxs-lookup"><span data-stu-id="b52a4-115">After you link the environments, users can sign in by using their account credentials and update an existing entity map.</span></span>

## <a name="error-when-you-open-the-link-to-common-data-service-page"></a><span data-ttu-id="b52a4-116">Error al abrir el enlace a la página Common Data Service</span><span class="sxs-lookup"><span data-stu-id="b52a4-116">Error when you open the Link to Common Data Service page</span></span>

<span data-ttu-id="b52a4-117">**Credenciales requeridas para arreglar el problema:** Administrador de inquilinos Azure AD</span><span class="sxs-lookup"><span data-stu-id="b52a4-117">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="b52a4-118">Es posible que reciba el siguiente mensaje de error cuando abra la página **Vincular a Common Data Service** en una aplicación Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="b52a4-118">You might receive the following error message when you open the **Link to Common Data Service** page in a Finance and Operations app:</span></span>

<span data-ttu-id="b52a4-119">*El código de estado de respuesta no indica éxito: 404 (no encontrado).*</span><span class="sxs-lookup"><span data-stu-id="b52a4-119">*Response status code does not indicate success: 404 (Not Found).*</span></span>

<span data-ttu-id="b52a4-120">Este error ocurre cuando el paso de consentimiento no se ha completado.</span><span class="sxs-lookup"><span data-stu-id="b52a4-120">This error occurs when the consent step hasn't been completed.</span></span> <span data-ttu-id="b52a4-121">Para validar si se ha completado el paso de consentimiento, inicie sesión en portal.Azure.com utilizando la cuenta de administrador del inquilino de Azure AD, y vea si la aplicación de terceros que tiene la ID **33976c19-1db5-4c02-810e-c243db79efde** aparece en la lista de **Aplicaciones empresariales** de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b52a4-121">To validate whether the consent step has been completed, sign in to portal.Azure.com by using the Azure AD tenant admin account, and see whether the third-party app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** appears in the Azure AD **Enterprise applications** list.</span></span> <span data-ttu-id="b52a4-122">Si no es así, debe proporcionar el consentimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b52a4-122">If it doesn't, you must provide app consent.</span></span>

<span data-ttu-id="b52a4-123">Para proporcionar el consentimiento de la aplicación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b52a4-123">To provide app consent, follow these steps.</span></span>

1. <span data-ttu-id="b52a4-124">Abra la siguiente URL utilizando sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="b52a4-124">Open the following URL by using your admin credentials.</span></span> <span data-ttu-id="b52a4-125">Se le debe solicitar su consentimiento.</span><span class="sxs-lookup"><span data-stu-id="b52a4-125">You should be prompted for consent.</span></span>

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. <span data-ttu-id="b52a4-126">Seleccione **Aceptar** para indicar que está dando su consentimiento para instalar la aplicación que tiene la ID **33976c19-1db5-4c02-810e-c243db79efde** en su inquilino.</span><span class="sxs-lookup"><span data-stu-id="b52a4-126">Select **Accept** to indicate that you're giving your consent to install the app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** in your tenant.</span></span>

    > [!TIP]
    > <span data-ttu-id="b52a4-127">Esta aplicación es necesaria para vincular Common Data Service y aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b52a4-127">This app is required to link Common Data Service and Finance and Operations apps.</span></span> <span data-ttu-id="b52a4-128">Si tiene problemas con este paso, abra su navegador en modo incógnito (en Google Chrome) o en modo InPrivate (en Microsoft Edge).</span><span class="sxs-lookup"><span data-stu-id="b52a4-128">If you have trouble with this step, open your browser in incognito mode (in Google Chrome) or InPrivate mode (in Microsoft Edge).</span></span>

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a><span data-ttu-id="b52a4-129">Verifique que los datos de la empresa y los equipos de doble escritura estén configurados correctamente durante el enlace</span><span class="sxs-lookup"><span data-stu-id="b52a4-129">Verify that company data and dual-write teams are set up correctly during linking</span></span>

<span data-ttu-id="b52a4-130">Para garantizar que la escritura doble funcione correctamente, las empresas que seleccione durante la configuración se crean en el entorno Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b52a4-130">To ensure that dual-write works correctly, the companies that you select during configuration are created in the Common Data Service environment.</span></span> <span data-ttu-id="b52a4-131">Por defecto, estas empresas son de solo lectura, y la propiedad **IsDualWriteEnable** se establece en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="b52a4-131">By default, these companies are read-only, and the **IsDualWriteEnable** property is set to **True**.</span></span> <span data-ttu-id="b52a4-132">Además, se crean el propietario y el equipo de la unidad de negocios propietaria predeterminada e incluyen el nombre de la empresa.</span><span class="sxs-lookup"><span data-stu-id="b52a4-132">In addition, the default owning business unit owner and team are created and include the company name.</span></span> <span data-ttu-id="b52a4-133">Antes de habilitar los mapas, verifique que se haya especificado el propietario del equipo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b52a4-133">Before you enable the maps, verify that the default team owner is specified.</span></span> <span data-ttu-id="b52a4-134">Para encontrar la entidad **Empresas (MDL\_Empresa)**, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b52a4-134">To find the **Companies (CDM\_Company)** entity, follow these steps.</span></span>

1. <span data-ttu-id="b52a4-135">En la aplicación basada en modelos en Dynamics 365, seleccione el filtro en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="b52a4-135">In the model-driven app in Dynamics 365, select the filter in the upper-right corner.</span></span>
2. <span data-ttu-id="b52a4-136">En la lista desplegable , seleccione **Compañía**.</span><span class="sxs-lookup"><span data-stu-id="b52a4-136">In the drop-down list, select **Company**.</span></span>
3. <span data-ttu-id="b52a4-137">Seleccione **Ejecutar** para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="b52a4-137">Select **Run** to see the results.</span></span>
4. <span data-ttu-id="b52a4-138">Seleccione la compañía que estaba vinculada cuando configuró la escritura doble.</span><span class="sxs-lookup"><span data-stu-id="b52a4-138">Select the company that was linked when you configured dual-write.</span></span>
5. <span data-ttu-id="b52a4-139">Verifique que el campo **Equipo propietario predeterminado** tiene un valor.</span><span class="sxs-lookup"><span data-stu-id="b52a4-139">Verify that the **Default owning team** field has a value.</span></span> <span data-ttu-id="b52a4-140">En la siguiente ilustración, el campo **Equipo propietario predeterminado** se establece en **USMF de doble escritura**.</span><span class="sxs-lookup"><span data-stu-id="b52a4-140">In the following illustration, the **Default owning team** field is set to **USMF Dual Write**.</span></span>

    ![Verificación del equipo propietario predeterminado](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-entities-or-companies-that-can-be-linked-for-dual-write"></a><span data-ttu-id="b52a4-142">Encuentre el límite en el número de personas jurídicas o empresas que pueden vincularse para doble escritura</span><span class="sxs-lookup"><span data-stu-id="b52a4-142">Find the limit on the number of legal entities or companies that can be linked for dual-write</span></span>

<span data-ttu-id="b52a4-143">Es posible que reciba el siguiente mensaje de error cuando intenta habilitar mapas:</span><span class="sxs-lookup"><span data-stu-id="b52a4-143">You might receive the following error message when you try to enable maps:</span></span>

<span data-ttu-id="b52a4-144">*Error de escritura doble - Error en el registro del complemento: \[(No se puede obtener el mapa de partición para el proyecto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Error Excede las particiones máximas permitidas para asignar DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], Ocurrieron uno o más errores.*</span><span class="sxs-lookup"><span data-stu-id="b52a4-144">*Dual write failure - Plugin registration failed: \[(Unable to get partition map for project DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Error Exceeds the maximum partitions allowed for mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], One or more errors occurred.*</span></span>

<span data-ttu-id="b52a4-145">El límite actual cuando vincula los entornos es de aproximadamente 40 entidades legales.</span><span class="sxs-lookup"><span data-stu-id="b52a4-145">The current limit when you link the environments is approximately 40 legal entities.</span></span> <span data-ttu-id="b52a4-146">Este error ocurre si intenta habilitar mapas, y más de 40 entidades legales están vinculadas entre los entornos.</span><span class="sxs-lookup"><span data-stu-id="b52a4-146">This error occurs if you try to enable maps, and more than 40 legal entities are linked between the environments.</span></span>
