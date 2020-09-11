---
title: Configurar materiales peligrosos
description: Este tema explica cómo configurar los datos necesarios para clasificar artículos como materiales peligrosos. Cuando crea un pedido de venta que incluye un artículo clasificado como material peligroso, el sistema genera documentación de material peligroso para el pedido de venta cuando se envía.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: aaf66b98717c72b4260e0a482400bdb29bbd9ecb
ms.sourcegitcommit: c009ec75f53872272f11c92a1ce81a391e3845a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "3699659"
---
# <a name="set-up-hazardous-materials"></a>Configurar materiales peligrosos

[!include [banner](../includes/banner.md)]

Para utilizar la funcionalidad de materiales peligrosos, primero debe configurar los datos necesarios para clasificar los artículos como materiales peligrosos. Luego, cuando crea un pedido de venta que incluye un artículo clasificado como material peligroso, el sistema genera documentación de material peligroso para el pedido de venta cuando se envía.

## <a name="turn-on-the-hazardous-materials-feature-for-your-system"></a>Activar la función de materiales peligrosos en el sistema

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de información de productos*
- **Nombre de la función:** *Información de productos de materiales peligrosos y documentación de envío*

## <a name="hazardous-material-regulations"></a>Regulaciones de materiales peligrosos

Para utilizar los procesos de materiales peligrosos, primero debe crear un reglamento. Las regulaciones definen cómo se crea el texto de envío impreso para un artículo. También definen los modos de administración asociados.

A continuación, se muestran algunas normativas habituales:

- **ADR** - Regulaciones relacionadas con el transporte internacional de mercancías peligrosas por carretera.
- **CFR 49** - Regulaciones en los Estados Unidos para el transporte de mercancías peligrosas
- **IMDG** - El código internacional de mercancías peligrosas marinas (IMDG)
- **IATA** - Las regulaciones de mercancías peligrosas de la Asociación Internacional de Transporte Aéreo (IATA)

Estas regulaciones ayudan a determinar qué información debe mostrarse al imprimir el texto de envío de un artículo. Puede definir tantas normativas como deba cumplir.

> [!IMPORTANT]
> La funcionalidad para configurar códigos de información relacionados con materiales peligrosos no hace que su empresa cumpla con las regulaciones. Es solo una herramienta que le ayuda a crear procesos para su empresa.

Por lo general, se dispone de un reglamento para un modo de transporte específico, como el transporte marítimo, terrestre o aéreo. Por lo tanto, puede asociar cada regulación con un modo de entrega. El modo de entrega se utilizará cuando se impriman documentos específicos en Gestión de almacenes. En Gestión de almacenes, cada envío está vinculado a un transportista y un servicio de transportista que se configuran en el módulo **Transporte**. El modo de entrega está asociado con el transportista de envío y el servicio de transportista. Al ejecutar un informe, el modo de entrega se usa para encontrar el texto de impresión de envío que está asociado con un artículo despachado.

Estos datos de configuración no son específicos de cada entidad jurídica (empresa). Por lo tanto, puede tener un conjunto común de información sobre materiales peligrosos que se comparte entre todas sus entidades legales.

Para cada regulación, puede definir una lista de materiales y usarla como una lista de plantillas asociadas con los artículos despachados. Para cada regulación, también puede definir una configuración de impresión. Una configuración de impresión le permite definir cómo se construye el texto de envío de un artículo. La configuración de impresión se utiliza para construir el texto de impresión de envío de un artículo despachado.

Para configurar las regulaciones de materiales peligrosos, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Regulación de materiales peligrosos**. En la página **Regulación de materiales peligrosos**, puede crear cualquier número de regulaciones y configurar cada una utilizando los campos que se describen en las siguientes subsecciones.

### <a name="hazardous-material-regulation-header"></a>Encabezado de regulaciones de materiales peligrosos

Cada reglamento tiene un código y una descripción. En la tabla siguiente se describen los campos disponibles en el encabezado.

