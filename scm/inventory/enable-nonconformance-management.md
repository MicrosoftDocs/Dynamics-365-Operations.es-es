---
title: "Gestión de disconformidad"
description: "Este artículo describe la configuración básica necesaria para usar disconformidades. Se requiere configuración adicional si desea usar pedidos de calidad."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 28951
ms.assetid: a62d4ba8-eebc-4b14-b587-630be7298522
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4aebabfc6160393e5c817cd07af835d3b1268c2e
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="nonconformance-management"></a>Gestión de disconformidad

[!include[banner](../includes/banner.md)]


Este artículo describe la configuración básica necesaria para usar disconformidades. Se requiere configuración adicional si desea usar pedidos de calidad. 

Para activar la gestión de disconformidades, siga estos pasos:

1.  Defina los parámetros de gestión de inventario y almacén relacionados con disconformidades:
    -   Defina la opción **Usar administración de calidad** en **Sí**.
    -   Use el campo **Índice por hora** para especificar una tasa de mano de obra por hora en la divisa local. El índice por hora se usa para calcular los costes de operaciones relacionadas con un caso de disconformidad. El índice por hora y los costes calculados proporcionan información de referencia para un caso de disconformidad. No interactúan con otra función.
    -   Utilice la pestaña **Gestión de calidad** de la página **Configuración del informe** para definir el tipo de documento que desea imprimir. Puede imprimir un informe de disconformidad, una etiqueta de disconformidad o un informe de corrección. Se puede definir más de un registro para imprimir diferentes tipos de documento en un informe, o para imprimir notas internas y externas. Puede ser útil usar la página **Tipo de documento** para definir un tipo de documento único para un caso de disconformidad, y un tipo de documento único para correcciones. Por ejemplo, desea escribir notas acerca un caso de disconformidad utilizando el tipo de documento exclusivo para casos de disconformidad. En este caso, identifique el tipo de documento único en las opciones del informe.
    -   Habilite secuencias numéricas para las referencias de disconformidad y correcciones.

2.  Active la aprobación del usuario de los casos de disconformidad. Use el campo **Nombre** de la página **Usuarios** para asignar un empleado a cada usuario que deba aprobar un caso de disconformidad. El sistema utiliza los empleados que cambian el estado de un caso de disconformidad para realizar un seguimiento del historial de disconformidad. Los usuarios no pueden aprobar los casos de disconformidad a menos que se les hayan asignado un identificador de empleado.
3.  Defina los tipos de problema que se asignarán a los casos de disconformidad. Use la página **Tipos de problemas** para definir una clasificación de problemas de calidad encontradas en los distintos tipos de disconformidad. Puede configurar los siguientes tipos de disconformidad: **Interna**, **Cliente**, **Proveedor**, **Solicitud de servicio**, **Producción** y **Producción de coproductos**. Use la página **Tipos de no conformidad** para autorizar el uso de un tipo de problema en uno o varios tipos de disconformidad. Por ejemplo, un tipo de problema relativo a un código defectuoso se podría aplicar a todos los tipos de disconformidad, mientras que un tipo de problema relacionado con quejas del cliente solo se puede aplicar a los tipos de disconformidad **Cliente** y **Solicitud de servicio**.
4.  Defina zonas de cuarentena para proporcionar instrucciones acerca de cómo tratar el material defectuoso. Use la página **Zonas de cuarentena** para definir zonas que pueden asignarse a una disconformidad. La etiqueta impresa de disconformidad mostrará las zonas de cuarentena asignadas junto con la información de uso para guiar el tratamiento del material defectuoso. Las zonas pueden corresponder a ubicaciones de inventario o a recursos de operaciones.
5.  Defina los tipos de diagnóstico que se asignarán a correcciones. Use la página **Tipos de diagnóstico** para definir una clasificación de acciones de diagnóstico. Una corrección especifica qué tipo de acción de diagnóstico se debe realizar en una disconformidad aprobada, quién debe efectuarla. También especifica la fecha de finalización solicitada y la fecha de finalización planificada.
6.  Defina las operaciones relacionadas que se asignarán a los casos de disconformidad. Use la página **Operaciones** para definir una clasificación del trabajo que se debe efectuar para un caso de disconformidad aprobado. Al asignar una operación relacionada a un caso de disconformidad, también se puede proporcionar información detallada acerca del material asociado, las horas de trabajo y los gastos varios requeridos para llevar a cabo la operación. Esta información se usa para calcular el coste estimado para la operación. La información detallada y los costes estimados sirven como referencia. Las operaciones relacionadas para la calidad son diferentes de las operaciones que se pueden definir para una ruta de producción.


<a name="see-also"></a>Consulte también
--------

[Creación y procesamiento de una disconformidad (guías de tareas)](https://ax.help.dynamics.com/en/wiki/create-and-process-a-nonconformance/)

[Procesos de gestión de calidad](quality-management-processes.md)

[Configurar requisitos previos para la gestión de no conformidades (guía de tareas)](https://ax.help.dynamics.com/en/wiki/set-up-prequisites-for-nonconformance-management/)




