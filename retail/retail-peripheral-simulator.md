---
title: Retail peripheral simulator
description: "Este tema describe la herramienta periférica de simulador que se ofrece Microsoft Dynamics 365 para las operaciones (al por menor."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
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

# <a name="retail-peripheral-simulator"></a>Retail peripheral simulator

Este tema describe la herramienta periférica de simulador que se ofrece Microsoft Dynamics 365 para las operaciones (al por menor.

<a name="overview"></a>Visión general
--------

Microsoft Dynamics 365 para las operaciones (el simulador periféricos Retail es una herramienta que ayuda a configuración, pruebas, y solucionan problemas los dispositivos periféricos que se usan en entornos de ventas al por menor. Puede usar el simulador periféricos para agilizar la prueba de periféricos al por menor, y para aislar problemas que son provocados por los controladores de dispositivo de instalación o que trabajan incorrectamente incorrectos. El simulador periféricos incluye un programa de escritorio que represente versiones virtuales de los dispositivos que Dynamics 365 para las operaciones (soporte al por menor. Una sección para cada dispositivo virtual muestra la interacción entre el dispositivo y el punto de venta al por menor (POS). También puede usarla para proporcionar la entrada que es válida para situaciones de Retail POS. El simulador periféricos admite la interacción entre Retail POS y los dispositivos virtuales siguientes:

-   ** La impresora – ** el simulador periféricos puede mostrar los recibos que se configuran para una impresora de Retail POS.
-   ** Visualización de línea ** – puede configurar una visualización de líneas virtual mostrar actividad en una pantalla de línea física.
-   ** Programa de lectura (MSR) de banda magnética ** – puede registrar eventos simulados de banda magnética a PDV de simulador periféricos.
-   ** ** Categoría – puede simular una caja registradora física.
-   ** Categoría de dos estrellas – configurando una segunda caja registradora en el simulador periféricos, puede simular las situaciones que implican un único registro de PDV que tiene dos activa cambia.
-   ** El escáner – ** el escáner de códigos de barras virtual que el simulador periféricos admite puede emitir eventos de análisis de código de barras.
-   ** La escala ** – una escala virtual permite simular la interacción de artículos pesados con Retail POS.
-   ** Traza de (PIN) del número de identificación personal ** – puede simular operaciones Terminal para ingreso de PIN. ** Nota: ** Debe implementar el soporte para ingreso de PIN físico a través de Connector de pago.
-   ** La captura de la firma – ** el simulador periféricos incluye un dispositivo de captura virtual de la firma que puede configurar para solicitar para las firmas que se requieren para algunas propuestas, como pagos de la cuenta de cliente.

Puede usar el simulador periféricos para simular los eventos de la cuña de teclado que se originan de un escáner de códigos de barras y MSR. Los soportes del simulador periféricos virtual se invoca y vincular específicamente para insertar los dispositivos al por menor de PDV OPDV ().

## <a name="key-scenarios"></a>Situaciones de clave ejemplo
### <a name="troubleshooting"></a>Solución de problemas

Puede usar el simulador periféricos para solucionar problemas la configuración del dispositivo. Si no tiene el simulador periféricos o un segundo dispositivo de la misma clase, puede resultar difícil determinar en las emisiones se originan. Sin embargo, cuando el simulador periféricos, puede configurar los dispositivos virtuales, y trabajar con las mismas rutas de acceso de códigos y lógica de negocios que se usan para los dispositivos físicos. Desde la perspectiva de simulador periféricos, la principal diferencia entre los dispositivos virtuales y dispositivos físicos es el objeto de servicio, o controlador de dispositivo. Para los dispositivos físicos, el objeto de servicio se proporciona por el fabricante del dispositivo. Por el contrario, para el simulador periféricos, los objetos de servicio se proporcionan como parte del simulador periféricos. Cuando está trabajando actualmente el simulador periféricos correctamente, si no funciona correctamente un dispositivo después de que el nombre de dispositivo en el perfil de hardware se cambie en el nombre de un dispositivo real, puede asumir que hay un problema con el objeto de servicio a que el proveedor ha proporcionado.

### <a name="training"></a>Formación

Puede usar el simulador periféricos para agregar un nivel real a la formación del cajero cuando una configuración de hardware física no está disponible. Cuando el simulador periféricos se incluye en escenarios de formación, el cajero puede interactuar más eficaz con PDV ofreciendo entrada como análisis del código de barras de producto y golpes fuertes de tarjeta regalo, y observando las recepciones se imprimen para una transacción específica.

### <a name="testing"></a>Prueba

Puede usar el simulador periféricos para probar los códigos de barras de producto, formatos de recepción, etc., sin tener que implementar el hardware físico en un entorno virtual. Dado que el hardware físico no es necesario, y no es necesario implementar un cliente de PDV en una emisora de hardware o un equipo físico, puede probar más rápidamente los cambios que se realizan en back office.

## <a name="set-up-the-peripheral-simulator"></a>Configurar el simulador periféricos
### <a name="set-up-a-hardware-profile"></a>Configurar un perfil de hardware

1.  Para configurar el simulador periféricos **, vaya al por menor y comercio ** &gt; ** canal configurar ** &gt; ** Configuración de PDV ** &gt; ** el PDV ** &gt; ** los perfiles de hardware **.
2.  Para crear un nuevo perfil, haga clic en ** ** nuevo.
3.  Especifique los valores en ** número del perfil y ** ** descripción ** campos.
4.  Use la tabla siguiente para configurar los dispositivos virtuales que deben someterse a prueba. A continuación se indica una explicación de las columnas en la tabla:
    -   ** El dispositivo ** – esta columna indique el nombre de la que se expanda para configurar el dispositivo.
    -   ** El tipo de dispositivo ** – esta columna da el valor seleccionado en el campo que se etiquetan con el nombre del dispositivo.
    -   ** El nombre del dispositivo ** – esta columna da el valor exacto que haya especificado para el nombre de dispositivo. ** Importante: ** Se requieren los nombres de dispositivo que se dan aquí, porque la emisora de hardware usa estos nombres específicos para dirigir los dispositivos. Si no usa estos nombres específicos, el dispositivo se no utilizable.

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

** Nota: ** No se requiere ninguna configuración específica en el perfil de hardware simular eventos de la cuña de teclado de escáner de códigos de barras y MSR.

### <a name="assign-the-hardware-profile-to-a-register"></a>Asignar el perfil de hardware a un registro

1.  Una vez creado el perfil de hardware **, vaya al por menor y comercio ** &gt; ** el canal configurar ** &gt; ** Configuración de PDV ** &gt; ** los registros **.
2.  En ** PDV ** registra la lista, haga clic en el vínculo de ** número de registro ** campo para el registro que debe usar el simulador periféricos.
3.  Haga clic en **Editar**.
4.  En ** los perfiles ** Idiomas, en ** perfil de hardware ** campo, seleccione el perfil de hardware que ha creado para periféricos virtuales.
5.  Click **Save**.

### <a name="synchronize-changes-to-the-channel-database"></a>Permite sincronizar los cambios en la base de datos del canal

1.  ** Va al por menor y comercio ** &gt; ** la TI al por menor ** &gt; ** programación de distribución **.
2.  Seleccione ** 1090 ** la programación de la distribución.
3.  Haga clic en ejecución ** ahora ** para sincronizar cambios a Retail POS.

Una vez que se sincronice los datos, el nuevo perfil de hardware y cambios en el registro están disponibles en la base de datos del canal.

## <a name="install-the-peripheral-simulator"></a>Instale el simulador periféricos
1.  ** Va al por menor y comercio ** &gt; ** el canal configurar ** &gt; ** Configuración de PDV ** &gt; ** el PDV ** &gt; ** los perfiles de hardware **.
2.  Haga clic ** descarga **, haga clic en PeripheralSimulator ** **. ** Nota: ** Debe desactivar los bloqueadores de elementos emergentes para poder descargar el simulador periféricos.
3.  Una vez que la descarga se complete, abra ** descargas ** la carpeta, y el doble clic VirtualPeripherals.msi ** ** para iniciar el instalador.
4.  Instale el simulador periféricos usando la configuración predeterminada.

Además del simulador periféricos, debe instalar los objetos de control de existencias Monroe Consulting Services. Si no, el simulador periféricos no funcionará correctamente. Para descargar los objetos de control de existencias, vaya< a http://monroecs.com/oposccos_current.htm>.

## <a name="using-the-peripheral-simulator"></a>Uso del simulador periféricos
Para iniciar el simulador, haga clic periféricos ** inicio ** en su equipo, tipo simulador ** periféricos al por menor ** y, a continuación seleccione la aplicación cuando aparece en los resultados de la búsqueda. Después del inicio del simulador periféricos, haga clic en un nombre de dispositivo para ver los dispositivos admitidos. Estos dispositivos se mostrarán como fichas en el lado izquierdo de la ventana. Para ver un dispositivo específico, haga clic en la ficha para dicho dispositivo.

### <a name="line-display-capabilities"></a>Capacidades de visualización de líneas

La pantalla de línea es el primer dispositivo que se muestra en el simulador periféricos. Cuando configuran en la pantalla de línea virtual, muestra los artículos de línea mientras se procesan en la transacción POS. Además de los artículos de línea, la visualización muestra el total que vence cuando una propuesta se selecciona en el sistema POS. También muestra el saldo que vence cuando se especifica una oferta pero un saldo queda pendiente en concepto de la transacción. Cuando PDV no se está utilizando, un mensaje se puede mostrar para indicar hasta que está cerrado. Debe configurar el mensaje en ** visualización de líneas ** la ficha desplegable en el perfil de hardware.

### <a name="cash-drawer-capabilities"></a>Capacidades de la caja registradora

La caja registradora es el segundo dispositivo que se muestra en el simulador periféricos. Cuando el perfil de hardware se configurado para usar las cajas registradoras virtuales, el sistema POS abre la caja registradora para el activo cambio en respuesta a operaciones del librador como declaraciones de forma y, de modo que el cajero pueda realizar el cambio o depositar efectivo durante transacciones estándar de las tiendas de ventas al contado. Las cajas registradoras virtuales tienen las etiquetas ** librador ** principal y secundario ** librador **. Estas etiquetas representan el cajón y el cajón 2 en el perfil de hardware, respectivamente. Cuando se ha cerrado un la caja, una imagen de una caja registradora cerrada se muestra, y el botón en la caja registradora cerrada se etiqueta ** librador ** abierto. Si hace clic en este botón, la imagen se reemplaza con una imagen de una caja registradora abierto para indicar que el cajón está abierto ahora. El botón en la caja registradora abierto se etiqueta ** librador ** cierre. Varias operaciones en el sistema POS pueden realizar la caja registradora para abrir. La mayoría de las operaciones no pueden continuar mientras que la caja registradora está abierto. Las excepciones son algunos procedimientos de final del día. Si el usuario POS recibe un mensaje de error que dice que una operación no puede realizarse mientras que la caja registradora está abierto, el usuario debe cerrar la caja registradora virtual o física a continuar. Si una caja registradora se marca como ** compartido ** en el perfil de hardware, el sistema no comprueba que el cajón esté cerrado antes de una operación. Los ingresos de la operación como de costumbre, incluso si la caja registradora está abierto. Este comportamiento admite escenarios donde las cajas registradoras se comparten entre socios de ventas, y en las aplicaciones asociars uno una caja registradora mientras que otro socio realizar tareas no relacionados en su propio dispositivo de Retail POS. Se abren los cambios realizados en la caja registradora no son evidentes hasta que se cierre el cambio actual y un nuevo cambio.

### <a name="msr-capabilities"></a>Capacidades MSR

El simulador periféricos ofrece un soporte robusto para las operaciones virtuales MSR trabajando en modo de OPDV o modo de la cuña de teclado. El modo de OPDV MSR requiere que se ha configurado en el perfil de hardware para funcionar como dispositivo de OPDV. El modo de la cuña de teclado sólo registrar eventos de datos de la cuña de teclado a Microsoft Windows. Además de diferencias en configuración, los modos de la cuña de OPDV de teclado y son diferentes de las siguientes formas:

-   El cliente de PDV habilita dispositivos de OPDV MSR para los escenarios de facturación específicos, como escenarios que permiten los datos de la banda magnética para fidelidad o la entrada de la tarjeta regalo.
-   En el modo de la cuña de teclado, el simulador periféricos registra datos de la cuña de teclado para el campo que está activo si se registra los datos. Este comportamiento se parece al comportamiento que aparece si los datos se especifica mediante un teclado. Para usar como MSR cuña de teclado, el usuario debe cambiar para vender Retail POS moderno (MPOS) para asegurarse de que los datos se recibirá en el campo correcto. Por lo tanto, puede configurar un retraso, de modo que el usuario obtenga tiempo para asegurarse de que los datos se registrarán en el campo correcto.

#### <a name="testing-gift-and-payment-card-swipes"></a>Golpes fuertes de regalo de la prueba y de la tarjeta de pago

MSR virtual que el simulador periféricos proporciona también permite configurar datos específicos MSR para probar las situaciones para el regalo y el pago para cardar golpes fuertes. Para crear una tarjeta, haga clic en el botón del signo más (** **+), y seleccione el tipo de tarjeta. Después especifique el número de tarjeta o siga los datos que se deben registrar en Retail POS, junto con el mes de caducidad y el año para la tarjeta que está definiendo. El valor seleccionado en ** tipo de tarjeta ** el campo es sólo una etiqueta que se puede asignar a una tarjeta. Esta etiqueta facilita la identificación de las tarjetas cuando se pasan de simulador periféricos. Puede seleccionar las tarjetas que se han configurado en el simulador periféricos mediante los botones de flecha izquierda (&lt;****) y la flecha derecha (&gt;****) Acerca de la imagen de tarjeta. Puede editar y eliminar las tarjetas mediante ** edición ** y ** Eliminar ** los botones junto al símbolo más (**+** botón).

### <a name="pin-pad"></a>Terminal para ingreso de PIN

Puede configurar el simulador Terminal para ingreso de PIN para simular un ingreso de PIN de OPDV. Cuando una transacción de (EFT) de transferencia electrónica de fondos se realiza en Retail POS y requiere entrada de PIN, la emisora de hardware denomina el dispositivo de PIN para solicitar para la entrada de PIN. Para trabajar, el ingreso de PIN en el simulador periféricos requiere el soporte de Connector de pago de EFT.

### <a name="printer"></a>Impresora

La impresora el periféricos virtual sólo muestra recepciones a medida que se imprimen desde Retail POS. Si una operación de impresión genera varios recibos, puede pasar a través de las recepciones.

#### <a name="configure-receipt-printing"></a>Configurar la impresión de recibos

1.  ** Va al por menor y comercio ** &gt; ** el canal configurar ** &gt; ** Configuración de PDV ** &gt; ** el PDV ** &gt; ** los perfiles de hardware **.
2.  Seleccione el perfil de hardware que ha creado para periféricos virtuales.
3.  ** Impresora En la ficha desplegable **, haga clic ** ** edición.
4.  En ** identificador de perfil de recibo ** campo, seleccione un perfil de recibo.
5.  Click **Save**.

### <a name="scale"></a>Escala

Cuando un producto de la escala se agrega a la transacción POS, y configura una escala, el sistema POS recupera el peso de la escala. Para la escala virtual y física, el producto o el peso debe ser especificado antes de que el producto se agregue a la transacción. Antes de agregar el artículo de la escala a la transacción, vaya a la escala en el simulador periféricos, y utilice el signo más (**+**) y los botones del signo menos (– ** **) de ajustar el peso la escala que debe informar. También puede especificar el peso deseada directamente en ** valor actual ** el campo. Puede ajustar las unidades de peso para la escala mediante el signo más (** **+), ** edición **, y ** Eliminar ** los botones. De esta manera, las unidades se pueden especificar en función de los productos que se pesan o la configuración regional donde se usa la escala.

#### <a name="configure-a-scale-product"></a>Configurar un producto de la escala

1.  ** Va al por menor y ** ** el comercio ** &gt; ** los productos y las categorías ** &gt; ** los productos emitidos por categoría **.
2.  Abre el registro de producto.
3.  Seleccione el artículo para calcular el peso.
4.  En ** al por menor ** la ficha desplegable, establezca ** producto de la escala ** la opción de ** ningún ** ** a Sí **.

#### <a name="synchronize-changes-to-the-channel-database"></a>Permite sincronizar los cambios en la base de datos del canal

1.  ** Va al por menor y comercio ** &gt; ** la TI al por menor ** &gt; ** programación de distribución **.
2.  Seleccione ** 1040 ** la programación de la distribución.
3.  Haga clic en ejecución ** ahora ** para sincronizar cambios a Retail POS.

Una vez que se sincronice los datos, cuando un producto de la escala se agrega a la transacción POS, el sistema POS comprueba la escala de peso.

### <a name="signature-capture"></a>Captura de firma

El dispositivo de captura virtual de la firma solicita al usuario proporcionar una firma en la traza virtual de la captura de la firma cuando la propuesta se utiliza que requiera una firma. El usuario puede aceptar la firma para mostrarla en el sistema POS. El cajero puede entonces aceptar la firma. La firma se guarda junto con la propuesta y se sincroniza con la línea de back-office junto con otros datos de transacción.

#### <a name="set-up-a-tender-to-require-a-signature"></a>Configurar una oferta para solicitar una firma

1.  ** Van al por menor y comercio ** &gt; ** los canales ** &gt; ** comercios ** &gt; ** todas comercios **.
2.  Seleccione la tienda al por menor.
3.  Haga clic en **Editar**.
4.  Haga clic en ** ** configuración y, a continuación, en ** configuración ** la sección, haga clic ** métodos de pago **.
5.  Haga clic en **Editar**.
6.  Seleccione el método de pago que requiere una firma.
7.  En ** general ** Idiomas, en ** digitalizador de firmas ** establece **, utilice el dispositivo de digitalizador de firmas ** la opción ** Sí **.
8.  En ** cantidad mínima de la digitalizador de firmas ** el campo, especifique el importe mínimo que desencadena digitalizador de firmas.

#### <a name="synchronize-changes-to-the-channel-database"></a>Permite sincronizar los cambios en la base de datos del canal

1.  ** Va al por menor y comercio ** &gt; ** la TI al por menor ** &gt; ** programación de distribución **.
2.  Seleccione ** 1070 ** la programación de la distribución.
3.  Haga clic en ejecución ** ahora ** para sincronizar cambios a Retail POS.

Una vez que se sincronice los datos, cuando una propuesta se utiliza que requiere una firma, y el importe coincide con el umbral de la firma, los indicadores de PDV para una firma en el dispositivo de captura virtual de la firma.

## <a name="additional-configuration"></a>Configuración adicional
Puede editar el archivo de configuración de simulador periféricos más adecuadamente la dirección las situaciones que está probando. Puede encontrar el archivo de configuración en la carpeta c: Microsoft Dynamics 365\\70 VirtualPeripherals\\\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config\\de los archivos de\\programa (x86). El archivo de configuración define las unidades disponibles para probar en la escala, los tipos de tarjeta que están disponibles para pruebas, y los tipos de código de barras. Por ejemplo, modificando valores de texto en el archivo de configuración, puede agregar un nuevo tipo o unidad de medida de tarjeta que se pueden seleccionados en el tiempo de ejecución. Los nuevos valores aparecerán después de que se reinicie la aplicación.

## <a name="troubleshooting"></a>Solución de problemas
Las actividades para el simulador periféricos se registran en el simulador periféricos. Puede buscar el registro en la carpeta c: Microsoft Dynamics 365\\70 VirtualPeripherals\\\\Microsoft.Dynamics.Commerce.VirtualPeripherals.Client.exe.config\\de los archivos de\\programa (x86). En el simulador los problemas periféricos de los informes también el Registro de sucesos de Windows, al que puede obtener acceso en ** la aplicación y mantener registros ** &gt; ** Microsoft ** &gt; ** DynamicsAX **. Si los cambios realizados al perfil de hardware o a otras áreas no son evidentes cuando se usa MPOS o el simulador periféricos, compruebe los trabajos del programador de distribución que se sincronizaba los datos a la base de datos de canal. Si los cambios se sincronizan pero aún no son evidentes en Retail POS, reinicie el cliente de Retail POS. Los cambios en las cajas registradoras configuradas no son efectivos hasta que se cree un nuevo cambio. Por lo tanto, si realiza cambios en las cajas registradoras, asegúrese de que siempre cierre el cambio existente para probar la nueva configuración de la caja registradora. A veces, si el controlador de un proveedor está instalado después de los objetos de control de existencias Monroe Consulting Services, el controlador puede hacer los objetos de control de existencias para dejar de trabajar correctamente. En este caso, debe restablecer los objetos de control de existencias.

<a name="see-also"></a>Consulte también
--------

[Visión general al por menor] periféricos (retail-peripherals-overview.md)


