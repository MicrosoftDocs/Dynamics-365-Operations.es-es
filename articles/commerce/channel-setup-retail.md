---
title: Configurar un canal comercial
description: En este artículo se describe cómo crear un nuevo canal comercial en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: eccbbff33ddf967b000940a8ea9910c34232431f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847741"
---
# <a name="set-up-a-retail-channel"></a>Configurar un canal comercial

[!include [banner](includes/banner.md)]

En este artículo se describe cómo crear un nuevo canal comercial en Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce admite varios canales comerciales. Estos canales de venta minorista incluyen tiendas en línea, centros de llamadas y tiendas minoristas (también conocidas como tiendas físicas). Cada canal de tienda puede tener sus propios métodos de pago, grupos de precios, registros de puntos de venta (PDV), cuentas de ingresos y gastos, o personal. Debe configurar todos estos elementos antes de crear una canal de tienda. 

Antes de crear un canal comercial, asegúrese de cumplir los [requisitos previos del canal](channels-prerequisites.md).

## <a name="create-and-configure-a-new-retail-channel"></a>Crear y configurar un nuevo canal comercial

1. En el panel de navegación, vaya a **Módulos \> Canales \> Tiendas \> Todas las tiendas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el campo **Nombre**, escriba un nombre para el nuevo canal.
1. En el campo **Número de tienda**, especifique un número de tienda único. El número puede ser alfanumérico, con un máximo de 10 caracteres.
1. En la lista desplegable **Entidad jurídica**, introduzca la entidad jurídica correspondiente.
1. En la lista desplegable **Almacén**, introduzca el almacén apropiado.
1. En el campo **Zona horaria de la tienda**, seleccione la zona horaria apropiada.
1. En la lista desplegable **Grupo de impuestos sobre las ventas**, seleccione un grupo de impuestos sobre las ventas apropiado para la tienda.
1. En el campo **Divisa**, seleccione la divisa apropiada.
1. En el campo **Libreta de direcciones de cliente**, especifique una libreta de direcciones válida.
1. En el campo **Cliente predeterminado**, especifique un cliente predeterminado válido.
1. En el campo **Perfil de funcionalidad**, seleccione un perfil de funcionalidad si corresponde.
1. En el campo **Perfil de notificación por correo electrónico**, proporcione un perfil de notificación de correo electrónico válido.
1. En el panel Acciones, seleccione **Guardar**.

La siguiente imagen muestra la creación de un nuevo canal comercial.

![Nuevo canal de comercial.](media/channel-setup-retail-1.png)

La siguiente imagen muestra un canal comercial de ejemplo.

![Ejemplo de canal comercial.](media/channel-setup-retail-2.png)

## <a name="other-settings"></a>Otras opciones de configuración

Hay muchas otras configuraciones opcionales que se pueden configurar en las secciones **Extracto/cierre** y **Varios**, en función de las necesidades de la tienda.

Consulte también [Diseños de pantalla para el punto de venta (PDV)](pos-screen-layouts.md) para obtener información sobre cómo configurar el diseño de pantalla predeterminado en la sección **Diseño de pantalla** y [Instalar y configurar Retail Hardware Station](retail-hardware-station-configuration-installation.md) para obtener información de configuración sobre la sección **Estaciones de hardware**.

En la siguiente imagen se muestra un ejemplo de configuración de instalación de canal comercial.

