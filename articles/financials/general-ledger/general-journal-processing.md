---
title: Procesamiento de diarios generales
description: "Este artículo describe las capacidades en Microsoft Dynamics 365 for Finance and Operations que pueden facilitar el proceso del diario general y que también pueden ayudar a garantizar que se capturan los datos correctos y que no se pone en peligro el control interno."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: eb46613f805999753c2ab73ffb91a6fdae04c68e
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="general-journal-processing"></a><span data-ttu-id="a05eb-103">Procesamiento de diarios generales</span><span class="sxs-lookup"><span data-stu-id="a05eb-103">General journal processing</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a05eb-104">Este artículo describe las capacidades en Microsoft Dynamics 365 for Finance and Operations que pueden facilitar el proceso del diario general y que también pueden ayudar a garantizar que se capturan los datos correctos y que no se pone en peligro el control interno.</span><span class="sxs-lookup"><span data-stu-id="a05eb-104">This articles describes capabilities in Microsoft Dynamics 365 for Finance and Operations that can help make general journal processing easier, and that can also help guarantee that correct data is captured and internal control isn't compromised.</span></span>  

<span data-ttu-id="a05eb-105">Nombres de diarios</span><span class="sxs-lookup"><span data-stu-id="a05eb-105">Journal names</span></span>

<span data-ttu-id="a05eb-106">Una de las áreas más importantes para configurar es los nombres de diario.</span><span class="sxs-lookup"><span data-stu-id="a05eb-106">One of the most important areas to set up is journal names.</span></span> <span data-ttu-id="a05eb-107">Conviene definir los nombres de diario específicos para cada propósito, como empresas vinculadas, ajuste de acumulación y corrección de error.</span><span class="sxs-lookup"><span data-stu-id="a05eb-107">It's a good idea to define specific journal names for each purpose, such as intercompany, accrual adjustment, and error correction.</span></span> <span data-ttu-id="a05eb-108">Puede ajustar cada nombre de diario para que la entrada de datos para cada propósito sea sencilla y segura.</span><span class="sxs-lookup"><span data-stu-id="a05eb-108">You can tailor each journal name to help make data entry for each purpose easy and secure.</span></span> 

<span data-ttu-id="a05eb-109">En la página **Nombres de diario**, puede configurar los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="a05eb-109">On the **Journal names** page, you can set up the following elements:</span></span>

-   <span data-ttu-id="a05eb-110">**Aprobación de flujo de trabajo:** para mejorar el control interno, defina los flujos de trabajo de diarios que establecen los límites de los pasos para su revisión y aprobación, en función de criterios como importe de débito total.</span><span class="sxs-lookup"><span data-stu-id="a05eb-110">**Workflow approval** – To increase internal control, define journal workflows that establish materiality limits for review and approval steps, based on criteria such as total debit amount.</span></span> <span data-ttu-id="a05eb-111">Debe configurar los flujos de trabajo para los diarios generales en la página **Flujos de trabajo de contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="a05eb-111">You set up workflows for the general journals on the** General ledger workflows** page.</span></span>
-   <span data-ttu-id="a05eb-112">**Valores predeterminados:** seleccione valores predeterminados para cuentas de contrapartida, divisa y dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="a05eb-112">**Default values** – Select default values for offset accounts, currency, and financial dimensions.</span></span>
-   <span data-ttu-id="a05eb-113">**Control del diario:** puede configurar las restricciones en la empresa y el tipo de cuenta, y también los valores de segmento.</span><span class="sxs-lookup"><span data-stu-id="a05eb-113">**Journal control** – You can set up restrictions on the company and account type, and also the segment values.</span></span> 

<span data-ttu-id="a05eb-114">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="a05eb-114">**Examples**</span></span>

