---
title: Tipo de destino de ER de correo electrónico
description: Este tema proporciona información sobre cómo configurar un destino de correo electrónico para cada componente FOLDER o FILE de un formato de informe electrónico (ER) que está configurado para generar documentos salientes.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 72f67ad915ba2acc90ecb52bdb97e42504450a03
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745570"
---
# <a name="email-destination"></a><span data-ttu-id="d34f5-103">Destino de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="d34f5-103">Email destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d34f5-104">Puede configurar un destino de correo electrónico para cada componente FOLDER o FILE de un formato de informe electrónico (ER) que está configurado para generar documentos salientes.</span><span class="sxs-lookup"><span data-stu-id="d34f5-104">You can configure an email destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="d34f5-105">Según la configuración de destino, un documento generado se entrega como archivo adjunto de un correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d34f5-105">Based on the destination setting, a generated document is delivered as an attachment of an electronic mail.</span></span>

<span data-ttu-id="d34f5-106">Establezca **Habilitado** en **Sí** para enviar un archivo de salida por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d34f5-106">Set **Enabled** to **Yes** to send an output file by email.</span></span> <span data-ttu-id="d34f5-107">Después de que se haya habilitado esta opción, puede especificar los destinatarios de correo electrónico y editar el asunto y el cuerpo del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d34f5-107">After this option is enabled, you can specify the email recipients and edit the subject and body of the email message.</span></span> <span data-ttu-id="d34f5-108">Puede configurar textos constantes para el asunto y el cuerpo de correo electrónico, o bien usar las [fórmulas](er-formula-language.md) de ER dinámicamente para crear textos de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d34f5-108">You can set up constant texts for the email subject and body, or you can use ER [formulas](er-formula-language.md) to dynamically create email texts.</span></span> 

<span data-ttu-id="d34f5-109">Puede configurar direcciones de correo electrónico para el ER de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="d34f5-109">You can configure email addresses for ER in two ways.</span></span> <span data-ttu-id="d34f5-110">La configuración se puede completar de la misma manera que la función de administración de impresión la completa, o puede resolver una dirección de correo electrónico utilizando una referencia directa a la configuración de ER a través de una fórmula.</span><span class="sxs-lookup"><span data-stu-id="d34f5-110">The configuration can be completed in the same way that the Print management feature completes it, or you can resolve an email address by using a direct reference to the ER configuration through a formula.</span></span>

