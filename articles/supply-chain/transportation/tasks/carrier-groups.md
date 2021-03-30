---
title: Grupos de transportistas
description: Este tema describe cómo configurar datos para grupos de transportistas.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 95517153dda06cecf8e57b1f9b080aa07966c111
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247271"
---
# <a name="carrier-groups"></a>Grupos de transportistas

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