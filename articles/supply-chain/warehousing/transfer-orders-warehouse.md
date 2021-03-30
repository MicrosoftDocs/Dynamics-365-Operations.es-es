---
title: Configuración de almacenes para pedidos de transferencia
description: Este tema describe cómo puede configurar los almacenes para pedidos de transferencia.
author: Mirzaab
manager: tfehr
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: e01629982bb383078e90ff3dad0592371f44bd1b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206856"
---
# <a name="set-up-warehouses-for-transfer-orders"></a>Configuración de almacenes para pedidos de transferencia 

[!include [banner](../includes/banner.md)]

Puede utilizar niveles de almacén para crear una jerarquía que admita pedidos de transferencia entre almacenes. En función de esta configuración, la programación maestra calcula los requisitos de artículos a nivel de almacén individual y genera pedidos de transferencia planificados desde un almacén de origen asignado para cumplirlos.

1.  Haga clic en **Gestión del inventario> Configuración > Desglose del inventario > Almacenes**

2.  Seleccione el almacén que desee reabastecer.

3.  En la ficha desplegable **Planificación maestra**, seleccione la casilla **Reabastecimiento**.

4.  En el campo **Almacén principal**, seleccione el almacén que desee asignar como almacén de reabastecimiento. La programación maestra calcula un requisito de transferencia para el almacén seleccionado y genera un pedido de transferencia planificado desde el **Almacén principal** asignado.
   
    > [!NOTE]
    > <P>Si deja el campo <STRONG>Reabastecimiento</STRONG> en blanco, se asigna al almacén seleccionado un nivel de almacén en relación con el <STRONG>Almacén principal</STRONG>, pero no se define el <STRONG>Almacén principal</STRONG> como almacén de reabastecimiento.</P>

5.  Cierre la página para aplicar la nueva configuración.


> [!TIP]
> <P>Si desea asignar un almacén para reabastecimiento, en primer lugar debe configurar el almacén como una dimensión de almacenamiento en el formulario <STRONG>Grupos de dimensiones de almacenamiento</STRONG>. En esta página, seleccione el campo <STRONG>Activo</STRONG> y el campo <STRONG>Plan de cobertura por dimensión</STRONG> para el almacén.</P>

## <a name="set-up-transport-lead-time"></a>Configuración del plazo de transporte

También debe configurar el plazo de transporte entre los almacenes en la página **Días de transporte**. 
1. Vaya a **Administración de inventario > configuración > distribución > días de transporte**.
2. En el campo **Punto de recepción**, seleccione **almacén**.
3. Seleccione **Almacén de envío**, **Almacén de recepción** y **Días de transporte**. 
4. (opcional) También puede establecer el tiempo de transporte, en función del modo de entrega, en la pestaña **Días de transporte por modo de entrega**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]