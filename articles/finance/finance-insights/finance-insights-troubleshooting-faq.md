---
title: Solucionar problemas de configuración de Finance Insights
description: Este tema enumera los problemas que pueden ocurrir cuando usa las capacidades de Finance Insights. También explica cómo solucionar esos problemas.
author: panolte
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 5669b414283013ae1de095de2201df066ab588dd
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725916"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Solucionar problemas de configuración de Finance Insights

[!include [banner](../includes/banner.md)]

Este tema enumera los problemas que pueden ocurrir cuando usa las capacidades de Finance Insights. También explica cómo solucionar esos problemas.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Síntoma: ¿Por qué no puedo asignar la columna de destino de la plantilla de integración de datos de información de pago del cliente?

### <a name="resolution"></a>Resolución

Es posible que esté utilizando una plantilla para una versión anterior. Antes del lanzamiento de la versión 10.0.17, los clientes de vista previa configuraban la plantilla **Resultados de información sobre pagos del cliente (CDS a Fin and Ops)** de integración de datos (DI) mediante la entidad **Resultado de la predicción de pago (vista previa)**. Después de una actualización a 10.0.17 y posterior, debe usar la plantilla **Resultados de información sobre pagos del cliente (CDS a Fin and Ops 10.0.17 y posterior)** DI para completar la asignación. Es posible que no pueda asignar la columna de destino de la plantilla DI hasta que se actualice la lista de entidades de administración de datos y la entidad **Resultado de la predicción de pago** aparece. Para actualizar la lista de entidades y mostrar el resultado de la predicción de pago, completará los pasos en tanto con Microsoft Dynamics 365 Finance como en Dataverse (anteriormente conocido como el Common Data Service \[CDS\] portal de administración).

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

## <a name="symptom-when-i-try-to-open-ai-builder-by-using-the-links-on-the-customer-payment-predictions-setup-page-why-do-i-receive-the-following-error-message-sorry-theres-been-a-disconnect"></a>Síntoma: cuando intento abrir AI Builder utilizando los enlaces de la página de configuración de predicciones de pago del cliente, ¿por qué recibo el siguiente mensaje de error: "Lo lamentamos, ha habido una desconexión"?

### <a name="resolution"></a>Resolución

Los usuarios de Dynamics 365 Finance deben tener una cuenta de usuario de Microsoft Power Apps para el entorno, y esa cuenta de usuario debe tener el rol de personalizador del sistema. El administrador del sistema de Microsoft Power Apps puede crear la cuenta de usuario y asignar el rol. Luego puede ir a <https://make.preview.powerapps.com/>, iniciar sesión con esa cuenta de usuario y volver a probar los enlaces.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>Síntoma: ¿Por qué la pestaña Previsión de efectivo en el espacio de trabajo Previsión de flujo de efectivo no muestra ningún dato?

### <a name="resolution"></a>Resolución

La función de pronóstico de flujo de efectivo en la gestión de efectivo y bancos y la función de pronóstico de flujo de efectivo en Finance Insights deben configurarse y habilitarse para mostrar correctamente los datos en el espacio de trabajo **Pronóstico de flujo de efectivo**.

Primero, configure y habilite la previsión de flujo de caja y las cuentas de liquidez. Para obtener más información consulte [Previsión de flujo de efectivo](../cash-bank-management/cash-flow-forecasting.md). Si esta configuración se ha completado, pero no ve los resultados que esperaba, consulte [Solucionar problemas de configuración de pronóstico de flujo de efectivo](../cash-bank-management/cash-flow-forecasting-tsg.md) para más información.

A continuación, confirme que la función de previsiones de flujo de caja en Finance Insights (**Gestión de caja y banco \> Configuración \> Finance Insights \> Previsiones de flujo de caja**) se ha habilitado y se ha completado el entrenamiento del modelo de IA. Si la formación no se ha completado, seleccione **Pronosticar ahora** para iniciar el proceso de formación del modelo.

## <a name="symptom-why-isnt-the-install-a-new-add-in-button-visible-in-microsoft-dynamics-lifecycle-services"></a>Síntoma: ¿Por qué el botón Instalar un nuevo complemento no está visible en Microsoft Dynamics Lifecycle Services?

### <a name="resolution"></a>Resolución

Primero, verifique que el rol **Administrador del entorno** o **Propietario del proyecto** está asignado al usuario que inició sesión en el campo **Rol de seguridad del proyecto** en Microsoft Dynamics Lifecycle Services (LCS). La instalación de los nuevos complementos requiere uno de estos roles de seguridad del proyecto.

Si se le asigna el rol de seguridad del proyecto correcto, es posible que deba actualizar la ventana del navegador para ver el botón **Instalar nuevo complemento**.

