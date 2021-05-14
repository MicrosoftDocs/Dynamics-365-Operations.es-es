---
title: Gestionar las unidades de medida
description: Este rema describe cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas.
author: sorenva
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d36839cd8e3398225d3421bf0f268068599ca49f
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921350"
---
# <a name="manage-units-of-measure"></a>Gestionar las unidades de medida

[!include [banner](../../includes/banner.md)]

Este rema describe cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas.

## <a name="open-the-units-page"></a>Abrir la página de unidades

Para crear y trabajar con las unidades de medida que están disponibles en su sistema, vaya a **Administración de la organización \> Configuración \> Unidades \> Unidades**.

Las secciones restantes de este tema describen lo que puede hacer en la página **Unidades**.

## <a name="create-standard-units-and-conversions"></a>Crear unidades y conversiones estándar

Si su sistema aún no incluye las unidades de medida más utilizadas para el sistema métrico y/o el sistema particular de EE. UU. (USCS), el asistente de configuración de unidades puede ayudarle a comenzar rápidamente con las definiciones y conversiones de unidades básicas. Para completar el asistente, seleccione **Asistente de creación de unidades** en el panel de acciones y luego siga las instrucciones en pantalla.

## <a name="create-or-edit-a-unit-of-measure"></a>Crear o editar una unidad de medida

Para crear o editar una unidad de medida, siga estos pasos.

1. Siga uno de estos pasos:

    - Para editar una unidad existente, selecciónela en el panel de lista.
    - Para crear una nueva unidad, seleccione **Nueva** en el panel de acciones.

1. En el encabezado del registro, establezca los siguientes campos:

    - **Unidad**: introduzca el id. o el símbolo que se utilizará para hacer referencia a la unidad en el idioma del sistema. Este id. o símbolo suele ser una abreviatura común de la unidad, como *ea* por cada uno o *cm* por centímetro.
    - **Descripción**: especifique un nombre descriptivo para la unidad de medida en el idioma del sistema. Este nombre suele ser el nombre completo de la unidad, como *Cada uno* o *Centímetro*.

1. En la ficha rápida **General**, establezca los siguientes campos:<!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - **Clase de unidad**: seleccione la propiedad que mide la unidad (como longitud, área, masa o cantidad).
    - **Sistema de unidades**: seleccione el sistema de medida al que pertenece la unidad (*Unidades metricas* o *Unidades particulares de Estados Unidos*).
    - **Unidad base**: establezca esta opción en *Sí* para utilizar la unidad actual como unidad base para su clase de unidad. En este caso, solo tiene que especificar el factor de conversión entre la unidad base y cada unidad adicional en la clase de unidad. A continuación, el sistema puede convertir entre todas las unidades de esa clase de unidad. Por lo tanto, es más fácil configurar conversiones.

        Por ejemplo, si galón es la unidad base para la clase de unidad *Volumen*, solo tiene que configurar los factores de conversión de un cuarto a un galón y de una pinta a un galón. Luego, el sistema también puede convertir de un cuarto a una pinta.

        Solo puede tener una unidad base por clase de unidad.

    - **Unidad del sistema**: establezca esta opción en *Sí* para utilizar la unidad actual como unidad supuesta para todas las medidas no especificadas de su clase de unidad. Por ejemplo, si un campo que se usa para introducir una cantidad no permite especificar una unidad (o si el usuario no selecciona una unidad), el sistema usa la unidad que está configurada como la unidad del sistema para la clase de unidad *Cantidad*. Solo puede tener una unidad de sistema por clase de unidad.
    - **Precisión decimal**: especifique el número de lugares decimales a los que se deben redondear los valores que se especifican para la unidad actual o que se convierten a ella.

1. En el panel Acciones, seleccione **Guardar**.

## <a name="define-unit-translations"></a>Definición de conversiones de unidades

Para definir traducciones para el id. o símbolo y la descripción de una unidad de medida, siga estos pasos.

