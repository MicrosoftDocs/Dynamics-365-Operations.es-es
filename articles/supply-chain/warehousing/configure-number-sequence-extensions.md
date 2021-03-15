---
title: Configurar secuencias numéricas para flujos de almacén
description: Este tema proporciona una descripción general de la funcionalidad que ofrece extensiones de secuencia numérica para identificaciones de matrículas, identificaciones de etiquetas de oleada, identificaciones de contenedores e identificaciones de conocimiento de embarque.
author: GarmMSFT
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSNumberSequenceExt
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: fa4074c23baa74983f4922d2d09d7da81c943bfe
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973844"
---
# <a name="configure-number-sequences-for-warehouse-flows"></a>Configurar secuencias numéricas para flujos de almacén

[!include [banner](../includes/banner.md)]

La característica *Extensiones de secuencia numérica* agrega una nueva página de configuración para configurar secuencias numéricas. Permite la configuración flexible de ID regulados por GS1, incluidos los prefijos GS1 y los dígitos de control (módulo 10), y aplica un límite de longitud en las secuencias numéricas existentes.

Los segmentos de secuencia numérica estándar no son adecuados para la implementación de GS1, porque no se calcula ningún dígito de control y el prefijo GS1 de la compañía debe actualizarse manualmente.

Esta característica agrega la siguiente funcionalidad:

- Los ID de conocimiento de embarque (BOL) se pueden generar por adelantado.
- Se puede generar una secuencia numérica única para los números de código de contenedor de envío en serie (SSCC).
- Se pueden crear secuencias de números compatibles con GS1 para los números BOL y SSCC. La característica agrega compatibilidad inmediata para los ID de matrículas, ID de contenedores, ID de etiquetas de oleada e ID de BOL.
- La configuración de los números de identificación de matrícula es flexible. Por ejemplo, puede incluir o excluir los identificadores de aplicaciones (IA), como los ceros iniciales (00).

Esta funcionalidad hace que sea más eficiente admitir el etiquetado de cajas de cartón y ajustar los nuevos números que genera el sistema.

## <a name="turn-on-the-number-sequence-extensions-feature"></a>Active la característica de extensiones de secuencia numérica

Antes de poder usar la característica debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de característica:** *Extensiones de secuencia numérica*

## <a name="set-up-the-feature"></a>Configuración de la característica

Para configurar extensiones de secuencia numérica en su sistema, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la pestaña **General**, en el campo **Prefijo GS1 de la empresa** ingrese el prefijo GS1 de su empresa. Este valor afectará a todas las secuencias numéricas donde el prefijo GS1 se incluye como un segmento.
1. Si desea generar números BOL para etiquetas de oleada, en la pestaña **Informes**, seleccione la casilla de verificación **Generar número de BOL al imprimir etiquetas de oleada**.

    > [!NOTE]
    > Esta casilla de verificación solo está disponible si la funcionalidad para [impresión de etiquetas de oleada](configure-wave-label-printing.md) está activada.

1. Vaya a **Gestión de almacenes** \> **Configuración** \> **Extensiones de secuencia numérica**
1. En el panel de acciones, seleccione **Crear configuración predeterminada**. Se crean una secuencia numérica BOL compatible con GS1 y tres tipos de secuencias numéricas SSCC. Todas estas secuencias numéricas tienen en cuenta la longitud del prefijo GS1 de su empresa.

    Para obtener más información sobre cómo personalizar estas secuencias numéricas predeterminadas y/o agregar nuevas secuencias, consulte la siguiente sección. También puede eliminar cualquiera de estas secuencias si no las necesita.

1. Vuelva a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la pestaña **Secuencias numéricas**, seleccione una extensión de secuencia de números relevante que usará para generar números para sus ID de matrícula, ID de etiqueta de oleada, ID de contenedor (en este caso, seleccione la secuencia **Número SSCC-18** apropiada) y/o ID de BOL (en este caso, seleccione la secuencia **BOL**). De forma predeterminada, las extensiones de secuencia numérica solo son compatibles con estos cuatro tipos de ID.

