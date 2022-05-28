---
title: Solucionar problemas de configuración de pronóstico de flujo de efectivo
description: Este tema ofrece respuestas a preguntas que puede que tenga al configurar la previsión de flujo de efectivo. Aborda las preguntas frecuentes (FAQ) sobre la configuración del flujo de efectivo, las actualizaciones del flujo de efectivo y el flujo de efectivo de Power BI.
author: panolte
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e2b5a8df84ff5159a85526251a6367857afa1808
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724596"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>Solucionar problemas de configuración de pronóstico de flujo de efectivo

[!include [banner](../includes/banner.md)]

Este tema ofrece respuestas a preguntas que puede que tenga al configurar la previsión de flujo de efectivo. Aborda las preguntas frecuentes (FAQ) sobre la configuración del flujo de efectivo, las actualizaciones del flujo de efectivo y el flujo de efectivo de Power BI.

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a>¿Por qué se muestra el flujo de efectivo para una sola entidad legal?

La previsión de flujo de caja se configura y calcula por entidad jurídica. Los informes de Power BI y la capacidad de pronóstico de flujo de efectivo en Finance Insights muestran los resultados.

La previsión de flujo de efectivo debe configurarse para cada entidad jurídica para la que desee ver una previsión. Revise la configuración de la previsión de flujo de caja en todas sus entidades legales. Alternativamente, revise la configuración de todas las entidades legales para la previsión de flujo de efectivo y asegúrese de que estén configuradas según lo previsto.

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a>¿Por qué Power BI no muestra todos los datos de flujo de caja?

Se deben completar varios pasos para que los pronósticos de flujo de efectivo puedan aparecer en las vistas de Power BI. Revise la siguiente lista de comprobación y asegúrese de que se hayan completado todos los pasos:

- Configure el flujo de caja para cada entidad legal.
- En los parámetros de contabilidad general, configure la divisa del sistema y el tipo de cambio.
- Configure la divisa de contabilidad general y el tipo de cambio.
- Introduzca los tipos de cambio entre la divisa de transacción y la divisa de contabilidad.
- Introduzca los tipos de cambio entre la divisa contable y la divisa del sistema.
- Introduzca los tipos de cambio entre la divisa contable y cada divisa de banco.

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a>¿Por qué el flujo de caja de Power BI funciona en versiones anteriores pero ahora está en blanco?

Verifique que se hayan configurado las medidas de "Medida de flujo de efectivo V2" y "LedgerCovLiquidityMeasurement" del almacén de entidades. Para obtener más información sobre cómo trabajar con datos del almacén de entidades, consulte [Integración de Power BI con el almacén de entidades](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md). Verifique que todos los pasos necesarios para ver el contenido de Power BI se hayan completado. Para obtener más información, consulte [Contenido de Power BI de visión general de efectivo](Cash-Overview-Power-BI-content.md).

## <a name="have-the-entity-store-entities-been-refreshed"></a>¿Se han actualizado las entidades del almacén de entidades?

Debe actualizar periódicamente sus entidades para asegurarse de que los datos estén actualizados y sean precisos. Para actualizar manualmente una entidad específica, vaya a **Administración del sistema \> Configurar \> Almacén de entidades**, seleccione la entidad y luego seleccione **Actualizar**. Los datos también se pueden actualizar automáticamente. En la página **Almacén de entidades**, configure la opción **Actualización automática habilitada** en **Sí**.

## <a name="which-calculation-method-should-be-used-when-calculating-cash-flow-forecasts"></a>¿Qué método de cálculo se debe utilizar al calcular los pronósticos de flujo de efectivo?

El método de cálculo del pronóstico de flujo de efectivo tiene dos opciones de selección importantes. La opción **Nuevo** calculará los pronósticos de flujo de caja para documentos nuevos y documentos que han cambiado desde que se ejecutó el último trabajo por lotes. Esta opción tiende a ejecutarse más rápido porque procesa un subconjunto más pequeño de documentos. La opción **Total** volverá a calcular los pronósticos de flujo de caja para cada documento del sistema. Esta opción lleva más tiempo porque tiene más trabajo que completar.

### <a name="how-do-i-improve-the-performance-of-the-cash-flow-forecasting-recurring-batch-job"></a>¿Cómo puedo mejorar el rendimiento del trabajo por lotes recurrente del pronóstico de flujo de efectivo?

Recomendamos ejecutar su pronóstico de flujo de efectivo una vez al día durante las horas de menor actividad utilizando el **Nuevo** método de cálculo. Recomendamos utilizar este enfoque seis días a la semana. Luego, ejecute un pronóstico de flujo de efectivo una vez a la semana utilizando el método de cálculo **Total** en el día con la menor cantidad de actividad.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

