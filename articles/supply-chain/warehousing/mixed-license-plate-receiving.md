---
title: Recepción de matrícula de entidad de almacén mixta
description: Este artículo describe cómo usar la recepción de matrícula mixta para registrar y para crear trabajo para varios artículos con un dispositivo móvil.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 76ba316a5ed55902aed35acb4ef21623c7676b38
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907069"
---
# <a name="mixed-license-plate-receiving"></a>Recepción de matrícula de entidad de almacén mixta

[!include [banner](../includes/banner.md)]

La recepción de matrículas mixtas le permite generar una matrícula que consiste en varios artículos antes de registrar y crear un trabajo de ubicación. 

Una matrícula que consiste de varios artículos no tiene que dividirse en el muelle recepción para que pueda registrar cada artículo. 

Al usar un flujo relacionado con artículos para identificar las líneas del documento de origen, puede digitalizar códigos de barras en el control de artículos. Si el código de barras tiene una cantidad y una unidad de medida (UOM) configurada en él, el artículo y la cantidad automáticamente se agregarán a la matrícula mixta y que volverá a la pantalla para escanear otro artículo. Esto le permite digitalizar rápidamente todos los artículos sin tener que crear una confirmación en cada paso. 

En el flujo para la recepción de matrículas mixtas, puede mostrar la lista de artículos que ya se han digitalizado para la matrícula y a partir de ahí puede modificar o corregir la cantidad de un artículo.

## <a name="where-it-applies"></a>Dónde se aplica

La recepción de matrículas es un dispositivo móvil que recibe flujo para registrar y crear trabajo para varios artículos o líneas al mismo tiempo. Esto resulta útil si recibe matrículas de entrada con varios artículos. 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a>Cómo configurar la recepción de matrículas mixtas
La recepción de matrículas mixtas se establece como un elemento de menú del dispositivo móvil.

Es necesario crear un nuevo elemento de menú en modo trabajo que no utilice el trabajo existente y use los métodos siguientes:

- Recepción de matrícula de entidad de almacén mixta
- Recepción de matrícula de entidad de almacén mixta y ubicación

Las opciones para identificar las líneas de documento de origen son artículos de pedidos de compra, línea de pedido de compra, pedido de devolución, artículo de pedido de transferencia y línea de pedido de transferencia. Estas opciones pueden cambiar el pedido de recepción en una sola matrícula. La última opción es cargar artículos. Puede agregar varios artículos a una matrícula, pero no puede alternar entre las varias cargas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]