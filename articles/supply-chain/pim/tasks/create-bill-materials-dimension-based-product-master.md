---
title: Crear una lista de materiales para un producto maestro basado en dimensiones
description: Para este procedimiento, debe tener completado las 4 guías anteriores de esta secuencia de ocho registros.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13053dd87242963586678b46c64493feb3383c4c
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920714"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Crear una lista de materiales para un producto maestro basado en dimensiones

[!include [banner](../../includes/banner.md)]

Para este procedimiento, debe tener completado las 4 guías anteriores de esta secuencia de ocho registros. Los primeros 4 registros configuraron datos necesarios para completar este procedimiento. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Esta tarea la gestiona normalmente el diseñador de productos.

## <a name="select-the-product"></a>Seleccionar el producto

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. En la lista, marque la fila seleccionada.
    * Busque el producto maestro liberado con la tecnología de configuración basada en dimensiones que ha creado en la primera guía de tareas de esta secuencia.  
1. En el panel de acciones, seleccione **Ingeniero**.
1. Seleccione **Versiones de L. MAT**.

## <a name="create-new-bom-and-bom-version"></a>Crear una L. MAT y una versión de L. MAT nuevas

1. Seleccione **Nuevo**.
1. Seleccione **L. MAT y versión de L. MAT**.
1. En el campo **Nombre**, escriba un valor.
    * Configuración de un sitio  
    * En este procedimiento no establecemos un sitio específico para la L. MAT.  
1. Seleccione **Aceptar**.
1. Seleccione **Nuevo**.
    * En este procedimiento agregaremos cuatro líneas a la L. MAT. Dos líneas representan opciones de cable y dos líneas representan opciones de armario.  
1. En la lista, marque la fila seleccionada.
1. En el campo **Número de artículo**, especifique o seleccione un valor.
    * Seleccione el número de artículo A0001, Cables HDMI de 6.  
1. En el campo **Grupo de configuración**, especifique o seleccione un valor.
    * Seleccione el grupo de configuración de cable creado en la guía 4 de esta secuencia.  
1. Seleccione **Nuevo**.
    * Seleccione el número de artículo A0002, Cables HDMI de 12.  
1. En la lista, marque la fila seleccionada.
1. En el campo **Número de artículo**, especifique o seleccione un valor.
1. En el campo **Grupo de configuración**, especifique o seleccione un valor.
    * Seleccione el grupo de configuración de cable de nuevo.  
1. Seleccione **Nuevo**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Número de artículo**, especifique o seleccione un valor.
    * Seleccione el número de artículo D0002 Armario.  
1. En el campo **Grupo de configuración**, especifique o seleccione un valor.
    * Seleccione el grupo de configuración de armario para esta línea de L. MAT.  
1. Seleccione **Nuevo**.
1. En la lista, marque la fila seleccionada.
1. En el campo **Número de artículo**, especifique o seleccione un valor.
    * Seleccione el número de artículo M0007 Armario estándar como la última línea de L. MAT.  
1. En el campo **Grupo de configuración**, especifique o seleccione un valor.
    * Seleccione el grupo de configuración de armario para la última línea de L. MAT.  

## <a name="approve-and-activate"></a>Aprobar y activar

1. Cierre la página.
1. Seleccione **Aprobar**.
1. En el campo **Aprobado por**, especifique o seleccione un valor.
1. Seleccione *Sí* en **¿Desea aprobar también la lista de materiales?**.
1. Seleccione **Aceptar**.
1. Seleccione **Activar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]