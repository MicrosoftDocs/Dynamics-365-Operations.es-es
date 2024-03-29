---
title: Configurar parámetros de bajas y ausencias
description: Este artículo describe cómo definir parámetros de recursos humanos para permisos y ausencias en Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3a39c74eef3865c03ccb9dd5aa2fece7f25e639a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891390"
---
# <a name="configure-leave-and-absence-parameters"></a>Configurar parámetros de bajas y ausencias

>[!Important]
>La funcionalidad mencionada en este artículo está disponible actualmente para los clientes de Dynamics 365 Human Resources independiente. Algunas o todas las funciones estarán disponibles como parte de una versión futura de la infraestructura de Finance después de la versión 10.0.26 de Finance.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Antes de configurar planes de bajas y ausencias en Dynamics 365 Human Resources, es una buena idea comprobar la configuración de todos los **Parámetros de recursos humanos** relacionados, incluidos los siguientes:

- Secuencia numérica para solicitudes de licencia
- Configuración de Ley de Ausencia Familiar y Médica
- Configuración de autoservicio de empleados para solicitudes de bajas y ausencias
- Parámetros de permisos y ausencias

## <a name="view-and-change-human-resources-parameters"></a>Ver y cambiar parámetros de recursos humanos

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.

2. En **Configuración**, seleccione **Parámetros de Recursos Humanos**.

3. En la pestaña **Secuencias numéricas**, compruebe el **Código de secuencia numérica** para el **Id. de solicitud de baja** y cambie según sea necesario. Esta configuración determina la secuencia que se usa para asignar id. automáticamente a solicitudes de bajas.

4. En la pestaña **FMLA**, compruebe la configuración de FMLA y cambie según sea necesario.

5. En la pestaña **Autoservicio para empleados**, indique si los responsables pueden introducir solicitudes de bajas y ausencias en nombre de sus empleados.

7. Seleccione **Guardar**.

>[!IMPORTANT]
>La visualización de permisos y ausencias en todas las empresas se encuentra actualmente en versión preliminar. Tendrá que habilitarlo en su entorno de **Espacio aislado** para mostrar la opción de permisos y ausencias. Para obtener más información sobre cómo habilitar las características en versión preliminar, consulte [Administrar características](hr-admin-manage-features.md).

## <a name="view-and-change-human-resources-shared-parameters"></a>Ver y cambiar parámetros compartidos de recursos humanos

1. En la página **Administración de personal**, seleccione la pestaña **Vínculos**.

2. En **Configuración**, seleccione **Parámetros compartidos de Recursos Humanos**.

3. En la pestaña **Acceso avanzado**, seleccione **Sí** para **Habilitar la vista de permisos entre empresas**, para permitir que la licencia se vea en toda la empresa.

4. Seleccione **Guardar**.

## <a name="view-and-change-leave-and-absence-parameters"></a>Ver y cambiar parámetros de permisos y ausencias

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.

2. En **Configuración**, seleccione **Parámetros de permisos y ausencias**.

3. En la pestaña **General**, establezca los parámetros siguientes:
 
    - Establezca **Unidad de permiso y ausencia** a horas o días. Si es días, puede seleccionar **Habilitar definición de medio día** para permitir a los empleados elegir la primera o segunda mitad del día en sus solicitudes de tiempo libre. 

    - Seleccione **Meses de servicio fecha efectiva** para establecer cuándo entran en vigencia las tasas de acumulación para los planes de permisos que utilizan meses de servicio.

    - Seleccione **Cálculo de saldo** para mostrar los saldos a partir de hoy o del período de acumulación. Si selecciona **Saldo a partir de hoy**, el saldo muestra el total de todas las acumulaciones, ajustes y solicitudes a partir de hoy. Si selecciona **Saldo a partir del período de acumulación**, el saldo muestra el total de todas las acumulaciones, ajustes y solicitudes a partir del período de acumulación definido por la frecuencia en el plan de permisos. 

    - Establezca la **Hora de inicio** para el trabajo por lotes **Vencimiento de transferencia**.  
    
    - Seleccione **Sí** para **Permitir que los empleados compren bajas** y **Permitir que los empleados vendan bajas**. Si selecciona **Sí** para estas opciones, puede crear políticas de compra y venta de bajas y permitir que los empleados envíen solicitudes de compra y venta de bajas.

## <a name="configure-calendar-parameters"></a>Configurar parámetros de calendario

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.

2. En **Configuración**, seleccione **Parámetros de permisos y ausencias**.

3. En la pestaña **Calendario**, compruebe la configuración del calendario según sea necesario.

4. Seleccione **Guardar**.

## <a name="see-also"></a>Consulte también

- [Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
