---
title: Inicializar Commerce Scale Unit (nube)
description: Este tema explica cómo inicializar Commerce Scale Unit (nube) en Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 02/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2018-4-30
ms.openlocfilehash: 84e70515accde161e7efa36755edec68d26be952
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092216"
---
# <a name="initialize-commerce-scale-unit-cloud"></a>Inicializar Commerce Scale Unit (nube)

[!include[banner](../includes/banner.md)]

Este tema explica cómo inicializar Commerce Scale Unit (nube) en Microsoft Dynamics 365 Commerce.

Si está utilizando un entorno de producción o sandbox de nivel 2 que tiene la versión de la aplicación 8.1.2.x o posterior, debe inicializar Commerce Scale Unit (nube) antes de poder usar la funcionalidad del canal minorista para las operaciones de punto de venta (POS). o para operaciones de comercio electrónico que utilizan Retail Server en la nube. La inicialización implementará Commerce Scale Unit (nube).

> [!IMPORTANT]
> Para los clientes existentes que usan la funcionalidad del canal minorista en la nube, para garantizar un soporte continuo e ininterrumpido para su negocio, requerimos que actualice sus canales minoristas para usar Commerce Scale Unit. Los nuevos entornos implementados sin Commerce Scale Unit ya no recibirán actualizaciones de calidad y servicio para los componentes del canal minorista alojados en la nube. No se requiere ninguna acción para los clientes que usan exclusivamente Commerce Scale Unit (autohospedado). Póngase en contacto con Microsoft FastTrack Solution Architect si necesita una extensión.

## <a name="prerequisites"></a>Requisitos previos

1. Implemente un entorno de producción o sandbox de nivel 2 que tenga la versión 8.1.2.x o posterior.
2. Puede autoimplementar hasta 2 Commerce Scale Units por entorno. Si necesita más de 2 Commerce Scale Units por entorno, en Microsoft Dynamics Lifecycle Services (LCS), cree una solicitud de soporte e ingrese **Solicitud de Commerce Scale Unit adicional** e indique el ID del entorno, el número de Commerce Scale Units y las regiones del centro de datos deseadas. La solicitud se completará dentro de los cinco días hábiles. Si no necesita más de 2 Commerce Scale Units por entorno, no necesita crear una solicitud de soporte. 
3. Debe tener permisos de Propietario de proyecto en Lifecycle Services antes de poder inicializar Commerce Scale Unit.
4. Asegúrese de que las claves de configuración de la licencia comercial estén habilitadas en su entorno. Para más información, vea [Informe de códigos de licencia y claves de configuración](../sysadmin/license-codes-configuration-keys-report.md). Debe tener las siguientes teclas activadas para usar Commerce Scale Unit.

    - RetailBasic
    - RetaileCommerce: si tiene previsto utilizar el comercio electrónico para Dynamics 365 Commerce.
    - RetailGiftCard: si planea usar tarjetas de regalo.
    - RetailInvent: si planea usar el inventario.
    - RetailModernPos: si planea utilizar el punto de venta (POS).
    - RetailReplenishment - Si planea usar replenishments.
    - RetailScheduler
    - RetailStores: si planea usar PDV.


## <a name="region-availability"></a>Disponibilidad en la región
Commerce Scale Unit está disponible para su implementación en las siguientes regiones.

| Ubicación mundial | Región              | Disponibilidad        |
|-----------------|---------------------|---------------------|
| AMÉRICAS        | Este de EE. UU.             | Disponibilidad general |
| AMÉRICAS        | Este de EE. UU. 2           | Disponibilidad general |
| AMÉRICAS        | Centro y norte de EE. UU.    | Disponibilidad general |
| AMÉRICAS        | Centro y sur de EE. UU.    | Disponibilidad general |
| AMÉRICAS        | Centro de EE. UU.          | Disponibilidad general |
| AMÉRICAS        | Oeste de EE. UU.             | Disponibilidad general |
| AMÉRICAS        | Oeste de EE. UU. 2           | Disponibilidad general |
| AMÉRICAS        | Canadá central      | Capacidad limitada    |
| AMÉRICAS        | Este de Canadá         | Capacidad limitada    |
| AMÉRICAS        | Centro y oeste de EE. UU.     | Capacidad limitada    |
| APAC            | Este de Australia      | Disponibilidad general |
| APAC            | Sudeste Asiático      | Disponibilidad general |
| APAC            | Este de Japón          | Disponibilidad general |
| APAC            | Oeste de Japón          | Disponibilidad general |
| APAC            | Sudeste de Australia | Capacidad limitada    |
| APAC            | Este de Asia           | Capacidad limitada    |
| APAC            | Sur de la india         | Capacidad limitada    |
| APAC            | Centro de la India       | Capacidad limitada    |
| EMEA            | Europa Occidental         | Disponibilidad general |
| EMEA            | Norte de Europa        | Disponibilidad general |
| EMEA            | Sur del Reino Unido            | Capacidad limitada    |
| EMEA            | Oeste del Reino Unido             | Capacidad limitada    |

