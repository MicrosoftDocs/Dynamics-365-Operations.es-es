---
title: MX-00020 Configuración del plan de cuentas para una entidad jurídica en México
description: Configure parámetros específicos en el plan contable para habilitar la generación de informes de contabilidad electrónicos para una entidad jurídica mexicana.
author: AdamTrukawka
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: MainAccount, LedgerConsolidateAccountGroup, MainAccountConsolidateAccount
ms.openlocfilehash: ba366ef651f4da495f1edaca828deb42003e6a79
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273729"
---
# <a name="mx-00020-set-up-the-chart-of-accounts-for-a-legal-entity-in-mexico"></a>MX-00020 Configuración del plan de cuentas para una entidad jurídica en México

[!include [banner](../../includes/banner.md)]

Configure parámetros específicos en el plan contable para habilitar la generación de informes de contabilidad electrónicos para una entidad jurídica mexicana. Esta tarea se creó con la empresa de datos de demostración MXMF.


## <a name="set-up-parameters-for-electronic-ledger-accounting-report"></a>Configuración de parámetros para el informe electrónico de contabilidad de libro mayor
1. Vaya a Contabilidad general > Plan contable > Cuentas > Cuentas principales.
2. Haga clic en Nuevo.
3. En el campo Cuenta principal, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. En el campo Valor predet. Debe/Haber, seleccione una opción.
    * Use este campo para especificar la transacción típica (débito o crédito). Este campo se usa en el archivo XML para notificar el tipo de cuenta principal de gobierno en el nodo `<Natur>`.  El tipo de cuenta principal se usará para determinar el tipo de cuenta de gobierno cuando este campo esté en blanco.  
6. En el campo Cuenta principal, haga clic en el botón desplegable para abrir la búsqueda.
    * Ejemplo: 110 Use este archivo para configurar la cuenta principal del nivel anterior.     Deje este campo en blanco cuando la cuenta principal represente el primer nivel de empresa en el plan contable.    
7. En la lista, busque y seleccione el registro deseado.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. Haga clic en Guardar.

## <a name="set-up-government-group-mapping"></a>Configuración de asignación de grupos del gobierno
1. Vaya a Contabilidad general > Plan contable > Cuentas > Grupos de cuentas de consolidación.
2. Haga clic en Nuevo.
3. En el campo Grupo de cuenta de consolidación, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. Haga clic en Guardar.
6. Cierre la página.
7. Vaya a Contabilidad general > Plan contable > Cuentas > Cuentas de consolidación adicionales.
8. Haga clic en Nuevo.
9. En el campo Cuenta principal, haga clic en el botón desplegable para abrir la búsqueda.
10. En la lista, busque y seleccione el registro deseado.
11. En la lista, haga clic en el vínculo de la fila seleccionada.
12. En el campo Grupo de cuenta de consolidación, haga clic en el botón desplegable para abrir la búsqueda.
13. En la lista, busque y seleccione el registro deseado.
14. En la lista, haga clic en el vínculo de la fila seleccionada.
15. En el campo Cuenta de consolidación, escriba un valor.
    * Introduzca el grupo de la cuenta SAT. La lista de grupos de cuentas del gobierno está disponible en el sitio web de la administración pública.    
16. En el campo Nombre de cuenta de consolidación, escriba un valor.
    * Puede insertar el nombre del grupo de cuentas SAT.    
17. En el campo Nivel de SAT, escriba un número.
    * Este es el nivel de grupo de cuentas SAT. La información se encuentra disponible en la lista de grupos de cuentas SAT.  
18. Haga clic en Guardar.
    * Necesita repetir esta acción para cada cuenta principal creada en su empresa. Si tiene muchas cuentas principales que crear, puede usar la herramienta de gestión de datos para importar las cuentas principales desde un archivo de Microsoft Excel.  
19. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
