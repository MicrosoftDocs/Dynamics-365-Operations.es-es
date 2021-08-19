---
title: Goteo en la creación de pedidos basados en fuente para transacciones de tienda
description: En este tema se describe el goteo de la creación de pedidos basados en fuente para las transacciones de tienda en Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 900480c926df58cc1eaca052903384ceeadcccbdc3a0ede8a35f4b2a8ff87556
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719450"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>Goteo en la creación de pedidos basados en fuente para transacciones de tienda

[!include [banner](includes/banner.md)]

En Dynamics 365 Retail versión 10.0.4 y anteriores, el registro del extracto es una operación de final del día y todas las transacciones se registran en los libros al final del día. Las transacciones grandes deben procesarse a continuación en una ventana de tiempo limitada, lo que a veces da lugar a errores de registro de extractos, carga y bloqueos. Los minoristas tampoco pueden reconocer ingresos y pagos en los libros durante todo el día.

Con el goteo de la creación de pedidos basados en fuente introducido en Retail versión 10.0.5, las transacciones se procesan durante todo el día y solo la conciliación financiera de formas de pago y otras transacciones de gestión de efectivo se procesan al final del día. Esta funcionalidad divide la carga de la creación de pedidos de ventas, facturas y pagos durante el día, ofreciendo el mejor rendimiento percibido y a la capacidad de reconocer ingresos y pagos en los libros casi en tiempo real. 


## <a name="how-to-use-trickle-feed-based-posting"></a>Cómo utilizar el goteo del registro basado en fuente
  
1. Para habilitar el goteo del registro basado en fuente de transacciones comerciales, habilite la característica denominada **Extractos comerciales - Fuente de goteo** utilizando la administración de características.

    > [!IMPORTANT]
    > Antes de habilitar la característica, asegúrese de que ningún extracto pendiente esté en espera de registrarse.

2. El documento de extracto actual se dividirá en dos tipos: extracto transaccional e informe financiero.

      - El extracto transaccional recogerá todas las transacciones sin registrar y validadas, y creará pedidos de ventas, facturas de ventas, diarios de pagos y descuentos, así como transacciones de ingresos y gastos en la cadencia configurada. Debe configurar este proceso para su ejecución en una frecuencia alta de manera que se creen documentos cuando se carguen las transacciones en Headquarters mediante el trabajo P. Con el extracto transaccional que ya crea pedidos de ventas y facturas de ventas, no es necesario realmente configurar el trabajo por lotes **Registrar inventario**. No obstante, puede seguir usándolo para cumplir los requisitos empresariales específicos que pueda tener.  
      
     - El informe financiero se ha diseñado para crearse al final del día y solo admite el método de cierre de **Turno**. Este informe se limitará a la conciliación financiera y solo creará los diarios para los importes de diferencia entre el importe contado y el importe de la transacción para las diferentes formas de pago, junto con los diarios para otras transacciones de administración de flujos de efectivo.   

3. Para calcular el extracto transaccional, vaya a **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Calcular extractos transaccionales por lotes**. Para registrar los extractos transaccionales por lotes, vaya a **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Registrar extractos transaccionales por lotes**.

4. Para calcular el informe financiero, vaya a **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Calcular informes financieros por lotes**. Para registrar los informes financieros por lotes, vaya a **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Registrar informes financieros por lotes**.

> [!NOTE]
> Los elementos de menú **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Calcular extractos por lotes** y **Retail y Commerce > TI de Retail y Commerce > Registro de PDV > Registrar extractos por lotes** se eliminan con esta nueva característica.

De manera alternativa, los tipos de informes financieros y transaccionales se pueden crear manualmente. Vaya a **Retail y Commerce > Canales > Tiendas** y haga clic en **Extractos**. Haga clic en **Nuevo** y, a continuación, elija el tipo de informe que desea crear. Los campos de la página **Extractos** y las acciones del **Grupo de extracto** de la página mostrarán datos pertinentes y acciones basadas en el tipo de extracto seleccionado.


[!INCLUDE[footer-include](../includes/footer-banner.md)]