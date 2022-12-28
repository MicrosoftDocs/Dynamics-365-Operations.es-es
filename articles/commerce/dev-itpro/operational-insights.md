---
title: Configurar Operational Insights
description: Este artículo describe cómo configurar y usar la función Operational Insights en Microsoft Dynamics 365 Commerce.
author: ashishMSFT
ms.date: 12/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: ca0d31e403275d6131fa6d53f0a7b46a7ddb651d
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832141"
---
# <a name="set-up-operational-insights"></a>Configurar Operational Insights

[!include [banner](../includes/banner.md)]

Este artículo describe cómo configurar y usar la función Operational Insights en Microsoft Dynamics 365 Commerce.

Operational Insights es una función Dynamics 365 Commerce diseñada para brindar a los clientes una mejor visibilidad del estado de su servicio y la funcionalidad comercial mediante el envío de telemetría directamente a una cuenta propiedad del cliente Application Insights .

Al habilitar Operational Insights para sus entornos en Commerce Headquarters, puede recopilar una lista seleccionada de eventos tanto de Commerce Scale Unit (CSU) como de sus dispositivos de punto de venta (POS). Estos eventos pueden ayudarlo a comprender mejor el rendimiento de sus sistemas y le permiten monitorear métricas técnicas y comerciales clave.

Incluso si no desea recopilar esta telemetría todo el tiempo, puede beneficiarse al habilitar o deshabilitar rápidamente la recopilación para entornos específicos. De esta manera, la telemetría puede ayudarlo a solucionar problemas o depurar durante el desarrollo o la producción.

## <a name="access-logs-in-application-insights"></a>Registros de acceso en Application Insights

Para acceder a los registros de eventos de diagnóstico para los componentes Commerce CSU y POS a través de Application Insights, complete los procedimientos de esta sección.

### <a name="minimum-version-requirements-for-csu"></a>Requisitos mínimos de versión para CSU

CSU tiene los siguientes requisitos mínimos de versión:

- 10.0.23 (versión del servidor minorista 9.33.22062.15 y posterior)
- 10.0.24 (versión del servidor minorista 9.34.22062.14 y posterior)
- 10.0.25 (versión del servidor minorista 9.35.22062.13 y posterior)
- 10.0.26 y posetrior (todas las versiones)

### <a name="enable-diagnostic-events-in-application-insights"></a>Habilitar eventos de diagnóstico en Application Insights

> [!IMPORTANT]
> Si usó anteriormente una versión preliminar de Operational Insights, debe usar el siguiente procedimiento para habilitar Operational Insights. De esta manera, se asegura de que pueda continuar el acceso confiable y seguro a los eventos.

