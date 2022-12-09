---
title: Crear un permiso para ausentarse con finalización abierta
description: Este artículo explica cómo crear un permiso para ausentarse con finalización abierta en Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
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
ms.openlocfilehash: 08231d4139209387c3c76923fafdd2061fceb280
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805347"
---
# <a name="create-an-open-ended-leave-of-absence"></a>Crear un permiso para ausentarse con finalización abierta

> [!IMPORTANT]
> La funcionalidad que se describe en este artículo estará disponible en la infraestructura de Finance como parte de una versión futura después de Microsoft Dynamics 365 Finance versión 10.0.31.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede enviar solicitudes de permiso para ausentarse con finalización abierta y ver el estado de sus solicitudes en Dynamics 365 Human Resources.

## <a name="prerequisites"></a>Requisitos previos

1. En **Administración de características**, asegúrese de que la característica **Permiso con finalización abierta** esté activada.

    > [!IMPORTANT]
    > Una vez activada la función, no se puede desactivar.

2. Cree un tipo de licencia de permiso para ausentarse.
3. Ingrese los detalles, como el tipo de permiso, la descripción y el Id. del flujo de trabajo.
4. En el campo **Tipo de solicitud**, seleccione **Permiso para ausentarse**.
5. En la sección de detalles, para permisos con finalización abierta, establezca la opción **Con finalización abierta** en **Sí**.
6. Establezca la opción **Aviso de vuelta al trabajo** en **Sí** o **No**.
7. Opcionalmente, se puede solicitar un aviso de vuelta al trabajo para las solicitudes de permiso para ausentarse de final abierto.

> [!NOTE]
> Después de habilitar esta característica, se habilitará la característica **Se requiere adjunto**.

## <a name="request-an-open-ended-leave-of-absence"></a>Solicitar un permiso para ausentarse con finalización abierta

1. En el espacio de trabajo **Autoservicio para empleados**, en el icono **Saldos de licencias**, seleccione **Más (...)**.
2. Para enviar una solicitud de excedencia, seleccione **Solicitar permiso para ausentarse**.
3. Introduzca información en los campos **Tipo de baja** y **Fecha inicial**. En el campo **Fecha final**, especifique una fecha final tentativa.
4. Si debe enviar documentación complementaria, en **Archivos adjuntos**, seleccione **Cargar**.
5. Si ya está listo para enviar su solicitud, seleccione **Enviar**. De lo contrario, seleccione **Guardar borrador**.
6. Para actualizar un permiso para ausentarse como de finalización abierta, seleccione la solicitud, ingrese una fecha de finalización en el campo **Fecha de finalización**, establezca la opción **Confirmar fecha de finalización** como **Sí** y cargue la documentación.
7. Si la opción **Aviso de vuelta al trabajo** está establecida en **Sí**, seleccione **Cargar** y luego seleccione la casilla para confirmar que se cargó un aviso de vuelta al trabajo válido.
8. Cuando haya ingresado todos los detalles, seleccione **Enviar**.
