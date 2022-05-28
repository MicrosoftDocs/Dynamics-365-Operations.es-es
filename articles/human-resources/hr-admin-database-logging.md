---
title: Configurar y administrar el registro de la base de datos
description: Puede realizar un seguimiento de los cambios en las tablas y campos en Dynamics 365 Human Resources con registro de base de datos.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5b8641655cf31453f6fc11e2056fb6bf96a43cbc
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8696274"
---
# <a name="configure-and-manage-database-logging"></a>Configurar y administrar el registro de la base de datos


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede realizar un seguimiento de los cambios en las tablas y campos en Dynamics 365 Human Resources con registro de base de datos. En este tema se describe cómo:

- Administrar la seguridad y el rendimiento para el registro de la base de datos
- Configurar nivel de registro de base de datos
- Limpiar registros de bases de datos

## <a name="overview-of-database-logging"></a>Descripción general del registro de la base de datos

El registro de la base de datos lleva el seguimiento de los cambios específicos en las tablas y campos en Microsoft Dynamics 365 Human Resources. Estos cambios incluyen insertar, actualizar o eliminar. El registro de la base de datos almacena un registro de cambios en las tablas o campos en la tabla de registro de la base de datos.

Los usos comerciales del registro de la base de datos incluyen:

- Crear un registro de auditoría de cambios para tablas específicas que contengan información confidencial.
- Seguimiento de transacciones individuales. El registro de la base de datos no está destinado a llevar el seguimiento de transacciones automatizadas que se ejecutan en trabajos por lotes.

## <a name="security-for-database-logging"></a>Seguridad para el registro de la base de datos

Los registros de las bases de datos pueden contener datos confidenciales. Limite el acceso para incluir solo roles de seguridad que necesiten acceso a los datos de registro.

## <a name="database-logging-and-performance"></a>Registro de base de datos y rendimiento

Pese a que puede ser valioso desde una perspectiva de negocio, el registro de bases de datos puede resultar caro si se mide por gestión y uso de recursos. Las implicaciones para el rendimiento del registro de la base de datos incluyen:

- La tabla de registro de la base de datos puede crecer rápidamente y causar un aumento en el tamaño de la base de datos. El crecimiento depende de la cantidad de datos registrados que decida conservar. De forma predeterminada, la tabla de registro de la base de datos conserva solo los datos de registro durante 30 días. 

- El registro de bases de datos puede afectar negativamente a los procesos automatizados de larga duración, como las importaciones de datos de larga ejecución.

### <a name="best-practices"></a>Prácticas recomendadas

Para mejorar el rendimiento, limite las entradas en el registro seleccionando campos específicos en lugar de tablas enteras. Para ayudar a conservar el rendimiento general, el registro de bases de datos está limitado a 20 tablas.

> [!NOTE]
> Para campos individuales, solo se pueden registrar las actualizaciones.

## <a name="set-up-database-logging"></a>Configurar nivel de registro de base de datos

Puede usar el asistente **Registro de cambios en la base de datos** para configurar el registro de bases de datos. El asistente proporciona una forma flexible de configurar el registro de tablas o campos.

1. Vaya a **Administración del sistema> Enlaces > Base de datos > Configuración del registro de bases de datos**. Seleccione **Nuevo** para comenzar el asistente **Registro de cambios en la base de datos**.
2. Seleccione **Siguiente**. 
3. En la página **Tablas y campos** del asistente, seleccione las tablas y los campos en los que desea habilitar el registro de la base de datos y seleccione **Siguiente**.

   > [!Note]
   > El registro de la base de datos no está disponible en todas las tablas de la base de datos de Human Resources. La selección de **Mostrar todas las tablas**, situada a continuación de la lista, expande la lista de tablas y campos para mostrar todas las tablas de la base de datos para las que está disponible el registro de la base de datos, pero esto será un subconjunto de la lista completa de tablas de la base de datos.

4. En la página **Tipos de cambio** del asistente, seleccione las operaciones de datos para las que desea realizar un seguimiento de los cambios para cada uno de los campos y tablas, y seleccione **Siguiente**. Consulte la tabla siguiente para obtener una descripción de las operaciones de datos disponibles para el registro.
5. En la página **Terminar**, revise los cambios que se realizarán y seleccione **Terminar**.

| Operación | Descripción |
| -- | -- |
| Realizar seguimiento de transacciones nuevas | Cree un registro para los nuevos registros que se crean en la tabla. |
| Actualización | Cree un registro para las actualizaciones de los registros de la tabla o actualizaciones de los campos seleccionados individualmente en la tabla. Si selecciona registrar las actualizaciones para la tabla, se crea un registro de registro cada vez que se realiza una actualización en cualquier campo de cualquier registro de la tabla. Si selecciona registrar actualizaciones para campos específicos, se crea un registro solo cuando se realizan actualizaciones en esos campos de registros de tabla. |
| Suprimir | Cree un registro de los registros eliminados de la tabla. |
| Asignar nuevo nombre a la clave | Cree un registro de registros cuando se cambie el nombre de una clave de tabla. |


## <a name="clean-up-database-logs"></a>Limpiar registros de bases de datos

Puede eliminar todo o parte de los registros de la base de datos, utilizando las siguientes opciones:

- Seleccione todos los registros para una tabla en particular.
- Seleccione tipos específicos de registro de base de datos.
- Seleccione una fecha y hora en que se creó un registro.

Siga estos pasos para configurar la limpieza del registro de bases de datos: 

1. Vaya a **Administración del sistema > Enlaces > Base de datos > Registro de bases de datos**. Seleccione **Limpiar registro**.
2. En el encabezado **Registros a incluir**, seleccione **Filtro**.
3. Elija el método que se utilizará para seleccionar los registros que desee eliminar. Introduzca una de las siguientes opciones:

   - ID de tabla
   - Tipo de registro
   - Fecha y hora de creación

4. Utilice la pestaña **Limpieza de registro de bases de datos** para determinar cuándo ejecutar la tarea de limpieza del registro. De forma predeterminada, los registros de la base de datos están disponibles durante 30 días.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
