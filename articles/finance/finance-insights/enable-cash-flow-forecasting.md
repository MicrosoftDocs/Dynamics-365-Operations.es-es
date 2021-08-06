---
title: Habilitar la previsión de flujo de efectivo (versión preliminar)
description: Este tema explica cómo activar la característica de previsiones de flujo de efectivo en Finance Insights.
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
ms.openlocfilehash: 29118557a1de4d3521f8125395b26471f7f48f3e
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638630"
---
# <a name="enable-cash-flow-forecasting-preview"></a>Habilitar la previsión de flujo de efectivo (versión preliminar)

[!include [banner](../includes/banner.md)]

Este tema explica cómo activar la característica de previsiones de flujo de efectivo en Finance Insights.

> [!NOTE]
> Para utilizar predicciones de pagos en el flujo de efectivo, debe configurar la característica de predicciones de pagos de clientes como se describe en [Habilitar las predicciones de pagos de clientes](enable-cust-paymnt-prediction.md).

1. Utilice la información de la página de entorno en Microsoft Dynamics Lifecycle Services (LCS) para conectarse a la instancia principal de Azure SQL para ese entorno. Ejecute el siguiente comando Transact-SQL (T-SQL) para activar paquetes piloto para el entorno de espacio aislado. (Es posible que tenga que activar el acceso para su dirección IP en LCS antes de poder conectarse de forma remota a Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > Omita este paso si usa la versión 10.0.20 o posterior, o si usa una implementación de Service Fabric. El equipo de información financiera ya debería haber activado el paquete piloto por usted. Si no ve la característica en el espacio de trabajo **Administración de características**, o si experimenta problemas al intentar activarlas, póngase en contacto con <fiap@microsoft.com>.
  
2. Abra el espacio de trabajo **Administración de funciones** y siga estos pasos:

    1. Seleccione **Buscar actualizaciones**.
    2. Active las siguientes características:

        - Nuevo control de cuadrícula
        - Agrupación en cuadrículas (versión preliminar) 
        - Previsiones de pago de clientes (versión preliminar)
        - Previsiones de flujo de efectivo (versión preliminar)

3. Vaya a **Gestión de efectivo y banco \> Configuración de pronóstico de flujo de efectivo** y agregue las cuentas de liquidez que deben incluirse en las previsiones.

    > [!NOTE]
    > Si no se configuran cuentas de liquidez, no se puede generar el flujo de efectivo.

4. Vaya a **Gestión de efectivo y banco \> Configurar \> Finance Insights (versión preliminar) \> Previsiones de flujo de efectivo (versión preliminar)** y siga estos pasos:

    1. En la pestaña **Pronóstico de flujo de efectivo**, seleccione **Habilitar característica**.
    2. Seleccione **Crear modelo de predicción**.

Para obtener más información sobre cómo configurar la capacidad de previsión de flujo de efectivo, consulte [Previsiones de flujo de efectivo](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
