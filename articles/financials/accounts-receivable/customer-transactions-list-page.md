---
title: "Página de lista de transacciones de cliente"
description: "Este tema proporciona información acerca de la página de lista de transacciones de cliente para Microsoft Dynamics 365 for Finance and Operations."
author: mikefalkner
manager: aolson
ms.date: 08/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e828cb292ad48bb4690117b41589b25edcdf28bc
ms.contentlocale: es-es
ms.lasthandoff: 08/31/2018

---

# <a name="customer-transaction-list-page"></a><span data-ttu-id="81f0e-103">Página de lista de transacciones de cliente</span><span class="sxs-lookup"><span data-stu-id="81f0e-103">Customer transaction list page</span></span>

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a><span data-ttu-id="81f0e-104">Ver liquidaciones</span><span class="sxs-lookup"><span data-stu-id="81f0e-104">View settlements</span></span>

<span data-ttu-id="81f0e-105">La pestaña **Ver liquidaciones** en el panel de acciones proporciona un acceso rápido al historial de liquidaciones e información adicional acerca de la transacción de liquidación completa.</span><span class="sxs-lookup"><span data-stu-id="81f0e-105">The **View settlements** tab on the action pane provides quick access to settlement history and more information about the whole settlement transaction.</span></span> <span data-ttu-id="81f0e-106">También puede mostrar transacciones adicionales relacionadas con la transacción seleccionada, ya sea porque formaban parte de la misma liquidación o porque son los pagos que se crearon en el mismo diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="81f0e-106">You can also show additional transactions that are related to the selected transaction, either because they were part of the same settlement or because they are payments that were created in the same payment journal.</span></span>

1. <span data-ttu-id="81f0e-107">Seleccione **Clientes \> Clientes**.</span><span class="sxs-lookup"><span data-stu-id="81f0e-107">Select **Accounts receivable \> Customers**.</span></span>
2. <span data-ttu-id="81f0e-108">Seleccione un cliente que tenga transacciones y, a continuación seleccione **Cliente \> Transacciones**.</span><span class="sxs-lookup"><span data-stu-id="81f0e-108">Select a customer that has transactions, and then select **Customer \> Transactions**.</span></span>
3. <span data-ttu-id="81f0e-109">Seleccionar una transacción para investigarla.</span><span class="sxs-lookup"><span data-stu-id="81f0e-109">Select a transaction to research.</span></span>
4. <span data-ttu-id="81f0e-110">Seleccione la pestaña **Ver liquidaciones** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="81f0e-110">Select the **View settlements** tab on the action pane.</span></span>

    <span data-ttu-id="81f0e-111">El cuadro de diálogo **Ver liquidaciones** muestra la transacción seleccionada y todos los documentos que se han liquidado con ella.</span><span class="sxs-lookup"><span data-stu-id="81f0e-111">The **View settlements** dialog box shows the selected transaction and all documents that have been settled against it.</span></span> <span data-ttu-id="81f0e-112">Este cuadro de diálogo es similar a la vista de historial de liquidaciones, pero incluye todos los documentos relacionados.</span><span class="sxs-lookup"><span data-stu-id="81f0e-112">This dialog box resembles the settlement history view, but it includes all related documents.</span></span> 

5. <span data-ttu-id="81f0e-113">Puede realizar varias tareas de este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="81f0e-113">You can perform various tasks from this dialog box.</span></span> <span data-ttu-id="81f0e-114">Seleccione uno o más asientos y luego seleccione uno de los menús siguientes:</span><span class="sxs-lookup"><span data-stu-id="81f0e-114">Select one or more vouchers, and then select one of the following menus:</span></span>

   - <span data-ttu-id="81f0e-115">**Ver contabilidad** - Se ven todos los asientos que están relacionados con los documentos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="81f0e-115">**View accounting** – All vouchers that are related to the selected documents appear.</span></span> <span data-ttu-id="81f0e-116">Haga clic en **Cerrar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="81f0e-116">Select **Close** to close the dialog box.</span></span>
   - <span data-ttu-id="81f0e-117">**Exportar** Exporte los asientos seleccionados a Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="81f0e-117">**Export** – Export the selected vouchers to Microsoft Excel.</span></span>
   - <span data-ttu-id="81f0e-118">**Ver pagos relacionados** Todas las transacciones del diario de pagos creadas en el diario de pagos relacionado con el documento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="81f0e-118">**View related payments** – All the payment journal transactions that were created in the payment journal that is related to the selected document appear.</span></span> <span data-ttu-id="81f0e-119">Además, aparecen todas las liquidaciones relacionadas con los pagos.</span><span class="sxs-lookup"><span data-stu-id="81f0e-119">In addition, all the settlements that are related to those payments appear.</span></span> <span data-ttu-id="81f0e-120">La etiqueta de este menú también cambia a **Ver liquidaciones**.</span><span class="sxs-lookup"><span data-stu-id="81f0e-120">The label of this menu also changes to **View settlements**.</span></span> <span data-ttu-id="81f0e-121">Seleccione **Ver liquidaciones** para mostrar sólo las transacciones que se mostraron cuando abrió por primera vez el cuadro de diálogo **Ver liquidaciones**.</span><span class="sxs-lookup"><span data-stu-id="81f0e-121">Select **View settlements** to show only the transactions that were shown when you first opened the  **View settlements** dialog box.</span></span>
    - <span data-ttu-id="81f0e-122">**Liquidar transacciones** Este menú aparece si el documento original seleccionado no se ha liquidado por completo.</span><span class="sxs-lookup"><span data-stu-id="81f0e-122">**Settle transactions** – This menu appears if the original document that was selected wasn't fully settled.</span></span> <span data-ttu-id="81f0e-123">Al seleccionarlo, el cuadro de diálogo **Liquidar transacciones** aparece, donde puede seleccionar las transacciones que quiere liquidar.</span><span class="sxs-lookup"><span data-stu-id="81f0e-123">When you select it, the **Settle transactions** dialog box appears, where you can select transactions for settlement.</span></span>
    - <span data-ttu-id="81f0e-124">**Deshacer liquidación** Este menú aparece si el documento original seleccionado se liquidó por completo.</span><span class="sxs-lookup"><span data-stu-id="81f0e-124">**Undo settlements** – This menu appears if the original document that was selected was fully settled.</span></span> <span data-ttu-id="81f0e-125">Al seleccionarlo, el cuadro de diálogo **Deshacer liquidación** aparece, donde puede deshacer liquidaciones que se realizaron para dicho documento.</span><span class="sxs-lookup"><span data-stu-id="81f0e-125">When you select it, the **Undo settlements** dialog box appears, where you can undo the settlements that were done for that document.</span></span>
    

