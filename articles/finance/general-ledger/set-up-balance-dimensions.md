---
title: ¿Cómo configuro las dimensiones financieras de equilibrio?
description: Este artículo describe las opciones para configurar y utilizar la función Equilibrar la dimensión financiera.
author: kweekley
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-08-17
ms.dyn365.ops.version: 10.0.210
ms.openlocfilehash: dd859629b0eb9f14fa4907699613382f3897d21d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878023"
---
# <a name="how-do-i-set-up-balancing-financial-dimensions"></a>¿Cómo configuro las dimensiones financieras de equilibrio?

[!include [banner](../includes/banner.md)]

Este artículo describe las opciones para configurar y utilizar la función Equilibrar la dimensión financiera.

## <a name="symptom"></a>Síntoma

Hay dos opciones para configurar las dimensiones financieras de equilibrio. La primera opción es utilizar el campo **Equilibrio de la dimensión financiera** en la página de configuración **Libro mayor** (**Libro mayor \> Configuración del libro mayor \> Libro mayor**). La segunda opción es usar el campo **Requerir que la dimensión se equilibre** en la página **Dimensioens financieras** (**Libro mayor > Plan de cuentas \> Dimensiones \> Conjuntos de dimensiones financieras**). Este artículo explica la diferencia entre estas dos opciones.

## <a name="resolution"></a>Resolución

Las organizaciones suelen utilizar dimensiones de equilibrio para generar un balance que está equilibrado en el nivel de la dimensión financiera. Habilitar cualquiera de las funciones no equilibrará las dimensiones desequilibradas publicadas. Primero debe ingresar los asientos de ajuste manualmente para equilibrar el balance antes de habilitar cualquiera de las funciones.

Las dos opciones no se excluyen mutuamente. La opción que utiliza su organización debe basarse en los requisitos de su negocio. A menudo escuchamos sobre clientes que definen la dimensión de equilibrio tanto en la configuración del libro mayor como en la configuración de la dimensión financiera, y luego completan parte o toda la configuración adicional que se requiere. Sin embargo, todavía no pueden publicar debido a un desequilibrio en el nivel de la dimensión financiera.

Las siguientes secciones describen las dos opciones y explican cómo configurarlas.

### <a name="ledger--balancing-financial-dimension"></a>Libro mayor: dimensión financiera de equilibrio

La dimensión de equilibrio en la página **Libro mayor** se utiliza para habilitar la contabilidad entre unidades. Siga estos pasos para activar la funcionalidad.

1. Determine qué dimensión financiera será la dimensión de equilibrio.

    - Esta funcionalidad le permite seleccionar solo una dimensión financiera como dimensión de equilibrio.
    - No seleccione todavía la dimensión en la página de configuración **Libro mayor**.
    - Asegúrese de que su balance ya esté equilibrado para la dimensión financiera seleccionada.

2. Actualice la estructura de la cuenta para la dimensión financiera de compensación.

    - La dimensión financiera de equilibrio debe incluirse en todas las estructuras contables que están asignadas al libro mayor.
    - La dimensión financiera no debe permitir espacios en blanco en la estructura contable. Esta restricción asegura que cada asiento contable que se contabiliza en el Libro mayor contiene un valor de dimensión financiera. Una dimensión en blanco no es válida cuando se utilizan dimensiones de equilibrio.

3. En la página **Cuentas para transacciones automáticas** (**Libro mayor \> Configuración de publicación \> Cuentas para transacciones automáticas**), define las principales cuentas de débito y crédito entre unidades.
4. En la página de configuración **Libro Mayor** (**Libro mayor \> Configuración del libro mayor \> Libro mayor**), en el campo **Equilibrio de la dimensión financiera**, seleccione una dimensión financiera para usar para el equilibrio.

Si la dimensión financiera seleccionada no está equilibrada cuando se ingresan y registran las transacciones, el sistema agregará automáticamente las entradas de débito o crédito que se requieren para equilibrar la entrada de contabilidad durante la contabilización. Las cuentas del libro mayor de débito y crédito para la transacción entre unidades se muestran en el comprobante registrado en el libro mayor. Sin embargo, no se mostrarán en los diarios o documentos fuente para los que se publicaron los asientos contables.

