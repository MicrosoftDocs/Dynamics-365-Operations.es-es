---
title: Configuración de segregación de controles
description: Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios.
author: maertenm
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 712cc90bef4f3ad56291e99edd9f963ae88add48
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143521"
---
# <a name="set-up-segregation-of-duties"></a>Configuración de segregación de controles

[!include [banner](../../includes/banner.md)]

Puede configurar reglas para tareas diferentes que deban llevar a cabo diferentes usuarios. Este concepto se denomina "segregación de controles". Por ejemplo, puede que no desee que sea la misma persona la que confirme la recepción de mercancías y procese el pago al proveedor. La segregación de controles ayuda a reducir el riesgo de fraude, y también ayuda a detectar errores o irregularidades. También puede usar la segregación de controles para aplicar directivas de control internas. Complete el siguiente procedimiento para crear una regla. Es necesario ser administrador del sistema para completar el procedimiento. La empresa de datos de demostración utilizada para crear este procedimiento es DAT. 

1. Vaya a **Panel de navegación > Módulos > Administración del sistema > Seguridad > Segregación de controles > Reglas de segregación de controles**.
2. Haga clic en **Nuevo**.
3. En el campo **Nombre** escriba un valor para la regla.
4. En el campo **Primer deber**, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, busque y seleccione el registro deseado. Seleccione el primer deber controlado por la regla.
6. En el campo **Segundo deber**, haga clic en el botón desplegable para abrir la búsqueda. 
7. En la lista, busque y seleccione el registro deseado. Seleccione el segundo deber controlado por la regla.
10. En el campo **Gravedad**, seleccione una opción. Seleccione la gravedad del riesgo que se genera cuando el mismo usuario o rol realiza ambos deberes.  
11. En el campo **Riesgo de seguridad**, escriba un valor. Escriba una descripción del riesgo para la seguridad.  
12. En el campo **Mitigación de seguridad**, escriba un valor. Escriba una descripción de las acciones para mitigar el riesgo de seguridad. Por ejemplo, puede mitigar el riesgo realizando revisiones más detalladas del proceso, realizando una revisión administrativa mensual o compartiendo recursos con otros departamentos.     
13. Haga clic en **Guardar**.

