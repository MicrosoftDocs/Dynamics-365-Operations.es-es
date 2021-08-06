---
title: P+F de restablecimiento de data mart
description: En este tema se proporcionan respuestas a algunas preguntas más frecuentes sobre los restblecimientos de data mart.
author: jinniew
ms.date: 07/16/2021
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
ms.openlocfilehash: 90abe1fc3e84e0a9777f3eabd790a4b7e9b509c5
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638276"
---
# <a name="data-mart-resets-faq"></a>P+F de restablecimiento de data mart

En este tema se proporcionan respuestas a algunas preguntas más frecuentes sobre los restblecimientos de data mart. El restablecimiento de la despensa de datos puede ser un proceso que requiere mucho tiempo y, según las circunstancias, puede que no sea la solución necesaria. Por lo tanto, este tema incluye información sobre circunstancias en las que un restablecimiento de la despensa de datos podría ayudar y también circunstancias en las que es poco probable que ayude.

## <a name="what-is-a-data-mart-reset"></a>¿Qué es un restablecimiento de data mart?

Un restablecimiento de la despensa de datos deshabilitará las tareas de integración, eliminará todos los datos de la despensa de datos y luego volverá a habilitar la integración.

Para asegurarse de que no se inserten datos antiguos, se puede iniciar un restablecimiento de la despensa de datos solo después de que se completen las tareas existentes. Si intenta restablecer la despensa de datos antes de que se completen todas las tareas, es posible que reciba un mensaje como, "El restablecimiento de la despensa de datos no se pudo procesar debido a una tarea activa. Vuelva a intentarlo más tarde".

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>¿Cuándo tengo que hacer un restablecimiento de data mart?

Si una o más de las siguientes afirmaciones se aplican a su situación, su organización puede beneficiarse de un restablecimiento de la despensa de datos:

- La base de datos de la aplicación se restauró.
- Ha abierto un vale de soporte y un ingeniero de soporte le ha indicado que reinicie el data mart como parte de un paso de la solución de problemas.
 
> [!NOTE]
> El proceso de restablecimiento de una despensa de datos se ve afectado por la cantidad de transacciones presupuestarias y del libro mayor en su base de datos. Dependiendo de la cantidad de transacciones en su sistema, un restablecimiento de la despensa de datos se puede completar en tan solo 15 minutos o puede demorar hasta cuatro horas. Sin embargo, si su restablecimiento se retrasa más de cuatro horas, le recomendamos que contacte con el Soporte.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>¿Cuando es apropiado restablecer un data mart?

Aquí tiene algunas de las circunstancias en las que no recomendamos restablecer un data mart:

- Tiene problemas de rendimiento asociados con una sincronización de datos.
- Tiene un patrón de restablecimiento recurrente debido a alguna de las siguientes razones:

    - **Datos perdidos** - Si nota que faltan datos, abra un ticket de soporte con Microsoft para revisar el formato de su informe y los posibles problemas de sincronización de datos.
    - **Estado de integración atascado**
    - **Registros obsoletos**: los registros obsoletos por sí mismos no justifican necesariamente el restablecimiento del data mart. Si tiene un conjunto de datos grande, el proceso de restablecimiento tardará algún tiempo en ejecutarse, pero es poco probable que mejore.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Si restablezco el data mart, ¿perderé los informes que ya diseñé?

No. Sus informes se almacenan en tablas SQL que no se ven afectadas por un restablecimiento de data mart. Si le preocupa perder los informes que ha diseñado, puede hacer una copia de seguridad de los diseños que no desea perder. Para hacer una copia de seguridad de los diseños, abra el diseñador de informes y vaya a **Empresa \> Empresas \> Bloques de creación \> Exportar**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>¿Todos los usuarios tienen que salir del sistema antes de que pueda restablecer la despensa de datos?

No. Los usuarios pueden seguir trabajando en el sistema durante un restablecimiento de data mart. Sin embargo, no podrán acceder a los informes que se crearon con Financial Reporter hasta que finalice el restablecimiento.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