La capacidad de implementación en las regiones de capacidad limitada está extremadamente restringida. Las solicitudes de implementación se evalúan caso por caso. Si tiene una necesidad comercial apremiante para la implementación en regiones con capacidad limitada, puede presentar una solicitud de soporte para agregarlo a la lista de espera.

![Mapa que muestra la disponibilidad de la región.](media/Commerce-Scale-Unit-Region-Availability.png "Mapa que muestra la disponibilidad de la región")

## <a name="initialize-commerce-scale-unit-as-part-of-a-new-environment-deployment"></a>Inicialice Commerce Scale Unit como parte de una implementación de entorno nuevo

Por favor, asegúrese de que la sede esté disponible. Esto es necesario para registrar la unidad de báscula en la sede durante el proceso de inicialización. No se recomienda inicializar una unidad de báscula cuando la sede está en servicio, ya que puede no estar disponible durante su proceso de servicio.

1. Asegúrese de que el entorno de la sede esté disponible y no en [Modo de mantenimiento](../sysadmin/maintenance-mode.md).
2. En LCS, en la página de detalles del entorno, seleccione **Características del entorno \> Comercio**.
3. En la página de implementación de la configuración de Commerce, seleccione **Inicializar**.
4. Seleccione la versión de Commerce Scale Unit para inicializar.
5. Seleccione una región en la que inicializar Commerce Scale Unit.

## <a name="configure-channels-to-use-commerce-scale-unit"></a>Configurar canales para usar Commerce Scale Unit

Después de implementar Commerce Scale Unit, debe asegurarse de que sus canales estén configurados para usar la base de datos. 

Para configurar sus canales para usar la base de datos de Commerce Scale Unit, siga estos pasos.

1. En la sede central de Commerce, vaya a **Retail y Commerce \> Configuración de sede central \> Programador de Commerce \> Base de datos de canal**.
1. En el panel izquierdo, seleccione una base de datos de canal.
1. En la ficha desplegable **Canal minorista**, seleccione **Agregar** y luego seleccione su canal minorista en la lista desplegable.
1. Seleccione **Agregar** y luego seleccione su canal en línea en la lista desplegable. 

Cuando haya terminado, vaya **Retail y Commerce \> TI de Retail y Commerce \> Programación distribución** y ejecute el trabajo 9999.

> [!NOTE] 
> El trabajo 9999 sincroniza todos los productos y clientes nuevos con Commerce Scale Unit. El proceso puede tardar mucho tiempo. Si el canal debe estar disponible solo para la configuración del creador de sitios de comercio electrónico, puede ejecutar el trabajo 1070 en lugar del trabajo 9999.

### <a name="database-refresh-and-commerce-scale-units"></a>Actualización de la base de datos y Commerce Scale Units

Antes de comenzar, asegúrese de estar familiarizado con [Pasos para completar después de una actualización de la base de datos para entornos que usan la funcionalidad de Commerce](../database/database-refresh.md).

Los registros de la base de datos del canal de la unidad de escala (en el formulario de la base de datos del canal) no se pueden mover entre entornos como parte de la actualización de la base de datos. Esto se debe a que los registros representan una configuración específica del entorno.

Después de actualizar la base de datos, puede volver a generar el registro de la base de datos del canal de la unidad de báscula emitiendo una nueva implementación de su unidad de báscula en LCS. Cualquier operación de implementación o mantenimiento en la unidad de báscula intentará registrar la unidad de báscula en la sede, si se detecta que falta el registro.

Puede volver a implementar la unidad de escala, sin cambiar ningún componente, seleccionando implementar la misma versión en la que ya se encuentra su unidad de escala. Esto se puede hacer en LCS mediante los siguientes pasos:

1. En LCS, en la página de detalles del entorno, seleccione **Características del entorno \> Retail**.
2. En la página de configuración de la implementación, seleccione la unidad de escala que desea volver a implementar.
3. En el menú de operación de la unidad de báscula, seleccione **Actualizar**.
4. En el control deslizante, en el menú desplegable para **Seleccionar versión**, elige la opción **Especificar una versión**.
5. En el cuadro de texto debajo de **Especificar una versión**, escriba la versión que se muestra para su unidad de escala, que se muestra junto a la etiqueta **Versión actual**.
6. Haga clic en el botón **Actualizar**.

No es necesario seleccionar **Actualizar extensiones**, incluso si ha aplicado extensiones anteriormente, ya que el último paquete de extensión aplicado a la unidad de escala se selecciona automáticamente al actualizar una unidad de escala.

Si tiene varias unidades de escala, debe realizar la operación anterior para cada unidad de escala. Puede realizar estas operaciones en paralelo, si lo desea.

## <a name="deploy-additional-commerce-scale-units-optional"></a>Implementar Commerce Scale Units adicionales (opcional)

Una vez que haya inicializado Commerce Scale Unit, puede implementar automáticamente una segunda unidad de escala si su licencia le permite hacerlo. Para implementar más de dos Scale Units, debe crear una solicitud de soporte. En la solicitud de soporte, indique la cantidad de Commerce Scale Unit que necesita, el nombre del entorno y las regiones deseadas. Para obtener más información acerca de las licencias, consulte [Guía de licencias de Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409). 

