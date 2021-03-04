---
title: Conciliación financiera en tiendas minoristas
description: Este tema describe la conciliación financiera en las tiendas minoristas de PDV para Microsoft Dynamics 365 Commerce.
author: anpurush
manager: AnnBe
ms.date: 06/09/2020
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
ms.openlocfilehash: 5d0520f35391f76b52fd8a333033b0d7ba4f7fe1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415424"
---
# <a name="financial-reconciliation-in-retail-stores"></a>Conciliación financiera en tiendas minoristas

[!include [banner](includes/banner.md)]

En Microsoft Dynamics 365 Commerce versión 10.0.10 y anteriores, la funcionalidad que el cliente de punto de venta (PDV) proporciona para los procesos de fin de día en las tiendas minoristas, permite que los empleados y gerentes de las tiendas realicen las operaciones de fin de día. Por ejemplo, pueden hacer declaraciones de licitación, turnos de cierre a ciegas, conciliar transacciones de turnos y cerrar turnos. Sin embargo, no hay capacidad en PDV para finalizar la información financiera para los turnos, de modo que pueda usarse para publicar los datos financieros en la sede de Commerce. Por lo general, los gerentes de tienda son responsables de completar esta tarea. Antes de que puedan firmar un turno, deben revisar la información, hacer las correcciones necesarias y finalizar los totales de ese turno. Los totales finalizados deben publicarse en módulos financieros en la sede de Commerce.

Además, en Commerce versión 10.0.10 y anteriores, los gerentes de las tiendas pueden revisar y hacer algunos ajustes a las líneas de declaración en la sede de Commerce. Sin embargo, la capacidad es limitada y los gerentes de las tiendas rara vez tienen acceso al cliente de la sede de Commerce. Además, la revisión y el ajuste de los estados financieros minoristas solo se pueden realizar cuando las instrucciones se crean en la sede de Commerce. Sin embargo, ese proceso es típicamente un proceso nocturno. Por lo tanto, los gerentes de las tiendas deben esperar la firma del turno cuando se crean los estados financieros minoristas en la sede de Commerce.

En Commerce versión 10.0.11 y posterior, los gerentes de las tiendas pueden revisar, ajustar y finalizar sus turnos en el propio cliente PDV. Esos datos se utilizan para crear y publicar declaraciones financieras minoristas en la sede de Commerce.

> [!NOTE]
> La funcionalidad que está relacionada con la reconciliación financiera en las tiendas minoristas solo funciona si la creación de pedidos basada en alimentación lenta está activada. Para más información, consulte [Goteo en la creación de pedidos basados en fuente para transacciones de tienda](trickle-feed.md).

## <a name="set-up-financial-reconciliation"></a>Configurar conciliación financiera

Siga estos pasos para comenzar a usar la funcionalidad de conciliación financiera.

1. En el espacio de trabajo **Gestión de funciones**, active la característica **Declaraciones minoristas: alimentación por goteo**.
1. En el perfil de funcionalidad PDV para la tienda adecuada, establezca la opción **Habilitar la conciliación financiera en la tienda** en **Sí**.

## <a name="more-information-about-financial-reconciliation"></a>Más información sobre la conciliación financiera

Cuando la funcionalidad de conciliación financiera está activada, algunos de los parámetros definidos en la ficha desplegable **Declaración / cierre** de la página **Tiendas minoristas** en la sede de Commerce se sincroniza con la base de datos del canal. Se aplica el mismo conjunto de criterios de cálculo y umbrales de importe que se utilizan para los extractos minoristas.

Cuando se invoca la operación **Cerrar turno**, el sistema valida que las cantidades calculadas por el sistema y las cantidades declaradas coinciden. Si difieren y la diferencia excede los umbrales definidos, se consulta al usuario y puede hacer los ajustes necesarios.

Se pueden hacer ajustes para cada oferta. Cuando se selecciona una operación, el usuario puede ver los totales para diferentes tipos de transacciones y editar los totales para un tipo de transacción específico. Durante la edición, el sistema muestra la cantidad calculada original y la cantidad anulada para ese tipo de transacción. El usuario también puede capturar notas como parte del proceso de edición. Las notas se pueden usar con fines de auditoría.

Los usuarios pueden ignorar las solicitudes y mensajes de validación y pueden proceder a cerrar el turno. Sin embargo, si un usuario ignora las indicaciones de validación, surgirán los mismos problemas y deberán corregirse cuando el turno publique los estados financieros en la sede de Commerce.

La operación **Cerrar turno** en PDV también valida que todas las transacciones en la base de datos fuera de línea se sincronizan con la base de datos del canal. Si alguna transacción no se sincroniza, el usuario recibe un mensaje de advertencia, ya que esta situación puede hacer que las cantidades del sistema se calculen incorrectamente. En esta situación, el usuario puede finalizar la operación **Cerrar turno** e intentar sincronizar las transacciones fuera de línea con la base de datos del canal. Alternativamente, el usuario puede ajustar manualmente las cantidades calculadas por el sistema para tener en cuenta las transacciones que no están sincronizadas, de modo que el conjunto correcto de números financieros se finalice y se contabilice. 

Cuando se utiliza la contabilización de declaraciones de alimentación por goteo, de modo que la contabilización de transacciones se separa de la contabilización de datos financieros, puede elegir ajustar los importes calculados por el sistema para las transacciones sin conexión que faltan. De esta manera, se asegura de que las finanzas siempre se contabilicen y contabilicen correctamente, independientemente de las transacciones faltantes. Las transacciones sin conexión se pueden sincronizar con la base de datos del canal y la sede de Commerce y luego publicarse más tarde, por separado de las contabilizaciones financieras.

Los detalles de la conciliación financiera para un turno se sincronizan con la sede de Commerce mediante el uso del trabajo P.

Los extractos financieros minoristas en la sede de Commerce no calculan los totales para mostrar los detalles en las líneas de los extractos financieros. En cambio, las cantidades finalizadas en el cliente PDV se utilizan para crear y publicar extractos financieros minoristas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]