---
title: Preparación de producto
description: En estos temas se explica cómo puede utilizar las verificaciones de preparación para asegurarse de que se completen los datos maestros necesarios para un producto antes de que se utilicen en las transacciones.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 8321a0d8516a6c2c085ce9c1236f70af1cca98da
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967267"
---
# <a name="product-readiness"></a>Preparación de producto

[!include [banner](../includes/banner.md)]

Puede utilizar las verificaciones de preparación para asegurarse de que se completen todos los datos maestros necesarios para un producto antes de que se utilicen en las transacciones. Cuando se utilizan verificaciones de preparación, un usuario o equipo es responsable de validar datos específicos predefinidos relacionados con el producto. Si hay una verificación de disponibilidad abierta para un producto, el producto no se puede lanzar ni utilizar en transacciones.

La casilla **Activo** para un producto de ingeniería, variante o versión está disponible solo después de que se hayan ingresado y verificado todos los datos requeridos, y después de que se hayan procesado todas las verificaciones de preparación. En ese momento, el producto, la versión o la variante pueden entregarse a otras empresas y utilizarse en transacciones. Puede crear verificaciones de preparación para nuevos productos, nuevas variantes y nuevas versiones de ingeniería.

## <a name="types-of-readiness-checks"></a>Tipos de controles de preparación

Hay tres tipos de comprobaciones de preparación:

- **Chequeo del sistema** - El sistema verifica si existe un registro válido. Por ejemplo, el registro puede ser una lista de materiales (BOM) activa.
- **Verificación manual** - Un usuario verifica si el registro es válido. Por ejemplo, una verificación de preparación puede requerir la validación de la configuración predeterminada del pedido. En algunos casos, como cuando el producto aún se está diseñando y, por lo tanto, no se colocará en stock, no se requieren configuraciones de pedido predeterminadas. Sin embargo, es posible que se requiera una configuración de pedido predeterminada para otro producto del mismo tipo, ya que el producto se puede mantener en stock. El usuario es responsable de saber cómo decidir correctamente si se requiere una verificación de preparación.
- **Lista de Verificación** - El usuario responde una serie de preguntas de una lista de verificación y el sistema determina si las respuestas cumplen con las expectativas. La lista de verificación puede tener cualquier tema. Por ejemplo, se puede utilizar para determinar si se completan los materiales de marketing o la documentación del producto.

## <a name="how-readiness-checks-are-created-for-a-new-product-variant-or-version"></a>Cómo se crean las verificaciones de preparación para un nuevo producto, variante o versión

Cuando crea un nuevo **producto** de ingeniería, el sistema determina si se ha configurado una política de verificación de disponibilidad para la categoría de producto de ingeniería. (Las políticas de verificación de preparación se pueden aplicar en el nivel de producto publicado, el nivel de variante publicado y el nivel de versión de ingeniería). Si se ha configurado una política, se producen los siguientes eventos:

- Se crean verificaciones de preparación para el producto, de acuerdo con la política aplicable.
- La versión de ingeniería está configurada como inactiva para bloquear el uso del producto. Todas las versiones del producto específico involucrado están inactivas.

Si se crea una nueva **variante** para un producto, el sistema verifica si se han configurado verificaciones de preparación en la categoría de producto de ingeniería. (Las comprobaciones de preparación se pueden aplicar en el nivel de variante publicado y el nivel de versión de ingeniería). Si se ha configurado una comprobación de preparación, se producen los siguientes eventos:

- Se crean controles de preparación para el producto.
- La versión de ingeniería está configurada como inactiva para bloquear el uso del producto.

Si se crea una nueva **versión** de ingeniería para un producto, el sistema verifica si se han configurado verificaciones de preparación en la categoría de producto de ingeniería. (Las comprobaciones de preparación se pueden aplicar en el nivel de vesión de ingeniería). Si se ha configurado una comprobación de preparación, se producen los siguientes eventos:

- Se crean controles de preparación para el producto.
- La versión de ingeniería está configurada como inactiva para bloquear el uso del producto.

## <a name="view-readiness-checks"></a>Ver verificaciones de preparación

### <a name="view-open-readiness-checks-for-a-product-or-product-version"></a>Ver comprobaciones de preparación abiertas para un producto o versión de producto

Para encontrar las comprobaciones de disponibilidad abiertas para un producto, abra la página **Detalles de productos publicados**. A continuación, en el panel de acciones, en la pestaña **Producto** del grupo **Comprobaciones de preparación**, haga clic en **Comprobaciones de preparción**.

