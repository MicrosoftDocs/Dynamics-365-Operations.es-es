---
title: Registrar en el diario movimientos de diario
description: Este procedimiento muestra los pasos para registrar en el diario las entradas del diario registradas.
author: aprilolson
ms.date: 03/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d8fca167563b14c825ebe29874c6488ddfb4d9a
ms.sourcegitcommit: 06acdfbccd7bd213a2397ea7b85d104f01914437
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2022
ms.locfileid: "8400884"
---
# <a name="journalize-posted-journal-entries"></a>Registrar en el diario movimientos de diario registrados

[!include [banner](../../includes/banner.md)]

El proceso de contabilización en el libro mayor proporciona una manera de agrupar e informar sobre asientos de comprobantes registrados para su libro mayor. En función de los criterios que proporcione, el procesamiento genera una lista de comprobantes que utilizan una secuencia numérica única y que tienen el valor del libro mayor **Número de diario** como referencia.

Siga estos pasos para registrar en el diario las entradas del diario registradas. Este procedimiento usa la empresa de datos de demostración **USMF**.

1. Vaya a **Contabilidad general** \> **Configuración de contabilidad** \> **Parámetros de Contabilidad general**.
2. En el campo **Diario de libro mayor extendido**, seleccione un valor. Si selecciona **Sí**, la salida de informes es diferente.
3. Seleccione si el período puede cerrarse si el proceso de registro en el diario no se ha ejecutado. Si selecciona **Sí**, no puede cerrarse el período hasta que el proceso de registro en el diario se haya completado para ese período.
4. Cierre la página.
5. Vaya a **Contabilidad general** \> **Tareas periódicas** \> **Periodismo** y seleccione **Filtrar**.
6. Seleccione la fila con los criterios de filtro que desee definir.
7. En el campo **Criterios**, especifique o seleccione los criterios de filtro.
8. Seleccione **Aceptar** para cerrar la página.
9. Seleccione **Aceptar** para iniciar el proceso de registro en el diario. Se generará un informe después de que se complete el proceso.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
