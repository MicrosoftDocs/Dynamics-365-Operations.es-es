---
title: Volver a imprimir y anular etiquetas de oleadas
description: En este artículo se explica cómo anular y reimprimir las etiquetas de oleada existentes.
author: perlynne
ms.date: 07/09/2020
ms.topic: article
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSWaveTableListPage, WHSWorkException, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelLayout, WHSWaveLabelType, WHSWaveLabelTemplateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-09
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: f9f057d9985fb8431ec7c9ced23f2cd3c476570d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871844"
---
# <a name="reprint-and-void-wave-labels"></a>Volver a imprimir y anular etiquetas de oleadas

[!include [banner](../includes/banner.md)]

En este artículo se explica cómo administrar etiquetas generadas por el procesamiento de oleada. (Para obtener una descripción detallada e instrucciones de configuración, consulte [Configurar la impresión de etiquetas de oleada](../warehousing/configure-wave-label-printing.md).)

Puede reimprimir etiquetas de oleada en cualquier momento. Por ejemplo, es posible que deba imprimir una única etiqueta si una etiqueta existente se perdió o se dañó. Como alternativa, un trabajador o supervisor de almacén puede que tenga que reimprimir un rollo completo de etiquetas si el número o la composición de una serie completa de etiquetas de oleada ha cambiado (por ejemplo, debido a la escasez de inventario u otras razones). Con frecuencia, incluso si solo ha cambiado el número de cajas, se debe volver a imprimir todo el rollo para mantener el número total exacto en la sección "Caja X de Y" de cada etiqueta.

La característica de reimpresión de etiquetas de oleada admite la siguiente funcionalidad:

- Volver a imprimir etiquetas desde la aplicación de almacenamiento y el cliente enriquecido.
- Anular etiquetas y volver a imprimirlas simultáneamente. (La capacidad de anular etiquetas está integrada en escenarios de selección corta, por ejemplo).
- Limpiar el historial de etiquetas de oleadas.

En este artículo se presenta una colección de escenarios que muestran, a través de ejemplos, cómo trabajar con la característica de reimpresión de etiquetas de oleada.

> [!IMPORTANT]
> Para trabajar en los escenarios que se presentan en este artículo, primero debe activar y configurar las características de impresión de oleadas pertinentes, como se describe en [Configurar la impresión de etiquetas de oleada](../warehousing/configure-wave-label-printing.md). Varios de los escenarios de este artículo también requieren que trabaje primero en los escenarios de ese artículo para generar datos de muestra de requisitos previos.

## <a name="scenario-1-reprint-labels-from-the-web-client"></a>Escenario 1: reimprimir etiquetas desde el cliente web

Puede ver y reimprimir etiquetas de oleada desde las siguientes páginas. En el panel de acciones de cada página, en la pestaña **Envíos** del grupo **Información relacionada**, seleccione **Etiquetas de oleada**.

- Todos los envíos \> Detalles del envío
- Todas las cargas \> Detalles de la carga
- Todas las oleadas
- Etiquetas de oleadas
- Historial de etiquetas de oleada

Para reimprimir una etiqueta de oleada desde el cliente web, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
1. Seleccione la oleada desde la que reimprimir etiquetas.
1. En el panel de acciones, en la pestaña **Oleada**, en el grupo **Imprimir**, seleccione **Etiquetas de oleada**.
1. Siga uno o ambos de los siguientes pasos:

    - Para reimprimir la etiqueta, seleccione una impresora en el campo **Nombre de impresora**. (Deje este campo en blanco si solo desea actualizar los detalles de la etiqueta de oleada, sin volver a imprimir la etiqueta).
    - Para actualizar la etiqueta, seleccione la casilla **Actualizar detalles de etiqueta de oleada**. (Deje esta casilla desactivada si solo desea reimprimir la etiqueta anterior).

    > [!NOTE]
    > Cada vez que se imprime o reimprime una etiqueta de oleada, sus datos se convierten a través del diseño de etiqueta de oleada apropiado, y todos los marcadores de posición se reemplazan por valores reales. La cadena resultante se almacena como un registro en el historial de etiquetas de oleada. Si la casilla **Actualizar detalles de etiqueta de oleada** está desactivada, los datos almacenados del lenguaje de programación Zebra (ZPL) se utilizan cuando se reimprime una etiqueta. Si la casilla **Actualizar detalles de etiqueta de oleada** está seleccionada, se genera una nueva cadena. Las etiquetas de oleada existentes también se recalculan y cualquier etiqueta sobrante (por ejemplo, si las líneas de trabajo relacionadas se han cancelado o modificado) se marca como **Anulado** y no se reimprimen.

