---
title: Impuestos integrados
description: Este tema describe la integración de datos de impuestos entre Finance and Operations y Dataverse.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 7501ef21492a96c81b971e1d9077beaba9be897b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560346"
---
# <a name="integrated-tax"></a>Impuestos integrados

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Los datos de configuración de impuestos definen la configuración para los impuestos indirectos (IVA, impuestos, GST) y la retención de impuestos. Describe la regla de cálculo del impuesto, el índice de impuestos, la contabilidad del impuesto, su liquidación y otros conceptos.

## <a name="templates"></a>Plantillas

Los datos de los impuestos incluyen una colección de mapas de tabla que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.

Aplicaciones de Finance and Operations | Aplicaciones basadas en modelos en Dynamics 365 | Descripción |
-------------------------|---------------------------------|----|
Grupo de impuestos de artículos | msdyn_taxitemgroups |
Autoridades fiscales | msdyn_taxauthorities |
Entidad de código de exención de impuestos para CDS | msdyn_taxexemptcodes |
Grupos de impuestos | msdyn_taxgroups |
Grupos de registro contable de impuestos de ventas V2 | msdyn_taxpostinggroups |
Códigos de retenciones de impuestos | msdyn_withholdingtaxcodes |
Grupos de retenciones de impuestos | msdyn_withholdingtaxgroups | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]