| Campo | Descripción |
|---|---|
| Código normativo | Introduzca un código para identificar el registro de regulación de materiales peligrosos. |
| Descripción | Escriba una descripción del reglamento de materiales peligrosos. |

### <a name="print-setup-fasttab"></a>Ficha desplegable Configuración de impresión

Cada regulación puede tener cualquier número de configuraciones de impresión. Defina las configuraciones de impresión en la ficha desplegable **Configuración de impresión**. En la tabla siguiente se describen los campos disponibles para cada configuración de impresión.

| Campo | Descripción |
|---|---|
| Secuencia | Defina el orden en el que se hará referencia a los campos en el texto de envío. |
| Imprimir campo | Seleccione el campo a incluir en el texto de envío. No todos los campos del material peligroso estarán disponibles para imprimir. Solo estarán disponibles los campos comunes que se utilizan para definir el texto de envío de las diversas regulaciones. Debe definir el primer campo de impresión como un separador de campo que tiene un valor de **Secuencia** de *0* (cero), para que pueda usarse como separador entre otros campos. Solo se requiere una referencia al separador de campo.<p>Los siguientes valores están disponibles:</p><ul></li><li>**Separador de campo**: este campo de impresión se utiliza como separador de campo para el texto. Solo se requiere un separador de campo en la secuencia. Por lo general, debe configurar el valor **Secuencia** para este campo de impresión en *0* (cero). El sistema buscará un separador de campo y utilizará el primero que encuentre en la lista. El valor de texto que se utiliza en la cadena vendrá del campo **Imprimir después**.</li><li>**Identificación**: este campo de impresión pone el [código de identificación y/o la descripción](#identification) en el texto impreso.</li><li>**Clase**: este campo de impresión pone el [código de clase y/o la descripción](#classes) en el texto impreso.</li><li>**División**: este campo de impresión pone el [código de división y/o la descripción](#divisions) en el texto impreso.</li><li>**Grupo de embalaje**: este campo de impresión pone el [código de grupo de embalaje y/o la descripción](#packing-group) en el texto impreso.</li><li>**Código y/o descripción de túnel**: este campo de impresión pone el [código y/o la descripción del túnel](#tunnel) en el texto impreso.</li><li>**Nombre de envío adecuado**: este campo de impresión pone el [nombre de envío adecuado](hazmat-items.md#hazmat-description) en el texto impreso.</li><li>**Nombre técnico**: este campo de impresión pone el [nombre técnico y/o la descripción](#technical-name) en el texto impreso.</li><li>**Categoría de transporte**: este campo de impresión pone el [código y/o la descripción de categoría de transporte](#transport-category) en el texto impreso.</li><li>**Estiba**: este campo de impresión pone el [código de estiba y/o la descripción](#stowage) en el texto impreso.</li><li>**Texto fijo**: este campo de impresión introduce el texto que se define en el campo **Texto fijo** para esta fila.</li><li>**Código y/o descripción de etiqueta**: este campo de impresión pone el [código y/o la descripción de la etiqueta](#label) en el texto impreso.</li><li>**Embalaje aéreo**: este campo de impresión pone el [código de instrucciones de embalaje aéreo y/o la descripción](#packing-instruction) en el texto impreso.</li><li>**Cantidad limitada**: este campo de impresión comprueba si el artículo está marcado como [artículo de cantidad limitada](hazmat-items.md#material-management) y, si es así, introduce el texto que se define en el campo **Texto fijo** de esta fila.</li><li>**Descripción de embalaje**: este campo de impresión pone el [código de embalaje y/o la descripción](#packing-description) en el texto impreso.</li></ul> |
| Imprimir antes de | Introduzca el texto que debe imprimirse antes del contenido definido por el ajuste **Campo de impresión**. |
| Imprimir después de | Introduzca el texto que debe imprimirse después del contenido definido por el ajuste **Campo de impresión**. |
| Imprimir con anterior | Seleccione esta casilla de verificación para evitar que el separador de campos se imprima entre el campo anterior y este campo. Utilice esta casilla de verificación para los campos de impresión que son opcionales o se incluyen con otro campo de impresión. |
| Texto fijo | Si configura el campo **Campo de impresión** en **Texto fijo** o **Cantidad limitada**, introduzca el texto que se debe imprimir. |
| Incluir en impresión | Seleccione qué valor o valores del campo de impresión seleccionado se deben imprimir para esta fila. Puede imprimir el código, la descripción o tanto el código como la descripción. |

### <a name="mode-of-delivery-fasttab"></a>Ficha desplegable Modo de entrega

La regulación es una tabla compartida y no es específica de cada entidad jurídica. Sin embargo, los modos de entrega son específicos de la entidad jurídica. Por lo tanto, cuando configura un modo de entrega, debe seleccionar la relación entre la regulación, la entidad legal y el modo de entrega.

En la tabla siguiente se describen los campos disponibles en la ficha desplegable **Modo de entrega**.

| Campo | Descripción |
|---|---|
| Empresa | Seleccione una entidad jurídica a asociar a este reglamento. |
| Modo de entrega | Según la entidad legal que haya elegido, seleccione el modo de entrega que debe asociarse con la regulación. |

### <a name="country-fasttab"></a>Ficha desplegable País

A modo de referencia, puede enumerar los países o regiones para los que es relevante la regulación. Sin embargo, cuando se generan informes de envío, solo se utiliza el modo de entrega para determinar la regulación. Cuando revisa un envío de almacén, no hay vínculo directo al modo de entrega. El modo de entrega puede estar asociado con un transportista de envío y un servicio de transportista. Cuando define un servicio de transportista, debe asociarlo con un modo de entrega. Esta relación se utilizará en los informes de envío, como el conocimiento de embarque, para encontrar el texto de impresión de envío de un artículo.

En la tabla siguiente se describe el campo disponible en la ficha desplegable **País**.

| Campo | Descripción |
|---|---|
| País/región | Seleccione un país o región a asociar con la normativa. |

## <a name="material-codes"></a><a name="hazmat-codes"></a>Códigos de materiales

Los códigos de materiales establecen configuraciones que están relacionadas con un componente peligroso específico que podría estar incluido en un producto despachado. Cada código de material pertenece a una regulación específica de materiales peligrosos y su definición debe ajustarse a esa regulación. Cuando aplica un código de material a un producto publicado mediante el campo **Código de material**, todas las configuraciones de materiales peligrosos del código de material se aplican automáticamente a ese producto. Por lo tanto, el proceso de configuración de productos despachados es más rápido y menos propenso a errores.

Para administrar sus definiciones de materiales peligrosos, siga estos pasos.

1. Vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Regulación de materiales peligrosos**.
2. Seleccione la regulación para la que establecer una definición de material peligroso.
3. En el Panel Acciones, en la pestaña **Configuración**, seleccione **Materiales peligrosos**.
4. En el campo **Código material**, introduzca un código de material para la definición de material peligroso. Seleccionará este valor cuando aplique el código de material a un producto despachado.

    El campo **Código de regulación** es de solo lectura y muestra la regulación que seleccionó en el paso 2.

5. Utilice los campos restantes de esta página para crear y configurar cada material peligroso que se aplique a su regulación seleccionada. Los campos disponibles son un subconjunto de los campos de materiales peligrosos disponibles para productos despachados individuales. Para más información, consulte [Materiales peligrosos en productos, pedidos, envíos y cargas](hazmat-items.md).

## <a name="hazardous-material-classification-groups"></a><a name="classification-groups"></a>Grupos de clasificación de materiales peligrosos

Cada grupo de clasificación de materiales peligrosos define un grupo de valores de campo que establecen una plantilla. Puede utilizar esta plantilla más adelante, cuando configure la información de materiales peligrosos para un artículo despachado.

Cuando asigna el código para un grupo de clasificación de materiales peligrosos a un artículo despachado, la información asociada con ese grupo de clasificación se copiará en los campos correspondientes del artículo. Por lo tanto, puede simplificar los procesos de configuración estableciendo un conjunto de valores de campo relacionados que a menudo usa juntos.

Estos datos de configuración no son específicos de cada entidad jurídica. Por lo tanto, puede tener un conjunto común de información sobre materiales peligrosos que se comparte entre todas sus entidades legales.

Para configurar los grupos de clasificación de materiales peligrosos, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Grupo de clasificación de materiales peligrosos**. En la página **Grupo de clasificación de materiales peligrosos**, puede crear cualquier número de grupos y configurar cada uno utilizando los campos que se describen en la tabla siguiente.

| Campo | Descripción |
|---|---|
| Código de grupo | Introduzca un código que identifique el grupo. |
| Descripción | Escriba una descripción del grupo. |
| Código de clase | Asocie un [código de clase](#classes) de material peligroso con el grupo. |
| Código de división | Asocie un [código de división](#divisions) de material peligroso con el grupo. |
| Código de grupo de embalaje | Asocie un [código del grupo de embalaje](#packing-group) con el grupo. |
| Código de categoría de transporte | Asocie un [código de categoría de transporte](#transport-category) con el grupo. |
| Multiplicador | Introduzca el multiplicador de material peligroso que se aplica a la clase y división seleccionadas de materiales peligrosos, de acuerdo con la regulación aplicable. Este multiplicador se usa como parte de la fórmula que calcula el total de *puntos de materiales peligrosos* que se incluyen en una carga o envío. Para obtener más información sobre los puntos de materiales peligrosos y este multiplicador, consulte [Ficha desplegable Gestión de materiales](hazmat-items.md#material-management). |

## <a name="hazardous-material-classes"></a><a name="classes"></a>Clases de materiales peligrosos

hay que cumplir. Por ejemplo, la regulación estadounidense CFR 49 enumera la "clase 3" como líquidos inflamables y combustibles. Puede configurar las clases que sean relevantes para los materiales que debe clasificar.

A cada clase se le asignará una configuración de material en la lista de materiales que está relacionada con la regulación. Asignará una clase a cada artículo despachado según sea necesario, para describir la naturaleza peligrosa de un producto.

Estos datos de configuración no son específicos de cada entidad jurídica. Por lo tanto, puede tener un conjunto común de información sobre materiales peligrosos que se comparte entre todas sus entidades legales.

Las clases de materiales peligrosos funcionan junto con divisiones, grupos y grupos de compatibilidad de la siguiente manera:

- Cuando asigna una clase de material peligroso a un artículo despachado, también debe asignar una [división de materiales peligrosos](#divisions).
- Puede utilizar clases de materiales peligrosos junto con [grupos de clasificación de materiales peligrosos](#classification-groups) para establecer una plantilla de códigos para configurar artículos.
- Puede usar [grupos de compatibilidad de materiales peligrosos](#compatibility-groups) para establecer qué clases y divisiones de materiales peligrosos se pueden enviar juntas.

Para configurar las clases de materiales peligrosos, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Clase de materiales peligrosos**. En la página **Clase de materiales peligrosos**, puede crear cualquier número de clases y configurar cada uno utilizando los campos que se describen en la tabla siguiente.

| Campo | Descripción |
|---|---|
| Código de clase | Introduzca un código que identifique esta clase. Defina este código para el artículo. Luego se utilizará en las listas de búsqueda cuando asigne una clase de material peligroso a un artículo despachado. |
| Descripción | Escriba una descripción de la clase. |

## <a name="hazardous-material-divisions"></a><a name="divisions"></a>Divisiones de materiales peligrosos

Una división de materiales peligrosos es un subconjunto de una clase de materiales peligrosos. Debe asignar una división y una clase a cada producto que incluya materiales peligrosos.

Para las clases que no tienen divisiones, cree una división donde el código sea *0*. Por ejemplo, en el reglamento de la IATA, los materiales radiactivos de clase 7 no tienen subdivisiones. En este caso, creará una división *0* que puede asociar con un producto despachado cuando asigna la clase.

Estos datos de configuración no son específicos de cada entidad jurídica. Por lo tanto, puede tener un conjunto común de información sobre materiales peligrosos que se comparte entre todas sus entidades legales.

Las divisiones de materiales peligrosos funcionan junto con clases, grupos y grupos de compatibilidad de las siguientes maneras:

- Cuando asigna una división de materiales peligrosos a un artículo despachado, también debe asignar una [clase de materiales peligrosos](#classes).
- Puede utilizar divisiones de materiales peligrosos junto con [grupos de clasificación de materiales peligrosos](#classification-groups) para establecer una plantilla de códigos para configurar artículos.
- Puede usar [grupos de compatibilidad de materiales peligrosos](#compatibility-groups) para establecer qué clases y divisiones de materiales peligrosos se pueden enviar juntas.

Para configurar las divisiones de materiales peligrosos, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> División de materiales peligrosos**. En la página **División de materiales peligrosos**, puede crear cualquier número de divisiones y configurar cada una utilizando los campos que se describen en la tabla siguiente.

| Campo | Descripción |
|---|---|
| División | Introduzca un código para usar como número de referencia para la división. |
| Descripción | Especifique una descripción de la división. |
| Clase | Busque y asigne la clase a la que pertenece la división. |

## <a name="hazardous-material-compatibility-groups"></a><a name="compatibility-groups"></a>Grupos de compatibilidad de materiales peligrosos

Los grupos de compatibilidad de materiales peligrosos establecen qué clases y divisiones de materiales peligrosos se pueden enviar juntas. Cuando los operadores crean cargas o envíos en el almacén, pueden ejecutar una comprobación de compatibilidad que emitirá una advertencia si la carga o el envío incluye artículos que no pertenecen todos al mismo grupo de compatibilidad.

Estos datos de configuración no son específicos de cada entidad jurídica. Por lo tanto, puede tener un conjunto común de información sobre materiales peligrosos que se comparte entre todas sus entidades legales.

Para configurar los grupos de compatibilidad de materiales peligrosos, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Grupo de compatibilidad de materiales peligrosos**. En la página **Grupo de compatibilidad de materiales peligrosos**, puede crear cualquier número de grupos de compatibilidad y configurar cada uno utilizando los campos que se describen en las subsecciones siguientes.

### <a name="hazardous-material-compatibility-group-header"></a>Encabezado de grupo de compatibilidad de materiales peligrosos

Cada grupo de compatibilidad tiene un código y una descripción. En la tabla siguiente se describen los campos disponibles en el encabezado.

| Campo | Descripción |
|---|---|
| Grupo de compatibilidad | Introduzca un código que identifique el grupo de compatibilidad |
| Descripción | Especifique una descripción del grupo de compatibilidad. |

### <a name="compatibility-group-details"></a>Detalles de grupo de compatibilidad

Cada grupo de compatibilidad establece una lista de clases y divisiones de materiales peligrosos se pueden enviar juntas.

| Campo | Descripción |
|---|---|
| Clase | Seleccione una clase de material peligroso que sea compatible con todas las demás clases del grupo. |
| División | Seleccione una división de material peligroso que pertenezca a la clase seleccionada. |

## <a name="hazardous-material-specification-values"></a>Valores de especificación de materiales peligrosos

Microsoft Dynamics 365 Supply Chain Management proporciona diversos tipos de especificaciones de materiales peligrosos. Para cada tipo, debe establecer un conjunto centralizado de valores para cada campo relevante. Luego, los usuarios pueden seleccionar entre esos valores cuando configuran definiciones de materiales peligrosos o productos despachados. Supply Chain Management proporciona una colección de páginas donde puede establecer los valores. Cada página está dedicada a un tipo de especificación. Para obtener una descripción de cada especificación disponible e información sobre cómo establecer los valores que están disponibles para ella, consulte las siguientes subsecciones.

Un ejemplo de una especificación de material peligroso es el _código de estiba_, que especifica cómo se puede almacenar un material determinado durante el transporte. Al utilizar la información de esta sección, establecerá una colección central de códigos de estiba. Esta colección se presentará a los usuarios en una lista desplegable cuando establezcan el código de estiba para un producto despachado.

Estos valores de especificación de materiales peligrosos no son específicos de cada entidad legal. Por lo tanto, puede tener un conjunto de valores comunes que se comparten entre todas sus entidades jurídicas.

Usará [códigos de materiales](#hazmat-codes) para establecer colecciones comunes de configuraciones para cada especificación según se aplique a un reglamento determinado. A continuación, puede aplicar el código apropiado a cada producto despachado según sea necesario. Para obtener información sobre cómo aplicar un código de material peligroso a un producto despachado específico, y cómo configurar los ajustes individuales de ese producto para cualquier especificación que se describe aquí, consulte [Materiales peligrosos en productos, pedidos, envíos y cargas](hazmat-items.md).

### <a name="hazardous-material-emergency-response"></a>Respuesta de emergencia de material peligroso

La especificación *Respuesta a emergencias de materiales peligrosos* indica qué se debe hacer si algo sale mal mientras se transporta un producto que contiene un material peligroso determinado.

Para configurar los valores de esta especificación, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Respuesta de emergencia de materiales peligrosos**. En la página **Respuesta a emergencias de materiales peligrosos**, puede crear cualquier número de valores y configurar cada uno con un código de clasificación y una breve descripción.

### <a name="hazardous-material-identification"></a><a name="identification"></a>Identificación de material peligroso

La especificación *Identificación de material peligroso* identifica la clase o naturaleza de un material peligroso. El valor es normalmente un código que se basa en un estándar de las Naciones Unidas (ONU). Cada clase se identifica mediante un código y una descripción, y puede establecer límites en los métodos de transporte. Por ejemplo, para identificar un artículo o material inflamable, cree una clase de material peligroso que use el código *FL* y la descripción *Inflamable*. También especifica que la clase no debe ser transportada por aire.

Para configurar los valores de esta especificación, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Identificación de materiales peligrosos**. En la página **Identificación de materiales peligrosos**, puede crear cualquier número de valores y configurar cada uno utilizando los campos que se describen en la tabla siguiente.

| Campo | Descripción |
|---|---|
| Identificación | Introduzca un código para usar como número de referencia que identifique esta clase de material peligroso. |
| Descripción | Escriba una descripción de esta clase. |
| Restringir del transporte aéreo | Seleccione esta casilla para indicar que esta clase de material peligroso no debe transportarse por aire. |
| Restringir del transporte marítimo | Seleccione esta casilla para indicar que esta clase de material peligroso no debe transportarse por mar. |

### <a name="hazardous-material-label"></a><a name="label"></a>Etiqueta de material peligroso

La especificación *Etiqueta de material peligroso* identifica la etiqueta de mercancías peligrosas que debe aplicarse a los productos despachados pertinentes. Las etiquetas mismas describirán cómo se debe manipular el producto. Por ejemplo, tiene un producto que contiene un gas venenoso. En este caso, configure un código de etiqueta que represente la etiqueta de gas venenoso. También puede crear su proceso comercial para que busque este valor cuando envíe productos.

Para configurar los valores de esta especificación, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Etiqueta de materiales peligrosos**. En la página **Etiquetas de material peligroso**, puede crear cualquier número de etiquetas y configurar cada una con un código identificador y una breve descripción.

### <a name="hazardous-material-packing-descriptions"></a><a name="packing-description"></a>Descripciones de embalaje de material peligroso

La especificación *Descripciones de embalajes de materiales peligrosos* indica cómo debe embalarse un artículo peligroso. Por ejemplo, puede que tenga que embalarse en un tipo específico de tambor de acero o en algún otro tipo de embalaje especial.

Para configurar los valores de esta especificación, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Descripciones de embalaje de materiales peligrosos**. En la página **Descripciones de embalaje de material peligroso**, puede crear cualquier número de descripciones de embalaje y configurar cada una con un código identificador y una breve descripción.

### <a name="hazardous-material-packing-group"></a><a name="packing-group"></a>Grupo de embalaje de materiales peligroso

La especificación *Grupo de embalaje de material peligroso* identifica el grupo de embalaje de un artículo peligroso. El grupo de embalaje le permite definir un código y una descripción para indicar cómo se deben embalar los artículos de materiales peligrosos durante el transporte o envío. El grupo de embalaje se asigna al artículo mediante la página **Artículo de materiales peligrosos**.

Para configurar los valores de esta especificación, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Grupo de embalaje de materiales peligrosos**. En la página **Grupo de embalaje de material peligroso**, puede crear cualquier número de grupos de embalaje y configurar cada una con un código identificador y una breve descripción.

### <a name="hazardous-material-packing-instruction"></a><a name="packing-instruction"></a>Instrucción de embalaje de material peligroso

La especificación *Instrucciones de embalaje de material peligroso* identifica las instrucciones de embalaje que deben seguirse cuando se prepara un artículo peligroso para su transporte aéreo.

Para configurar los valores de esta especificación, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Instrucción de embalaje de materiales peligrosos**. En la página **Instrucción de embalaje de material peligroso**, puede crear cualquier número de identificadores de instrucción y configurar cada uno con un código identificador y una breve descripción.

### <a name="hazardous-material-stowage"></a><a name="stowage"></a>Estiba de material peligroso

La especificación *Estiba de material peligroso* indica cómo se debe almacenar un producto en un barco cuando se transporta por transporte marítimo.

Para configurar los valores de esta especificación, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Estiba de materiales peligrosos**. En la página **Estiba de material peligroso**, puede crear cualquier número de identificadores de estiba y configurar cada uno con un código identificador y una breve descripción.

### <a name="hazardous-material-transport-category"></a><a name="transport-category"></a>Categoría de transporte de material peligroso

La especificación *Categoría de transporte de material peligroso* se utiliza normalmente para agrupar productos peligrosos similares en informes. Por ejemplo, las categorías de transporte se utilizan en el informe **Resumen de envío**, que puede imprimir desde el registro de envío del almacén.

Para configurar los valores de esta especificación, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Categoría de transporte de materiales peligrosos**. En la página **Categoría de transporte de material peligroso**, puede crear cualquier número de categorías de transporte y configurar cada una con un nombre para mostrar y una breve descripción.

### <a name="hazardous-material-technical-name"></a><a name="technical-name"></a>Nombre técnico de material peligroso

La especificación *Nombre técnico del material peligroso* se puede utilizar para proporcionar un nombre de empresa interno o de uso común que describa cada material.

Para configurar los valores de esta especificación, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Nombre técnico de materiales peligrosos**. En la página **Nombre técnico de material peligroso**, puede crear cualquier número de nombres técnicos y configurar cada uno con un nombre para mostrar y una breve descripción.

### <a name="hazardous-material-tunnel"></a><a name="tunnel"></a>Túnel de material peligroso

La especificación *Túnel de material peligroso* limita los tipos de túneles a través de los cuales se puede transportar un material peligroso, identificando los tipos de túneles que deben usarse. Las categorías de túneles están establecidas por las regulaciones aplicables para el transporte de materiales peligrosos. Esta especificación generalmente se aplica solo al transporte por carretera.

Para configurar los valores de esta especificación, vaya a **Gestión de información de producto \> Configurar \> Documentación de envío de material peligroso \> Túnel de materiales peligrosos**. En la página **Túnel de material peligroso**, puede crear cualquier número de identificadores de túnel y configurar cada uno con un código identificador y una breve descripción.
