---
title: Principios de reducción de devolución
description: Este tema describe cómo configurar principios de reducción. Los principios de reducción controlan el comportamiento cuando se aplican múltiples devoluciones al mismo artículo o transacción.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: f586e0f40b5362510333263a985eada39d3c53f5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020375"
---
# <a name="rebate-reduction-principles"></a>Principios de reducción de devolución

[!include [banner](../includes/banner.md)]

Puede agrupar acuerdos de gestión de devoluciones en *principios de reducción* para reducir otras provisiones que están asociadas con un artículo, y / o para reducir los valores resultantes de los cálculos de rebajas. Una vez configurados los principios de reducción de devoluciones, puede asignarlos opcionalmente, según sea necesario, a las líneas de sus acuerdos de gestión de devoluciones.

Las reglas del principio de reducción de devoluciones se aplican solo cuando los acuerdos de devoluciones se superponen. Por lo tanto, pueden otorgar múltiples reembolsos en situaciones en las que no se adeuden múltiples devoluciones.

## <a name="manage-rebate-reduction-principles"></a>Administrar principios de reducción de devolución

Para trabajar con los principios de reducción de devoluciones, vaya a **Gestión de devoluciones \> Configuración \> Principios de reducción de devoluciones**. Entonces use los botones del Panel de acciones para agregar y quitar principios de reducción según sea necesario. Por cada principio, configure los campos como se describe en la siguiente tabla.

| Campo | Descripción |
|---|---|
| Principio de reducción de devolución | Introduzca un nombre exclusivo para el principio de reducción de devoluciones. |
| Descripción | Introduzca una descripción para el principio de reducción de devoluciones. |
| Aplicar reducción | Seleccione esta casilla de verificación para aplicar una base de reducción a las devoluciones que pertenecen a este principio de reducción de devoluciones. |
| Base de reducción | Si seleccionó la casilla de verificación **Aplicar reducción**, seleccione la base de reducción (*Provisión*, *Devoluciones*, o *Ambas cosas*). Si selecciona *Ambas cosas*, y si se han registrado tanto una provisión como una devolución para un acuerdo anterior, solo se aplicará la devolución. |
| Excluir de la reducción | Si se selecciona esta casilla de verificación, las provisiones y devoluciones que pertenecen a este principio de reducción de devoluciones se excluirán de las reducciones posteriores. La configuración del campo **Base de reducción** no se aplica a esta configuración. |

## <a name="examples-of-rebate-reduction-principle-setups"></a>Ejemplos de configuraciones del principio de reducción de devoluciones

La siguiente tabla muestra algunos ejemplos típicos de configuraciones del principio de reducción de devoluciones. Para cada uno de estos principios de reducción de devoluciones, el valor del campo **Descripción** describe el propósito del principio de reducción de devoluciones.

| principio de reducción de devolución | Descripción | Aplicar reducción | Base de reducción | Excluir de la reducción |
|---|---|---|---|---|
| Aplazado | Reducir devolución | Sí | Ambas | N.º |
| Exclreb | Excluir devolución | Sí | Devolución | Sí |
| Varias | Múltiples devoluciones | Sí | Ambas | Sí |
| None | Prov y devolución solamente | N.º | Ambas | Sí |
| Aprovisionar | Solo provisión | Sí | Aprovisionar | N.º |
| Devolución | Solo devolución | Sí | Devolución | Sí |

## <a name="examples-of-rebate-reduction-principle-calculations"></a>Ejemplos de cálculos del principio de reducción de devoluciones

Tiene un pedido de ventas que tiene una sola línea de pedido de ventas. Esta línea tiene un valor de 1000 $. Al pedido se le aplican los siguientes acuerdos:

- **Acuerdo 1:** 10 por ciento en 1000 $
- **Acuerdo 2:** 15 por ciento en 1000 $
- **Acuerdo 3:** 20 por ciento en 1000 $
- **Acuerdo 4:** 25 por ciento en 1000 $

El orden de procesamiento es muy importante. El orden de procesamiento se basa en la forma en que trabaja, como se describe en [Procesar, revisar y publicar devoluciones](process-review-post.md).

