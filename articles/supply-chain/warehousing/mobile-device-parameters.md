---
title: Parámetros globales de dispositivos móviles
description: Este artículo explica cómo configurar los ajustes del dispositivo móvil en la página de parámetros de gestión de almacén.
author: Mirzaab
ms.date: 08/13/2021
ms.topic: article
ms.search.form: WHS
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e6e03414edd9243fcc4156195928455b30a7cee9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847770"
---
# <a name="global-mobile-device-parameters"></a>Parámetros globales de dispositivos móviles

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar los parámetros globales de gestión de almacén que afectan a la forma en que el sistema interactúa con los dispositivos móviles.

Para obtener más información sobre cómo configurar trabajadores de almacén, consulte [Administrar trabajador de almacén](manage-warehouse-workers.md). Para obtener más información sobre el manejo de matrículas en dispositivos móviles, consulte [Recepción de matrículas a través de la aplicación móvil Warehouse Management](warehousing-mobile-device-app-license-plate-receiving.md). Para obtener más información sobre los procesos de recuento cíclico, consulte [Recuento cíclico](cycle-counting.md) y [Escenarios de ejemplo de recuento cíclico](cycle-counting-scenarios.md).

## <a name="open-the-warehouse-management-parameters-page"></a>Abrir la página de parámetros de gestión de almacenes

Para abrir la página **Parámetros de gestión de almacenes**, vaya a **Gestión de almacenes \> Configuración \> Parámetros generales del almacén**. A continuación, puede configurar los campos relacionados con el trabajo del dispositivo móvil, como se describe en la siguiente sección de este artículo.

## <a name="mobile-device-fasttab-on-the-general-tab"></a>Ficha desplegable Dispositivo móvil en la pestaña General

La configuración global del dispositivo móvil se encuentra en la ficha desplegable **Dispositivo móvil** de la pestaña **General** de la página **Parámetros de gestión de almacén**. Están disponibles los siguientes campos.

| Campo | Descripción |
|---|---|
| Tipo de nota del dispositivo móvil | Seleccione el tipo de información que se muestra a los trabajadores durante la recogida de pedidos de ventas. |
| Límite de cantidad escaneada | Ingrese la cantidad máxima de artículos que un trabajador puede escanear durante cada sesión, utilizando un elemento de menú de dispositivo móvil que tiene un valor de **Proceso de creación de trabajo** de *Ajuste*. Este campo no afecta a los escaneos que se realizan con cualquier otro tipo de elemento de menú. |
| Usar el inicio de sesión del dispositivo móvil | Establezca esta opción en *Sí* para mantener un registro del historial de inicios de sesión de los trabajadores. Para ver el registro, vaya a **Sesiones de usuarios de trabajo \> Consultas e informes \> Registros de dispositivos móviles \> Sesiones de usuarios de trabajo**. |
| Número de errores almacenados | Ingrese el número máximo de registros de error que el sistema debería almacenar. Para ver el registro de errores, vaya a **Sesiones de usuarios de trabajo \> Consultas e informes \> Registros de dispositivos móviles \> Sesiones de usuarios de trabajo**. |
| Diario de transferencia de almacén predeterminado | Seleccione el diario que se usa cuando los trabajadores usan un dispositivo móvil para mover productos de un almacén a otro. |
| Permitir el registro de líneas de pedido de compra cuando hay una revisión externa | Establezca esta opción en *Sí* caso de que los trabajadores debieran poder usar un dispositivo móvil para registrar líneas de pedido para pedidos de compra que tienen un valor de **Estado de aprobación** de *En revisión externa*. Establezca esta opción en *No* para evitar que los trabajadores registren líneas para órdenes de compra que están en revisión externa. |
| Habilitar compatibilidad con RSAT | El campo habilita el validador de tareas de la aplicación móvil Warehouse Management, que registra y valida cada paso que realiza la aplicación. Debido a que este proceso puede ralentizar significativamente el rendimiento del sistema, debe habilitar el validador solo durante la prueba. Nunca debe habilitarlo en un entorno de producción. |
