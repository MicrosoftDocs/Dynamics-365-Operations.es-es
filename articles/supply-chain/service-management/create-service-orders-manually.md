---
title: Crear pedidos de servicio manualmente
description: Es posible crear pedidos de servicio manualmente mediante un acuerdo de servicio o mediante el formulario **Pedidos de servicio**.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 51cfdb94a368df9e7082af3c768c79df44000342
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978734"
---
# <a name="create-service-orders-manually"></a>Crear pedidos de servicio manualmente    

[!include [banner](../includes/banner.md)]


Es posible crear pedidos de servicio manualmente mediante un acuerdo de servicio o mediante el formulario **Pedidos de servicio**. También podrá crear un pedido de servicio a partir de un proyecto.

> [!TIP]
> <P>Puede utilizar procesos automatizados para crear pedidos de servicio. 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a>Crear un pedido de servicio manualmente a partir de un acuerdo de servicio

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.

2.  Seleccione un acuerdo de servicio o cree uno nuevo.

3.  Haga clic en la pestaña **Entregar** y en el grupo **Crear** haga clic en **Pedidos de servicio planificados** para abrir el formulario **Crear pedidos de servicio**.

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a>Crear un pedido de servicio manualmente en el formulario de pedidos de servicio

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.

2.  Presione Ctrl+N para crear un nuevo pedido de servicio.

3.  Cree las líneas del pedido de servicio para el pedido.

> [!NOTE]
> <P>Si la casilla de verificación <STRONG>Permitir sin acuerdo de servicio</STRONG> del formulario <STRONG>Parámetros de la gestión de servicio</STRONG> está activada, podrá registrar las transacciones desde las líneas del pedido de servicio sin adjuntar el pedido de servicio a un acuerdo de servicio. Si la casilla de verificación no está marcada, deberá adjuntar el pedido de servicio creado manualmente a un proyecto antes de registrar las líneas del pedido de servicio.</P>

## <a name="create-a-service-order-from-a-project"></a>Crear un pedido de servicio desde un proyecto

1.  Haga clic en **Gestión de proyectos y contabilidad** \> **Común** \> **Proyectos** \> **Todos los proyectos**.

2.  En el formulario **Proyectos**, en el **Panel Acciones**, haga clic en la pestaña **Administrar** \> y luego en **Servicio** \> **Pedidos de servicio**.

3.  Siga el procedimiento anterior para crear un pedido de servicio manualmente en el formulario **Pedidos de Servicio**. El campo **Id. de proyecto** muestra la referencia del proyecto.

> [!NOTE]
> <P>Si la casilla de verificación <STRONG>Permitir sin acuerdo de servicio</STRONG> del formulario <STRONG>Parámetros de la gestión de servicio</STRONG> está activada, podrá registrar las transacciones desde las líneas del pedido de servicio sin adjuntar el pedido de servicio a un acuerdo de servicio. Si la casilla de verificación no está marcada, deberá adjuntar el pedido de servicio creado manualmente a un proyecto antes de registrar las líneas del pedido de servicio.</P>

## <a name="create-a-service-order-from-the-sales-order-form"></a>Crear un pedido de servicio desde el formulario de pedido de ventas

Puede crear un pedido de servicio desde el formulario **Pedidos de ventas** mediante el asistente **Crear un nuevo pedido de servicio basado en el pedido de ventas**.

1.  Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de ventas** \> **Todos los pedidos de ventas**.

2.  Abra el pedido de ventas pertinente.

3.  En la pestaña **pedido de ventas**, haga clic en **Pedido de servicio** para iniciar el asistente **Crear un nuevo pedido de servicio basado en el pedido de ventas**.

4.  Haga clic en **Siguiente \>**, y ejecute los pasos siguientes en la página **Seleccionar acuerdo para pedido de servicio**:
    
      - Use el campo **Acuerdo de servicio** para seleccionar el acuerdo de servicio al que desea asociar el pedido de servicio nuevo.
    
      - Opcional: use el campo **Id. de proyecto** para asociar este pedido de servicio a un proyecto particular.

5.  Haga clic en **Siguiente \>**, y ejecute los pasos siguientes en la página **Crear pedido de servicio**:
    
      - Especifique una fecha y una hora de inicio para la llamada de servicio en el campo **Hora de servicio preferida**.
    
      - Opcional: modifique el texto en el campo **Descripción**. De forma predeterminado, este campo contiene la descripción del acuerdo de servicio que seleccionó en la página anterior.
    
      - En el campo **Responsable**, seleccione el identificador del empleado responsable del contrato, y si lo conoce, especifique el identificador del técnico preferido del cliente para la llamada de servicio.
    
      - En el campo **Id. de contacto**, seleccione la persona de la empresa del cliente con la que se debe poner en contacto en relación con este pedido de servicio.

6.  Haga clic en **Siguiente\>** y, a continuación, haga clic en **Finalizar**.


## <a name="see-also"></a>Consulte también

[Pedidos de servicio](service-orders.md)

[Crear pedidos de servicio automáticamente](create-service-orders-automatically.md)

[Crear pedidos de servicio (formulario de clase)](https://technet.microsoft.com/library/aa553901\(v=ax.60\)) 

