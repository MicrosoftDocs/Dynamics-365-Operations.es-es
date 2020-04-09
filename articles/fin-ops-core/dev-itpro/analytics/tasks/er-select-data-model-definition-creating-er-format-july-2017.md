---
title: Seleccionar definiciones de modelo de datos al crear formatos
description: 'Para completar los pasos de este procedimiento, primero debe completar los pasos del procedimiento, ER: Creación y activación de un proveedor de configuraciones.'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 374c31b5ea9160fba773e82f658e8de05c67cab4
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143255"
---
# <a name="select-data-model-definitions-when-you-create-formats"></a>Seleccionar definiciones de modelo de datos al crear formatos

[!include [banner](../../includes/banner.md)]

Para completar los pasos de este procedimiento, primero debe completar los pasos del procedimiento, ER: Creación y activación de un proveedor de configuraciones. 

Este procedimiento muestra cómo el elemento raíz de un modelo se puede seleccionar como definición del modelo de datos para insertar una configuración de formato de informe electrónico (ER) que se designa para generar documentos electrónicos. En este procedimiento, usted agregará una configuración de formato de ER para la empresa de ejemplo Litware, Inc. 

Este procedimiento se ha creado para los usuarios con los roles de Administrador del sistema o Desarrollador de informes electrónicos asignados. Los pasos se pueden completar mediante cualquier conjunto de datos.

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como Activo. Si no ve a este proveedor de configuración, complete los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".  
2. Haga clic en Configuraciones de informes.

## <a name="add-a-new-er-data-model-configuration"></a>Agregue una nueva configuración para los datos de ER
1. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
    * Agregamos una nueva configuración del modelo de ER que contiene un modelo de datos que se designa para usarlo como origen de datos para generar informes ER.  
2. En el campo Nombre, escriba "Modelo de pagos (ficticio)".
    * Modelo de pago (ficticio)  
3. Haga clic en Crear configuración.
4. Haga clic en Diseñador.
    * Abra el diseñador de ER para especificar la estructura del modelo de datos de esta configuración.  
    * Supongamos que diseñamos el modelo de datos para que el dominio de pagos de la empresa admita 2 métodos de pago: transferencia de crédito y transferencia bancaria.  
5. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
6. En el campo Nombre, escriba "Pagos: transferencia de crédito".
    * Pagos: transferencia de crédito  
7. Haga clic en Agregar.
8. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
9. En el campo "Nuevo nodo como", escriba "Raíz del modelo".
10. En el campo Nombre, escriba "Pagos: transferencia bancaria".
    * Pagos: domiciliación bancaria  
11. Haga clic en Agregar.
12. Haga clic en Guardar.
13. Cierre la página.
14. Haga clic en Cambiar estado.
    * Complete la versión de borrador del modelo para que esté disponible en las asignaciones y los formatos del modelo nuevo.  
15. Haga clic en Completar.
16. Haga clic en Aceptar

## <a name="start-to-enter-a-new-er-format-configuration"></a>Empezar a especificar una nueva configuración del formato de ER
1. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
2. En el campo Nuevo, especifique "Formato basado en el modelo de datos del Modelo de pagos (ficticio)".
3. En el campo definición del modelo de Datos, introduzca o seleccione un valor.
    * Tenga en cuenta que todos los elementos raíz del modelo de datos seleccionados están actualmente disponibles para su selección como definición del modelo de datos. Puede continuar diseñando el formato mediante cualquiera de los elementos raíz necesarios del modelo de datos. Si falta una asignación de modelo para el elemento raíz seleccionado no impide que continúe.  
4. Cierre la página.

## <a name="add-a-new-er-model-mapping-configuration"></a>Agregar una nueva configuración de asignación al modelo de ER
1. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
2. En el campo Nuevo, especifique "Asignación de modelo basado en el modelo de datos del Modelo de pagos (ficticio)".
3. En el campo Nombre, escriba "Asignaciones de Modelo de pagos (ficticio)".
    * Asignaciones del modelo de pago (ficticio)  
4. En el campo definición del modelo de Datos, introduzca o seleccione un valor.
5. Haga clic en Crear configuración.

## <a name="design-er-model-mappings"></a>Diseñar asignaciones de modelo de ER
1. Haga clic en Diseñador.
    * Use el diseñador de ER para especificar las asignaciones de modelo para los elementos raíz necesarios.  
2. Haga clic en Diseñador.
    * Simule el valor de la asignación del modelo seleccionado para el elemento raíz del modelo seleccionado.  
3. En el árbol, seleccione "Dynamics 365 for Operations\Registros de tabla".
4. Haga clic en Agregar raíz.
5. En el campo Nombre escriba "Libro mayor".
6. En el campo Tabla, escriba "LedgerJournalTrans".
    * LedgerJournalTrans  
7. Haga clic en Aceptar
8. Haga clic en Guardar.
9. Cierre la página.
10. Cierre la página.

## <a name="start-to-enter-another-new-er-format-configuration"></a>Empezar a especificar otra configuración de formato de ER nueva
1. En el árbol, seleccione "Modelo de pagos (ficticio)".
2. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
3. En el campo Nuevo, especifique "Formato basado en el modelo de datos del Modelo de pagos (ficticio)".
4. En el campo definición del modelo de Datos, introduzca o seleccione un valor.
    * Tenga en cuenta que solo un elemento raíz está disponible ahora asignar a los orígenes de datos de la aplicación. Cuando se introduce al menos una asignación de modelo, solo los artículos raíz del modelo se asignan a los orígenes de datos de la aplicación se pueden seleccionar como definición de modelo cuando se agrega el formato de ER.   
5. Cierre la página.

