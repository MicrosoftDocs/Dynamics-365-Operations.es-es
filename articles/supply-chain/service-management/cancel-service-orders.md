---
title: Cancelar pedidos de servicio
description: Puede cancelar un pedido de servicio o línea de pedido de servicio desde el propio pedido o cancelar varios pedidos de servicio mediante un trabajo periódico.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 228b76d6f6f0bb048662c8e82df76f51b7cb3652
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017387"
---
# <a name="cancel-service-orders"></a>Cancelar pedidos de servicio   

[!include [banner](../includes/banner.md)]


Puede cancelar un pedido de servicio o línea de pedido de servicio desde el propio pedido o cancelar varios pedidos de servicio mediante un trabajo periódico.


> [!NOTE]
> <P>Los pedidos de servicio no se pueden cancelar si la etapa del pedido de servicio no permite la cancelación, si el pedido de servicio tiene requisitos de artículos o si el pedido de servicio ya se ha registrado.</P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a>Cancelar un pedido de servicio desde el formulario Pedidos de servicio

1.  Haga clic en **Gestión de servicio** \> **Pedidos de servicio** \> **Pedidos de servicio**. Seleccione el pedido de servicio y haga clic en **Cancelar pedido** en el panel de acciones.

## <a name="cancel-a-service-order-line"></a>Cancelar una línea de pedido de servicio

1.  Haga clic en **Gestión de servicio** \> **Pedidos de servicio** \> **Pedidos de servicio**. Haga doble clic en el pedido de servicio que contiene la línea que desee cancelar.

2.  Seleccione la línea del pedido de servicio que desea cancelar y, a continuación, haga clic en **Cancelar línea de pedido** para cambiar el estado de la línea a **Cancelado**.


> [!TIP]
> <P>Para invertir la cancelación de una línea de pedido de servicio y volver a cambiar el estado a <STRONG>Creada</STRONG>, haga clic en <STRONG>Revocar cancelación</STRONG>.</P>


## <a name="cancel-multiple-service-orders"></a>Cancelación de varios pedidos de servicio

1.  Haga clic en **Gestión de servicio** \> **Periódico** \> **Pedidos de servicio** \> **Cancelar pedidos de servicio**.

2.  Haga clic en el botón **Seleccionar**.

3.  En el formulario **Consulta**, en la columna **Criterios**, seleccione los pedidos de servicio que desee cancelar.

4.  Haga clic en **Aceptar** para cerrar el formulario **Consulta**.

5.  Active la casilla **Mostrar registro de información** para generar un registro de información con los pedidos de servicio cancelados.

6.  Active la casilla **Revocar cancelación** para invertir el estado **Cancelado** de un pedido de servicio.

7.  Haga clic en **Aceptar**.

Los pedidos de servicio seleccionados se cancelarán o su estado de progreso de **Cancelado** se ha invertido a **En proceso**.


> [!NOTE]
> <P>Si activa la casilla <STRONG>Revocar cancelación</STRONG>, los pedidos de servicio con el estado de progreso <STRONG>Cancelado</STRONG> se invertirán y no se producirá ninguna cancelación de pedidos de servicio con el estado <STRONG>En proceso</STRONG>.</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]