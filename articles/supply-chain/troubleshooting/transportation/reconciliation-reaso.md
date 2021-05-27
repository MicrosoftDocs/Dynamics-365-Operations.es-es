---
title: Puede agregar solo la cuenta principal como cuenta de crédito por motivos de conciliación
description: Cuando configura un motivo de conciliación en la Administración de transporte, puede agregar solo la cuenta principal como cuenta de crédito.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026867"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a><span data-ttu-id="0483a-103">Puede agregar solo la cuenta principal como cuenta de crédito por motivos de conciliación</span><span class="sxs-lookup"><span data-stu-id="0483a-103">You can add only the main account as the credit account for reconciliation reasons</span></span>

<span data-ttu-id="0483a-104">Número de KB: 4603538</span><span class="sxs-lookup"><span data-stu-id="0483a-104">KB number: 4603538</span></span>

## <a name="symptoms"></a><span data-ttu-id="0483a-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="0483a-105">Symptoms</span></span>

<span data-ttu-id="0483a-106">Cuando configura un motivo de conciliación en la Administración de transporte, puede agregar solo la cuenta principal como cuenta de crédito.</span><span class="sxs-lookup"><span data-stu-id="0483a-106">When you set up a reconciliation reason in Transportation management, you can add only the main account as the credit account.</span></span> <span data-ttu-id="0483a-107">No puede agregar un centro de coste o cualquier otra dimensión como la cuenta de crédito.</span><span class="sxs-lookup"><span data-stu-id="0483a-107">You can't add a cost center or any other dimension as the credit account.</span></span> <span data-ttu-id="0483a-108">Sin embargo, la cuenta de débito le permite seleccionar otras dimensiones.</span><span class="sxs-lookup"><span data-stu-id="0483a-108">However, the debit account lets you select other dimensions.</span></span>

## <a name="resolution"></a><span data-ttu-id="0483a-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="0483a-109">Resolution</span></span>

<span data-ttu-id="0483a-110">Si la conciliación no se realiza para pagar al proveedor, sino para acreditar una cuenta principal específica, el sistema no le permite seleccionar una dimensión financiera para la cuenta de crédito cuando configura el motivo de conciliación.</span><span class="sxs-lookup"><span data-stu-id="0483a-110">If the reconciliation isn't done to pay the vendor but to credit a specific main account, the system doesn't allow you to select a financial dimension for the credit account when you set up the reconciliation reason.</span></span>

<span data-ttu-id="0483a-111">Si la estructura contable necesita un valor de dimensión financiera específico para la cuenta principal de crédito, el diario del proveedor resultante no se puede registrar automáticamente porque falta el valor de la dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="0483a-111">If the account structure requires a specific financial dimension value for the credit main account, the resulting vendor journal can't be posted automatically, because the financial dimension value is missing.</span></span> <span data-ttu-id="0483a-112">Por lo tanto, primero debe especificar manualmente la cuenta de crédito mediante la página **Diario de facturas**.</span><span class="sxs-lookup"><span data-stu-id="0483a-112">Therefore, you must first manually specify the credit account by using the **Invoice journal** page.</span></span>

<span data-ttu-id="0483a-113">Debido a que se necesita un valor de dimensión para la cuenta de crédito, el diario de facturas del proveedor no se puede registrar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0483a-113">Because a dimension value is required for the credit account, the vendor invoice journal can't be automatically posted.</span></span> <span data-ttu-id="0483a-114">Debe registrarlo manualmente después de agregar manualmente el valor de dimensión a la cuenta principal para la línea de crédito.</span><span class="sxs-lookup"><span data-stu-id="0483a-114">You must manually post it after you manually add the dimension value to the main account for the credit line.</span></span>
