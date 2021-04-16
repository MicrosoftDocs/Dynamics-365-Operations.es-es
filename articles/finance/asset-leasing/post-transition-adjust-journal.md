---
title: Registrar asientos de diario de ajuste de transición en Arrendamiento de activos
description: Este tema describe la funcionalidad que le permite realizar la transición de una cartera de arrendamientos a los nuevos estándares de contabilidad de arrendamientos, Tema de codificación de estándares de contabilidad 842 (ASC 842) y Norma Internacional de Información Financiera 16 (IFRS 16).
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ea61a0d6e30695a2ef6b93529fcf3d21882c9cd2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819779"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a><span data-ttu-id="e1fb0-103">Registrar asientos de diario de ajuste de transición en Arrendamiento de activos</span><span class="sxs-lookup"><span data-stu-id="e1fb0-103">Post transition adjustment journal entries in Asset leasing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1fb0-104">Este tema describe la funcionalidad que le permite realizar la transición de una cartera de arrendamientos a los nuevos estándares de contabilidad de arrendamientos: Tema 842 de codificación de estándares de contabilidad (ASC 842), que es el estándar en Principios de contabilidad generalmente aceptados en los EE. UU. (US GAAP), y Norma Internacional de Información Financiera 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="e1fb0-104">This topic describes the functionality that lets you transition a lease portfolio to the new lease accounting standards: Accounting Standards Codification Topic 842 (ASC 842), which is the standard in Generally Accepted Accounting Principles in the US (US GAAP), and International Financial Reporting Standard 16 (IFRS 16).</span></span>

<span data-ttu-id="e1fb0-105">Para obtener información sobre cómo configurar un libro para la transición a los nuevos estándares, consulte [Configurar libros de arrendamiento](set-up-lease-books.md).</span><span class="sxs-lookup"><span data-stu-id="e1fb0-105">For information about how to set up a book for the transition to the new standards, see [Set up lease books](set-up-lease-books.md).</span></span>

<span data-ttu-id="e1fb0-106">Cuando crea un asiento de diario de ajuste de transición, se genera un asiento de diario.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-106">When you create a transition adjustment journal entry, a journal entry is generated.</span></span> <span data-ttu-id="e1fb0-107">Esta entrada refleja el impacto en el balance de situación del registro del arrendamiento bajo las nuevas normas en esa fecha.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-107">This entry reflects the balance sheet impact of recording the lease under the new standards on that date.</span></span> <span data-ttu-id="e1fb0-108">La cuenta de activos apropiada se adeuda por el importe en libros en esa fecha y la cuenta de pasivo se abona.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-108">The appropriate asset account is debited for the carrying amount on that date, and the liability account is credited.</span></span> <span data-ttu-id="e1fb0-109">La diferencia se adeuda o abona a las ganancias acumuladas.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-109">The difference is either debited or credited to retained earnings.</span></span>

<span data-ttu-id="e1fb0-110">Para publicar un ajuste de transición de conformidad con las nuevas normas contables, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-110">To post a transition adjustment in compliance with the new accounting standards, follow these steps.</span></span>

1. <span data-ttu-id="e1fb0-111">En la página **Resumen de arrendamiento**, seleccione el arrendamiento y luego seleccione **Libros**.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-111">On the **Lease summary** page, select the lease, and then select **Books**.</span></span>
2. <span data-ttu-id="e1fb0-112">En el libro, seleccione **Programación de pagos**.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-112">In the book, select **Payment schedule**.</span></span>
3. <span data-ttu-id="e1fb0-113">En el cuadro de diálogo **Programación de pagos**, seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-113">In the **Payment schedule** dialog box, select **Confirm**.</span></span> <span data-ttu-id="e1fb0-114">A continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-114">Then close the dialog box.</span></span>
4. <span data-ttu-id="e1fb0-115">Seleccione **Ajuste de transición**.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-115">Select **Transition adjustment**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1fb0-116">Se puede crear un ajuste de transición solo para los libros de arrendamiento asignados a un libro donde el campo **Libro de transición** está disponible.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-116">A transition adjustment can be created only for lease books that are assigned to a book where the **Transition book** field is available.</span></span> <span data-ttu-id="e1fb0-117">Si el valor en el campo **Inicio de arrendamiento** es posterior a la fecha de transición, el valor del campo **Ajuste de transición** no se actualizará.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-117">If the value in the **Lease commencement** field is later than the transition date, the value in the **Transition adjustment** field won't be updated.</span></span>

5. <span data-ttu-id="e1fb0-118">Para ver el movimiento de diario, seleccione **Diarios de arrendamiento de activos**.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-118">To view the journal entry, select **Asset leasing journals**.</span></span>
6. <span data-ttu-id="e1fb0-119">Seleccione el nuevo diario y luego seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="e1fb0-119">Select the new journal, and then select **Post**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]