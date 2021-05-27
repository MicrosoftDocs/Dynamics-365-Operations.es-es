---
title: Configurar cuentas contables de TDS
description: Este tema explica cómo configurar cuentas contables para la características de impuestos deducidos en el origen (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 93d4cb54488ec0eeee40ca56f3e46f30012f54f5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023567"
---
# <a name="set-up-tds-ledger-accounts"></a><span data-ttu-id="4f264-103">Configurar cuentas contables de TDS</span><span class="sxs-lookup"><span data-stu-id="4f264-103">Set up TDS ledger accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4f264-104">Este tema explica cómo configurar cuentas contables para la características de impuestos deducidos en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="4f264-104">This topic explains how to set up ledger accounts for the Tax Deducted at Source (TDS) feature.</span></span> <span data-ttu-id="4f264-105">Use la página **Plan de cuentas** para configurar cuentas contables para TDS.</span><span class="sxs-lookup"><span data-stu-id="4f264-105">You use the **Chart of accounts** page to set up ledger accounts for TDS.</span></span>

1. <span data-ttu-id="4f264-106">Vaya a **Contabilidad general \> Plan de cuentas \> Cuentas \> Cuentas principales**.</span><span class="sxs-lookup"><span data-stu-id="4f264-106">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**.</span></span>
2. <span data-ttu-id="4f264-107">En la pestaña **Información general**, seleccione **Alt + N** para crear una cuenta contable de TDS e introduzca los detalles necesarios.</span><span class="sxs-lookup"><span data-stu-id="4f264-107">On the **Overview** tab, select **Alt+N** to create a TDS ledger account, and enter the required details.</span></span>
3. <span data-ttu-id="4f264-108">En la pestaña **Configuración**, en el campo **Tipo de registro**, seleccione **Retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="4f264-108">On the **Setup** tab, in the **Posting type** field, select **Withholding tax**.</span></span>     

    > [!NOTE]
    > <span data-ttu-id="4f264-109">Las cuentas contables que tienen un tipo de registro de **Retención de impuestos** solo se puede definir como cuentas de clientes que se utilizan para registrar el importe de la cuenta de cliente de TDS para un código de impuestos de TDS.</span><span class="sxs-lookup"><span data-stu-id="4f264-109">Ledger accounts that have a posting type of **Withholding tax** can be defined only as receivable accounts that are used to post the TDS receivable amount for a TDS tax code.</span></span>

4. <span data-ttu-id="4f264-110">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4f264-110">Close the page.</span></span>
