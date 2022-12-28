---
title: Problemas con la conciliación de datos de un informe Z
description: Este artículo describe problemas que los usuarios pueden experimentar con la conciliación de datos de un informe Z en Commerce Headquarters. También describe posibles causas raíz y soluciones que pueden ayudar a prevenir futuras ocurrencias.
author: Shajain
ms.date: 12/06/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 9803134c4c77233e565525e96fd82af293d4c829
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832148"
---
# <a name="issues-with-the-data-reconciliation-of-a-z-report"></a>Problemas con la conciliación de datos de un informe Z

[!include [banner](../../includes/banner.md)]

Este artículo proporciona una guía para la solución de problemas que puede ayudar si encuentra problemas con la conciliación de datos de un informe Z en Microsoft Dynamics 365 Commerce Headquarters. Describe los problemas que los usuarios pueden experimentar con la reconciliación de datos, las posibles causas principales y las soluciones que pueden ayudar a prevenir futuras ocurrencias.

## <a name="description"></a>Description

- Hay una discrepancia entre los importes que se muestran en el informe Z y los totales que se muestran en el extracto calculado.
- La transacción en la sede tiene un número incorrecto de elementos de línea o hay una discrepancia entre el total de la línea y el total de la transacción.
- La cantidad de transacciones que se muestran en un turno en la sede es menor que la cantidad de transacciones en el informe Z.
- La publicación del estado de cuenta falló por uno de los motivos anteriores.

### <a name="root-cause"></a>Causa principal

La causa principal más común de los síntomas descritos anteriormente es la generación de ID de transacción duplicados en la base de datos del canal. Los id. de transacciones duplicados se pueden generar por las siguientes razones:

- El almacenamiento de la base de datos local de Modern Point of Sale (MPOS) está dañado.
- MPOS tiene algunas transacciones en modo fuera de línea y se reactiva usando una cuenta que no tiene acceso a la base de datos fuera de línea.
- Hay un problema con la personalización relacionado con la generación de ID de transacciones.

## <a name="resolution"></a>Resolución

Por lo general, Commerce se basa en una secuencia numérica para generar ID de transacciones secuenciales. Si el sistema no puede determinar que se utilizó una secuencia numérica por algún motivo, se genera un ID de transacción duplicado. 

Para solucionar el problema del ID de transacción duplicado, cree un ticket de soporte para verificar si los datos de la transacción se pueden corregir. En algunos casos, como cuando no hay pérdida de datos en la sede, no es posible ni necesario corregir los datos.

Para ayudar a prevenir este problema en el futuro, debe habilitar la función **Habilitar nueva ID de transacción para evitar ID de transacciones duplicadas** en la sede. Esta característica se introdujo en la versión 10.0.19 de Commerce. Ayuda a evitar la creación de ID de transacciones secuenciales al garantizar que se cree un ID de transacción único para cada transacción. Para más información sobre esta función, consulte [Prevenir id. de transacción duplicados](../channel-setup-retail.md#ensure-unique-transaction-ids).
