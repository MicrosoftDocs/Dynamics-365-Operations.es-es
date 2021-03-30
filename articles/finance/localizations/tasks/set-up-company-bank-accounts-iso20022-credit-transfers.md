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
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5ad1ebbea9bca41f43f3f4098114116e32f8517b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205479"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="28181-103">Configurar cuentas bancarias de la empresa para transferencias de crédito ISO20022</span><span class="sxs-lookup"><span data-stu-id="28181-103">Set up company bank accounts for ISO20022 credit transfers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="28181-104">Este procedimiento muestra cómo configurar la información de cuenta bancaria específica de empresa necesaria para generar el archivo de pago.</span><span class="sxs-lookup"><span data-stu-id="28181-104">This procedure shows how to set up company-specific bank account information that is required for payment file generation.</span></span> <span data-ttu-id="28181-105">Debe configurar la información necesaria para generar el formato de transferencia de crédito ISO 20022 pero en función del formato es posible que se precise otra información, como el identificador de empresa o el código de ordenación.</span><span class="sxs-lookup"><span data-stu-id="28181-105">You set up information required to generate ISO 20022 credit transfer format but depending on the format there might be other information required, such as the Company ID or the Sort code.</span></span> 

<span data-ttu-id="28181-106">La empresa de datos de demostración utilizada para crear este procedimiento es DEMF.</span><span class="sxs-lookup"><span data-stu-id="28181-106">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="28181-107">Este es el segundo procedimiento, de cinco, que muestra el proceso de pago del proveedor mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="28181-107">This is the second procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="28181-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="28181-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-iban-and-swift-code"></a><span data-ttu-id="28181-109">Configuración del IBAN y el código SWIFT</span><span class="sxs-lookup"><span data-stu-id="28181-109">Set up IBAN and SWIFT code</span></span>
1. <span data-ttu-id="28181-110">Vaya a Gestión de efectivo y bancos > Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="28181-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="28181-111">Use un filtro rápido para filtrar por el campo Cuenta bancaria, por el valor ''DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="28181-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="28181-112">Haga clic en DEMF OPER para abrir los detalles de la cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="28181-112">Click DEMF OPER to open bank account details.</span></span>
4. <span data-ttu-id="28181-113">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="28181-113">Click Edit.</span></span>
5. <span data-ttu-id="28181-114">Expanda la sección Identificación adicional.</span><span class="sxs-lookup"><span data-stu-id="28181-114">Expand the Additional identification section.</span></span>
6. <span data-ttu-id="28181-115">En el campo IBAN, escriba ''DE89370400440532013000".</span><span class="sxs-lookup"><span data-stu-id="28181-115">In the IBAN field, type 'DE89370400440532013000'.</span></span>
7. <span data-ttu-id="28181-116">En el campo Código SWIFT, escriba "DEUTDEFF".</span><span class="sxs-lookup"><span data-stu-id="28181-116">In the SWIFT code field, type 'DEUTDEFF'.</span></span>
    * <span data-ttu-id="28181-117">Tenga en cuenta que no requiere SWIFT\BIC para muchos formatos de pago, aunque se recomienda tenerlos registrados para una cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="28181-117">Note that SWIFT\BIC is not required for many payment formats, however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="28181-118">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="28181-118">Click Save.</span></span>

## <a name="set-up-bank-account-for-the-legal-entity"></a><span data-ttu-id="28181-119">Configuración de la cuenta bancaria para la entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="28181-119">Set up bank account for the legal entity</span></span>
1. <span data-ttu-id="28181-120">Vaya a Administración de la organización > Organizaciones > Entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="28181-120">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="28181-121">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="28181-121">Click Edit.</span></span>
3. <span data-ttu-id="28181-122">Expanda la sección Información de cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="28181-122">Expand the Bank account information section.</span></span>
4. <span data-ttu-id="28181-123">En el campo Cuenta bancaria, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="28181-123">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="28181-124">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="28181-124">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]