---
title: Configurar las denominaciones de efectivo para el punto de venta (POS)
description: Cobre denominaciones en las notas y las divisas se pueden definir en back office que se usará en los cajeros, socios de ventas, y los administradores en el almacén dentro de Retail POS.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 24775044e5a502a5615392a6a8c4030bdfafb0ab
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "343521"
---
# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a>Configurar las denominaciones de efectivo para el punto de venta (POS)

[!include [banner](includes/banner.md)]

Cobre denominaciones en las notas y las divisas se pueden definir en back office que se usará en los cajeros, socios de ventas, y los administradores en el almacén dentro de Retail POS. Estas denominaciones se pueden usar para ayudar a contar el efectivo al final del día o para rápidamente obtener una venta.

## <a name="define-denominations"></a>Especificar  denominaciones

Las denominaciones se configuran por almacén en la página **Configurar** \> **Opción de la declaración de efectivo de la propiedad de la tienda**.

![Denominaciones de efectivo](./media/image1-denomination.png)

Definir denominaciones

1. Haga clic en **Nuevo**.
1. Especifique el tipo (moneda o billete).
1. Especifique el importe (valor).

![Denominaciones de efectivo](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a>Configure el perfil de funcionalidad.

Al pagar en efectivo mediante PDV, el usuario puede usar las denominaciones de la nota para especificar rápidamente el importe pagado el cliente. En el perfil de funcionalidad, puede configurar las dos opciones para mostrar la denominación en el sistema PDV.

- **Mayor o igual al importe debido**: De forma predeterminada, el sistema PDV solo mostrará las denominaciones de la nota que sean mayores que el importe debido, lo que permite la venta a un toque. Por ejemplo, si el importe debido es 7,50$, el sistema PDV mostraría las siguientes denominaciones: 10$, 20$ y 100$. Al tocar en cualquiera de estos importes automáticamente ofrecerá la venta por dicho importe. Los billetes de 1$ y 5$ no se muestran ya que estos importes son inferiores al importe debido.
- **Todas las denominaciones**: Seleccione esta opción para mostrar siempre todas las denominaciones de nota en el PDV, independientemente del importe debido. Esto significa que el usuario puede usar una combinación de notas para lograr el importe debido. Por ejemplo, si el importe debido es 25,00$, el usuario puede elegir 20$ y 5$ para completar la venta.
