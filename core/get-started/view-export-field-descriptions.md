---
title: Ver y exportar descripciones de campos
description: "En este artículo se describe cómo ver las descripciones de campos y cómo utilizar la página Descripciones de campos para exportar las descripciones."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 7898ff427ede4447a5798d4989ffd3088a776d9c
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Ver y exportar descripciones de campos
<a id="view-and-export-field-descriptions" class="xliff"></a>

[!include[banner](../includes/banner.md)]


En este artículo se describe cómo ver las descripciones de campos y cómo utilizar la página Descripciones de campos para exportar las descripciones.

Microsoft Dynamics 365 for Finance and Operations tiene descripciones para algunos de los campos más complejos. Estas descripciones aparecen al colocar el puntero sobre un campo. También puede ver y exportar descripciones en la página **Descripciones de campos**. 

No todas las páginas tienen descripciones de campos. Queremos proporcionar descripciones solo para los campos más complejos y no donde el uso del campo es evidente. Por tanto, algunas páginas no tienen descripciones de campos, otras tienen algunas descripciones y algunas de las páginas más complejas, como muchas de las páginas de parámetros, tienen muchas descripciones. 

Si tiene acceso al entorno de desarrollo de Finance and Operations, puede agregar nuevas descripciones de campo y personalizar las existentes. Por ejemplo, puede agregar información específica de la empresa a una descripción de campo. Para obtener más información, consulte [Personalizar ayuda de campo](/dynamics365/unified-operations/dev-itpro/user-interface/customize-field-help).

## Consulte las descripciones del campo en la interfaz del usuario.
<a id="see-field-descriptions-in-the-user-interface" class="xliff"></a>
Puede ver descripciones de los campos manteniendo el ratón sobre un campo. Si no hay ninguna descripción disponible, verá el nombre del campo al mantener el puntero sobre el campo. (Nota: En Dynamics AX 7.0 (febrero de 2016), las descripciones de los campos se pueden ver únicamente en la página **Descripciones de los campos**) En la ilustración siguiente se muestra la descripción del campo que aparece al pasar el puntero sobre el campo **Bloquear artículos durante el recuento**. 

[![Ejemplo de una descripción de campo](./media/field-description.png)](./media/field-description.png)

## Utilice la página Descripciones de campos para ver y exportar la ayuda de campo.
<a id="use-the-field-descriptions-page-to-view-and-export-field-help" class="xliff"></a>
La página **Descripciones de campos** permite ver y exportar descripciones de campos. Puede ver las descripciones que están disponibles para una página a la vez.

### Vea las descripciones de una página
<a id="view-the-descriptions-for-a-page" class="xliff"></a>

Para ver las descripciones de una página, siga este paso.

-   En el campo **Seleccionar una página**, escriba el nombre de la página. De forma alternativa, haga clic en la flecha para abrir una lista de todas las páginas y, a continuación, examine o filtre la lista.

Puede usar el nombre de la página que se muestra en la interfaz de usuario (IU) (por ejemplo, **Clientes**) o el nombre de código (nombre AOT) que está disponible al hacer clic con el botón secundario en una página (por ejemplo, **CustTable**). 

Para obtener información sobre las diversas maneras de filtrar la lista de páginas, vea la sección "Buscar una página" más adelante en este artículo. 

Si establece la opción **Incluir campos sin descripción** en **Sí**, se muestran todos los campos de la página, incluso si no tienen una descripción de campo.

### Exportar las descripciones de una página
<a id="export-the-descriptions-for-a-page" class="xliff"></a>

Para exportar las descripciones de una página, siga estos pasos.

1.  En el campo **Seleccionar una página**, seleccione una página.
2.  Haga clic en el botón **Abrir de Microsoft Office** que se encuentra en la esquina superior derecha y, a continuación, haga clic en **FieldDescriptionTmp**.

### Buscar una página
<a id="searching-for-a-page" class="xliff"></a>

Hay varias formas de buscar una página en el campo **Seleccionar una página**. En muchos casos deberá hacer clic en la flecha del campo **Seleccionar una página** para abrir la lista desplegable y, a continuación, seleccione entre una lista de páginas.

-   Escriba una parte del nombre y, a continuación, abra la lista desplegable para seleccionar entre una lista de páginas filtrada.
-   Abra la lista desplegable y, a continuación, haga clic en el encabezado **Nombre de página** en la parte superior de la liste o en el encabezado **Nombre AOT de página**. Aparece un cuadro de diálogo, donde puede utilizar las opciones de filtrado avanzadas, como **El nombre de la página empieza por**.
-   Escriba el nombre completo de la página. Al usar esta opción, es mejor abrir la lista desplegable y ver qué más se encuentra en la lista, aunque se muestren las descripciones de campo.
    -   Si hay una única coincidencia exacta del nombre, se muestran las descripciones de campo de esa página.
    -   Si hay más de una coincidencia exacta, no se muestran descripciones. Debe abrir la lista desplegable y seleccionar la página que desea.
    -   Si el nombre que ha escrito forma parte del nombre de otra página, vea las descripciones de la página. Sin embargo, si abre la lista desplegable, consulte las páginas adicionales que contienen ese nombre.

Por ejemplo, no se muestran descripciones al escribir **Recuento** en el campo ****Seleccionar una página***. Abre la lista desplegable y ve que hay dos páginas con el nombre **Recuento**, así como varias páginas que contienen la palabra "Recuento" en el nombre. Si selecciona la página que tiene el nombre AOT **InventJournalCount**, se muestran las descripciones de campo de esa página. Sin embargo, si vuelve a abrir la lista desplegable, verá que, ahora, la lista contiene todas las páginas que tienen "InventJournalCount" como parte de su nombre de AOT.

## Solución de problemas
<a id="troubleshooting" class="xliff"></a>
En esta sección se proporciona información que le ayudará a solucionar los problemas que puedan surgir al utilizar las descripciones de campos.

### No puedo encontrar una descripción de campo
<a id="i-cant-find-a-field-description" class="xliff"></a>

Estamos en proceso de agregar descripciones de campos más complejos. Si necesita ayuda para un campo determinado, háganoslo saber agregando un comentario en este tema.

### La descripción de campo no es útil
<a id="the-field-description-isnt-helpful" class="xliff"></a>

Háganoslo saber agregando un comentario en este tema. Si es posible, describa la información adicional que requiera.

### No encuentro un campo en la página de Descripciones de campos
<a id="i-cant-find-a-field-on-the-field-descriptions-page" class="xliff"></a>

Para mostrar todos los campos de una página, establezca la opción **Incluir campos sin descripción** en **Sí**. Haga clic en el campo **Seleccionar una página** para comprobar que ha seleccionado la página correcta. Si el nombre que ha escrito forma parte de otro nombre de campo, probablemente haya seleccionado la página con el nombre más largo.

### No encuentro una página en la página de Descripciones de campos
<a id="i-cant-find-a-page-on-the-field-descriptions-page" class="xliff"></a>

Para obtener información sobre las diversas maneras de encontrar páginas, vea la sección "Buscar páginas" anteriormente en este artículo. Si ha escrito el nombre exacto de la página, es posible que las descripciones de campo no se muestren si más de una página tiene el mismo nombre. Haga clic en la flecha del campo **Seleccionar una página** para abrir una lista filtrada de las páginas que están disponibles.

Consulte también
<a id="see-also" class="xliff"></a>
--------

[Ayuda para personalizar campo](/dynamics365/unified-operations/dev-itpro/user-interface/customize-field-help)





