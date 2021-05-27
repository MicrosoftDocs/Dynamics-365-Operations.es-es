---
title: Solucionar problemas del Conector de pago de Dynamics 365 para problemas de Adyen
description: Este tema proporciona una guía para la resolución de problemas que puede ayudarle a obtener soporte cuando tenga problemas con el Conector de pago de Microsoft Dynamics 365 para Adyen.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 707efeba9553b996e4e33a4754e42a9d22643e33
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019598"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a><span data-ttu-id="fe458-103">Solucionar problemas del Conector de pago de Dynamics 365 para problemas de Adyen</span><span class="sxs-lookup"><span data-stu-id="fe458-103">Troubleshoot Dynamics 365 Payment Connector for Adyen issues</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fe458-104">Este tema proporciona una guía para la resolución de problemas que puede ayudarle a obtener soporte cuando tenga problemas con el Conector de pago de Microsoft Dynamics 365 para Adyen.</span><span class="sxs-lookup"><span data-stu-id="fe458-104">This topic provides troubleshooting guidance that can help you get support when you have issues with the Microsoft Dynamics 365 Payment Connector for Adyen.</span></span>

## <a name="description"></a><span data-ttu-id="fe458-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe458-105">Description</span></span>

<span data-ttu-id="fe458-106">Tiene problemas con el Conector de pago de Dynamics 365 para Adyen en las siguientes áreas y necesita soporte del equipo de Adyen:</span><span class="sxs-lookup"><span data-stu-id="fe458-106">You have issues with the Dynamics 365 Payment Connector for Adyen in the following areas, and you require support from the Adyen team:</span></span>

- <span data-ttu-id="fe458-107">Configuración de Punto de venta (POS), Punto de venta moderno (MPOS), centro de llamadas o Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="fe458-107">Configuration of Point of sale (POS), Modern point of sale (MPOS), call center, or Dynamics 365 Commerce</span></span>
- <span data-ttu-id="fe458-108">El número de referencia del proveedor de servicios de pago (PSP) de Adyen (por ejemplo, si tiene preguntas sobre rechazos, incluidos rechazos de introducción manual de claves \[ MKE\])</span><span class="sxs-lookup"><span data-stu-id="fe458-108">The Adyen payment service provider (PSP) reference number (for example, if you have questions about refusals, including manual key entry \[MKE\] refusals)</span></span>
- <span data-ttu-id="fe458-109">Todo lo que no funcione en entornos comerciales de prueba o en vivo</span><span class="sxs-lookup"><span data-stu-id="fe458-109">Anything that isn't working in test or live merchant environments</span></span>

## <a name="resolution"></a><span data-ttu-id="fe458-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="fe458-110">Resolution</span></span>

<span data-ttu-id="fe458-111">Utilice la siguiente plantilla de correo electrónico para iniciar el proceso de soporte con el equipo de Adyen.</span><span class="sxs-lookup"><span data-stu-id="fe458-111">Use the following email template to start the support process with the Adyen team.</span></span> <span data-ttu-id="fe458-112">Para acelerar la resolución de problemas, asegúrese de que el correo electrónico contenga todos los detalles requeridos.</span><span class="sxs-lookup"><span data-stu-id="fe458-112">To expedite troubleshooting, make sure that the email contains all the required details.</span></span>

| <span data-ttu-id="fe458-113">Campo</span><span class="sxs-lookup"><span data-stu-id="fe458-113">Field</span></span>        | <span data-ttu-id="fe458-114">Valor</span><span class="sxs-lookup"><span data-stu-id="fe458-114">Value</span></span> |
|--------------|-------|
| <span data-ttu-id="fe458-115">Para</span><span class="sxs-lookup"><span data-stu-id="fe458-115">To</span></span>           | `support@adyen.com` |
| <span data-ttu-id="fe458-116">CC</span><span class="sxs-lookup"><span data-stu-id="fe458-116">Cc</span></span>           | |
| <span data-ttu-id="fe458-117">Línea de asunto</span><span class="sxs-lookup"><span data-stu-id="fe458-117">Subject line</span></span> | <span data-ttu-id="fe458-118">Solicitud de soporte técnico de Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="fe458-118">Microsoft Dynamics Support Request</span></span> |
| <span data-ttu-id="fe458-119">Cuerpo</span><span class="sxs-lookup"><span data-stu-id="fe458-119">Body</span></span>         | <p><span data-ttu-id="fe458-120">Hola, soporte técnico:</span><span class="sxs-lookup"><span data-stu-id="fe458-120">Hi Support,</span></span></p><p><span data-ttu-id="fe458-121">Proporcionen soporte técnico para el siguiente problema:</span><span class="sxs-lookup"><span data-stu-id="fe458-121">Please provide support for the following issue:</span></span></p><ul><li><span data-ttu-id="fe458-122">Cuenta de comerciante</span><span class="sxs-lookup"><span data-stu-id="fe458-122">Merchant account</span></span></li><li><span data-ttu-id="fe458-123">Entorno (prueba/producción)</span><span class="sxs-lookup"><span data-stu-id="fe458-123">Environment (Test/Prod)</span></span></li><li><span data-ttu-id="fe458-124">Canal (PDV/centro de llamadas/comercio electrónico de Commerce)</span><span class="sxs-lookup"><span data-stu-id="fe458-124">Channel (POS/call center/Commerce e-commerce)</span></span></li><li><span data-ttu-id="fe458-125">Número de referencia de PSP, si el problema involucró una transacción específica (puede encontrar el número de referencia de PSP en el recibo, en el Área de clientes de Adyen o en el menú de transacciones en el terminal PDV).</span><span class="sxs-lookup"><span data-stu-id="fe458-125">PSP reference number, if the issue involved a specific transaction (You can find the PSP reference number on the receipt, in the Adyen Customer Area, or on the transactions menu on the POS terminal.)</span></span></li><li><span data-ttu-id="fe458-126">Captura de pantalla o foto del mensaje de error, si corresponde</span><span class="sxs-lookup"><span data-stu-id="fe458-126">Screenshot or photo of the error message, if applicable</span></span></li><li><span data-ttu-id="fe458-127">Registros del Visor de eventos (en formato .txt)</span><span class="sxs-lookup"><span data-stu-id="fe458-127">Event Viewer logs (in .txt format)</span></span></li><li><span data-ttu-id="fe458-128">Descripción del problema y pasos de solución de problemas que ha intentado</span><span class="sxs-lookup"><span data-stu-id="fe458-128">Description of the issue and troubleshooting steps that you've tried</span></span></li></ul> |

## <a name="additional-resources"></a><span data-ttu-id="fe458-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fe458-129">Additional resources</span></span>

[<span data-ttu-id="fe458-130">Aceptar pagos con el conector Adyen para Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="fe458-130">Accept payments with the Adyen connector for Dynamics 365 Commerce</span></span>](https://www.adyen.com/partners/dynamics-365-commerce)

[<span data-ttu-id="fe458-131">Conector de pago de Dynamics 365 para Adyen</span><span class="sxs-lookup"><span data-stu-id="fe458-131">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="fe458-132">Configurar el conector de pago de Adyen para Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="fe458-132">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