![Ejemplo de configuración de canal comercial.](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a>Configuración adicional de canal

Hay elementos adicionales que debe configurar para un canal que se pueden encontrar en el panel de acciones, en la sección **Configurar**.

Las tareas adicionales requeridas para la configuración del canal en línea incluyen: configuración de métodos de pago, declaración de efectivo, modos de entrega, cuenta de ingresos/gastos, secciones, asignación de grupo de cumplimiento y cajas fuertes.

En la imagen siguiente se muestran varias opciones adicionales de configuración de canales comerciales en la pestaña **Configurar**.

![Configurar canal.](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a>Configurar métodos de pago

Para configurar métodos de pago, siga los pasos siguientes para cada tipo de pago admitido en este canal.

1. En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Métodos de pago**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el panel de navegación, seleccione el método de pago deseado.
1. En la sección **General**, proporcione un **Nombre de la operación** y configure las otras opciones de configuración que desee.
1. Configure opciones de configuración adicionales según sea necesario para el tipo de pago.
1. En el panel Acciones, seleccione **Guardar**.

En la imagen siguiente se muestra un ejemplo de método de pago en efectivo.

![Ejemplo de métodos de pago.](media/channel-setup-retail-5.png)

La siguiente imagen muestra un ejemplo de un método de pago en efectivo y la configuración de la pestaña **Importe**.

![Ejemplo de configuración de método de pago para importes.](media/payment-methods-recount.png)

> [!NOTE]
> Los valores de la pestaña **Importe** se almacenan en caché en el servidor minorista y no surtirán efecto inmediatamente después de ejecutar los trabajos del programa de distribución. Es posible que deba reiniciar Cloud Scale Unit para aplicar inmediatamente estos valores para la prueba.

### <a name="set-up-cash-declaration"></a>Configurar declaración de efectivo

1. En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Declaración de efectivo**.
1. En el panel de acciones, seleccione **Nuevo** y, a continuación, cree todas las denominaciones de **Moneda** y **Nota** que sean aplicables.

En la imagen siguiente se muestra un ejemplo de declaración de efectivo.

![Configurar declaraciones de efectivo.](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a>Configurar modos de entrega

Para ver los modos de entrega configurados, seleccione **Modos de entrega** en la pestaña **Configurar** del panel de acciones.  

Para cambiar o agregar un modo de entrega, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Gestión de inventarios \> Modos de entrega**.
1. En el panel de acciones, seleccione **Nuevo** para crear un nuevo modo de entrega o seleccionar un modo existente.
1. En la sección **Canales comerciales**, seleccione **Agregar línea** para agregar el canal. Agregar canales utilizando nodos de organización en lugar de agregar cada canal individualmente puede simplificar la adición de canales.

En la imagen siguiente se muestra un ejemplo de mode de entrega.

![Configurar modos de entrega.](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a>Configurar una cuenta de ingresos y gastos

Para configurar una cuenta de ingresos y gastos siga estos pasos.

1. En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Cuenta de ingresos/gastos**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En **Nombre**, escriba un nombre.
1. En **Nombre de búsqueda**, escriba un nombre de búsqueda.
1. En **Tipo de cuenta**, especifique el tipo de cuenta.
1. Introduzca texto para **Línea de mensaje 1**, **Línea de mensaje 2**, **Texto de resguardo 1** y **Texto de resguardo 2** según sea necesario.
1. En **Registro**, introduzca la información de registro.
1. En el panel Acciones, seleccione **Guardar**.

La siguiente imagen muestra un ejemplo de cuenta de ingresos/gastos.

![Configurar una cuenta de ingresos/gastos.](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a>Configurar secciones

para configurar secciones, siga estos pasos.

1. En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, haga clic en **Secciones**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En **Numero de sección**, introduzca un número de sección.
1. En **Descripción**, escriba una descripción.
1. En **Tamaño de sección**, introduzca un tamaño de sección.
1. Establezca opciones de configuración adicionales para **General** y **Estadísticas de ventas** según sea necesario.
1. En el panel Acciones, seleccione **Guardar**.

### <a name="set-up-a-fulfillment-group-assignment"></a>Configurar una asignación de grupo de cumplimiento

Para configurar una asignación de grupo de cumplimiento, siga estos pasos.

1. En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Asignación de grupo de cumplimiento**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En la lista desplegable **Grupo de cumplimiento**, seleccione un grupo de cumplimiento.
1. En la lista desplegable **Descripción**, escriba una descripción.
1. En el panel Acciones, seleccione **Guardar**

La siguiente imagen muestra un ejemplo de configuración de asignación de grupo de cumplimiento.

![Configurar asignaciones de grupo de cumplimiento.](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a>Configurar cajas fuertes

para configurar cajas fuertes, siga estos pasos.

1. En el panel de acciones, seleccione la pestaña **Configurar** y, a continuación, seleccione **Cajas fuertes**.
1. En el panel de acciones, haga clic en **Nueva**.
1. Introduzca un nombre para la caja fuerte.
1. En el panel Acciones, seleccione **Guardar**.

### <a name="ensure-unique-transaction-ids"></a>Garantizar id. de transacción únicos

A partir de la versión 10.0.18 de Commerce, los id. de transacción generados para el punto de venta (PDV) son secuenciales e incluyen las siguientes partes:

- Una parte fija, que es una concatenación del id. de la tienda y el id. del terminal. 
- Una parte secuencial, que es una secuencia numérica. 

Específicamente, el formato es *{store}-{terminal}-{numbersequence}*. 

Debido a que los id. de transacción se pueden generar en modo fuera de línea y en línea, ha habido casos en que se han generado id. de transacción duplicados. La eliminación de id. de transacciones duplicadas requiere mucha corrección manual de datos. 

Con la versión 10.0.19 de Commerce, el formato de id. de transacción se ha actualizado para eliminar la parte secuencial y, en su lugar, utiliza un número de 13 dígitos generado calculando el tiempo en milisegundos desde 1970. Con este cambio, el nuevo formato de id. de transacción es *{store}-{terminal}-{millisecondsSince1970}*. Esta actualización hace que el id. de transacción no sea secuencial y garantiza que los id. de transacción sean siempre únicos. 

> [!NOTE]
> Los id. de transacción están destinados solo para uso interno del sistema, por lo que no es necesario que sean secuenciales. Sin embargo, muchos países requieren que los id. sean secuenciales.

La nueva función de formato de id. de transacción se puede habilitar desde el área de trabajo **Gestión de funciones**. 

Para habilitar el uso de nuevos id. de transacción, siga estos pasos:

1. En la sede de Commerce, vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.
1. Filtre por el módulo "Minorista y comercio".
1. Busque el nombre de la función **Habilitar nuevo id. de transacción para evitar id. de transacción duplicados**.
1. Seleccione la característica y, a continuación, en el panel de la derecha, seleccione **Habilitar ahora**.  
1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.
1. Ejecute los traajos **1070 Configuración de canal** y **1170 Registrador de tareas PDV** para sincronizar la función habilitada con las tiendas.
1. Después de que los cambios se hayan enviado a las tiendas, los terminales PDV deben cerrarse y volverse a abrir para usar el nuevo formato de id. de transacción. 

> [!NOTE]
> Una vez habilitada la nueva función de formato de id. de transacción, no podrá deshabilitar esta función. Si debe deshabilitarse, comuníquese con el soporte técnico de Commerce.

## <a name="additional-resources"></a>Recursos adicionales

[Información general de canales](channels-overview.md)

[Requisitos previos de configuración del canal](channels-prerequisites.md)

[Configurar un canal en línea](channel-setup-online.md)

[Configurar un canal de centro de llamadas](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
