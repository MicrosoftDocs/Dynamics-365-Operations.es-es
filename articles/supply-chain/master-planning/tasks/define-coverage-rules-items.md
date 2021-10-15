---
title: Definir reglas de cobertura para los artículos
description: Este procedimiento muestra cómo crear reglas de cobertura y anular opciones de cobertura para un artículo específico. También se muestra cómo especificar parámetros de inventario predeterminados.
author: ChristianRytt
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15b0ad9faf2bcac25dec01a7ab44f804ad2345cd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567232"
---
# <a name="define-coverage-rules-for-items"></a>Definir reglas de cobertura para los artículos

[!include [banner](../../includes/banner.md)]

La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento muestra cómo crear reglas de cobertura y anular opciones de cobertura para un artículo específico. También se muestra cómo especificar parámetros de inventario predeterminados.

## <a name="create-a-coverage-group"></a>Crear un grupo de cobertura

Cree un grupo de cobertura haciendo lo siguiente:

1. Vaya al **Panel de exploración > Módulos > Planificación maestra > Configuración > Grupos de cobertura**.
1. Seleccione **Nuevo**.
1. En el campo **Grupo de cobertura**, escriba un valor.
1. En el campo **Nombre**, escriba un valor.
1. En el campo **Calendario**, escriba un valor. Elija el calendario que utiliza la planificación maestra para crear sugerencias de reabastecimiento para los artículos en el grupo.  
1. En el campo **Código de cobertura**, seleccione una opción. Seleccione "Requisito" para este procedimiento.  
1. En el campo **Límite de tiempo de cobertura (días)**, escriba "90". Para los artículos de este grupo, la planificación maestra creará las sugerencias de reabastecimiento de hasta 90 días en el futuro.  
1. En el campo **Días negativos**, especifique '1'.
1. En el campo **Días positivos**, especifique "1".
1. Expanda o contraiga la sección **Otros**.
1. En la sección **Márgenes de seguridad en días**, en el campo **Días de recepción sumados a la fecha de requisito**, especifique "1". Por ejemplo, si el margen de recepción se establece en 1 día y se programa la recepción de una línea de pedido de compra para el 15 de mayo, la planificación maestra calcula la fecha de recepción ajustada como el 16 de mayo.
1. En el campo **Días de emisión deducidos de la fecha de requisito**, especifique "1". Por ejemplo, si el margen de seguridad se establece en 1 día y se programa la entrega de una línea del pedido de ventas para el 15 de mayo, la programación maestra calcula la fecha de entrega ajustada como el 14 de mayo.  
1. En el campo **Días de administración agregados al plazo del artículo**, especifique "1".
1. Seleccione **Guardar**.

## <a name="create-a-new-product"></a>Crear un nuevo producto

Cree un producto nuevo haciendo lo siguiente:

1. Vaya a **Panel de navegación > Módulos > Gestión de información de productos > Productos > Productos despachados**.
1. Seleccione **Nuevo**.
1. En el campo **Número de producto**, escriba un valor.
1. En el campo **Nombre de producto**, escriba un valor.
1. En el campo **Grupo de modelos de artículo**, seleccione el botón de la lista desplegable para abrir la búsqueda.
1. En la lista, busque y seleccione el registro deseado.
1. En la lista, seleccione el vínculo de la fila seleccionada.
1. En el campo **Grupo de artículos**, seleccione el botón de la lista desplegable para abrir la búsqueda.
1. En la lista, busque y seleccione el registro deseado.
1. En la lista, seleccione el vínculo de la fila seleccionada.
1. En el campo **Grupo de dimensiones de almacenamiento**, haga clic en el botón de la lista desplegable para abrir la búsqueda.
1. En la lista, busque y seleccione el registro deseado.
1. En la lista, seleccione el vínculo de la fila seleccionada.
1. En el campo **Grupo de dimensiones de seguimiento**, seleccione en el botón de la lista desplegable para abrir la búsqueda.
1. En la lista, busque y seleccione el registro deseado.
1. En la lista, seleccione el vínculo de la fila seleccionada.
1. Seleccione **Aceptar**.

## <a name="set-up-default-order-settings"></a>Configuración de ajustes predeterminados de pedido

Configure las opciones de pedido predeterminadas haciendo lo siguiente:

1. En el **Panel de acciones**, seleccione **Plan**.
1. En **Configuración de pedido**, seleccione **Configuración predeterminada de pedido**.
1. En **Pedido de compra**, en el campo **Sitio predeterminado**. escriba el sitio usado como predeterminado cuando se crean los pedidos de compra.
1. En el campo **Almacén predeterminado**, escriba el sitio donde está almacenado el artículo.
1. Expanda o contraiga la sección **Inventario**.
1. En el campo **Varios**, escriba "10".
1. En el campo **Cantidad mínima de pedido**, escriba "10".
1. En el campo **Cantidad máxima de pedido**, escriba "100".
1. En el campo **Cantidad de pedido estándar**, escriba "10".
1. En el campo **Plazo de compra**, especifique un número.
1. Active o desactive la casilla **Días laborales**.
1. Seleccione **Guardar**.
1. En el campo **Tipo de pedido predeterminado**, seleccione "Pedido de compra".
1. Seleccione **Guardar**.
1. Cierre la página. Cierre la página Configuración predeterminada de pedido.  

## <a name="add-an-item-to-a-coverage-group"></a>Agregar un artículo a un grupo de cobertura

Agregue un artículo a un grupo de cobertura haciendo lo siguiente:

1. Expanda o contraiga la sección **Plan**.
1. En el campo **Grupo de cobertura**, seleccione el botón desplegable para abrir la búsqueda.
1. En la lista, busque el **Grupo de cobertura** que ha creado.
1. En la lista, seleccione el vínculo de la fila seleccionada.

## <a name="create-item-coverage-rules"></a>Crear reglas de cobertura de artículos

Cree reglas de artículo de cobertura haciendo lo siguiente:

1. En el **Panel de acciones**, seleccione **Plan**.
1. En **Cobertura**, seleccione **Cobertura de artículos**.
1. Seleccione **Nuevo**.
1. Seleccione la ficha **General**.
1. Active la casilla en el encabezado de **Anular configuración de grupo de cobertura**.
1. En el campo **Límite de tiempo de cobertura (días)**, escriba "60". Aunque los artículos del grupo de cobertura Requisito se planifiquen con 90 días de adelanto, este artículo se planea con 60 días de adelanto.  
1. En el campo **Días negativos**, especifique "2".
1. En el campo **Días positivos**, especifique "2".
1. Seleccione la pestaña **Plazo**.
1. Active la casilla en el encabezado de **Compra**.
1. En el campo **Hora de compra**, especifique "5".
1. Seleccione **Guardar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]