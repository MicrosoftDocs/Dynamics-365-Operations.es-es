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
ms.openlocfilehash: 14a2f4c7d8d053ffd7b4b5d090113e1d9c3294c4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974119"
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