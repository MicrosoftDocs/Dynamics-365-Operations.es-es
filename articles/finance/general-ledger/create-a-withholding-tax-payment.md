---
title: Crear un pago de retención de impuestos
description: El procedimiento de la tarea Pago de retención de impuestos liquida los saldos de retención de impuestos de Proveedores en las cuentas de retención de impuestos y los anota como contrapartida en la cuenta de liquidación retención de impuestos para un período determinado. Este tema enumera los pasos para configurar un pago de retención de impuestos.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 72d80fbb3b2448f4b89fa7d7fa580387e1a3621c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832955"
---
# <a name="create-a-withholding-tax-payment"></a><span data-ttu-id="61d3f-104">Crear un pago de retención de impuestos</span><span class="sxs-lookup"><span data-stu-id="61d3f-104">Create a withholding tax payment</span></span>

<span data-ttu-id="61d3f-105">El procedimiento de la tarea Pago de retención de impuestos liquida los saldos de retención de impuestos de Proveedores en las cuentas de retención de impuestos y los anota como contrapartida en la cuenta de liquidación retención de impuestos para un período determinado.</span><span class="sxs-lookup"><span data-stu-id="61d3f-105">The Withholding tax payment job procedure settles withholding tax balances from Accounts payable on withholding tax accounts, and offsets them to the withholding tax settlement account for a given period.</span></span> <span data-ttu-id="61d3f-106">Este tema enumera los pasos para configurar un pago de retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="61d3f-106">This topic lists the steps for setting up a withholding tax payment.</span></span>

> [!NOTE] 
> <span data-ttu-id="61d3f-107">La compensación de retención de impuestos (de clientes) no se tiene en cuenta al calcular un pago de retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="61d3f-107">Withholding tax offset (from accounts receivable) is not taken into account when a withholding tax payment is calculated.</span></span>

1. <span data-ttu-id="61d3f-108">Vaya **Panel de navegación > Módulos > Impuestos > Declaraciones > Retención de impuestos > Pago de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="61d3f-108">Go to **Navigation pane > Modules > Tax > Declarations > Withholding tax > Withholding tax payment**.</span></span>
2. <span data-ttu-id="61d3f-109">En el campo **Período de liquidación**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="61d3f-109">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="61d3f-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="61d3f-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="61d3f-111">En el campo **Fecha inicial**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="61d3f-111">In the **From date** field, enter a date.</span></span>
5. <span data-ttu-id="61d3f-112">En el campo **Fecha de transacción**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="61d3f-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="61d3f-113">Seleccione **Actualizar** para registrar el vale de pago de retención de impuestos en la cuenta de liquidación de retención de impuestos.</span><span class="sxs-lookup"><span data-stu-id="61d3f-113">Select **Update** to post withholding tax payment voucher to the withholding tax settlement account.</span></span>
7. <span data-ttu-id="61d3f-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="61d3f-114">Click **OK**.</span></span>

![Parámetros para el pago de la retención de impuestos](media/withholding-tax-payment.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]