--- 
title: "Configuración del id. de IVA"
description: "Este procedimiento recorre los requisitos previos de registro del identificador de IVA, como configuración de un tipo de registro y asignación a la categoría del registro."
author: v-oloski
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: b9db3b66b86f79540145e9da8e2a3dab728b12b8
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-vat-id"></a>Configuración del id. de IVA

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento recorre los requisitos previos de registro del identificador de IVA, como configuración de un tipo de registro y asignación a la categoría del registro. Puede obtener información adicional acerca del identificador de registro y el procesamiento del identificador de registro, incluidas requisitos previos necesarios, en el tema de ayuda Id. de registro. 

Esta información se aplica a todos los países o regiones europeos. La tarea se ha creado con los datos de demostración de la empresa DEMF y con una dirección principal de entidad jurídica en Alemania. Esta tarea está destinada a administradores del sistema. Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.

1. Vaya a Administración de la organización > Libreta de direcciones global > Tipos de registro > Tipos de registro.
2. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
3. En el campo Nombre, escriba "Id. de IVA".
4. En el campo Descripción, número de IVA.
5. En el campo País o región, especifique o seleccione un valor DEU
6. Seleccione Sí en el campo Único.
    * Seleccione esta casilla para comprobar si el Id. de IVA es único.  
7. Seleccione Sí en el campo Principal para país.
    * Seleccione esta casilla si el Id. de IVA debe ser efectivo para todas las direcciones que pertenecen al país/región especificados.  
8. Haga clic en Crear.
9. Haga clic en Agregar.
10. En el campo País o región, especifique o seleccione un valor ITA
11. En el campo Formato, escriba "###########".
    * Cuando se especifica un identificador de registro de este tipo para el país o la región seleccionada, el identificador de registro se comprueba según este formato.  
12. Seleccione la casilla Único.
    * Seleccione esta casilla para comprobar si el Id. de IVA es único.  
13. Seleccione la casilla Principal para país.
    * Seleccione esta casilla si el Id. de IVA debe ser efectivo para todas las direcciones que pertenecen al país/región especificados.  
14. Haga clic en Guardar.
15. Vaya a Administración de la organización > Libreta de direcciones global > Tipos de registro > Categorías de registro.
16. Haga clic en Nuevo.
17. En el campo País o región, especifique o seleccione un valor Id. de IVA, DEU
18. En el campo Categoría de registro, seleccione "Id. de IVA".
    * Asigne el tipo de registro que ha creado anteriormente a una categoría de registro predefinida.  
19. Haga clic en Nuevo.
20. En el campo País o región, especifique o seleccione un valor Id. de IVA, ITA
21. En el campo Categoría de registro, seleccione "Id. de IVA".
    * Asigne el tipo de registro que ha creado a una categoría de registro predefinida.  
22. Haga clic en Guardar.


