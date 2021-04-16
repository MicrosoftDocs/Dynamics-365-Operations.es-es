---
title: Digitalizar códigos de barras mediante una cámara en la aplicación Gestión de almacenes
description: Este tema explica cómo configurar la aplicación móvil Warehouse Management para digitalizar códigos de barras mediante una cámara en un dispositivo móvil.
author: MarkusFogelberg
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2f61f9c45b95b730a7f1743963658ec00abfbb56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831227"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="4dd35-103">Digitalizar códigos de barras mediante una cámara en la aplicación Gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="4dd35-103">Scan bar codes using a camera in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4dd35-104">Este tema explica cómo configurar la aplicación móvil Warehouse Management para digitalizar códigos de barras mediante una cámara en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="4dd35-104">This topic explains how to set up the Warehouse Management mobile app to scan bar codes using a camera on a mobile device.</span></span>

## <a name="setup"></a><span data-ttu-id="4dd35-105">Configurar</span><span class="sxs-lookup"><span data-stu-id="4dd35-105">Setup</span></span>

<span data-ttu-id="4dd35-106">En la configuración de visualización de la aplicación móvil Warehouse Management, puede seleccionar si la cámara debe utilizarse para la digitalización de códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="4dd35-106">In the display settings of the Warehouse Management mobile app, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="4dd35-107">Si habilita la opción **Usar la cámara como escáner**, puede usar la cámara en cada campo de entrada que tenga el modo de entrada preferido establecido en **Exploración**.</span><span class="sxs-lookup"><span data-stu-id="4dd35-107">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span>

<span data-ttu-id="4dd35-108">Para controlar si un campo de entrada debe ser escaneable, en la página **Nombres de campo de aplicación Warehouse**, establezca **Modo de entrada preferido** en **Exploración**.</span><span class="sxs-lookup"><span data-stu-id="4dd35-108">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="4dd35-109">Cuando se selecciona esta opción, se puede usar una cámara para escanear en la aplicación móvil Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="4dd35-109">When this option is selected, a camera can be used for scanning in the Warehouse Management mobile app.</span></span> <span data-ttu-id="4dd35-110">Para más información, consulte [Configurar campos para la aplicación](configure-app-field-names-priorities-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="4dd35-110">For more information, see [Configure fields for the Warehouse Management mobile app](configure-app-field-names-priorities-warehouse.md).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="4dd35-111">Formatos de códigos de barras admitidos</span><span class="sxs-lookup"><span data-stu-id="4dd35-111">Supported bar code formats</span></span>

<span data-ttu-id="4dd35-112">Se admiten los formatos de códigos de barras más comúnes, incluido el Código 128, el Código 39, el Código 93, EAN-8, EAN-13, UPC-E, UPC-A y códigos QR.</span><span class="sxs-lookup"><span data-stu-id="4dd35-112">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span>

## <a name="navigation"></a><span data-ttu-id="4dd35-113">Navegación</span><span class="sxs-lookup"><span data-stu-id="4dd35-113">Navigation</span></span>

<span data-ttu-id="4dd35-114">La página de la cámara se iniciará en cada página donde el campo de entrada tenga el **Modo de entrada preferido** establecido en *Exploración*, cuando se encuentre en la página Cámara, use las siguientes opciones para navegar:</span><span class="sxs-lookup"><span data-stu-id="4dd35-114">The camera page will be initiated on each page where the input field has its **Preferred input mode** set to *Scanning*, when you are on the camera page use the following options to navigate:</span></span>

- <span data-ttu-id="4dd35-115">Seleccione el botón Atrás para volver a la página de **Tarea y detalles**.</span><span class="sxs-lookup"><span data-stu-id="4dd35-115">Select the back button to go back to the **Task and details** page.</span></span>
- <span data-ttu-id="4dd35-116">Seleccione el lápiz en la página de **Tarea y detalles** para pasar a la página donde puede escribir la entrada manualmente.</span><span class="sxs-lookup"><span data-stu-id="4dd35-116">Select the pencil on the **Task and details** page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="4dd35-117">Seleccione la cámara en la página de **Tarea y detalles** para volver a la página Cámara.</span><span class="sxs-lookup"><span data-stu-id="4dd35-117">Select the camera on the **Task and details** page to go back to the camera page.</span></span>

<span data-ttu-id="4dd35-118">En la página de la cámara, al seleccionar el botón Cámara, aparecerá atenuada mientras trata de identificar un código de barras.</span><span class="sxs-lookup"><span data-stu-id="4dd35-118">On the camera page, when you select the camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="4dd35-119">Si no se identifica un código de barras en menos de 5 segundos, el proceso se pondrá en tiempo de espera y el botón cámara volverá a estar disponible.</span><span class="sxs-lookup"><span data-stu-id="4dd35-119">If a bar code is not identified within 5 seconds, the process will time out and the camera button will become available again.</span></span> <span data-ttu-id="4dd35-120">A continuación, podrá intentar escanear de nuevo un código de barras.</span><span class="sxs-lookup"><span data-stu-id="4dd35-120">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="4dd35-121">Cuando apunte la cámara a un código de barras, mantenga el código de barras alineado entre los corchetes para lograr un mejor resultado.</span><span class="sxs-lookup"><span data-stu-id="4dd35-121">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="4dd35-122">Cuando un código de barras se digitaliza correctamente, el resultado se procesará y pasará al siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="4dd35-122">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="4dd35-123">Si el siguiente paso contiene otro campo de entrada con el modo de entrada preferido establecido en Exploración, la página de la cámara se volverá a iniciar.</span><span class="sxs-lookup"><span data-stu-id="4dd35-123">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="4dd35-124">Si el paso siguiente no es un campo de exploración, la página de la cámara no se iniciará.</span><span class="sxs-lookup"><span data-stu-id="4dd35-124">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]