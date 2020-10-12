---
title: Configuración de proyecto de orden de trabajo
description: En este tema se explica la configuración de proyectos de órdenes de trabajo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjectSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a51837275203dc2d4f31dc4dec9bf970a7ebeba7
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889323"
---
# <a name="work-order-project-setup"></a>Configuración de proyecto de orden de trabajo

[!include [banner](../../includes/banner.md)]

 

En el módulo **Administración de activos**, se requiere una relación de proyecto para cada trabajo de la orden de trabajo. El proyecto que está asociado a un trabajo de la orden de trabajo permite realizar un seguimiento de los costes de distintos proyectos relacionados con la gestión de activos, como proyectos internos de mantenimiento, proyectos de gestión de servicios, y proyectos de inversión. 

## <a name="project-setup-for-a-work-order-job"></a>Configuración de proyecto de un trabajo de una orden de trabajo

Al crear un trabajo de pedido de trabajo en un pedido de trabajo, la configuración del proyecto en el módulo **Gestión de proyectos y contabilidad** y la configuración de proyecto de la orden de trabajo en el módulo **Administración de activos** determinan cómo los proyectos pueden usarse para el control de costes del activo seleccionado en ese trabajo de la orden de trabajo. Esta sección describe las siguientes partes de la configuración de proyecto que se usa para un pedido de trabajo: el proyecto principal (Id de proyecto), tipo de proyecto, actividades de proyecto, y dimensiones financieras:

- Al crear un trabajo de órdenes de trabajo en un pedido de trabajo, un identificador único del proyecto y una actividad de proyecto relacionada se crean automáticamente para abrirlo. Sin embargo, si varios trabajos de un pedido de trabajo incluyen el mismo activo, el mismo identificador del proyecto se usa para ellos. Dicho de otra forma, un identificador de proyecto se crea para cada activo de un pedido de trabajo.

    - El proyecto principal (identificador del proyecto) para un trabajo de la orden de trabajo se encuentra en la configuración del proyecto principal. (Para obtener más información sobre la configuración del proyecto principal, consulte la sección siguiente.) Por ejemplo, si se asocia un cliente o una ubicación funcional con un proyecto principal específico, el proyecto principal se usará cada vez que cree las órdenes de trabajo para ese cliente esa ubicación funcional. Si no relaciona un identificador de proyecto específico con, por ejemplo, una ubicación funcional, se usará el siguiente proyecto principal pertinente en la configuración de proyecto de la orden de trabajo.
    - Es obligatorio un tipo de proyecto para cada identificador de proyecto. El tipo de proyecto se encuentra en la configuración de la configuración del grupo de proyectos. (Para obtener más información acerca de la configuración del grupo de proyectos, consulte la sección siguiente.) Si no se encuentra ninguna coincidencia en la configuración del grupo de proyectos, se usará la configuración del grupo de proyectos del proyecto principal.
    - La configuración para requerir actividades de proyecto en previsiones y diarios se copia del proyecto principal en el proyecto de la orden de trabajo. Si las opciones **Hora**, **gasto** y **Artículo** se establecen en **Sí** para el proyecto que se usa como proyecto principal, una actividad de proyecto es obligatoria en previsiones y diarios. (Para obtener acceso a estas opciones, seleccione **Gestión de proyectos y contabilidad** \> **Proyectos** \> **Todos los proyectos**, y seleccione el proyecto que se usa como proyecto principal. Las opciones se encuentran en la sección **Requerir actividad en los diarios** en la ficha desplegable **Configuración**).

- Las dimensiones financieras se copian del activo y se combinan con el proyecto principal.

La siguiente sección explica cómo configurar proyectos principales y grupos de proyectos. El proyecto principal y los grupos principales se usan para controlar órdenes de trabajo. También se utilizan para informar sobre las órdenes de trabajo.

## <a name="set-up-work-order-projects"></a>Configuración de proyectos de orden de trabajo

Antes de comenzar a crear órdenes de trabajo, debe configurar proyectos de órdenes de trabajo. La página **Configuración de proyecto de orden de trabajo** (**Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Configuración de proyecto**) contiene dos fichas: **Proyecto principal** y **Grupo de proyectos**.

En la pestaña **Proyecto principal**, puede las relaciones de proyectos que se pueden usar si no se ha configurado ningún proyecto en el activo seleccionado en el trabajo de la orden de trabajo. Una configuración del proyecto principal no es necesaria si su empresa utiliza proyectos de activo. Es relevante solo si desea usar proyectos de órdenes de trabajo en lugar de proyectos de activos. En ese caso, debe configurar al menos un proyecto principal.

En la pestaña **Grupo de proyectos**, puede configurar los grupos de proyectos que se pueden asociar a los tipos de pedido de trabajo, tipos de activos, y activos.

Los grupos de proyectos se pueden usar para crear categorías específicas (grupos) que se usan para el control de costes. Por ejemplo, crear grupos de proyectos para tipos de activos específicos o tipos de órdenes de trabajo, le permite hacer el seguimiento detallado de los costes de mantenimiento por tipo.

