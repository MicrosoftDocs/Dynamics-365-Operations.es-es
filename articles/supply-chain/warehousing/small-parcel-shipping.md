---
title: Envío de paquetes pequeños
description: Este tema proporciona información acerca de la función de envío de paquetes pequeños (SPS). Esta característica permite a Microsoft Dynamics 365 Supply Chain Management enviar detalles sobre un contenedor empaquetado al transportista y luego recibir una etiqueta de envío, tarifa de envío y número de seguimiento de ese transportista.
author: Mirzaab
manager: tfehr
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 37f07139853c30da25c067a3d736b4b9bf4eb361
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501183"
---
# <a name="small-parcel-shipping"></a>Envío de paquetes pequeños

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La función de envío de paquetes pequeños (SPS) permite a Microsoft Dynamics 365 Supply Chain Management interactuar directamente con los transportistas proporcionando un marco para la comunicación a través de las API del transportista. Esta funcionalidad es útil cuando envía pedidos de venta individuales a través de transportistas comerciales en lugar de utilizar el envío con contenedores o el envío inferior a clases de camión (LTL).

La función SPS interactúa con su transportista a través de un *motor de tarifas* dedicado. Su organización debe desarrollar este motor de tarifas en colaboración con su operador o servicio del centro de operador. El motor de tarifas permite a Supply Chain Management enviar detalles sobre un contenedor empaquetado a su transportista, y luego recibir una etiqueta de envío, tarifa de envío y número de seguimiento de ese transportista.

La tarifa de envío que se devuelve se agrega al pedido de venta asociado como cargos varios. La etiqueta de envío que se devuelve puede entonces imprimirse automáticamente mediante una impresora de lenguaje de programación Zebra (ZPL) y aplicarse al envío. El transportista escaneará esta etiqueta de envío cuando recoja los paquetes en su almacén.

## <a name="prepare-your-system-to-support-sps"></a>Preparar el sistema para admitir SPS

Para poder empezar a usar la funcionalidad SPS, debe activar la característica SPS en la administración de funciones, agregar su motor de tarifas y configurar los módulos **Administración de transporte** y **Administración de características** para admitirla.

### <a name="turn-on-the-sps-feature"></a>Activar la característica SPS

Antes de poder usar la característica SPS, debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo**: *Administración de transporte*
- **Nombre de característica**: *Envío de paquetes pequeños*

### <a name="deploy-and-set-up-rate-engines"></a>Implementar y configurar motores de tarifas

Supply Chain Management no incluye motores de tarifas. Debe obtener o crear los motores de tarifas que necesite, y luego agregarlos a su sistema. Sin embargo, Microsoft proporciona un motor de tarifas de demostración que puede utilizar para realizar pruebas.

#### <a name="download-and-deploy-the-demo-rate-engine"></a>Descargar e implementar el motor de tarifas de demostración

Siga estos pasos para obtener el motor de tarifas de demostración.

1. En GitHub, descargue la [ biblioteca de vínculos dinámicos (DLL) para el motor de tarifas de demostración](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).
1. En su servidor de Supply Chain Management, guarde la DLL en la carpeta **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.

#### <a name="create-and-deploy-functional-rate-engines"></a>Crear e implementar motores de tarifas funcionales

Para obtener información sobre cómo crear e implementar motores de tarifas funcionales para que se puedan usar en un entorno de producción o de prueba, consulte los siguientes temas:

