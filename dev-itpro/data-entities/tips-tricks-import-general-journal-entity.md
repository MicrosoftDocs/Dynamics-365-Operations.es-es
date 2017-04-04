---
title: "Prácticas recomendadas para importar los asientos mediante la entidad general del diario"
description: Este tema proporciona sugerencias para importar datos al diario general mediante la entidad general del diario.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 81a52acd1d9baa12fcfe9d848441901894fa5682
ms.lasthandoff: 03/31/2017


---

# <a name="best-practices-for-importing-vouchers-using-the-general-journal-entity"></a>Prácticas recomendadas para importar los asientos mediante la entidad general del diario

Este tema proporciona sugerencias para importar datos al diario general mediante la entidad general del diario.  

Puede usar la entidad general del diario para importar los asientos de los que tenga una cuenta o un tipo de cuenta de contrapartida ** libro mayor, cliente, proveedor, o ** banco. El asiento se pueden especificar como una línea, mediante ambos ** cuenta ** el campo y ** cuenta de contrapartida ** campo, o como asiento multilínea, donde sólo ** ** cuenta se usa el campo (y ** cuenta de contrapartida ** se deja en blanco en cada línea). La entidad general del diario no admite cada tipo de cuenta. En su lugar, existen otras entidades para escenarios donde se requieren diferentes combinaciones de tipos de cuenta. Por ejemplo, para importar una transacción de proyecto, utilice la entidad del diario de gastos de proyectos. Están diseñados a cada entidad para admitir los escenarios de facturación específicos, que los campos adicionales de los medios disponibles en las entidades que dichas escenarios pero no en las partes a otra situación.

## <a name="setup"></a>Configuración
Antes de importar mediante la entidad general, valide la configuración siguiente:

-   ** La secuencia numérica configurada para el número de lote del diario - ** de forma predeterminada, al importar mediante la entidad general, el número de lote del diario usa la secuencia numérica que se define en los parámetros de contabilidad general. Si establece la secuencia numérica para el número de lote de diario en **Manual de**, no se aplica un número predeterminado. No se admite esta configuración.
-   ** La configuración de la dimensión financiera ** - Cada organización debe definir el pedido de dimensiones financieras cuando use a las entidades a las transacciones de importación. El orden se define para ** integración de las dimensiones contables ** el formato, en ** contabilidad general ** &gt; ** el plan contable ** &gt; ** las dimensiones ** &gt; ** configuración de la dimensión financiera para las aplicaciones de integración ** &gt; ** seleccionar las entidades de los datos **. Los segmentos de la cuenta contable que se importa deben tener el mismo orden. De lo contrario, se producirá un error durante la importación.

## <a name="general-journal-entity-setup"></a>Configuración de la entidad Diario general
Dos valores de administración de datos afectan a cómo se aplica el número o el número de asiento de lote del diario predeterminado:

-   ** procesamiento Establecer- basado en ** (la entidad de los datos)
-   ** Crear generado ** (en la asignación de campos)

Las secciones siguientes describen el efecto de esta configuración y también explican cómo se generan los números de lote de diario y los números de asiento.

### <a name="journal-batch-number"></a>Número de lote de diario