Para cada Commerce Scale Unit que implemente, le recomendamos que cree un grupo de base de datos de canal independiente siguiendo estos pasos.

1. En la oficina central de Commerce, vaya a **Retail y Commerce > Retail Headquarters > Configuración Programador de Retail > Grupo de bases de datos de canal**.
2. Crear un nuevo grupo de bases de datos de canales.
3. Vaya a **Retail y Commerce > Retail Headquarters > Configuración de Programador de tareas Retail > Base de datos de canal** y seleccione la base de datos del canal que corresponde a la Commerce Scale Unit recién creada.
4. Seleccione **Editar** y seleccione el nuevo grupo de base de datos de canales.
5. Seleccione **Guardar**.
6. Seleccione **Ejecutar sincronización de datos completa** para la base de datos del canal seleccionado.

## <a name="additional-considerations-if-you-initialize-cloud-hosted-commerce-channel-components-in-an-existing-environment"></a>Consideraciones adicionales si inicializa componentes de canales de comercio alojados en la nube en un entorno existente

Si ya está utilizando componentes de canales de comercio alojados en la nube en un entorno, la inicialización de Commerce Scale Unit ayudará a reducir el tiempo de inactividad cuando se actualicen esos componentes. Se requiere una planificación adicional antes de la inicialización de Commerce Scale Unit.

Cuando inicializa su primera Commerce Scale Unit Commerce en un entorno que usa componentes de canal de Commerce alojados en la nube, el proceso de inicialización migrará sus canales asociados a los componentes de canal alojados en la nube a la primera unidad de escala. Los canales asociados con las unidades Store Scale no se ven afectados.

El proceso de migración es transparente para los canales. Una vez iniciada la inicialización de la unidad de báscula, se realizan automáticamente las siguientes operaciones:

1. Se creará una nueva Commerce Scale Unit y se asociará con el entorno.
2. Commerce Scale Unit se registrará como Base de Datos del Canal disponible en la sede.
3. Todos los canales asignados a la la base de datos de canal **predeterminada** en la sede se actualizará para mapear a la nueva Commerce Scale Unit.
4. Se realizará una sincronización completa de datos de Commerce Data Exchange (CDX) para llevar los datos del canal a la nueva unidad de escala.

**Planificación y prueba para la inicialización de la unidad de escala de comercio** Como regla general, al inicializar Commerce Scale Unit, debe planificar una ventana de tiempo de inactividad de cinco horas para las operaciones de la tienda, así como para cualquier operación del canal de comercio electrónico que use Retail Server o Cloud Point of Sale.

1. Realice una actualización de la base de datos desde su entorno de producción a un entorno UAT de espacio aislado. 
2. Inicialice Commerce Scale Unit en el entorno de UAT de espacio aislado. 
3. Tenga en cuenta el tiempo de inicialización para completar la Commerce Scale Unit. Esto será comparable al tiempo que toma esta operación en su entorno de producción, durante el cual las operaciones de la tienda y las operaciones de comercio electrónico no estarán disponibles.

Debe realizar los siguientes pasos adicionales antes de inicializar Commerce Scale Unit.

- **Cerrar todos los turnos de POS** - Después de la migración, los usuarios de POS no podrán cerrar ningún turno que estuviera activo durante el proceso de migración.
- **Valide que todos los trabajos P se hayan completado con éxito** - Se recomienda que los trabajos P para sincronizar las transacciones pendientes se hayan completado antes de que se inicialice la CSU.
- **Cerrar sesión en todos los dispositivos POS** - Las operaciones de POS no se admiten durante la migración.
- **Retirar y anular todas las transacciones suspendidas en POS** - Las transacciones suspendidas no se conservan como parte de la inicialización.

> [!IMPORTANT]
> Como parte de la inicialización de Commerce Scale Unit, las transacciones suspendidas anteriores se perderán y no se podrán recuperar. 

Esto es lo que ocurre durante el período de inicialización:

- Los canales de comercio alojados en la nube no funcionarán, a menos que active la capacidad de POS fuera de línea.
- Los dispositivos POS con la capacidad fuera de línea activada tendrán una funcionalidad reducida.
- Cualquier cliente de comercio electrónico que dependa de Retail Server se verá interrumpido.
- Los canales alojados en Commerce Scale Units (autohospedados) no se verán afectados.
- La funcionalidad de la oficina central no se ve afectada.

Esto es lo que ocurre después de que se completa la inicialización:

- El estado de activación del dispositivo de todos los dispositivos POS activados se conserva, lo que significa que los dispositivos no tendrán que reactivarse.
- Las instancias de estaciones de hardware independientes seguirán funcionando.
- Los informes del lado del canal POS se restablecerán y no mostrarán datos anteriores a la inicialización.
- La operación Mostrar diario también se restablecerá y no mostrará datos anteriores a la inicialización.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