## <a name="symptom-the-finance-insights-add-in-doesnt-seem-to-be-installing-why-is-that"></a>Síntoma: el complemento Finance Insights no parece instalarse. ¿Por qué?

### <a name="resolution"></a>Resolución

Se deberían haber completado los siguientes pasos.

- Verifique que tiene acceso **Administrador de sistema** y **Personalizador del sistema** en el Centro de administración de Power Portal.
- Verifique que se aplica una licencia de Dynamics 365 Finance o equivalente al usuario que está instalando el complemento.
- Verifique que la siguiente aplicación Azure AD está registrada en Azure AD: 

  | Solicitud                  | Id. de aplicación           |
  | ---------------------------- | ---------------- |
  | CDS de microservicios de Microsoft Dynamics ERP | 703e2651-d3fc-48f5-942c-74274233dba8 | 
  
## <a name="symptom-error-we-didnt-find-any-data-for-the-selected-filter-range-please-select-a-different-filter-range-and-try-again"></a>Síntoma: Error, "No encontramos ningún dato para el rango de filtro seleccionado. Seleccione un rango de filtro diferente y vuelva a intentarlo". 

### <a name="resolution"></a>Resolución

Verifique la configuración del integrador de datos para validar que esté funcionando como se esperaba y alterando los datos de AI Builder volver a Finance.  
Para obtener más información, consulte la sección [Crear un proyecto de integración de datos](../finance-insights/create-data-integrate-project.md).

## <a name="symptom-customer-payment-prediction-training-failed-and-the-ai-builder-error-states-prediction-should-have-only-2-distinct-outcome-values-to-train-the-model-map-to-two-outcomes-and-retrain-training-report-issue-isnotminrequireddistinctnonnullvalues"></a>Síntoma: el entrenamiento de predicción de pago del cliente falló y el error de AI Builder dice: "La predicción debe tener solo 2 valores de resultado distintos para entrenar el modelo. Asigne a dos resultados y vuelva a entrenar", "Problema del informe de entrenamiento: IsNotMinRequiredDistinctNonNullValues".

### <a name="resolution"></a>Resolución

Este error indica que no hay suficientes transacciones históricas en el último año que representen cada categoría descrita en las categorías **A tiempo**, **Tarde** y **Muy tarde**. Para resolver este error, ajuste el período de transacción **Muy tarde**. Si ajustando el el período de transacción **Muy tarde** no corrige el error, **Predicciones de pago del cliente** no es la mejor solución para usar, ya que necesita datos en cada categoría con fines de capacitación.

Para obtener más información sobre cómo ajustar las categorías **A tiempo**, **Tarde** y **Muy tarde**, vea [Habilitar predicciones de pago de clientes](../finance-insights/enable-cust-paymnt-prediction.md).

## <a name="symptom-model-training-failed"></a>Síntoma: el entrenamiento del modelo falló

### <a name="resolution"></a>Resolución

El entrenamiento del modelo **Pronóstico de flujo de efectivo** requiere datos que abarquen más de un año y contengan más de 100 transacciones. Recomendamos que tenga al menos dos años de datos con más de 1000 transacciones.

La característica **Predicciones de pago de cliente** requiere más de 100 transacciones en los seis a nueve meses anteriores. Las transacciones pueden incluir facturas de servicios, pedidos de venta y pagos de clientes. Estos datos deben estar repartidos por toda la configuración **A tiempo**, **Tarde** y **Muy tarde** definida en la página **Configuración**.    

La característica **Propuesta de presupuesto** requiere un mínimo de tres años de presupuesto o datos reales. Esta solución utiliza de tres a diez años de datos en las proyecciones. Más de tres años de datos proporcionarán mejores resultados. Los datos en sí funcionan mejor cuando hay variación en los valores. Si los datos contienen todos los datos constantes, como un gasto de arrendamiento, la capacitación puede fallar porque la falta de variación no requiere que la IA proyecte las cantidades.

## <a name="symptom-error-message-states-that-the-table-with-name-msdyn_paypredpredictionresultentities-does-not-exist-the-remote-server-returned-an-error-404-not-found"></a>Síntoma: el mensaje de error indica que la "Tabla con el nombre, 'msdyn_paypredpredictionresultentities' no existe. El servidor remoto devolvió un error: (404) Not Found..."

### <a name="resolution"></a>Resolución

El entorno alcanzó el límite máximo de tablas de los servicios de Data Lake. Para obtener más información sobre el límite, consulte la sección **Habilitar cambios de datos casi en tiempo real** del tema, [Información general de Exportar a Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/Azure-Data-Lake-GA-version-overview.md).
