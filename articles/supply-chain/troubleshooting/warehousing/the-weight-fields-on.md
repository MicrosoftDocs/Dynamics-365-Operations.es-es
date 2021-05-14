---
title: Los campos de peso en las líneas de carga no coinciden con los campos de peso en la carga
description: Los campos de peso en las líneas de carga no coinciden con los campos de peso en la carga
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924360"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a><span data-ttu-id="85110-103">Los campos de peso en las líneas de carga no coinciden con los campos de peso en la carga</span><span class="sxs-lookup"><span data-stu-id="85110-103">The weight fields on load lines don't match the weight fields on the load</span></span>

<span data-ttu-id="85110-104">Códigos de error: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span><span class="sxs-lookup"><span data-stu-id="85110-104">Error codes: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span></span>

## <a name="symptoms"></a><span data-ttu-id="85110-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="85110-105">Symptoms</span></span>

<span data-ttu-id="85110-106">El sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="85110-106">The system shows the following error message:</span></span>

> <span data-ttu-id="85110-107">Los campos de peso en las líneas de carga no coinciden con los campos de peso en la carga %1.</span><span class="sxs-lookup"><span data-stu-id="85110-107">The weight fields on load lines do not match the weight fields on load %1.</span></span> <span data-ttu-id="85110-108">Ejecute la comprobación de coherencia del peso de la carga del almacén para volver a calcular los campos de peso.</span><span class="sxs-lookup"><span data-stu-id="85110-108">Run the Warehouse load weight consistency check to recalculate the weight fields.</span></span>

## <a name="cause"></a><span data-ttu-id="85110-109">Causa</span><span class="sxs-lookup"><span data-stu-id="85110-109">Cause</span></span>

<span data-ttu-id="85110-110">Los campos **Peso neto** y **Peso muerto** están configurados en *0* (cero) en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="85110-110">The **Net weight** and **Tara weight** fields are set to *0* (zero) on the load line.</span></span> <span data-ttu-id="85110-111">Sin embargo, los campos de peso no están configurados en *0* para las medidas de peso del producto.</span><span class="sxs-lookup"><span data-stu-id="85110-111">However, the weight fields aren't set to *0* for the weight measurements on the product.</span></span> <span data-ttu-id="85110-112">Cuando los campos de peso no están configurados en la línea de carga, cualquier corrección de la cantidad en la línea de carga podría causar un cálculo de peso incorrecto en la carga.</span><span class="sxs-lookup"><span data-stu-id="85110-112">When weight fields aren't set on the load line, any corrections of the quantity on the load line might cause incorrect weight calculation on the load.</span></span> <span data-ttu-id="85110-113">Este problema puede ocurrir si se han cambiado los pesos del producto desde que se creó la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="85110-113">This issue might occur if the weights on the product have been changed since the load line was created.</span></span>

## <a name="resolution"></a><span data-ttu-id="85110-114">Resolución</span><span class="sxs-lookup"><span data-stu-id="85110-114">Resolution</span></span>

<span data-ttu-id="85110-115">De forma predeterminada, cuando se crea una línea de carga, los campos de peso del producto se introducen en ella.</span><span class="sxs-lookup"><span data-stu-id="85110-115">By default, when a load line is created, the weight fields from the product are entered on it.</span></span> <span data-ttu-id="85110-116">Si el peso es cero, puede volver a calcularlo utilizando la funcionalidad *Comprobación de la coherencia del peso de la carga del almacén*.</span><span class="sxs-lookup"><span data-stu-id="85110-116">If the weight is zero, you can recalculate it by using the *Warehouse load weight consistency check* functionality.</span></span>

