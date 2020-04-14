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
ms.openlocfilehash: a4da37d45698290b40f6c72148f1500bef72127a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173094"
---
# <a name="integrated-tax"></a>Impuestos integrados

[!include [banner](../../includes/banner.md)]



Los datos de configuración de impuestos definen la configuración para los impuestos indirectos (IVA, impuestos, GST) y la retención de impuestos. Describe la regla de cálculo del impuesto, el índice de impuestos, la contabilidad del impuesto, su liquidación y otros conceptos.

## <a name="templates"></a>Plantillas

Los datos de los impuestos incluyen una colección de mapas de entidad que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.

| Aplicaciones de Finance and Operations | Aplicaciones basadas en modelos en Dynamics 365 | Descripción |
-------------------------|---------------------------------
Códigos de impuestos                   | msdyn\_taxcodes.md | 
Grupos de impuestos                 | msdyn\_taxgroups.md | 
Grupos de artículos con impuestos             | msdyn\_taxitemgroups.md | 
Exenciones fiscales             | msdyn\_taxexemptcodes.md | 
Autoridades fiscales             | msdyn\_taxauthorities.md | 
Códigos de retenciones de impuestos       | msdyn\_withholdingtaxcodes.md | 
Grupos de retenciones de impuestos     | msdyn\_withholdingtaxgroups.md | 
Grupo de cuentas contables de impuestos | msdyn\_taxpostinggroups     | 

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

