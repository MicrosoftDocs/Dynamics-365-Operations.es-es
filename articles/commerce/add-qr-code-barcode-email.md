---
title: Agregar un código QR o un código de barras a los correos electrónicos transaccionales y de recibos
description: Este tema explica cómo insertar códigos QR y códigos de barras que representan id. de pedidos en correos electrónicos transaccionales y de recibos en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: f8d9408090846799c1bb421c4b6e5e248d37fa07
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797512"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a><span data-ttu-id="33237-103">Agregar un código QR o un código de barras a los correos electrónicos transaccionales y de recibos</span><span class="sxs-lookup"><span data-stu-id="33237-103">Add a QR code or bar code to transactional and receipt emails</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="33237-104">Este tema explica cómo insertar códigos QR y códigos de barras que representan id. de pedidos en correos electrónicos transaccionales y de recibos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="33237-104">This topic explains how to insert QR codes and bar codes that represent order IDs into transactional and receipt emails in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="33237-105">Puede incluir fácilmente códigos QR y códigos de barras en correos electrónicos transaccionales para ayudar a acelerar el proceso de búsqueda de pedidos en un entorno minorista.</span><span class="sxs-lookup"><span data-stu-id="33237-105">You can easily include QR codes and bar codes in transactional emails to help speed up the order lookup process in a retail environment.</span></span> <span data-ttu-id="33237-106">Para insertar códigos QR y códigos de barras en correos electrónicos, utilice una etiqueta HTML **\<img\>** que solicita un código QR o una imagen de código de barras de un servicio de generación y representación.</span><span class="sxs-lookup"><span data-stu-id="33237-106">To insert QR codes and bar codes into emails, you use an HTML **\<img\>** tag that requests a QR code or bar code image from a generation and rendering service.</span></span> <span data-ttu-id="33237-107">Microsoft no proporciona este servicio.</span><span class="sxs-lookup"><span data-stu-id="33237-107">Microsoft doesn't provide this service.</span></span> <span data-ttu-id="33237-108">Sin embargo, existen muchos servicios gratuitos o económicos que pueden servir códigos QR o códigos de barras que se generan dinámicamente en función de un valor que se pasa en una cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="33237-108">However, there are many free or inexpensive services that can serve QR codes or bar codes that are dynamically generated based on a value that is passed in a query string.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a><span data-ttu-id="33237-109">Agregar un código QR o un código de barras a un correo electrónico transaccional</span><span class="sxs-lookup"><span data-stu-id="33237-109">Add a QR code or bar code to a transactional email</span></span>

<span data-ttu-id="33237-110">Para insertar un código QR o un código de barras en un correo electrónico transaccional que se envía como parte de una compra de comercio electrónico, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33237-110">To insert a QR code or bar code into a transactional email that is sent as part of an e-commerce purchase, follow these steps.</span></span>

1. <span data-ttu-id="33237-111">Abra el HTML de origen para la plantilla de correo electrónico transaccional y agregue una etiqueta HTML **\<img\>** que apunte a su código QR o servicio de código de barras.</span><span class="sxs-lookup"><span data-stu-id="33237-111">Open the source HTML for the transactional email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="33237-112">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="33237-112">Here is an example.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    <span data-ttu-id="33237-113">A continuación se ofrece una explicación del ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="33237-113">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="33237-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** representa el dominio de su servicio de códigos QR o códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="33237-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="33237-115">**data** representa el parámetro que utiliza el código QR o el servicio de código de barras para recibir el contenido que debe mostrarse como un código QR o código de barras.</span><span class="sxs-lookup"><span data-stu-id="33237-115">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="33237-116">El valor **%salesid%** debe asignarse a este parámetro.</span><span class="sxs-lookup"><span data-stu-id="33237-116">The value **%salesid%** must be assigned to this parameter.</span></span> <span data-ttu-id="33237-117">En este ejemplo, observe que el valor también se usa como texto alternativo para la imagen.</span><span class="sxs-lookup"><span data-stu-id="33237-117">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="33237-118">**param1** y **param2** representan parámetros opcionales adicionales.</span><span class="sxs-lookup"><span data-stu-id="33237-118">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="33237-119">Vaya a **Comercio minorista y Commerce \> Configuración de la sede \> Parámetros \> Plantillas de correo electrónico de organización** y cargue el HTML actualizado en la plantilla de correo electrónico transaccional correspondiente.</span><span class="sxs-lookup"><span data-stu-id="33237-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the appropriate transactional email template.</span></span>

