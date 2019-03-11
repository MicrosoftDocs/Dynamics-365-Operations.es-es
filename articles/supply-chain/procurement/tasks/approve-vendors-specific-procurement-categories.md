---
title: Aprobar proveedores para categorías de compras específicas
description: Cuando se crea una solicitud de compra, puede haber un requisito para seleccionar un proveedor aprobado o preferido, en función de cómo se configuran las directivas de compras.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b783d1ce8f02ad119dc6768e6d9cd3c61ae07e70
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "308400"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Aprobar proveedores para categorías de compras específicas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cuando se crea una solicitud de compra, puede haber un requisito para seleccionar un proveedor aprobado o preferido, en función de cómo se configuran las directivas de compras. Este procedimiento le muestra cómo especificar que un proveedor está aprobado o preferido para una categoría de compras específica. Esta tarea la lleva a cabo normalmente un profesional de compras. Puede utilizar este procedimiento en la empresa de datos de demostración USMF.

1. Vaya a Adquisición y abastecimiento > Proveedores > Todos los proveedores.
2. Seleccione el proveedor que desea establecer como proveedor aprobado o preferido para una categoría.
3. En el panel de acciones, haga clic en General.
4. Haga clic Categorías.
5. Haga clic en Agregar categoría.
6. En el campo Categoría, seleccione OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES).
7. En el campo Estado de categoría del proveedor, seleccione "Preferido".
    * Es posible especificar más de un proveedor preferido para una categoría.  
8. Haga clic en Guardar.
9. Vaya a Adquisición y abastecimiento > Categorías de compras.
10. En el árbol, seleccione "CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES".
11. Expanda la sección Proveedores.
    * Compruebe si el proveedor que ha seleccionado aparece como proveedor preferido para la categoría de accesorios de la oficina y escritorio. Si está ejecutando este procedimiento como guía de tareas, es posible que tenga que hacer clic en el botón Desbloquear para poder desplazarse hacia abajo en la lista de proveedores.  También es posible agregar proveedores preferidos y aprobados en esta página.  
12. En el árbol, expanda "OFFICE AND DESK ACCESSORIES".
13. En el árbol, seleccione "Tijeras".
14. Seleccione No en el campo Heredar proveedores de la categoría principal:.
15. Seleccione Sí en el campo Heredar proveedores de la categoría principal:.

