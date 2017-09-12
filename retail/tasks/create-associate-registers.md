--- 
title: Crear y asociar registros
description: "Este procedimiento muestra cómo crear un registro de punto de venta (PDV)."
author: rubencdelgado
manager: AnnBe
ms.date: 10/05/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6a95019e50bcc060165dab3e6aa2b3ca8a897bf3
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="create-and-associate-registers"></a><span data-ttu-id="56fa0-103">Crear y asociar registros</span><span class="sxs-lookup"><span data-stu-id="56fa0-103">Create and associate registers</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="56fa0-104">Este procedimiento muestra cómo crear un registro de punto de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="56fa0-104">This procedure demonstrates how to create a point of sale (POS) register.</span></span> <span data-ttu-id="56fa0-105">Este procedimiento usa la empresa de datos de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="56fa0-105">This procedure uses the demo data company USRT.</span></span>

1. <span data-ttu-id="56fa0-106">Vaya a Venta minorista y comercio > Configuración de canal > Configuración de PDV > PDV > Cajas registradoras.</span><span class="sxs-lookup"><span data-stu-id="56fa0-106">Go to Retail and commerce > Channel setup > POS setup > Registers.</span></span>
2. <span data-ttu-id="56fa0-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="56fa0-107">Click New.</span></span>
3. <span data-ttu-id="56fa0-108">En el campo Número de registro, escriba un id. para el nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="56fa0-108">In the Register number field, type an ID for the new register.</span></span>
    * <span data-ttu-id="56fa0-109">El id. de registro incluye normalmente códigos que ayudan a asignar el registro a la tienda a la que pertenece y a la ubicación dentro del almacén.</span><span class="sxs-lookup"><span data-stu-id="56fa0-109">The register ID typically includes codes that help map the register to the store to which it belongs, and the location within the store.</span></span>  
4. <span data-ttu-id="56fa0-110">En el campo Nombre, escriba un nombre descriptivo para el registro.</span><span class="sxs-lookup"><span data-stu-id="56fa0-110">In the Name field, type a descriptive name for the register..</span></span>
5. <span data-ttu-id="56fa0-111">En el campo Número de tienda, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="56fa0-111">In the Store number field, enter or select a value.</span></span>
6. <span data-ttu-id="56fa0-112">En el campo Perfil de hardware, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="56fa0-112">In the Hardware profile field, enter or select a value.</span></span>
    * <span data-ttu-id="56fa0-113">Los perfiles de hardware se utilizan para especificar los periféricos comerciales que se conectarán con el registro, como la caja registradora y la impresora de recibos.</span><span class="sxs-lookup"><span data-stu-id="56fa0-113">Hardware profiles are used to specify the retail peripherals that will be connected to the register, such as cash drawer and receipt printer.</span></span>  
7. <span data-ttu-id="56fa0-114">En el campo Perfil visual, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="56fa0-114">In the Visual profile field, enter or select a value.</span></span>
    * <span data-ttu-id="56fa0-115">Los perfiles visuales se utilizan para especificar las imágenes usadas en el fondo del PDV y la página de inicio de sesión así como los temas para el PDV.</span><span class="sxs-lookup"><span data-stu-id="56fa0-115">Visual profiles are used to specify the images used in the POS background and login page as well as themes for the POS.</span></span>  
8. <span data-ttu-id="56fa0-116">En el campo Número de caja registradora de PDV de EFT, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="56fa0-116">In the EFT POS register number field, type a value.</span></span>
    * <span data-ttu-id="56fa0-117">El número de registro de PDV de EFT se utiliza para informar al procesador de pagos de qué terminal de pago está enviando solicitudes de autorización.</span><span class="sxs-lookup"><span data-stu-id="56fa0-117">The EFT POS register number is used to inform the payment processor which payment terminal is sending authorization requests.</span></span> <span data-ttu-id="56fa0-118">Este valor a menudo se denomina "Id. de terminal" o "TID".</span><span class="sxs-lookup"><span data-stu-id="56fa0-118">This value is often called the "Terminal ID" or “TID”.</span></span> <span data-ttu-id="56fa0-119">El TID se puede encontrar generalmente en una etiqueta adhesiva del dispositivo de pago.</span><span class="sxs-lookup"><span data-stu-id="56fa0-119">The TID can generally be found on a sticker on the payment device.</span></span>  
9. <span data-ttu-id="56fa0-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="56fa0-120">Click Save.</span></span>


