---
title: Consultas e informes sobre materiales peligrosos
description: Este tema explica cómo trabajar con los distintos informes relacionados con materiales peligrosos. Muchos de estos informes son necesarios para que pueda seguir cumpliendo con las diversas regulaciones de materiales peligrosos durante el envío y almacenamiento.
author: dasani-madipalli
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 07f103680cacc1273b2b28f6e4e905d6dabb006a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820331"
---
# <a name="hazardous-materials-inquiries-and-reports"></a>Consultas e informes sobre materiales peligrosos

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management proporciona divesos informes relacionados con materiales peligrosos. Muchos de estos informes son necesarios para que pueda seguir cumpliendo con las diversas regulaciones de materiales peligrosos durante el envío y almacenamiento.

Todos estos informes, excepto el informe **Mercancías peligrosas multimodales**, utilizan el modo de entrega que se define para el envío para encontrar la regulación que se debe utilizar para imprimir el texto de envío de los artículos. El modo de entrega está asociado con el transportista de envío y el servicio de transportista. Por lo tanto, debe configurar un transportista de envío y un servicio de transportista, y vincularlos a un modo de entrega. El modo de entrega está relacionado con la regulación de materiales peligrosos.

La siguiente ilustración muestra la secuencia de actividades que ocurren cuando el sistema genera informes de materiales peligrosos.

![Secuencia de actividades para informes de materiales peligrosos](media/hazmat-report-sequence.png "Secuencia de actividades para informes de materiales peligrosos")

## <a name="set-up-hazardous-materials-reporting"></a><a name="set-up"></a>Configurar informes de materiales peligrosos

Por lo general, si envía artículos que contienen materiales peligrosos, debe generar informes específicos para ayudar a preservar la seguridad y cumplir con las regulaciones de materiales peligrosos. Siga estos pasos para configurar los informes:

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
2. Abra la pestaña **Informes**. En la ficha desplegable **Parámetro de informe de materiales peligrosos**, establezca los siguientes campos.

    | Grupo | Campo | Descripción |
    |---|---|---|
    | Mercancías peligrosas multimodales | Código normativo | Seleccione la regulación que se debe utilizarse cuando se genera el informe **Mercancías peligrosas multimodales**. |
    | Límites de existencias de materiales peligrosos | Código normativo | Seleccione la regulación que debe usarse cuando se evalúan los límites de existencias. |
    | Transporte de mercancías por carretera | Producto de grupo de CMR | CMR significa "sustancias cancerígenas, mutágenas y reprotóxicas". Establezca esta opción en **Sí** para configurar el sistema para que imprima avisos y mensajes específicos relacionados con la manipulación de estas sustancias. |
    | Transporte de mercancías por carretera | Descripción de grupo de materiales peligrosos | Introduzca el texto de las advertencias específicas que se relacionen con CMR y el ransporte de mercaderías por carretera. Este texto se incluirá en el informe. |
    | Declaración de remitentes | Advertencia | Introduzca el texto de un mensaje de advertencia a imprimir en el formulario de declaración del remitente (por ejemplo, "Advertencia: Mercancía peligrosa, inflamable"). |
    | Declaración de remitentes | Declaración de pie de página | Introduzca el texto de un mensaje a imprimir en la parte inferior del documento de declaración de envío. |
    | Idioma de informe de mercancías peligrosas | Idioma de informe nacional de mercancías peligrosas | Seleccione el idioma predeterminado para los informes de materiales peligrosos asociados con los envíos nacionales. |
    | Idioma de informe de mercancías peligrosas | Idioma de informe de exportación de mercancías peligrosas | Seleccione el idioma predeterminado para los informes de materiales peligrosos asociados con los envíos internacionales. |

## <a name="hazardous-materials-report"></a>Informe de materiales peligrosos

El informe **Materiales peligrosos** muestra una lista de todos los elementos que se han configurado y definido para que tengan información sobre mercancías peligrosas. Puede utilizar este informe para supervisar y revisar la información que debe mantener. La página del informe muestra una selección limitada de campos de la configuración de materiales peligrosos. Sin embargo, puede personalizarlo para agregar campos adicionales según lo requiera.

Para ver este informe, vaya a **Gestión de información de productos \> Consultas e informes \> Documentación de envío de material peligroso \> Materiales peligrosos**.

## <a name="hazardous-material-stock-limit-report"></a><a name="stock-limit-report"></a>Informe de límites de existencias de materiales peligrosos

El informe **Límite de existencias de materiales peligrosos** le permite monitorear los niveles de existencias de los materiales peligrosos en las ubicaciones de su almacén, para asegurarse de que permanezcan por debajo de los límites de seguridad establecidos y seguros. Estos límites provienen de los límites que se definen para cada producto despachado.

Para ver este informe, vaya a **Gestión de información de productos \> Consultas e informes \> Documentación de envío de material peligroso \> Límites de existencias de materiales peligrosos**.