-   La configuración **Procesamiento basado en conjuntos** de la entidad Diario general no afecta a la forma en que se generan los números de lote del diario.
-   Si el campo **Número de lote de diario** se establece en **Generado automáticamente**, se crea un nuevo número de lote del diario para cada línea que se importa. No se recomienda este comportamiento. La configuración **Generado automáticamente** se encuentra en el proyecto de importación en **Ver mapa**, en la pestaña **Detalles de la asignación**.
-   Si el campo **Número de lote de diario** no se establece en **Generado automáticamente**, se crea el número de lote del diario de la siguiente manera.
    -   Si coincide con el número de lote de diario que se define en el archivo importado una existente, diario sin registrar en Microsoft Dynamics 365 para las operaciones, todas las líneas que tienen un número de lote de conciliación de diario se importan en el diario existente. Las líneas nunca se importan en un número de lote del diario registrado. En su lugar, se crea un nuevo número.
    -   Si no coincide con el número de lote de diario que se define en el archivo importado una existente, diario sin registrar en Dynamics 365 para las operaciones, todas las líneas que tienen el mismo número de lote del diario se agrupan sujetos a un nuevo diario. Por ejemplo, todas las líneas que tienen un número de lote del diario de 1 se importan a un diario nuevo y todas las líneas que tienen un número de lote del diario de 2 se importan en un segundo diario nuevo. El número de lote del diario se crea mediante la secuencia numérica que se define en los parámetros de Contabilidad General.

### <a name="voucher-number"></a>Número de asiento

-   Al utilizar la configuración **Procesamiento basado en conjuntos** en la entidad Diario general, se debe proporcionar el número de asiento en el archivo importado. Todas las transacciones del Diario general se asignan al número de asiento que se proporciona en el archivo importado, incluso si el asiento no está equilibrado. Si desea usar el procesamiento establecer- basado, pero también desea usar la secuencia numérica que se define para los números de asiento de Dynamics 365 para las operaciones, una sustitución se ha proporcionado para la liberación febrero de 2016. El número de revisión es 3170316 y está disponible para su descarga desde Lifecycle Services (LCS). Para obtener más información, consulte [Descargar revisiones desde Lifecycle Services](..\migration-upgrade\download-hotfix-lcs.md).
    -   Para habilitar esta funcionalidad, en el nombre del diario que se usa para importaciones de Dynamics 365 para las operaciones, establece ** asignación de números en el registro ** ** a Sí **.
    -   Todavía se debe definir un número de asiento en el archivo importado. Sin embargo, este número son temporales y se sobrescribirá con Dynamics 365 para el número de asiento de operaciones cuando se registra el diario. Debe asegurarse de que las líneas del diario se agrupan correctamente por número de asiento temporal. Por ejemplo, durante el registro, se encuentran tres líneas que tienen un número de asiento temporal de 1. El número de asiento temporal de las tres líneas se sobrescribirá con el siguiente número de la secuencia numérica. Si esas tres líneas no son una entrada equilibrada, el asiento no está registrado. A continuación, si se encuentran líneas que tienen un número de asiento temporal de 2, este número se sobrescribe con el siguiente número de asiento de la secuencia numérica, y así sucesivamente.

<!-- -->

-   Cuando no usa ** procesamiento Establecer- basado ** el valor, no debe proporcionar un número de asiento en el archivo importado. Los números de asiento que se crean durante la importación, en función de la configuración del nombre del diario (**Sólo un número de asiento**, **Según el saldo**, etc). Por ejemplo, si el nombre del diario se define como **Según el saldo**, la primera línea recibe un nuevo número de asiento predeterminado. El sistema evalúa entonces la línea para determinar si los débitos son iguales a los créditos. Si existe una cuenta de contrapartida en la línea, la línea siguiente importada recibe un nuevo número de asiento. Si no existe ninguna cuenta de contrapartida, el sistema evalúa si los débitos son iguales a los créditos conforme se importa cada línea nueva.
-   Si el campo **número de asiento** se establece en **Generado automáticamente**, la importación no será correcta. No se admite la configuración **Generado automáticamente** para el campo **Número de asiento**.

De forma predeterminada, la entidad Diario general utiliza el procesamiento basado en conjuntos. Después de evaluar los requisitos empresariales para su organización, puede cambiar la configuración **Procesamiento basado en conjuntos** haciendo clic en **Entidades de datos** en el área de trabajo **Administración de datos**. El procesamiento basado en conjuntos se utiliza para acelerar el proceso de importación. Si no utiliza el procesamiento basado en conjuntos, la importación de la entidad Diario general será más lenta.