Por ejemplo, la siguiente tabla resume el resultado si usa el pedido *1, 2, 3, 4*, y si procesa solo las provisiones.

| Oferta | Descripción y configuración | Resultado de la provisión |
|---|---|---|
| 1 | <p>La clasificación no verifica otros acuerdos para ver si hay reducciones. La verificación se realiza tanto para provisiones como para devoluciones.</p><ul><li>**Aplicar reducción**: *No*</li><li>**Base de reducción:** *Ambas*</li><li>**Excluir de la reducción:** *No*</li></ul> | 1000 $ × 10 % = 100 $ |
| 2 | <p>La clasificación comprueba si hay reducciones en otros acuerdos, pero se marca para que se ignore. La verificación se realiza solo para devoluciones.</p><ul><li>**Aplicar reducción**: *Sí*</li><li>**Base de reducción:** *Devolución*</li><li>**Excluir de la reducción:** *Sí*</li></ul> | 1000 $ × 15 % = 150 $ |
| 3 | <p>La clasificación verifica otros acuerdos para ver si hay reducciones. La verificación se realiza tanto para provisiones como para devoluciones.</p><ul><li>**Aplicar reducción**: *Sí*</li><li>**Base de reducción:** *Ambas*</li><li>**Excluir de la reducción:** *No*</li></ul> | (1000 $ – Acuerdo 1) × 20 % = 180 $ |
| 4 | <p>La clasificación verifica otros acuerdos para ver si hay reducciones. La verificación se realiza tanto para provisiones como para devoluciones.</p><ul><li>**Aplicar reducción**: *Sí*</li><li>**Base de reducción:** *Ambas*</li><li>**Excluir de la reducción:** *No*</li></ul> | (1000 $ - Oferta 1 - Oferta 3) × 25% = 180 $ |

La siguiente tabla muestra algunos ejemplos donde la provisión se procesa en diferentes órdenes, y donde por lo tanto se alcanzan diferentes totales. La variación en las disposiciones depende del orden en el que el sistema procesa las transacciones. Es importante que comprenda cómo el orden de procesamiento afecta el monto final de la devolución.

| Secuencia | Cálculo |
|---|---|
| 1<br>(1, 2, 3, 4) | <ul><li>**Acuerdo 1:** 1000 $ × 10 % = 100 $</li><li>**Acuerdo 2:** 1000 $ × 15 % = 150 $</li><li>**Acuerdo 3**: (1000 $ - Acuerdo 1) × 20% = 180 $</li><li>**Acuerdo 4:** (1000 $ - Acuerdo 1 - Acuerdo 2) × 25% = 180 $</li><li>**Provisión total:** 610 $</li></ul> |
| 2<br>(4, 3, 2, 1) | <ul><li>**Acuerdo 4:** 1000 $ x 25% = 250 $</li><li>**Acuerdo 3**: (1000 $ - Acuerdo 4) × 20% = 150 $</li><li>**Acuerdo 2:** 1000 $ x 15% = 150 $</li><li>**Acuerdo 1:** 1000 $ x 10% = 100 $</li><li>**Provisión total:** 650 $</li></ul> |
| 3<br>(3, 2, 1, 4) | <ul><li>**Acuerdo 3:** 1000 $ x 20% = 200 $</li><li>**Acuerdo 2:** 1000 $ x 15% = 150 $</li><li>**Acuerdo 1:** 1000 $ x 10% = 100 $</li><li>**Acuerdo 4:** (1000 $ - Acuerdo 3 - Acuerdo 1) × 25% = 175 $</li><li>**Provisión total:** 625 $</li></ul> |
| 4<br>(2, 4, 1, 3) | <ul><li>**Acuerdo 2:** 1000 $ × 15 % = 150 $</li><li>**Acuerdo 4:** 1000 $ × 25 % = 250 $</li><li>**Acuerdo 1:** 1000 $ × 10 % = 100 $</li><li>**Acuerdo 3:** (1000 $ - Acuerdo 4 - Acuerdo 1) × 20 % = 130 $</li><li>**Provisión total:** 630 $</li></ul> |
