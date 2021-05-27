---
title: Cuando restablecer un data mart
description: En este tema se enumeran las circunstancias que podrían mejorarse al restablecer un data mart y las circunstancias en las que es poco probable que el restablecimiento de su data mart resulte útil.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "5989001"
---
# <a name="when-to-reset-a-data-mart"></a>Cuando restablecer un data mart

El restablecimiento de un data mart puede llevar mucho tiempo. Dependiendo de las circunstancias, es posible que esta acción no sea la solución necesaria. En este tema se enumeran las circunstancias que podrían mejorarse al restablecer un data mart, así como las circunstancias en las que es poco probable que el restablecimiento de su data mart resulte útil.  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a>¿Cuándo necesito hacer un restablecimiento de data mart?
Tenga en cuenta las siguientes preguntas antes de restablecer un data mart. Responder afirmativamente a una o más preguntas podría indicar que su organización puede beneficiarse al restablecer el data mart.

- ¿Se restableció la base de datos de la aplicación?
- ¿Ha abierto un incidente de soporte y un ingeniero de soporte le ha indicado que reinicie el data mart como parte de un paso de la solución de problemas?
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a>¿Cuándo no es apropiado restablecer un data mart?
Hay algunas circunstancias en las que no recomendamos restablecer un data mart. Entre estas se incluyen las siguientes: 

- Tiene problemas de rendimiento asociados con una sincronización de datos. 
- Si tiene un patrón de restablecimiento recurrente debido a alguna de las siguientes razones: 
  - **Datos perdidos** 
  - **Estado de integración atascado** 
  - **Registros obsoletos**: los registros obsoletos por sí mismos no justifican necesariamente el restablecimiento del data mart. Si tiene un conjunto de datos grande, el proceso de restablecimiento tardará algún tiempo en ejecutarse, pero es poco probable que mejore.
 
## <a name="what-is-a-data-mart-reset"></a>¿Qué es un restablecimiento de data mart?
- Un restablecimiento solo comenzará cuando se completen las tareas existentes. Esto garantizan que no se inserten datos antiguos. En este punto, es posible que vea un mensaje como, "El restablecimiento del data mart no se pudo procesar debido a una tarea activa. Vuelva a intentarlo más tarde".
- El restablecimiento deshabilitará las tareas de integración y eliminará todos los datos del data mart. Se vuelve a habilitar la integración.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Si restablezco el data mart, ¿perderé los informes que ya diseñé? 
No, sus informes se almacenan en tablas SQL que no se ven afectadas por un restablecimiento de data mart. Si le preocupa perder los informes que ha diseñado, puede hacer una copia de seguridad de los diseños que no desea perder. Para hacer una copia de seguridad, abra el diseñador de informes y vaya a **Empresa > Empresas > Bloques de creación > Exportar**.
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a>¿Es necesario que todos los usuarios salgan del sistema para restablecer el data mart?
No, los usuarios pueden seguir trabajando en el sistema al restablecer el data mart. Sin embargo, no podrán acceder a los informes que se crearon con Financial Reporter hasta que finalice el restablecimiento. 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