1. Seleccione **Aceptar** para confirmar su selección.

## <a name="scenario-2-reprint-labels-from-the-warehousing-app"></a>Escenario 2: reimprimir etiquetas desde la aplicación de almacenamiento

Este escenario se suele aplicar si un rollo de etiquetas se ha perdido o dañado. Proporciona un ejemplo que muestra cómo configurar elementos de menú del dispositivo móvil que permitirán a los trabajadores reimprimir etiquetas simples y múltiples. A continuación, muestra cómo usar esos nuevos elementos de menú mientras trabaja en un dispositivo móvil.

### <a name="set-up-the-required-menu-items-and-menu-for-the-mobile-device"></a>Configurar los elementos de menú necesarios y el menú para el dispositivo móvil

Antes de que los trabajadores puedan reimprimir etiquetas desde un dispositivo móvil, debe configurar los elementos del menú para proporcionar esta funcionalidad y luego agregar esos elementos al menú de la aplicación de almacenamiento.

#### <a name="create-new-mobile-device-menu-items"></a>Crear nuevos elementos de menú del dispositivo móvil

Siga estos pasos para crear una nueva colección de elementos de menú para reimprimir etiquetas desde la aplicación de almacenamiento.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. Cree un elemento de menú y establezca los siguientes valores para este:

    - **Nombre del elemento del menú:** *Reimprimir una única etiqueta de oleada*
    - **Título:** *Reimprimir una única etiqueta de oleada*
    - **Modo:** *Indirecto*
    - **Código de actividad:** *Reimprimir una única etiqueta de oleada*

1. Cree un segundo elemento de menú y establezca los siguientes valores para este:

    - **Nombre del elemento del menú:** *Reimprimir etiquetas (artículo)*
    - **Título:** *Reimprimir etiquetas de oleada (artículo)*
    - **Modo:** *Indirecto*
    - **Código de actividad:** *Reimprimir múltiples etiquetas de oleada*
    - **Mostrar el filtro de agrupación de la lista de trabajo:** *Sí*
    - **Campo de agrupamiento del sistema:** *ShipmentID*
    - **Etiqueta de agrupamiento del sistema:** *ID de envío*
    - **Modo de impresión:** *Producto*

1. En el panel de acciones, seleccione **Lista de campos** para abrir una página en la que pueda seleccionar los campos que se mostrarán para ayudar a los trabajadores a identificar el rollo de etiquetas correcto.
1. Puede mostrar hasta siete campos. Use las listas desplegables para seleccionar el campo que se muestra en cada posición disponible. Deje en blanco los campos que no requiera. 

    Este es un ejemplo:

    - **Campo de visualización:** *LabelItemId*
    - **Campo de visualización 2:** *LabelItemName*
    - **Campo de visualización 3:** *InventQty*
    - **Campo de visualización 4:** *LabelUnitId*

1. Cierre la página.
1. Cree un tercer elemento de menú y establezca los siguientes valores para este:

    - **Nombre del elemento del menú:** *Reimprimir etiquetas (enumeración)*
    - **Título:** *Reimprimir etiquetas de oleada (enumeración)*
    - **Modo:** *Indirecto**.
    - **Código de actividad:** *Reimprimir múltiples etiquetas de oleada*
    - **Mostrar el filtro de agrupación de la lista de trabajo:** *Sí*
    - **Campo de agrupamiento del sistema:** *ShipmentID*
    - **Etiqueta de agrupamiento del sistema:** *ID de envío*
    - **Modo de impresión:** *Enumeración*

