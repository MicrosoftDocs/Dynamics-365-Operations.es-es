---
title: Cuando restablecer un data mart
description: En este tema se enumeran las circunstancias que podrían mejorarse al restablecer un data mart y las circunstancias en las que es poco probable que el restablecimiento de su data mart resulte útil.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1c1524c7a1a3fbe71c51b23571996d87641cdf7e
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093221"
---
# <a name="when-to-reset-a-data-mart"></a>Cuando restablecer un data mart

El restablecimiento de un data mart puede llevar mucho tiempo. Dependiendo de las circunstancias, es posible que esta acción no sea la solución necesaria. En este tema se enumeran las circunstancias que podrían mejorarse al restablecer un data mart, así como las circunstancias en las que es poco probable que el restablecimiento de su data mart resulte útil.  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a>¿Cuándo necesita hacer restablecer un data mart?
Tenga en cuenta las siguientes preguntas antes de restablecer un data mart. Responder afirmativamente a una o más preguntas podría indicar que su organización puede beneficiarse al restablecer el data mart.

- La base de datos de aplicaciones se restauró, pero la base de datos de data mart no se restauró.
- Ve datos incorrectos para un período contable, que no es el resultado de un problema con el diseño del informe.
- Ve datos incorrectos para un período contable y los registros se enumeran en Intentos de integración en la página **Estado de integración** en el Diseñador de informes (inicie el Diseñador de informes y seleccione **Herramientas> Estado de integración**).
- Ha abierto un incidente de soporte y un ingeniero de soporte le ha indicado que reinicie el data mart como parte de un paso de la solución de problemas.
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a>¿Cuándo no es apropiado restablecer un data mart?
Hay algunas circunstancias en las que no recomendamos restablecer un data mart. Entre estas se incluyen las siguientes: 

- Siempre que el motivo no se mencione en este tema.
- Tiene problemas de rendimiento asociados a una sincronización de datos. En esta circunstancia, el restablecimiento del data mart probablemente no ayudará.
- Si tiene un patrón de restablecimiento recurrente debido a alguna de las siguientes razones: 
  - **Datos perdidos**: primero, elimine los problemas de diseño de informes y los problemas de tiempo de sincronización de datos; por ejemplo, observe que el mapa de hechos no se ha ejecutado desde que se publicaron los datos que faltan.
  - **Estado de integración atascado**: si la integración es lenta o parece bloqueada, es poco probable que el restablecimiento del data mart resuelva el problema.
  - **Los intentos de restablecimiento no han tenido éxito**: si se han realizado varios intentos de completar un restablecimiento y no han tenido éxito debido a que faltan datos, recomendamos abrir un incidente de soporte y trabajar con un ingeniero de soporte para analizar su situación antes de intentar restablecer el data mart nuevamente.
  - **Registros obsoletos**: los registros obsoletos por sí mismos no justifican necesariamente el restablecimiento del data mart. Si tiene un conjunto de datos grande, el proceso de restablecimiento tardará algún tiempo en ejecutarse, pero es poco probable que mejore.
 
## <a name="what-a-data-mart-reset-does-not-do"></a>Lo que no hace un restablecimiento de data mart  
- Un restablecimiento solo comenzará cuando se completen las tareas existentes. Esto garantizan que no se inserten datos antiguos. En este punto, es posible que vea un mensaje como, "El restablecimiento del data mart no se pudo procesar debido a una tarea activa. Vuelva a intentarlo más tarde".
- El restablecimiento deshabilitará las tareas de integración y eliminará todos los datos del data mart. Se vuelve a habilitar la integración.

> [!NOTE]
> Los siguientes puntos especifican dos cosas que el restablecimiento de un data mart *no* hará. <br>
> - Los restablecimientos no borran los diseños de informes. <br>
> - Los restablecimientos no borran los datos de la empresa o los datos del usuario a menos que se seleccionen.
