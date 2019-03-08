---
title: Creación del canal en línea y definición de los atributos del canal
description: Este procedimiento le guía por la creación de un nuevo canal en línea y su adición a la jerarquía organizativa.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e066e9901a97bd5b72815a7af472247ef519ecb9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "312379"
---
# <a name="create-online-channel-and-define-channel-attributes"></a>Creación del canal en línea y definición de los atributos del canal

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimiento le guía por la creación de un nuevo canal en línea y su adición a la jerarquía organizativa. Debe crear la jerarquía organizativa para poder crear un nuevo canal en línea. Este procedimiento usa la empresa de datos de demostración USRT.


## <a name="create-a-new-online-channel"></a>Crear un nuevo canal en línea
1. Vaya a Venta minorista y comercio > Canales > Tiendas en línea.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. En el campo Almacén, especifique o seleccione un valor.
5. En el campo Zona horaria de la tienda, seleccione una opción.
6. En el campo Cliente predeterminado, especifique o seleccione un valor.
7. En el campo Libreta de direcciones de cliente, especifique o seleccione un valor.
8. En el campo Condiciones de pago, especifique o seleccione un valor.
9. En el campo Método de pago, especifique o seleccione un valor.
10. En el campo Perfil de notificación por correo electrónico, especifique o seleccione un valor.
11. Expanda la sección Dimensiones financieras.
12. En el campo BusinessUnit, especifique o seleccione un valor.
    * Defina de forma similar el valor para las demás dimensiones predeterminadas.  
13. Haga clic en Guardar.

## <a name="add-the-online-channel-to-organization-hierarchy"></a>Agregar el canal en línea a la jerarquía organizativa
1. Cierre la página.
2. Vaya a Administración de la organización > Organizaciones > Jerarquías organizativas.
3. En la lista, busque y seleccione el registro deseado.
4. Haga clic en Ver.
5. Haga clic en Editar.
    * Puede seleccionar cualquier nodo de jerarquía bajo el que desea insertar el nuevo canal.  
6. Haga clic en Insertar.
7. Haga clic en Canal comercial.
8. Haga clic en Aceptar
9. Haga clic en Publicar para abrir el cuadro de diálogo desplegable.
10. En el campo Fecha de vigencia, especifique una fecha y una hora.
11. Haga clic en Publicar.

