---
title: P+F de restablecimiento de data mart
description: En este artículo se proporcionan respuestas a algunas preguntas más frecuentes sobre los restblecimientos de data mart.
author: jinniew
ms.date: 03/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.search.form: ''
ms.openlocfilehash: 949bf64fefe2dc70541eb5a94518d6b9fe1d3eb8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289918"
---
# <a name="data-mart-resets-faq"></a>P+F de restablecimiento de data mart

En este artículo se proporcionan respuestas a algunas preguntas más frecuentes sobre los restblecimientos de data mart. El restablecimiento de la despensa de datos puede ser un proceso que requiere mucho tiempo y, según las circunstancias, puede que no sea la solución necesaria. Por lo tanto, este artículo incluye información sobre circunstancias en las que un restablecimiento de la despensa de datos podría ayudar y también circunstancias en las que es poco probable que ayude.

## <a name="what-is-a-data-mart-reset"></a>¿Qué es un restablecimiento de data mart?

Un restablecimiento de la despensa de datos deshabilitará las tareas de integración, eliminará todos los datos de la despensa de datos y luego volverá a habilitar la integración.

Para asegurarse de que no se inserten datos antiguos, se puede iniciar un restablecimiento de la despensa de datos solo después de que se completen las tareas existentes. Si intenta restablecer la despensa de datos antes de que se completen todas las tareas, es posible que reciba un mensaje como, "El restablecimiento de la despensa de datos no se pudo procesar debido a una tarea activa. Vuelva a intentarlo más tarde".

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>¿Cuándo tengo que hacer un restablecimiento de data mart?

Si una o más de las siguientes afirmaciones se aplican a su situación, su organización puede beneficiarse de un restablecimiento de la despensa de datos:

- **La base de datos de la aplicación se restauró**
- **Ha abierto un vale de soporte**: un ingeniero de soporte le ha indicado que reinicie el data mart como parte de un paso de la solución de problemas.
- **Alto porcentaje de registros obsoletos**: los registros obsoletos por sí mismos no justifican necesariamente el restablecimiento del data mart. Los altos porcentajes de datos obsoletos pueden degradar la generación general de informes y el rendimiento de la integración, e incurrir en un uso adicional del espacio de la base de datos. Le recomendamos que complete un restablecimiento de datamart para eliminar los datos obsoletos cuando haya más del 80 % de datos obsoletos en el data mart.
 
> [!NOTE]
> El proceso de restablecimiento de una despensa de datos se ve afectado por la cantidad de transacciones presupuestarias y del libro mayor en su base de datos. Dependiendo de la cantidad de transacciones en su sistema, un restablecimiento de la despensa de datos se puede completar en tan solo 15 minutos o puede demorar hasta cuatro horas. Sin embargo, si su restablecimiento se retrasa más de cuatro horas, le recomendamos que contacte con el Soporte.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>¿Cuando es apropiado restablecer un data mart?

Aquí tiene algunas de las circunstancias en las que no recomendamos restablecer un data mart:

- Está experimentando problemas de rendimiento de integración de datos.
- Su integración con Financial Reporter no está habilitada. 

    - Esto significa que los datos de contabilidad general ya no se sincronizan con el datamart de Financial Reporting. Es posible que Financial Reporter no obtenga números actualizados para sus informes financieros. Esto suele ocurrir si lleva mucho tiempo sin usar Financial Reporter.
    - Se le pedirá que habilite la integración reiniciando el datamart. Para proceder, seleccione **Sí**. También puede optar por restablecer el data mart en otro momento. Una vez habilitada la integración, los datos de contabilidad general se sincronizan nuevamente en Financial Reporter. 
- Tiene un patrón de restablecimiento recurrente debido a alguna de las siguientes razones:

    - **Datos perdidos o inesperados en el informe**: si nota que faltan datos, abra un ticket de soporte con Microsoft para revisar el formato de su informe y los posibles problemas de sincronización de datos.
    - **Estado de integración atascado** - Si nota que el estado de la integración está atascado en ejecución, esto puede deberse a un gran volumen de transacciones en el sistema. Este estado se resolverá solo. Sin embargo, si nota que el estado de integración está atascado durante más de cuatro horas, abra una incidencia de soporte técnico con Microsoft. 
   
## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Si restablezco el data mart, ¿perderé los informes que ya diseñé?

No. Sus informes se almacenan en tablas SQL que no se ven afectadas por un restablecimiento de data mart. Si le preocupa perder los informes que ha diseñado, puede hacer una copia de seguridad de los diseños que no desea perder. Para hacer una copia de seguridad de los diseños, abra el diseñador de informes y vaya a **Empresa \> Empresas \> Bloques de creación \> Exportar**.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>¿Todos los usuarios tienen que salir del sistema antes de que pueda restablecer la despensa de datos?

No. Los usuarios pueden seguir trabajando en el sistema durante un restablecimiento de data mart. Sin embargo, no podrán acceder a los informes que se crearon con Financial Reporter hasta que finalice el restablecimiento.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
