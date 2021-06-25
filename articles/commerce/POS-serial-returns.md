---
title: Devolver productos controlados por número de serie en POS
description: Este tema describe las capacidades para validar artículos serializados como parte del proceso de devolución en la aplicación del punto de venta (PDV) de Microsoft Dynamics 365 Commerce.
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7a067994828f3df577c0dc4146d26ac81990d4ac
ms.sourcegitcommit: 927574c77f4883d906e5c7bddf0af9b717e492bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129829"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a><span data-ttu-id="60b92-103">Devolver productos controlados por número de serie en PDV</span><span class="sxs-lookup"><span data-stu-id="60b92-103">Return serial number–controlled products in POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="60b92-104">Este tema describe las capacidades para validar artículos serializados como parte del proceso de devolución en la aplicación del punto de venta (PDV) de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="60b92-104">This topic describes the capabilities for validating serialized items as part of the return process in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

> [!NOTE]
> <span data-ttu-id="60b92-105">En el lanzamiento de Commerce versión 10.0.20 y posteriores, está disponible una nueva característica que se llama **Experiencia unificada de procesamiento de devoluciones en PDV**.</span><span class="sxs-lookup"><span data-stu-id="60b92-105">In the Commerce version 10.0.20 release and later, a new feature that is named **Unified return processing experience in POS** is available.</span></span> <span data-ttu-id="60b92-106">Para utilizar la validación del número de serie durante el procesamiento de pedidos de devolución en PDV, debe activar esta función.</span><span class="sxs-lookup"><span data-stu-id="60b92-106">To use serial number validation during return order processing in POS, you must turn on this feature.</span></span> <span data-ttu-id="60b92-107">Para obtener información sobre otras capacidades que ofrece esta función cuando está activada, consulte [Crear devoluciones en PDV)](POS-returns.md).</span><span class="sxs-lookup"><span data-stu-id="60b92-107">For information about others capabilities that this feature provides when it's turned on, see [Create returns in POS)](POS-returns.md).</span></span>
>
> <span data-ttu-id="60b92-108">Una vez activada la función, no se puede desactivar.</span><span class="sxs-lookup"><span data-stu-id="60b92-108">After the feature is turned on, it can't be turned off.</span></span>

## <a name="options-for-validating-serialized-returns"></a><span data-ttu-id="60b92-109">Opciones para validar devoluciones serializadas</span><span class="sxs-lookup"><span data-stu-id="60b92-109">Options for validating serialized returns</span></span>

<span data-ttu-id="60b92-110">Cuando la característica **Experiencia unificada de procesamiento de devoluciones en PDV** está activada, las organizaciones pueden realizar una validación en las devoluciones de artículos controlados por número de serie a través de PDV.</span><span class="sxs-lookup"><span data-stu-id="60b92-110">When the **Unified return processing experience in POS** feature is turned on, organizations can perform a validation on returns of serial number–controlled items through POS.</span></span> <span data-ttu-id="60b92-111">Esta capacidad puede advertir a los usuarios si el número de serie que se devuelve difiere del número de serie original que se vendió.</span><span class="sxs-lookup"><span data-stu-id="60b92-111">This capability can warn users if the serial number that is being returned differs from the original serial number that was sold.</span></span> <span data-ttu-id="60b92-112">En la versión de Commerce 10.0.20 y posteriores, el mensaje que reciben los usuarios es solo un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="60b92-112">In the Commerce version 10.0.20 release and later, the message that users receive is only a warning message.</span></span> <span data-ttu-id="60b92-113">Los usuarios pueden continuar procesando una devolución con un número de serie que difiera del número de serie que se vendió originalmente.</span><span class="sxs-lookup"><span data-stu-id="60b92-113">Users can continue to process a return against a serial number that differs from the serial number that was originally sold.</span></span>

<span data-ttu-id="60b92-114">Para configurar la validación del número de serie para una organización después de activar la función **Experiencia unificada de procesamiento de devoluciones en PDV**, vaya a **Retail y Commerce \> Configuración de la sede central \> Parámetros \> Parámetros de Commerce** en la sede central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="60b92-114">To configure serial number validation for an organization after the **Unified return processing experience in POS** feature is turned on, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters** in Commerce headquarters.</span></span> <span data-ttu-id="60b92-115">En la pestaña **Inventario**, en la ficha desplegable **Operaciones de inventario de la tienda**, establezca la opción **Habilitar la validación de los números de serie en las devoluciones de PDV** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="60b92-115">On the **Inventory** tab, on the **Store inventory operations** FastTab, set the **Enable validation of serial numbers on POS returns** option to **Yes**.</span></span>

## <a name="process-returns-for-serialized-items-in-pos"></a><span data-ttu-id="60b92-116">Procesar devoluciones de artículos serializados en PDV</span><span class="sxs-lookup"><span data-stu-id="60b92-116">Process returns for serialized items in POS</span></span>

<span data-ttu-id="60b92-117">Si la opción **Habilitar la validación de los números de serie en las devoluciones de PDV** se ha establecido en **Sí**, cuando un artículo controlado por número de serie se devuelve a través de PDV, el usuario puede ingresar el número de serie para la línea de devolución en el panel de detalles en la página **Productos que se pueden devolver**.</span><span class="sxs-lookup"><span data-stu-id="60b92-117">If the **Enable validation of serial numbers on POS returns** option has been set to **Yes**, when a serial number–controlled item is returned through POS, the user can enter the serial number for the return line in the details pane on the **Returnable products** page.</span></span> <span data-ttu-id="60b92-118">Si el número de serie que se ingresa no coincide con el número de serie original que se vendió para la transacción de venta, el usuario recibe un mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="60b92-118">If the serial number that is entered doesn't match the original serial number that was sold for the sales transaction, the user receives a warning message.</span></span> <span data-ttu-id="60b92-119">Sin embargo, la aplicación no impide que el usuario continúe procesando la devolución.</span><span class="sxs-lookup"><span data-stu-id="60b92-119">However, the application doesn't prevent the user from continuing to post the return.</span></span>

> [!NOTE]
> <span data-ttu-id="60b92-120">Actualmente, PDV admite la validación de números de serie solo en líneas de devolución donde la cantidad original pedida no es más de uno.</span><span class="sxs-lookup"><span data-stu-id="60b92-120">Currently, POS supports validation of serial numbers only on return lines where the original ordered quantity is no more than one.</span></span> <span data-ttu-id="60b92-121">Si la línea de pedido de venta original se creó en un canal que no es PDV, y si la cantidad solicitada para el artículo serializado en una línea de venta determinada es más de uno, el artículo no se puede devolver correctamente a través de PDV.</span><span class="sxs-lookup"><span data-stu-id="60b92-121">If the original sales order line was created in a non-POS channel, and if the quantity that was ordered for the serialized item on a given sales line is more than one, the item can't be correctly returned through POS.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="60b92-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="60b92-122">Additional resources</span></span>

[<span data-ttu-id="60b92-123">Crear devoluciones en PDV.</span><span class="sxs-lookup"><span data-stu-id="60b92-123">Create returns in POS</span></span>](POS-returns.md)
