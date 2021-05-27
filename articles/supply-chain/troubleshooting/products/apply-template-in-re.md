---
title: No puede aplicar una plantilla a un producto lanzado
description: No puede aplicar una plantilla a un producto lanzado.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026874"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a><span data-ttu-id="dd5db-103">No puede aplicar una plantilla para crear un producto lanzado</span><span class="sxs-lookup"><span data-stu-id="dd5db-103">You can't apply a template to create a released product</span></span>

<span data-ttu-id="dd5db-104">Número de KB: 4612097</span><span class="sxs-lookup"><span data-stu-id="dd5db-104">KB number: 4612097</span></span>

## <a name="symptoms"></a><span data-ttu-id="dd5db-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="dd5db-105">Symptoms</span></span>

<span data-ttu-id="dd5db-106">Cuando crea un nuevo producto lanzado utilizando el cuadro de diálogo **Nuevo producto lanzado**, puede seleccionar una plantilla.</span><span class="sxs-lookup"><span data-stu-id="dd5db-106">When you create a new released product by using the **New released product** dialog box, you can select a template.</span></span> <span data-ttu-id="dd5db-107">La plantilla debe proporcionar la configuración predeterminada para muchos campos del nuevo producto lanzado.</span><span class="sxs-lookup"><span data-stu-id="dd5db-107">The template is supposed to provide default settings for many fields of the new released product.</span></span> <span data-ttu-id="dd5db-108">Sin embargo, algunos o todos los campos no se configuran después de seleccionar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="dd5db-108">However, some or all of the fields aren't set after you select the template.</span></span>

## <a name="cause"></a><span data-ttu-id="dd5db-109">Causa</span><span class="sxs-lookup"><span data-stu-id="dd5db-109">Cause</span></span>

<span data-ttu-id="dd5db-110">Muchas páginas en Microsoft Dynamics 365 Supply Chain Management le permiten crear una plantilla que establece la configuración inicial para los registros que se muestran en esas páginas.</span><span class="sxs-lookup"><span data-stu-id="dd5db-110">Many pages in Microsoft Dynamics 365 Supply Chain Management let you create a template that establishes initial settings for the records that are shown on those pages.</span></span> <span data-ttu-id="dd5db-111">Puede crear una de estas plantillas seleccionando **Información de registro** en la pestaña **Opciones** del Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="dd5db-111">You can create one of these templates by selecting **Record info** on the **Options** tab of the Action Pane.</span></span> <span data-ttu-id="dd5db-112">Sin embargo, los productos lanzados son mucho más complejos que la mayoría de los otros tipos de registros.</span><span class="sxs-lookup"><span data-stu-id="dd5db-112">However, released products are much more complex than most other types of records.</span></span> <span data-ttu-id="dd5db-113">Aunque puede seleccionar **Información de registro** en la página **Productos lanzados** para crear una plantilla y, aunque puede seleccionar esa plantilla cuando crea un producto lanzado, la plantilla no proporcionará los valores de campo esperados para el nuevo producto lanzado.</span><span class="sxs-lookup"><span data-stu-id="dd5db-113">Although you can select **Record info** on the **Released products** page to create a template, and although you can select that template when you create a released product, the template won't provide the expected field values for the new released product.</span></span> <span data-ttu-id="dd5db-114">Por lo tanto, no puede usar plantillas de "información de registro" para productos lanzados.</span><span class="sxs-lookup"><span data-stu-id="dd5db-114">Therefore, you can't use "record info" templates for released products.</span></span> <span data-ttu-id="dd5db-115">En su lugar, debe crear plantillas de productos dedicadas.</span><span class="sxs-lookup"><span data-stu-id="dd5db-115">Instead, you must create dedicated product templates.</span></span>

## <a name="resolution"></a><span data-ttu-id="dd5db-116">Resolución</span><span class="sxs-lookup"><span data-stu-id="dd5db-116">Resolution</span></span>

<span data-ttu-id="dd5db-117">Para crear una plantilla de producto, use el menú **Plantilla** en la pestaña **Producto** del Panel de acciones, no el botón **Información de registro** en la pestaña **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="dd5db-117">To create a product template, use the **Template** menu on the **Product** tab of the Action Pane, not the **Record info** button on the **Options** tab.</span></span>

1. <span data-ttu-id="dd5db-118">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="dd5db-118">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="dd5db-119">En el panel de acciones, en la pestaña **Producto**, en el grupo **Nuevo**, seleccione **Plantilla** y luego seleccione **Crear plantilla personal** o **Crear plantilla compartida**, según le convenga.</span><span class="sxs-lookup"><span data-stu-id="dd5db-119">On the Action Pane, on the **Product** tab, in the **New** group, select **Template**, and then select either **Create personal template** or **Create shared template**, as appropriate.</span></span>
