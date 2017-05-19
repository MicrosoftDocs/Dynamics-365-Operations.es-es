---
title: "Catálogos de centros de llamadas"
description: "Este artículo describe la funcionalidad específica del centro de llamadas para catálogos en Microsoft Dynamics 365 for Operations."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: e495d5a94e714eb42e04eb12fbd551fa2f552c1f
ms.contentlocale: es-es
ms.lasthandoff: 04/26/2017


---

# <a name="call-center-catalogs"></a>Catálogos de centros de llamadas

[!include[banner](includes/banner.md)]


Este artículo describe la funcionalidad específica del centro de llamadas para catálogos en Microsoft Dynamics 365 for Operations.

En un centro de llamadas, puede usar los catálogos de productos comerciales para identificar los productos que desee ofrecer a los clientes. Los centros de llamadas usan normalmente catálogos impresos. El diseño y la producción de un catálogo impreso se gestiona fuera de Microsoft Dynamics 365 for Operations. Sin embargo, puede crear y almacenar un formulario digital de un catálogo de venta al por mayor y comercio en Dynamics 365 for Operations con las mismas páginas que usa para configurar catálogos de venta al por mayor en línea. Antes de poder crear un catálogo, debe configurar las selecciones de productos y asignar las selecciones a un centro de llamadas. A continuación agrega productos al catálogo seleccionando los productos de estas selecciones. Después de agregar los productos al catálogo y de haberlo completado, debe validar el catálogo para comprobar los datos. A continuación, debe enviar el catálogo para su revisión y aprobación. Una vez aprobado el catálogo, es se puede publicar. Cuando se crea un catálogo de centro de llamadas, puede tomar una instantánea de los datos del catálogo en el momento en que el catálogo se publica. Esta función de la instantánea permite el acceso a una versión concreta del catálogo incluso si el catálogo se cambia y se actualiza más adelante. Los catálogos del centro de llamadas también se pueden configurar para incluir las características opcionales siguientes:

-   **Códigos fuente**: códigos fuente que se utilizan para realizar un seguimiento de la respuesta del cliente en correos de catálogos específicos.
-   **Productos gratuitos**: se pueden incluir productos en el pedido de un cliente sin ningún gasto adicional. Estos productos se agregan a un pedido automáticamente cuando el código fuente del catálogo se especifica en el pedido.
-   **Scripts**: los scripts son textos que un trabajador del centro de llamadas lee a un cliente cuando se crea un pedido de ventas. Las secuencias de comandos pueden incluir saludos o sugerencias de compras.
-   **Diseño de página**: un diseño de página captura la posición de la página de productos del catálogo impreso. Esta información se usa para el informe de análisis del área del catálogo.