> [!NOTE]
> <span data-ttu-id="33237-120">Los parámetros pueden diferir entre los proveedores de servicios de códigos QR y códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="33237-120">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="33237-121">Por lo tanto, asegúrese de contactar con su proveedor de servicios para confirmar los parámetros a los que debe asignar valores.</span><span class="sxs-lookup"><span data-stu-id="33237-121">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a><span data-ttu-id="33237-122">Agregar un código QR o un código de barras a un correo electrónico de recibo</span><span class="sxs-lookup"><span data-stu-id="33237-122">Add a QR code or bar code to a receipt email</span></span> 

<span data-ttu-id="33237-123">Para insertar un código QR o un código de barras en un correo electrónico de recibo que se puede enviar después de realizar una compra en el punto de venta (PDV), siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33237-123">To insert a QR code or bar code into a receipt email that can be sent after a purchase is made at the point of sale (POS), follow these steps.</span></span>

1. <span data-ttu-id="33237-124">Abra el HTML de origen para la plantilla de correo electrónico de recibo y agregue una etiqueta HTML **\<img\>** que apunte a su código QR o servicio de código de barras.</span><span class="sxs-lookup"><span data-stu-id="33237-124">Open the source HTML for the receipt email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="33237-125">A continuación viene un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="33237-125">Here is an example below.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    <span data-ttu-id="33237-126">A continuación se ofrece una explicación del ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="33237-126">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="33237-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** representa el dominio de su servicio de códigos QR o códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="33237-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="33237-128">**data** representa el parámetro que utiliza el código QR o el servicio de código de barras para recibir el contenido que debe mostrarse como un código QR o código de barras.</span><span class="sxs-lookup"><span data-stu-id="33237-128">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="33237-129">El valor **%receiptid%** debe asignarse a este parámetro.</span><span class="sxs-lookup"><span data-stu-id="33237-129">The value **%receiptid%** must be assigned to this parameter.</span></span> <span data-ttu-id="33237-130">En este ejemplo, observe que el valor también se usa como texto alternativo para la imagen.</span><span class="sxs-lookup"><span data-stu-id="33237-130">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="33237-131">**param1** y **param2** representan parámetros opcionales adicionales.</span><span class="sxs-lookup"><span data-stu-id="33237-131">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="33237-132">Vaya a **Comercio minorista y Commerce \> Configuración de la sede \> Parámetros \> Plantillas de correo electrónico de organización** y cargue el HTML actualizado en la plantilla de correo electrónico que tenga el id. de correo **emailrecpt**.</span><span class="sxs-lookup"><span data-stu-id="33237-132">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the email template that has the email ID **emailrecpt**.</span></span>

> [!NOTE]
> <span data-ttu-id="33237-133">Los parámetros pueden diferir entre los proveedores de servicios de códigos QR y códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="33237-133">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="33237-134">Por lo tanto, asegúrese de contactar con su proveedor de servicios para confirmar los parámetros a los que debe asignar valores.</span><span class="sxs-lookup"><span data-stu-id="33237-134">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33237-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="33237-135">Additional resources</span></span>

[<span data-ttu-id="33237-136">Enviar recibos por correo electrónico desde Modern PDV (MPOS)</span><span class="sxs-lookup"><span data-stu-id="33237-136">Send email receipts from Modern POS (MPOS)</span></span>](email-receipts.md)

[<span data-ttu-id="33237-137">Crear plantillas de correo electrónico para eventos transaccionales</span><span class="sxs-lookup"><span data-stu-id="33237-137">Create email templates for transactional events</span></span>](email-templates-transactions.md)
