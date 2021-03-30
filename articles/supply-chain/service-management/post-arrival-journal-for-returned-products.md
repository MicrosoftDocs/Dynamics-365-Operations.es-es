---
title: Registrar diario de llegadas para productos devueltos
description: Registrar diario de llegadas para productos devueltos.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14619069c0e984060f67fc4536b311c6802bfec7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214307"
---
# <a name="post-arrival-journal-for-returned-products"></a>Registrar diario de llegadas para productos devueltos 

[!include [banner](../includes/banner.md)]


Para procesar una devolución, primero valide la cantidad de devolución y actualice el campo de cantidad en el diario de recepción de artículos. A continuación, seleccione un código de disposición o indique que los artículos devueltos tienen que inspeccionarse. Cuando haya completado estos pasos, puede registrar el diario de llegadas de artículos del pedido de devolución.

1.  Haga clic en **Gestión del inventario** \> **Periódico** \> **Visión general de llegadas**.

2.  En el filtro **Configurar nombre** , seleccione **Pedido de devolución**.

3.  Si la lista de recepciones es larga, utilice los campos del área **Intervalo** para limitar la lista.

4.  Localice la línea del pedido de devolución que desea registrar, seleccione el cuadro **Seleccionar para llegada** y, a continuación, haga clic en **Iniciar llegada**.

5.  Haga clic en **Diarios** \> **Mostrar llegadas a partir de recepciones** para abrir el formulario **Diario de ubicaciones**.
    

    > [!TIP]
    > <P>Para ver información detallada, seleccione un diario y, a continuación, haga clic en <STRONG>Líneas</STRONG>.</P>


6.  Realice las actualizaciones necesarias y haga clic en **Registrar**.

Una vez registrado el diario, se registran los artículos devueltos en el inventario y el formulario **Pedidos de devolución** indica que los artículos han llegado al almacén.

## <a name="see-also"></a>Consulte también

[Diario de ubicaciones (formulario)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]