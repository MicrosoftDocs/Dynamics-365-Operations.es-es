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
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 3efa05f49748f6bbff680f322a77cec24da46c0c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5240588"
---
# <a name="nf-e-custom-certificate-validation"></a>Validación de certificados personalizados NF-e

[!include [banner](../includes/banner.md)]

Cuando activa la función de verificación de certificado personalizado NF-e, la validación personalizada permite una conexión con los servicios web. Esta conexión es necesaria para transmitir NF-e y recibir autorización de SEFAZ.

La propiedad **Propósito de autenticación del servidor** del certificado V5 es emitida por la Autoridad de Certificación Raíz de Brasil. Esta propiedad está desactivada de forma predeterminada y debe habilitarse manualmente. En algunas circunstancias, la actualización automática del certificado puede cambiar esta propiedad para que ya no esté habilitada. Si esto sucede, la conexión TLS se ve afectada y ya no es de confianza. La capacidad de emitir NF-e en entornos de producción para los estados de Minas Gerais (MG) y Paraná (PR) también se ve afectada.

Esta actualización permite una solución alternativa para la validación de certificados, lo que significa que es posible establecer una comunicación segura.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]