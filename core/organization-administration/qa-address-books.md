---
title: Libretas de direcciones
description: 
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirPartyCheckDuplicate, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23601
ms.assetid: b177fa0f-ac9a-415e-9498-15438e132f60
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 7b3bed2bec4b109c6e3b557b8c3651f15f25169c
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Libretas de direcciones
<a id="address-books" class="xliff"></a>

[!include[banner](../includes/banner.md)]




¿Cómo compruebo los registros duplicados?
<a id="how-do-i-check-for-duplicate-records" class="xliff"></a>
-------------------------------------

Puede comprobar los registros duplicados directamente en la página de lista **Libreta de direcciones global**. En el en el panel de acciones, en la ficha **Parte**, en el grupo **Mantener**, haga clic en **Buscar duplicados**. A continuación, seleccione los valores que incluirá en la comprobación de duplicados.

## ¿Puedo agregar o eliminar registros de manera masiva desde una libreta de direcciones?
<a id="can-i-bulk-add-or-delete-party-records-from-an-address-book" class="xliff"></a>
Sí, puede agregar varios registros de partes a una libreta de direcciones y también quitar varios registros de partes.

-   Para agregar varios registros de partes a una libreta de direcciones, en la página de lista **Libreta de direcciones global**, seleccione las partes en la lista. A continuación, en el panel de acciones, en la ficha **Parte**, en el grupo **Mantener**, haga clic en **Asignar partes**. Seleccione las libretas de direcciones a las que desea agregar los registros de parte seleccionados y, a continuación, haga clic en **Aceptar**. Todos los registros de parte seleccionados se agregan a las libretas de direcciones que ha seleccionado.
-   Para quitar varios registros de partes de una libreta de direcciones, en la página de lista **Libreta de direcciones global**, seleccione las partes en la lista. A continuación, en el panel de acciones, en la ficha **Parte**, en el grupo **Mantener**, haga clic en **Quitar partes**. Seleccione las libretas de direcciones de las que desea quitar las partes y, a continuación, haga clic en **Aceptar**. Todos los registros de parte seleccionados se quitan de las libretas de direcciones que ha seleccionado.

## ¿Puedo cambiar el tipo de parte de un registro o tengo que eliminar el antiguo registro y crear uno nuevo?
<a id="can-i-change-the-party-type-of-a-record-or-do-i-have-to-delete-the-old-record-and-create-a-new-one" class="xliff"></a>
Ocasionalmente, es posible que tenga que el tipo de parte de un registro de persona organización o de organización a persona. Por ejemplo, Nancy forma parte del equipo de ventas para Fabrikam U.K. En una muestra comercial de Londres, conoce a seis nuevos clientes potenciales. Nancy crea un registro de parte de cliente potencial para cada cliente potencial. Cuando Nancy guarda los registros, cada registro también se crea en la libreta de direcciones global. Fabrikam ha establecido el tipo de parte predeterminado en organización, pero dos de los clientes potenciales nuevos deben tener un tipo de registro de persona. Por tanto, cuando Nancy regresa de la muestra comercial, debe cambiar el tipo de parte de los dos registros de clientes potenciales. Para cambiar un registro de parte de un tipo de parte a otro, primero debe crear un nuevo registro de parte del tipo adecuado en la libreta de direcciones global. A continuación, asocie el antiguo registro de parte a este registro nuevo. Una vez que haya realizado la nueva asociación de la parte, elimine el registro de parte original que tiene el tipo de registro incorrecto.

## ¿Cómo cambio el nombre o la dirección de un registro de parte?
<a id="how-do-i-change-the-name-or-address-of-a-party-record" class="xliff"></a>
Puede actualizar el nombre de un registro de parte, y las direcciones que están asociadas a ese registro, en cualquier momento.

-   Para actualizar el nombre de un registro de parte, abra el registro de parte y, a continuación, en el panel de acciones, haga clic en **Editar**. En la ficha desplegable **General**, especifique el nuevo nombre para la parte y luego guarde el registro.
-   Para actualizar una dirección para un registro de parte, abra el registro de parte y, a continuación, en la ficha desplegable **Direcciones**, seleccione la dirección que desea actualizar. Haga clic en **Editar** y, a continuación, en la página **Editar dirección**, realice los cambios necesarios a la dirección o los parámetros de dirección.

