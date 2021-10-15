---
title: Solucionar problemas de configuración de Finance Insights
description: Este tema enumera los problemas que pueden ocurrir cuando usa las capacidades de Finance Insights. También explica cómo solucionar esos problemas.
author: panolte
ms.date: 08/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 7ff42ffc334147c1a4c6b6349c86580df7f1955b
ms.sourcegitcommit: 47a3ad71210c7ac84d0c25e913c440b5ba205282
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2021
ms.locfileid: "7512899"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Solucionar problemas de configuración de Finance Insights

[!include [banner](../includes/banner.md)]

Este tema enumera los problemas que pueden ocurrir cuando usa las capacidades de Finance Insights. También explica cómo solucionar esos problemas.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Síntoma: ¿Por qué no puedo asignar la columna de destino de la plantilla de integración de datos de información de pago del cliente?

### <a name="resolution"></a>Resolución

Es posible que esté utilizando una plantilla para una versión anterior. Antes del lanzamiento de la versión 10.0.17, los clientes de vista previa configuraban la plantilla **Resultados de información sobre pagos del cliente (CDS a Fin and Ops)** de integración de datos (DI) mediante la entidad **Resultado de la predicción de pago (vista previa)**. Después de una actualización a 10.0.17 y posterior, debe usar la plantilla **Resultados de información sobre pagos del cliente (CDS a Fin and Ops 10.0.17 y posterior)** DI para completar la asignación. Es posible que no pueda asignar la columna de destino de la plantilla DI hasta que se actualice la lista de entidades de administración de datos y la entidad **Resultado de la predicción de pago** aparece. Para actualizar la lista de entidades y mostrar el resultado de la predicción de pago, completará los pasos en Microsoft Dynamics 365 Finance y Dataverse (anteriormente conocido como el Common Data Service \[CDS\] portal de administración).

### <a name="in-finance"></a>En Finance

Siga estos pasos en Finance después de la actualización.

1. Vaya a **Administración del sistema \> Áreas de trabajo \> Administración de datos**.
2. En espacio de trabajo **Administración de datos**, seleccione la ventana **Parámetros de marco**.
3. En la página **Parámetros del marco de importación / exportación de datos**, seleccione **Configuración de la entidad** y luego seleccione **Actualizar lista de entidades**.
4. Cierre la página **Parámetros del marco de importación / exportación de datos**.
5. En espacio de trabajo **Administración de datos**, seleccione la ventana **Entidades de datos**.
6. Busque "Resultado de la predicción de pago". Verifique que la entidad **Resultado de la predicción de pago** no es la versión de vista previa. El nombre de la versión de vista previa termina en "(vista previa)". Si solo ve la versión de vista previa de la entidad, contacte con el Soporte técnico de Microsoft.

### <a name="in-dataverse"></a>En Dataverse

Siga estos pasos en el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com/environments) para actualizar sus proyectos de integración de datos.

1. Si está utilizando una versión de vista previa de Finance Insights, elimine el proyecto de DI que está asociado con la plantilla **Resultados de información sobre pagos del cliente (CDS a Fin and Ops)**.
2. Siga los pasos en [Crea un proyecto de integrador de datos](create-data-integrate-project.md). Use la plantilla **Resultados de información sobre pagos del cliente (CDS a Fin and Ops 10.0.17 y posterior)**.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>Síntoma: ¿Por qué la pestaña Previsión de efectivo en el espacio de trabajo Previsión de flujo de efectivo no muestra ningún dato?

### <a name="resolution"></a>Resolución

La función de pronóstico de flujo de efectivo en la gestión de efectivo y bancos y la función de pronóstico de flujo de efectivo en Finance Insights deben configurarse y habilitarse para mostrar correctamente los datos en el espacio de trabajo **Pronóstico de flujo de efectivo**.

Primero, configure y habilite la previsión de flujo de caja y las cuentas de liquidez. Para obtener más información consulte [Previsión de flujo de efectivo](../cash-bank-management/cash-flow-forecasting.md). Si esta configuración se ha completado, pero no ve los resultados que esperaba, consulte [Solucionar problemas de configuración de pronóstico de flujo de efectivo](../cash-bank-management/cash-flow-forecasting-tsg.md) para más información.

A continuación, confirme que la función de previsiones de flujo de caja en Finance Insights (**Gestión de caja y banco \> Configuración \> Finance Insights \> Previsiones de flujo de caja**) se ha habilitado y se ha completado el entrenamiento del modelo de IA. Si la formación no se ha completado, seleccione **Pronosticar ahora** para iniciar el proceso de formación del modelo.
