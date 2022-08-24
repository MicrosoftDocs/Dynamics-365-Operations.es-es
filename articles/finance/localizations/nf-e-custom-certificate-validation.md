---
title: Validación de certificados personalizados NF-e
description: Este artículo proporciona información sobre cómo habilitar y usar el certificado personalizado NF-e.
author: gionoder
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: f78fdbd133aecaf9dbf8abe0006abd6deb1b1b15
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288556"
---
# <a name="nf-e-custom-certificate-validation"></a>Validación de certificados personalizados NF-e

[!include [banner](../includes/banner.md)]

La propiedad **Propósito de la autenticación del servidor** de los certificados emitidos por la autoridad de certificados raíz de Brasil está desactivada de forma predeterminada y debe activarse manualmente. En algunas circunstancias, la actualización automática del certificado puede cambiar esta propiedad para que ya no esté habilitada. Si esto sucede, la conexión TLS se ve afectada y ya no es de confianza. La capacidad de emitir el modelo del documento fiscal electrónico de Brasil 55 (NF-e) en entornos de producción para los estados de Minas Gerais (MG) y Paraná (PR) también se ve afectada.

Para habilitar la solución para la **Validación de certificados personalizados NF-e**, vaya a **Administración de características**. Esta característica permite una solución alternativa para las validaciones de los certificados V5 y V10 y permite una conexión de confianza con los servicios web, que es necesaria para la transmisión segura del NF-e y la recepción de la autorización de SEFAZ.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
