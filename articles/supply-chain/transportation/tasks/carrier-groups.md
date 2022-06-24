---
title: Grupos de transportistas
description: Este artículo describe cómo configurar datos para grupos de transportistas.
author: Weijiesa
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d3f8618de520880aa807a21f49f164e8483274ca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871873"
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