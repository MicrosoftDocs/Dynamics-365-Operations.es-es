---
title: Habilitar la previsión de flujo de efectivo (versión preliminar)
description: Este tema explica cómo activar la característica de previsiones de flujo de efectivo en Finance Insights.
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
ms.openlocfilehash: 1977dac4a3ab66cca2248dc0124d3a06d6963f40
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978773"
---
# <a name="enable-cash-flow-forecasting-preview"></a>Habilitar la previsión de flujo de efectivo (versión preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema explica cómo activar la característica de previsiones de flujo de efectivo en Finance Insights.

> [!NOTE]
> Para utilizar predicciones de pagos en el flujo de efectivo, debe configurar la característica de predicciones de pagos de clientes como se describe en [Habilitar las predicciones de pagos de clientes](enable-cust-paymnt-prediction.md).

1. Utilice la información de la página de entorno en Microsoft Dynamics Lifecycle Services (LCS) para conectarse a la instancia principal de Azure SQL para ese entorno. Ejecute el siguiente comando Transact-SQL (T-SQL) para activar paquetes piloto para el entorno de espacio aislado. (Es posible que tenga que activar el acceso para su dirección IP en LCS antes de poder conectarse de forma remota a Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > Si su implementación de Microsoft Dynamics 365 Finance es una implementación de Service Fabric, puede omitir este paso. El equipo de Finance Insights ya debería haber activado el paquete piloto por usted. Si no ve las características en el espacio de trabajo **Administración de funciones**, o si experimenta problemas al intentar activarlas, póngase en contacto con <fiap@microsoft.com>.
  
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

## <a name="privacy-notice"></a>Aviso de privacidad

Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.
