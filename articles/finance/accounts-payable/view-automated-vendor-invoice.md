---
title: Ver resultados de automatización de facturas de proveedores (versión preliminar)
description: Este artículo explica cómo ver el estado de las facturas de proveedores que se encuentran en el proceso automatizado de envío al flujo de trabajo.
author: abruer
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dd9b74d2ed34399aff455563504c296a5a25a874
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895178"
---
# <a name="view-vendor-invoice-automation-results"></a>Ver resultados de automatización de facturas de proveedores

[!include [banner](../includes/banner.md)]

Este artículo explica cómo ver el estado de las facturas de proveedores que se encuentran en el proceso automatizado de envío al flujo de trabajo. Los detalles del historial de automatización se mantienen para cada factura de proveedor importada. Dependiendo de los procesos comerciales que haya automatizado, la página **Facturas de proveedores pendientes** muestra los valores **Estado de conciliación del recibo automatizado** y **Envío automatizado al estado del flujo de trabajo**. Puede ver los detalles y hacer un plan para enfocarse en las facturas que fallaron en un paso automático. Luego, después de corregir el problema, puede reanudar el proceso automatizado para la factura importada.

Antes de poder editar una factura que se ha enviado, debe pausar el procesamiento automatizado. Si una factura en el proceso automatizado de envío a flujo de trabajo debe estar en pausa, configure el campo **Incluir en procesamiento automatizado** como **No** en la página **Facturas de proveedores**. La automatización no se ejecutará hasta que **Incluir en procesamiento automatizado** se establezca en **Sí**. Una factura se puede pausar para una mayor automatización si aún no está en el sistema de flujo de trabajo y el proceso automatizado no la utiliza.

Si una factura importada está sujeta al proceso de envío al flujo de trabajo, puede ver su valor **Estado de la automatización** en la página **Facturas de proveedores**. Se siguen los siguientes estados:

- **Incluido** - Los procesos automatizados que se definen en la página **Parámetros de cuentas por pagar** se ejecutan correctamente pero aún no se han completado.
- **Pausado** - Los procesos automatizados que se definen en la página **Parámetros de cuentas por pagar** se han ejecutado, pero al menos un paso del proceso falló. El estado **Pausado** también se aplica si el campo **Incluir en procesamiento automatizado** está configurado como **No**. Puede ver los errores seleccionando **Ver resultados más recientes**.
- **En flujo de trabajo** - La factura importada se ha enviado al sistema de flujo de trabajo, ya sea mediante el proceso automatizado de envío al flujo de trabajo o manualmente.
- **Flujo de trabajo completo** - Se ha completado el proceso de flujo de trabajo para la factura importada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
