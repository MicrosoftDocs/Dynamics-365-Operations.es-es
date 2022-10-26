---
title: Panel de información de Invoice Capture
description: Este artículo describe el panel de control de la solución de Invoice Capture .
author: sunfzam
ms.date: 10/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4c9000039488c1290f4ab992d7fe79b8ccac7b19
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690136"
---
# <a name="invoice-capture-solution-dashboard"></a>Panel de información de Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En Invoice Capture , el tablero incluye gráficos que brindan una descripción general de las facturas que se han importado. Estos gráficos pueden ayudar al administrador de cuentas por pagar (AP) a analizar el rendimiento del proceso de generación de facturas. El administrador de AP puede ver el estado del proceso de generación de facturas y, al aplicar diferentes filtros, también puede ver los detalles.

## <a name="available-charts"></a>Gráficos disponibles

Los gráficos siguientes están disponibles en el panel:

- **Todas las facturas capturadas por estado** – Este gráfico muestra los siguientes estados para una factura capturada. Al seleccionar un estado, los usuarios pueden filtrar las facturas capturadas en la lista detallada.

    - Capturado
    - Completada
    - En revisión
    - Obsoleto

- **Volumen total de facturas capturadas** – Este gráfico muestra el número de facturas capturadas por período. Los usuarios pueden cambiar el período utilizando la lista desplegable.
- **Factura capturada de los principales proveedores** – Este gráfico muestra el número total de facturas por proveedor. Los proveedores que tienen más facturas aparecen en la parte superior.
- **Días para completar por factura con excepciones** – Este gráfico muestra la cantidad promedio de días que se requieren para capturar una factura. Esta información puede ayudar al administrador de AP a analizar el tiempo para procesar una factura cuando se requiere una intervención manual. Si hay una tendencia al alza, los usuarios pueden revisar los detalles del proceso y ajustar la configuración para ayudar a reducir la cantidad de días necesarios.
- **Facturas incompletas por tiempo pendiente** – Este gráfico muestra el número de días que no se ha generado una factura capturada en el sistema de planificación de recursos empresariales (ERP). Cuanto mayor sea el número de días pendientes, más largo será el proceso de generación de facturas. El administrador de AP puede profundizar en las facturas capturadas detalladas y generar facturas en el sistema ERP.
