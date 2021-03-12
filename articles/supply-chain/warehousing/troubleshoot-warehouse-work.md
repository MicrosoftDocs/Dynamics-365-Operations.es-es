---
title: Solucionar problemas de trabajo de almacén
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con trabajo de almacenes en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 3015ec777953cedb5a5d8eea873ed1043cac04cb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970253"
---
# <a name="troubleshoot-warehouse-work"></a>Solucionar problemas de trabajo de almacén

[!include [banner](../includes/banner.md)]

Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con trabajo de almacenes en Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a>No puedo mover placas de matrícula que tienen elementos de número de serie cuando se permiten la emisión en blanco y el recibo en blanco en el grupo de dimensiones de seguimiento.

### <a name="issue-description"></a>Descripción del problema

No puede mover una matrícula usando un elemento de menú **Movimiento** si el número de serie tiene ajustes *Se permite un problema en blanco* y *Recibo en blanco permitido* en el grupo de dimensiones de seguimiento, y si hay varias placas de matrícula en la misma ubicación, algunas de las cuales tienen números de serie y otras no.

### <a name="issue-resolution"></a>Solución del problema

Este problema se solucionará con los cambios implementados en [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Esos cambios harán que el campo opcional **Número de serie** cuando se permiten recibo en blanco y emisión en blanco.

## <a name="i-receive-the-following-error-message-in-the-warehouse-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a>Recibo el siguiente mensaje de error en la aplicación del almacén cuando proceso movimientos: "El propietario del inventario %1 no está permitido en este proceso".

### <a name="issue-description"></a>Descripción del problema

La dimensión de seguimiento **Propietario** falta cuando se utiliza la aplicación del almacén para realizar movimientos. Un diario de transferencia de inventario regular del cliente de Supply Chain Management parece funcionar según lo previsto y solo se puede registrar si la dimensión **Propietario** se completa.

### <a name="issue-resolution"></a>Solución del problema

Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones. Actualmente, los procesos de gestión de almacenes solo admiten el inventario que es propiedad de la entidad jurídica.