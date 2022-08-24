---
title: Configurar la integración fiscal para canales de Commerce
description: En este artículo se proporcionan instrucciones para configurar la funcionalidad de integración fiscal para canales de Commerce.
author: EvgenyPopovMBS
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 9fd801395f2ba04c703734a1de7998d6a53b6462
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276142"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>Configurar la integración fiscal para canales de Commerce

[!include [banner](../includes/banner.md)]

En este artículo se proporcionan instrucciones para configurar la funcionalidad de integración fiscal para canales de Commerce. Para obtener más información acerca de la integración fiscal, consulte [Visión general de la integración fiscal para los canales de Commerce](fiscal-integration-for-retail-channel.md).

## <a name="enable-features-in-commerce-headquarters"></a>Habilitar características en la sede central de Commerce

Para habilitar características relacionadas con la funcionalidad de integración fiscal para los canales de Commerce, siga estos pasos.

1. En la sede de Commerce, vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.
1. Busque y habilite las siguientes características:

    - **Integración fiscal directa desde los registros de PDV** – Esta característica amplía el marco de integración fiscal al agregar la capacidad de crear conectores fiscales que se ejecutarán en el punto de venta (POS). Este tipo de conector se comunica con un dispositivo o servicio fiscal que proporciona una interfaz de programación de aplicaciones (API) HTTP y no requiere una máquina física dedicada en la tienda. Por ejemplo, esta funcionalidad permite la integración fiscal para dispositivos móviles sin necesidad de una estación de hardware compartida.
    - **Anulaciones de perfiles técnicos de integración fiscal** – Esta característica permite ampliar la configuración de la integración fiscal y agrega la capacidad de verificar los parámetros de conexión en la página de configuración de un registro POS. Cuando esta característica está habilitada, puede anular los parámetros de un perfil técnico.
    - **Estado de registro fiscal de los registros de PDV** – Cuando esta característica está habilitada, puede deshabilitar el proceso de registro fiscal para registros de PDV específicos. Si el registro fiscal está deshabilitado para un registro de PDV, las transacciones de venta no se pueden completar en ese registro.
    - **Copia de seguridad del almacenamiento de datos local** – Esta característica amplía las capacidades de control de errores del marco de integración fiscal. También permite la copia de seguridad automática de los datos del registro fiscal en caso de pérdida de datos, de modo que los datos en el almacenamiento local se restauran mientras se activa un dispositivo.

## <a name="set-up-commerce-parameters"></a>Configurar los parámetros de Commerce

Para configurar parámetros de Commerce, siga estos pasos.

1. En la página **Parámetros compartidos de Commerce**, en la pestaña **General**, establezca la opción **Habilitar integración fiscal** en **Sí**.
1. En la ficha **Secuencias numéricas**, defina el número de secuencias para las siguientes referencias:

    - Número de perfil técnico fiscal
    - Número de grupo del conector fiscal
    - Número de proceso de registro

1. En la página **Parámetros de Commerce** defina la secuencia numérica para el número de perfil funcional fiscal.

> [!NOTE]
> Las secuencias numéricas son opcionales. Los números de las entidades de integración fiscal se pueden generar desde secuencias numéricas o manualmente.

## <a name="set-up-a-fiscal-registration-process"></a>Configuración de un proceso de registro fiscal

El proceso de configurar la integración fiscal incluye las tareas globales siguientes:

- Configurar los conectores fiscales que representan los dispositivos o servicios fiscales que se usan para fines fiscales de registro, como impresoras fiscales.
- Configurar los proveedores de documentos que generan los documentos fiscales que se registrarán en dispositivos o servicios fiscales mediante conectores fiscales.
- Configurar el proceso de registro fiscal que define una secuencia de pasos de registro fiscal y los conectores fiscales y proveedores de documentos fiscales que se usan para cada paso.
- Asigne el proceso de registro fiscal a perfiles de funcionalidad de PDV.
- Asignar perfiles técnicos de conectores a los perfiles de hardware.
- Asignar perfiles técnicos de conectores a los perfiles de hardware PDV o de funcionalidad.

### <a name="upload-configurations-of-fiscal-document-providers"></a>Cargar las configuraciones de proveedores de documentos fiscales

Un proveedor de documentos fiscales es responsable de generar documentos fiscales que representan las transacciones y los eventos que se registran en el sistema PDV en un formato que también se usa para la interacción con un dispositivo o un servicio fiscal. Por ejemplo, un proveedor de documentos fiscales puede generar una representación de un recibo fiscal en un formato XML.

