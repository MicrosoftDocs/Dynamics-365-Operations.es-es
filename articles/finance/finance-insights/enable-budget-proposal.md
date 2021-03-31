---
title: Habilitar propuestas de presupuesto (versión preliminar)
description: Este tema explica cómo activar la función de propuesta de presupuesto en Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 3a2060d082ed55e3b6fac506898916942ccc9db7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208494"
---
# <a name="enable-budget-proposals-preview"></a>Habilitar propuestas de presupuesto (versión preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema explica cómo activar la función de propuesta de presupuesto en Finance Insights.

1. Utilice la información de la página de entorno en Microsoft Dynamics Lifecycle Services (LCS) para conectarse a la instancia principal de Azure SQL para ese entorno. Ejecute el siguiente comando Transact-SQL (T-SQL) para activar paquetes piloto para el entorno de espacio aislado. (Es posible que tenga que activar el acceso para su dirección IP en LCS antes de poder conectarse de forma remota a Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > Si su implementación de Microsoft Dynamics 365 Finance es una implementación de Service Fabric, puede omitir este paso. El equipo de Finance Insights ya debería haber activado el paquete piloto por usted. Si no ve la característica en el espacio de trabajo **Administración de características**, o si tiene problemas cuando intenta activarla, envíe un correo electrónico al [equipo de Vista previa de la aplicación Finance Insights](mailto:fiap@microsoft.com).

2. Abra el espacio de trabajo **Administración de funciones** y siga estos pasos:

    1. Seleccione **Buscar actualizaciones**.
    2. Busque **Propuesta de presupuesto** y active esa característica.

3. Vaya a **Presupuestación \> Configurar \> Presupuesto básico \> Propuesta de presupuesto (versión preliminar)** y seleccione **Habilitar característica**.

#### <a name="privacy-notice"></a>Aviso de privacidad
Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]