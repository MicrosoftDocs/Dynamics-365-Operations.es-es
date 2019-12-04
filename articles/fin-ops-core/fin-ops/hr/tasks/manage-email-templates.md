---
title: Gestionar plantillas de correo electrónico
description: En este tema se explica cómo administrar plantillas de correo electrónico.
author: andreabichsel
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMApplicationWordBookmark, HRMApplicationEmailTemplate
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ecfa720dfa9b3ed6ee15ec68498d2a46612a9ae
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179877"
---
# <a name="manage-email-templates"></a><span data-ttu-id="24f7b-103">Gestionar plantillas de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="24f7b-103">Manage email templates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="24f7b-104">Puede transferir información de la base de datos de su organización a los marcadores en un documento nuevo y usarla en plantillas que le ayuden a comunicarse eficazmente con los candidatos.</span><span class="sxs-lookup"><span data-stu-id="24f7b-104">You can transfer information from your organization’s database to the bookmarks in a new document and use it in templates that help you communicate efficiently with applicants and candidates.</span></span> <span data-ttu-id="24f7b-105">Para ello, cree una plantilla con texto estándar y algunos marcadores en los que se vayan a insertar datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="24f7b-105">To do this, you create a template that contains standard text and some bookmarks where the system data should be inserted.</span></span> <span data-ttu-id="24f7b-106">Por ejemplo, puede insertar la dirección y la información de contacto para un candidato en un documento de Microsoft Word que pueda usar para comunicarse con él o ella.</span><span class="sxs-lookup"><span data-stu-id="24f7b-106">For example, you can insert address and contact information for an applicant into a Microsoft Word document that you can use when communicating with that applicant.</span></span> <span data-ttu-id="24f7b-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="24f7b-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="select-which-bookmarks-to-use-in-your-email-templates"></a><span data-ttu-id="24f7b-108">Selección de los marcadores que usar en las plantillas de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="24f7b-108">Select which bookmarks to use in your email templates</span></span>
1. <span data-ttu-id="24f7b-109">En el panel de navegación, vaya a **Módulos > Recursos Humanos > Contratación > Comunicación > Marcadores de solicitud**.</span><span class="sxs-lookup"><span data-stu-id="24f7b-109">In the navigation pane, go to **Modules > Human Resources > Recruitment > Communication > Application bookmarks**.</span></span>
2. <span data-ttu-id="24f7b-110">En la lista, busque y seleccione la acción de correspondencia en cuestión.</span><span class="sxs-lookup"><span data-stu-id="24f7b-110">In the list, find and select the desired correspondence action.</span></span>
3. <span data-ttu-id="24f7b-111">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="24f7b-111">Select **Edit**.</span></span>
4. <span data-ttu-id="24f7b-112">Seleccione los campos que desea poder utilizar en una plantilla de correo electrónico para la acción de correspondencia seleccionada y muévalos a los campos de marcador.</span><span class="sxs-lookup"><span data-stu-id="24f7b-112">Select the fields you would like to be able to use in an email template for the selected Correspondence action and move them to the Bookmark fields.</span></span>  
5. <span data-ttu-id="24f7b-113">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="24f7b-113">Close the page.</span></span>

## <a name="create-an-email-template"></a><span data-ttu-id="24f7b-114">Crear una plantilla de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="24f7b-114">Create an email template</span></span>
1. <span data-ttu-id="24f7b-115">En el panel de navegación, vaya a **Módulos > Recursos Humanos > Contratación > Comunicación > Plantillas de correo electrónico de solicitud**.</span><span class="sxs-lookup"><span data-stu-id="24f7b-115">In the navigation pane, go to **Modules > Human resources > Recruitment > Communication > Application e-mail templates**.</span></span>
2. <span data-ttu-id="24f7b-116">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="24f7b-116">Select **New**.</span></span>
3. <span data-ttu-id="24f7b-117">En el campo **Acción de correspondencia**, seleccione **Entrevista**.</span><span class="sxs-lookup"><span data-stu-id="24f7b-117">In the **Correspondence action** field, select **Interview**.</span></span> <span data-ttu-id="24f7b-118">Seleccione la acción de correspondencia con los marcadores que usar para este tipo de comunicación por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="24f7b-118">Select the correspondence action that contains the bookmarks to use for this type of email communication.</span></span>  
4. <span data-ttu-id="24f7b-119">En el campo **Plantilla de correo electrónico**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="24f7b-119">In the **E-mail template** field, type a value.</span></span>
5. <span data-ttu-id="24f7b-120">En el campo **Asunto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="24f7b-120">In the **Subject** field, type a value.</span></span>
6. <span data-ttu-id="24f7b-121">En el campo **Texto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="24f7b-121">In the **Text** field, type a value.</span></span>
7. <span data-ttu-id="24f7b-122">En la lista, busque y seleccione el campo de marcador deseado.</span><span class="sxs-lookup"><span data-stu-id="24f7b-122">In the list, find and select the desired bookmark field.</span></span>
8. <span data-ttu-id="24f7b-123">A continuación, escriba el mensaje de correo electrónico insertando los campos de marcador donde estime oportuno.</span><span class="sxs-lookup"><span data-stu-id="24f7b-123">Continue typing your email message, inserting the bookmark fields where you need them.</span></span>
9. <span data-ttu-id="24f7b-124">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="24f7b-124">Select **Save**.</span></span>
