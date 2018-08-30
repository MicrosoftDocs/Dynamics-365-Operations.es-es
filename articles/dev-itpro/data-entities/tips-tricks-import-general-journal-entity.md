---
title: Procedimientos recomendados para importar asientos mediante la entidad Diario general
description: Este tema ofrece sugerencias para importar datos en el Diario general mediante la entidad Diario general.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 7bc24b5e3bc13d6dbb4313f25ff44d8fae0998cc
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="best-practices-for-importing-vouchers-by-using-the-general-journal-entity"></a>Procedimientos recomendados para importar asientos mediante la entidad Diario general

[!include [banner](../includes/banner.md)]

Este tema ofrece sugerencias para importar datos en el Diario general mediante la entidad Diario general.  

Puede utilizar la entidad Diario General para importar asientos que tengan un tipo de cuenta o tipo de cuenta de contrapartida **Contabilidad, Cliente, Proveedor o Banco**. El asiento se pueden especificar como una línea, mediante el campo **Cuenta** y **Cuenta de contrapartida**, o como asiento multilínea, donde solo se usa el campo **Cuenta** (y **Cuenta de contrapartida** se deja en blanco en cada línea). La entidad Diario general no admite todos los tipos de cuenta. En su lugar, existen otras entidades para escenarios donde se requieren diferentes combinaciones de tipos de cuenta. Por ejemplo, para importar una transacción de proyecto, utilice la entidad Diario de gastos de proyecto. Cada entidad está diseñada para admitir escenarios específicos, es decir, pueden mostrar campos adicionales para un escenario que no se muestran en otros escenarios.

## <a name="setup"></a>Configuración
Antes de importar con la entidad Diario general, valide la siguiente configuración:

-   **Configuración de secuencia numérica para el número de lote del diario**: de forma predeterminada, al importar con la entidad Diario general, el número de lote de diario utiliza la secuencia numérica que se define en los parámetros de Contabilidad general. Si establece la secuencia numérica para el número de lote de diario en **Manual de**, no se aplica un número predeterminado. No se admite esta configuración.
-   **Configuración de la dimensión financiera**: cada organización debe definir el orden de las dimensiones financieras cuando las entidades se utilizan para importar transacciones. El orden se define para el formato **Integración de dimensiones contables**, en **Contabilidad general** &gt; **Plan contable** &gt; **Dimensiones** &gt; **Configuración de la dimensión financiera para la integración de aplicaciones** &gt; **Seleccionar entidades de datos**. Los segmentos de la cuenta contable que se importa deben tener el mismo orden. De lo contrario, se producirá un error durante la importación.

## <a name="general-journal-entity-setup"></a>Configuración de la entidad Diario general
Dos valores de administración de datos afectan a cómo se aplica el número de lote del diario o el número de asiento predeterminado:

-   **Procesamiento basado en conjuntos** (en la entidad de datos)
-   **Generado automáticamente** (en la asignación de campos)

Las secciones siguientes describen el efecto de esta configuración y también explican cómo se generan los números de lote de diario y los números de asiento.

### <a name="journal-batch-number"></a>Número de lote de diario

-   La configuración **Procesamiento basado en conjuntos** de la entidad Diario general no afecta a la forma en que se generan los números de lote del diario.
-   Si el campo **Número de lote de diario** se establece en **Generado automáticamente**, se crea un nuevo número de lote del diario para cada línea que se importa. No se recomienda este comportamiento. La configuración **Generado automáticamente** se encuentra en el proyecto de importación en **Ver mapa**, en la pestaña **Detalles de la asignación**.
-   Si el campo **Número de lote de diario** no se establece en **Generado automáticamente**, se crea el número de lote del diario de la siguiente manera.
    -   Si el número de lote del diario que se define en el archivo importado coincide con un diario no registrado existente, todas las líneas con un número de lote de diario coincidente se importan en el diario existente. Las líneas nunca se importan en un número de lote del diario registrado. En su lugar, se crea un nuevo número.
    -   Si el número de lote del diario que se define en el archivo importado no coincide con un diario no registrado existente, todas las líneas con el mismo número de lote de diario se agrupan en un diario nuevo. Por ejemplo, todas las líneas que tienen un número de lote del diario de 1 se importan a un diario nuevo y todas las líneas que tienen un número de lote del diario de 2 se importan en un segundo diario nuevo. El número de lote del diario se crea mediante la secuencia numérica que se define en los parámetros de Contabilidad General.

### <a name="voucher-number"></a>Número de asiento

-   Al utilizar la configuración **Procesamiento basado en conjuntos** en la entidad Diario general, se debe proporcionar el número de asiento en el archivo importado. Todas las transacciones del Diario general se asignan al número de asiento que se proporciona en el archivo importado, incluso si el asiento no está equilibrado. Si desea utilizar el procesamiento basado en conjuntos, pero desea utilizar la secuencia numérica que se define para los números de asiento, se ha proporcionado una revisión para la versión de febrero de 2016. El número de revisión es 3170316 y está disponible para su descarga desde Lifecycle Services (LCS). Para obtener más información, consulte [Descargar revisiones desde Lifecycle Services](../migration-upgrade/download-hotfix-lcs.md).
    -   Para habilitar esta funcionalidad, en el nombre del diario que se usa para las importaciones, establezca **Asignación numérica en el registro** en **Sí**.
    -   Todavía se debe definir un número de asiento en el archivo importado. Sin embargo, este número es temporal y se sobrescribe por el número de asiento cuando se registra el diario. Debe asegurarse de que las líneas del diario se agrupan correctamente por número de asiento temporal. Por ejemplo, durante el registro, hay tres líneas que tienen un número de asiento temporal de 1. El número de asiento temporal de las tres líneas se sobrescribirá con el siguiente número de la secuencia numérica. Si esas tres líneas no son una entrada equilibrada, el asiento no está registrado. A continuación, si se encuentran líneas que tienen un número de asiento temporal de 2, este número se sobrescribe con el siguiente número de asiento de la secuencia numérica, y así sucesivamente.

<!-- -->

-   Cuando no se utiliza la configuración **Procesamiento basado en conjuntos**, no debe proporcionar ningún número de asiento en el archivo importado. Los números de asiento que se crean durante la importación, en función de la configuración del nombre del diario (**Sólo un número de asiento**, **Según el saldo**, etc). Por ejemplo, si el nombre del diario se define como **Según el saldo**, la primera línea recibe un nuevo número de asiento predeterminado. El sistema evalúa entonces la línea para determinar si los débitos son iguales a los créditos. Si existe una cuenta de contrapartida en la línea, la línea siguiente importada recibe un nuevo número de asiento. Si no existe ninguna cuenta de contrapartida, el sistema evalúa si los débitos son iguales a los créditos conforme se importa cada línea nueva.
-   Si el campo **número de asiento** se establece en **Generado automáticamente**, la importación no será correcta. No se admite la configuración **Generado automáticamente** para el campo **Número de asiento**.

De forma predeterminada, la entidad Diario general utiliza el procesamiento basado en conjuntos. Después de evaluar los requisitos empresariales para su organización, puede cambiar la configuración **Procesamiento basado en conjuntos** haciendo clic en **Entidades de datos** en el área de trabajo **Administración de datos**. El procesamiento basado en conjuntos se utiliza para acelerar el proceso de importación. Si no utiliza el procesamiento basado en conjuntos, la importación de la entidad Diario general será más lenta.