- [Crear un nuevo motor de administración de transporte](../transportation/create-new-transportation-management-engine.md)
- [Configurar motores de administración de transporte](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

Para obtener más información sobre cómo crear un motor de tarifas SPS, consulte la siguiente entrada de blog: [Envío de paquetes pequeños: cómo aprovechar la funcionalidad de envío de paquetes pequeños en Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a>Configurar un motor de tarifas en Supply Chain Management

Una vez que haya creado e implementado un motor de tarifas para SPS, siga estos pasos para configurarlo.

1. Vaya a **Administración de transporte \> Configuración \> Motores \> Motor de tarifas**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. Establezca los siguientes campos en la fila nueva.

    - **Motor de clasificación**: introduzca un nombre único para el motor de tarifas. Si está usando el motor de tarifas de demostración, introduzca *Motor de tarifas de demostración*.
    - **Nombre**: escriba una breve descripción del motor de tarifas. Si está usando el motor de tarifas de demostración, introduzca *Motor de tarifas de demostración*.
    - **Id. de metadatos de calificación**: seleccione la base que se debe usar para calcular su tarifa. Por ejemplo, su tarifa podría calcularse en función de la distancia. Si está utilizando el motor de tarifas de demostración, puede dejar este campo en blanco.
    - **Ensamblado de motores**: introduzca el nombre de archivo del paquete DLL ha que implementado. Si está usando el motor de tarifas de demostración, introduzca *TMSSmallParcelShippingEngine.dll*.
    - **Clase de motor**: escriba el nombre de la clase que se estableció para su motor de tarifas. Si está usando el motor de tarifas de demostración, introduzca *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.

## <a name="example-scenario"></a>Supuesto de ejemplo

Este escenario de ejemplo muestra cómo configurar y usar SPS después de haber preparado su sistema como se ha descrito anteriormente en este tema. Este escenario utiliza el motor de tarifas de demostración mencionado anteriormente.

### <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Para trabajar en este escenario mediante el uso de los registros y valores de demostración que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

### <a name="set-up-the-scenario"></a>Configuración el escenario

Para este escenario de ejemplo, debe tener un transportista de demostración, un grupo de transportistas, una directiva de embalaje y un perfil de embalaje. En las siguientes subsecciones se explica cómo preparar los registros necesarios para el escenario. En un escenario de producción, el proceso de configuración suele parecerse al proceso que se describe aquí. Sin embargo, establecerá valores diferentes.

#### <a name="set-up-carriers"></a>Configurar transportistas

Siga estos pasos para configurar un transportista.

1. Vaya a **Administración de transporte \> Configuración \> Transportistas \> Transportistas de envío**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar un transportista.
1. Establezca los siguientes valores en el encabezado:

    - **Transportista de envío:** *Transportista de demostración*
    - **Nombre:** *Transportista de demostración*
    - **Modo:** *Tierra*

1. En la ficha desplegable **Visión general**, establezca los valores siguientes:

    - **Activación de interfaces de transportistas de envío:** *Sí*
    - **Activar calificación de transportistas:** *Sí*

1. En la ficha desplegable **Servicios**, seleccione **Nuevo** para agregar un servicio a la cuadrícula.
1. Establezca los siguientes valores para el nuevo servicio:

    - **Servicio de transportista:** *Servicio de transportista de demostración*
    - **Nombre:** *Servicio de transportista de demostración*
    - **Método de transporte:** *Tierra*

    Introduzca valores arbitrarios para todos los demás campos, según sea necesario. (Cuando guarde el nuevo registro de transportista, se creará un nuevo modo de entrega y el campo **Modo de entrega** se establecerá automáticamente.)

1. En la ficha desplegable **Perfiles de clasificación**, seleccione **Nuevo** para crear un perfil de clasificación a la cuadrícula.
1. Establezca los siguientes valores para el nuevo perfil:

    - **Perfil de clasificación:** *Servicio de transportista de demostración*
    - **Nombre:** *Servicio de transportista de demostración*
    - **Motor de tarifas:** *Motor de tarifas de demostración*

    Introduzca valores arbitrarios para todos los demás campos, según sea necesario.

1. En el panel Acciones, seleccione **Guardar**.

Para obtener más información acerca de la configuración de transportista, consulte [Configuración de transportistas de envío](../transportation/tasks/set-up-shipping-carriers.md).

#### <a name="set-up-carrier-service-accounts"></a>Configurar cuentas de servicio de transportista

Siga estos pasos para configurar una cuenta de servicio de transportista.

1. Vaya a **Administración de transporte \> Configuración \> Clasificación \> Cuenta de servicio de transportista**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una cuenta de servicio de transportista.
1. Establezca los siguientes valores para la nueva cuenta:

    - **Transportista de envío:** *Transportista de demostración*
    - **Servicio de transportista:** *Servicio de transportista de demostración*
    - **Número de cuenta del cliente del transportista:** el número de cuenta del cliente del transportista que se usa para comprobar y autenticar la conexión con el transportista. Su transportista le proporcionará este valor. Si está usando el servicio de demostración, puede introducir un valor arbitrario.
    - **Sitio**: *6*
    - **Almacén**: *62*

    > [!NOTE]
    > A menudo, el valor del **Número de cuenta del cliente del transportista** es el único valor que se requiere para autenticar la conexión. Sin embargo, si su transportista requiere parámetros de autenticación adicionales, su organización debe personalizar esta página para agregar campos adicionales según corresponda.

#### <a name="set-up-a-container-packing-policy"></a>Configurar una directiva de embalaje de contenedores

Siga estos pasos para configurar una directiva de embalaje de contenedores.

1. Si aún no ha configurado una definición de impresora ZPL, utilice la aplicación Agente de ruta de documentos para configurarla. Para más información, consulte [Descripción general de la impresión de documentos](../../fin-ops-core/dev-itpro/analytics/print-documents.md) y temas relacionados.
1. Vaya a **Administración de almacenes \> Configurar \> Contenedores \> Directivas de embalaje en contenedores**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una directiva de embalaje en contenedores.
1. En el encabezado de la nueva directiva, establezca los siguientes valores:

    - **Directiva de embalaje en contenedores:** *Directiva de embalaje de demostración*
    - **Descripción:** una descripción de la directiva

1. En la ficha desplegable **Visión general**, establezca los valores siguientes:

    - **Almacén**: *62*
    - **Ubicación predeterminada para envío final:** *Baydoor*
    - **Unidad de peso:** *KG*
    - **Directiva de cierre del contenedor:** *Liberación automática*
    - **Directiva de lanzamiento de contenedores:** *Hacer que esté disponible en la ubicación de envío final*

1. En la ficha rápida **Manifiesto de contenedor**, puede establecer los siguientes valores:

    - **Manifiesto automático al cerrar el contenedor:** *Sí*
    - **Requisitos de manifiesto para contenedor:** *Administración de transporte*
    - **Imprimir contenido del contenedor:** *No*

1. En la ficha rápida **Impresión de etiquetas de transportista**, establezca los siguientes valores:

    - **Imprimir etiqueta de envío de contenedor:** *Siempre*
    - **Nombre de la impresora:** El nombre de la impresora ZPL que debe imprimir etiquetas de envío

#### <a name="set-up-a-packing-profile"></a>Configurar un perfil de embalaje

Para configurar un perfil de embalaje, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configurar \> Embalaje \> Perfiles de embalaje**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar un perfil de embalaje a la cuadrícula.
1. Establezca los siguientes valores para el nuevo perfil:

    - **Id. de perfil de embalaje:** *Perfil de embalaje de demostración*
    - **Descripción:** una descripción del perfil
    - **Directiva de embalaje en contenedores:** *Directiva de embalaje de demostración*
    - **Modo del id. de contenedor:** *Automático*
    - **Tipo de contenedor:** *Caja pequeña*

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a>Configurar un cliente para usar el transportista SPS

Siga estos pasos para configurar un cliente para que pueda utilizar el transportista que ha creado.

1. Vaya a **Clientes \> Clientes \> Todos los clientes**.
1. En la cuadrícula, busque y seleccione el cliente *US-027*.
1. En el panel de acciones, en la pestaña **General**, del grupo **Configuración**, seleccione **Cuentas de cliente de transportista**.
1. En la página **Cuentas de clientes de transportista**, en el Panel de acciones, seleccione **Nueva** para agregar una cuenta a la cuadrícula.
1. Establezca los siguientes valores para la nueva cuenta:

    - **Transportista de envío:** *Transportista de demostración*
    - **Número de cuenta del cliente del transportista:** *12345* (El valor no es importante para este escenario, pero se hará referencia a él en la siguiente sección).

### <a name="go-through-the-example-scenario"></a>Repase el escenario de ejemplo

Una vez que haya configurado todos los datos de muestra como se describe en la sección anterior, estará listo para repasar el escenario de ejemplo.

#### <a name="create-a-sales-order-and-process-the-work"></a>Crear un pedido de venta y procesar el trabajo

Siga los pasos para crear un pedido de ventas.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear un pedido de ventas.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca el campo **Cuenta de cliente**, en *US-027*.
1. Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre el nuevo pedido de ventas. En la ficha desplegable **Encabezado de pedidos de ventas**, establezca el campo **Número de cuenta del cliente del transportista** en el valor que seleccionó para este cliente anteriormente (*12345*).
1. En la sección **Líneas de pedido de ventas**, agregue una línea de ventas y establezca los siguientes valores para ella:

    - **Código de artículo:** *A0002*
    - **Cantidad:** *1*
    - **Sitio**: *6*
    - **Almacén**: *62*

1. Cambie a la vista **Encabezado**.
1. En la ficha desplegable **Entrega**, establezca los valores siguientes:

    - **Transportista de envío:** *Transportista de demostración*
    - **Servicio de transportista:** *Servicio de transportista de demostración*

1. Vuelva a la vista **Líneas**. Si se le solicita que actualice el modo de entrega de las líneas de venta, seleccione **Sí**.
1. En la sección **Líneas de pedido de ventas**, seleccione la línea de pedido que configuró anteriormente y, a continuación, **Inventario\> Reserva**.
1. En la página **Reserva**, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.
1. Cierre la página **Reserva** para volver al pedido de ventas.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    El trabajo se crea para mover artículos de la ubicación de picking a la estación de embalaje.

1. En la sección **Líneas de pedido de ventas**, seleccione **Almacén \> Detalles de envío**.
1. En la página **Detalles de envío**, anote el id. de envío. Lo necesitará cuando embale el paquete del envío en la estación de embalaje.
1. Cierre la página **Detalles de envío** para volver al pedido de ventas.
1. Anote el número del pedido de venta y luego vaya a **Gestión de almacenes \> Trabajo \> Todo el trabajo**.
1. Utilice el número del pedido de venta para buscar y seleccionar el trabajo que se creó para el pedido.
1. En el panel de acciones, en la pestaña **Trabajo**, seleccione **Trabajo completo**.
1. En la página **Finalización de trabajo**, en el campo **Id. de usuario**, seleccione un id. de usuario. Después, en el panel de acciones, seleccione **Validar trabajo**.
1. Si el trabajo pasa la validación, seleccione **Trabajo completado** en el panel de acciones.

    El trabajo se marca como completado para simular el movimiento de artículos a la estación de embalaje.

#### <a name="pack-the-shipment"></a>Embalar el envío

Para embalar el envío, siga estos pasos:

1. Vaya a **Gestión de almacenes \> Configuración \> Trabajador** y asegúrese de que su cuenta de usuario esté asociada a una cuenta de trabajador para la gestión de almacenes.
1. Vaya a **Gestión de almacenes \> Picking y puesta en contenedores \> Paquete**.
1. En el cuadro de diálogo **Seleccionar estación de embalaje**, establezca los siguientes valores:

    - **Sitio**: *6*
    - **Almacén**: *62*
    - **Ubicación:** *Paquete*
    - **Id. de perfil de embalaje:** *Perfil de embalaje de demostración*

1. Seleccione **Aceptar**.
1. Aparecerá la página **Paquete**. En un escenario de producción, un trabajador escaneará una matrícula o un id. de envío. Sin embargo, para este escenario, abra la página **Todos los envíos** y busque el número del envío que acaba de crear. A continuación, introduzca este valor en el campo **Matrícula de entidad de almacén o envío** de la página **Paquete**. También puede introducir el id. de envío que anotó anteriormente.
1. En el panel de acciones, seleccione **Nuevo contenedor**.
1. El cuadro de diálogo que aparece muestra detalles sobre el nuevo contenedor. Deje los valores predeterminados y luego seleccione **Aceptar**.
1. En la página **Paquete**, en la ficha desplegable **Embalaje de artículos**, en el campo **Identificador**, seleccione *A0002* para embalar ese artículo. El artículo se agrega al contenedor.
1. En el panel de acciones, seleccione **Contenedores para envío**.

    La página **Contenedores para envío** que aparece tiene una fila para el contenedor que acaba de crear. Sin embargo, el campo **Id. de manifiesto de contenedor** de esa fila está actualmente en blanco porque aún no ha recibido la etiqueta de envío y el número de seguimiento del transportista.

1. En el panel de acciones, seleccione **Cerrar contenedor**.
1. En el cuadro de diálogo **Cerrar contenedor**, establezca el campo **Peso bruto** en *1 kilogramo* y, a continuación, seleccione **Aceptar**.

    La etiqueta de envío ahora debería imprimirse en la impresora ZPL que seleccionó anteriormente. El resultado se parecerá al ejemplo siguiente.

    ![Ejemplo de etiqueta de envío](media/sps-label-example.png "Ejemplo de etiqueta de envío")

1. Observe que los valores **Id. de manifiesto de contenedor** y **Flete total** se han agregado como se recibieron del transportista.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]