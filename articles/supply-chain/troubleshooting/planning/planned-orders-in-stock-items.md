---
title: Los pedidos planificados se generan para el stock con los pedidos de producción
description: Los pedidos planificados se generan aunque tenga artículos en stock y ya existan pedidos de producción para ellos
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: aa803bcd7d43aa36675596050ccbe06831f1724d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477573"
---
# <a name="planned-orders-are-generated-for-in-stock-with-production-orders"></a>Los pedidos planificados se generan para el stock con los pedidos de producción

## <a name="symptoms"></a>Síntomas

Los pedidos planificados se generan aunque tenga artículos en stock y ya existan pedidos de producción para ellos.

## <a name="resolution"></a>Resolución

Es posible que pueda solucionar este problema aumentando el valor **Días positivos** para los grupos relevantes en la página **Grupo de cobertura**. Este cambio hará que el sistema determine si el inventario disponible se puede utilizar para la demanda. Entonces, no se generará un nuevo pedido planificado para los artículos que están en stock.