1. En el panel de acciones, seleccione **Lista de campos** y, a continuación, use las listas desplegables para seleccionar los campos que se mostrarán para ayudar a los trabajadores a identificar el rollo de etiquetas correcto (por ejemplo, *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* y *NumberOfLabels*).
1. Cierre la página.
1. Cree un cuarto elemento de menú y establezca los siguientes valores para este:

    - **Nombre del elemento del menú:** *Reimprimir etiquetas (por última vez)*
    - **Título:** *Reimprimir etiquetas de oleada (por última vez)*
    - **Modo:** *Indirecto*
    - **Código de actividad:** *Reimprimir múltiples etiquetas de oleada*
    - **Mostrar el filtro de agrupación de la lista de trabajo:** *Sí*
    - **Campo de agrupamiento del sistema:** *ShipmentID*
    - **Etiqueta de agrupamiento del sistema:** *ID de envío*
    - **Modo de impresión:** *Última id. de etiqueta de oleada buena*

1. En el panel de acciones, seleccione **Lista de campos** y, a continuación, use las listas desplegables para seleccionar los campos que se mostrarán para ayudar a los trabajadores a identificar el rollo de etiquetas correcto (por ejemplo, *LabelItemId*, *LabelItemName*, *InventQty*, *LabelUnitId* y *NumberOfLabels*).
1. Cierre la página.

#### <a name="set-up-the-mobile-device-menu"></a>Configurar el menú de dispositivo móvil

Siga estos pasos para agregar sus nuevos elementos de menú al menú de la aplicación de almacenamiento.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. Seleccione un menú **Saliente** existente.
1. En la lista de la izquierda, busque los elementos del menú de reimpresión que acaba de crear y luego use el botón de flecha derecha para agregarlos a la lista de la derecha.
1. Cierre la página.

### <a name="use-cases"></a>Casos de uso

Los casos de uso que se proporcionan aquí proporcionan ejemplos que muestran cómo usar los distintos elementos de menú del dispositivo móvil que configura para permitir a los trabajadores reimprimir etiquetas de oleada.

Antes de trabajar con estos casos de uso, los siguientes requisitos previos deben estar presentes:

- Los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica **USMF**.
- Debe configurarse una impresión de etiquetas de oleada y deben generarse algunas etiquetas, como se describe en [Configurar la impresión de etiquetas de oleada](../warehousing/configure-wave-label-printing.md).

#### <a name="use-case-21-a-single-wave-label-is-scratched-and-must-be-reprinted"></a>Caso de uso 2.1: una única etiqueta de oleada está rayada y debe reimprimirse.

1. Inicie sesión en la aplicación de almacenamiento como un usuario que accede al almacén *62*. (En los datos de demostración estándar, puede iniciar sesión utilizando *62* como el id. de sesión y *1* como la contraseña).
1. Vaya a **Saliente \> Reimprimir una única etiqueta de oleada**.
1. Introduzca o escanee el id. de la etiqueta de oleada.
1. Seleccione la impresora en la que desea reimprimir.
1. Seleccione **Aceptar** para confirmar la acción.

#### <a name="use-case-22-several-labels-for-boxes-of-the-same-item-were-damaged-and-must-be-reprinted-each-label-has-a-product-bar-code-but-no-enumeration-or-sscc-number"></a>Caso de uso 2.2: se dañaron varias etiquetas para cajas del mismo artículo y deben reimprimirse. Cada etiqueta tiene un código de barras del producto, pero no hay enumeración ni número de SSCC.

1. Inicie sesión en la aplicación de almacenamiento como un usuario que tiene acceso al almacén *62*. (En los datos de demostración estándar, puede iniciar sesión utilizando *62* como el id. de sesión y *1* como la contraseña).
1. Vaya a **Saliente \> Reimprimir etiquetas (artículo)**.
1. Introduzca o escanee el id. del envío.
1. Seleccione el icono que tiene el rollo de etiquetas correcto para la reimpresión.
1. Escanee el código de barras del producto de una etiqueta existente para confirmar que se ha seleccionado la línea correcta.
1. Escriba la cantidad de etiquetas que deben reimprimirse.
1. Seleccione la impresora en la que desea reimprimir.
1. Seleccione **Aceptar** para confirmar la acción.

#### <a name="use-case-23-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-because-the-labels-have-enumeration-you-can-define-the-carton-range-to-reprint"></a>Caso de uso 2.3: no se pudieron imprimir varias etiquetas para cajas debido a un atasco de la impresora. Debido a que las etiquetas tienen enumeración, puede definir el rango de caja para reimprimir.

