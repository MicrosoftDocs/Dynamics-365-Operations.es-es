---
title: Preguntas frecuentes sobre informes financieros
description: Este tema enumera preguntas relacionadas con los informes financieros que han tenido otros usuarios.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923034"
---
# <a name="financial-reporting-faq"></a>Preguntas frecuentes sobre informes financieros 

En este tema se proporcionan respuestas a las preguntas más frecuentes sobre los informes financieros. 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>¿Cómo puedo restringir el acceso a un informe mediante seguridad de árbol?

En el siguiente ejemplo se muestra cómo restringir el acceso a un informe mediante seguridad de árbol.

La empresa de demostración USMF tiene un informe de balance de situación al que no todos los usuarios de informes financieros deberían tener acceso. Para restringir el acceso, puede usar la seguridad de árbol para restringir el acceso a un solo informe, de modo que solo determinados usuarios puedan acceder al informe. Siga estos pasos para restringir el acceso: 

1. Inicie sesión en Financial Reporter Report Designer.
2. Cree una nueva definición de árbol. Vaya a **Archivo > Nuevo > Definición de árbol**.
3. Haga doble clic en la línea **Resumen** de la columna **Seguridad de la unidad**.
4. Seleccione **Usuarios y grupos**.  
5. Seleccione los usuarios o grupos a los que debe conceder acceso a este informe. 
6. Seleccione **Guardar**.
7. En la definición del informe, agregue su nueva definición de árbol.
8. En la definición del árbol, seleccione **Configuración**. En **Selección de unidad de informes**, seleccione **Incluir todas las unidades**.

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a>¿Cómo identifico qué cuentas no coinciden con mis saldos?

Si cuenta con un informe que no tiene saldos coincidentes, aquí hay algunos pasos que puede seguir para identificar cada una de las cuentas y desviaciones. 

**Financial Reporter Report Designer**
1. En Financial Reporter Report Designer, cree una nueva definición de fila. 
2. Seleccione **Editar > Insertar filas desde Dimensiones**.
3. Seleccione **MainAccount**.  
4. Seleccione **Aceptar**.
5. Guarde la definición de fila.
6. Cree una nueva definición de columna.
7. Cree una nueva definición de informe.
8. Seleccione **Ajustes** y desmarque esta opción.  
9. Genere el informe. 
10. Exporte el informe a Microsoft Excel.

**Dynamics 365 Finance** 
1. En Dynamics 365 Finance, vaya a **Contabilidad general > Consultas e informes > Saldo de comprobación**.
2. Configure los siguientes parámetros:
   - **Fecha inicial**: introduzca el inicio del ejercicio.
   - **Fecha final**: introduzca la fecha para la que está generando el informe.
   - **Dimensión financiera**: establezca este campo en **Conjunto de cuenta principal**.
 3. Seleccione **Calcular**.
 4. Exporte el informe a Microsoft Excel.

Ahora debería poder copiar los datos desde el informe de Excel de Financial Reporter al informe de saldo de comprobación, de modo que puede comparar las columnas **Saldo de cierre**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]