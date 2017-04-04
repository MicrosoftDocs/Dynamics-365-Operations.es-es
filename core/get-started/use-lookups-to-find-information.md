---
title: "Búsquedas de uso para encontrar la información"
description: "En Microsoft Dynamics 365 para las operaciones, muchos campos búsquedas tienen que pueden ayudarle con facilidad a encontrar el valor correcto o deseado. Varios mejoras se han agregado a las búsquedas que crean estos controles más utilizables a partir crean y a usuarios más productivas. En este tema, es aprenderá sobre estas características nuevas de búsqueda y recibirá algunas sugerencias útiles para salir del uso óptimo fuera de búsquedas en el sistema."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 6a25593632575dcd71fa4a3c9cf5b83c9f8ecd39
ms.lasthandoff: 03/31/2017


---

# <a name="use-lookups-to-find-information"></a>Búsquedas de uso para encontrar la información

En Microsoft Dynamics 365 para las operaciones, muchos campos búsquedas tienen que pueden ayudarle con facilidad a encontrar el valor correcto o deseado. Varios mejoras se han agregado a las búsquedas que crean estos controles más utilizables a partir crean y a usuarios más productivas. En este tema, es aprenderá sobre estas características nuevas de búsqueda y recibirá algunas sugerencias útiles para salir del uso óptimo fuera de búsquedas en el sistema.  

<a name="responsive-lookups"></a>Búsquedas responsivas
------------------

En versiones anteriores de las Dynamics 365 para las operaciones, al interactuar con un control de la búsqueda, un usuario que tendría tomar medidas explícitas para abrir el menú desplegable. Esto podría haber estado escribiendo un asterisco (\*) en el control para filtrar la búsqueda basada en el valor actual del control, haciendo clic en el botón desplegable, o mediante ** Alt **+** Flecha abajo ** método abreviado de teclado. Los controles de la búsqueda se hayan modificado de las siguientes maneras para mejorar alinearla con prácticas web actuales:

-   Los menús desplegables de la búsqueda ahora abrirá automáticamente después de una pausa en leve escribir, con el contenido del menú desplegable filtrados según el valor del control de la búsqueda.
    -   Tenga en cuenta que el antiguo comportamiento de apertura automática de desplegable después de escribir un asterisco (\*) se ha dejado de utilizar.
-   Una vez que haya abierto el menú desplegable de búsqueda, lo siguiente: aparecerá
    -   El cursor permanecerá en el control de la búsqueda (en lugar del enfoque que desplaza en el menú desplegable) para que pueda continuar realizando modificaciones sobre el valor de control. Sin embargo, el usuario puede seguir utilizando ** flecha hacia arriba ** y ** Flecha abajo ** cambiar filas en el menú desplegable, y especifica para seleccionar la ficha actual en el menú desplegable.
    -   El contenido del menú desplegable ajustarán después de las modificaciones que se cree el valor de control de la búsqueda.

Por ejemplo, considere un campo de búsqueda denominado ** ** ciudad. 

Cuando el enfoque se encuentra en ** ciudad ** campo, puede iniciar buscar en la ciudad que desea escribiendo algunas cartas, como “columna.”  Una vez que detenga el escribir, la búsqueda abrirá automáticamente, filtrado ciudades a aquellas que comienzan por la columna “”. 

[typeaheadLookupExample de![] (. /media/typeaheadlookupexample.png])(. /media/typeaheadlookupexample.png) 

En este punto, el cursor se encuentra todavía en el campo de búsqueda. Si continúa escribiendo por lo que el valor es “,” colum el ajuste del contenido de la búsqueda automáticamente para reflejar el último valor del control. 

![updateFilterLookupExample](./media/updatefilterlookupexample.png) 

Aunque el enfoque se encuentra todavía en el control de la búsqueda, puede usar ** flecha hacia arriba o ** ** Flecha abajo ** las teclas para resaltar la fila que desee seleccionar. Si pulsa ** Entrar ** la fila seleccionada se resaltado de búsqueda y el valor de control se actualizarán. 

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>El escribir en más de id.
Al especificar datos, es natural que los usuarios intenten identificar a una entidad, como un cliente o un proveedor, en términos de nombre en lugar de un identificador que representa la entidad. En la versión actual de Dynamics 365 para las operaciones, muchas (pero no todas las búsquedas) ahora permiten la entrada de datos contextual. Esta característica potente permite al usuario escriba el identificador o el nombre correspondiente en el control de la búsqueda. 

Por ejemplo, considere ** cuenta de cliente ** colocan al crear un pedido de ventas. Este campo muestra ** identificador de la cuenta ** para el cliente, pero un usuario preferiría normalmente especificar ** nombre de cuenta ** en lugar de ** el identificador de la cuenta ** para este campo al crear un pedido de ventas, como “Forest Wholesales “en lugar de “US-003”.

Si abrir el usuario iniciado para especificar ** identificador de la cuenta ** de control de la búsqueda, el menú desplegable automáticamente como describe en la sección anterior y el usuario visto la búsqueda como se muestra a continuación.

[contextual búsqueda![Cuando se especifica una cuenta de cliente (]. /media/howtocontextuallookups-1.png])(. /media/howtocontextuallookups-1.png)

Sin embargo, el usuario también puede especificar el principio de ** nombre de cuenta ** también. Si se detecta esto, el usuario verá la próxima búsqueda. Aviso cómo ** nombre ** la columna se mueve a la primera columna en la búsqueda, y cómo la búsqueda se clasifica y se filtra según ** ** nombre de la columna.

[contextual búsqueda![Cuando se especifica un nombre de cliente (]. /media/howtocontextuallookups-2.png])(. /media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Mediante los encabezados de columnas de la cuadrícula para un filtrado más avanzada y la ordenación
Los incrementos de la búsqueda discutidos en las dos secciones anteriores mejoran significativamente la capacidad de un usuario para navegar las filas en una búsqueda en función de los “comience con” la búsqueda ** ** de identificador o nombre ** ** campo en la búsqueda. Sin embargo, existen las situaciones en las que un filtrado más avanzada () o ordenación es necesario encontrar la fila correcta. En estos casos, el usuario necesita utilizar las opciones de filtro y de ordenación en los encabezados de columnas de la cuadrícula dentro de la búsqueda. Por ejemplo, volvamos a un empleado que especifica una línea de pedido de ventas que deba localizar “cable derecho” como el producto. Escribir “cable” en ** número de artículo ** el control no es útil, ya que no es nombres de producto que empiezan por “cable.” 

![emptyitemlookup](./media/emptyitemlookup.png) 

En su lugar, el usuario necesita borrar el valor de control de la búsqueda, abra el menú desplegable de búsqueda, y filtrar el menú desplegable mediante la cabecera de la columna de la cuadrícula, como se muestra a continuación. Un usuario del mouse (o contacto) puede hacer clic en (o simplemente contacto) cualquier encabezado de columna para obtener acceso a las opciones de filtro y de ordenación para dicha columna. Para un usuario de teclado, el usuario necesita presione simplemente ** Alt **+** abajo ** ** flecha ** una segunda vez de mover el enfoque el menú desplegable, tras la cual el usuario pueden ficha a la columna correcta, y presione ** Ctrl **+** G ** para abrir el menú desplegable del encabezado de la columna de la cuadrícula. 

[gridfilteritemlookup de![] (. /media/gridfilteritemlookup.png])(. /media/gridfilteritemlookup.png) 

Después de que se haya aplicado el filtro (consulte la imagen a continuación), el usuario puede encontrar y seleccione la fila como de costumbre. 

![filtereditemlookup](./media/filtereditemlookup.png)


