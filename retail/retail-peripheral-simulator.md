---
title: "Simulador periférico de Retail"
description: "Este tema describe la herramienta de simulador periférico que ofrece Microsoft Dynamics 365 for Operations - Retail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 266544
ms.assetid: 16f31e70-15fc-441e-9727-e6a31c3a48f5
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 42dc414ff2bb6359b47d89c3bd3c510e4258f816
ms.openlocfilehash: b2229466040351d8c2b9494b30b4c928651820b8
ms.lasthandoff: 03/31/2017


---

# <a name="retail-peripheral-simulator"></a>Simulador periférico de Retail

[!include[banner](includes/banner.md)]


Este tema describe la herramienta de simulador periférico que ofrece Microsoft Dynamics 365 for Operations - Retail.

<a name="overview"></a>Visión general
--------

El simulador periférico de Microsoft Dynamics 365 for Operations - Retail es una herramienta que ayuda a configurar, probar y solucionar los problemas de los dispositivos periféricos que se usan en entornos de ventas minoristas. Puede usar el simulador periférico para agilizar las pruebas de los periféricos de Retail y para aislar problemas que son provocados por configuraciones incorrectas o los controladores de dispositivos defectuosos. El simulador periférico incluye un programa de escritorio que incluye versiones virtuales de los dispositivos compatibles con Dynamics 365 for Operations - Retail. Hay una sección para cada dispositivo virtual que muestra la interacción entre el dispositivo y el punto de venta (PDV) minorista. También se puede usar para proporcionar datos que sean válidos para diversas situaciones de PDV. El simulador periférico admite la interacción entre los PDV y los dispositivos virtuales siguientes:

-   **Impresora**. El simulador periférico puede mostrar los recibos que se configuraron para una impresora de PDV.
-   **Visualización de línea**. Puede configurar una visualización de línea virtual para mostrar actividad en una pantalla de línea física.
-   **Lector de bandas magnéticas (MSR)**. Puede registrar eventos simulados de banda magnética para los PDV desde el simulador periférico.
-   **Caja**. Puede simular una caja registradora física.
-   **Caja 2**. Si configura una segunda caja registradora en el simulador periférico, puede simular las situaciones que incluyen un único registro de PDV que tiene dos turnos activos.
-   **Escáner**. El escáner de códigos de barras virtual que admite el simulador periférico admite emitir eventos de análisis de código de barras.
-   **Balanza**. Una balanza virtual que permite simular la interacción de artículos pesados con PDV.
-   **Termina para número de identificación personal (PIN)**. Puede simular operaciones de la terminal para ingreso de PIN. **Nota**. Debe implementar la compatibilidad para la terminal para ingreso de PIN físico a través del conector de pago.
-   **Captura de firma**. El simulador periférico incluye un dispositivo de captura virtual de firmas que puede configurar para solicitar las firmas que se requieren para algunas propuestas, como pagos de la cuenta de cliente.

Puede usar el simulador periférico para simular los eventos de un teclado en cuña que se originan desde un escáner de códigos de barras y MSR. El simulador periférico virtual admite concretamente dispositivos Object Linking y Embedding for Retail POS (OPDV).

## <a name="key-scenarios"></a>Situaciones clave
### <a name="troubleshooting"></a>Solución de problemas

Puede usar el simulador periférico para solucionar problemas de la configuración del dispositivo. Si no tiene el simulador periférico o un segundo dispositivo de la misma clase, puede resultar difícil determinar donde se originan los problemas. Sin embargo, con el simulador periférico, puede configurar los dispositivos virtuales y trabajar con las mismas rutas de acceso de código y lógica empresarial que se usan para los dispositivos físicos. Desde la perspectiva de simulador periférico, la principal diferencia entre los dispositivos virtuales y los dispositivos físicos es el objeto de servicio, o el controlador de dispositivos. Para los dispositivos físicos, el objeto de servicio lo proporciona el fabricante del dispositivo. Por el contrario, para el simulador periférico, los objetos de servicio forman parte del simulador periférico. Cuando el simulador periférico funciona correctamente, si un dispositivo no funciona bien después de cambiar el nombre del dispositivo en el perfil de hardware por el nombre de un dispositivo real, puede asumir que hay un problema con el objeto de servicio que proporcionó el proveedor.

