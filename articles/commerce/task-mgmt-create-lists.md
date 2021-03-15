---
title: Crear listas de tareas y agregar tareas
description: Este tema describe cómo crear listas de tareas y agregarlas tareas en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cca5e0efd6516d02c372e8a616b6bb0c39f3088c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006219"
---
# <a name="create-task-lists-and-add-tasks"></a>Crear listas de tareas y agregar tareas

[!include [banner](includes/banner.md)]

Este tema describe cómo crear listas de tareas y agregarlas tareas en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Una *tarea* define un trabajo específico o una acción que alguien debe completar en o antes de una fecha de vencimiento especificada. En Dynamics 365 Commerce, una tarea puede incluir instrucciones detalladas e información sobre una persona de contacto. También puede incluir enlaces a operaciones de back-office, operaciones de punto de venta (PDV) o páginas del sitio, para ayudar a mejorar la productividad y proporcionar el contexto que el propietario de la tarea requiere para completar la tarea de manera eficiente.

Una *lista de tareas* es una colección de tareas que deben completarse como parte de un proceso empresarial. Por ejemplo, puede haber una lista de tareas que un nuevo trabajador debe completar durante la incorporación, una lista de tareas para los cajeros que trabajan en turnos nocturnos o una lista de tareas que debe completarse para preparar la tienda para una próxima temporada de vacaciones. En Commerce, cada lista de tareas que tiene una fecha objetivo se puede asignar a cualquier número de tiendas o empleados y se puede configurar para que se repita.

Tanto los gerentes como los trabajadores pueden crear listas de tareas en la oficina administrativa de Commerce y luego asignarlas a un conjunto de tiendas.

## <a name="create-a-task-list"></a>Crear una lista de tareas

Para crear una lista de tareas, siga estos pasos.

1. Vaya a **Retail y Commerce \> Administración de tareas \> Administración de tareas**.
1. Seleccione **Nueva** y luego introduzca valores en los campos **Nombre**, **Descripción** y **Propietario**.
1. Seleccione **Guardar**.

## <a name="add-tasks-to-a-task-list"></a>Agregar tareas a una lista de tareas

Para agregar tareas a una lista de tareas, siga estos pasos.
 
1. En la ficha desplegable **Tareas** de una lista de tareas existente, seleccione **Nueva** para agregar una tarea.
1. En el cuadro de diálogo **Crear una tarea nueva**, en el campo **Nombre** introduzca un nombre para la tarea.
1. En el campo **Datos debidos compensados desde la fecha objetivo**, introduzca un valor entero positivo o negativo. Por ejemplo, introduzca **-2** si la tarea debe completarse dos días antes de la fecha de vencimiento de la lista de tareas.
1. En el campo **Notas**, introduzca instrucciones detalladas.
1. En el campo **Persona de contacto** introduzca el nombre de un experto en la materia que el propietario de la tarea puede contactar si necesita ayuda.
1. En el campo **Enlace de tarea**, introduzca un enlace, basado en la naturaleza de la tarea.

> [!TIP]
> Aunque puedes usar el campo **Asignado a** para asignar tareas a alguien mientras está creando una lista de tareas, le recomendamos que evite asignar tareas durante la creación de la lista de tareas. En su lugar, asigne las tareas después de que la lista se instancie para tiendas individuales.

## <a name="use-task-links-to-help-improve-worker-productivity"></a>Use enlaces de tareas para ayudar a mejorar la productividad de los trabajadores

Commerce le permite vincular tareas a operaciones PDV específicas, como ejecutar un informe de ventas, ver un video de capacitación en línea para orientación de nuevos empleados o realizar una operación de back-office. Esta característica ayuda a los propietarios de tareas a obtener la información que necesitan para completar una tarea de manera eficiente.

Para agregar enlaces de tareas mientras crea una tarea, siga estos pasos.

1. En la ficha desplegable **Tareas** de una lista de tareas existente, seleccione **Editar**.
1. En el cuadro de diálogo **Editar tarea**, en el campo **Enlace de tarea**, seleccione una o más de las siguientes opciones:

    - Seleccione **Opción del menú** para configurar una operación de back-office, como "Kits de productos".
    - Seleccione **Operación PDV** para configurar una operación PDV, como "Informes de ventas".
    - Seleccione **URL** para configurar una URL absoluta.

La siguiente ilustración muestra la selección de enlaces de tareas en el cuadro de diálogo **Editar tarea**.

![Seleccionar enlaces de tareas en el cuadro de diálogo Editar tarea](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a>Configure una operación PDV para que pueda vincularse a una tarea

Para configurar una operación PDV para que pueda vincularse a una tarea, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> PDV \> Operaciones PDV**.
1. Seleccione **Editar**, encuentre la operación PDV y después seleccione la casilla **Habilitar administración de tareas**.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la administración de tareas](task-mgmt-overview.md)

[Configurar la administración de tareas](task-mgmt-configure.md)

[Asignar listas de tareas a tiendas o empleados](task-mgmt-assign-lists.md)

[Administración de tareas en PDV](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]