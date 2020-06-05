---
title: Gastos de empresas vinculadas
description: Un trabajador que sea empleado en una entidad jurídica de una organización podría realizar trabajos para otra entidad jurídica de la misma organización. En esta situación, puede usar la función de gastos de empresas vinculadas para asignar los gastos del trabajador a la entidad jurídica para la que se realizó el trabajo.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390893"
---
# <a name="intercompany-expenses"></a>Gastos de empresas vinculadas

[!include [banner](../includes/banner.md)]

Un trabajador que sea empleado en una entidad jurídica de una organización podría realizar trabajos para otra entidad jurídica de la misma organización. En esta situación, puede usar la función de gastos de empresas vinculadas para asignar los gastos del trabajador a la entidad jurídica para la que se realizó el trabajo. La entidad jurídica que emplea al trabajador se denomina entidad jurídica que presta el trabajador. La entidad jurídica para la que el trabajador genera gastos se llama la entidad jurídica prestataria. 

Antes de que un trabajador pueda crear y registrar los gastos del trabajo que se ha realizado para una entidad jurídica diferente, en la entidad jurídica que otorga el préstamo, en la página **Parámetros de gestión de gastos**, seleccione la opción **Permitir las líneas de gastos de empresas vinculadas**. 

## <a name="tax-posting-for-intercompany-expenses"></a>Contabilización de impuestos para gastos de empresas vinculadas

[!include [banner](../includes/banner.md)]

Si desea utilizar grupos de IVA de importación asociados con la entidad jurídica prestataria (origen) en lugar de la entidad jurídica prestadora (destino) en su informe de gastos, deberá configurar esto en la configuración del impuesto sobre las ventas de contabilidad general mayor. Cuando el parámetro de contabilidad general, **Entidad legal para la contabilización de impuestos entre empresas vinculadas** se establece en **Origen** y **Aplicar las reglas de impuestos sobre las ventas** se establece en **No**, se utilizará la combinación de impuestos para la entidad jurídica prestataria. Cuando el mismo parámetro se establece en **Destino**, se utilizará la combinación de impuestos para la entidad jurídica prestadora. Para entidades legales de los Estados Unidos, cuando el parámetro se establece en **Origen**, el campo **Impuesto a las ventas por cobrar** también debe configurarse en la nueva página **Grupos contables del libro mayor**. El motor de contabilidad utilizará la información de este campo para la entrada de contabilidad relacionada con los impuestos.   
El comportamiento es coherente para las líneas de gastos contabilizadas con o sin un proyecto.  
