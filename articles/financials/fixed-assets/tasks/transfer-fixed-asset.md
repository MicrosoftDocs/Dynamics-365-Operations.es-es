--- 
title: Transferir un activo fijo
description: "Esta guía de tareas transferirá la Información financiera de un libro de activo fijo desde un conjunto de dimensiones financieras a un nuevo conjunto de dimensiones financieras."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b193cf6fbed810f0d5234514573d0f5c23c7b2c8
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="transfer-a-fixed-asset"></a>Transferir un activo fijo

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta guía de tareas transferirá la Información financiera de un libro de activo fijo desde un conjunto de dimensiones financieras a un nuevo conjunto de dimensiones financieras.  Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.

1. Vaya a Activos fijos > Activos fijos > Activos fijos.
2. En la lista, busque y seleccione el activo fijo para transferir.
3. En el panel de acciones, haga clic en Activo fijo.
4. Haga clic en Transferir activos fijos.
5. En el campo Fecha de transferencia, especifique una fecha.
6. Escriba comentarios para describir la transferencia.
    * Esta lista muestra todos los libros para el activo fijo.  
7. Marque los libros que desea transferir a un nuevo conjunto de dimensiones financieras.
    * Esta lista muestra los valores de dimensión financiera existentes para el libro seleccionado.  
    * seleccione la dimensión financiera que desee actualizar para el libro de activo fijo seleccionado.  
8. En el campo Dimensión financiera, haga clic en el botón desplegable para abrir la búsqueda.
    * Defina otros valores de la dimensión financiera si procede.  
    * Todos los valores de la dimensión financiera cambiarán cuando se produzca una transferencia, tanto si se ha especificado un valor como si se ha dejado en blanco. Por ejemplo, si se ha especificado un valor para BusinessUnit y se han dejado en blanco las dimensiones financieras CostCenter y Departamento. Si la estructura de cuentas permite valores en blanco para CostCenter y Departamento, la transferencia haría que cada modelo de valor tenga el nuevo valor para BusinessUnit y un valor en blanco para CostCenter y Departamento.  
9. Haga clic en Actualizar.
    * Tiene la oportunidad de ver los cambios de requisito previo antes de finalizar la transferencia.  
    * Revise los resultados antes de transferir los libros de activo fijo.  
10. Haga clic en Transferir.


