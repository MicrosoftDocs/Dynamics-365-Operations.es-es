---
title: Configurar códigos de disposiciones
description: Este procedimiento se centra en la configuración de un código de disposición que se puede utilizar en un dispositivo móvil para el proceso de recepción de pedidos de devolución.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSDispositionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d8eeba07aafbcbc327aa5e28a10d10c16b0e0f43
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236554"
---
# <a name="set-up-dispositions-codes"></a>Configurar códigos de disposiciones

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en la configuración de un código de disposición que se puede utilizar en un dispositivo móvil para el proceso de recepción de pedidos de devolución. Los códigos de disposición son una recopilación de reglas que se pueden usar cuando se reciben artículos. Por ejemplo, cuando un usuario usa un dispositivo móvil para recibir artículos dañados, el usuario debe escanear un código de disposición para artículos dañados. El estado de inventario de las mercancías recibidas, la plantilla de trabajo y la directiva de la ubicación se pueden determinar a partir del código de disposición escaneado. Para el proceso de recepción de pedido de compra y el informe de pedido de producción como proceso finalizado, es opcional usar un código de disposición. Para el proceso de recepción de devolución de pedido de ventas, si los artículos se registran mediante un dispositivo móvil, el uso del código de disposición es obligatorio.  Este procedimiento se creó con los datos de demostración de la empresa USMF. Este procedimiento va destinado al encargado de almacén. 

1. Vaya a Gestión de almacenes > Configurar > Dispositivo móvil > Códigos de disposición.
2. Haga clic en Nuevo.
    * Cree un nuevo código de disposición que usar para las devoluciones de los clientes.  
3. En el campo Código de disposición, escriba un valor.
4. En el campo Estado de inventario, seleccione un estado de inventario donde haya un bloqueo de inventario.
    * Si utiliza USMF, seleccione Bloqueo. Puede agregar un estado de inventario al código de disposición para anular el estado predeterminado que muestran las líneas de pedido.  
5. En el campo Plantilla de trabajo, escriba un valor.
    * Opcional: seleccione un código de plantilla de trabajo asociado a un pedido de devolución. Si no se proporciona ningún valor, la plantilla de trabajo se resolverá con las reglas estándar configuradas en su sistema. La selección de una plantilla de trabajo limitará los procesos con los que se puede usar este código de disposición. Por ejemplo, si un código de disposición tiene una plantilla de trabajo con un pedido de trabajo del tipo de pedido de compra, no puede usarse para registrar artículos devueltos por los clientes.  
6. En el campo Código de disposición de devolución, escriba un valor.
    * El código de disposición de devolución determina el resto del proceso del pedido de devolución para los artículos registrados. En este ejemplo, el cliente debe recibir una nota de abono. Agregue un código de disposición de devoluciones que contenga una acción de crédito.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]