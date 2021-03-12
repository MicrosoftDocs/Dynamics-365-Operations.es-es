---
title: Importar datos de las filiales desde archivos
description: Este tema explica cómo preparar los datos de sistemas externos para que se puedan importar en Microsoft Dynamics 365 Finance.
author: jinniew
manager: AnnBe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 7ced1b970aefa20a27ab16e005dff8fabace78d1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988834"
---
# <a name="import-subsidiary-data-from-files"></a>Importar datos de las filiales desde archivos

[!include [banner](../includes/banner.md)]

Este tema explica cómo preparar los datos de sistemas externos para que se puedan importar en Microsoft Dynamics 365 Finance. Debe usar la página **Consolidar con importación** (**Consolidaciones \> Consolidar con importación**) para preparar la transferencia de los datos de filiales desde sistemas externos.

1. Cree una entidad jurídica filial para el proceso de consolidación. Para obtener más información sobre cómo crear entidades jurídicas, consulte [Crear una entidad jurídica](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Para obtener más información, consulte [Preparar una entidad jurídica para su uso en el proceso de consolidación](prepare-company-for-consolidation.md) y [Establecer una entidad jurídica filial para la consolidación](set-up-subsidiary-company-for-consolidation.md).

2. Prepare un archivo con los datos que se van a importar. Para obtener más información sobre el proceso de importación, consulte [Visión general de los trabajos de exportación e importación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).
3. Exporte los datos a un archivo siguiendo los pasos del procedimiento "Proceso de importación/exportación de datos" en [Visión general de los trabajos de exportación e importación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md). Puede utilizar ese procedimiento para consolidar datos de otra instancia de Dynamics 365 Finance o de Dynamics 365 Business Central. Si va a importar datos de sistemas externos, los datos deben tener el formato que se describe en [Exportar datos de filial a archivos](export-subsidiary-data-to-file.md).
4. Vaya a **Consolidaciones \> Consolidar con importación**. En la página **Consolidar con importación**, en la pestaña **Criterios**, especifique los detalles del informe o la importación estableciendo los valores de los siguientes campos.

    | Campo                                 | Valor para el informe | Valor para la importación |
    |---------------------------------------|----------------------|----------------------|
    | Descripción                           | No aplicable | Escriba una descripción para identificar la importación. |
    | Cuenta principal                          | Defina el rango de cuentas que el informe debe incluir. Si no define un rango, se incluirán todas las cuentas. | Defina el rango de cuentas que la importación debe incluir. Si no define un rango, se incluirán todas las cuentas. |
    | Período de consolidación                  | Defina el rango de fechas para consolidar. | Defina el rango de fechas para consolidar. |
    | Incluir importes reales                | Establezca esta opción en **Sí** para incluir datos reales. | Establezca esta opción en **Sí** para incluir datos reales. |
    | Incluir importes de presupuesto                | Establezca esta opción en **Sí** para incluir importes de presupuesto en las consolidaciones. | Establezca esta opción en **Sí** para incluir importes de presupuesto en las consolidaciones. |
    | Reconstruir saldos durante la consolidación | Establezca esta opción en **Sí** si el proceso de reconstrucción debe borrar completamente el saldo y los nuevos registros, y volver a crear el saldo desde el principio. | Establezca esta opción en **Sí** si el proceso de reconstrucción debe borrar completamente el saldo y los nuevos registros, y volver a crear el saldo desde el principio. |
    | Modelos presupuestarios                         | No aplicable | Si seleccionó importar los importes presupuestarios, introduzca los modelos presupuestarios para consolidar. |
    | Tipo de tasa presupuestaria                      | No aplicable | Especifique el tipo de cambio de presupuesto. |

6. Si tiene distintas divisas contables, use los campos de la pestaña **Conversión de divisas** para configurar la conversión que se realizará durante la consolidación.

    | Campo                      | Descripción |
    |----------------------------|-------------|
    | Entidad jurídica de origen        | Seleccione la entidad jurídica desde la que está importando. |
    | Divisa de contabilidad de origen | Esta divisa predeterminada es la divisa asociada con la entidad jurídica de origen que seleccionó en el campo **Entidad jurídica de origen**. |
    | Cuentas De y cuentas A       | Defina el rango de cuentas que se van a importar desde la entidad jurídica de origen. |
    | Tipo de cambio         | Seleccione el tipo de cambio. Los tipos de cambio se asignan al crear una cuenta principal. Para obtener más información, consulte [Crear una cuenta principal](tasks/create-main-account.md). |
    | Aplicar tipo de cambio de   | Introduzca una fecha para aplicar el tipo de cambio vigente en esa fecha. Como alternativa, especifique el valor que se debe usar como tipo de cambio. |
    | Tipo de cambio              | El valor predeterminado depende del tipo de cambio seleccionado en el campo **Tipo de cambio**. Si específico un tipo de cambio definido por el usuario, puede definir una tasa. |

7. Establezca la opción **Ejecutar en segundo plano** en **Sí** para permitir que el proceso de importación se ejecute en segundo plano.
8. Establezca la opción **Procesamiento por lotes** en **Sí** para ejecutar la consolidación como un trabajo por lotes en un momento específico. Para ejecutar la consolidación inmediatamente, seleccione **Aceptar**. 

Las transacciones y los saldos especificados para la consolidación en las filiales se agregan a las cuentas apropiadas de la entidad jurídica consolidada.
