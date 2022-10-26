---
title: Configurar un sensor simulado para pruebas
description: Este artículo describe cómo configurar un simulador que puede usar para probar Sensor Data Intelligence sin instalar ningún sensor físico.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: f12d6e1d417a260477b1eb4e027b850d1862f51f
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689814"
---
# <a name="set-up-a-simulated-sensor-for-testing"></a>Configurar un sensor simulado para pruebas

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Si desea probar Sensor Data Intelligence sin instalar ningún sensor físico, puede utilizar el servicio *Simulador en línea de Raspberry PI Azure IoT* para emular señales de sensores y enviarlas a su solución de Internet de las cosas (IoT) en Microsoft Azure. Para obtener más información sobre el simulador, consulte [Conecte el simulador en línea de Raspberry Pi a Azure IoT Hub (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started).

## <a name="video-instructions"></a>Instrucciones de vídeo

El siguiente vídeo muestra cómo configurar un sensor simulado para realizar pruebas. Las secciones restantes de este artículo proporcionan las mismas instrucciones en formato de texto.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE588g6]

## <a name="create-a-device-in-azure-iot-hub"></a>Crear un dispositivo en Azure IoT Hub

Primero debe configurar un dispositivo para autenticar las señales del sensor en Azure IoT Hub.

1. En Azure, vaya a la lista de recursos para el grupo de recursos que creó para usar con Sensor Data Intelligence. (Para obtener más información, vea [Implementar una solución IoT en Azure](sdi-deploy-iot-solution-on-azure.md).)
1. En la lista de recursos, busque el registro donde el campo **Tipo** se establece en *IoT Hub*. En la columna **Nombre** seleccione el nombre para abrir la página de detalles del recurso.
1. En el panel de navegación izquierdo, seleccione **Dispositivos**.
1. En la página **Dispositivos**, seleccione **Agregar dispositivo**.
1. En la página **Crear un dispositivo**, configure los siguientes campos:

    - **Identificación del dispositivo** – Introduzca un nombre para el nuevo dispositivo (por ejemplo, *Mi-dispositivo-IoT*).
    - **Tipo de autenticación** - Seleccione *Claves simétricas*.
    - **Generar claves automáticamente** – Seleccione esta casilla de verificación.
    - **Conectar este dispositivo a un centro de IoT** - Seleccione *Habilitar*.

1. Seleccione **Guardar** para volver a la página **Dispositivos**.
1. Busque el nuevo dispositivo en la lista. En la columna **Id. de dispositivo** seleccione el nombre para abrir la página de detalles del dispositivo. Si no ve el nuevo dispositivo en la lista, actualice la página.
1. Copie el valor **Cadena de conexión principal** (por ejemplo, seleccionando el botón **Copiar al portapapeles**). Necesitará este valor más adelante cuando configure el simulador IoT de Raspberry Pi para emular las señales del sensor. Por lo tanto, considere pegarlo en un archivo de texto por ahora.

## <a name="add-the-azure-connection-string-to-the-raspberry-pi-iot-simulator"></a>Agregue la cadena de conexión de Azure al simulador de IoT de Raspberry Pi

Siga estos pasos para agregar la cadena de conexión desde el dispositivo en Azure IoT Hub al script en el servicio Raspberry.

1. Abra el [Simulador IoT de Raspberry Pi](https://azure-samples.github.io/raspberry-pi-web-simulator/).
1. En el panel del editor de código, busque la línea que contiene el siguiente comando.

    `const connectionString = '[Your IoT hub device connection string]';`

1. Reemplace el texto de ayuda, incluidos los corchetes, con el valor de **Cadena de conexión principal** que copió en la sección anterior. El resultado se parecerá al ejemplo siguiente.

    `const connectionString = 'HostName=XXX;DeviceId=YYY;SharedAccessKey=ZZZ';`

## <a name="add-sensor-ids-and-values-to-the-payload-in-the-raspberry-pi-iot-simulator"></a>Agregue ID y valores de sensores a la carga útil en el simulador de IoT de Raspberry Pi

Ahora debe configurar el simulador Raspberry Pi IoT con sensores simulados y los valores que enviarán como cargas útiles.

- En el editor de código del simulador Raspberry Pi IoT, busque la función `getMessage` y edítela para que coincida con el siguiente código. (Los sensores se configuran en las líneas `cb()`.)

    ```cpp
    function getMessage(cb) {
        messageId++;
        sensor.readSensorData()
        .then(function (data) {
            cb(JSON.stringify({ value: 1, sensorId: 'MachineStatus' }), false);
            cb(JSON.stringify({ value: 70, sensorId: 'Quality' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'AssetMaintenance' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'ProductionDelay' }), false);
            cb(JSON.stringify({ value: 20, sensorId: 'AssetDowntime' }), false);
        })
        .catch(function (err) {
            console.error('Failed to read out sensor data: ' + err);
        });
    }
    ```

    > [!IMPORTANT]
    > Los ID de sensores que se definen en el editor de código para el simulador de IoT de Raspberry Pi deben ser idénticos a los ID de sensores que especificará más adelante para los escenarios en Supply Chain Management. El código de ejemplo anterior utiliza ID de sensor legibles por humanos. Sin embargo, en un escenario real, los ID de sensor serán valores de identificador único global (GUID) proporcionados por el fabricante del sensor. Los ID de sensor legibles por humanos que se usan en este código de ejemplo también se usan en los ejemplos de [El escenario de la calidad del producto](sdi-scenario-product-quality.md), [El escenario de mantenimiento de activos](sdi-scenario-asset-maintenance.md), [El escenario de retrasos en la producción](sdi-scenario-production-delays.md), y [El escenario del estado de la máquina](sdi-scenario-equipment-downtime.md)). Por lo tanto, use este código si trabajará en esos escenarios.

## <a name="edit-the-interval-for-sending-sensor-signals"></a>Edite el intervalo para enviar señales del sensor

Ahora debe establecer el intervalo en el que el simulador Raspberry Pi IoT debe enviar las señales del sensor emulado.

1. En el editor de código del simulador Raspberry Pi IoT, busque la siguiente invocación de función.

    `setInterval(sendMessage, 2000);`

2. De forma predeterminada, el simulador IoT de Raspberry Pi envía una señal de sensor cada 2000 milisegundos (dos segundos). Puede ajustar el valor si es necesario.

## <a name="run-the-raspberry-pi-iot-simulator"></a>Ejecute el Simulador IoT de Raspberry Pi

- Seleccione **Ejecutar** para iniciar el simulador y comenzar a enviar datos de sensores simulados.
