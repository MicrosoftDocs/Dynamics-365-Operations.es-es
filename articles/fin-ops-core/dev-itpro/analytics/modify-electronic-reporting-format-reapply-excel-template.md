---
title: Modificar formatos de informes electrónicos al aplicar de nuevo plantillas de Excel
description: Este tema describe cómo modificar el formato de informes electrónicos (ER) que se usa para generar documentos empresariales reaplicando una plantilla de Excel modificada.
author: NickSelin
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: e3f7960d-2e01-46a7-9ac8-c355ac933cd6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 626450b05789c93f63675a55e050649c862c86f6
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811403"
---
# <a name="modify-electronic-reporting-formats-by-reapplying-excel-templates"></a>Modificar formatos de informe electrónico al aplicar de nuevo plantillas de Excel

[!include [banner](../includes/banner.md)]

La herramienta de informes electrónicos (ER) se usa para generar documentos empresariales en formato electrónico. Para generar un documento empresarial, debe crear un formato de ER, y luego usar el diseñador de ER para definir el diseño de documento empresarial y especificar los datos que se deben incluir en él. A continuación puede ejecutar el formato de ER para generar el documento empresarial.

La herramienta de ER se puede usar para generar documentos empresariales como archivos de Microsoft Excel. Puede usar un documento de Excel como plantilla para estos documentos. Para definir el diseño de documento en el diseñador de ER, puede importar el contenido del documento de Excel que desea utilizar como plantilla en el formato definido de ER. Para más detalles y practicar este escenario, reproduzca la guía de tareas **Diseñar una configuración ER para generar informes en formato OPENXML** (parte del proceso empresarial 7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)). En el paso de la guía de tareas donde importa una plantilla de Excel, utilice plantilla inicial del archivo de Excel de informe de pago, [SampleVendPaymWsReport](https://download.microsoft.com/download/e/6/b/e6bb79f0-cc08-44af-96fa-49c7929d4fb8/SampleVendPaymWsReport.xlsx)

Si edita el documento de Excel que se usa como plantilla para un documento empresarial, la nueva funcionalidad de ER permite reaplicar la plantilla actualiza al formato de ER. El formato de ER se actualiza a continuación para ajustarse a la plantilla actualizada. Para más detalles sobre esta funcionalidad, reproduzca la guía de tareas **Modificar un formato de ER reaplicando una plantilla de Excel** (parte del proceso empresarial 7.5.5.3 Adquirir o desarrollar componentes de soluciones y servicios de TI (10683)). En el paso de la guía de tareas donde importa una plantilla actualizada, utilice plantilla modificada del archivo de Excel de informe de pago, [SampleVendPaymWsReport2](https://download.microsoft.com/download/3/1/0/3104d397-c9c5-4227-b68e-f98625313801/SampleVendPaymWsReport2.xlsx).

## <a name="additional-resources"></a>Recursos adicionales

[Actualizar una plantilla](er-fillable-excel.md#update-a-template)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