1. Cree o seleccione la unidad para la que creará traducciones.
1. En el panel de acciones, seleccione **Textos de unidades**.

    Aparece la página **Textos de unidades**. Utilice esta página para definir traducciones para el id. o símbolo de la unidad seleccionada. A continuación, esas traducciones se pueden utilizar en documentos externos en idiomas específicos del cliente o del proveedor.

1. En el panel de acciones, haga clic en **Nueva**.
1. En ell campo **Idioma**, seleccione el idioma al que traducir el id. de unidad o símbolo.
1. En el campo **Texto**, introduzca la traducción del id. de la unidad o símbolo en el idioma seleccionado.
1. En el panel Acciones, seleccione **Guardar**.
1. Cierre la página.
1. En el **Panel de acciones**, seleccione **Descripciones de unidades convertidas**.

    Aparece la página **Descripciones de unidades traducidas**. Utilice esta página para definir descripciones específicas del idioma para la unidad seleccionada.

1. En el panel de acciones, haga clic en **Nueva**.
1. En el campo **Idioma**, seleccione el idioma al que traducir la descripción de la unidad.
1. En el campo **Descripción**, introduzca la traducción de la descripción de la unidad en el idioma seleccionado.
1. En el panel Acciones, seleccione **Guardar**.
1. Cierre la página.

## <a name="define-unit-conversion-rules"></a>Definición de reglas de conversión de unidades

Para definir reglas de conversiones entre unidades de medida, siga estos pasos.

1. Cree o seleccione la unidad para la que definir reglas de conversión.
1. En el panel de acciones, seleccione **Conversiones de unidades**.

    Se abrirá la página **Conversiones de unidades**. Puede usar esta página para definir reglas para convertir la unidad seleccionada a y desde otras unidades de la clase de unidad.

1. Seleccione una de las siguientes pestañas, en función del tipo de conversión que desee configurar:

    - **Conversiones estándar**: permite configurar reglas de conversión estándar para todos los productos.
    - **Conversiones intraclase**: permite configurar reglas de conversión específicas de producto para unidades de la misma clase de unidad.
    - **Conversiones entre clases**: permite configurar reglas de conversión específicas de producto para unidades de todas las clases de unidades.

1. Siga uno de estos pasos:

    - Para crear una nueva conversión, seleccione **Nueva** en la barra de herramientas.
    - Para editar una conversión existente, seleccione la conversión en la cuadrícula y luego seleccione **Editar** en la barra de herramientas.

1. En el cuadro de diálogo emergente, establezca los campos siguientes:

    - **Producto**: seleccione el producto específico al que se aplica la conversión. Este campo está disponible solo para conversiones intraclase y entre clases.
    - **Diseño de fórmula**: deje este campo configurado en *Sencillo* para especificar una conversión simple que tiene un solo factor. Configúrelo en *Avanzado* para configurar una ecuación más compleja. El formato de las ecuaciones avanzadas varía según la clase de unidad.
    - **De la unidad**: este campo muestra la unidad seleccionada. Por lo general, no debe cambiarse el valor. (Si cambia el valor, debe abrir la página **Conversiones de unidades** de la unidad seleccionada para ver su nueva conversión después de guardarla).
    - **A la unidad**: seleccione la unidad a la que desea convertir.
    - **Redondeo**: seleccione cómo se deben redondear las fracciones, según el valor **Precisión decimal** de la unidad seleccionada (*Al más cercano*, *Superior* o *Inferior*).
    - **Fórmula de conversión**: utilice los campos restantes en la parte superior del cuadro de diálogo desplegable para especificar la fórmula de conversión entre las dos unidades. Los campos disponibles varían, según la clase de unidad y el diseño de fórmula que haya seleccionado.

1. Seleccione **Aceptar**.
1. Cierre la página.

> [!TIP]
> También puede configurar conversiones de unidades por variante de producto. Para más información, consulte [Conversión de unidad de medida por variante del producto](../uom-conversion-per-product-variant.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
