---
title: Garantías de activos y tipos de activos
description: Este artículo explica cómo configurar garantías de activos y tipos de activos en Administración de activos.
author: johanhoffmann
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2e63161aa32ecbc99baace9bb0cc649aedc600ed
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016003"
---
# <a name="warranties-on-assets-and-asset-types"></a>Garantías de activos y tipos de activos

[!include [banner](../../includes/banner.md)]

 


Este artículo explica cómo configurar garantías de activos y tipos de activos en Administración de activos.

## <a name="set-up-a-warranty-on-an-asset-type"></a>Configuración de una garantía de un tipo de activo

1. Seleccione **Administración de activos** \> **Configuración** \> **Tipos de activos** \> **Tipos de activos**.
2. En el panel izquierdo, seleccione el tipo de activo al que vincular un acuerdo de la garantía de proveedor y, a continuación seleccione **Valores predeterminados de tipo de activo**.
3. En la ficha desplegable **General**, en el campo **Garantía de proveedor**, seleccione el acuerdo.

## <a name="set-up-a-warranty-on-an-asset"></a>Configuración de una garantía de un activo

1. Seleccione **Administración de activos** \> **Activos** \> **Todos los activos**.
2. Seleccione el activo y, a continuación, seleccione **Editar**.
3. En la ficha desplegable **Proveedor**, en la sección **Garantía del proveedor**, en el campo **Garantía**, seleccione el contrato de la garantía.
4. En los campos **Inicio de la garantía** y **Fin de la garantía**, seleccione las fechas inicial y final.

    > [!IMPORTANT]
    > Si una fecha se selecciona en el campo **Inicio de la garantía** en un pedido de trabajo, la garantía empezará a ser válida para la orden de trabajo en esa fecha. Al crear un pedido de trabajo, el campo **Inicio de la garantía** se establece automáticamente en la fecha de creación. Sin embargo, puede cambiar la fecha de modo que corresponda a, por ejemplo, la fecha inicial de un acuerdo de la garantía.
    >
    > ![Página Orden de trabajo.](media/02-warranty.png)

> [!NOTE]
> Al crear un pedido de trabajo para un activo cubierto por una garantía del proveedor, si la orden de trabajo tiene una fecha de inicio prevista durante el período de garantía, usted recibirá una notificación sobre el acuerdo de la garantía. En ese momento podrás cancelar la orden de trabajo, como sea necesario.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]