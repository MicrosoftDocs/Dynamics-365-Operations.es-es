--- 
title: Crear y procesar una conformidad
description: "Sírvase de este procedimiento para gestionar los casos de disconformidad, en función de un pedido de calidad existente."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 4082caf2cc8393345d4f79a991f2cf205b06b142
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-process-a-conformance"></a>Crear y procesar una conformidad

[!include[task guide banner](../../includes/task-guide-banner.md)]

Sírvase de este procedimiento para gestionar los casos de disconformidad, en función de un pedido de calidad existente. Puede ejecutar esta grabación en la empresa de demostración USMF, y puede utilizar los valores sugeridos. Normalmente, este procedimiento lo realiza un empleado de control de calidad.  Como requisito previo, ejecute la grabación de tarea "Inspección de la calidad de las mercancías". Para procesar la aprobación de un caso de disconformidad, el usuario que ejecuta la grabación de la tarea debe tener un valor "Nombre" asignado en la página Usuarios. Para usar las notas de documento, el usuario también debe tener activada la gestión de documentos en las opciones de usuario. 


## <a name="select-a-quality-order"></a>Selección de un pedido de calidad
1. Vaya a Pedidos de calidad.
2. En la lista, marque la fila seleccionada.
    * Seleccione el pedido de calidad que se creó de la grabación de la tarea "Inspección de la calidad de las mercancías".  

## <a name="create-a-nonconformance"></a>Creación de una disconformidad
1. Haga clic en Consultas.
2. Haga clic en Disconformidades.
3. Haga clic en Nuevo.
4. En el campo Tipo de problema, haga clic en el botón desplegable para abrir la búsqueda.
    * Seleccione el problema que se encontró durante el proceso de inspección.  
5. En el campo Tipo de problema, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Haga clic en Aceptar

## <a name="approvereject-a-nonconformance"></a>Aprobación o rechazo de una disconformidad
1. Haga clic en Funciones.
2. Haga clic en Aprobar disconformidad.
    * Por ejemplo, apruebe la disconformidad. Las disconformidades aprobadas se pueden asociar con operaciones relacionadas para registrar trabajo realizado dentro del proceso de gestión de disconformidades y, como en esta grabación de tarea, el procesamiento de la gestión de correcciones.  
3. Haga clic en Sí.

## <a name="create-a-correction-action"></a>Creación de una acción de corrección
1. Haga clic en Correcciones.
2. Haga clic en Nuevo.
3. En la lista, marque la fila seleccionada.
4. En el campo Número de personal, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en Seleccionar.
7. Haga clic en Vincular.
    * Cree una nota sobre la corrección. En este ejemplo, la acción es contactar con el proveedor para hablar del caso de disconformidad.  
8. Haga clic en Nuevo.
9. Haga clic en Nota.
    * Tenga en cuenta que, en función de la configuración del informe, se pueden imprimir distintos tipos de documentos en los informes relacionados con la gestión de la disconformidad.  
10. En el campo Descripción, escriba un valor.
11. Cierre la página.

## <a name="maintain-a-correction"></a>Mantenimiento de una corrección
1. Haga clic en Marcar como finalizado.
2. Haga clic en Aceptar
3. Cierre la página.

## <a name="close-a-nonconformance"></a>Cierre de una disconformidad
1. Haga clic en Funciones.
2. Haga clic en Cerrar disconformidad.
3. Haga clic en Sí.
4. Cierre la página.
5. Cierre la página.


