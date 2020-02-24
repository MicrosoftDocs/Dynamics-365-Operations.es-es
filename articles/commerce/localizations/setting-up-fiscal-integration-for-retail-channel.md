---
title: Configurar la integración fiscal para canales de Commerce
description: En este tema se proporcionan instrucciones para configurar la funcionalidad de integración fiscal para canales de Commerce.
author: josaw
manager: annbe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: b221bfede5d1db8d7970e1efede85e8dba7fe017
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024002"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>Configurar la integración fiscal para canales de Commerce

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Introducción

En este tema se proporcionan instrucciones para configurar la funcionalidad de integración fiscal para canales de Commerce. Para obtener más información acerca de la integración fiscal, consulte [Visión general de la integración fiscal para los canales de Commerce](fiscal-integration-for-retail-channel.md).

El proceso de configurar la integración fiscal incluye las tareas globales siguientes:

1. Configurar los conectores fiscales que representan los dispositivos o servicios fiscales que se usan para fines fiscales de registro, como impresoras fiscales.
2. Configurar los proveedores de documentos que generan los documentos fiscales que se registrarán en dispositivos o servicios fiscales mediante conectores fiscales.
3. Configurar el proceso de registro fiscal que define una secuencia de pasos de registro fiscal y los conectores fiscales y proveedores de documentos fiscales que se usan para cada paso.
4. Asignar el proceso de registro fiscal a perfiles de funcionalidad de punto de venta (PDV).
5. Asignar perfiles técnicos de conectores a los perfiles de hardware.

## <a name="set-up-a-fiscal-registration-process"></a>Configuración de un proceso de registro fiscal

Antes de usar la funcionalidad de la integración fiscal, debe configurar los valores siguientes.

1. Actualice parámetros de Commerce.

    1. En la página **Parámetros compartidos de Commerce**, en la pestaña **General**, establezca la opción **Habilitar integración fiscal** en **Sí**. En la ficha **Secuencias numéricas**, defina el número de secuencias para las siguientes referencias:

        - Número de perfil técnico fiscal
        - Número de grupo del conector fiscal
        - Número de proceso de registro

    2. En la página **Parámetros de Commerce** defina la secuencia numérica para el número de perfil funcional fiscal.

    > [!NOTE]
    > Las secuencias numéricas son opcionales. Los números de las entidades de integración fiscal se pueden generar desde secuencias numéricas o manualmente.

