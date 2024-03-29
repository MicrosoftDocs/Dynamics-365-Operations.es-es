---
title: Transferir un activo fijo
description: Esta guía de tareas transferirá la Información financiera de un libro de activo fijo desde un conjunto de dimensiones financieras a un nuevo conjunto de dimensiones financieras.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c8428467d6e12b6d6af9023980b8cf8738d9294
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727016"
---
# <a name="transfer-a-fixed-asset"></a>Transferir un activo fijo

[!include [banner](../../includes/banner.md)]

Esta guía de tareas transferirá la Información financiera de un libro de activo fijo desde un conjunto de dimensiones financieras a un nuevo conjunto de dimensiones financieras.  

1. En el panel de navegación, vaya a **Módulos > activos fijos > activos fijos > activos fijos**.
2. En la lista, busque y seleccione el activo fijo para transferir.
3. En el panel de acciones, haga clic en **Activo fijo.**
4. Haga clic en **Transferir activos fijos**.
5. En el campo **Fecha de transferencia**, especifique una fecha.
6. Escriba comentarios para describir la transferencia.
    
    Esta lista muestra todos los libros para el activo fijo.  
7. Marque los libros que desea transferir a un nuevo conjunto de dimensiones financieras.
    * Esta lista muestra los valores de dimensión financiera existentes para el libro seleccionado.  
    * seleccione la dimensión financiera que desee actualizar para el libro de activo fijo seleccionado.  
8. En el campo **Dimensión financiera**, haga clic en el botón desplegable para abrir la búsqueda.
    * Defina otros valores de la dimensión financiera si procede.  
    * Todos los valores de la dimensión financiera cambiarán cuando se produzca una transferencia, tanto si se ha especificado un valor como si se ha dejado en blanco. Por ejemplo, si se ha especificado un valor para BusinessUnit y se han dejado en blanco las dimensiones financieras CostCenter y Departamento. Si la estructura de cuentas permite valores en blanco para CostCenter y Departamento, la transferencia haría que cada modelo de valor tenga el nuevo valor para BusinessUnit y un valor en blanco para CostCenter y Departamento.  
9. Haga clic en **Actualizar**.
    * Tiene la oportunidad de ver los cambios de requisito previo antes de finalizar la transferencia.  
    * Revise los resultados antes de transferir los libros de activo fijo.  
10. Haga clic en **Transferir**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
