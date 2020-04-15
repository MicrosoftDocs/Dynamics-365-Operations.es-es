---
title: Configurar cuentas bancarias de empresa para débitos directos ISO20022
description: Esta tarea le explica cómo configurar la información de la cuenta bancaria específica de la empresa necesaria para generar archivos de pago de cliente.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 652d8aa8f78d9a12ee390d23904f2c94d9bcf684
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144881"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="cd106-103">Configurar cuentas bancarias de empresa para débitos directos ISO20022</span><span class="sxs-lookup"><span data-stu-id="cd106-103">Set up company bank accounts for ISO20022 direct debits</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cd106-104">Esta tarea le explica cómo configurar la información de la cuenta bancaria específica de la empresa necesaria para generar archivos de pago de cliente.</span><span class="sxs-lookup"><span data-stu-id="cd106-104">This task walks you through setting up the company specific bank account information that is required for generating customer payment files.</span></span> <span data-ttu-id="cd106-105">Este procedimiento usa el formato de débito directo ISO 20022 como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cd106-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> <span data-ttu-id="cd106-106">Otros formatos pueden requerir información de configuración adicional como el identificador de empresa o el código de ordenación.</span><span class="sxs-lookup"><span data-stu-id="cd106-106">Other formats might require additional setup information like the Company ID or the Sort code.</span></span>



<span data-ttu-id="cd106-107">Esta tarea se creó con los datos de demostración de la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="cd106-107">This task was created using the demo data company DEMF.</span></span>



<span data-ttu-id="cd106-108">Este es el segundo de cinco procedimientos que muestra el proceso de pago del cliente mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="cd106-108">This is the second of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-the-iban-and-swift-codes"></a><span data-ttu-id="cd106-109">Configuración de códigos IBAN y SWIFT</span><span class="sxs-lookup"><span data-stu-id="cd106-109">Set up the IBAN and SWIFT codes</span></span>
1. <span data-ttu-id="cd106-110">Vaya a Gestión de efectivo y bancos > Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="cd106-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="cd106-111">Use un filtro rápido para filtrar por el campo Cuenta bancaria, por el valor ''DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="cd106-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="cd106-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cd106-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="cd106-113">Por ejemplo, haga clic en "DEMF OPER" para abrir los detalles de la cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="cd106-113">For example, click 'DEMF OPER' to open the bank account details.</span></span>  
4. <span data-ttu-id="cd106-114">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="cd106-114">Click Edit.</span></span>
5. <span data-ttu-id="cd106-115">Expanda o contraiga la sección Identificación adicional.</span><span class="sxs-lookup"><span data-stu-id="cd106-115">Expand or collapse the Additional identification section.</span></span>
6. <span data-ttu-id="cd106-116">Escriba un valor en el campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="cd106-116">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="cd106-117">Por ejemplo, escriba "DE89370400440532013000".</span><span class="sxs-lookup"><span data-stu-id="cd106-117">For example, enter 'DE89370400440532013000'.</span></span>  
7. <span data-ttu-id="cd106-118">En el campo Código SWIFT, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cd106-118">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="cd106-119">Por ejemplo, especifique "DEUTDEFF".</span><span class="sxs-lookup"><span data-stu-id="cd106-119">For example, enter 'DEUTDEFF'.</span></span>    <span data-ttu-id="cd106-120">Tenga en cuenta que no requiere SWIFT\BIC para muchos formatos de pago, aunque se recomienda tenerlos registrados para una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="cd106-120">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="cd106-121">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="cd106-121">Click Save.</span></span>

## <a name="set-up-a-bank-account-for-the-legal-entity"></a><span data-ttu-id="cd106-122">Configuración de una cuenta bancaria para la entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="cd106-122">Set up a bank account for the legal entity</span></span>
1. <span data-ttu-id="cd106-123">Vaya a Administración de la organización > Organizaciones > Entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="cd106-123">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="cd106-124">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="cd106-124">Click Edit.</span></span>
3. <span data-ttu-id="cd106-125">Expanda o contraiga la sección Información de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="cd106-125">Expand or collapse the Bank account information section.</span></span>
4. <span data-ttu-id="cd106-126">En el campo Cuenta bancaria, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cd106-126">In the Bank account field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="cd106-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cd106-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="cd106-128">Por ejemplo, seleccione la cuenta bancaria "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="cd106-128">For example, select the "DEMF OPER" bank account.</span></span>  
6. <span data-ttu-id="cd106-129">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="cd106-129">Click Save.</span></span>