2. Cargue las configuraciones de conectores fiscales y proveedores de documentos fiscales.

    Un proveedor de documentos fiscales es responsable de generar documentos fiscales que representan las transacciones y los eventos que se registran en el sistema PDV en un formato que también se usa para la interacción con un dispositivo o un servicio fiscal. Por ejemplo, un proveedor de documentos fiscales puede generar una representación de un recibo fiscal en un formato XML.

    Un conector fiscal es responsable de la comunicación con un dispositivo o un servicio fiscal. Por ejemplo, un conector fiscal puede enviar un recibo fiscal que un proveedor fiscal de documentos ha creado en un formato XML a una impresora fiscal. Para obtener más detalles sobre los componentes de integración fiscal, consulte [Proceso de registro fiscal y ejemplos fiscales de la integración de los dispositivos fiscales](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

    1. En la página **conectores fiscales** (**Retail y Commerce \> Configuración de canal \> integración fiscal \> conectores fiscales**) cargue una configuración XML para cada dispositivo o servicio que tenga previsto usar para fines de integración fiscal.

        > [!TIP]
        > Seleccionando **Ver**, puede ver todos los perfiles funcionales y técnicos relacionados con el conector fiscal actual.

    2. En la página **Proveedores de documentos fiscales** (**Retail y Commerce \> Configuración de canal \> integración fiscal \> Proveedores de documentos fiscales**) cargue una configuración XML para cada dispositivo o servicio que tenga previsto usar.

        > [!TIP]
        > Seleccionando **Ver**, puede ver todos los perfiles funcionales relacionados con el proveedor de documentos fiscales actual.

    Para obtener ejemplos de configuraciones de conectores fiscales y proveedores de documentos fiscales, consulte [Ejemplos fiscales de integración en el SDK al por menor](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-retail-sdk).

    > [!NOTE]
    > La asignación de datos se considera parte de un proveedor de documentos fiscales. Para configurar diferentes asignaciones de datos para el mismo conector (por ejemplo, normas de estado específicas), debe crear varios proveedores de documentos fiscales.

3. Cree perfiles funcionales de conector y perfiles técnicos de conectores.

    1. En la página **Perfiles funcionales de conectores** (**Retail y Commerce \> Configuración del canal \> Integración fiscal \> Perfiles funcionales de conectores**), cree un perfil funcional de conector para cada combinación de un conector fiscal y de un proveedor de documentos fiscales relacionado con este conector fiscal.

        1. Seleccione un nombre de conector.
        2. Seleccione un proveedor de documentos.

        Puede cambiar los parámetros de la asignación de los datos de un perfil funcional de conector. Para restablecer los parámetros predeterminados que se definen en la configuración del proveedor de documentos fiscales, seleccione **Actualizar**.

        **Ejemplos**

        |   | Formato | Ejemplo |
        |---|--------|---------|
        | **Configuración de índices de IVA** | valor: VATrate | 1 : 2000, 2 : 1800 |
        | **Asignación de códigos de IVA** | VATcode : valor | vat20 : 1, vat18 : 2 |
        | **Asignación de tipos de forma de pago** | TenderType : valor | Cash : 1, Card : 2 |

        > [!NOTE]
        > Los perfiles funcionales de conectores son específicos de la empresa. Si tiene previsto usar la misma combinación de un conector fiscal y de un proveedor de documentos fiscales en distintas empresas, debe crear un perfil funcional de conector para cada empresa.

    2. En la página **Perfiles técnicos del conector** (**Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles técnicos del conector**), cree un perfil técnico de conector para cada conector fiscal.

        1. Seleccione un nombre de conector.
        2. Seleccione un tipo de conector. Para los dispositivos asociados a una emisora de hardware, seleccione **Local**.

            > [!NOTE]
            > Solo los conectores locales se admiten actualmente.

        Los parámetros de las pestañas **Dispositivo** y **Configuración** de un perfil técnico de conector se pueden modificar. Para restablecer los parámetros predeterminados que se definen en la configuración del conector fiscal, seleccione **Actualizar**. Mientras una nueva versión de una configuración de XML se carga, recibirá un mensaje que indica que el conector fiscal o el proveedor de documentos fiscales actual ya se está utilizando. Este procedimiento no anula los cambios manuales que se realizaron previamente en perfiles funcionales de conector y en perfiles técnicos de conector. Para aplicar el conjunto de parámetros predeterminado desde una configuración, en la página **Perfiles funcionales del conector** y la página **Perfiles técnicos del conector** seleccione **Actualizar**.

4. Cree grupos de conectores fiscales.

    Un grupo de conectores fiscales combina perfiles funcionales de conectores fiscales que realizan idénticas funciones y se usan en la misma etapa del proceso de registro fiscal. Por ejemplo, si varios modelos de impresora fiscales se pueden usar en una tienda, los conectores fiscales para las impresoras fiscales se pueden combinar en un grupo fiscal de conectores.

    1. En la página **Grupo fiscal de conectores** (**Retail y Commerce \> Configuración del canal \> Integración fiscal \> Grupos de conectores fiscales**), cree un nuevo grupo fiscal de conectores.
    2. Agregue perfiles funcionales el grupo de conectores. En la pestaña **Perfiles funcionales**, seleccione **Agregar** y seleccione un número del perfil. Cada conector fiscal de un grupo de conectores solo puede tener un perfil funcional.
    3. Para suspender el uso del perfil funcional, establezca la opción **Deshabilitar** en **Sí**. Este cambio afecta al grupo de conectores actuales únicamente. Puede continuar usando el mismo perfil funcional en otros grupos de conectores.

5. Cree un proceso de registro fiscal.

    Un proceso de registro fiscal se define por la secuencia de los pasos de registro y el grupo de conectores utilizados en cada paso.

    1. En la página **Proceso de registro fiscal** (**Retail y Commerce \> Configuración de canal \> Integración fiscal \> Procesos de registro fiscal**) cree un nuevo registro para cada proceso único de registro fiscal.
    2. Agregar pasos de registro al proceso:

        1. Seleccione **Agregar**.
        2. Seleccione un tipo de conector fiscal.
        3. En el campo **Número de grupo** , seleccione un grupo de conectores fiscales adecuado.

6. Asigne entidades del proceso de registro fiscal a perfiles PDV.

    1. En la página **Perfiles de funcionalidad del PDV** (**Retail y Commerce \> Configuración del canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad**), asigne el proceso de registro fiscal a un perfil de funcionalidad de PDV. Seleccione **Editar**y, a continuación, en la pestaña **Proceso de registro fiscal** , en el campo **Número de proceso** , seleccione un proceso.
    2. En la página **Perfil de hardware del PDV** (**Retail y Commerce \> Configuración del canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de hardware**), asigne perfiles técnicos de conector a un perfil de hardware. Seleccione **Editar**, agregue una línea en la pestaña **Periféricos fiscales** y, a continuación, en el campo **Número de perfil** , seleccione un perfil técnico de conector.

    > [!NOTE]
    > Puede agregar varios perfiles técnicos al mismo perfil de hardware. Sin embargo, un perfil de hardware o un perfil de funcionalidad de PDV debe tener una sola intersección con cualquier grupo de conectores fiscales.

    El flujo de registro fiscal se define mediante el proceso de registro fiscal y también por algunos parámetros de componentes de integración fiscales: la extensión del tiempo de ejecución de comercio para el proveedor de documentos fiscales y la extensión de estación de hardware para el conector fiscal.

    - La suscripción de eventos y transacciones al registro fiscal está predefinida en el proveedor de documentos fiscales.
    - El proveedor de documentos fiscales también es responsable de identificar el conector fiscal que se usa para el registro fiscal. Coincide con los perfiles funcionales de conectores que se incluyen en el grupo de conectores fiscales que se especifica para el paso actual del proceso de registro fiscal con el perfil técnico de conectores que se asigna el perfil de hardware de la emisora de hardware a la que está emparejado el PDV.
    - El proveedor de documentos fiscales usa la configuración de asignación de datos de la configuración del proveedor de documentos fiscales para transformar datos de transacciones u eventos como impuestos y pagos mientras se genera un documento fiscal.
    - Cuando el proveedor de documentos fiscales genera un documento fiscal, el conector fiscal puede enviarlo al dispositivo fiscal tal como está, o bien analizarlo y transformarlo en una secuencia de comandos de la interfaz de programación de la aplicación (API) para dispositivos, en función de cómo se gestiona la comunicación.

7. En la página **Proceso de registro fiscal** (**Retail y Commerce \> configurar canal \> integración fiscal \> procesos de registro fiscales**) seleccione **Validar** para validar el proceso de registro fiscal.

    Es recomendable ejecutar este tipo de validación en los casos siguientes:

    - Después de completar toda la configuración de un proceso de registro nuevo, incluido cuando asigna procesos de registro a perfiles de funcionalidad de PDV y de hardware.
    - Una vez que haya creado los cambios en un proceso de registro fiscal existente, y que dichos cambios puedan provocar que se seleccione otro conector fiscal en el tiempo de ejecución (por ejemplo, si cambia el grupo de conectores para un paso del proceso de registro fiscal, habilite un perfil funcional en un grupo de conectores o agregue un perfil funcional de conector nuevo a un grupo de conectores).
    - Después de realizar cambios en la asignación de los perfiles técnicos de conectores a perfiles de hardware.

8. En la página **Programador de distribución** , ejecute los trabajos **1070** y **1090** para transferir datos a la base de datos del canal.

## <a name="set-up-fiscal-texts-for-discounts"></a>Configuración de textos fiscales para descuentos

En algunos casos, un texto especial se debe imprimir en un recibo fiscal si se aplica un descuento. Puede configurar textos fiscales para descuentos en la página **Grupo fiscal de conectores** (**Retail y Commerce \> Configuración del canal \> Integración fiscal \> Grupos de conectores fiscales**).

- Para descuentos manuales que se aplican en el PDV, debe configurar un texto fiscal para el código información o el grupo de códigos de información especificado como código de información de **Descuento del producto**en el perfil de funcionalidad del PDV.

    1. En la página **Grupo del conector fiscal** , seleccione **Texto de recibo fiscal**.
    2. En la pestaña **Códigos de información** , seleccione **Agregar**, y seleccione un código de información o un grupo de códigos de información.
    3. En el **Número de código de información**, seleccione un valor.
    4. En el campo **Número de subcódigos**, seleccione un valor si un subcódigo se requiere para el código de información seleccionado.
    5. En el campo **Texto de recibo fiscal**, especifique un texto fiscal que se debe imprimir en un recibo fiscal.
    6. Establezca la opción **Imprimir entrada de usuario en recibo fiscal** en **Sí** para reemplazar el texto en un recibo fiscal con la información que un usuario introduce manualmente en el PDV. Esta opción solo se aplica a los códigos de información que tienen un tipo de entrada de **Texto**.

    > [!NOTE]
    > Puede especificar un texto fiscal para varios códigos de información para admitir los escenarios donde se utilizan grupos de códigos de información, códigos de información vinculados y códigos activados de la información. En estos casos, el recibo fiscal contendrá los textos fiscales de todos los códigos de información vinculados a la línea de transacción en la se aplicó el descuento.

- Para descuentos específicos del canal, debe definir un texto fiscal para el identificador del descuento.

    1. En la página **Grupo del conector fiscal** , seleccione **Texto de recibo fiscal**.
    2. En la pestaña **Descuentos**, seleccione **Agregar**, y seleccione un identificador de descuento.
    3. En el campo **Texto de recibo fiscal**, especifique un texto fiscal que se debe imprimir en un recibo fiscal.

    > [!NOTE]
    > Si varios descuentos se aplican a la misma línea de transacción, la recepción fiscal contendrá los textos fiscales de todos los descuentos vinculados a dichas líneas de transacción.

## <a name="set-error-handling-settings"></a>Establecimiento de la configuración de tratamiento de errores

Las opciones de procesamiento de errores que están disponibles en la integración fiscal se establecen en el proceso de registro fiscal. Para obtener más información acerca de tratamiento de errores en la integración fiscal, consulte [Control de errores](fiscal-integration-for-retail-channel.md#error-handling).

1. En la página **Proceso de registro fiscal** (**Retail y Commerce \> Configuración de canal \> Integración fiscal \> Procesos de registro fiscal**) puede establecer los parámetros siguientes para cada paso del proceso de registro fiscal:

    - **Permitir omisión** Este parámetro habilita la opción **Omitir** en el cuadro de diálogo de tratamiento de errores.
    - **Permitir lo marcado como registrado** Este parámetro habilita la opción **Marcar como registrado** en el cuadro de diálogo de control de errores.
    - **Continuar con errores**: si se habilita este parámetro, el proceso de registro fiscal puede continuar en el registro de PDV si falla el registro fiscal de una transacción o de un evento. Si no, para ejecutar el registro fiscal de la transacción u evento siguiente, el operador debe reintentar el registro fiscal fallido, omitirlo, o marcar la transacción o el evento como registrado. Para obtener más información, consulte [Registro fiscal opcional](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Si se habilita el parámetro **Continuar con errores** , los parámetros **Permitir saltar** y **Permitir marcar como registrado** se deshabilitan automáticamente.

2. Las opciones **Omitir** y **Marcar como registrado** en el cuadro de diálogo de tratamiento de errores requieren el permiso **Permitir omitir o marcar como registrado**. Por tanto, en la página **Grupos de permisos** (**Retail y Commerce \> Empleados \> Grupos de permisos**), habilite el permiso **Permitir omitir o marcar como registrado**.
3. Las opciones **Omitir** y **Marcar como registrado** permiten a los operadores especificar información adicional cuando el registro fiscal genera errores. Para hacer que esta funcionalidad esté disponible, debe especificar los códigos de información **Omitir** y **Marcar como registrado** en un grupo de conectores fiscales. La información que los operadores introducen se guarda como una transacción de código de información que está vinculada a la transacción fiscal. Para obtener más información acerca de códigos de información, consulte [Códigos de información y grupos de códigos de información](../info-codes-retail.md).

    > [!NOTE]
    > La función de activación **Producto** no se admite para los códigos de información que se usan para **Omitir** y **Marcar como registrado** en grupos de conectores fiscales.

    - En la página **Grupo de conectores fiscales**, en la pestaña **Códigos de información** , seleccione códigos de información o grupos de códigos de información en los campos **Omitir** y **Marcar como registrado**.

    > [!NOTE]
    > Un documento fiscal y un documento no fiscal se pueden generar en cualquier paso de un proceso de registro fiscal. Una extensión del proveedor de documentos fiscales identifica cada tipo de transacción o evento en relación con documentos fiscales o no fiscales. La característica de tratamiento de errores solo se aplica a los documentos fiscales.
    >
    > - **Documento fiscal**: un documento obligatorio que se debe registrar correctamente (por ejemplo, un recibo fiscal).
    > - **Documento no fiscal** – Un documento suplementario para la transacción o el evento (por ejemplo, un resguardo de tarjeta regalo).

4. Si el operador debe poder continuar procesando la operación actual (por ejemplo, creación o finalización de una transacción) después de que se produzca un error en la comprobación de estado, debe habilitar el permiso **Permite omitir error de comprobación de estado** en la página **Grupos de permisos** (**Retail y Commerce \> Empleados \> Grupos de permisos**). Para obtener más información sobre el procedimiento de comprobación de estado, consulte [Comprobar estado del registro fiscal](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Configuración de informes X/Z fiscales de PDV

Para habilitar los informes fiscales de X/Z que se ejecutarán desde PDV, debe agregar nuevos botones a un diseño de PDV.

- En la página **Cuadrículas de botones** , siga las instrucciones que se indican en [Agregar operaciones de PDV a diseños de PDV mediante el diseñador de cuadrícula de botones](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) para instalar el diseñador y actualizar un diseño de PDV.

    1. Seleccionar el diseño que se va a actualizar. 
    2. Agregue un nuevo botón y defina la propiedad del botón **Impresión fiscal X**.
    3. Agregue un nuevo botón y defina la propiedad del botón **Impresión fiscal Z**.
    4. En la página **Programación de distribución**, ejecute el trabajo **1090** para transferir cambios a la base de datos del canal.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>Habilitar la ejecución manual del registro fisca postpuesto.

Para habilitar la ejecución manual de un registro fiscal postpuesto, debe agregar un nuevo botón a un diseño de PDV.

- En la página **Cuadrículas de botones** , siga las instrucciones que se indican en [Agregar operaciones de PDV a diseños de PDV mediante el diseñador de cuadrícula de botones](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) para instalar el diseñador y actualizar un diseño de PDV.

    1. Seleccionar el diseño que se va a actualizar.
    2. Agregue un nuevo botón y defina la propiedad del botón **Completar el proceso de registro fiscal**.
    3. En la página **Programación de distribución**, ejecute el trabajo **1090** para transferir sus cambios a la base de datos del canal.
