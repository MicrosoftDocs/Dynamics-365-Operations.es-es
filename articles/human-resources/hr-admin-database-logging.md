---
title: Configurar y administrar el registro de la base de datos
description: Puede realizar un seguimiento de los cambios en las tablas y campos en Dynamics 365 Human Resources con registro de base de datos.
author: andreabichsel
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 50346cc495fe08f49137dba59dbcbb3f7f838c7b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129288"
---
# <a name="configure-and-manage-database-logging"></a>Configurar y administrar el registro de la base de datos

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
2. Complete el asistente.

## <a name="clean-up-database-logs"></a>Limpiar registros de bases de datos

Puede eliminar todo o parte de los registros de la base de datos, utilizando las siguientes opciones:

- Seleccione todos los registros para una tabla en particular.
- Seleccione tipos específicos de registro de base de datos.
- Seleccione una fecha y hora en que se creó un registro.

Siga estos pasos para configurar la limpieza del registro de bases de datos: 

1. Vaya a **Administración del sistema > Enlaces > Base de datos > Registro de bases de datos**. Seleccione **Limpiar registro**.

2. Elija un método de selección de registros para eliminar especificando una de las siguientes opciones:

   - ID de tabla
   - Tipo de registro
   - Fecha y hora de creación

3. Utilice la pestaña **Limpieza de registro de bases de datos** para determinar cuándo ejecutar la tarea de limpieza del registro. De forma predeterminada, los registros de la base de datos están disponibles durante 30 días.
