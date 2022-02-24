---
title: Mejoras en la administración de efectivo
description: En este tema se describe las mejoras en la administración de efectivo en PDV para Dynamics 365 Commerce.
author: anpurush
manager: AnnBe
ms.date: 05/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0c561c39dfcbfa739c5a22394c05191e7f9bc107
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415500"
---
# <a name="cash-management-improvements"></a>Mejoras en la administración de efectivo

[!include [banner](includes/banner.md)]


La administración de efectivo es una función clave para los minoristas en tiendas físicas. Los minoristas quieren que sus tiendas tengan sistemas que puedan ayudarle para proporcionar rastreabilidad y la contabilidad de efectivo y de su movimiento en varios registros y cajeros en una tienda. Deben poder conciliar cualquier diferencia y determinar la responsabilidad.


Microsoft Dynamics 365 Commerce tiene capacidades de flujo de efectivo en su de aplicación de punto de venta (PDV). Sin embargo, en versiones de Retail que sean anteriores a la versión 10.0.3, la funcionalidad de gestión de efectivo no es lo suficiente robusta para proporcionar la rastreabilidad completa de los movimientos de efectivo en tiendas. Aunque los minoristas pueden conciliar el efectivo para una tienda, no pueden determinar la responsabilidad exacta en caso de discrepancia de efectivo.


En Retail versión 10.0.3 y posteriores, los minoristas obtendrán la rastreabilidad para la gestión de efectivo. Como parte de esta rastreabilidad, los minoristas podrán definir los cajas fuertes, crear transacciones de efectivo bilaterales, y conciliar transacciones de flujo de efectivo.

## <a name="set-up-traceability-and-define-safes"></a>Configurar la rastreabilidad y definir cajas fuertes

Para configurar la nueva funcionalidad de gestión de efectivo, siga estos pasos para configurar el perfil de funcionalidad para las tiendas.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad** y seleccione un perfil de funcionalidad que esté vinculado a las tiendas para las que desea realizar mejoras en la administración de efectivo disponible.
2. En la ficha desplegable **Funciones** del perfil de funcionalidad, en **Administración de efectivo avanzada**, establezca la opción **Habilitar rastreabilidad de efectivo** a **Sí**.
3. Para configurar cajas fuertes, vaya a **Retail y Commerce \> Canales \> Tiendas \> Todas las tiendas** y seleccione una tienda.
4. En la página **Tiendas**, en el panel de acciones, en la pestaña **Configurar**, en el grupo **Configurar**, seleccione **Cajas fuertes**. Con esta opción puede definir y mantener varias cajas fuertes para un almacén.
4. Antes de que la funcionalidad se pueda usar, debe ejecutar el trabajo de la programación de la distribución **Configuración de canales 1070** para sincronización estas configuraciones con la base de datos del canal.

## <a name="additional-cash-management-changes"></a>Cambios adicionales de flujo de efectivo

En la versión 10.0.3 de Retail y posteriores, también se proporcionan las siguientes competencias relacionadas con las transacciones de efectivo:

- Un usuario al que se le solicita “declare el importe inicial” debe especificar el origen del efectivo. El usuario puede buscar las cajas fuertes disponibles que se definen en la tienda y seleccione la caja fuerte de la que se saca el efectivo para que se pueda colocarse en la caja registradora.
- Un usuario que realice una operación de "retirada con forma de pago" deberá seleccionar, entre una lista de transacciones abiertas de "entrada flotante", la transacción contra la que está haciendo la operación. Si la entrada flotante correspondiente no existe en el sistema, el usuario puede crear una forma de pago no vinculada a la transacción de retirada.
- Una operación de "entrada flotante" solicitará al usuario que seleccione, en una lista de transacciones de "retirada con forma de pago" la transacción contra la que se hace la operación de entrada flotante. Si la retirada con forma de pago correspondiente no existe en el sistema, el usuario puede crear una entrada flotante no vinculada a la transacción de retirada.
- Un usuario que hace un "ingreso seguro" deberá seleccionar la caja fuerte en la que está dejando el efectivo.
- Para las cajas fuertes definidas en una tienda, los usuarios pueden administrar operaciones como declarar la cantidad inicial, hacer una entrada flotante, una retirada con forma de pago y hacer un ingreso bancario.
- Para los usuarios que tengan privilegios de usuario adecuados, las operaciones de “gestionar turnos” mostrará el saldo en efectivo de activo, suspendidos, y los turnos cerrados a ciegas.
- Para conciliar las transacciones de efectivo dentro de un turno o a través de turnos, seleccione el turno para conciliar y, a continuación seleccione **Conciliar**. La vista abierta muestra la lista de transacciones conciliadas y no conciliadas en pestañas independientes. De esta vista, los usuarios pueden seleccionar las transacciones no conciliadas y conciliarlas, o seleccionar transacciones anteriormente conciliadas y no conciliarlas.
- Durante la conciliación, si la transacción seleccionada no están compensadas, el usuario debe especificar una descripción del motivo de la conciliación desequilibrada. Los usuarios pueden seleccionar una sola transacción y conciliarla con la descripción de razón relevante que necesiten.
- Los usuarios pueden seguir conciliando y no conciliando transacciones hasta que se cierre el turno. Después de que se cierre un turno, las transacciones no se pueden no conciliar.
- Cuando un usuario elige cerrar un turno, Commerce valida que no haya transacciones no conciliadas de flujo de efectivo en el turno. Los usuarios no pueden cerrar un turno si hay transacciones sin conciliar.
