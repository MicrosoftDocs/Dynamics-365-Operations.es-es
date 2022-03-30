---
title: Diferencia inesperada entre la solicitud y los datos de la sesión durante la prueba
description: Se produce una diferencia inesperada entre los datos de la solicitud y la sesión en los resultados de validación de tareas de la aplicación de almacén.
author: mamuszal
ms.date: 03/11/2022
ms.topic: troubleshooting
ms.search.form: WHSValidatorRunInstance_executeRun
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mamuszal
ms.search.validFrom: 2022-03-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: da8f0506a76b0d0cc02bfc2e1bff01b4ddccb578
ms.sourcegitcommit: 941119133be1765f653d5d5270dfdf58466e1d07
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "8456946"
---
# <a name="unexpected-difference-between-request-and-session-data-during-testing"></a>Diferencia inesperada entre la solicitud y los datos de la sesión durante la prueba

Código de error: WarehouseMobileDeviceRequestInputValidationError

## <a name="symptoms"></a>Síntomas

Cuando está usando el [marco de validación de tareas de la aplicación de almacén](/dynamics365-release-plan/2019wave2/dynamics365-supply-chain-management/warehouse-app-task-validation-rsat), el validador devuelve el siguiente mensaje de error:

> Diferencia inesperada entre la solicitud y los datos de la sesión. Protocolo XML de dispositivos móviles de almacén violado.REQUEST_XML_TAMPERING

## <a name="cause"></a>Causa

El error ocurre cuando la salida del último paso que se ejecutó con éxito en la ejecución de prueba no coincide con la entrada registrada para el siguiente paso. Esta situación puede surgir porque el validador de tareas no utiliza la salida de un paso anterior como entrada para un paso sucesivo. En su lugar, utiliza XML grabado como entrada para cada paso.

En la mayoría de los casos, el error ocurre cuando vuelve a ejecutar una tarea, pero la prueba requiere algunos registros que fueron modificados o eliminados por una ejecución anterior de la misma tarea.

## <a name="resolution"></a>Resolución

La ejecución de la prueba de validación de la tarea de la aplicación de almacén no es una operación idempotente, sino que modifica los datos subyacentes. Por lo tanto, antes de volver a ejecutar una tarea, es posible que deba restablecer los datos relevantes.

1. Revise el XML de salida del último paso de prueba exitoso para determinar dónde quedó su ejecución de prueba.
1. Inspeccione su prueba y asegúrese de que todas las órdenes de venta, órdenes de transferencia, encabezados de trabajo y otros registros requeridos aún estén presentes y en el estado esperado.
1. Vuelva a crear o edite los registros faltantes o modificados. Alternativamente, cree una nueva configuración de prueba y diseñe la prueba para usar registros existentes válidos.