Los grupos de proyectos no son obligatorios. Si no configura grupos de proyectos, se utilizará el proyecto principal para determinar el grupo de proyectos, y un proyecto secundario se crea a partir del grupo de proyectos del proyecto principal.

La configuración permite una integración completa con el módulo **Gestión de proyectos y contabilidad**. Por lo tanto, puede realizar un seguimiento de los costes relacionados con las órdenes de trabajo de los proyectos relacionados. El siguiente procedimiento describe la configuración de los proyectos de órdenes de trabajo.

1. Seleccione **Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Configuración del proyecto**.
2. En la pestaña **Proyecto principal** haga clic en **Agregar**.
3. En los campos **Tipo de orden de trabajo**, **Ubicación funcional**, **Tipo de activo**, y **Activo**, seleccione los valores según sea necesario. Para cada línea que desee agregar, puede establecer sólo un campo o varios campos. El número de campos que establezca determina la combinación que se usa cuando un identificador de proyecto se selecciona en administración de activos. 

    Si selecciona una ubicación funcional, las ubicaciones secundarias relacionadas son automáticamente incluidas. Si selecciona un activo, puede crear más líneas de configuración del proyecto de la orden de trabajo para el mismo activo, pero puede seleccionar diferentes proyectos para dicho activo.

4. En el campo **Identificador del proyecto**, seleccione el proyecto que debe estar relacionado con la configuración que ha creado en el paso 3.
5. Si la configuración del proyecto debe ser válida únicamente por un período limitado, seleccione una fecha final en el campo **Fecha de finalización**. De lo contrario, seleccione **Ninguno**.

    De forma predeterminada, la fecha inicial es la fecha en que agrega el proyecto de pedido de trabajo a la página. Se controla mediante el campo **Válido desde**, que está oculto de forma predeterminada. Para mostrar el campo **Válido desde**, seleccione **Ver** \> **Todos**. Luego puede utilizar el campo **Válido desde** junto con el campo **Fecha de finalización** para configurar un período de validez limitado para el proyecto de la orden de trabajo.

    ![Página Configuración de proyecto de orden de trabajo](media/17-setup-for-work-orders.png)

6. En la pestaña **Grupo de proyectos** haga clic en **Agregar**.
7. En el campo **Tipo de orden de trabajo**, seleccione un tipo de orden de trabajo.
8. Si desea que la asociación del grupo de proyectos sea más específica, seleccione un tipo de activo en el campo **Tipo de activo** o un activo en el campo **Activo**.
9. En el campo **Grupo de proyectos**, seleccione el grupo de proyectos que debe estar relacionado con el tipo de pedido del trabajo. Por ejemplo, un tipo de pedido de trabajo que se llama **Mantenimiento preventivo** puede estar asociado a un grupo de proyectos que se denomina **Mant ant** o **Interno**. Como alternativa, un tipo de pedido del trabajo **Inversión** que se usa para órdenes de trabajo relacionados con inversiones y activos fijos puede estar asociado un grupo de proyectos que se denomina **Invertir** o **Inversión**.
10. Seleccione **Guardar**.

![Página Configuración de proyecto de orden de trabajo, Agregar pedido de trabajo](media/18-setup-for-work-orders.png)

> [!NOTE]
> Cada vez que se crea una línea de pedido de trabajo, la administración de activos busca un grupo de proyectos que debe estar relacionado con el proyecto de trabajo de la orden de trabajo. La búsqueda se basa en la configuración que se describe en este tema. Cada grupo de proyectos tiene un tipo de proyecto relacionado. Los grupos de proyectos que tienen el tipo de proyecto **Tiempo y material** o **precio fijo** solo serán válidos para los activos relacionados con una cuenta de cliente.
>
> Para los proyectos principales y los grupos de proyectos, cuando el sistema selecciona el proyecto o el grupo de proyectos disponibles de la orden de trabajo, la selección se basa en los registros que ha creado mediante el procedimiento anterior. La administración de activos revisa los registros relacionados con el proyecto de la orden de trabajo para comprobar si hay una posible coincidencia. Comprueba siempre primero la combinación más específica. Es decir, para el proyecto principal de orden de trabajo, la administración de activos primero busca una posible coincidencia para el campo **Activo**. Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Tipo de activo**. Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Ubicación técnica**, y así sucesivamente. Como puede ver en el diseño de la página **Configuración de proyecto de orden de trabajo**, este comportamiento significa que, para encontrar la combinación más específica, Administración de activos comprueba cada registro de derecha a izquierda en busca de una coincidencia. Si no se encuentra ninguna coincidencia, se utiliza el registro predeterminado donde sólo se selecciona un identificador de proyecto. El proceso para encontrar el grupo de proyectos relacionados es similar. Administración de activos primero comprueba si hay una posible coincidencia para el campo **Activo**, luego el campo **Tipo de activo** y, a continuación, el campo **Tipo de orden de trabajo**. Si no se encuentra ninguna coincidencia, se utiliza el registro predeterminado donde sólo se selecciona un grupo de proyectos.
