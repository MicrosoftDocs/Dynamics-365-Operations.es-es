---
title: Crear un contrato de crédito bancario para un crédito documentario
description: Esta tarea le lleva por la creación de un contrato de instalaciones bancarias para procesar un crédito documentario.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankDocumentFacilityAgreement, BankAccountTableLookUp, BankDocumentFacilityAgreementExtension, DefaultDashboard
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e63e0ffa4ddafd38595d7e9d84ffa2399a9f67b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188220"
---
# <a name="create-a-bank-facility-agreement-for-a-letter-of-credit"></a><span data-ttu-id="74424-103">Crear un contrato de crédito bancario para un crédito documentario</span><span class="sxs-lookup"><span data-stu-id="74424-103">Create a bank facility agreement for a letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="74424-104">Esta tarea le lleva por la creación de un contrato de instalaciones bancarias para procesar un crédito documentario.</span><span class="sxs-lookup"><span data-stu-id="74424-104">This task walks through the creating a Bank facility agreement to process a Letter of credit.</span></span> <span data-ttu-id="74424-105">Es conveniente configurar los créditos bancarios y los perfiles de contabilización antes de realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="74424-105">You will want to set up bank facilities and posting profiles before this task.</span></span>  <span data-ttu-id="74424-106">Esta tarea usa la empresa de demostración "USMF".</span><span class="sxs-lookup"><span data-stu-id="74424-106">This task uses the demo company 'USMF'.</span></span>  


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="74424-107">Crear un contrato de instalaciones bancarias</span><span class="sxs-lookup"><span data-stu-id="74424-107">Create Bank facility agreement</span></span>
1. <span data-ttu-id="74424-108">Vaya a Gestión de efectivo y bancos > Créditos documentarios > Contratos de instalaciones bancarias.</span><span class="sxs-lookup"><span data-stu-id="74424-108">Go to Cash and bank management > Letters of credit > Bank facility agreements.</span></span>
2. <span data-ttu-id="74424-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="74424-109">Click New.</span></span>
3. <span data-ttu-id="74424-110">En el campo de Número de contrato, especifique el número de contrato según el acuerdo con el banco.</span><span class="sxs-lookup"><span data-stu-id="74424-110">In the Agreement number field, enter the agreement number according to the agreement with the bank.</span></span>
4. <span data-ttu-id="74424-111">En el campo Cuenta bancaria, indique el número de cuenta bancaria en el banco emisor.</span><span class="sxs-lookup"><span data-stu-id="74424-111">In the Bank account field, enter the account number at the issuing bank.</span></span>
5. <span data-ttu-id="74424-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="74424-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="74424-113">En el campo Fecha inicial, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="74424-113">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="74424-114">En el campo Fecha final, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="74424-114">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="74424-115">Expanda o contraiga la sección General.</span><span class="sxs-lookup"><span data-stu-id="74424-115">Expand or collapse the General section.</span></span>
9. <span data-ttu-id="74424-116">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="74424-116">Click Add line.</span></span>
10. <span data-ttu-id="74424-117">En el campo Tipo de instalación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="74424-117">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="74424-118">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="74424-118">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="74424-119">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="74424-119">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="74424-120">En el campo Límite, especifique el importe de crédito negociado con el banco.</span><span class="sxs-lookup"><span data-stu-id="74424-120">In the Limit field, enter the facility amount that was negotiated with the bank.</span></span>
14. <span data-ttu-id="74424-121">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="74424-121">Click Save.</span></span>
15. <span data-ttu-id="74424-122">Haga clic en Extender para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="74424-122">Click Extend to open the drop dialog.</span></span>
16. <span data-ttu-id="74424-123">En el campo Nuevo número de contrato, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="74424-123">In the New agreement number field, type a value.</span></span>
17. <span data-ttu-id="74424-124">En el campo Fecha final, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="74424-124">In the End date field, enter a date and time.</span></span>
18. <span data-ttu-id="74424-125">Haga clic en Extender.</span><span class="sxs-lookup"><span data-stu-id="74424-125">Click Extend.</span></span>
19. <span data-ttu-id="74424-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="74424-126">Close the page.</span></span>

