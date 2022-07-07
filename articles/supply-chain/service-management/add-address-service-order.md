---
title: Agregar una dirección a un pedido de servicio
description: Este artículo describe cómo agregar una dirección de cliente a un pedido de servicio.
author: sorenva
ms.date: 06/15/2020
ms.topic: article
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c485c50bab7c2e945aa0f0fc0601008dcebd3328
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015736"
---
# <a name="add-an-address-to-a-service-order"></a>Agregar una dirección a un pedido de servicio

[!include [banner](../includes/banner.md)]

Este artículo describe cómo agregar una dirección de cliente a un pedido de servicio. Al crear un pedido de servicio, la información de dirección se transfiere del proyecto al que está vinculado el pedido de servicio. Sin embargo, puede seleccionar una ubicación alternativa a las direcciones que ya haya especificado en Microsoft Dynamics AX para clientes, proveedores, sitios, almacenes, pedidos de servicio y proyectos.

También puede crear una nueva dirección. De forma predeterminada, la nueva dirección se transfiere al proyecto. Sin embargo, puede especificar que la nueva dirección solo sea pertinente para esta instancia del servicio. Si lo hace, la nueva dirección no se transfiere al proyecto.

## <a name="create-a-customer-address-for-a-service-order"></a>Crear una dirección de cliente para un pedido de servicio

Para agregar una dirección a un pedido de servicio, siga estos pasos:

1. Vaya a **Gestión de servicio** \> **Pedidos de servicio** \> **Pedidos de servicio**.

1. Abra el pedido de servicio para el que desea crear una dirección.

1. Abra la pestaña **Encabezado**.

1. Amplíe la ficha desplegable **Dirección** y seleccione **Añadir dirección** desde la barra de herramientas de la ficha desplegable.

1. En el cuadro de diálogo **Dirección nueva**, especifique un nombre exclusivo para la dirección y complete los campos restantes. 

    > [!WARNING]
    > Si especifica el mismo nombre que una dirección existente, la información que especifique en los campos restantes sobrescribirá la información de la dirección existente.

1. Seleccione **Aceptar** para copiar la nueva dirección al pedido de servicio.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Especificar una dirección alternativa en un pedido de servicio

Para agregar una dirección alternativa a un pedido de servicio, siga estos pasos:

1. Vaya a **Gestión de servicio** \> **Pedidos de servicio** \> **Pedidos de servicio**.

1. Abra el pedido de servicio para el que especificar una dirección alternativa.

1. Abra la pestaña **Encabezado**.

1. Amplíe la ficha desplegable **Dirección** y seleccione **Otra dirección** desde la barra de herramientas de la ficha desplegable.

1. En el cuadro de diálogo **Selección de dirección**, seleccione **Pedidos de servicio** desde la lista desplegable que está encima de la cuadrícula.

1. Seleccione una dirección y seleccione **Aceptar** para copiarla en el pedido de servicio.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]