### <a name="training"></a>Formación

Puede usar el simulador periférico para agregar un nivel real a la formación del cajero cuando una configuración de hardware física no está disponible. Cuando el simulador periférico se incluye en escenarios de formación, el cajero puede interactuar de forma más eficaz con PDV ofreciendo información como análisis del código de barras de productos y pases de tarjeta regalo y observando qué recibos se imprimen para una transacción específica.

### <a name="testing"></a>Prueba

Puede usar el simulador periférico para probar los códigos de barras de productos, formatos de recibo, etc., sin tener que implementar el hardware físico en un entorno virtual. Dado que el hardware físico no es necesario y no tiene que implementar un cliente de PDV en una estación de hardware o un equipo físico, puede probar más rápidamente los cambios que se realizan en la oficina administrativa.

## <a name="set-up-the-peripheral-simulator"></a>Configurar el simulador periférico
### <a name="set-up-a-hardware-profile"></a>Configurar un perfil de hardware

1.  Para configurar el simulador periférico, vaya a **Retail y Commerce** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Perfiles de PDV** &gt; **Perfiles de hardware**.
2.  Para crear un perfil nuevo, haga clic en **Nuevo**.
3.  Especifique valores en los campos **Número de perfil** y **Descripción**.
4.  Use la tabla siguiente para configurar los dispositivos virtuales que se deben probar. Aquí hay una explicación de las columnas en la tabla:
    -   **Dispositivo**. Esta columna indica el nombre de la ficha desplegable que se expanda para configurar el dispositivo.
    -   **Tipo de dispositivo**. Esta columna proporciona el valor seleccionado en el campo que se etiqueta con el nombre del dispositivo.
    -   **Nombre del dispositivo**. Esta columna proporciona el valor exacto que haya especificado para el nombre de dispositivo. **Importante**. Se requieren los nombres de dispositivo que se proporcionaron aquí porque la estación de hardware usa estos nombres específicos para ocuparse de los dispositivos. Si no usa estos nombres específicos, el dispositivo se podrá usar.

    | Dispositivo            | Tipo de dispositivo | Nombre del dispositivo              |
    |-------------------|-------------|--------------------------|
    | Impresora           | OPDV        | MockOPOSPrinter          |
    | Visualización de líneas      | OPDV        | MockOPOSLineDisplay      |
    | MSR               | OPDV        | MockOPOSMSR              |
    | Librador            | OPDV        | MockOPOSDrawer1          |
    | Drawer2           | OPDV        | MockOPOSDrawers          |
    | Escáner           | OPDV        | MockOPOSScanner          |
    | Escala             | OPDV        | MockOPOSScale            |
    | terminal para ingreso de PIN           | OPDV        | MockOPOSPinPad           |
    | Captura de firma | OPDV        | MockOPOSSignatureCapture |

**Nota**. No se requiere ninguna configuración específica en el perfil de hardware para simular eventos de la cuña de teclado desde el escáner de códigos de barras y MSR.

### <a name="assign-the-hardware-profile-to-a-register"></a>Asignar el perfil de hardware a un registro

1.  Una vez creado el perfil de hardware, vaya a **Retail y Commerce** &gt; **Configuración de canales** &gt; **Configuración de PDV** &gt; **Registros**.
2.  En la lista **Registros de PDV**, haga clic en el campo **Número de registro** para el registro que debe usar el simulador periférico.
3.  Haga clic en **Editar**.
4.  En la sección **Perfiles**, en el campo **Perfil de hardware**, seleccione el perfil de hardware que ha creado para periféricos virtuales.
5.  Haga clic en **Guardar**.

### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizar cambios en la base de datos del canal

1.  Vaya a **Retail y Commerce** &gt; **TI de Retail** &gt; **Programación de distribución**.
2.  Seleccione la programación de distribución **1090**.
3.  Haga clic **Ejecutar ahora** para sincronizar cambios en el PDV.

Una vez que se sincronicen los datos, el nuevo perfil de hardware y los cambios en el registro estarán disponibles en la base de datos del canal.

