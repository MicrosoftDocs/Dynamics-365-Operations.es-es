---
title: Abrir plantillas de diario financiero en Office
description: Este tema describe los problemas que pueden surgir al crear diarios financieros personalizados mediante una plantilla de Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0773f47551b2460ec310b92b67c634b433147749
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "6089466"
---
# <a name="open-financial-journal-templates-in-office"></a><span data-ttu-id="ced71-103">Abrir plantillas de diario financiero en Office</span><span class="sxs-lookup"><span data-stu-id="ced71-103">Open financial journal templates in Office</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ced71-104">Este tema describe los problemas que pueden surgir al crear diarios financieros personalizados mediante una plantilla de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="ced71-104">This topic describes issues that might occur when you create custom financial journals by using a Microsoft Excel template.</span></span>

## <a name="symptom"></a><span data-ttu-id="ced71-105">Síntoma</span><span class="sxs-lookup"><span data-stu-id="ced71-105">Symptom</span></span>

<span data-ttu-id="ced71-106">Ha creado una plantilla de Excel personalizada para diarios financieros, pero no aparece en el menú **Abrir líneas en Excel**.</span><span class="sxs-lookup"><span data-stu-id="ced71-106">You created a custom Excel template for financial journals, but it doesn't appear on the **Open lines in Excel** menu.</span></span> <span data-ttu-id="ced71-107">Alternativamente, aparece en el menú, se abre una plantilla diferente cuando la selecciona.</span><span class="sxs-lookup"><span data-stu-id="ced71-107">Alternatively, it does appear on the menu, a different template is opened but when you select it.</span></span>

## <a name="resolution"></a><span data-ttu-id="ced71-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="ced71-108">Resolution</span></span>

<span data-ttu-id="ced71-109">La funcionalidad predeterminada Abrir en Excel utiliza el origen de datos raíz (tabla) de la página actual para determinar qué plantillas de Office o entidades de datos aparecen como opciones en el menú **Abrir en Excel**.</span><span class="sxs-lookup"><span data-stu-id="ced71-109">The default Open in Excel functionality uses the root data source (table) of the current page to determine which Office templates or data entities appear as options on the **Open in Excel** menu.</span></span> <span data-ttu-id="ced71-110">Este comportamiento no es una experiencia ideal para los diarios financieros, porque estos utilizan las mismas tablas (LedgerJournalTable y LedgerJournalTrans) como orígenes de datos raíz de muchos otros tipos de diarios.</span><span class="sxs-lookup"><span data-stu-id="ced71-110">This behavior isn't an ideal experience for financial journals, because financial journals use the same tables (LedgerJournalTable and LedgerJournalTrans) as the root data source of many other types of journals.</span></span>

<span data-ttu-id="ced71-111">Para los diarios financieros, la funcionalidad Abrir líneas en Excel tiene como objetivo mostrar plantillas diseñadas para el diario en el que está trabajando actualmente, como el diario general o un diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="ced71-111">For financial journals, the Open Lines in Excel functionality is intended to show templates that are designed for the journal that you're currently working in the context of, such as the general journal or a payment journal.</span></span> <span data-ttu-id="ced71-112">Por ejemplo, una plantilla destinada a utilizarse con un diario de pagos de proveedor se diseñará para hacer cumplir su cuenta principal como cuenta de proveedor.</span><span class="sxs-lookup"><span data-stu-id="ced71-112">For example, a template that is intended to be used with a vendor payment journal will be designed to enforce your primary account as a vendor account.</span></span>

<span data-ttu-id="ced71-113">Si desea promocionar una plantilla para que esté disponible en los menús **Abrir líneas en Excel** y **Abrir en Excel**, una experiencia fácil para el desarrollador es implementar la interfaz **LedgerIJournalExcelTemplate** y extender la clase **DocuTemplateRegistrationBase**.</span><span class="sxs-lookup"><span data-stu-id="ced71-113">If you want to promote a template so that it's available on the **Open lines in Excel** and **Open in Excel** menus, an easy developer experience is to implement the **LedgerIJournalExcelTemplate** interface and extend the **DocuTemplateRegistrationBase** class.</span></span> <span data-ttu-id="ced71-114">Muchos ejemplos de este enfoque se implementan en el sistema.</span><span class="sxs-lookup"><span data-stu-id="ced71-114">Many examples of this approach are implemented in the system.</span></span> <span data-ttu-id="ced71-115">Un ejemplo que se puede utilizar como referencia es la interfaz **LedgerDailyJournalExcelTemplate** que se creó para el diario general (o diario).</span><span class="sxs-lookup"><span data-stu-id="ced71-115">One example that can be used for reference is the **LedgerDailyJournalExcelTemplate** interface that was created for the general journal (or daily journal).</span></span>

<span data-ttu-id="ced71-116">Cuando se implementa la interfaz **LedgerIJournalExcelTemplate** para la plantilla, el menú **Abrir líneas en Excel** filtrará las plantillas por el tipo de diario y mostrará solo las plantillas que están disponibles para el mismo.</span><span class="sxs-lookup"><span data-stu-id="ced71-116">When the **LedgerIJournalExcelTemplate** interface is implemented for your template, the **Open Lines in Excel** menu will filter templates by the journal type of your journal and will show only the templates that are available for that journal.</span></span> <span data-ttu-id="ced71-117">La interfaz también proporciona un método de validación que garantiza que no se pueda abrir una plantilla para un diario si no cumple con los requisitos del tipo de cuenta.</span><span class="sxs-lookup"><span data-stu-id="ced71-117">The interface also provides a validation method that ensures that a template can't be opened for a journal if it doesn't meet the account type requirements.</span></span> <span data-ttu-id="ced71-118">Por ejemplo, puede especificar que el tipo de cuenta debe ser del tipo **Proveedor** o **Libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="ced71-118">For example, you can specify that the account type must be of the **Vendor** or **Ledger** type.</span></span>

<span data-ttu-id="ced71-119">Para obtener más información sobre esta funcionalidad, consulte [Agregar plantillas al menú Abrir líneas en Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span><span class="sxs-lookup"><span data-stu-id="ced71-119">For more information about this functionality, see [Add templates to the Open lines in Excel menu](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span></span>