Para cargar las configuraciones de los proveedores de documentos fiscales, sigas estos pasos.

1. En Commerce Headquarters, vaya a a la página **Proveedores de documentos fiscales** (**Retail y Commerce \> Configuración de canal \> Integración fiscal \> Proveedores de documentos fiscales**).
1. Cargue una configuración XML para cada dispositivo o servicio que planee usar.

> [!TIP]
> Seleccionando **Ver**, puede ver todos los perfiles funcionales relacionados con el proveedor de documentos fiscales actual.

> [!NOTE]
> La asignación de datos se considera parte de un proveedor de documentos fiscales. Para configurar diferentes asignaciones de datos para el mismo conector (por ejemplo, normas de estado específicas), debe crear varios proveedores de documentos fiscales.

### <a name="upload-configurations-of-fiscal-connectors"></a>Subir configuraciones de conectores fiscales

Un conector fiscal es responsable de la comunicación con un dispositivo o un servicio fiscal. Por ejemplo, un conector fiscal puede enviar un recibo fiscal que un proveedor fiscal de documentos ha creado en un formato XML a una impresora fiscal. Para obtener más detalles sobre los componentes de integración fiscal, consulte [Proceso de registro fiscal y ejemplos fiscales de la integración de los dispositivos fiscalesy servicios](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

Para cargar las configuraciones de los conectores fiscales, sigas estos pasos.

1. En Commerce Headquarters, vaya a a la página **Conectores fiscales** (**Retail y Commerce \> Configuración de canal \> Integración fiscal \> Conectores fiscales**).
1. Cargue una configuración XML para cada dispositivo o servicio que planee usar para fines de integración fiscal.

> [!TIP]
> Seleccionando **Ver**, puede ver todos los perfiles funcionales y técnicos relacionados con el conector fiscal actual.

Para obtener ejemplos de configuraciones de conectores fiscales y proveedores de documentos fiscales, consulte [Ejemplos fiscales de integración en el SDK de Commerce](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-commerce-sdk).

### <a name="create-connector-functional-profiles"></a>Crear perfiles funcionales de conector

Para crear perfiles funcionales de conector, siga estos pasos.

1. En Commerce Headquarters, vaya a a la página **Perfiles funcionales de conectores** (**Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles funcioanles de conectores**).
1. Para cada combinación de un conector fiscal y de un proveedor de documentos fiscales que esté relacionado con este conector fiscal, cree un perfil funcional de conector con estos pasos:

    1. Seleccione un nombre de conector.
    1. Seleccione un proveedor de documentos.

#### <a name="change-data-mapping-parameters-in-a-connector-functional-profile"></a>Cambiar los parámetros de la asignación de los datos de un perfil funcional de conector

Puede cambiar los parámetros de la asignación de los datos de un perfil funcional de conector. La siguiente tabla proporciona algunos ejemplos de parámetros de asignación de datos en un perfil funcional de conector.

| Parámetro | Formato | Ejemplo |
|-----------|--------|---------|
| Configuración de índices de IVA | valor: VATrate | 1 : 2000, 2 : 1800 |
| Asignación de códigos de IVA | VATcode : valor | vat20 : 1, vat18 : 2 |
| Asignación de tipos de forma de pago | TenderType : valor | Cash : 1, Card : 2 |

Para restablecer los parámetros predeterminados que se definen en la configuración del proveedor de documentos fiscales, seleccione **Actualizar** en la página **Perfiles funcionales de conector**.

> [!NOTE]
> Los perfiles funcionales de conectores son específicos de la empresa. Si tiene previsto usar la misma combinación de un conector fiscal y de un proveedor de documentos fiscales para distintas empresas, debe crear un perfil funcional de conector para cada empresa.

### <a name="create-connector-technical-profiles"></a>Crear perfiles técnicos de conector

Para crear perfiles técnicos de conector, siga estos pasos.

1. En Commerce Headquarters, vaya a a la página **Perfiles técnicos de conectores** (**Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles técnicos de conectores**).
1. Cree un perfil técnico de conector para cada conector fiscal siguiendo estos pasos:

    1. Seleccione un nombre de conector.
    1. Seleccione un tipo de conector:

        - Para dispositivos o servicios que están conectados a una estación de hardware o presentes en la red local, seleccione **Local**.
        - Para servicios externos, seleccione **Externo**.
        - Para conectores internos en Commerce Runtime (CRT), seleccione **Interno**. 

    1. Seleccione una ubicación de conector:

        - Si el conector está ubicado en la estación de hardware, seleccione **estación de hardware**.
        - Si el conector está ubicado en el registro POS, seleccione **Registrarse**.

Los parámetros de las pestañas **Dispositivo** y **Configuración** de un perfil técnico de conector se pueden modificar. Para restablecer los parámetros predeterminados que se definen en la configuración del conector fiscal, seleccione **Actualizar**. Mientras una nueva versión de una configuración de XML se carga, recibirá un mensaje que indica que el conector fiscal o el proveedor de documentos fiscales actual ya se está utilizando. Este procedimiento no anula los cambios manuales que se realizaron previamente en perfiles funcionales de conector y en perfiles técnicos de conector. Para aplicar el conjunto de parámetros predeterminado desde una configuración, seleccione **Actualizar** en la página **Perfiles funcionales del conector** y la página **Perfiles técnicos del conector**.

Si debe configurar parámetros específicos para una caja registradora o tienda POS individual, siga estos pasos.

1. Seleccione el elemento de menú **Reemplazar**.
1. En la página **Reemplazar**, cree un nuevo registro.
1. Seleccione una tienda o un registro POS. Puede anular los parámetros del perfil técnico seleccionado para un registro POS individual o todos los registros POS en una tienda individual.
1. Sobre la pestaña **Dispositivo**, ingrese los parámetros para el registro o tienda POS seleccionado.

### <a name="create-fiscal-connector-groups"></a>Cree grupos de conectores fiscales

Un grupo de conectores fiscales combina perfiles funcionales de conectores fiscales que realizan idénticas funciones y se usan en la misma etapa del proceso de registro fiscal. Por ejemplo, si varios modelos de impresora fiscales se pueden usar en una tienda, los conectores fiscales para las impresoras fiscales se pueden combinar en un grupo fiscal de conectores.

Para crear un grupo de conectores fiscales, siga estos pasos.

1. Vaya a a la página **Grupo fiscal de conectores** (**Retail y Commerce \> Configuración del canal \> Integración fiscal \> Grupos de conectores fiscales**).
1. Cree un nuevo grupo de conectores fiscales.
1. Agregue perfiles funcionales el grupo de conectores. En la pestaña **Perfiles funcionales**, seleccione **Agregar** y seleccione un número del perfil. Cada conector fiscal de un grupo de conectores solo puede tener un perfil funcional.
1. Para suspender el uso del perfil funcional, establezca la opción **Deshabilitar** en **Sí**. Este cambio afecta al grupo de conectores actuales únicamente. Puede continuar usando el mismo perfil funcional en otros grupos de conectores.

### <a name="create-a-fiscal-registration-process"></a>Crear un proceso de registro fiscal

Un proceso de registro fiscal se define por la secuencia de los pasos de registro y el grupo de conectores utilizados en cada paso.

Para crear un proceso de registro fiscal, siga estos pasos.

1. En Commerce Headquarters, vaya a a la página **Proceso de registro fiscal** (**Retail y Commerce \> Configuración de canal \> Integración fiscal \> Procesos de registro fiscal**).
1. Cree un nuevo registro para cada proceso único de registro fiscal.
1. Agregue pasos de registro al proceso siguiendo estos pasos:

    1. Seleccione **Agregar**.
    1. Seleccione un tipo de conector fiscal.
    1. En el campo **Número de grupo** , seleccione un grupo de conectores fiscales adecuado.

### <a name="assign-entities-of-the-fiscal-registration-process-to-pos-profiles"></a>Asigne entidades del proceso de registro fiscal a perfiles PDV

Para asignar entidades del proceso de registro fiscal a perfiles PDV, siga estos pasos.

1. En Commerce headquarters, vaya a la página **Perfiles de funcionalidad de PDV** (**Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad**). 
1. Asigne el proceso de registro fiscal a un perfil de funcionalidad de PDV.
1. Seleccione **Editar** y, a continuación, en la pestaña **Proceso de registro fiscal** , en el campo **Número de proceso** , seleccione un proceso.
1. En la pestaña **Servicios fiscales**, seleccione los perfiles técnicos del conector con la ubicación del conector **Registrarse**.
1. Vaya a la página **Perfil de hardware de PDV** (**Retail y Commerce \> Configuración del canal \> Configuración del PDV \> Perfiles del PDV \> Perfiles de hardware**).
1. Asignar perfiles técnicos de conectores a un perfil de hardware. 
1. Seleccione **Editar** y luego, en la ficha **Periféricos fiscales**, agregue una línea. 
1. En el campo **Número de perfil**, seleccione un perfil técnico de conector.
1. En la pestaña **Periféricos fiscales**, seleccione los perfiles técnicos del conector con la ubicación del conector **Estación de hardware**.

> [!NOTE]
> Puede agregar varios perfiles técnicos al mismo perfil de hardware. Sin embargo, un perfil de hardware o un perfil de funcionalidad de PDV debe tener una sola intersección con cualquier grupo de conectores fiscales.

El flujo de registro fiscal se define mediante el proceso de registro fiscal y también por algunos parámetros de componentes de integración fiscales: la extensión CRT para el proveedor de documentos fiscales y la extensión de estación de hardware para el conector fiscal.

- La suscripción de eventos y transacciones al registro fiscal está predefinida en el proveedor de documentos fiscales.
- El proveedor de documentos fiscales también es responsable de identificar el conector fiscal que se usa para el registro fiscal. Coincide con los perfiles funcionales de conectores que se incluyen en el grupo de conectores fiscales que se especifica para el paso actual del proceso de registro fiscal con el perfil técnico de conectores que se asigna el perfil de hardware de la emisora de hardware a la que está emparejado el PDV.
- El proveedor de documentos fiscales usa la configuración de asignación de datos de la configuración del proveedor de documentos fiscales para transformar datos de transacciones u eventos como impuestos y pagos mientras se genera un documento fiscal.
- Cuando el proveedor de documentos fiscales genera un documento fiscal, el conector fiscal puede enviarlo al dispositivo fiscal tal como está, o bien analizarlo y transformarlo en una secuencia de comandos de la API para dispositivos, en función de cómo se gestiona la comunicación.

### <a name="set-up-registers-with-fiscal-registration-restrictions"></a>Configurar registros con restricciones de registro fiscal

Puede seleccionar registros en los que el registro fiscal está prohibido, por ejemplo en casos en los que necesite proporcionar solo operaciones no fiscales, como búsqueda de catálogo de productos, búsqueda de clientes o creación de borrador de transacción en estos dispositivos.

Para configurar los registros con restricciones de registro fiscal, siga estos pasos.

1. En la sede de Commerce vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Procesos de registro fiscal**.
1. Seleccione el proceso requerido.
1. Seleccione la pestaña **Registros PDV con restricciones de proceso fiscal**.
1. Agregue registros con restricciones de proceso fiscal según sea necesario.

### <a name="validate-the-fiscal-registration-process"></a>Validar el proceso de registro fiscal

Se recomienda validar el proceso de registro fiscal en los siguientes casos:

- Ha completado todas las configuraciones para un nuevo proceso de registro. Estas configuraciones incluyen la asignación de procesos de registro a perfiles de funcionalidad de POS y perfiles de hardware.
- Ha realizado cambios en un proceso de registro fiscal existente y esos cambios pueden hacer que se seleccione un conector fiscal diferente en tiempo de ejecución. (Por ejemplo, cambió el grupo de conectores para un paso del proceso de registro fiscal, habilitó un perfil funcional de conector en un grupo de conectores o agregó un nuevo perfil funcional de conector a un grupo de conectores).
- Ha realizado cambios en la asignación de los perfiles técnicos de conectores a perfiles de hardware.

Para validar el proceso de registro fiscal, siga estos pasos.

1. En Commerce Headquarters, vaya a a la página **Proceso de registro fiscal** (**Retail y Commerce \> Configuración de canal \> Integración fiscal \> Procesos de registro fiscal**).
1. Seleccione **Validar** para validar el proceso de registro fiscal.
1. En la página **Programador de distribución** , ejecute los trabajos **1070** y **1090** para transferir datos a la base de datos del canal.

## <a name="set-up-fiscal-texts-for-discounts"></a>Configuración de textos fiscales para descuentos

En algunos casos, un texto especial se debe imprimir en un recibo fiscal si se aplica un descuento. Puede configurar textos fiscales para descuentos en la página **Grupo fiscal de conectores** (**Retail y Commerce \> Configuración del canal \> Integración fiscal \> Grupos de conectores fiscales**).

- Para descuentos manuales que se aplican en el PDV, debe configurar un texto fiscal para el código información o el grupo de códigos de información especificado como código de información de **Descuento del producto** en el perfil de funcionalidad del PDV.

    1. En la página **Grupo del conector fiscal** , seleccione **Texto de recibo fiscal**.
    1. En la pestaña **Códigos de información** , seleccione **Agregar**, y seleccione un código de información o un grupo de códigos de información.
    1. En el campo **Número de código de información**, seleccione un valor.
    1. En el campo **Número de subcódigos**, seleccione un valor si un subcódigo se requiere para el código de información seleccionado.
    1. En el campo **Texto de recibo fiscal**, especifique un texto fiscal que se debe imprimir en un recibo fiscal.
    1. Establezca la opción **Imprimir entrada de usuario en recibo fiscal** en **Sí** para reemplazar el texto en un recibo fiscal con la información que un usuario introduce manualmente en el PDV. Esta opción solo se aplica a los códigos de información que tienen un tipo de entrada de **Texto**.

    > [!NOTE]
    > Puede especificar un texto fiscal para varios códigos de información para admitir los escenarios donde se utilizan grupos de códigos de información, códigos de información vinculados y códigos activados de la información. En estos casos, el recibo fiscal contendrá los textos fiscales de todos los códigos de información vinculados a la línea de transacción en la se aplicó el descuento.

- Para descuentos específicos del canal, debe definir un texto fiscal para el identificador del descuento.

    1. En la página **Grupo del conector fiscal** , seleccione **Texto de recibo fiscal**.
    1. En la pestaña **Descuentos**, seleccione **Agregar**, y seleccione un identificador de descuento.
    1. En el campo **Texto de recibo fiscal**, especifique un texto fiscal que se debe imprimir en un recibo fiscal.

    > [!NOTE]
    > Si varios descuentos se aplican a la misma línea de transacción, la recepción fiscal contendrá los textos fiscales de todos los descuentos vinculados a dichas líneas de transacción.

## <a name="set-error-handling-settings"></a>Establecimiento de la configuración de tratamiento de errores

Las opciones de procesamiento de errores que están disponibles en la integración fiscal se establecen en el proceso de registro fiscal. Para obtener más información acerca de tratamiento de errores en la integración fiscal, consulte [Control de errores](fiscal-integration-for-retail-channel.md#error-handling).

Para establecer la configuración de manejo de errores, siga estos pasos.

1. En la página **Proceso de registro fiscal** (**Retail y Commerce \> Configuración de canal \> Integración fiscal \> Procesos de registro fiscal**) puede establecer los parámetros siguientes para cada paso del proceso de registro fiscal:

    - **Permitir omisión** Este parámetro habilita la opción **Omitir** en el cuadro de diálogo de tratamiento de errores.
    - **Permitir lo marcado como registrado** Este parámetro habilita la opción **Marcar como registrado** en el cuadro de diálogo de control de errores.
    - **Permitir posponer** - Este parámetro habilita la opción **Posponer** en el cuadro de diálogo de tratamiento de errores.
    - **Continuar con errores**: si se habilita este parámetro, el proceso de registro fiscal puede continuar en el registro de PDV si falla el registro fiscal de una transacción o de un evento. Si no, para ejecutar el registro fiscal de la transacción u evento siguiente, el operador debe reintentar el registro fiscal fallido, omitirlo, o marcar la transacción o el evento como registrado. Para obtener más información, consulte [Registro fiscal opcional](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Si se habilita el parámetro **Continuar con errores** , los parámetros **Permitir saltar** y **Permitir marcar como registrado** se deshabilitan automáticamente.

1. Las opciones **Omitir** y **Marcar como registrado** en el cuadro de diálogo de tratamiento de errores requieren que el permiso **Permitir omitir o marcar como registrado** esté habilitado. Para habilitar este permiso, vaya a la página **Grupos de permisos** (**Retail y Commerce \> Empleados \> Grupos de permisos**), y establezca la opción **Permitir omitir o marcar como registrado** en **Sí**.
1. La opción **Posponer** del cuadro de diálogo de tratamiento de errores requiere que el permiso **Permitir posponer** esté habilitado. Para habilitar el permiso, vaya a la página **Grupos de permisos** (**Retail y Commerce \> Empleados \> Grupos de permisos**), y establezca la opción **Permitir posponer** en **Sí**.
1. Las opciones **Omitir**, **Marcar como registrado** y **Posponer** permiten a los operadores especificar información adicional cuando el registro fiscal genera errores. Para hacer que esta funcionalidad esté disponible, debe especificar los códigos de información **Omitir**, **Marcar como registrado** y **Posponer** en un grupo de conectores fiscales. La información que los operadores introducen se guarda como una transacción de código de información que está vinculada a la transacción fiscal. Para obtener más información acerca de códigos de información, consulte [Códigos de información y grupos de códigos de información](../info-codes-retail.md).

    > [!NOTE]
    > La función de activación **Producto** no se admite para los códigos de información que se usan para **Omitir** y **Marcar como registrado** en grupos de conectores fiscales.

    - En la página **Grupo de conectores fiscales**, en la pestaña **Códigos de información**, seleccione códigos de información o grupos de códigos de información en los campos **Omitir**, **Marcar como registrado** y **Posponer**.

    > [!NOTE]
    > Un documento fiscal y un documento no fiscal se pueden generar en cualquier paso de un proceso de registro fiscal. Una extensión del proveedor de documentos fiscales identifica cada tipo de transacción o evento en relación con documentos fiscales o no fiscales. La característica de tratamiento de errores solo se aplica a los documentos fiscales.
    >
    > - **Documento fiscal**: un documento obligatorio que se debe registrar correctamente (por ejemplo, un recibo fiscal).
    > - **Documento no fiscal** – Un documento suplementario para la transacción o el evento (por ejemplo, un resguardo de tarjeta regalo).

1. Si el operador debe poder continuar procesando la operación actual (por ejemplo, creación o finalización de una transacción) después de que se produzca un error en la comprobación de estado, debe habilitar el permiso **Permite omitir error de comprobación de estado** en la página **Grupos de permisos** (**Retail y Commerce \> Empleados \> Grupos de permisos**). Para obtener más información sobre el procedimiento de comprobación de estado, consulte [Comprobar estado del registro fiscal](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Configuración de informes X/Z fiscales de PDV

Para habilitar los informes fiscales de X/Z que se ejecutarán desde PDV, debe agregar nuevos botones a un diseño de PDV.

- En la página **Cuadrículas de botones** , siga las instrucciones que se indican en [Agregar operaciones de PDV a diseños de PDV mediante el diseñador de cuadrícula de botones](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) para instalar el diseñador y actualizar un diseño de PDV.

    1. Seleccionar el diseño que se va a actualizar. 
    1. Agregue un nuevo botón y defina la propiedad del botón **Impresión fiscal X**.
    1. Agregue un nuevo botón y defina la propiedad del botón **Impresión fiscal Z**.
    1. En la página **Programación de distribución**, ejecute el trabajo **1090** para transferir cambios a la base de datos del canal.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>Habilitar la ejecución manual del registro fisca postpuesto.

Para habilitar la ejecución manual de un registro fiscal postpuesto, debe agregar un nuevo botón a un diseño de PDV.

- En la página **Cuadrículas de botones** , siga las instrucciones que se indican en [Agregar operaciones de PDV a diseños de PDV mediante el diseñador de cuadrícula de botones](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) para instalar el diseñador y actualizar un diseño de PDV.

    1. Seleccionar el diseño que se va a actualizar.
    1. Agregue un nuevo botón y defina la propiedad del botón **Completar el proceso de registro fiscal**.
    1. En la página **Programación de distribución**, ejecute el trabajo **1090** para transferir sus cambios a la base de datos del canal.


## <a name="view-connection-parameters-and-other-information-in-pos"></a>Ver parámetros de conexión y otra información en PDV

Para ver parámetros de conexión y otra información en PDV, siga estos pasos.

1. Abra Modern POS (MPOS) o Cloud POS (CPOS).
1. Seleccione **Configuración**. Si la integración fiscal está habilitada, la sección **Integración Fiscal** de la derecha mostrará la siguiente información:

    - Estado del registro fiscal
    - Estado de la última transacción fiscal
    - Número de de eventos de auditoría pendientes

1. Seleccione **Detalles** para ver la siguiente información:

    - Pasos del proceso de registro
    - Parámetros de conexión
    - Detalles de eventos de auditoría
 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
