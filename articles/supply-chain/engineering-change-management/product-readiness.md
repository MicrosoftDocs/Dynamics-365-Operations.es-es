---
title: Preparación de producto
description: En este artículo se explica cómo puede utilizar las verificaciones de preparación para asegurarse de que se completen los datos maestros necesarios para un producto antes de que se utilicen en las transacciones.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a8e76d5fc786b6f4cac7cd0430399ca3ad13a7bc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856233"
---
# <a name="product-readiness"></a>Preparación de producto

[!include [banner](../includes/banner.md)]

Puede utilizar las comprobaciones de preparación para intentar asegurarse de que se completen todos los datos maestros necesarios para un producto antes de utilizarlo en las transacciones. Cuando se utilizan verificaciones de preparación, un usuario o equipo es responsable de validar datos específicos predefinidos relacionados con el producto.

Puede marcar la casilla **Activo** para un producto de ingeniería, variante o versión después de que se hayan introducido y verificado todos los datos requeridos, y después de que se hayan procesado todas las comprobaciones de preparación. Si una o más comprobaciones no se han procesado para el producto, la versión o la variante, cuando intente marcar la casilla **Activo** recibirá una advertencia que le indicará que no se han completado todas las comprobaciones.

Puede crear comprobaciones de preparación para nuevos productos, nuevas variantes y nuevas versiones de ingeniería. También puede aplicar comprobaciones de preparación a productos estándar (que no sean de ingeniería) (consulte también [Comprobaciones de preparación en productos estándar](#standard-products)). 

Puede utilizar productos estándar en transacciones aunque no se hayan completado todas las comprobaciones de preparación. Si necesita bloquear un producto para que no se use en transacciones, use su estado de ciclo de vida. Puede asignar un estado de ciclo de vida que bloquee el uso de un producto en transacciones y luego, después de que se hayan completado todas las comprobaciones de preparación, asignar un nuevo estado de ciclo de vida que permita las transacciones requeridas.

## <a name="types-of-readiness-checks"></a>Tipos de controles de preparación

Hay tres tipos de comprobaciones de preparación:

- **Chequeo del sistema** - El sistema verifica si existe un registro válido. Por ejemplo, el registro puede ser una lista de materiales (BOM) activa.
- **Verificación manual** - Un usuario verifica si el registro es válido. Por ejemplo, una verificación de preparación puede requerir la validación de la configuración predeterminada del pedido. En algunos casos, como cuando el producto aún se está diseñando y, por lo tanto, no se colocará en stock, no se requieren configuraciones de pedido predeterminadas. Sin embargo, es posible que se requiera una configuración de pedido predeterminada para otro producto del mismo tipo, ya que el producto se puede mantener en stock. El usuario es responsable de saber cómo decidir correctamente si se requiere una verificación de preparación.
- **Lista de Verificación** - El usuario responde una serie de preguntas de una lista de verificación y el sistema determina si las respuestas cumplen con las expectativas. La lista de verificación puede tener cualquier tema. Por ejemplo, se puede utilizar para determinar si se completan los materiales de marketing o la documentación del producto.

<a name="checks-engineering"></a>

## <a name="how-readiness-checks-are-created-for-a-new-engineering-product-variant-or-version"></a>Cómo se crean las verificaciones de preparación para un nuevo producto de ingeniería, variante o versión

Las políticas de verificación de preparación se pueden aplicar en el nivel de producto publicado, el nivel de variante publicado y el nivel de versión de ingeniería.

Cuando crea un nuevo *producto de ingeniería*, el sistema determina si [se le aplica la política de verificación de preparación](#assign-policy). Si se aplica una política de verificación de preparación, se producen los siguientes eventos:

- Se crean verificaciones de preparación para el producto, de acuerdo con la política aplicable.
- La versión de ingeniería está configurada como inactiva para bloquear el uso del producto. Todas las versiones de ingeniería del producto están inactivas.

Si se crea una *variante* nueva para un producto, el sistema verifica si se le aplica una política de verificación de disponibilidad. (Las comprobaciones de preparación se pueden aplicar en el nivel de variante publicado y el nivel de versión de ingeniería). Si una directiva se aplica, se producen los siguientes eventos:

- Se crean verificaciones de preparación para el producto, de acuerdo con la política aplicable.
- La versión de ingeniería y variante están configuradas como inactivas para bloquear el uso del producto.

Si se crea una *versión* de ingeniería para un producto, el sistema verifica si se le aplica una política de verificación de disponibilidad. (Las comprobaciones de preparación se pueden aplicar en el nivel de versión de ingeniería). Si una directiva se aplica, se producen los siguientes eventos:

- Se crean verificaciones de preparación para el producto, de acuerdo con la política aplicable.
- La versión de ingeniería está configurada como inactiva para bloquear el uso del producto.

> [!NOTE]
> También puede configurar verificaciones de directivas de preparación para productos estándar (que no sean de ingeniería). (Para obtener más información, consulte la sección [Comprobaciones de preparación de productos estándar](#standard-products) más adelante en este artículo).

## <a name="view-readiness-checks"></a>Ver verificaciones de preparación

### <a name="view-open-readiness-checks-for-a-product-or-product-version"></a>Ver comprobaciones de preparación abiertas para un producto o versión de producto

Para encontrar las comprobaciones de disponibilidad abiertas para un producto, abra la página **Detalles de productos publicados**. A continuación, en el panel de acciones, en la pestaña **Producto** del grupo **Comprobaciones de preparación**, haga clic en **Comprobaciones de preparción**.

Para encontrar las comprobaciones de disponibilidad abiertas para una versión de producto, abra la página **Versiones de ingeniería** de un producto lanzado y elija una versión. A continuación, en el panel de acciones, en la pestaña **Producto** del grupo **Lista de comprobación**, haga clic en **Comprobaciones de preparción**.

### <a name="view-open-readiness-checks-that-are-assigned-to-you"></a>Ver las verificaciones de preparación abiertas que se le asignaron

Para ver las comprobaciones de disponibilidad abiertas que se le asignaron, siga uno de estos pasos.

- Ir **Gestión de cambios de ingeniería \> Común \> Disponibilidad del producto \> Mis comprobaciones abiertas de preparación**.
- Ir **Gestión de información de producto \> Espacios de trabajo \> Disponibilidad del producto para fabricación discreta**.

La configuración que especifica a quién se asigna una verificación de preparación se realiza para la directiva de preparación. Los controles de preparación pueden asignarse a una persona o un equipo. Si se asigna una verificación de preparación a un equipo, hay una persona en el equipo que debe procesar la verificación de disponibilidad.

## <a name="process-open-readiness-checks"></a>Procesar comprobaciones de disponibilidad abiertas

### <a name="process-system-and-manual-readiness-checks"></a>Verificaciones de preparación manual y del sistema de proceso

Después de abrir la página **Verificaciones de preparación**, puede ver el tema de las verificaciones de preparación del sistema y manuales seleccionando **Ver información relacionada** en el Panel de acciones. Luego, puede completar y / o validar los datos para la verificación de preparación. Los controles de disponibilidad abiertos tienen un valor de **Estado** *Pendiente*. Este estado indica que la verificación de disponibilidad aún debe procesarse. Para procesar una comprobación de preparación, siga uno de estos pasos:

- En el panel de acciones, seleccione **Verificar/completar** para revisar y completar la verificación de preparación. Cuando haya terminado, el campo **Estado** se actualiza como *Aprobado*.
- En el panel de acciones, seleccione **Omitir** si desea omitir una verificación de preparación que no es obligatoria. Por ejemplo, configura una verificación de disponibilidad para los cálculos de precios. Sin embargo, decide omitir esta verificación mientras el producto aún se encuentra en la fase de diseño. En este caso, el campo **Estado** se actualiza a *Omitido*.

Dependiendo de la configuración de la política de preparación, cuando el campo **Estado** para una verificación de preparación se actualiza a *Aprobado*, es posible que se requiera un paso adicional para aprobar la verificación de disponibilidad. En este caso, seleccione **Aprobación** para completar la verificación de disponibilidad. Este paso de aprobación siempre es obligatorio cuando se omite la verificación de disponibilidad.

Cuando todas las verificaciones de disponibilidad abiertas para un nuevo producto, variante o versión se han procesado y aprobado según sea necesario, el artículo se activa automáticamente y, por lo tanto, está listo para usar.

### <a name="process-checklist-readiness-checks"></a>Procesar comprobaciones de disponibilidad de lista de comprobación

Para abrir una lista de verificación, abra la página **Verificaciones de preparación** y, a continuación, en el panel de acciones, seleccione **Iniciar lista de verificación**. Cuando haya completado la lista de verificación, el sistema valida si se aprueba la verificación de preparación, según la configuración del cuestionario. Si se aprueba la comprobacióǹ, el campo **Estado** se actualiza a *Aprobado*. Si la verificación de preparación no es obligatoria, puede omitirla. En este caso, el campo **Estado** se actualiza a *Omitido*.

Dependiendo de la configuración de la política de preparación, cuando el campo **Estado** para una verificación de preparación se actualiza a *Aprobado*, es posible que se requiera un paso adicional para aprobar la verificación de disponibilidad. En este caso, seleccione **Aprobación** para completar la verificación de disponibilidad. Este paso de aprobación siempre es obligatorio cuando se omite la verificación de disponibilidad.

Cuando todas las verificaciones de disponibilidad abiertas para un nuevo producto, variante o versión se han procesado y aprobado según sea necesario, el artículo se activa automáticamente y, por lo tanto, está listo para usar.

## <a name="create-and-manage-product-readiness-policies"></a>Crear y administrar políticas de preparación de productos

Utilice las políticas de preparación del producto para administrar las comprobaciones de preparación que se aplican a un producto. Cada política de preparación contiene un conjunto de comprobaciones de preparación. Cuando se asigna una política de preparación a una categoría de productos de ingeniería o producto compartido, todos los productos que están relacionados con esa categoría o producto compartido tendrán las verificaciones de preparación que se incluyen en la directiva de preparación.

Para trabajar con directivas de preparación de productos, vaya a **Gestión de cambios de ingeniería \> Preparar \> Directivas de preparación de productos**. Luego siga uno de estos pasos.

- Para crear una nueva directiva, seleccione **Nuevo** en el Panel de acciones y luego configure los campos como se describe en las siguientes subsecciones.
- Para editar una directiva existente, selecciónelo en el panel de lista, seleccione **Editar** en el Panel de acciones y luego configure los campos como se describe en las siguientes subsecciones.
- Para eliminar una política existente, selecciónela en el panel de lista, seleccione **Editar** en el Panel de acciones, y luego, en la ficha desplegable **General**, asegúrese de que la opción **Activo** está configurada en *No*. A continuación, seleccione **Eliminar** en el panel de acciones.

### <a name="header"></a>Encabezado

Configure los siguientes campos en el encabezado de una directiva de preparación de producto.

| Campo | Descripción |
|---|---|
| Nombre | Introduzca un nombre para la directiva. |
| Descripción | Especificar una descripción de la directiva. |

### <a name="general-fasttab"></a>Ficha desplegable General

Configure los siguientes campos en la ficha desplegable **General** de una directiva de preparación de producto.

| Campo | Descripción |
|---|---|
| Tipo de producto | Seleccione si la política se aplica a los productos de tipo *Artículo* o *Servicio*. No puede cambiar esta configuración después de guardar el registro. |
| Activa | Utilice esta opción para ayudar a mantener sus políticas de preparación. Ponlo en *Sí* para todas las políticas de preaparación que utilice. Ponlo en *No* para marcar una política de preparación como inactiva cuando no se utiliza. Tenga en cuenta que no puede desactivar una política de preparación asignada a una categoría de producto de ingeniería o un producto compartido y solo puede eliminar las políticas de lanzamiento inactivas. |

### <a name="readiness-control-fasttab"></a>Ficha desplegable de control de preparación

Para cada tipo de verificación de preparación que desee incluir en la política, agregue una fila en la ficha desplegable **Control de disponibilidad**. Utilice los siguientes botones de la barra de herramienats de la ficha desplegable para agregar y eliminar filas según sea necesario:

- **Agregar cheque** - Agregue una verificación de preparación estándar a la política. Cuando selecciona este botón, el cuadro de diálogo **Agregar cheque** aparece. Allí, puede seleccionar de una lista de cheques disponibles.
- **Agregar cuestionario existente** - Agregue una fila en blanco a la cuadrícula. Luego puede asignar un cuestionario existente configurando los campos en la siguiente tabla.
- **Copiar** - Agregue una copia de la fila seleccionada a la cuadrícula.
- **Eliminar** - Eliminar la fila seleccionada de la cuadrícula.

Para cada fila que agregue, configure los siguientes campos.

| Campo | Descripción |
| --- | --- |
| Área de proceso | Seleccione el área con la que está relacionada la verificación. |
| Tipo | Seleccione si la verificación es una verificación del sistema, una verificación manual o una lista de verificación (cuestionario). |
| Nombre | Si la verificación es una lista de verificación, introduzca un nombre. Para las verificaciones manuales y del sistema, este campo se configura automáticamente. |
| Descripción | Si la verificación es una lista de verificación, introduzca una descripción. Para las verificaciones manuales y del sistema, este campo se establece automáticamente y la descripción explica el enfoque de la verificación. |
| Aplicar controles en | Seleccione si la fila debe generar verificaciones de preparación en respuesta a un nuevo producto lanzado, una variante lanzada o una versión lanzada. |
| Ejecutar en | Seleccione si las comprobaciones de preparación que genera la fila se aplican a todas las empresas o a una sola empresa. |
| Empresa | Si configura el campo **Ejecutar en** como *Empresa única*, seleccione la empresa. |
| Tipo de propietario | Seleccione si las comprobaciones de preparación que genera la fila deben asignarse a una persona o un equipo. |
| Propietario | Seleccione la persona o equipo al que se deben asignar las comprobaciones de preparación que genera la fila. |
| Cuestionarios | Seleccione el cuestionario que debe usarse para la lista de verificación. La lista de verificación es una lista de verificación local en la empresa donde se realiza la verificación de preparación. El sistema debe poder evaluar si la lista de verificación se responde correctamente. Por lo tanto, la lista de verificación debe configurarse de manera que se realice una evaluación basada en las respuestas correctas. Para obtener más información sobre cómo crear cuestionarios, consulte [Usando cuestionarios](/dynamicsax-2012/appuser-itpro/using-questionnaires) y sus artículos relacionados. |
| Aprobación automática | Los registros de verificación de preparación incluyen una casilla **Aprobado** que indica el estado de aprobación. Seleccione la casilla **Aprobación automática** para verificaciones que deben establecerse como aprobadas inmediatamente después de que el usuario asignado las complete. Desactive esta casilla de verificación para solicitar una aprobación explícita como paso adicional. |
| Obligatoria | Seleccione esta casilla de verificación para las comprobaciones que debe completar el usuario asignado. Los controles obligatorios no se pueden omitir. |

<a name="assign-policy"></a>

## <a name="assign-readiness-policies-to-standard-and-engineering-products"></a>Asignar directivas de preparación a productos estándar y de ingeniería

Cuando crea un nuevo producto basado en una categoría de ingeniería, crea un *producto lanzado* y un *producto compartido* relacionado. La forma en que se resuelven las políticas de preparación para un producto lanzado depende de si la característica *Comprobaciones de preparación de producto* está activada para su sistema (consulte la sección [Comprobaciones de preparación de productos estándar](#standard-products) más adelante en este artículo para obtener detalles sobre esta característica y cómo activarla o desactivarla).

- Cuando la función *Comprobaciones de disponibilidad del producto* está *desactivada* en su sistema, la directiva de preparación se establece y se muestra solo en los registros de [categoría de ingeniería](engineering-versions-product-category.md). Para saber qué directiva se aplica a un producto lanzado, el sistema verifica el campo **Directiva de preparación del producto** para la categoría de ingeniería relacionada. Puede cambiar la directiva de preparación de un producto existente editando la categoría de ingeniería relacionada (no el producto compartido).
- Cuando la función *Comprobaciones de disponibilidad del producto* está *activada*, agrega un campo **Política de preparación del producto** a la página **Producto** (donde se configuran los productos compartidos) y a la página **Producto lanzado** (donde el valor es de solo lectura y se toma del producto compartido relacionado). El sistema encuentra la directiva de preparación para un producto lanzado al verificar el producto compartido relacionado. Cuando utiliza una categoría de ingeniería para crear un nuevo producto de ingeniería, el sistema crea tanto un producto compartido como un producto lanzado, y copia cualquier configuración de **Directiva de preparación del producto** de la categoría de ingeniería para el nuevo producto compartido. Entonces puede cambiar la directiva de preparación de un producto existente editando el producto compartido (no la categoría de ingeniería de lanzamiento).

Para asignar una directiva de preparación a un producto compartido, siga estos pasos:

1. Vaya a **Información de producto \> Productos \> Productos**.
1. Abra o cree el producto al que desea asignar una política de preparación.
1. En la ficha desplegable **General**, establezca el campo **Política de preparación del producto** al nombre de la directiva que debe aplicarse al producto.

Para asignar una directiva de preparación a una categoría de ingeniería, siga estos pasos:

1. Vaya a **Gestión de cambios de ingeniería \> Configuración \> Detalles de la categoría de productos de ingeniería**.
1. Abra o cree la categoría de ingeniería al que desea asignar una política de preparación.
1. En la ficha desplegable **Directiva de preparación del producto**, establezca el campo **Política de preparación del producto** al nombre de la directiva que debe aplicarse a la categoría de ingeniería.

<a name="standard-products"></a>

## <a name="readiness-checks-on-standard-products"></a>Comprobaciones de preparación de productos estándar

Puede habilitar las comprobaciones de disponibilidad de productos para productos estándar (que no sean de ingeniería) activando la función *Comprobaciones de disponibilidad del producto* en la administración de características. Esta característica realiza algunos pequeños cambios en el sistema de verificación de disponibilidad para que admita productos estándar.

### <a name="enable-or-disable-readiness-checks-on-standard-products"></a>Activar o desactivar comprobaciones de preparación de productos estándar

Esta característica requiere que se activen las características *Gestión de cambios de ingeniería* y *Comprobaciones de preparación de producto* en su sistema. Para obtener detalles sobre cómo activar o desactivar estas características, consulte [Información general de la gestión de cambios de ingeniería](product-engineering-overview.md).

### <a name="create-readiness-policies-for-standard-products"></a>Cree políticas de preparación para productos estándar

Puede crear políticas de preparación para productos estándar del mismo modo que lo hace para productos de ingeniería. Consulte la información anterior en este artículo.

### <a name="assign-readiness-policies-to-standard-products"></a>Asignar políticas de preparación a productos estándar

Para asignar una directiva de preparación a un producto estándar, abra el producto compartido relacionado y configure el campo **Directiva de preparación del producto** al nombre de la directiva que se debe aplicar. Para obtener más información, consulte la sección [Asignar políticas de preparación a productos estándar y de ingeniería](#assign-policy) anterior en este artículo.

### <a name="view-and-process-readiness-checks-on-standard-products"></a>Ver y procesar comprobaciones de preparación de productos estándar

Cuando esta función está activada, puede ver y procesar las comprobaciones de preparación para productos estándar de la misma manera que lo hace para productos de ingeniería. Consulte la información anterior en este artículo.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