Para encontrar las comprobaciones de disponibilidad abiertas para una versión de producto, abra la página **Versiones de ingeniería** de un producto lanzado y elija una versión. A continuación, en el panel de acciones, en la pestaña **Producto** del grupo **Lista de comprobación**, haga clic en **Comprobaciones de preparción**.

### <a name="view-open-readiness-checks-that-are-assigned-to-you"></a>Ver las verificaciones de preparación abiertas que se le asignaron

Para ver las comprobaciones de disponibilidad abiertas que se le asignaron, siga uno de estos pasos.

- Ir **Gestión de cambios de ingeniería \> Común \> Disponibilidad del producto \> Mis comprobaciones abiertas de preparación**.
- Ir **Gestión de información de producto \> Espacios de trabajo \> Disponibilidad del producto para fabricación discreta**.

La configuración que especifica a quién se asigna una verificación de preparación se realiza para la categoría de producto de ingeniería. Los controles de preparación pueden asignarse a una persona o un equipo. Si se asigna una verificación de preparación a un equipo, hay una persona en el equipo que debe procesar la verificación de disponibilidad. Para más información, vea [Versiones de ingeniería y categorías de productos de ingeniería](engineering-versions-product-category.md).

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

Utilice las políticas de preparación del producto para administrar las comprobaciones de preparación que se aplican a un producto. Dado que se asigna una política de preparación a la categoría de ingeniería, todas las comprobaciones de la política de preparación se aplican a todos los productos de ingeniería que se basan en la categoría de ingeniería. Para más información, vea [Versiones de ingeniería y categorías de productos de ingeniería](engineering-versions-product-category.md).

Cada política de preparación contiene un conjunto de comprobaciones de preparación. Cuando se asigna una política de preparación a una categoría de productos de ingeniería, todos los productos que se crean a partir de esa categoría de productos de ingeniería tendrán las verificaciones de preparación que se indican en la política de preparación.

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
| Activa | Utilice esta opción para ayudar a mantener sus políticas de preparación. Ponlo en *Sí* para todas las políticas de preaparación que utilice. Ponlo en *No* para marcar una política de preparación como inactiva cuando no se utiliza. Tenga en cuenta que no puede desactivar una política de preparación asignada a una categoría de producto de ingeniería y solo puede eliminar las políticas de lanzamiento inactivas. |

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
| Nombre | Si la verificación es una lista de verificación, ingrese un nombre. Para las verificaciones manuales y del sistema, este campo se configura automáticamente. |
| Descripción | Si la verificación es una lista de verificación, ingrese una descripción. Para las verificaciones manuales y del sistema, este campo se establece automáticamente y la descripción explica el enfoque de la verificación. |
| Aplicar controles en | Seleccione si la fila debe generar verificaciones de preparación en respuesta a un nuevo producto lanzado, una variante lanzada o una versión lanzada. |
| Ejecutar en | Seleccione si las comprobaciones de preparación que genera la fila se aplican a todas las empresas o a una sola empresa. |
| Empresa | Si configura el campo **Ejecutar en** como *Empresa única*, seleccione la empresa. |
| Tipo de propietario | Seleccione si las comprobaciones de preparación que genera la fila deben asignarse a una persona o un equipo. |
| Propietario | Seleccione la persona o equipo al que se deben asignar las comprobaciones de preparación que genera la fila. |
| Cuestionarios | Seleccione el cuestionario que debe usarse para la lista de verificación. La lista de verificación es una lista de verificación local en la empresa donde se realiza la verificación de preparación. El sistema debe poder evaluar si la lista de verificación se responde correctamente. Por lo tanto, la lista de verificación debe configurarse de manera que se realice una evaluación basada en las respuestas correctas. Para obtener más información sobre cómo crear cuestionarios, consulte [Usando cuestionarios](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/using-questionnaires) y sus temas relacionados. |
| Aprobación automática | Los registros de verificación de preparación incluyen una casilla **Aprobado** que indica el estado de aprobación. Seleccione la casilla **Aprobación automática** para verificaciones que deben establecerse como aprobadas inmediatamente después de que el usuario asignado las complete. Desactive esta casilla de verificación para solicitar una aprobación explícita como paso adicional. |
| Obligatoria | Seleccione esta casilla de verificación para las comprobaciones que debe completar el usuario asignado. Los controles obligatorios no se pueden omitir. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]