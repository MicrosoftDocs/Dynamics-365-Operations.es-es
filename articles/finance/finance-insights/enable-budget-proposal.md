---
title: Habilitar propuestas de presupuesto (versión preliminar)
description: Este tema explica cómo activar la función de propuesta de presupuesto en Finance Insights.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: cc7b06ee40553a254a939babc30e6f5c99f85507c1a3db4e916f480560cf8835
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768948"
---
# <a name="enable-budget-proposals-preview"></a>Habilitar propuestas de presupuesto (versión preliminar)

[!include [banner](../includes/banner.md)]

Este tema explica cómo activar la función de propuesta de presupuesto en Finance Insights.

1. Utilice la información de la página de entorno en Microsoft Dynamics Lifecycle Services (LCS) para conectarse a la instancia principal de Azure SQL para ese entorno. Ejecute el siguiente comando Transact-SQL (T-SQL) para activar paquetes piloto para el entorno de espacio aislado. (Es posible que tenga que activar el acceso para su dirección IP en LCS antes de poder conectarse de forma remota a Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > Omita este paso si usa la versión 10.0.20 o posterior, o si usa una implementación de Service Fabric. El equipo de información financiera ya debería haber activado el paquete piloto por usted. Si no ve la característica en el espacio de trabajo **Administración de características**, o si experimenta problemas al intentar activarlas, póngase en contacto con <fiap@microsoft.com>.

2. Abra el espacio de trabajo **Administración de funciones** y siga estos pasos:

    1. Seleccione **Buscar actualizaciones**.
    2. Busque **Propuesta de presupuesto** y active esa característica.

3. Vaya a **Presupuestación \> Configurar \> Presupuesto básico \> Propuesta de presupuesto (versión preliminar)** y seleccione **Habilitar característica**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
