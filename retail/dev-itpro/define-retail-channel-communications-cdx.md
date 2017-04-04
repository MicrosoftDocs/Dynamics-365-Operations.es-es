---
title: Definir comunicaciones de canal comercial (Commerce Data Exchange)
description: "Este artículo proporciona una visión general de Commerce Data Exchange y sus componentes. Explica la parte que cada componente realiza en la transferencia de datos entre Microsoft Dynamics 365 para las operaciones y los canales minoristas."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 29938d962db42a521dd8dc03b8e45e0e34410e4d
ms.openlocfilehash: d3b36ec2a3f859215d93dd7ebf1f1ecfb2731c59
ms.lasthandoff: 03/31/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Definir comunicaciones de canal comercial (Commerce Data Exchange)

Este artículo proporciona una visión general de Commerce Data Exchange y sus componentes. Explica la parte que cada componente realiza en la transferencia de datos entre Microsoft Dynamics 365 para las operaciones y los canales minoristas.

<a name="overview"></a>Visión general
--------

Comercio intercambio de datos es un sistema que transfiere datos entre las Dynamics 365 para las operaciones y los canales minoristas, como tiendas en línea o de tiendas físicas. La base de datos que almacena los datos para un canal minorista está a parte de Dynamics 365 de la base de datos de las operaciones. La base de datos del canal solo mantiene los datos necesarios para las transacciones comerciales. Los datos maestros se configuran en Dynamics 365 para las operaciones y se distribuye a los canales. El datos transaccionales se crea en el sistema de (POS) de punto de venta o la tienda en línea y, a continuación se carga a Dynamics 365 para las operaciones. La distribución de datos es asincrónica. Es decir, el proceso de recopilar y empaquetar datos en el origen se produce por separado del proceso de recepción y aplicación de datos en el destino. Para algunos casos, como las búsquedas de precios y de inventario, los datos se deben recuperar en tiempo real. Para apoyar estos casos, comercio intercambio de datos también incluye un servicio que habilita la comunicación en tiempo real entre Dynamics 365 para las operaciones y un canal. 

[actualizar-venta al por menor- gráfico![] (. /media/updated-retail-graphic.png])(. /media/updated-retail-graphic.png)  

## <a name="async-service"></a>Servicio asincrónico
El seguimiento de cambios de Microsoft SQL Server en Dynamics 365 de la base de datos de las operaciones se usa para determinar los datos que se deben registrar en los canales. Basado en una programación de distribución, Dynamics 365 para los paquetes de las operaciones que los datos y los guarda almacenamiento (central almacenamiento blanco cielo del objeto binario). Un proceso por lotes independiente usa la biblioteca de Commerce Data Exchange: Async Client para insertar este paquete de datos en la base de datos del canal. 

[![Async Service](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Programador de tareas Retail

Los trabajos del programador son el mecanismo para la distribución de datos a sus ubicaciones y desde ellas. Los trabajos se componen de subtrabajos, que especifican las tablas y los campos de tablas que contienen los datos que se van a distribuir. La Dynamics 365 para las operaciones incluye los trabajos y trabajos subordinados predefinidos del programador que cumplan los requisitos de cualquier motivo de la mayoría de las organizaciones. Se crean los siguientes tipos de trabajos predefinidos:

-   ** Los trabajos de la descarga ** – los trabajos de la descarga registran los datos que ha cambiado de Dynamics 365 para que las operaciones acanalen las bases de datos. Se realiza un seguimiento de las modificaciones a los registros con el seguimiento de cambios de SQL Server.
-   ** Trabajos de flete (trabajos P) – ** los trabajos de flete extraen transacciones de ventas de un canal en Dynamics 365 de la base de datos de las operaciones. Los trabajos P cargan los datos de manera incremental. Cuando se ejecuta un trabajo P, la biblioteca de Async Client comprueba el contador de réplicas para los registros que ya se han recibido de una ubicación. Solo se carga un registro si el contador de réplicas es superior al valor mayor que se encuentra. Los trabajos P no actualizan los datos que se han cargado anteriormente.

La programación de distribución se usa para ejecutar la transferencia de datos, manualmente o programando un trabajo por lotes en Dynamics 365 para las operaciones. Una programación de distribución puede contener uno o más grupos de datos de canal, y uno o más trabajos del programador de tareas.

## <a name="realtime-service"></a>Servicio en tiempo real
Comercio intercambio de datos: El servicio en tiempo real es un servicio que proporciona integrado la comunicación en tiempo real entre Dynamics 365 para las operaciones y los canales minoristas. El servicio en tiempo real permite a los equipos individuales y a las tiendas en línea de PDV para recuperar los datos específicos de las Dynamics 365 para las operaciones en tiempo real. Aunque la mayoría de las operaciones clave se pueden realizar en la base de datos del canal local, los siguientes escenarios requieren acceso directo a datos que se almacenan en Dynamics 365 para las operaciones:

-   Emisión y canje de tarjetas regalo.
-   Canje de puntos de fidelización.
-   Emisión y canje de notas de crédito.
-   Creación y actualización de registros de clientes.
-   Creación, actualización y finalización de los pedidos de ventas.
-   Recepción de inventario con un pedido de compra o un pedido de transferencia.
-   Realización de recuentos de inventario.
-   Recuperación de transacciones de ventas en almacenes y finalización de transacciones de devolución.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

Se crea un perfil de servicio en tiempo real predefinido.


