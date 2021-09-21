---
title: No se puede cambiar la fecha efectiva de un proveedor aprobado
description: La lista de proveedores aprobados por entidad de producto no permite cambiar la fecha de vigencia
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: cb6dbd134d63daa163261cabdbd7eceb978877ae
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477480"
---
# <a name="cant-change-the-effective-date-for-an-approved-vendor"></a>No se puede cambiar la fecha efectiva de un proveedor aprobado


## <a name="symptoms"></a>Síntomas

Un producto tiene un proveedor aprobado que tiene, por ejemplo, una fecha de vigencia del 11 de enero de 2018 (*11/01/2018*) y *Nunca* como fecha de vencimiento. Si intenta cambiar la fecha de vigencia al 10 de enero de 2018 (*10/01/2018*) o al 12 de enero de 2018 (*12/01/2018*), aparecerá el siguiente error:

> No se puede crear un registro en la lista de proveedores aprobados (PdsApproveVendorList). El valor de 'Vencimiento' debe ser mayor o igual que el valor de 'Vigencia'.

## <a name="resolution"></a>Resolución

Solo puede ampliar el período para el que está aprobado el proveedor. Se aplican las siguientes reglas:

- Para cambiar la fecha de vigencia de modo que sea anterior a cualquiera de los registros (períodos) existentes para el proveedor del artículo, la fecha de vencimiento del nuevo período debe ser anterior a todas las fechas de vencimiento de los registros existentes.
- Para cambiar la fecha de vencimiento de forma que sea posterior a cualquiera de los períodos existentes, la fecha de vigencia debe ser posterior a la última fecha de vencimiento en cualquier registro existente.
- Para reducir el período general para el que está aprobado el proveedor, debe eliminar o modificar los registros existentes. Como alterna, puede utilizar el modificador **truncate** durante la importación. Este modificador elimina todos los registros existentes en la tabla de proveedores aprobados por artículo.

Para el escenario de ejemplo que se describe en la descripción del problema, donde un registro tiene como fecha de vigencia *11/01/2018* y *Nunca* como fecha de vencimiento, puede importar un nuevo registro que tenga como fecha de vigencia *10/01/2018* y *Nunca* como fecha de vencimiento. Sin embargo, no puede reducir el período para que la fecha de vigencia se actualice a *12/01/2018* a través de la administración de datos. Debe realizar este cambio a través de la interfaz de usuario.
