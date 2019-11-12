---
title: Goteo en la creación de pedidos basados en fuente para transacciones de tienda
description: En este tema se describe el goteo de la creación de pedidos basados en fuente para las transacciones de tienda en Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 80233a73dbffc7380503cf03703758b187824c2a
ms.sourcegitcommit: 0262a19e32b2c0c84c731d9f4fbe8ba91822afa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "2622675"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions-public-preview"></a>Goteo en la creación de pedidos basados en fuente para transacciones de tienda (versión preliminar pública)

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

En Dynamics 365 Retail versión 10.0.4 y anteriores, el registro del extracto comercial es una operación de final del día y todas las transacciones se registran en los libros al final del día. Las transacciones grandes deben procesarse a continuación en una ventana de tiempo limitada, lo que a veces da lugar a errores de registro de extractos, carga y bloqueos. Los minoristas tampoco pueden reconocer ingresos y pagos en los libros durante todo el día.

Con la versión preliminar pública del goteo de la creación de pedidos basados en fuente introducido en Retail versión 10.0.5, las transacciones se procesan durante todo el día y solo la conciliación financiera de formas de pago y otras transacciones de gestión de efectivo se procesan al final del día. Esta funcionalidad divide la carga de la creación de pedidos de ventas, facturas y pagos durante el día, ofreciendo el mejor rendimiento percibido y a la capacidad de reconocer ingresos y pagos en los libros casi en tiempo real. 


## <a name="how-to-use-trickle-feed-based-posting"></a>Cómo utilizar el goteo del registro basado en fuente
  
1. Para habilitar el goteo del registro basado en fuente de las transacciones comerciales, vaya a **Administración del sistema > Configuración > Configuración de licencias** y deshabilita la clave **Extractos comerciales**.

2. En la misma página, habilite la clave de licencia **Extractos comerciales (fuente de goteo): versión preliminar**. Al habilitar esta clave, asegúrese de que no haya extractos pendientes en espera de registrarse. 

> [!Important]
> Antes de habilitar la clave de licencia **Extractos comerciales (fuente de goteo): versión preliminar**, asegúrese de que ninguno de los extractos pendientes están en espera de ser registrados.

3. El documento de extracto actual se dividirá en dos tipos diferentes: extracto transaccional e informe financiero.

      - El extracto transaccional recogerá todas las transacciones comerciales sin registrar y validadas, y creará pedidos de ventas, facturas de ventas, diarios de pagos y descuentos, así como transacciones de ingresos y gastos en la cadencia configurada. Debe configurar este proceso para su ejecución en una frecuencia alta de manera que se creen documentos cuando se carguen las transacciones comerciales en Retail Headquarters mediante el trabajo P. Con el extracto transaccional que ya crea pedidos de ventas y facturas de ventas, no es necesario realmente configurar el trabajo por lotes **Registrar inventario**. No obstante, puede seguir usándolo para cumplir los requisitos empresariales específicos que pueda tener.  
      
     - El informe financiero se ha diseñado para crearse al final del día y solo admite el método de cierre de **Turno**. Este informe se limitará a la conciliación financiera y solo creará los diarios para los importes de diferencia entre el importe contado y el importe de la transacción para las diferentes formas de pago, junto con los diarios para otras transacciones de administración de flujos de efectivo.   

4. Para calcular el extracto transaccional, haga clic en **Venta minorista > TI de venta minorista > Registro de PDV > Calcular extractos transaccionales por lotes**. Para registrar los extractos transaccionales por lotes, haga clic en **Venta minorista > TI de venta minorista > Registro de PDV > Registrar extractos transaccionales por lotes**.

5. Para calcular el informe financiero, haga clic en **Venta minorista > TI de venta minorista > Registro de PDV > Calcular informes financieros por lotes**. Para registrar los informes financieros por lotes, haga clic en **Venta minorista > TI de venta minorista > Registro de PDV > Registrar informes financieros por lotes**.

> [!NOTE]
> Los elementos de menú **Venta minorista > TI de venta minorista > Registro de PDV > Calcular extractos por lotes** y **Venta minorista > TI de venta minorista > Registro de PDV > Registrar extractos por lotes** se eliminan con esta nueva característica.

De manera alternativa, los tipos de informes financieros y transaccionales se pueden crear manualmente. Vaya a **Venta minorista > Canales > Tiendas** y haga clic en **Extractos comerciales**. Haga clic en **Nuevo** y, a continuación, elija el tipo de informe que desea crear. Los campos de la página **Extractos comerciales** y las acciones del **Grupo de extracto** de la página mostrarán datos pertinentes y acciones basadas en el tipo de extracto seleccionado.
