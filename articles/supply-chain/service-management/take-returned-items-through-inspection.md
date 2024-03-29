---
title: Inspeccionar artículos devueltos
description: Inspeccionar artículos devueltos.
author: sorenva
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41214663ec48a8cbcd8bec7f6801adb4311b2373
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669947"
---
# <a name="take-returned-items-through-inspection"></a>Inspeccionar artículos devueltos 

[!include [banner](../includes/banner.md)]


1.  Haga clic en **Gestión del inventario** \> **Periódico** \> **Administración de calidad** \> **Órdenes de cuarentena**.

2.  Localice la línea de pedido que corresponde al artículo devuelto que va a inspeccionar.

    > [!NOTE]
    > <P>Las órdenes de cuarentena solo pueden estar asociadas a un número de artículo. Si se devuelven 10 artículos con números de artículos diferentes en un solo envío y se envían a cuarentena, se crearán 10 órdenes de cuarentena individuales.</P>

3.  Después de examinar el artículo, realice una selección en el campo **Código de disposición** para indicar qué acción debe tomarse con el artículo y cómo deberá gestionarse la transacción financiera relacionada. Por ejemplo, las acciones incluyen la devolución del artículo al inventario y el reembolso al cliente, dar de baja el artículo y enviar un reemplazo al cliente o devolver el artículo al cliente sin crédito.
    
    > [!NOTE]
    > <P>En caso de que no se pueda asignar el mismo código de disposición a varios artículos devueltos de un solo lote de números de artículo, debe dividir la orden de cuarentena (<STRONG>Funciones</STRONG> &gt; <STRONG>Dividir</STRONG>) para poder asignar un código de disposición diferente a cada sublote.</P>


4.  Una vez finalizada la inspección, haga clic en **Notificar como terminado** para liberar los artículos devueltos y crear una entrada del diario de recepción de artículos. La persona o el departamento que recibe los artículos procesará el diario de los artículos que se devuelvan al inventario.
    
    O bien
    
    Finalice la orden de cuarentena y mueva los artículos al inventario directamente mediante una de las funciones del botón **Inventario**.

5.  Cierre el formulario para guardar los cambios.

## <a name="see-also"></a>Consulte también

[Especificar la disposición de artículos devueltos](specify-how-to-dispose-of-returned-items.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]