## <a name="install-the-peripheral-simulator"></a>Instalar el simulador periférico
1.  Vaya a **Retail y Commerce** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Perfiles de PDV** &gt; **Perfiles de hardware**.
2.  Haga clic en **Descargar** y en **PeripheralSimulator**. **Nota:** Debe desactivar los bloqueadores de elementos emergentes para poder descargar el simulador periférico.
3.  Una vez que la descarga se complete, abra la carpeta **Descargas** y haga doble clic en **VirtualPeripherals.msi** para iniciar el instalador.
4.  Instale el simulador periférico usando la configuración predeterminada.

Además del simulador periférico, debe instalar Common Control Objects desde Monroe Consulting Services. De lo contrario, el simulador periférico no funcionará correctamente. Para descargar Common Control Objects, vaya a <http://monroecs.com/oposccos_current.htm>.

## <a name="using-the-peripheral-simulator"></a>Usar el simulador periférico
Para iniciar el simulador periférico, haga en **Inicio** en su equipo, escriba **Simulador periférico de Retail** y, a continuación, seleccione la aplicación cuando aparece en los resultados de la búsqueda. Después iniciar el simulador periférico, haga clic en un nombre de dispositivo para ver los dispositivos admitidos. Estos dispositivos se mostrarán como fichas en el lado izquierdo de la ventana. Para ver un dispositivo específico, haga clic en la ficha para dicho dispositivo.

### <a name="line-display-capabilities"></a>Capacidades de visualización de líneas

La pantalla de línea es el primer dispositivo que se muestra en el simulador periférico. Cuando se configura la pantalla de línea virtual, muestra los artículos de línea mientras se analizan en la transacción de PDV. Además de los artículos de línea, la pantalla muestra el total que se debe cuando una se selecciona una forma de pago en el PDV. También muestra el saldo que vence cuando se especifica una forma de pago, pero un saldo queda pendiente en concepto de la transacción. Cuando no se usa el PDV, puede aparecer un mensaje para indicar que la caja registradora está cerrada. Debe configurar el mensaje en la ficha desplegable **Visualización de líneas** en el perfil de hardware.

### <a name="cash-drawer-capabilities"></a>Capacidades de la caja registradora

La caja registradora es el segundo dispositivo que se aparece en el simulador periférico. Cuando el perfil de hardware se configura para usar las cajas registradoras virtuales, el PDV abre la caja registradora para el turno activo en respuesta a las operaciones de la caja registradora como declaraciones de forma de pago, de forma que el cajero pueda cambiar o ingresar efectivo durante las transacciones estándar de pago al contado sin entrega a domicilio. Las cajas registradoras virtuales tienen las etiquetas **Caja registradora principal** y **Caja registradora secundaria**. Estas etiquetas representan la Caja registradora y la Caja registradora 2 en el perfil de hardware, respectivamente. Cuando se ha cerrado un la caja, aparece una imagen de una caja registradora cerrada y el botón en esta caja registradora cerrada indica **Abrir caja**. Si hace clic en este botón, la imagen se sustituye con una imagen de una caja registradora abierta para indicar que la caja está ahora abierta. El botón en la caja registradora abierta se indica **Cerrar caja**. Hay varias operaciones en el PDV que pueden hacer que la caja se abra. La mayoría de las operaciones no pueden realizarse mientras que la caja registradora está abierta. Las excepciones son algunos procedimientos de final del día. Si el usuario del PDV recibe un mensaje de error que dice que una operación no puede realizarse mientras que la caja registradora está abierta, el usuario debe cerrar la caja registradora virtual o física para continuar. Si una caja registradora se marca **Compartida** en el perfil de hardware, el sistema no comprueba que el cajón esté cerrado antes de una operación. La operación continúa como de costumbre, incluso si la caja registradora está abierta. Este comportamiento admite situaciones donde las cajas registradoras se comparten entre socios de ventas y donde un asociado usa una caja registradora mientras otro realiza tareas que no están relacionadas con esto en su propio dispositivo PDV. Los cambios realizados en la caja registradora no se identifican hasta que se cierra el turno actual y se abre uno nuevo.

### <a name="msr-capabilities"></a>Capacidades de MSR

El simulador periférico ofrece un soporte eficaz para las operaciones virtuales MSR cuando se trabaja en modo OPDV o en modo de cuña de teclado. Con el modo OPDV, MSR debe configurarse en el perfil de hardware para que funcione como dispositivo de OPDV. El modo de la cuña de teclado solo envía eventos de datos de la cuña de teclado a Microsoft Windows. Además de las diferencias de configuración, los modos OPDV y cuña de teclado son diferentes por lo siguiente:

