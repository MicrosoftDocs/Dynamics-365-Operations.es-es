---
title: Incluir peso y volumen del contenedor de la carga
description: En este artículo se describe cómo configurar y aplicar una funcionalidad para incluir el peso y el volumen del contenedor en las cargas.
author: Weijiesa
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66dc84171f8b175476f37f736489d3d83cacfe57
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897411"
---
# <a name="include-container-weight-and-volume-on-load"></a>Incluir peso y volumen del contenedor de la carga

[!include [banner](../includes/banner.md)]

La funcionalidad para incluir el peso y el volumen del contenedor en una carga ofrece una representación clara del peso y volumen totales de los contenedores y los artículos que se vayan a cargar.

Una carga contiene un envío único o varios envíos y estos contienen distintos artículos que pertenecen a un único pedido de ventas o a varios pedidos de ventas. Los artículos se almacenan en un contenedor y los contenedores se cargan en una carga. Los artículos que se encuentran fuera de un contenedor también pueden formar parte de una carga. Según estas condiciones, el sistema calculará los valores del peso y volumen en la carga considerando el peso y el volumen de los contenedores y los artículos.

Si los valores calculados no coinciden exactamente, puede ajustarlos especificando valores reales del peso y el volumen en la carga. Los valores de peso y volumen se usan en procesos de gestión de transporte. Por ejemplo, los valores se usan en el banco de trabajo de una ruta de tasa, donde se definen la tasa y la ruta de las cargas y también las formas de pago de transporte y el registro de entrada del conductor.

## <a name="where-it-applies"></a>Dónde se aplica

La funcionalidad para incluir el peso y el volumen del contenedor en una carga, se aplica a los procesos de gestión de transporte tales como el banco de trabajo de una ruta de tasa, las formas de pago de transporte y el registro de entrada del conductor

## <a name="how-it-is-set-up"></a>Cómo se configura

El número de contenedores que se deben tener en cuente para una carga se calcula en función del peso y el volumen del contenedor, así como el porcentaje del contenedor que se utiliza.

-   Para establecer el peso y el volumen de un contenedor, haga clic en **Gestión de almacenes** \> **Configuración** \> **Contenedores** \> **Tipos de contenedor**.

-   Para configurar el porcentaje de utilización del contenedor, haga clic en **Gestión de almacenes** \> **Configuración** \> **Contenedores** \> **Grupos de contenedor** y, a continuación, especifique un valor en el campo **Porcentaje de utilización del contenedor**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]