1. Inicie sesión en la aplicación de almacenamiento como un usuario que tiene acceso al almacén *62*. (En los datos de demostración estándar, puede iniciar sesión utilizando *62* como el id. de sesión y *1* como la contraseña).
1. Vaya a **Saliente \> Reimprimir etiquetas (enumeración)**.
1. Introduzca o escanee el id. del envío.
1. Seleccione el icono que tiene el rollo de etiquetas correcto para la reimpresión.
1. Introduzca la primera caja para reimprimir una etiqueta.
1. Introduzca la última caja para reimprimir una etiqueta. Como alternativa, deje este campo en blanco para reimprimir etiquetas para todas las cajas después de la primera caja especificada.
1. Seleccione la impresora en la que desea reimprimir.
1. Seleccione **Aceptar** para confirmar la acción.

#### <a name="use-case-24-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-the-last-good-label-has-a-wave-label-id-that-is-printed-as-a-bar-code"></a>Caso de uso 2.4: no se pudieron imprimir varias etiquetas para cajas debido a un atasco de la impresora. La última etiqueta buena tiene un id. de etiqueta de oleada que se imprime como un código de barras.

1. Inicie sesión en la aplicación de almacenamiento como un usuario que tiene acceso al almacén *62*. (En los datos de demostración estándar, puede iniciar sesión utilizando *62* como el id. de sesión y *1* como la contraseña).
1. Vaya a **Saliente \> Reimprimir etiquetas (por última vez)**.
1. Introduzca o escanee el id. del envío.
1. Seleccione el icono que tiene el rollo de etiquetas correcto para la reimpresión.
1. Introduzca o escanee el id. de etiqueta de oleada de la última etiqueta de oleada buena. La aplicación identifica la siguiente etiqueta de la secuencia como la primera caja para la que se reimprimirá una etiqueta.
1. Introduzca la última caja para reimprimir una etiqueta. Como alternativa, deje este campo en blanco para reimprimir etiquetas para todas las cajas después de la primera caja especificada.
1. Seleccione la impresora en la que desea reimprimir.
1. Seleccione **Aceptar** para confirmar la acción.

## <a name="scenario-3-short-pick-and-reprint"></a>Escenario 3: selección corta y reimpresión

Antes de trabajar con este escenario, los siguientes requisitos previos deben estar presentes:

- Los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica **USMF**.
- Debe configurarse una impresión de etiquetas de oleada y deben generarse algunas etiquetas, como se describe en [Configurar la impresión de etiquetas de oleada](../warehousing/configure-wave-label-printing.md).

### <a name="set-up-work-exceptions"></a>Configurar excepciones de trabajo

Las excepciones de trabajo controlan el comportamiento de la selección corta. Siga esos pasos para configurar una excepción de trabajo:

1. Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Excepciones de trabajo**.
1. Cree un registro que tenga la siguiente configuración:

    - **Código de excepción de trabajo:** *Selección corta e impresión*
    - **Tipo de excepción:** *Selección corta*
    - **Sugerir reimpresión de etiquetas de oleada:** *Sí*

### <a name="void-and-reprint-after-a-short-pick"></a>Anular y reimprimir después de una selección corta

1. Inicie sesión en la aplicación de almacenamiento como un usuario que tiene acceso al almacén *62*. (En los datos de demostración estándar, puede iniciar sesión utilizando *62* como el id. de sesión y *1* como la contraseña).
1. Abra un flujo de procesamiento de trabajo para el trabajo de pedido de ventas que se creó cuando las etiquetas de oleada se imprimieron originalmente.
1. Seleccione **Selección corta**.
1. Seleccione el código de excepción de trabajo que creó para este escenario.
1. Si seleccionó la excepción correcta, la casilla **Anular y reimprimir** debe estar disponible. Seleccione esta casilla y confirme. Cuando se confirme, la secuencia del rollo de etiquetas identificada por el campo **Id. de compilación de etiqueta** se recalcula en función de la cantidad de línea de trabajo modificada. A continuación, se reimprime en la impresora especificada.

## <a name="additional-resources"></a>Recursos adicionales

- [Impresión de etiquetas de oleadas](configure-wave-label-printing.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]