## ¿Puedo combinar dos o más registros de parte en un registro?
<a id="can-i-merge-two-or-more-party-records-into-one-record" class="xliff"></a>
Es posible que, en ocasiones, desee combinar dos o varios registros de parte en un único registro. Esto puede suceder si crea uno o varios registros de parte duplicados, ya sea a propósito o por error. Al combinar registros de parte, se selecciona el registro que se desea conservar. La información de los demás registros se combina a continuación con la de este. Por ejemplo, supongamos que descubre que la información acerca de Fabrikam está almacenada en tres registros de parte: A, B y C. Decide conservar el registro de parte A. Por tanto, la información almacenada en los registros de parte B y C se combinará con la del registro de parte A. Hay algunas situaciones en las que no puede combinar registros de partes.

-   No es posible combinar los registros de parte que están asociados con el mismo rol de parte (por ejemplo, un cliente o proveedor) en la misma entidad jurídica. Por ejemplo, la parte A está asociada con un cliente en la entidad jurídica 123 y la parte B está asociada con un cliente distinto en la entidad jurídica 123. Estos registros de parte no se pueden combinar porque el registro de parte combinado quedaría asociado con varios clientes de la misma entidad jurídica, una situación que no está permitida. Sin embargo, los registros se pueden combinar si la parte B está asociada con un proveedor en la entidad jurídica 123 o con un cliente en una entidad jurídica diferente.
-   No es posible combinar registros de parte de tipo organización internos en la misma entidad jurídica, equipo o unidad operativa.

## ¿Debo crear un registro de parte en la libreta de direcciones global o en otro lugar, como la página Cliente o Proveedor?
<a id="should-i-create-a-party-record-in-the-global-address-book-or-in-another-place-such-as-the-customer-or-vendor-page" class="xliff"></a>
Puede especificar registros de partes en la libreta de direcciones global o en la página de entidad correspondiente. Al agregar un registro en una ubicación, el mismo registro se agrega siempre en la otra ubicación. Por ejemplo, si agrega un registro de parte para un cliente en la libreta de direcciones global, el registro también se agrega en la página **Cliente**. Del mismo modo, si agrega un registro de parte para un cliente en la página **Cliente**, el registro también se agrega en la libreta de direcciones global. Use las siguientes directrices para decidir donde debe especificar los nuevos registros de partes:

-   **Creación de un registro de parte cuando no conozca el tipo de entidad**: si debe crear un registro de parte pero no conoce el tipo de entidad (por ejemplo, no se sabe si la entidad es un cliente o una oportunidad), cree el registro en la libreta de direcciones global. Puede seleccionar el tipo de entidad más adelante.
-   **Creación de un registro de parte cuando conozca el tipo de entidad**: si conoce al tipo de entidad de la parte, puede crear un registro en la página aplicable para dicho tipo. Por ejemplo, cree un registro para un cliente en la página **Cliente**. Cuando crea y guarda un registro mediante la página de entidad correspondiente, el registro se crea automáticamente en la libreta de direcciones global.

## ¿Puedo traducir información de dirección para los registros de partes?
<a id="can-i-translate-address-information-for-party-records" class="xliff"></a>
Puede configurar traducciones de la información de dirección de modo que la información aparezca en el idioma del usuario (idioma del sistema) en Microsoft Dynamics 365 for Finance and Operations pero en otro idioma en documentos como los pedidos de ventas. Puede especificar las traducciones para los nombres de país o región, los propósitos de direcciones y las secuencias de nombres. Por ejemplo, su idioma del sistema es el danés y crea un pedido de ventas para un cliente en Francia. En este caso, puede ver el registro del cliente en danés en el programa pero visualizar la información de dirección en francés en el pedido de ventas impreso. Al configurar traducciones, debe especificar una traducción para cada elemento de la lista. Los artículos para los que no especifique una traducción aparecerán en el idioma del sistema. Por ejemplo, su idioma del sistema es el danés y envía un documento a un cliente en España. Si no ha especificado las traducciones de español (ESP) para la información de dirección, esa información aparecerá en danés tanto en el programa como en el documento impreso.




