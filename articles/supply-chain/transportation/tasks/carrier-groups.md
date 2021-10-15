---
title: Grupos de transportistas
description: Este tema describe cómo configurar datos para grupos de transportistas.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 10a30d8fae52a25b7d65b5a9cc991677df33a2a7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574890"
---
# <a name="carrier-groups"></a>Grupos de transportistas

[!include [banner](../../includes/banner.md)]

Un grupo de transportistas es un conjunto de transportistas y servicios de transportistas. Cada grupo de transportistas especifica la secuencia preferida para los transportistas de envío y los servicios de transportista que le pertenecen.

Cuando existen varios transportistas de envío y servicios de transportista para el mismo segmento de ruta, puede especificar un grupo de transportistas en lugar de un transportista de envío específico y un servicio de transportista en el plan de ruta o guía de ruta.

## <a name="create-a-carrier-group"></a>Crear un grupo de transportistas

1. Vaya a **Administración de transporte &gt; Configuración &gt; Transportistas &gt; Grupo de transportistas**.
1. Seleccione **Nuevo**.
1. En el campo **Grupo de transportistas**, especifique un identificador (ID) único para el grupo.
1. En el campo **Nombre**, especifique un nombre descriptivo para el grupo.
1. En la ficha desplegable **Detalles**, agregue una fila y seleccione un transportista de envío y un servicio de transportista para ello. Repita este paso hasta que haya agregado tantos operadores como necesite para el grupo.
1. Cierre la página.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]