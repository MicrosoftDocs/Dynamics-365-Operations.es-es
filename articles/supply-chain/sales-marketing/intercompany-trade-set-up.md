---
title: Configurar el comercio de empresas vinculadas
description: En este tema se explica cómo configurar el comercio de empresas vinculadas
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage, InterCompanyTradingRelationSetupCustomer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 5080267568f4d0626d2c727efb533295e7d8e397
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669415"
---
# <a name="set-up-intercompany-trade"></a>Configurar el comercio de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Para permitir que Microsoft Dynamics 365 Supply Chain Management haga negocios entre empresas vinculadas, debe configurar los clientes y proveedores hacer negocios entre empresas vinculadas. También debe configurar los proveedores, clientes, compras y abastecimiento, y las ventas y marketing.

## <a name="before-you-set-up-intercompany-trade"></a>Antes de configurar negocios entre empresas vinculadas

Antes de configurar negocios entre empresas vinculadas, debe decidir qué clientes son clientes de empresas vinculadas y qué proveedores son de proveedores de empresas vinculadas. Para cada entidad jurídica en Microsoft Dynamics 365 Supply Chain Management, debe decidir qué directiva comercial se aplicará a la relación comercial de empresas vinculadas con el cliente o proveedor de empresas vinculadas específicas.

Concretamente, se recomienda que usted y su organización se familiaricen con los parámetros de empresas vinculadas.

- Discuta las consecuencias de la configuración con los directores responsables de negocios entre empresas vinculadas en cada entidad jurídica.
- Configure valores adecuados para cada entidad jurídica.

## <a name="set-up-trading-relations"></a>Configurar relaciones comerciales

Para configurar negocios de empresas vinculadas para clientes y proveedores, siga estos pasos.

1. Vaya a **Clientes \> Clientes \> Todos los clientes**.
1. Seleccionar una cuenta de cliente.
1. En el panel de acciones, en la pestaña **General**, seleccione **Empresas vinculadas**.
1. Especifique los parámetros de configuración de empresas vinculadas para la cuenta de cliente. Estos parámetros incluyen la entidad jurídica que contiene el proveedor correspondiente y la cuenta del proveedor. Los parámetros también incluyen las directivas de pedido de compra, las directivas de pedido de ventas, la asignación de valores y las directivas para los acuerdos de venta y los acuerdos de compra. También especificará si desea utilizar los valores de los datos base de la cuenta del cliente o de la cuenta del proveedor en la otra entidad jurídica.
1. Repita los pasos 1 a 4 para los clientes de empresas vinculadas restantes en la entidad jurídica.
1. Vaya a **Proveedores \> Proveedores \> Todos los proveedores**.
1. Seleccione una cuenta de proveedor.
1. En el panel de acciones, en la pestaña **General**, seleccione **Empresas vinculadas**.
1. Especifique los parámetros de configuración de empresas vinculadas para la cuenta de proveedor. Estos parámetros incluyen la entidad jurídica que contiene el clientes y la cuenta del clientes correspondientes. Los parámetros también incluyen las directivas de pedido de compra, las directivas de pedido de ventas, la asignación de valores y las directivas para los acuerdos de venta y los acuerdos de compra. También especificará si desea utilizar los valores de los datos base de la cuenta del proveedor o de la cuenta del cliente en la otra entidad jurídica.
1. Repita los pasos 6 a 9 para los proveedores de empresas vinculadas restantes en la entidad jurídica.

## <a name="set-up-products"></a>Configurar productos

Para configurar negocios de empresas vinculadas para clientes y proveedores, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Todos los productos y productos maestros**.
1. Definir productos emitidos a las entidades jurídicas en las que desea realizar el negocio entre empresas vinculadas.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
