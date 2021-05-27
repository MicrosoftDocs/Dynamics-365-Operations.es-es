---
title: No se puede configurar un grupo de seguridad para el creador de sitios de Commerce durante la implementación inicial
description: Este tema proporciona una guía de solución de problemas que puede ayudar cuando el grupo de seguridad de Microsoft Azure Active Directory (Azure AD) para el creador de sitios de Commerce no aparece como una opción al crear componentes de comercio electrónico en Microsoft Dynamics Lifecycle Services (LCS) durante la implementación inicial de un nuevo inquilino de comercio electrónico.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d29e560d0f7b2bbc2415d7a0f6fe18f2ca17dc7c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020741"
---
# <a name="cant-configure-a-security-group-for-commerce-site-builder-during-initial-deployment"></a><span data-ttu-id="115da-103">No se puede configurar un grupo de seguridad para el creador de sitios de Commerce durante la implementación inicial</span><span class="sxs-lookup"><span data-stu-id="115da-103">Can't configure a security group for Commerce site builder during initial deployment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="115da-104">Este tema proporciona una guía de solución de problemas que puede ayudar cuando el grupo de seguridad de Microsoft Azure Active Directory (Azure AD) para el creador de sitios de Commerce no aparece como una opción al crear componentes de comercio electrónico en Microsoft Dynamics Lifecycle Services (LCS) durante la implementación inicial de un nuevo inquilino de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="115da-104">This topic provides troubleshooting guidance that can help when the Microsoft Azure Active Directory (Azure AD) security group for Commerce site builder doesn't appear as an option when you create e-commerce components in Microsoft Dynamics Lifecycle Services (LCS) during initial deployment of a new e-commerce tenant.</span></span>

## <a name="description"></a><span data-ttu-id="115da-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="115da-105">Description</span></span>

<span data-ttu-id="115da-106">Cuando crea los componentes de comercio electrónico como parte del proceso de implementación de un nuevo inquilino de comercio electrónico que incluye el componente de creación de sitios de Commerce, el grupo de seguridad de Azure AD no aparece como opción en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="115da-106">When you create the e-commerce components as part of the process of deploying a new e-commerce tenant that includes the Commerce site builder component, the Azure AD security group doesn't appear as an option in the dialog box.</span></span>

## <a name="resolution"></a><span data-ttu-id="115da-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="115da-107">Resolution</span></span>

### <a name="provision-the-e-commerce-site-with-a-user-in-the-correct-tenant"></a><span data-ttu-id="115da-108">Aprovisionar el sitio de comercio electrónico con un usuario en el inquilino correcto</span><span class="sxs-lookup"><span data-stu-id="115da-108">Provision the e-commerce site with a user in the correct tenant</span></span>

1. <span data-ttu-id="115da-109">Vaya a [Azure Portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="115da-109">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="115da-110">En el inquilino para el que se aprovisionó el proyecto LCS para su sitio de comercio electrónico, siga las instrucciones en [Crear un grupo básico y agregar miembros usando Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="115da-110">Under the tenant that the LCS project for your e-commerce site was provisioned for, follow the instructions in [Create a basic group and add members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal).</span></span>
1. <span data-ttu-id="115da-111">Vaya a [LCS](https://lcs.dynamics.com/) e inicie sesión con una cuenta que comparta el mismo inquilino que el grupo de seguridad de Azure AD que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="115da-111">Go to [LCS](https://lcs.dynamics.com/), and sign in by using an account that shares the same tenant as the Azure AD security group that you just created.</span></span> <span data-ttu-id="115da-112">La cuenta debe tener acceso para ver el grupo de seguridad de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="115da-112">The account must have access to view the Azure AD security group.</span></span>
1. <span data-ttu-id="115da-113">Complete los pasos de configuración para configurar el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="115da-113">Complete the setup steps to configure the e-commerce site.</span></span> <span data-ttu-id="115da-114">Cuando aprovisiona los componentes de comercio electrónico, el grupo de seguridad ahora debería aparecer como una opción en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="115da-114">When you provision the e-commerce components, the security group should now appear as an option in the dialog box.</span></span>

> [!NOTE]
> <span data-ttu-id="115da-115">Para asegurarse de que el campo del cuadro de diálogo se rellene con la lista de grupos de seguridad, debe seleccionar **Entrar** después de introducir el nombre del grupo de seguridad de Azure AD que creó.</span><span class="sxs-lookup"><span data-stu-id="115da-115">To ensure that the field in the dialog box is filled with the list of security groups, you must select **Enter** after you enter the name of the Azure AD security group that you created.</span></span> <span data-ttu-id="115da-116">Los resultados de la búsqueda enumerarán todos los grupos de seguridad de Azure AD que comienzan con el texto de búsqueda y a los que el usuario tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="115da-116">The search results will list all the Azure AD security groups that start with the search text, and that the user has access to.</span></span> <span data-ttu-id="115da-117">Puede utilizar un término de búsqueda más corto para permitir resultados de búsqueda más amplios.</span><span class="sxs-lookup"><span data-stu-id="115da-117">You can use a shorter search term to allow for broader search results.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="115da-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="115da-118">Additional resources</span></span>

[<span data-ttu-id="115da-119">Crear un grupo básico y agregar miembros usando Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="115da-119">Create a basic group and add members using Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

[<span data-ttu-id="115da-120">Implementar un inquilino nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="115da-120">Deploy a new e-commerce tenant</span></span>](../deploy-ecommerce-site.md)