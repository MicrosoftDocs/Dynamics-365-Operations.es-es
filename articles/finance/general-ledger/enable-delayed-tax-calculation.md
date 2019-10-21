---
title: Habilitar el cálculo de impuestos retrasado en el diario
description: Este tema explica cómo usar la función **Habilitar el cálculo de impuestos retrasado en el diario** para mejorar el rendimiento del cálculo de impuestos cuando el volumen de las líneas de diario es muy grande.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179741"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a>Habilitar el cálculo de impuestos retrasado en el diario
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema explica cómo usar la función **Habilitar el cálculo de impuestos retrasado en el diario** para mejorar el rendimiento del cálculo de impuestos cuando el volumen de las líneas de diario es muy grande.

El comportamiento actual del cálculo de impuestos en diario se activa en tiempo real cuando el usuario actualiza los campos relacionados con impuestos, por ejemplo grupo de impuestos/grupo de impuestos de artículos. Todas las actualizaciones en el nivel de línea de diario recalculan el importe de los impuestos en todas las líneas de diario. Ayuda al usuario a consultar el importe de impuestos calculado en tiempo real, pero también podría elevar la degradación del rendimiento si el volumen de líneas de diario es muy elevado.

Esta característica proporciona una opción para retrasar el cálculo de impuestos para solucionar la degradación de rendimiento. Si está activada esta función, el importe de impuestos sólo se calculará cuando el usuario haga clic en el comando "Impuestos" o registra en el diario.

El usuario puede activar o desactivar el parámetro en tres niveles:
- Por entidad jurídica
- Por nombre del diario
- Por encabezado de diario

El sistema tomará el valor de parámetro de la cabecera de diario como valor final. El valor de parámetro de la cabecera de diario se tomará predeterminadamente del nombre de diario. El valor de parámetro en el nombre de diario se tomará predeterminadamente del parámetro de contabilidad general cuando se crea el nombre del diario.

Los campos "Importe real de impuestos" y "Importe de impuestos calculado" del diario estarán ocultos si está activado este parámetro. El propósito es no confundir al usuario porque el valor de estos dos campos siempre mostrará 0 antes de que el usuario desencadene el cálculo de impuestos.

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a>Habilitar el cáculo de impuestos retrasado por entidad jurídica

1. Vaya a **Contabilidad general > Configuración de contabilidad > Parámetros de Contabilidad general**
2. Haga clic en **Impuestos**
3. En la ficha rápida **General**, busque el parámetro **Cálculo retrasado de impuestos** y actívelo o desactívelo.

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a>Habilitar el cálculo de impuestos retrasado por nombre de diario

1. Vaya a **Contabilidad general > Configuración de diario > Nombres de diarios**
2. En la ficha rápida **General**, busque el parámetro **Cálculo retrasado de impuestos** y actívelo o desactívelo.

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a>Habilitar el cálculo de impuestos retrasado por diario

1. Vaya a **Contabilidad general > Movimientos de diario > Diarios generales**
2. Haga clic en **Nuevo**
3. Seleccione un nombre de diario
4. Haga clic en **Configurar**
5. Busque el parámetro **Cálculo retrasado de impuestos** y actívelo o desactívelo.

![](media/delayed-tax-calculation-journal-header.png)
