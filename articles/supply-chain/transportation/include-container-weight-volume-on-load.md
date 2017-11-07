---
title: Incluir peso y volumen del contenedor de la carga
description: "En este tema se describe cómo configurar y aplicar una funcionalidad para incluir el peso y el volumen del contenedor en las cargas."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: b137db6f67da30d6ac3a973940c1df1fd7268a1a
ms.openlocfilehash: ac1df9b430feb025e4a544a7ecd7baa0c919cbe4
ms.contentlocale: es-es
ms.lasthandoff: 10/02/2017

---

# <a name="include-container-weight-and-volume-on-load"></a>Incluir peso y volumen del contenedor de la carga

[!include[banner](../includes/banner.md)]

La funcionalidad para incluir el peso y el volumen del contenedor en una carga ofrece una representación clara del peso y volumen totales de los contenedores y los artículos que se vayan a cargar.

Una carga contiene un envío único o varios envíos y estos contienen distintos artículos que pertenecen a un único pedido de ventas o a varios pedidos de ventas. Los artículos se almacenan en un contenedor y los contenedores se cargan en una carga. Los artículos que se encuentran fuera de un contenedor también pueden formar parte de una carga. Según estas condiciones, el sistema calculará los valores del peso y volumen en la carga considerando el peso y el volumen de los contenedores y los artículos.

Si los valores calculados no coinciden exactamente, puede ajustarlos especificando valores reales del peso y el volumen en la carga. Los valores de peso y volumen se usan en procesos de gestión de transporte. Por ejemplo, los valores se usan en el banco de trabajo de una ruta de tasa, donde se definen la tasa y la ruta de las cargas y también las formas de pago de transporte y el registro de entrada del conductor.

## <a name="where-it-applies"></a>Dónde se aplica

La funcionalidad para incluir el peso y el volumen del contenedor en una carga, se aplica a los procesos de gestión de transporte tales como el banco de trabajo de una ruta de tasa, las formas de pago de transporte y el registro de entrada del conductor

## <a name="how-it-is-set-up"></a>Cómo se configura

El número de contenedores que se deben tener en cuente para una carga se calcula en función del peso y el volumen del contenedor, así como el porcentaje del contenedor que se utiliza.

-   Para establecer el peso y el volumen de un contenedor, haga clic en **Gestión de almacenes** \> **Configuración** \> **Contenedores** \> **Tipos de contenedor**.

-   Para configurar el porcentaje de utilización del contenedor, haga clic en **Gestión de almacenes** \> **Configuración** \> **Contenedores** \> **Grupos de contenedor** y, a continuación, especifique un valor en el campo **Porcentaje de utilización del contenedor**.

