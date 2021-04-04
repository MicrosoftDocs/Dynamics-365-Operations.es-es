---
title: Encontrar información mediante el uso de búsquedas
description: Muchos campos tienen búsquedas que pueden ayudarle a encontrar el valor correcto o deseado con facilidad. Varias mejoras se han agregado a las búsquedas para que estos controles sean más utilizables y para que los usuarios sean más productivos. En este tema, aprenderá estas nuevas características de búsquedas y recibirá algunas sugerencias útiles para el uso óptimo de las búsquedas en el sistema.
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ae5f31c2cc46bf395acfbd053168e88aa69ebdc
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566303"
---
# <a name="find-information-by-using-lookups"></a>Encontrar información mediante el uso de búsquedas

[!include [banner](../includes/banner.md)]

Muchos campos tienen búsquedas que pueden ayudarle a encontrar el valor correcto o deseado con facilidad. Varias mejoras se han agregado a las búsquedas para que estos controles sean más utilizables y para que los usuarios sean más productivos. En este tema, aprenderá estas nuevas características de búsquedas y recibirá algunas sugerencias útiles para el uso óptimo de las búsquedas en el sistema.

## <a name="responsive-lookups"></a>Búsquedas con capacidad de respuesta

En versiones anteriores, al interactuar con un control de búsqueda, un usuario tenía que realizar una acción explícita para abrir el menú desplegable. Podía ser escribir un asterisco (\*) en el control para filtrar la búsqueda por el valor actual del control, hacer clic en el botón desplegable o usar el método abreviado de teclado **Alt**+**Flecha hacia abajo**. Los controles de búsqueda se han modificado de las siguientes maneras para adaptarse mejor a las prácticas web actuales:

- Los menús desplegables de la búsqueda ahora se abrirán automáticamente después de una pausa breve al escribir, con el contenido del menú desplegable filtrado por el valor del control de la búsqueda.

    Tenga en cuenta que el antiguo método de apertura automática del menú desplegable después de escribir un asterisco (\*) se ha dejado de utilizar.

- Una vez que haya abierto el menú desplegable de búsqueda, sucederá lo siguiente:

    - El cursor permanecerá en el control de la búsqueda (en vez de que el foco se mueva al menú desplegable) para que pueda continuar realizando modificaciones en el valor de control. Sin embargo, el usuario puede seguir utilizando la **flecha hacia arriba** y la **flecha hacia abajo** para cambiar las filas en el menú desplegable e Entrar para seleccionar la fila actual del menú desplegable.
    - El contenido del menú desplegable se ajustará tras realizar cualquier modificación en el valor de control de la búsqueda.

Por ejemplo, supongamos un campo de búsqueda denominado **Ciudad**.

Si el foco se encuentra en el campo **Ciudad**, puede comenzar a buscar la ciudad que desea escribiendo unas pocas letras como “col.” Una vez que pare de escribir, la búsqueda se abrirá automáticamente y filtrará las ciudades que comienzan por “col.”.

[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png)

En este punto, el cursor se encuentra todavía en el campo de búsqueda. Si continúa escribiendo hasta el valor ”colum." el contenido de la búsqueda se ajustará automáticamente para reflejar el último valor del control.

![updateFilterLookupExample](./media/updatefilterlookupexample.png)

Aunque el foco siga en el control de la búsqueda, puede usar también las teclas de **flecha hacia arriba** o **flecha hacia abajo** para resaltar la fila que desee seleccionar. Si pulsa **Entrar** la fila resaltada se seleccionará en la búsqueda y se actualizará el valor del control.

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Escribir más que Id.

Al especificar datos, es natural que los usuarios intenten identificar una entidad, como un cliente o un proveedor, por el nombre en lugar de por un identificador que representa a la entidad. Muchas (pero no todas) búsquedas ahora permiten la entrada de datos contextual. Esta potente característica permite al usuario escribir el id. o el nombre correspondiente en el control de la búsqueda.

Por ejemplo, supongamos un campo **Cuenta de cliente** al crear un pedido de ventas. Este campo muestra el **Id. de cuenta** para el cliente, pero un usuario preferiría normalmente especificar un **Nombre de cuenta** en lugar de un **Id. de cuenta** para este campo al crear un pedido de ventas como “Forest Wholesales “en lugar de “US-003”.

Si el usuario ha empezado a introducir un **Id. de cuenta** en el control de la búsqueda, el menú desplegable se abrirá automáticamente como se describe en la sección anterior y el usuario verá la búsqueda de la siguiente forma.

[![Búsqueda contextual al introducir un Id. de cuenta de un cliente](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

Sin embargo, el usuario también puede especificar ahora el principio de un **Nombre de cuenta**. Si se detecta esto, el usuario verá la siguiente búsqueda. Vea cómo la columna **Nombre** se mueve a la primera columna de la búsqueda y cómo la búsqueda se ordena y se filtra por la columna **Nombre**.

[![Búsqueda contextual al introducir un nombre de un cliente](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Uso de los encabezados de las columnas de la cuadrícula para un filtrado y una ordenación más avanzados

Las mejoras de las búsquedas descritas en las dos secciones anteriores mejoran significativamente la capacidad de un usuario de desplazarse por las filas en una búsqueda "empieza por" del campo **Id.** o **Nombre** de la búsqueda. Sin embargo, existen situaciones en las que un filtrado más avanzado (o una ordenación) es necesario para encontrar la fila correcta. En estos casos, el usuario necesita utilizar las opciones de filtro y de ordenación en los encabezados de las columnas de la cuadrícula dentro de la búsqueda. Por ejemplo, supongamos que un empleado está introduciendo una línea de pedido de ventas y necesita localizar el "cable" correcto como producto. Escribir “cable” en el control **código de artículo** no es útil, ya que no hay nombres de producto que empiezan por “cable.”

![emptyitemlookup](./media/emptyitemlookup.png)

En su lugar, el usuario necesita borrar el valor del control de la búsqueda, abrir el menú desplegable de búsqueda y filtrar el menú desplegable con el encabezado de la columna de la cuadrícula, como se muestra a continuación. Un usuario de ratón (o táctil) puede hacer clic (o tocar) en cualquier encabezado de columna para obtener acceso a las opciones de filtro y de ordenación de dicha columna. Para un usuario de teclado, el usuario solo tiene que pulsar **Alt**+**flecha** **hacia abajo** una segunda vez para mover el foco al menú desplegable y después puede pulsar en la columna correcta y en **Ctrl**+**G** para abrir el menú desplegable del encabezado de la columna de la cuadrícula.

[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png)

Después de que se haya aplicado el filtro (consulte la imagen a continuación), el usuario puede buscar y seleccionar la fila como de costumbre.

![filtereditemlookup](./media/filtereditemlookup.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]