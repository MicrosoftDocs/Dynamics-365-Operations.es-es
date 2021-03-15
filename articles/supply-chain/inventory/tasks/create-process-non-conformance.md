---
title: Crear y procesar una conformidad
description: Este tema explica cómo gestionar los casos de disconformidad, en función de un pedido de calidad existente.
author: perlynne
manager: tfehr
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4525e79cb388cc9bbcfe1d038a53cf53916a678c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008107"
---
# <a name="create-and-process-a-conformance"></a>Crear y procesar una conformidad

[!include [banner](../../includes/banner.md)]

Este tema explica cómo gestionar los casos de disconformidad, en función de un pedido de calidad existente. Puede ejecutar esta grabación en la empresa de demostración USMF, y puede utilizar los valores sugeridos. Normalmente, este procedimiento lo realiza un empleado de control de calidad.  Como requisito previo, complete las instrucciones en [Inspección de la calidad de las mercancías](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md). Para procesar la aprobación de un caso de disconformidad, el usuario que ejecuta la grabación de la tarea debe tener un valor "Nombre" asignado en la página Usuarios. Para usar las notas de documento, el usuario también debe tener activada la gestión de documentos en las opciones de usuario.


## <a name="select-a-quality-order"></a>Selección de un pedido de calidad
1. En el panel de navegación, vaya a **Módulos > Gestión de inventario > Tareas periódicas > Administración de calidad > Pedidos de calidad**.
2. En la lista, seleccione el pedido de calidad que se creó en [Inspección de la calidad de las mercancías](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).  

## <a name="create-a-nonconformance"></a>Creación de una disconformidad
1. En el panel Acciones, seleccione **Consultas**.
2. Seleccione **No conformidades**.
3. Seleccione **Nuevo**.
4. En el menú desplegable del campo **Tipo de problema**, seleccione el problema encontrado durante el proceso de inspección.  
5. Seleccione **Aceptar**.

## <a name="approvereject-a-nonconformance"></a>Aprobación o rechazo de una disconformidad
1. Seleccione **Funciones**.
2. Seleccione **Aprobar la no conformidad**. Por ejemplo, apruebe la disconformidad. Las disconformidades aprobadas se pueden asociar con operaciones relacionadas para registrar trabajo realizado dentro del proceso de gestión de disconformidades y, como en este tema, el procesamiento de la gestión de correcciones.  
3. Seleccione **Sí**.

## <a name="create-a-correction-action"></a>Creación de una acción de corrección
1. Seleccione **Correcciones**.
2. Seleccione **Nuevo**.
3. En el campo **Número de personal** de la nueva fila, seleccione el registro deseado desde el menú desplegable.
4. Haga clic en **Seleccionar**.
5. Seleccione **Adjuntar**. Cree una nota sobre la corrección. En este ejemplo, la acción es contactar con el proveedor para hablar del caso de disconformidad.  
6. Seleccione **Nuevo**.
7. Seleccione **Nota**. En función de la configuración del informe, se pueden imprimir distintos tipos de documentos en los informes relacionados con la gestión de la disconformidad.  
8. En el campo **Descripción**, escriba un valor.
9. Cierre la página.

## <a name="maintain-a-correction"></a>Mantenimiento de una corrección
1. Seleccione **Marcar como finalizado**.
2. Seleccione **Aceptar**.
3. Cierre la página.

## <a name="close-a-nonconformance"></a>Cierre de una disconformidad
1. Seleccione **Funciones**.
2. Seleccione **Cerrar la no conformidad**.
3. Seleccione **Sí**.
4. Cierre las páginas.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]