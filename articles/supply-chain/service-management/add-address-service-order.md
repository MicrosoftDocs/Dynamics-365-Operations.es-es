---
title: Agregar una dirección a un pedido de servicio
description: Este tema describe cómo agregar una dirección de cliente a un pedido de servicio.
author: ShylaThompson
manager: tfehr
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6c8f00eb1a1fe2ef3aea22da20ce218d7568f64
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966064"
---
# <a name="add-an-address-to-a-service-order"></a>Agregar una dirección a un pedido de servicio    

[!include [banner](../includes/banner.md)]


Este tema describe cómo agregar una dirección de cliente a un pedido de servicio. Al crear un pedido de servicio, la información de dirección se transfiere del proyecto al que está vinculado el pedido de servicio. Sin embargo, puede seleccionar una ubicación alternativa a las direcciones que ya haya especificado en Microsoft Dynamics AX para clientes, proveedores, sitios, almacenes, pedidos de servicio y proyectos.

También puede crear una nueva dirección. De forma predeterminada, la nueva dirección se transfiere al proyecto. Sin embargo, puede especificar que la nueva dirección solo sea pertinente para esta instancia del servicio. Si lo hace, la nueva dirección no se transfiere al proyecto.

## <a name="create-a-customer-address-for-a-service-order"></a>Crear una dirección de cliente para un pedido de servicio

Para agregar una dirección a un pedido de servicio, siga estos pasos:

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.

2.  Abra el pedido de servicio para el que desea crear una dirección.

3.  En el **panel de acciones**, haga clic en **Editar** y, a continuación, haga clic en la **Visualización de encabezado**.

4.  En la ficha desplegable **Dirección**, haga clic en **Agregar dirección**.

5.  En el formulario **Dirección nueva**, especifique un nombre exclusivo para la dirección y complete los campos restantes. 
    

    > [!WARNING]
    > <P>Si especifica el mismo nombre que una dirección existente, la información que especifique en los campos restantes sobrescribirá la información de la dirección existente.</P>


6.  Haga clic en **Aceptar** para copiar la nueva dirección al pedido de servicio.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Especificar una dirección alternativa en un pedido de servicio

Para agregar una dirección alternativa a un pedido de servicio, siga estos pasos:

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.

2.  Abra el pedido de servicio para el que especificar una dirección alternativa.

3.  En el **panel de acciones**, haga clic en **Editar** y, a continuación, haga clic en la **Visualización de encabezado**.

4.  En la ficha desplegable **Dirección**, haga clic en **Otra dirección**.

5.  En el formulario **Selección de dirección**, en el campo **Tipo de registro**, seleccione **Pedidos de servicio**.

6.  Seleccione una dirección y haga clic en **Aceptar** para copiarla en el pedido de servicio.


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]