-   El cliente de PDV habilita dispositivos MSR de OPDV para escenarios de facturación específicos, como situaciones que permiten datos por banda magnética con fines de fidelidad y pasar tarjetas de regalo.
-   En el modo de cuña de teclado, el simulador periférico envía datos de la cuña de teclado al campo que está activo cuando se envían los datos. Este comportamiento se asemeja al comportamiento que se produce si los datos se especifican mediante un teclado. Para usar MSR como cuña de teclado, el usuario debe cambiar a Retail Modern POS (MPOS) para asegurarse de que los datos se recibirán en el campo correcto. Por lo tanto, puede configurar un retraso para que el usuario tenga tiempo de asegurarse de que los datos se registrarán en el campo correcto.

#### <a name="testing-gift-and-payment-card-swipes"></a>Probar a pasar las tarjetas de regalo y de pago

El MSR virtual que proporciona el simulador periférico también permite configurar datos MSR específicos para probar situaciones de pasar tarjetas de regalo y de pago. Para crear una tarjeta, haga clic en el botón del signo más (**+**) y seleccione el tipo de tarjeta. Después especifique el número de tarjeta o siga los datos que se deben registrar en los PDV, junto con el mes de caducidad y el año para la tarjeta que está definiendo. El valor seleccionado en el campo **Tipo de tarjeta** es solo una etiqueta que se puede asignar a una tarjeta. Esta etiqueta facilita la identificación de las tarjetas cuando se pasan por el simulador periférico. Puede seleccionar las tarjetas que se han configurado en el simulador periférico mediante los botones de flecha izquierda (**&lt;**) y la flecha derecha (**&gt;**) sobre la imagen de la tarjeta. Puede editar y eliminar tarjetas mediante los botones **Edición** y **Eliminar** junto al botón del símbolo más (**+**).

### <a name="pin-pad"></a>Terminal para ingreso de PIN

Puede configurar el simulador del terminal para ingreso de PIN para simular terminal de ingreso de PIN de OPDV. Cuando una transacción de transferencia electrónica de fondos (EFT) se realiza en el PDV y requiere especificar el PIN, la estación de hardware llama al dispositivo del PIN para solicitar la especificación del PIN. Para trabajar, el terminal de ingreso de PIN en el simulador periférico requiere admitir el conector de pago de EFT.

### <a name="printer"></a>Impresora

La impresora el periféricos virtual solo muestra recibos a medida que se imprimen desde el PDV. Si una operación de impresión genera varios recibos, puede desplazarse por los recibos.

#### <a name="configure-receipt-printing"></a>Configurar la impresión de recibos

1.  Vaya a **Retail y Commerce** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Perfiles de PDV** &gt; **Perfiles de hardware**.
2.  Seleccione el perfil de hardware que ha creado para periféricos virtuales.
3.  En la ficha desplegable **Impresora**, haga clic en **Editar**.
4.  En el campo **Id. de perfil de recibo**, seleccione un perfil de recibo.
5.  Haga clic en **Guardar**.

### <a name="scale"></a>Escala

Cuando un producto de la balanza se agrega a la transacción de PDV y se configura una balanza, el PDV recupera el peso de la balanza. Para la balanza virtual y la física, el producto o el peso se debe especificar antes de que el producto se agregue a la transacción. Antes de agregar el artículo de la balanza a la transacción, vaya a la balanza en el simulador periférico y utilice los botones del signo más (**+**) y menos (**–**) para ajustar el peso que debe notificar la balanza. También puede especificar el peso deseada directamente en el campo **Valor actual**. Puede ajustar las unidades de peso para la escala mediante los botones de signo más (**+**), **Editar** y **Eliminar**. De esta manera, las unidades se pueden especificar en función de los productos que se pesan o la configuración regional donde se usa la balanza.

#### <a name="configure-a-scale-product"></a>Configurar un producto de la balanza

1.  Vaya a **Retail y** **Commerce** &gt; **Productos y categorías** &gt; **Productos emitidos por categoría**.
2.  Abra el registro de producto.
3.  Seleccione el producto que se va a pesar.
4.  En la ficha desplegable **Retail**, establezca la opción **Producto de la balanza** de **No** a **Sí**.

#### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizar cambios en la base de datos del canal

1.  Vaya a **Retail y Commerce** &gt; **TI de Retail** &gt; **Programación de distribución**.
2.  Seleccione la programación de distribución **1040**.
3.  Haga clic **Ejecutar ahora** para sincronizar cambios en el PDV.

Después de sincronizar los datos, cuando se agrega un producto de la balanza a la transacción de PDV, el PDV comprueba la balanza para el peso.

### <a name="signature-capture"></a>Captura de firma

El dispositivo de captura virtual de firma solicita al usuario que proporcione una firma en la captura de firma virtual cuando la forma de pago que se utiliza requiere una firma. El usuario puede aceptar la firma para mostrarla en el PDV. El cajero puede entonces aceptar la firma. La firma se guarda junto con la forma de pago y se sincroniza con la oficina administrativa junto con otros datos de la transacción.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Configurar una oferta para solicitar una firma

1.  Vaya a **Retail y Commerce** &gt; **Canales** &gt; **Tiendas** &gt; **Todas las tiendas minoristas**.
2.  Seleccione la tienda minorista.
3.  Haga clic en **Editar**.
4.  Haga clic en **Configuración** y, a continuación, la sección **Configuración**, haga clic en **Métodos de pago**.
5.  Haga clic en **Editar**.
6.  Seleccione el método de pago que requiera una firma.
7.  En la sección **General**, en **Captura de firma**, establezca la opción **Usar dispositivo de captura de firma** en **Sí**.
8.  En el campo **Importe mínimo de captura de firma**, indique el importe mínimo que debería desencadenar la captura de la firma.

#### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizar cambios en la base de datos del canal

1.  Vaya a **Retail y Commerce** &gt; **TI de Retail** &gt; **Programación de distribución**.
2.  Seleccione la programación de distribución **1070**.
3.  Haga clic **Ejecutar ahora** para sincronizar cambios en el PDV.

Una vez que se sincronicen los datos, cuando se utilice una forma de pago que requiera una firma y el importe coincida con el umbral de la firma, el PDV solicita una firma en el dispositivo de captura de firma virtual.

## <a name="additional-configuration"></a>Configuración adicional
Puede editar el archivo de configuración del simulador periférico para que se encargue mejor de los escenarios que esté probando. Puede encontrar el archivo de configuración en la carpeta C:\\Archivos de programa (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. El archivo de configuración define las unidades disponibles para probar en la balanza, los tipos de tarjeta que están disponibles para pruebas y los tipos de código de barras. Por ejemplo, modificando valores de texto en el archivo de configuración, puede agregar un nuevo tipo de tarjeta o unidad de medida que se pueden seleccionar en tiempo de ejecución. Los nuevos valores aparecerán después de que se reiniciar la aplicación.

## <a name="troubleshooting"></a>Solución de problemas
Las actividades para el simulador periférico se registran en el simulador periférico. Puede encontrar el registro en C:\\Archivos de programa (x86)\\Microsoft Dynamics 365\\70\\VirtualPeripherals\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config. El simulador periférico también notifica errores al registro de eventos de Windows, al que puede obtener acceso en **Registros de aplicación y servicios** &gt; **Microsoft** &gt; **DynamicsAX**. Si los cambios realizados al perfil de hardware o a otras áreas no se muestran cuando se usa MPOS o el simulador periférico, compruebe los trabajos del programador de distribución que usó para sincronizar los datos en la base de datos del canal. Si los cambios se sincronizaron pero aún no se muestran en el PDV, reinicie el cliente de PDV. Los cambios en las cajas registradoras configuradas no surtirán efecto hasta que se cree un nuevo turno. Por tanto, si realiza cambios en las cajas registradoras, asegúrese de que siempre cierre el turno existente para probar la nueva configuración de la caja registradora. A veces, si el controlador de un fabricante se instala después de Common Control Objects desde Monroe Consulting Services, el controlador puede hacer que Common Control Objects deje de funcionar correctamente. En este caso, debe reinstalar Common Control Objects.

<a name="see-also"></a>Consulte también
--------

[Descripción general de los periféricos de Retail](retail-peripherals-overview.md)




