---
title: "Página de lista de transacciones de proveedor"
description: "Este tema proporciona información acerca de la página de lista de transacciones de proveedor para Microsoft Dynamics 365 for Finance and Operations."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 1ef7d97f059801f2fb2c0d451546b57055208f81
ms.contentlocale: es-es
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-transaction-list-page"></a><span data-ttu-id="34c02-103">Página de lista de transacciones de proveedor</span><span class="sxs-lookup"><span data-stu-id="34c02-103">Vendor transaction list page</span></span>

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a><span data-ttu-id="34c02-104">Ver liquidaciones</span><span class="sxs-lookup"><span data-stu-id="34c02-104">View settlements</span></span>

<span data-ttu-id="34c02-105">La pestaña **Ver liquidaciones** en el panel de acciones proporciona un acceso rápido al historial de liquidaciones e información adicional acerca de la transacción de liquidación completa.</span><span class="sxs-lookup"><span data-stu-id="34c02-105">The **View settlements** tab on the action pane provides quick access to settlement history and more information about the whole settlement transaction.</span></span> <span data-ttu-id="34c02-106">También puede mostrar transacciones adicionales relacionadas con la transacción seleccionada, ya sea porque formaban parte de la misma liquidación o porque son los pagos que se crearon en el mismo diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="34c02-106">You can also show additional transactions that are related to the selected transaction, either because they were part of the same settlement or because they are payments that were created in the same payment journal.</span></span>

1. <span data-ttu-id="34c02-107">Seleccione **Proveedores \> Todos los proveedores**.</span><span class="sxs-lookup"><span data-stu-id="34c02-107">Select **Accounts payable \> All vendors**.</span></span>
2. <span data-ttu-id="34c02-108">Seleccione un proveedor que tenga transacciones y, a continuación, seleccione **Proveedor \> Transacciones**.</span><span class="sxs-lookup"><span data-stu-id="34c02-108">Select a vendor that has transactions, and then select **Vendor \> Transactions**.</span></span>
3. <span data-ttu-id="34c02-109">Seleccionar una transacción para investigarla.</span><span class="sxs-lookup"><span data-stu-id="34c02-109">Select a transaction to research.</span></span>
4. <span data-ttu-id="34c02-110">Seleccione la pestaña **Ver liquidaciones** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="34c02-110">Select the **View settlements** tab on the action pane.</span></span>

    <span data-ttu-id="34c02-111">El cuadro de diálogo **Ver liquidaciones** se abre y muestra la transacción seleccionada y todos los documentos que liquidan con ella.</span><span class="sxs-lookup"><span data-stu-id="34c02-111">The **View settlements** dialog box opens and shows the selected transaction and all documents that are settled against it.</span></span> <span data-ttu-id="34c02-112">Este cuadro de diálogo es similar a la vista de historial de liquidaciones, pero incluye todos los documentos relacionados.</span><span class="sxs-lookup"><span data-stu-id="34c02-112">This dialog box resembles the settlement history view, but it includes all related documents.</span></span>

5. <span data-ttu-id="34c02-113">Puede realizar varias tareas de este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="34c02-113">You can perform various tasks from this dialog box.</span></span> <span data-ttu-id="34c02-114">Seleccione uno o más asientos y luego seleccione uno de los menús siguientes:</span><span class="sxs-lookup"><span data-stu-id="34c02-114">Select one or more vouchers, and then select one of the following menus:</span></span>

   - <span data-ttu-id="34c02-115">**Ver contabilidad** - Se ven todos los asientos que están relacionados con los documentos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="34c02-115">**View accounting** – All vouchers that are related to the selected documents appear.</span></span> <span data-ttu-id="34c02-116">Haga clic en **Cerrar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="34c02-116">Select **Close** to close the dialog box.</span></span>
   - <span data-ttu-id="34c02-117">**Exportar** Exporte los asientos seleccionados a Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="34c02-117">**Export** – Export the selected vouchers to Microsoft Excel.</span></span>
   - <span data-ttu-id="34c02-118">**Ver pagos relacionados** Todas las transacciones del diario de pagos creadas en el diario de pagos relacionado con el documento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="34c02-118">**View related payments** – All the payment journal transactions that were created in the payment journal that is related to the selected document appear.</span></span> <span data-ttu-id="34c02-119">Además, aparecen todas las liquidaciones relacionadas con los pagos.</span><span class="sxs-lookup"><span data-stu-id="34c02-119">In addition, all the settlements that are related to those payments appear.</span></span> <span data-ttu-id="34c02-120">La etiqueta de este menú también cambia a **Ver liquidaciones**.</span><span class="sxs-lookup"><span data-stu-id="34c02-120">The label of this menu also changes to **View settlements**.</span></span> <span data-ttu-id="34c02-121">Seleccione **Ver liquidaciones** para mostrar sólo las transacciones que se mostraron cuando abrió por primera vez el cuadro de diálogo **Ver liquidaciones**.</span><span class="sxs-lookup"><span data-stu-id="34c02-121">Select **View settlements** to show only the transactions that were shown when you first opened the  **View settlements** dialog box.</span></span>
    - <span data-ttu-id="34c02-122">**Liquidar transacciones** Este menú aparece si el documento original seleccionado no se ha liquidado por completo.</span><span class="sxs-lookup"><span data-stu-id="34c02-122">**Settle transactions** – This menu appears if the original document that was selected wasn't fully settled.</span></span> <span data-ttu-id="34c02-123">Al seleccionarlo, el cuadro de diálogo **Liquidar transacciones** aparece, donde puede seleccionar las transacciones que quiere liquidar.</span><span class="sxs-lookup"><span data-stu-id="34c02-123">When you select it, the **Settle transactions** dialog box appears, where you can select transactions for settlement.</span></span>
    - <span data-ttu-id="34c02-124">**Deshacer liquidación** Este menú aparece si el documento original seleccionado se liquidó por completo.</span><span class="sxs-lookup"><span data-stu-id="34c02-124">**Undo settlements** – This menu appears if the original document that was selected was fully settled.</span></span> <span data-ttu-id="34c02-125">Al seleccionarlo, el cuadro de diálogo **Deshacer liquidación** aparece, donde puede deshacer liquidaciones que se realizaron para dicho documento.</span><span class="sxs-lookup"><span data-stu-id="34c02-125">When you select it, the **Undo settlements** dialog box appears, where you can undo the settlements that were done for that document.</span></span>

