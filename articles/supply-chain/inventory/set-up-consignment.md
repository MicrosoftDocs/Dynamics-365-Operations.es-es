---
title: Configuración de entrega
description: Este tema explica cómo configurar las operaciones de entrada de inventario de envío.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 51f7d6b0402ebbed417554978fc8d927f6b9c606
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207218"
---
# <a name="set-up-consignment"></a>Configuración de entrega

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar las operaciones de entrada de inventario de envío.

El inventario de envío es el inventario que es propiedad de un proveedor, pero se almacena en su ubicación. Cuando esté listo para consumir o usar el inventario, asume el control de la propiedad del inventario. Este tema describe la configuración necesaria para habilitar procesos de envío. Para obtener más información acerca de los procesos de envío, consulte [Configuración de entrega](consignment.md).

## <a name="inventory-owners"></a>Propietarios de inventario
Para registrar el inventario entrante físico de envío, es necesario definir un propietario de proveedor. Esto se hace en la página **Propietario de inventario**. Al seleccionar **Cuenta de proveedor** se generan valores predeterminados para los campos **Nombre** y **Propietario**. El valor del campo **Propietario** estará visible para el proveedor, por lo que es posible que desee cambiarlo si los nombres de cuenta de sus proveedores no son fáciles de reconocer por parte de las entidades externas. Es posible editar el campo **Propietario**, pero solo hasta el punto al guardar el registro **Propietario de inventario**. El campo **Nombre** se rellena con el nombre de la parte a la que se asocia la cuenta del proveedor y no se puede cambiar.

[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>Grupo de dimensiones de seguimiento
Los artículos que se van a usar en procesos de envío se deben asociar al **Grupo de dimensiones de seguimiento** donde la dimensión de **Propietario** está establecida en **Activa**. La dimensión de Propietario siempre tiene las opciones **Inventario físico** e **Inventario financiero** seleccionadas. El **Plan de cobertura por dimensión** nunca está seleccionado.

[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)

## <a name="inventory-ownership-change-journal"></a>Diario de cambio de propiedad de inventario
El diario de **Cambio de propiedad de inventario**se usa para registrar la transferencia de propiedad del inventario de envío del proveedor a la entidad jurídica que lo consume. Como cualquier diario de inventario, debe identificarse con un nombre de diario de inventario. Dichos nombres se crean en la página **Nombres de diario de inventario**, y el **Tipo de diario** se debe establecer en **Cambio de propiedad**.

[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Colaboración de proveedor en procesos de envío
Si los proveedores usan la interfaz de colaboración de proveedor, pueden usarla para controlar el consumo de inventario de su ubicación. Para obtener más información acerca de la configuración de los proveedores para utilizar la colaboración de proveedor, consulte [Seguridad para los usuarios del portal de proveedores](../procurement/configure-security-vendor-portal-users.md).
