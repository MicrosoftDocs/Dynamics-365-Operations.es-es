---
title: Definir comunicaciones de canal comercial (Commerce Data Exchange)
description: "Este artículo proporciona una visión general de Commerce Data Exchange y sus componentes. Explica la parte que desempeña cada componente en la transferencia de datos entre Microsoft Dynamics 365 for Operations y los canales de venta minorista."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: ba1bb54a29250a2bb59622ee4391b64ac455af33
ms.contentlocale: es-es
ms.lasthandoff: 04/26/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Definir comunicaciones de canal comercial (Commerce Data Exchange)

[!include[banner](../includes/banner.md)]


Este artículo proporciona una visión general de Commerce Data Exchange y sus componentes. Explica la parte que desempeña cada componente en la transferencia de datos entre Microsoft Dynamics 365 for Operations y los canales de venta minorista.

<a name="overview"></a>Visión general
--------

Commerce Data Exchange es un sistema que transfiere datos entre Microsoft Dynamics 365 for Operations y los canales de venta minorista, como tiendas en línea o tiendas físicas. La base de datos que almacena datos para un canal comercial es independiente de la base de datos de Microsoft Dynamics 365 for Operations. La base de datos del canal solo mantiene los datos necesarios para las transacciones comerciales. Los datos maestros se configuran en Microsoft Dynamics 365 for Operations y se distribuyen a los canales. Los datos transaccionales se crean en el sistema de punto de venta (PDV) o la tienda en línea y, a continuación, se cargan en Microsoft Dynamics 365 for Operations. La distribución de datos es asincrónica. Es decir, el proceso de recopilar y empaquetar datos en el origen se produce por separado del proceso de recepción y aplicación de datos en el destino. Para algunos casos, como las búsquedas de precios y de inventario, los datos se deben recuperar en tiempo real. Para admitir estos escenarios, Commerce Data Exchange también incluye un servicio que habilita la comunicación en tiempo real entre Microsoft Dynamics 365 for Operations y un canal. 

[![updated-retail-graphic](./media/updated-retail-graphic.png)](./media/updated-retail-graphic.png)  

## <a name="async-service"></a>Servicio asincrónico
El seguimiento de cambios de Microsoft SQL Server en la base de datos de Microsoft Dynamics 365 for Operations se usa para determinar los cambios de datos que se deben enviar a los canales. En función de una programación de distribución, Microsoft Dynamics 365 for Operations empaqueta esos datos y los guarda en el almacenamiento central (almacenamiento de blobs de Azure). Un proceso por lotes independiente usa la biblioteca de Commerce Data Exchange: Async Client para insertar este paquete de datos en la base de datos del canal. 

[![Servicio asincrónico](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Programador de tareas Retail

Los trabajos del programador son el mecanismo para la distribución de datos a sus ubicaciones y desde ellas. Los trabajos se componen de subtrabajos, que especifican las tablas y los campos de tablas que contienen los datos que se van a distribuir. Dynamics 365 for Operations incluye trabajos y subtrabajos del programador predefinidos que cumplan requisitos de réplica de la mayoría de las organizaciones. Se crean los siguientes tipos de trabajos predefinidos:

-   **Trabajos de descarga**: los trabajos de descarga envían datos que han cambiado de Dynamics 365 for Operations a las bases de datos de canal. Se realiza un seguimiento de las modificaciones a los registros con el seguimiento de cambios de SQL Server.
-   **Trabajos de carga (trabajos P)**: los trabajos de carga extraen transacciones de ventas de un canal a la base de datos de Dynamics 365 for Operations. Los trabajos P cargan los datos de manera incremental. Cuando se ejecuta un trabajo P, la biblioteca de Async Client comprueba el contador de réplicas para los registros que ya se han recibido de una ubicación. Solo se carga un registro si el contador de réplicas es superior al valor mayor que se encuentra. Los trabajos P no actualizan los datos que se han cargado anteriormente.

La programación de distribución se usa para ejecutar la transferencia de datos, ya sea manualmente o mediante un trabajo por lotes en Dynamics 365 for Operations. Una programación de distribución puede contener uno o más grupos de datos de canal, y uno o más trabajos del programador de tareas.

## <a name="realtime-service"></a>Real-time Service
Commerce Data Exchange: Real-time Service es un servicio integrado que proporciona comunicación en tiempo real entre Dynamics 365 for Operations y los canales comerciales. El servicio de tiempo real permite a los equipos de PDV individuales y las tiendas en línea recuperar los datos específicos de Dynamics 365 for Operations en tiempo real. Aunque la mayoría de las operaciones clave se pueden realizar en la base de datos de canal local, los siguientes escenarios requieren acceso directo a los datos almacenados en Dynamics 365 for Operations:

-   Emisión y canje de tarjetas regalo.
-   Canje de puntos de fidelización.
-   Emisión y canje de notas de crédito.
-   Creación y actualización de registros de clientes.
-   Creación, actualización y finalización de los pedidos de ventas.
-   Recepción de inventario con un pedido de compra o un pedido de transferencia.
-   Realización de recuentos de inventario.
-   Recuperación de transacciones de ventas en almacenes y finalización de transacciones de devolución.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

Se crea un perfil de Real-time Service predefinido.




