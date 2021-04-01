---
title: Garantías de activos y tipos de activos
description: Este tema explica cómo configurar garantías de activos y tipos de activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 78ac93b1e681fca7d7eefd921f282a8496aa9d0a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245332"
---
# <a name="warranties-on-assets-and-asset-types"></a>Garantías de activos y tipos de activos

[!include [banner](../../includes/banner.md)]

 


Este tema explica cómo configurar garantías de activos y tipos de activos en Administración de activos.

## <a name="set-up-a-warranty-on-an-asset-type"></a>Configuración de una garantía de un tipo de activo

1. Seleccione **Administración de activos** \> **Configuración** \> **Tipos de activos** \> **Tipos de activos**.
2. En el panel izquierdo, seleccione el tipo de activo al que vincular un acuerdo de la garantía de proveedor y, a continuación seleccione **Valores predeterminados de tipo de activo**.
3. En la ficha desplegable **General**, en el campo **Garantía de proveedor**, seleccione el acuerdo.

## <a name="set-up-a-warranty-on-an-asset"></a>Configuración de una garantía de un activo

1. Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos**.
2. Seleccione el activo y, a continuación, seleccione **Editar**.
3. En la ficha desplegable **Proveedor**, en la sección **Garantía del proveedor**, en el campo **Garantía**, seleccione el contrato de la garantía.
4. En los campos **Inicio de la garantía** y **Fin de la garantía**, seleccione las fechas inicial y final.

    > [!IMPORTANT]
    > Si una fecha se selecciona en el campo **Inicio de la garantía** en un pedido de trabajo, la garantía empezará a ser válida para la orden de trabajo en esa fecha. Al crear un pedido de trabajo, el campo **Inicio de la garantía** se establece automáticamente en la fecha de creación. Sin embargo, puede cambiar la fecha de modo que corresponda a, por ejemplo, la fecha inicial de un acuerdo de la garantía.
    >
    > ![Página Orden de trabajo](media/02-warranty.png)

> [!NOTE]
> Al crear un pedido de trabajo para un activo cubierto por una garantía del proveedor, si la orden de trabajo tiene una fecha de inicio prevista durante el período de garantía, usted recibirá una notificación sobre el acuerdo de la garantía. En ese momento podrás cancelar la orden de trabajo, como sea necesario.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]