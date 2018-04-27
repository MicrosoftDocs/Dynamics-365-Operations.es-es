--- 
title: "Configuración de segregación de controles"
description: Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.
author: maertenm
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 754f28cd2831d8a9a57c408518d240de460b732b
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-segregation-of-duties"></a>Configuración de segregación de controles

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios. Este concepto se denomina "segregación de controles". Por ejemplo, puede que no desee que sea la misma persona la que confirme la recepción de mercancías y procese el pago al proveedor. La segregación de controles ayuda a reducir el riesgo de fraude, y también ayuda a detectar errores o irregularidades. También puede usar la segregación de controles para aplicar directivas de control internas. Complete el siguiente procedimiento para crear una regla. Es necesario ser administrador del sistema para completar el procedimiento. La empresa de datos de demostración utilizada para crear este procedimiento es DAT. 

1. Vaya a Administración del sistema > Seguridad > Segregación de controles > Reglas de segregación de controles.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
    * Especifique un nombre para la regla.  
4. En el campo Primer deber, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, busque y seleccione el registro deseado.
    * Seleccione el primer deber controlado por la regla.  
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. En el campo Segundo deber, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, busque y seleccione el registro deseado.
    * Seleccione el segundo deber controlado por la regla.  
9. En la lista, haga clic en el vínculo de la fila seleccionada.
10. En el campo Gravedad, seleccione una opción.
    * Seleccione la gravedad del riesgo que se genera cuando el mismo usuario o rol realiza ambos deberes.  
11. En el campo Riesgo de seguridad, escriba un valor.
    * Escriba una descripción del riesgo para la seguridad.  
12. En el campo Mitigación de seguridad, escriba un valor.
    * Escriba una descripción de las acciones para mitigar el riesgo de seguridad. Por ejemplo, puede mitigar el riesgo realizando revisiones más detalladas del proceso, realizando una revisión administrativa mensual o compartiendo recursos con otros departamentos.  
13. Haga clic en Guardar.


