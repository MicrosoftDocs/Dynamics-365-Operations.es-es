---
title: Implementar una solución IoT en Azure
description: Sensor Data Intelligence utiliza datos de sensores que están conectados a Microsoft Azure. Este artículo explica cómo implementar una solución de Internet de las cosas (IoT) en su suscripción de Azure.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreAzureResourceDeploymentWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 5f0f49c0f7daaacb85b75dc11b9f015b6aa4e997
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689731"
---
# <a name="deploy-an-iot-solution-on-azure"></a>Implementar una solución IoT en Azure

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Sensor Data Intelligence utiliza datos de sensores que están conectados a Microsoft Azure. Para permitir que Azure recupere datos de sus sensores y los comparta con Dynamics 365 Supply Chain Management, debe implementar una solución de Internet de las cosas (IoT) en su suscripción de Azure. El siguiente diagrama arquitectónico proporciona una descripción general de la solución y sus componentes.

![Diagrama arquitectónico de Sensor Data Intelligence.](media/sdi-architecture.png "Diagrama arquitectónico de Sensor Data Intelligence")

## <a name="video-instructions"></a>Instrucciones de vídeo

El siguiente vídeo muestra cómo [activar la característica de Inteligencia de datos de sensor](sdi-enable-feature.md) e implementar los recursos necesarios de Azure. La otra sección de este artículo proporciona las mismas instrucciones en formato de texto.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE58g3I]

## <a name="procedure"></a>Procedimiento

Siga estos pasos para implementar los recursos necesarios en Azure.

1. Inicie sesión en Supply Chain Management como administrador.
1. Vaya a **Administración del sistema \> Configuración \> Sensor Data Ingelligence \> Implementar y conectar recursos de Azure** para abrir el asistente de implementación.
1. En la página **Bienvenida** página, lea la información y luego seleccione **Siguiente**.
1. En la página **Implementar la solución de IoT de muestra en Azure**, lea la información y luego, en la sección **Instrucciones**, seleccione **Implementar**.
1. Se abre una nueva pestaña del navegador y se le dirige a Azure Portal para que pueda implementar los recursos de Azure. Si se le solicita, inicie sesión con sus credenciales para su suscripción de Azure.
1. En la página **Implementación personalizada**, en el campo **Suscripción**, seleccione su suscripción.
1. En el campo **Grupo de recursos**, seleccione **Crear nuevo** para crear un grupo de recursos para los componentes de Azure que implementará.
1. En el cuadro de diálogo desplegable que aparece, en el campo **Nombre**, introduzca un nombre para el nuevo grupo de recursos (por ejemplo, *IoT-demo*). A continuación seleccione **Aceptar**.
1. Establezca los campos siguientes:

    - **Grupo de recursos** – Seleccione el grupo de recursos que acaba de crear.
    - **Región** – Seleccione una región, idealmente la región donde se implementa su entorno de Supply Chain Management. Tenga en cuenta que las regiones de Azure tienen precios diferentes. Puede ver los costos estimados para su región utilizando la [Calculadora de precios de Sensor Data Intelligence](https://azure.com/e/c36c4947ebff4215b2e62590c2a24c68).
    - **URL del entorno de gestión de la cadena de suministro** – Introduzca la URL de su entorno de Supply Chain Management.
    - **Reutilizar Azure IoT Hub existente** – Deje esta casilla sin marcar.

1. Seleccione **Siguiente: Revisar y crear**.
1. En la pantalla de **Implementación personalizada**, compruebe que se pasa la validación y después seleccione **Crear**.
1. La página **Implementación en progreso** realiza un seguimiento del progreso de su implementación. El proceso de implementación puede tardar hasta 30 minutos. Cuando la página **Implementación en progreso** indica que la implementación se completó, seleccione el enlace del nombre del grupo de recursos para abrir una página que muestre la lista de recursos que se implementan en el grupo.
1. En la lista de recursos, busque el registro donde el campo **Tipo** se establece en *Identidad administrada*. En la columna **Nombre** seleccione el nombre para abrir la página de detalles del recurso.
1. Copie el valor en el campo **Id. de cliente** (por ejemplo, seleccionando el botón **Copiar al portapapeles**).
1. Vuelva a la pestaña del navegador donde se ejecuta Supply Chain Management, *pero no cierre la pestaña de Azure Portal*. La página del asistente **Implementar la solución de IoT de muestra en Azure** aún debe estar abierta. 
1. Seleccione **Siguiente**.
1. En la página **Conectar los recursos de Azure**, en el campo **Id. de cliente de aplicación de Azure AD**, pegue el valor **Id. del cliente** que copió.
1. Vuelva a la pestaña del navegador donde Azure portal está abierto, *pero no cierre la pestaña de Supply Chain Management*. La página de detalles para el recursos debería seguir abierta.
1. Seleccione el botón **Atrás** del navegador para volver a la lista de recursos en el nuevo grupo de recursos.
1. En la lista de recursos, busque el registro donde el campo **Tipo** se establece en *Azure Cache for Redis*. En la columna **Nombre** seleccione el nombre para abrir la página de detalles del recurso.
1. En el panel de navegación izquierdo, seleccione **Claves de acceso**.
1. En la página **Claves de acceso**, copie el valor que se muestra para **Cadena de conexión principal (StackExchange.Redis)** (por ejemplo, seleccionando el botón **Copiar al portapapeles**).
1. Vuelva a la pestaña del navegador donde se está ejecutando Supply Chain Management. La página **Conectar los recursos de Azure** aún debe estar abierta.
1. En el campo **Cadena de conexión del almacén de métricas de Redis**, pegue el valor **Cadena de conexión principal (StackExchange.Redis)** que copió.
1. Seleccione **Fin**.

Los recursos de Azure para Sensor Data Intelligence ahora se implementan en su suscripción de Azure.

> [!NOTE]
> En cualquier momento, puede ver o editar la información de conexión que se guarda en Supply Chain Management abriendo la página **Parámetros del sensor Data Intelligence**. Para obtener más información, consulte los [Parámetros del sensor de Data Intelligence](sdi-parameters.md).