La próxima vez que se genere un nuevo número para una de estas secuencias numéricas, se utilizará la nueva lógica.

> [!NOTE]
> Si no selecciona una extensión de secuencia numérica para las ID de matrícula, se utilizarán las reglas actuales para generar los ID de matrícula. De lo contrario, se usará la secuencia numérica seleccionada. Las otras ID utilizarán una secuencia numérica simple hasta que se les aplique una extensión de secuencia numérica.

## <a name="create-and-edit-number-sequences"></a>Crear y editar secuencias numéricas

En la sección anterior, generó un conjunto predeterminado de secuencias numéricas. Esta sección explica cómo se define cada secuencia numérica. También explica cómo crear secuencias personalizadas y cómo editar las secuencias predeterminadas o personalizadas.

Para crear y editar secuencias numéricas, siga estos pasos.

1. Vaya a **Gestión de almacenes** \> **Configuración** \> **Extensiones de secuencia numérica**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el campo **Extensión de secuencia numérica**, escriba el nombre de la nueva secuencia. En el campo **Descripción**, escriba una descripción.
1. En la ficha desplegable **Segmentos**, use los botones en la barra de herramientas para ensamblar su formato de numeración agregando, eliminando y organizando los segmentos. En el campo **Segmento** de cada fila, asigne un tipo de segmento para definir el propósito y el contenido de ese segmento. En la tabla siguiente se describen los tipos de segmentos disponibles.

    | Tipo de segmento | Descripción |
    |---|---|
    | Constante | Este tipo de segmento agrega el mismo texto constante a cada número generado en la secuencia. En el campo **Valor**, escriba el texto necesario. El campo **Longitud** se actualiza automáticamente a la longitud del texto introducido en el campo **Valor**. |
    | Secuencia numérica | En el campo **Valor**, escriba un signo de número (*\#*) para cada carácter que debe mostrarse en la secuencia generada. La secuencia numérica en sí misma puede generar números más largos, pero solo se mostrarán los caracteres más a la derecha. El campo **Longitud** se actualiza automáticamente al número o los signos de número introducidos en el campo **Valor**.<p>Para cumplir con los requisitos de GS1 en los números SSCC-18, asegúrese de que la longitud de este segmento sea 16 menos la longitud de su prefijo GS1.</p> |
    | Prefijo GS1 | Este tipo de segmento agrega el valor que se establece en el campo **Prefijo GS1 de la empresa** en la página **Parámetros de gestión de almacenes**. El campo **Valor** muestra el valor establecido en la página **Parámetros de gestión de almacenes** y el campo **Longitud** muestra el número de caracteres en el valor. Tanto el campo **Valor** como el campo **Longitud** son de solo lectura. |
    | Identificador de la aplicación | En el campo **Valor**, escriba un identificador de aplicación, según lo especificado en la política GS1 relevante para este tipo de secuencia numérica. Por ejemplo, introduzca *00* para SSCC o *420* para BOL. El campo **Longitud** se actualiza automáticamente a la longitud del identificador introducido en el campo **Valor**. |
    | Tipo de embalaje | En los elementos que pueden identificarse claramente, este tipo de segmento agrega un valor de campo del grupo de secuencia de unidades relevante (de la página **Grupos de secuencias de unidades**). (Este comportamiento coincide con la lógica existente de los ID de matrículas). En las matrículas que incluyen múltiples referencias de almacén (SKU), este tipo de segmento agrega *0* (cero) de manera predeterminada. En este tipo de segmento, el campo **Valor** siempre se establece en *P* y el campo **Longitud** siempre se establece en *1*.|
    | Dígito control | Este tipo de segmento agrega un dígito de control que es un cálculo de módulo 10. (Este comportamiento coincide con la lógica existente de los ID de matrículas). En este tipo de segmento, el campo **Valor** siempre se establece en un intercalado (*^*) y el campo **Longitud** siempre se establece en *1*. |

1. Para ver un ejemplo de su formato de número final, inspeccione el campo **Formato** en la parte inferior de la ficha desplegable **Segmentos**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]