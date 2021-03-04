---
title: Preguntas frecuentes sobre informes financieros
description: Este tema enumera preguntas relacionadas con los informes financieros que han tenido otros usuarios.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3f9381f5b656d0cc0b46c8828b2ef9d024e296b0
ms.sourcegitcommit: 14785208d84b2c1efd30f140c52df35a2ccd1577
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "5070226"
---
# <a name="financial-reporting-faq"></a>Preguntas frecuentes sobre informes financieros 

Este tema enumera preguntas relacionadas con los informes financieros que han tenido otros usuarios. 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>¿Cómo puedo restringir el acceso a un informe mediante seguridad de árbol?

Escenario: la empresa de demostración USMF tiene un informe de balance de situación que no desea que todos los usuarios de informes financieros puedan ver en D365. Solución: puede utilizar la seguridad de árbol para restringir el acceso a un solo informe, de modo que solo determinados usuarios puedan acceder al informe. 

1.  Inicie sesión en Financial Reporter Report Designer

2.  Cree una nueva definición de árbol (Archivo | Nuevo | Definición de árbol) a.    Haga doble clic en la línea **Resumen** de la columna **Seguridad de la unidad**.
  i.    Haga clic en Usuarios y grupos.  
          1.    Seleccione los usuarios o el grupo a los que desearía conceder acceso a este informe. 
          
[![pantalla de usuario](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)

[![pantalla de seguridad](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)

  b.    Haga clic en **Guardar**.
  
[![botón de guardar](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)

3.  En su definición del informe, agregue su nueva definición de árbol

[![formulario de definición de árbol](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)

A.  Mientras se encuentra en la definición de árbol, haga clic en Configuración y, en "Selección de unidad de informes", marque “Incluir todas las unidades”

[![formulario de selección de unidad de informes](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)

**Antes:** [![antes de la captura de pantalla](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)

**Después:** [![después de la captura de pantalla](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)

Nota: el motivo del mensaje anterior es que mi usuario no tiene acceso a ese informe después de aplicar Seguridad de la unidad



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a>¿Cómo puedo determinar qué cuentas no coinciden con mis saldos en D365?

Cuando tenga un informe que no coincida con lo que podría esperar en D365, aquí hay algunos pasos que puede seguir para identificar esas cuentas y las desviaciones. 

### <a name="in-financial-reporter-report-designer"></a>En Financial Reporter Report Designer

1.  Cree una nueva definición de fila a.    Haga clic en Editar | Insertar filas desde Dimensiones i.  Seleccione MainAccount [![Seleccione Pantalla principal_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)
    
    ii. Haga clic en Aceptar b.    Guardar la definición de fila

2.  Crear una nueva definición de columna     [![Crear una nueva definición de columna](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)

3.  Cree una nueva definición del informe a.    Haga clic en Configuración y desmarque [![Formulario de configuración](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)
   
4.  Genere el informe. 

5.  Exportar el informe a Excel.

### <a name="in-d365"></a>En D365: 
1.  Haga clic en Contabilidad general | Consultas e informes | Saldo de comprobación a.    Parámetros i.  Desde la fecha: inicio del ejercicio ii. Hasta la fecha: fecha en la que generó el informe para iii.    Conjunto de dimensiones financieras “Conjunto de cuenta principal” [![Formulario de cuenta principal](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)
      
  b.    Haga clic en Calcular

2.  Exportar el informe a Excel

Ahora debería poder copiar los datos desde el informe de Excel de FR al informe de saldo de comprobación de D365 y comparar las columnas "Saldo de cierre".


[!INCLUDE[footer-include](../../includes/footer-banner.md)]