Para habilitar los eventos de diagnóstico del componente Commerce, debe tener una cuenta Application Insights . Puede usar una cuenta existente o [crear una cuenta nueva](/azure/azure-monitor/app/create-workspace-resource#create-workspace-based-resource). Por motivos de privacidad de datos, le recomendamos que utilice cuentas de Application Insights independientes para los entornos de producción, sandbox y desarrollo. Después de crear una cuenta, debe habilitar la función **Operational Insights** en la sede.

Para habilitar eventos de diagnóstico en Application Insights, siga estos pasos.

1. En la sede, abra el espacio de trabajo **Administración de funciones** y habilite la función **Operational Insights**.
1. Vaya a **Administración del sistema \> Configuración \> Operational Insights**.
1. En la pestaña **Configurar**, establezca la opción **Eventos de canal de Commerce** en **Sí**.
1. En la pestaña **Entornos**, ingrese los valores **ID de entorno LCS** y **Modo de entorno** para cada entorno en el que planea usar Application Insights. Puede encontrar el ID de entorno de cada entorno en la página **Detalles del entorno** para ese entorno en Microsoft Dynamics Lifecycle Services. Este paso es necesario para ayudar a evitar que los eventos de diagnóstico se envíen inadvertidamente a un entorno incorrecto cuando se realizan operaciones de copia de la base de datos.
1. En la pestaña **Registro de Application Insights**, especifique el valor de la **clave de instrumentación** de Application Insights y el **modo de entorno** correspondiente de los entornos en los que piensa utilizar cada cuenta de Application Insights.
1. Después de completar la configuración anterior, debe ejecutar el trabajo **CDX Job 1110**. Puede esperar a que este trabajo se ejecute en su propio horario o puede ejecutarlo manualmente.
1. En Lifecycle Services, vaya a **Detalles del entorno \> Commerce \> Gestionar**, seleccione una instancia de CSU y luego seleccione **Reiniciar**. Repita este paso para cada CSU.
1. Repita los pasos anteriores para cada entorno en el que planee usar Application Insights.

> [!NOTE]
> - Los eventos de telemetría en Operational Insights están sujetos a cambios. Le recomendamos que utilice los eventos de Operational Insights para realizar análisis preliminares y solucionar problemas por su cuenta, no para definir paneles o alertas. Si usa eventos para fines que van más allá de la solución de problemas de autoservicio, le recomendamos que valide y actualice sus consultas después de cada lanzamiento de CSU/POS.
> - A partir de la versión 10.0.29 de Commerce, los procedimientos de esta sección también permiten la transmisión de eventos de POS Operational Insights a su cuenta de Application Insights. Para obtener más información, consulte [Perspectivas operativas para POS: eventos y consultas](https://download.microsoft.com/download/9/2/b/92be35b0-0e24-4a4d-940d-6f4db29791c0/Operational-Insights-Commerce-POS-events-queries.pdf).

#### <a name="use-the-dllhostexeconfig-file-to-control-pos-operational-insights-events"></a>Use el archivo DLLHost.exe.config para controlar los eventos de POS Operational Insights

Para usar el archivo DLLHost.exe.config para controlar los eventos de POS Operational Insights, siga estos pasos.

1. En un editor de texto, abra el archivo **DLLHost.exe.config** en **C:\\Archivos de programa (x86)\\Microsoft Dynamics 365\\70\\Retail Modern POS\\ClientBroker**.
1. En la sección **diagnosticsSection**, elimine el elemento XML receptor que tiene el nombre de clase **Microsoft.Dynamics.Retail.Diagnostics.OperationalInsights.OperationalInsightsLogger**.
1. Guarde el archivo.

### <a name="disable-diagnostic-events-in-application-insights"></a>Deshabilitar eventos de diagnóstico en Application Insights

> [!IMPORTANT]
> Si desea deshabilitar los eventos de diagnóstico y no enviarlos más a Application Insights, debe completar el siguiente procedimiento. No puede simplemente deshabilitar esta característica de vista previa en Gestión de funciones.

Para deshabilitar eventos de diagnóstico en Application Insights, siga estos pasos.

1. En la sede, vaya a **Administración del sistema \> Operational Insights**.
1. En la pestaña **Configurar**, establezca la opción **Eventos de canal de Commerce** en **No**.
1. Después de completar la configuración anterior, debe ejecutar el trabajo **CDX Job 1110**. Puede esperar a que este trabajo se ejecute en su propio horario o puede ejecutar el trabajo manualmente.
1. En Lifecycle Services, vaya a **Detalles del entorno \> Commerce \> Gestionar**, seleccione una instancia de CSU y luego seleccione **Reiniciar**. Repita este paso para cada CSU.
1. Repita los pasos anteriores para cada entorno en el que planee desactivar Application Insights.

Para deshabilitar eventos de diagnóstico para un solo entorno, elimine la clave de instrumentación en la pestaña **Registro de Application Insights** de la página **Operational Insights**. Luego complete los pasos 3 y 4 del procedimiento anterior.

> [!NOTE]
> En Commerce versión 10.0.29 y posteriores, los pasos de esta sección también deshabilitan la transmisión de eventos de POS Operational Insights a su cuenta de Application Insights. 
