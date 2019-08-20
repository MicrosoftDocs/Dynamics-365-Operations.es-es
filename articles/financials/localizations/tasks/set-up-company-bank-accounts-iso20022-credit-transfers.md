---
title: Configurar cuentas bancarias de la empresa para transferencias de crédito ISO20022
description: Este procedimiento muestra cómo configurar la información de cuenta bancaria específica de empresa necesaria para generar el archivo de pago.
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
ms.openlocfilehash: 2bbbf55ed28ad2131d7e1253dd44842d85d39315
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848753"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="35b17-103">Configurar cuentas bancarias de la empresa para transferencias de crédito ISO20022</span><span class="sxs-lookup"><span data-stu-id="35b17-103">Set up company bank accounts for ISO20022 credit transfers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="35b17-104">Este procedimiento muestra cómo configurar la información de cuenta bancaria específica de empresa necesaria para generar el archivo de pago.</span><span class="sxs-lookup"><span data-stu-id="35b17-104">This procedure shows how to set up company-specific bank account information that is required for payment file generation.</span></span> <span data-ttu-id="35b17-105">Debe configurar la información necesaria para generar el formato de transferencia de crédito ISO 20022 pero en función del formato es posible que se precise otra información, como el identificador de empresa o el código de ordenación.</span><span class="sxs-lookup"><span data-stu-id="35b17-105">You set up information required to generate ISO 20022 credit transfer format but depending on the format there might be other information required, such as the Company ID or the Sort code.</span></span> 

<span data-ttu-id="35b17-106">La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.</span><span class="sxs-lookup"><span data-stu-id="35b17-106">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="35b17-107">Este es el segundo procedimiento, de cinco, que muestra el proceso de pago del proveedor mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="35b17-107">This is the second procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="35b17-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="35b17-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-iban-and-swift-code"></a><span data-ttu-id="35b17-109">Configuración del IBAN y el código SWIFT</span><span class="sxs-lookup"><span data-stu-id="35b17-109">Set up IBAN and SWIFT code</span></span>
1. <span data-ttu-id="35b17-110">Vaya a Gestión de efectivo y bancos > Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="35b17-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="35b17-111">Use un filtro rápido para filtrar por el campo Cuenta bancaria, por el valor ''DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="35b17-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="35b17-112">Haga clic en DEMF OPER para abrir los detalles de la cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="35b17-112">Click DEMF OPER to open bank account details.</span></span>
4. <span data-ttu-id="35b17-113">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="35b17-113">Click Edit.</span></span>
5. <span data-ttu-id="35b17-114">Expanda la sección Identificación adicional.</span><span class="sxs-lookup"><span data-stu-id="35b17-114">Expand the Additional identification section.</span></span>
6. <span data-ttu-id="35b17-115">En el campo IBAN, escriba ''DE89370400440532013000".</span><span class="sxs-lookup"><span data-stu-id="35b17-115">In the IBAN field, type 'DE89370400440532013000'.</span></span>
7. <span data-ttu-id="35b17-116">En el campo Código SWIFT, escriba "DEUTDEFF".</span><span class="sxs-lookup"><span data-stu-id="35b17-116">In the SWIFT code field, type 'DEUTDEFF'.</span></span>
    * <span data-ttu-id="35b17-117">Tenga en cuenta que no requiere SWIFT\BIC para muchos formatos de pago, aunque se recomienda tenerlos registrados para una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="35b17-117">Note that SWIFT\BIC is not required for many payment formats, however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="35b17-118">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="35b17-118">Click Save.</span></span>

## <a name="set-up-bank-account-for-the-legal-entity"></a><span data-ttu-id="35b17-119">Configuración de la cuenta bancaria para la entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="35b17-119">Set up bank account for the legal entity</span></span>
1. <span data-ttu-id="35b17-120">Vaya a Administración de la organización > Organizaciones > Entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="35b17-120">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="35b17-121">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="35b17-121">Click Edit.</span></span>
3. <span data-ttu-id="35b17-122">Expanda la sección Información de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="35b17-122">Expand the Bank account information section.</span></span>
4. <span data-ttu-id="35b17-123">En el campo Cuenta bancaria, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="35b17-123">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="35b17-124">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="35b17-124">Click Save.</span></span>