<span data-ttu-id="a05eb-115">Un nombre de diario también se puede usar solo para ajustes.</span><span class="sxs-lookup"><span data-stu-id="a05eb-115">A journal name can be used only for adjustments.</span></span> <span data-ttu-id="a05eb-116">En este caso, puede especificar que solo el tipo de cuenta **Libro mayor** es válido en todas las empresas.</span><span class="sxs-lookup"><span data-stu-id="a05eb-116">In this case, you can specify that only the **Ledger** account type is valid across all companies.</span></span> <span data-ttu-id="a05eb-117">[![Tipos de cuenta de control de diarios](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span><span class="sxs-lookup"><span data-stu-id="a05eb-117">[![Journal control account types](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span></span>

<span data-ttu-id="a05eb-118">Un nombre de diario solo se puede usar para un segmento específico o para un intervalo para las cuentas principales.</span><span class="sxs-lookup"><span data-stu-id="a05eb-118">A journal name can be used only for a specific segment or for a range for main accounts.</span></span> <span data-ttu-id="a05eb-119">[![Segmento de control de diarios](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span><span class="sxs-lookup"><span data-stu-id="a05eb-119">[![Journal control segment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span></span>

<span data-ttu-id="a05eb-120">La opción **Inversión automática** solo está disponible en los diarios generales.</span><span class="sxs-lookup"><span data-stu-id="a05eb-120">The **Automatic reversal** option is available in general journals.</span></span> <span data-ttu-id="a05eb-121">Por ejemplo, tiene un ajuste de acumulación donde el documento real aún no se ha procesado, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="a05eb-121">For example, you have an accrual adjustment where the actual document hasn't yet been processed, as shown in the following illustration.</span></span>
<span data-ttu-id="a05eb-122">[![Inversión del diario general](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span><span class="sxs-lookup"><span data-stu-id="a05eb-122">[![General journal reversing](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span></span> 

<span data-ttu-id="a05eb-123">El complemento de Microsoft Excel para el movimiento del diario proporciona un nivel adicional de automatización y hace que la entrada de datos sea más fácil.</span><span class="sxs-lookup"><span data-stu-id="a05eb-123">The Microsoft Excel add-in for journal entry provides an additional level of automation and makes data entry easier.</span></span> <span data-ttu-id="a05eb-124">La acción **Líneas abiertas en Excel** está disponible en las páginas del **Diario general** y **Asiento del diario** .</span><span class="sxs-lookup"><span data-stu-id="a05eb-124">The **Open lines in Excel** action is available on the **General journal** and **Journal voucher** pages.</span></span> 

<span data-ttu-id="a05eb-125">En la página **Diarios periódicos**, puede configurar los diarios periódicos para automatizar el proceso de diario.</span><span class="sxs-lookup"><span data-stu-id="a05eb-125">On the **Periodic journals** page, you can set up recurring journals to automate journal processing.</span></span> 

<span data-ttu-id="a05eb-126">Puede usar plantillas de asientos en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="a05eb-126">You can use voucher templates at any time.</span></span> <span data-ttu-id="a05eb-127">En la página **Diarios generales**, las acciones **Guardar** y **Seleccionar la plantilla de asientos** se encuentran en la página **Asiento del diario**, en **Funciones** para las líneas de asientos.</span><span class="sxs-lookup"><span data-stu-id="a05eb-127">On the **General journals** page, the **Save** and **Select voucher template** actions are found on the **Journal voucher** page, under **Functions** for the voucher lines.</span></span>

## <a name="related-setup"></a><span data-ttu-id="a05eb-128">Configuración relacionada</span><span class="sxs-lookup"><span data-stu-id="a05eb-128">Related setup</span></span>
<span data-ttu-id="a05eb-129">La configuración siguiente no es específica para los diarios generales, pero ayudará a garantizar que la entrada de datos sea correcta y fácil.</span><span class="sxs-lookup"><span data-stu-id="a05eb-129">The following setup isn't specific to general journals, but will help guarantee that data entry is correct data and easy.</span></span>

### <a name="main-account"></a><span data-ttu-id="a05eb-130">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="a05eb-130">Main account</span></span>

<span data-ttu-id="a05eb-131">La configuración de la cuenta principal ofrece muchas opciones para el proceso del diario general:</span><span class="sxs-lookup"><span data-stu-id="a05eb-131">The main account setup provides many options for general journal processing:</span></span>

-   <span data-ttu-id="a05eb-132">**Requisito de DC/CR:** use esta opción si una cuenta principal está limitada a las transacciones de débito o crédito.</span><span class="sxs-lookup"><span data-stu-id="a05eb-132">**DC/CR requirement** – Use this option if a main account is limited to debit or credit transactions.</span></span> <span data-ttu-id="a05eb-133">Se comprueba la configuración cuando se valida o se registra un diario.</span><span class="sxs-lookup"><span data-stu-id="a05eb-133">The setup is verified when a journal is validated or posted.</span></span>
-   <span data-ttu-id="a05eb-134">**Cuenta de contrapartida predeterminada**</span><span class="sxs-lookup"><span data-stu-id="a05eb-134">**Default offset account**</span></span>
-   <span data-ttu-id="a05eb-135">**Suspendida:** suspenda una cuenta principal para la entrada de datos en todas las empresas o para una empresa o entidad jurídica específicas.</span><span class="sxs-lookup"><span data-stu-id="a05eb-135">**Suspended** – Suspend a main account for data entry across all companies or for a specific company/legal entities.</span></span>
-   <span data-ttu-id="a05eb-136">**No permitir entrada manual:** evitar que los usuarios especifiquen manualmente un valor para la cuenta en los diarios.</span><span class="sxs-lookup"><span data-stu-id="a05eb-136">**Do not allow manual entry** – Prevent users from manually entering a value for the account in journals.</span></span>
-   <span data-ttu-id="a05eb-137">**Validar divisa o predeterminada**</span><span class="sxs-lookup"><span data-stu-id="a05eb-137">**Default/Validate currency**</span></span>
-   <span data-ttu-id="a05eb-138">**Anulación de la entidad jurídica:** esta configuración es específica a la empresa o a entidad jurídica definidas:</span><span class="sxs-lookup"><span data-stu-id="a05eb-138">**Legal entity override** – This setup is specific to the defined company/legal entity:</span></span>
    -   <span data-ttu-id="a05eb-139">**Validar impuestos o predeterminados**</span><span class="sxs-lookup"><span data-stu-id="a05eb-139">**Default/Validate sales tax**</span></span>
    -   <span data-ttu-id="a05eb-140">**Dimensión predeterminada**: **Valor no fijo** o **Valor fijo**.</span><span class="sxs-lookup"><span data-stu-id="a05eb-140">**Default dimension** – **Not fixed** or **Fixed value**.</span></span> <span data-ttu-id="a05eb-141">**Valor fijo** ayudará a garantizar que todos los registros para esta cuenta principal usan siempre un valor de dimensión que está configurado como **Fijo**.</span><span class="sxs-lookup"><span data-stu-id="a05eb-141">**Fixed value** will help guarantee that all postings for this main account always use any dimension value that is set up as **Fixed**.</span></span>
-   <span data-ttu-id="a05eb-142">**Validación del registro**</span><span class="sxs-lookup"><span data-stu-id="a05eb-142">**Posting validation**</span></span>
    -   <span data-ttu-id="a05eb-143">**Validación de usuario:** esta opción controla qué usuarios pueden registrar en una cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="a05eb-143">**User validation** – This option controls which users are allowed to post to a main account.</span></span>
    -   <span data-ttu-id="a05eb-144">**Validación de tipo de registro:** esta opción controla qué tipos de registro se premiten en una cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="a05eb-144">**Posting type validation** – This option controls which posting types are allowed for a main account.</span></span>

### <a name="accounting-structures-and-advanced-rules-structures"></a><span data-ttu-id="a05eb-145">Estructuras contables y estructuras de reglas avanzadas</span><span class="sxs-lookup"><span data-stu-id="a05eb-145">Accounting structures and advanced rules structures</span></span>

<span data-ttu-id="a05eb-146">Las estructuras contables y las estructuras de reglas avanzadas son muy importantes para garantizar que los datos necesarios para los informes financieros y el seguimiento del rendimiento se capture durante el proceso del diario general y la documentación.</span><span class="sxs-lookup"><span data-stu-id="a05eb-146">Accounting structures and advanced rules structures are extremely important for guaranteeing that the data that is required for financial reporting and performance tracking is captured during general journal processing and any documentation.</span></span> <span data-ttu-id="a05eb-147">Las estructuras contables y las estructuras de reglas avanzadas le permiten adaptar la experiencia de entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="a05eb-147">Accounting structures and advanced rules structures let you tailor the data entry experience.</span></span> <span data-ttu-id="a05eb-148">Puede permitir la entrada de datos solo para las dimensiones financieras que son relevantes en cada situación, y también puede exigir el requisito de que los datos necesarios y correctos se capturen siempre.</span><span class="sxs-lookup"><span data-stu-id="a05eb-148">You can allow data entry only for financial dimensions that are relevant in each situation, and can also enforce the requirement that mandatory and correct data always be captured.</span></span>

<span data-ttu-id="a05eb-149">Para obtener más información, consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="a05eb-149">For more information, see the following topics:</span></span>
- <span data-ttu-id="a05eb-150">[Planificación: plan de cuentas](plan-chart-of-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="a05eb-150">[Planning: Chart of accounts](plan-chart-of-accounts.md).</span></span> 
- [<span data-ttu-id="a05eb-151">Crear reglas avanzadas para diarios</span><span class="sxs-lookup"><span data-stu-id="a05eb-151">Create advanced rules for journals</span></span>](tasks/create-advanced-rules-journals.md)
- [<span data-ttu-id="a05eb-152">Crear un movimiento de diario mediante una plantilla</span><span class="sxs-lookup"><span data-stu-id="a05eb-152">Create a journal entry using a template</span></span>](tasks/create-journal-entry-template.md)
- [<span data-ttu-id="a05eb-153">Crear y validar diarios</span><span class="sxs-lookup"><span data-stu-id="a05eb-153">Create and validate journals</span></span>](tasks/create-validate-journals.md)
- [<span data-ttu-id="a05eb-154">Registrar diarios periódicos</span><span class="sxs-lookup"><span data-stu-id="a05eb-154">Post periodic journals</span></span>](tasks/post-periodic-journals.md)
- [<span data-ttu-id="a05eb-155">Procesar diario de asignaciones contables</span><span class="sxs-lookup"><span data-stu-id="a05eb-155">Process ledger allocation journal</span></span>](tasks/process-ledger-allocation-journal.md)



