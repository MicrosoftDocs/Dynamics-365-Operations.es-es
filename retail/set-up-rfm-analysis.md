---
title: "Configurar análisis de RFM"
description: "Este tema explica cómo configurar un análisis de novedad, frecuencia y monetario (RFM) de los clientes."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail Version
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1d5deb781d938dd31326826049372f705bdf6938
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-rfm-analysis"></a>Configurar análisis de RFM

[!include[banner](includes/banner.md)]


Este tema explica cómo configurar un análisis de novedad, frecuencia y monetario (RFM) de los clientes.

El análisis de RFM es una herramienta de marketing que su organización puede usar para evaluar los datos que se generan mediante las compras del cliente. Después de configurar un análisis de RFM, a los clientes se les asigna una puntuación calculada de RFM mientras realizan compras. La puntuación de RFM puede ser una calificación de tres dígitos o un número global, en función de cómo haya configurado el análisis de RFM su organización. Si su organización usa una calificación de tres dígitos para la puntuación, el primer dígito es el grado de proximidad de la compra del cliente (cuánto hace que el cliente realizó una compra en su organización). El segundo dígito es el grado de la frecuencia del cliente (con qué frecuencia el cliente realiza compras en su organización). El tercer dígito es el grado del importe monetario del cliente (cuánto gasta el cliente cuando realiza compras en su organización). Por ejemplo, su organización ha configurado las clasificaciones en una escala de 1 a 5, donde 5 es el grado más alto. En este caso, una clasificación de cliente de 535 le indicará la siguiente información acerca del cliente:

-   **Grado de proximidad de 5:** el cliente ha comprado recientemente.
-   **Grado de frecuencia de 3:** el cliente compra productos de la organización con una frecuencia moderada.
-   **Grado monetario de 5:** cuando el cliente realiza una compra, gasta un importe significativo de dinero.

Si su organización usa una calificación global de la puntuación, las puntuaciones se suman. Para el mismo ejemplo, el cliente tiene un puntuación de 13 (5 + 3 + 5).




