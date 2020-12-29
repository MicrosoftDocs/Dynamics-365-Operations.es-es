---
title: Uso del programa de continuidad
description: Este procedimiento muestra el proceso de venta de un programa de continuidad y el procesamiento de pedidos de ventas relacionados.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2baf0127a35cc62952fd78daaf8204d35ec8d2b3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415564"
---
# <a name="using-continuity-program"></a>Uso del programa de continuidad

[!include [banner](../includes/banner.md)]

Este procedimiento muestra el proceso de venta de un programa de continuidad y el procesamiento de pedidos de ventas relacionados. Para completar este procedimiento, el usuario tiene que configurarse como un usuario del centro de llamadas. Este procedimiento usa la empresa de datos de demostración USRT.

1. Vaya a Retail y Commerce > Clientes > Servicio al cliente.
2. En el campo SearchText, escriba "Karen" y luego presione la tecla de tabulador.
    * Debería surgir el diálogo de búsqueda avanzada. Si no es así, haga clic en Búsqueda a la derecha de este campo.  
3. En la lista, marque la fila seleccionada.
    * Debe haber una sola fila con la demostración de Karen Berg. Seleccione la fila haciendo clic en la columna de la marca de verificación en el extremo izquierdo de la cuadrícula.  
4. Haga clic en Seleccionar.
5. Haga clic en Nuevo pedido de ventas.
    * Conviene anotar el número de pedido de venta. Lo necesitará más adelante en este procedimiento.  
6. En el campo Número de artículo, escriba "88000" y luego presione la tecla de tabulador.
    * Esto es un elemento de continuidad en los datos de demostración de USRT.  
7. Haga clic en Completar.
8. En el campo Método de pago, seleccione "Visa".
9. Haga clic en Agregar tarjeta de crédito.
    * Especifique la información de la tarjeta de crédito requerida en esta página.  
10. Haga clic en Aceptar
11. Expanda la sección Pago.
    * Para enviar un pedido del centro de llamadas, es necesario especificar los pagos para el pedido.  
12. Haga clic en Aceptar
13. Haga clic en Enviar.
    * Ha finalizado con la creación de un nuevo pedido de continuidad. A continuación, deberá ejecutar dos procesos de lotes que se usan para procesar los pedidos de continuidad.  
14. Cierre la página.
15. Vaya a Retail y Commerce > Continuidad > Procesar pagos de continuidad.
16. En el campo Artículo de continuidad, escriba “88000 " y luego presione la tecla de tabulador.
17. Haga clic en Aceptar.
18. Vaya a Retail y Commerce > Continuidad > Crear pedidos secundarios de continuidad.
    * Este proceso creará nuevos pedidos de ventas en función de los valores de sus programas de continuidad.  
19. En el campo Artículo de continuidad, escriba “88000 " y luego presione la tecla de tabulador.
    * El artículo "88000" es un artículo de continuidad en los datos de demostración de USRT.  
20. En el campo Pedido de ventas, especifique o seleccione un valor.
    * Especifique el número de pedido de ventas que ha anotado antes en el procedimiento. Esto mantendrá el tiempo de procesamiento al mínimo para este procedimiento. El campo Pedido de ventas es opcional. Podría procesar todos los pedidos para cualquier programa.  
21. Haga clic en Aceptar

