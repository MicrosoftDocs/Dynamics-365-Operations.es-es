---
title: No se puede insertar la versión activa de la lista de materiales y los números de ruta
description: Si el sitio y almacén ya están definidos para un producto seleccionado, no se le pedirá que inserte la versión activa de la L. MAT. y los números de ruta.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 241618d70f01c85df946a48493f5d84e0964218e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477477"
---
# <a name="cant-insert-bill-of-material-and-route-when-creating-a-new-production-order"></a>No se puede insertar la lista de materiales y la ruta al crear un nuevo pedido de producción

## <a name="symptoms"></a>Síntomas

Cuando crea una nueva orden de producción, después de ingresar el número de artículo, los campos **Sitio** y **Almacén** se establecen automáticamente en el sitio y el almacén predeterminados que se definen en la página **Configuración de orden predeterminada** para el artículo de productos terminados. Además, el número de lista de materiales activo y el número de ruta se ingresan automáticamente, por lo que no recibe el siguiente mensaje que le solicita esos valores:

> ¿Insertar versión activa para lista de materiales y ruta?

## <a name="resolution"></a>Resolución

No se le solicitará que inserte los números de lista de materiales y de ruta si selecciona un producto para el que ya se han definido un sitio y un almacén en la página **Configuración de orden predeterminada**. Solo se le solicitará si esos valores no están definidos para el producto seleccionado.
