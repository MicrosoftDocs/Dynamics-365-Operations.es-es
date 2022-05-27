---
title: Exportar datos de las filiales a archivos
description: Este tema explica cómo prepararse para exportar datos de Microsoft Dynamics 365 Finance y luego importarlos a una entidad jurídica consolidada.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 4df59938def317ad6ebc837104e20c4efa05005f
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713540"
---
# <a name="export-subsidiary-data-to-files"></a>Exportar datos de las filiales a archivos

[!include [banner](../includes/banner.md)]

Use la página **Exportar** (**Administración del sistema \> Espacios de trabajo \> Import/Export**) para prepararse para exportar datos subsidiarios a archivos que luego se pueden importar a una entidad legal consolidada. Para obtener más información sobre los procesos de importación y exportación, consulte [Resumen de tareas de importación y exportación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

1. Cree una entidad jurídica para el proceso de consolidación. Para obtener más información sobre cómo crear entidades jurídicas, consulte [Crear una entidad jurídica](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Para obtener más información, consulte [Preparar una entidad jurídica para su uso en el proceso de consolidación](prepare-company-for-consolidation.md) y [Establecer una entidad jurídica filial para la consolidación](set-up-subsidiary-company-for-consolidation.md). 

2. Vaya a **Consolidaciones \> Saldos de empresas exportadoras**. En la página **Saldos de empresas exportadoras**, en la pestaña **Criterios**, especifique los detalles de la consolidación, configurando los siguientes campos.

    | Campo                             | Descripción |
    |-----------------------------------|-------|
    | Cuenta principal                      | Especifique las cuentas a consolidar. Para incluir todas las cuentas, deje este campo en blanco. |
    | Usar cuenta de consolidación         | Si ha especificado cuentas de consolidación, establezca esta opción en **Sí**. |
    | Seleccionar cuenta de consolidación de | Seleccione **Cuenta principal** o **Grupo de cuentas de consolidación**. |
    | Grupo de cuentas de consolidación       | Seleccione un grupo de cuentas de consolidación para la cuenta de consolidación seleccionada. |
    | Período de consolidación              | Especifique las fechas "desde" y "hasta" para la consolidación. |
    | Incluir importes reales            | Establezca esta opción en **Sí** para incluir las cantidades reales. |
    | Incluir importes de presupuesto            | Establezca esta opción en **Sí** para incluir importes de presupuesto en las consolidaciones. |
    | Modelos presupuestarios                     | Especifique el modelo de presupuesto a incluir. |

3. En la pestaña **Dimensiones financieras**, especifique los detalles de la consolidación:

    - Especifique la información de dimensiones financieras que debe transferirse desde las transacciones en las cuentas filiales a las transacciones en la entidad jurídica consolidada.
    - Seleccione las dimensiones financieras en la lista.
    - Identificar la especificación correcta para cada dimensión financiera que se consolida. Las opciones disponibles incluyen **Dimensión**, **Dimensión de grupo**, **Cuentas de la empresa** y **Cuenta**.

        > [!NOTE]
        > La opción **Dimensión de grupo** le permite definir el valor de dimensión que utiliza el grupo de empresas que se está consolidando.

    - Especifique el orden de los segmentos en el que consolidar.

4. En la pestaña **Entidades legales**, siga estos pasos para especificar la entidad jurídica que está exportando:

    1. Seleccione **Nuevo**.
    2. En el campo **Entidad jurídica de origen**, introduzca la entidad jurídica.

        Si se aplican los mismos criterios a varias filiales que se encuentran en la misma base de datos, puede transferir datos desde dichas filiales a los archivos de exportación individuales en una sola operación:

        1. Cree una línea para cada entidad jurídica filial cuyas cuentas deben exportarse a los archivos. Estos archivos se importarán más adelante a la entidad jurídica consolidada.
        2. Para cada filial, especifique el nombre de la filial, así como el nombre del archivo de exportación que se creará durante la operación.

    3. En el campo **Tipo de cuenta de diferencias de conversión**, seleccione **Ganancia y perdida** o **Balance de situación**.
    4. Introduzca un nombre de archivo para el archivo de exportación que se creará.

5. Seleccione **Aceptar** para ejecutar la exportación.

Una vez completada la exportación, recibirá un mensaje que muestra el número de registros guardados en cada archivo. A continuación, puede importar los archivos a la entidad jurídica consolidada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
