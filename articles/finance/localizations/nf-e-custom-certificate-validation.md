---
title: Validación de certificados personalizados NF-e
description: Este tema proporciona información sobre cómo habilitar y usar el certificado personalizado NF-e.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8144e16b127bdbe954ef44f52c5ac71689a2036e6085e9a4ccc8bb17f91ae9b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755600"
---
# <a name="nf-e-custom-certificate-validation"></a>Validación de certificados personalizados NF-e

[!include [banner](../includes/banner.md)]

La propiedad **Propósito de la autenticación del servidor** de los certificados emitidos por la autoridad de certificados raíz de Brasil está desactivada de forma predeterminada y debe activarse manualmente. En algunas circunstancias, la actualización automática del certificado puede cambiar esta propiedad para que ya no esté habilitada. Si esto sucede, la conexión TLS se ve afectada y ya no es de confianza. La capacidad de emitir el modelo del documento fiscal electrónico de Brasil 55 (NF-e) en entornos de producción para los estados de Minas Gerais (MG) y Paraná (PR) también se ve afectada.

Para habilitar la solución para la **Validación de certificados personalizados NF-e**, vaya a **Administración de características**. Esta característica permite una solución alternativa para las validaciones de los certificados V5 y V10 y permite una conexión de confianza con los servicios web, que es necesaria para la transmisión segura del NF-e y la recepción de la autorización de SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
