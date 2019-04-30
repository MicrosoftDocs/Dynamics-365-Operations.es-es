---
title: Novedades y cambios en Dynamics 365 for Talent Core HR (16 de octubre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 51cfe8a92d1ac611e946934fe8ebbc99053788f1
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "858362"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-19-2018"></a>Novedades y cambios en Dynamics 365 for Talent Core HR (19 de octubre de 2018)

[!include[banner](includes/banner.md)]

**Compilación 8.1.1067**

Este tema describe las características que son nuevas o que se han cambiado en Core HR.

## <a name="allow-managers-to-update-time-off-requests"></a>Permitir que los administradores actualicen solicitudes de licencia

Las solicitudes de licencia de los empleados es posible que necesiten actualizarse después de que se aprueben con el flujo de trabajo. En muchos casos, el administrador se encarga de estas actualizaciones en nombre del empleado. Esta nueva característica permite a los administradores actualizar las solicitudes de licencia o cancelarlas en nombre de sus empleados. Esta capacidad se controla mediante el parámetro **Trabajo en nombre de** que se establece en la página **Parámetros de recursos humanos**. 
 
## <a name="allow-hr-to-update-time-off-requests"></a>Permitir que HH. RR. actualice solicitudes de licencia

Similar a la función anterior, es posible que RR. HH. tenga que actualizar las solicitudes de licencia de los empleados después de que se hayan aprobado anteriormente con el flujo de trabajo. Esta característica proporciona la capacidad a los usuarios de RR. HH. de actualizar las solicitudes de licencia. La capacidad se habilita en el área de trabajo **Personas** y en la página **Trabajador** , mediante una nueva opción denominada **Ver licencia**. En tales páginas, los usuarios de RR. HH. pueden ver solicitudes y actualizar las transacciones de licencia, igual a cómo los administradores pueden realizar estas acciones.

El derecho de seguridad que controla el acceso a esta función es:
- Derecho: Mantener procesos de bajas y ausencias específicos de trabajador.
- Privilegio: Mantener solicitudes de baja y de ausencia para todos los trabajadores.

## <a name="other-changes"></a>Otros cambios
Las actualizaciones siguientes se han creado en esta versión:
- Cambios en las acciones de contratación del trabajador que ya no están "atascados" en el estado **Flujo de trabajo completado**.
- Ahora se puede crear un registro de empleo sin una fecha de inicio del empleo.
- Ahora la fecha del registro de Dynamics 365 Talent para un curso mostrado en autoservicio de empleados aplica la diferencia de zona horaria a la fecha.
- Los archivos Excel se pueden importar varias veces sin errores con **Entidad del empleado**.

## <a name="known-issue"></a>Problema conocido

- **Emisión**: Al agregar un nuevo archivo adjunto a un trabajador, los botones **Nuevo** y **Editar** se atenúan. 
- **Solución alternativa:** Antes de abrir la página de los datos adjuntos, asegúrese de que los cuadros informativos en la página **Trabajador** estén cerrados. Si se cierran los cuadros informativos cuando la página **Trabajador** se carga, los botones de datos adjuntos se habilitan. (Este problema se corregirá en la siguiente actualización de la plataforma).
