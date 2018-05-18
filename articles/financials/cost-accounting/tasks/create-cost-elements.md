--- 
title: Crear elementos de coste
description: Existen varias maneras de crear elementos de coste en la contabilidad de costes.
author: YuyuScheller
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e665fc53455e457a2488f4ec28ebb5b715d90eb
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-cost-elements"></a>Crear elementos de coste 

[!include [task guide banner](../../includes/task-guide-banner.md)]

Existen varias maneras de crear elementos de coste en la contabilidad de costes. Este procedimiento muestra cómo crear elementos de costes importando las cuentas principales mediante un conector de datos. Se ha utilizado la empresa de demostración USMF para crear este procedimiento. Este procedimiento es para una función de la contabilidad de costes que se ha añadido en la versión 1611 de Dynamics 365 for Operations.


## <a name="create-new-cost-elements"></a>Crea nuevos elementos de coste.
1. Vaya a contabilidad de costes > Dimensiones > dimensiones del elemento de coste.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. En el conector de datos para el campo de miembros de dimensión, especifique o seleccione un valor.
5. En el campo Descripción, escriba un valor.
6. Haga clic en Guardar.

## <a name="configure-the-data-connector"></a>Configura el conector de datos
1. Haga clic en Configurar proveedor de miembros de dimensión.
2. En el campo Plan de cuentas, introduzca o seleccione un valor.
    * Seleccione Compartido para usar el plan contable compartido.  
3. Haga clic en Nuevo.
4. En la lista, marque la fila seleccionada.
    * Puede aplicar filtros a las cuentas para que cumplan sus criterios.  
5. En el campo Desde cuenta principal, introduzca o seleccione un valor.
6. En el campo A la cuenta principal, introduzca o seleccione un valor.
7. Haga clic en Aceptar

## <a name="import-main-accounts"></a>Importar cuentas principales
1. Haga clic en Importar miembros de dimensión.
    * Las cuentas principales se importarán a la contabilidad de costes y se utilizarán como elementos de coste.  
2. Haga clic en Aceptar

## <a name="view-the-imported-accounts-as-cost-elements"></a>Ver las cuentas importadas como elementos de coste
1. Haga clic en miembros de dimensión.
    * Ver las cuentas contables importadas como elementos de coste en su negocio a los que se pueden derivar costes.  