<span data-ttu-id="d34f5-111">[![Habilitar destino de correo electrónico](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span><span class="sxs-lookup"><span data-stu-id="d34f5-111">[![Enable email destination](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)</span></span>

## <a name="email-address-types"></a><span data-ttu-id="d34f5-112">Tipos de direcciones de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="d34f5-112">Email address types</span></span>

<span data-ttu-id="d34f5-113">Al seleccionar **Editar** en los campos **Para** o **Cc**, se muestra el cuadro de diálogo **Correo electrónico para**.</span><span class="sxs-lookup"><span data-stu-id="d34f5-113">When you select **Edit** in the **To** or **Cc** fields, the **Email to** dialog box appears.</span></span> <span data-ttu-id="d34f5-114">A continuación puede seleccionar el tipo de dirección de correo electrónico que se usará.</span><span class="sxs-lookup"><span data-stu-id="d34f5-114">You can then select the type of email address to use.</span></span> <span data-ttu-id="d34f5-115">Los tipos de correo electrónico **Correo electrónico de configuración** y **Gestión de impresión** son compatibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="d34f5-115">The **Configuration email** and **Print Management** email types are currently supported.</span></span>

<span data-ttu-id="d34f5-116">[![Seleccionar el tipo de correo electrónico](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span><span class="sxs-lookup"><span data-stu-id="d34f5-116">[![Select email type](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)</span></span>

### <a name="print-management"></a><span data-ttu-id="d34f5-117">Gestión de impresión</span><span class="sxs-lookup"><span data-stu-id="d34f5-117">Print management</span></span>

<span data-ttu-id="d34f5-118">Si selecciona el tipo de correo electrónico **Administración de impresión**, puede especificar direcciones de correo electrónico fijas en el campo **Para**.</span><span class="sxs-lookup"><span data-stu-id="d34f5-118">If you select the **Print Management** email type, you can enter fixed email addresses in the **To** field.</span></span> 

<span data-ttu-id="d34f5-119">[![Configurar direcciones de correo electrónico fijas](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span><span class="sxs-lookup"><span data-stu-id="d34f5-119">[![Configure fixed email addresses](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)</span></span>

<span data-ttu-id="d34f5-120">Para utilizar direcciones de correo electrónico que no son fijas, debe seleccionar el tipo de origen de correo electrónico para un destino de archivo.</span><span class="sxs-lookup"><span data-stu-id="d34f5-120">To use email addresses that aren't fixed, you must select the email source type for a file destination.</span></span> <span data-ttu-id="d34f5-121">Se admiten los siguientes valores: **Cliente**, **Proveedor**, **Cliente potencial**, **Contacto**, **Competidor**, **Trabajador**, **Candidato**, **Proveedor potencial** y **Proveedor no permitido**.</span><span class="sxs-lookup"><span data-stu-id="d34f5-121">The following values are supported: **Customer**, **Vendor**, **Prospect**, **Contact**, **Competitor**, **Worker**, **Applicant**, **Prospective vendor**, and **Disallowed vendor**.</span></span> <span data-ttu-id="d34f5-122">Tras seleccionar un tipo de origen de correo electrónico, use el botón junto al campo **Cuenta de origen de correo electrónico** para abrir el formulario **Diseñador de fórmula**.</span><span class="sxs-lookup"><span data-stu-id="d34f5-122">After you select an email source type, use the button next to the **Email source account** field to open the **Formula designer** form.</span></span> <span data-ttu-id="d34f5-123">Puede usar este formulario para adjuntar una fórmula que devuelve en tiempo de ejecución la **cuenta de la parte** del tipo de origen seleccionado desde el documento procesado hasta el destino del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d34f5-123">You can use this form to attach a formula that returns at runtime, the **party account** of the selected source type from the processed document to the email destination.</span></span>

<span data-ttu-id="d34f5-124">[![Configurar la cuenta de origen de correo electrónico](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span><span class="sxs-lookup"><span data-stu-id="d34f5-124">[![Configure email source account](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)</span></span>

<span data-ttu-id="d34f5-125">Las fórmulas son específicas de la configuración de ER.</span><span class="sxs-lookup"><span data-stu-id="d34f5-125">Formulas are specific to the ER configuration.</span></span> <span data-ttu-id="d34f5-126">En la **Fórmula**, especifique una referencia específica de documento para un tipo de parte de cliente o proveedor.</span><span class="sxs-lookup"><span data-stu-id="d34f5-126">In the **Formula** field, enter a document-specific reference to a customer or vendor party type.</span></span> <span data-ttu-id="d34f5-127">En lugar de escribir, puede encontrar el nodo del origen de datos que represente la cuenta del cliente o proveedor y, a continuación, seleccionar **Agregar origen de datos** para actualizar la fórmula.</span><span class="sxs-lookup"><span data-stu-id="d34f5-127">Instead of typing, you can find the data source node that represents the customer or vendor account, and then select **Add data source** to update the formula.</span></span> <span data-ttu-id="d34f5-128">Por ejemplo, si utiliza la configuración **ISO 20022 Transferencia de crédito**, el nodo que representa una cuenta de proveedor es `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span><span class="sxs-lookup"><span data-stu-id="d34f5-128">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents a vendor account is `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.</span></span>

<span data-ttu-id="d34f5-129">Si introduce un valor de cadena, como `"DE-001"` y guarda una fórmula, se enviará un correo electrónico a la persona de contacto del proveedor, **DE-001**.</span><span class="sxs-lookup"><span data-stu-id="d34f5-129">If you enter a string value, such as `"DE-001"`, and save a formula, an email will be sent to the contact person of the vendor, **DE-001**.</span></span>


<span data-ttu-id="d34f5-130">[![Página del diseñador de fórmulas de ER](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span><span class="sxs-lookup"><span data-stu-id="d34f5-130">[![ER formula designer page](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)</span></span>

<span data-ttu-id="d34f5-131">[![Configurar la cuenta de atributos de origen de correo electrónico](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span><span class="sxs-lookup"><span data-stu-id="d34f5-131">[![Configure email source attributes account](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)</span></span>



### <a name="configuration-email"></a><span data-ttu-id="d34f5-132">Correo electrónico de configuración</span><span class="sxs-lookup"><span data-stu-id="d34f5-132">Configuration email</span></span>

<span data-ttu-id="d34f5-133">Use este tipo de correo electrónico si la configuración que utiliza tiene un nodo en los orígenes de datos que devuelve una **dirección de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="d34f5-133">Use this email type if the configuration that you use has a node in the data sources that returns an **email address**.</span></span> <span data-ttu-id="d34f5-134">Puede usar orígenes de datos y funciones en el diseñador de fórmula para obtener una dirección de correo electrónico con formato correcto.</span><span class="sxs-lookup"><span data-stu-id="d34f5-134">You can use data sources and functions in the formula designer to get a correctly formatted email address.</span></span> <span data-ttu-id="d34f5-135">Por ejemplo, si utiliza la configuración **ISO 20022 Transferencia de crédito**, el nodo que representa una dirección de correo electrónico de la persona de contacto del proveedor es `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span><span class="sxs-lookup"><span data-stu-id="d34f5-135">For example, if you use the **ISO 20022 Credit Transfer** configuration, the node that represents an email address of a vendor's contact person is `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.</span></span>

<span data-ttu-id="d34f5-136">[![Configurar el origen de la dirección de correo electrónico](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span><span class="sxs-lookup"><span data-stu-id="d34f5-136">[![Configure email address source](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d34f5-137">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d34f5-137">Additional resources</span></span>

- [<span data-ttu-id="d34f5-138">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="d34f5-138">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="d34f5-139">Destinos de informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="d34f5-139">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="d34f5-140">Diseñador de fórmulas en los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="d34f5-140">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