Para obtener más información sobre cómo establecer límites de existencias en un producto despachado, consulte [Establecer límites de existencias para productos peligrosos](hazmat-items.md#stock-limits).

La regulación que se utiliza para los límites de existencias se define en la página **Parámetros de gestión de almacén**. Vaya a **Gestión de almacenes \> Preparar \> Parámetros de gestión de almacén** y luego, en la pestaña **Informes** de **Límite de existencias de materiales peligrosos**, especifique un código de regulación. Para obtener más información, consulte la sección [Configurar un informe de materiales peligrosos](#set-up) previa de este tema.

## <a name="verified-gross-mass-report"></a>Informe de peso bruto verificado

El informe **Peso bruto verificado** le permite imprimir información sobre el peso de un envío.

Para generar e imprimir este informe, vaya a **Gestión de almacenes \> Envíos \> Todos los envios** y abra el envío correspondiente. Luego, en el Panel Acciones, en la pestaña **Envíos** del grupo **Documento de materiales peligrosos**, seleccione **Peso bruto verificado**.

## <a name="multimodal-dangerous-goods-report"></a>Informe de mercancías peligrosas multimodales

El informe **Mercancías peligrosas multimodales** se proporciona para los envíos que deben moverse mediante una combinación de métodos de transporte. Por lo general, se usa cuando un envío se mueve primero por carretera y luego por mar.

Para generar e imprimir este informe, vaya a **Gestión de almacenes \> Envíos \> Todos los envios** y abra el envío correspondiente. Luego, en el Panel Acciones, en la pestaña **Envíos** del grupo **Documento de materiales peligrosos**, seleccione **Mercancías peligrosas multimodales**.

Cuando genera este informe, la información se guarda, para que pueda editarlo y/o volver a imprimirlo si es necesario. Para editar un informe generado, vaya a **Gestión de almacenes \> Consultas e informes \> Documentación de envío de materiales peligrosos \> Mercancías peligrosas multimodales** y busque el informe correspondiente en la lista. Una vez que haya terminado de editar el contenido como lo necesita, seleccione **Imprimir** en el Panel Acciones para imprimir el informe.

## <a name="shippers-declaration-report"></a>Informe de declaración de remitentes

El informe **Declaración de remitentes** le permite imprimir información relacionada con una declaración de los materiales que se incluyen en el envío.

Para generar e imprimir este informe, vaya a **Gestión de almacenes \> Envíos \> Todos los envios** y abra el envío correspondiente. Luego, en el Panel Acciones, en la pestaña **Envíos** del grupo **Documento de materiales peligrosos**, seleccione **Declaración de remitentes**.

## <a name="carriage-of-merchandise-by-road-report"></a>informe de transporte de mercancías por carretera

El informe **Transporte de mercancías por carretera** se asemeja a un conocimiento de embarque, pero normalmente se utiliza para el transporte por carretera en Europa en virtud de las normativas del Acuerdo sobre el transporte internacional de mercancías peligrosas por carretera (ADR). Este informe utiliza el texto de impresión de envío de un artículo a menos que establezca el campo **Descripción del grupo de materiales peligrosos** de la página **Parámetros de gestión de almacén**.

Para generar e imprimir este informe, vaya a **Gestión de almacenes \> Envíos \> Todos los envios** y abra el envío correspondiente. Luego, en el Panel Acciones, en la pestaña **Envíos** del grupo **Documento de materiales peligrosos**, seleccione **Transporte de mercancías por carretera**.

Cuando genera este informe, la información se guarda, para que pueda editarlo y/o volver a imprimirlo si es necesario. Para editar un informe generado, vaya a **Gestión de almacenes \> Consultas e informes \> Documentación de envío de materiales peligrosos \> Transporte de mercancías por carretera** y busque el informe correspondiente en la lista. Una vez que haya terminado de editar el contenido como lo necesita, seleccione **Imprimir** en el Panel Acciones para imprimir el informe.

## <a name="shipment-summary-report"></a>Informe de resumen de envío

El informe **Resumen de envío** proporciona información resumida por la categoría de transporte relacionada con los artículos despachados.

Para generar e imprimir este informe, vaya a **Gestión de almacenes \> Envíos \> Todos los envios** y abra el envío correspondiente. Luego, en el Panel Acciones, en la pestaña **Envíos** del grupo **Documento de materiales peligrosos**, seleccione **Resumen de envío**.

## <a name="bill-of-lading-report"></a>Informe de conocimiento de embarque

Cuando la función de materiales peligrosos está activada en su sistema, el informe **Conocimiento de embarque** incluye una columna **Materiales peligrosos** que indica si una carga incluye materiales peligrosos. Este informe está disponible en la página **Todas las cargas**, como de costumbre.

## <a name="packing-list-report"></a>Informe de lista de embalaje

Cuando la función de materiales peligrosos está activada en su sistema, las listas de embalaje incluyen información adicional relacionada con el texto de impresión de envío de un artículo. Este informe está disponible en la página **Todas las cargas**, como de costumbre.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]