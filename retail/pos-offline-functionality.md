---
title: "Funcionalidad sin conexión de PDV"
description: "Este artículo proporciona información acerca del modo sin conexión para Retail Modern POS, en el que los dispositivos de PDV cambian automáticamente de la base de datos de canales a la base de datos sin conexión si el servidor minorista no está disponible. Este artículo también incluye la información de configuración general para el modo sin conexión y explica la sincronización de datos que se produce entre la base de datos sin conexión y la base de datos de canales."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 27041
ms.assetid: 20b51874-8912-40cf-9296-864df707315a
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ef4d20b3302e4a420c7013b77a57ebdfa99fe6a3
ms.lasthandoff: 03/31/2017


---

# <a name="pos-offline-functionality"></a>Funcionalidad sin conexión de PDV

[!include[banner](includes/banner.md)]


Este artículo proporciona información acerca del modo sin conexión para Retail Modern POS, en el que los dispositivos de PDV cambian automáticamente de la base de datos de canales a la base de datos sin conexión si el servidor minorista no está disponible. Este artículo también incluye la información de configuración general para el modo sin conexión y explica la sincronización de datos que se produce entre la base de datos sin conexión y la base de datos de canales.

<a name="overview"></a>Visión general
--------

En Retail Modern POS, un dispositivo de punto de venta (PDV) entra en el modo sin conexión siempre que Retail Server no está disponible. Por lo tanto, si se pierde la conexión con Retail Server, Retail Modern POS cambia automáticamente a la base de datos sin conexión. Durante una transacción de ventas, si una solicitud de datos no es correcta dentro del intervalo de tiempo de espera que se configura en el perfil sin conexión, Retail Modern POS cambia automáticamente a la base de datos sin conexión y continúa la transacción de ventas. Mientras el dispositivo de PDV se encuentra en el modo sin conexión, Retail Modern POS intenta volver a conectarse a Retail Server tras el intervalo del intento de reconexión que se configura en el perfil sin conexión. Este intento de reconexión solo se produce al comienzo de una transacción.

### <a name="determining-the-connection-mode-of-retail-modern-pos"></a>Determinación del modo de conexión de Retail Modern POS

El encabezado del estado en Retail Modern POS indica el estado actual de la conexión y la ventana **Estado de conexión** muestra el estado del último intento de sincronización con la base de datos sin conexión. [![Estado de conexión](./media/status.png)](./media/status.png)

### <a name="creating-a-button-to-manually-switch-between-online-and-offline-modes"></a>Creación de un botón para pasar manualmente entre los modos en línea y sin conexión

Puede agregar un botón a Retail Modern POS para cambiar manualmente entre los modos en línea y sin conexión. Cree un botón para la operación del PDV **917 – Estado de conexión de base de datos**. El nombre de este botón es **Desconectar** cuando Retail Modern POS está conectado a Retail Server y **Conectar** cuando está desconectado. Puede usar este botón para ver la conexión y para desconectarse de Retail Server o conectarse a él. [![Botón Desconectar en Retail Modern POS](./media/details-1024x537.png)](./media/details.png)

## <a name="setup"></a>Instalación
Para habilitar el soporte sin conexión para un dispositivo de PDV (registro), establezca la opción **Soporte sin conexión** en **Sí** en la página **Registro**. Se crea una nueva entidad de base de datos de canal y se agrega al grupo de datos de canal de la tienda. A continuación, ejecute todas las programaciones de distribución necesarias para generar los paquetes de datos para la base de datos sin conexión. A continuación, configure la versión sin conexión de Retail Modern POS. El proceso de instalación crea la base de datos sin conexión. Además, instale Microsoft SQL Server 2014 Express si es necesario. La sincronización de datos sin conexión empieza tras el primer inicio de sesión en Retail Modern POS.

## <a name="data-synchronization"></a>Sincronización de datos
El Programador de tareas Retail se usa para enviar datos maestros a la base de datos sin conexión. De manera predeterminada, cuando se ejecuta una programación de distribución, los cambios de datos se envían tanto a la base de datos de canal como a la base de datos sin conexión. Retail Modern POS incluye la biblioteca asincrónica/sincrónica, que descarga los paquetes de datos disponibles y los inserta en la base de datos sin conexión. Si las transacciones se crean sin conexión, Retail Modern POS las carga en Retail Server, para que se puedan insertar en la base de datos de canal. La sincronización de datos solo se puede producir si se está ejecutando Retail Modern POS. [![Sincronización sin conexión](./media/offline-sync-1024x521.png)](./media/offline-sync.png)




