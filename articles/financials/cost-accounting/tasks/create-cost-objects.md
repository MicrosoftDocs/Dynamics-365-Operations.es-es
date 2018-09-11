--- 
title: Crear objetos de coste
description: "Este procedimiento muestra cómo crear objetos de coste importando la dimensión financiera del centro de coste de Dynamics 365 for Finance and Operations, Enterprise edition, en la contabilidad de Costes a través de un conector de los datos."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5d43274aed2edbb91fd4e399cb8d45e91646b055
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-cost-objects"></a>Crear objetos de coste 

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear objetos de coste importando la dimensión financiera del centro de coste de Dynamics 365 for Finance and Operations, Enterprise edition, en la contabilidad de Costes a través de un conector de los datos. Se ha utilizado la empresa de demostración USMF para crear este procedimiento. Este procedimiento es para una función de la contabilidad de costes que se ha añadido en la versión 1611 de Dynamics 365 for Operations.


## <a name="create-new-cost-objects"></a>Crea nuevos objetos de coste.
1. Vaya a contabilidad de Costes > Dimensiones > dimensiones del objeto de Coste.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. En el conector de datos para el campo de miembros de dimensión, especifique o seleccione un valor.
5. En el campo Descripción, escriba un valor.
6. Haga clic en Guardar.

## <a name="configure-the-data-connector"></a>Configura el conector de datos
1. Haga clic en Configurar proveedor de miembros de dimensión.
    * Seleccione CostCenter para importar la dimensión de CostCenter en la contabilidad de Costes.  
2. En el campo Nombre de dimensión, seleccione el centro de coste.
3. Haga clic en Aceptar

## <a name="import-cost-centers"></a>Importar centros de coste
1. Haga clic en Importar miembros de dimensión.
2. Haga clic en Aceptar

## <a name="view-the-imported-cost-centers"></a>Ver los centros de coste importados
1. Haga clic en miembros de dimensión.


