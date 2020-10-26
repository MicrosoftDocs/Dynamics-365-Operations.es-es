---
title: Validación de certificados personalizados NF-e
description: Este tema proporciona información sobre cómo habilitar y usar el certificado personalizado NF-e.
author: gionoder
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 26ffed1f49d9087ca767aab1b8cac41b099f73cb
ms.sourcegitcommit: 3c88c4adafb78b807842b0b41c69b19cf2b7aa23
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973101"
---
# <a name="nf-e-custom-certificate-validation"></a><span data-ttu-id="34058-103">Validación de certificados personalizados NF-e</span><span class="sxs-lookup"><span data-stu-id="34058-103">NF-e custom certificate validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34058-104">Cuando activa la función de verificación de certificado personalizado NF-e, la validación personalizada permite una conexión con los servicios web.</span><span class="sxs-lookup"><span data-stu-id="34058-104">When you turn the NF-e custom certificate verification feature, custom validation allows a connection with the web services.</span></span> <span data-ttu-id="34058-105">Esta conexión es necesaria para transmitir NF-e y recibir autorización de SEFAZ.</span><span class="sxs-lookup"><span data-stu-id="34058-105">This connection is required to transmit NF-e and receive authorization from SEFAZ.</span></span>

<span data-ttu-id="34058-106">La propiedad **Propósito de autenticación del servidor** del certificado V5 es emitida por la Autoridad de Certificación Raíz de Brasil.</span><span class="sxs-lookup"><span data-stu-id="34058-106">The **Server authentication purpose** property from the certificate V5 is issued by the Brazilian Root Certificate Authority.</span></span> <span data-ttu-id="34058-107">Esta propiedad está desactivada de forma predeterminada y debe habilitarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="34058-107">This property is turned off by default and must be manually enabled.</span></span> <span data-ttu-id="34058-108">En algunas circunstancias, la actualización automática del certificado puede cambiar esta propiedad para que ya no esté habilitada.</span><span class="sxs-lookup"><span data-stu-id="34058-108">In some circumstances, the automatic certificate update can switch this property to no longer be enabled.</span></span> <span data-ttu-id="34058-109">Si esto sucede, la conexión TLS se ve afectada y ya no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="34058-109">If this happens, the TLS connection is affected and is no longer trusted.</span></span> <span data-ttu-id="34058-110">La capacidad de emitir NF-e en entornos de producción para los estados de Minas Gerais (MG) y Paraná (PR) también se ve afectada.</span><span class="sxs-lookup"><span data-stu-id="34058-110">The ability to issue NF-e on production environments for states of Minas Gerais (MG) and Paraná (PR) states is also impacted.</span></span>

<span data-ttu-id="34058-111">Esta actualización permite una solución alternativa para la validación de certificados, lo que significa que es posible establecer una comunicación segura.</span><span class="sxs-lookup"><span data-stu-id="34058-111">This update allows for an alternative solution for certificate validation, which means that it’s possible to establish a secure communication.</span></span>