### <a name="financial-dimensions--require-the-dimension-to-be-balanced"></a>Dimensiones financieras: requieren que la dimensión esté equilibrada

Aunque la dimensión de equilibrio en la página **Dimensiones financieras** es utilizada normalmente por empresas del sector público, la funcionalidad no está vinculada a ninguna clave de configuración del sector público. Debido a que no existe ninguna limitación en el sistema, puede utilizar esta funcionalidad incluso si su organización no es una entidad del sector público.

Esta funcionalidad se utiliza normalmente en la base de clientes del sector público porque requiere que se utilicen definiciones de contabilización para equilibrar automáticamente cada transacción. No utiliza las cuentas de débito y crédito entre unidades que se definen en la página **Cuentas para transacciones automáticas** para equilibrar automáticamente los asientos contables. Si una entrada de contabilidad no se equilibra en el nivel de dimensión después de que se aplican las definiciones de contabilización, la transacción no se contabilizará, incluso si se definen las cuentas de débito y crédito entre unidades.

A menudo escuchamos sobre clientes que definen la dimensión de equilibrio tanto en la configuración del libro mayor como en la configuración de la dimensión financiera. En este caso, el sistema utiliza la funcionalidad de dimensiones financieras. La configuración para equilibrar dimensiones a nivel de dimensión financiera tiene prioridad durante la contabilización. La contabilización fallará si la definición de contabilización no crea un asiento contable equilibrado en el nivel de la dimensión financiera.

Siga estos pasos para activar el uso de una dimensión de equilibrio en el nivel de la dimensión financiera.

1. Determine qué dimensiones financieras serán las dimensiones de equilibrio.

    - Puede establecer más de una dimensión financiera como dimensión de equilibrio.
    - Aún no establezca las dimensiones financieras que serán necesarias para equilibrar una transacción en la página **Dimensiones financieras**.

2. Defina las definiciones de publicación para cada tipo de diario o documento fuente utilizado por su organización. Las definiciones de contabilización consumen las cuentas del libro mayor de un diario o documento de origen no contabilizado como "criterios de coincidencia". La definición de contabilización devuelve los 'asientos generados' que se convierten en el asiento contable. Si la definición de contabilización está configurada correctamente, la entrada generada incluye las cuentas del libro mayor de criterios de coincidencia, además de cuentas adicionales para equilibrar la entrada contable a nivel de dimensión. Para obtener más información, consulte [Definiciones de contabilización](posting-definitions.md). 
   
   La publicación de definiciones no es compatible con todos los tipos de transacciones. Por ejemplo, las definiciones de contabilización no se pueden definir para ninguna transacción ingresada a través del diario general o del diario de activos fijos. Si no se puede definir una definición de contabilización para un diario o un documento de origen, la transacción debe equilibrarse manualmente en el valor de la dimensión financiera. Por ejemplo, si se realiza un asiento de diario general y la dimensión Departamento es la dimensión de equilibrio, debe asegurarse de que el valor de cada departamento esté equilibrado.  Si la dimensión no está equilibrada para cada valor de departamento, el comprobante no se contabilizará hasta que se corrija el desequilibrio agregando manualmente un débito o crédito entre unidades al comprobante. 

    > [!IMPORTANT]
    > Si se debe equilibrar manualmente un número excesivo de transacciones, **no** debe utilizar la funcionalidad de la dimensión de equilibrio en la página **Dimensiones financieras**. En su lugar, utilice la funcionalidad de dimensión de equilibrio en la página de configuración **Libro mayor**.

3. Una vez definidas las definiciones de contabilización, las dimensiones financieras se pueden marcar como necesarias para el balance.

A medida que ingresa y contabiliza transacciones, las definiciones de contabilización se llaman durante la contabilización para determinar los asientos contables. Si las dimensiones financieras están equilibradas, la validación se produce después de que se hayan determinado los asientos contables. Si las dimensiones financieras no están equilibradas, la transacción no se contabilizará y recibirá un mensaje que indica que los débitos no son iguales a los créditos para una dimensión específica.
