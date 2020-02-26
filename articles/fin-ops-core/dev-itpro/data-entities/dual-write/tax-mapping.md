---
title: Impuestos integrados
description: Este tema describe la integración de datos de impuestos entre Finance and Operations y Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 0d32a5f7859f0200da823a73d94b9a6b2a9c8e7d
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019996"
---
# <a name="integrated-tax"></a>Impuestos integrados

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Los datos de configuración de impuestos definen la configuración para los impuestos indirectos (IVA, impuestos, GST) y la retención de impuestos. Describe la regla de cálculo del impuesto, el índice de impuestos, la contabilidad del impuesto, su liquidación y otros conceptos.

## <a name="templates"></a>Plantillas

Los datos de los impuestos incluyen una colección de mapas de entidad que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.

Finance and Operations   | Otras aplicaciones de Dynamics 365
-------------------------|---------------------------------
Códigos de impuestos                  | msdyn\_taxcodes.md
Grupos de impuestos               | msdyn\_taxgroups.md
Grupos de artículos con impuestos          | msdyn\_taxitemgroups.md
Exenciones fiscales           | msdyn\_taxexemptcodes.md
Autoridades fiscales          | msdyn\_taxauthorities.md
Códigos de retenciones de impuestos      | msdyn\_withholdingtaxcodes.md
Grupos de retenciones de impuestos   | msdyn\_withholdingtaxgroups.md
Grupo de cuentas contables de impuestos | msdyn\_taxpostinggroups  

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

