---
title: Crear elementos de coste
description: Existen varias maneras de crear elementos de coste en la contabilidad de costes.
author: kfend
ms.date: 08/29/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
ms.openlocfilehash: 0254f486816e852bcda52f90fe4da65c413c7032
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779699"
---
# <a name="create-cost-elements"></a>Crear elementos de coste 

[!include [banner](../../includes/banner.md)]

Existen varias maneras de crear elementos de coste en la contabilidad de costes. Este procedimiento muestra cómo crear elementos de costes importando las cuentas principales mediante un conector de datos. Se ha utilizado la empresa de demostración USMF para crear este procedimiento. Este procedimiento se utiliza para la función contabilidad de cuentas, que se ha añadido a Dynamics 365 for Operations, versión 1611.


## <a name="create-new-cost-elements"></a>Crea nuevos elementos de coste.
1. Vaya a **Contabilidad de costes > Dimensiones > Dimensiones de elemento de coste**.
2. Haga clic en **Nuevo**.
3. En el campo **Nombre**, escriba un valor.
4. En el campo **Conector de datos para miembros de dimensión**, especifique o seleccione un valor.
5. En el campo **Descripción**, escriba un valor.
6. Haga clic en **Guardar**.

## <a name="configure-the-data-connector"></a>Configura el conector de datos
1. Haga clic en **Configurar proveedor de miembros de dimensión**.
2. En el campo **Plan de cuentas**, introduzca o seleccione un valor.
    * Seleccione **Compartido** para usar el plan contable compartido.  
3. Haga clic en **Nuevo**.
4. En la lista, marque la fila seleccionada.
    * Puede aplicar filtros a las cuentas para que cumplan sus criterios.  
5. En el campo **Desde cuenta principal**, introduzca o seleccione un valor.
6. En el campo **A la cuenta principal**, introduzca o seleccione un valor.
7. Haga clic en **Aceptar**.

## <a name="import-main-accounts"></a>Importar cuentas principales
1. Haga clic en **Importar miembros de dimensión**.
    * Las cuentas principales se importarán a la contabilidad de costes y se utilizarán como elementos de coste.  
2. Haga clic en **Aceptar**.

## <a name="view-the-imported-accounts-as-cost-elements"></a>Ver las cuentas importadas como elementos de coste
1. Haga clic en **Ver miembros de dimensión**.
    * Ver las cuentas contables importadas como elementos de coste en su negocio a los que se pueden derivar costes.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