1. <span data-ttu-id="85110-117">Vaya a **Administración del sistema \> Tareas periódicas \> Base de datos \> Comprobación de coherencia**.</span><span class="sxs-lookup"><span data-stu-id="85110-117">Go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="85110-118">En el cuadro de diálogo **Comprobación de coherencia**, establezca el campo **Módulo** en *Gestion de almacenes*.</span><span class="sxs-lookup"><span data-stu-id="85110-118">In the **Consistency check** dialog box, set the **Module** field to *Warehouse management*.</span></span>
1. <span data-ttu-id="85110-119">Establezca el campo **Comprobar/arreglar** en *Arreglar error*.</span><span class="sxs-lookup"><span data-stu-id="85110-119">Set the **Check/Fix** field to *Fix error*.</span></span>
1. <span data-ttu-id="85110-120">En la lista de casillas, seleccione la casilla **Comprobación de la coherencia del peso de la carga del almacén** y asegúrese de que solo esté resaltada la fila de esta casilla.</span><span class="sxs-lookup"><span data-stu-id="85110-120">In the checkbox list, select the **Warehouse load weight consistency check** checkbox, and make sure that only the row for this checkbox is highlighted.</span></span>
1. <span data-ttu-id="85110-121">En la parte superior de la lista de casillas, seleccione el botón de puntos suspensivos (**...**) y luego seleccione **Diálogo** en el menú.</span><span class="sxs-lookup"><span data-stu-id="85110-121">At the top of the checkbox list, select the ellipsis button (**...**), and then select **Dialog** on the menu.</span></span>
1. <span data-ttu-id="85110-122">En el cuadro de diálogo **Comprobación de la coherencia del peso de la carga del almacén**, configure los siguientes campos para especificar los criterios para los que se debe ejecutar la comprobación de coherencia:</span><span class="sxs-lookup"><span data-stu-id="85110-122">In the **Warehouse load weight consistency check** dialog box, set the following fields to specify the criteria that the consistency check should run for:</span></span>

    - <span data-ttu-id="85110-123">**Id. de carga:** especifique un id. de carga.</span><span class="sxs-lookup"><span data-stu-id="85110-123">**Load ID:** Specify a load ID.</span></span> <span data-ttu-id="85110-124">Deje este espacio en blanco para comprobar todos los id. de carga.</span><span class="sxs-lookup"><span data-stu-id="85110-124">Leave this blank to check all load IDs.</span></span>
    - <span data-ttu-id="85110-125">**Número de artículo:**: especifique un número de artículo.</span><span class="sxs-lookup"><span data-stu-id="85110-125">**Item number:** Specify an item number.</span></span> <span data-ttu-id="85110-126">Deje este espacio en blanco para comprobar todos los artículos.</span><span class="sxs-lookup"><span data-stu-id="85110-126">Leave this blank to check all items.</span></span>
    - <span data-ttu-id="85110-127">**recalcular siempre el peso de las cargas:** establezca esta opción en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="85110-127">**Always recalculate weight on loads:** Set this option to *Yes*.</span></span>
    - <span data-ttu-id="85110-128">**Permitir sobrescribir el peso en las líneas de carga:** establezca esta opción en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="85110-128">**Allow overwrite of weight on load lines:** Set this option to *Yes*.</span></span>

1. <span data-ttu-id="85110-129">Seleccione **Aceptar** para cerrar el cuadro de diálogo **Comprobación de coherencia del peso de la carga del almacén**.</span><span class="sxs-lookup"><span data-stu-id="85110-129">Select **OK** to close the **Warehouse load weight consistency check** dialog box.</span></span>
1. <span data-ttu-id="85110-130">Seleccione el botón de puntos suspensivos y luego seleccione **Ejecutar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="85110-130">Select the ellipsis button, and then select **Execute** on the menu.</span></span>

<span data-ttu-id="85110-131">El peso se vuelve a calcular según los criterios que especificó.</span><span class="sxs-lookup"><span data-stu-id="85110-131">The weight is recalculated based on the criteria that you specified.</span></span> <span data-ttu-id="85110-132">Seleccione el vínculo **Detalles del mensaje** para ver el resultado de la comprobación de coherencia.</span><span class="sxs-lookup"><span data-stu-id="85110-132">Select the **Message details** link to view the result of the consistency check.</span></span>
