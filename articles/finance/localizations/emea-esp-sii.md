---
title: Suministro inmediato de información del IVA, SII
description: Este tema describe cómo configurar y usar Microsoft Dynamics 365 Finance para interoperar con el sistema SII de España.
author: liza-golub
ms.date: 07/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Spain
ms.author: elgolu
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: b3ceb73287b08555782ed6f465ed73b21a9cbdcf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260763"
---
# <a name="immediate-supply-of-information-on-vat-suministro-inmediato-de-informacin-del-iva-sii"></a>Suministro inmediato de información del IVA, SII

[!include [banner](../includes/banner.md)]

De acuerdo con el R.D. 596/2016 en España, un nuevo sistema de gestión del impuesto sobre el valor agregado (IVA) basado en el Suministro inmediato de información del IVA (SII) permite una relación bidireccional y automatizada entre la Agencia Tributaria Española (AEAT) y el contribuyente. En el resto de este tema, este sistema se denominará el sistema SII. A partir del 1 de julio de 2017, los contribuyentes sujetos a SII, y otros que lo adopten voluntariamente, deben enviar detalles de sus registros de facturación en un plazo de cuatro días mediante presentación en línea en el sitio web de AEAT.

Para obtener más información sobre el sistema SII de España, consulte el [sitio web oficial del Suministro inmediato de información del IVA (SII)](https://www.agenciatributaria.es/AEAT.internet/en_gb/Inicio/La_Agencia_Tributaria/Campanas/Suministro_Inmediato_de_Informacion_en_el_IVA__SII_/Suministro_Inmediato_de_Informacion_en_el_IVA__SII_.shtml).

## <a name="overview"></a>Información general

Este tema describe cómo configurar y usar Microsoft Dynamics 365 Finance para interoperar con el sistema SII de España. Incluye información sobre cómo completar las siguientes tareas:

-   Importar configuraciones de informes electrónicos (ER).
-   Configurar la funcionalidad de mensajería electrónica (EM).
-   Configurar informes para el sistema SII.
-   Trabajar con la funcionalidad EM para interoperar con el sistema SII.

## <a name="import-er-configurations"></a>Importar configuraciones de ER

Para preparar Finance para interoperar con el sistema SII, debe importar las siguientes configuraciones de ER.

| **Número** | **Nombre de configuración**                  | **Tipo de configuración** |
|------------|-----------------------------------------|------------------------|
| **1**      | **Modelo de comunicación de facturas**        | **Modelo**              |
| 2          | Asignación del modelo SII                       | Distribución del modelo          |
| 3          | Formato de factura emitida de SII (ES)          | Formato                 |
| 4          | Formato de factura recibida de SII (ES)        | Formato                 |
| 5          | Formato intracomunitario de SII (ES)         | Formato                 |
| 6          | Formato de pago del cliente de SII (ES)        | Formato                 |
| 7          | Formato de pago del proveedor de SII (ES)          | Formato                 |
| 8          | Formato de colección de SII en efectivo (ES)      | Formato                 |
| **9**      | **Modelo marco de trabajo de mensajes electrónicos** | **Modelo**              |
| 10         | Asignación de modelo de importación de SII (ES)             | Distribución del modelo          |
| 11         | Formato de importación de SII (ES)                  | Formato                 |

> [!IMPORTANT]
> Asegúrese de importar las versiones más recientes de estas configuraciones. La descripción de la versión generalmente incluye el número del artículo de Microsoft Knowledge Base (KB) que explica los cambios que se introdujeron en la versión de configuración.

> [!NOTE]
> Después de importar todas las configuraciones de ER de la tabla anterior, configure la opción **Valores predeterminados para la asignación de modelos** en **Sí** para las configuraciones **Asignación del modelo de SII** y **Asignación del modelo de importación de SII (ES)**.

Para obtener más información sobre cómo descargar configuraciones de ER desde el repositorio global de Microsoft, vea [Descarar las configuraciones de ER del repositorio global](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="import-a-package-of-data-entities-that-includes-a-predefined-em-setup"></a>Importar un paquete de entidades de datos que incluya una configuración EM predefinida

La funcionalidad de mensajes electrónicos se proporciona para mantener los diferentes procesos que se utilizan en los informes electrónicos para diferentes tipos de documentos. Para obtener más información sobre los mensajes electrónicas, consulte [Mensajes electrónicos](https://docs.microsoft.com/dynamics365/finance/general-ledger/electronic-messaging).

El proceso de configuración de la funcionalidad de mensajes electrónicos para interoperar con el sistema SII tiene muchos pasos. Debido a que los nombres de algunas entidades predefinidas se usan en las configuraciones de ER, es importante que use un conjunto de valores predefinidos que se entregan en un paquete de entidades de datos para las tablas relacionadas, y que importe las configuraciones de ER antes de importar las entidades de datos.

1.  En [Microsoft Dynamics Lifecycle Service (LCS)](https://lcs.dynamics.com/v2), vaya a la Biblioteca de activos compartidos y seleccione el tipo de activo **Paquete de datos**.
2.  En la lista de archivos de paquetes de datos, busque y descargue **ES SII setup.zip**.

![Biblioteca de activos compartidos de LCS](media/emea-esp-sii-data-package-file.png)

3.  Después de descargar el archivo, abra Finance y seleccione la compañía desde la cual interoperará con el sistema SII.
4.  Vaya a **Espacios de trabajo \> Administración de datos**.
5.  En el espacio de trabajo **Administración de datos**, vaya a **Parámetros del marco de trabajo \> Configuración de entidad** y seleccione **Actualizar lista de entidades**. Espere la confirmación de que la actualización se ha completado. Para obtener más información sobre cómo actualizar la lista de entidades, vea [Actualización de la lista de entidades](https://docs.microsoft.com/dynamics365/dev-itpro/data-entities/data-entities#entity-list-refresh).
6.  Confirme que los datos de origen y destino estén asignados correctamente. Para obtener más información, consulte [Confirmar que los datos de origen y destino estén asignados correctamente](https://docs.microsoft.com/dynamics365/dev-itpro/data-entities/data-import-export-job#validate-that-the-source-data-and-target-data-are-mapped-correctly).
7.  Antes de que las entidades de datos se usen por primera vez para importar los datos del paquete, sincronice el mapeo de los datos de origen y de destino. En la lista del paquete, seleccione una entidad de datos y luego, en el Panel de acciones, seleccione **Modificar la asignación objetivo**.
8.  Sobre la cuadrícula del paquete, seleccione **Generar asignación** para crear una asignación desde cero y luego guardar la asignación.
9.  Repita los pasos 7 y 8 para cada entidad de datos en el paquete antes de comenzar la importación.

Para obtener más información sobre la administración de datos, vea [Descripción general de la administración de datos](https://docs.microsoft.com/dynamics365/dev-itpro/data-entities/data-entities-data-packages).

Importe los datos desde el archivo **ES SII setup.zip** en la empresa seleccionada. En el espacio de trabajo **Administración de datos**, seleccione **Importar**, especifique un **Nombre de grupo**, seleccione **Agregar archivo** y luego, en el cuadro de diálogo desplegable, establezca el campo **Formato de datos de origen** en **Paquete** y establezca el campo **Formato de datos de origen** en **Paquete**.

10.  Seleccione **Cargar y agregar**, seleccione el archivo **ES SII setup.zip** en su ordenador y cárguelo.
11.  Después de cargar las entidades de datos, en el Panel de acciones, seleccione **Importar**.

![Página de configuración de SII (ES)](media/emea-esp-sii-data-entities-upload.png)

Recibirá una notificación en **Centro de acción**, o puede actualizar manualmente la página para ver el progreso de la importación de datos. Cuando se completa la importación, la página **Resumen de ejecución** muestra los resultados.

Después de importar las entidades de datos, encontrará dos tipos de procesamiento de mensajes electrónicos: **SII** y **CollectionInCash**. Este procesamiento contiene casi toda la configuración que se requiere en su entidad jurídica.


| **En procesamiento**   | **Nombre**                                                   | **Descripción**                                                                                                                                                                                                                                                                                                                                |
|------------------|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SII              | Suministro inmediato de información (SII): facturas, pagos  | Este procesamiento admite la interoperación con el sistema SII para enviar información sobre facturas de clientes y proveedores, información adicional sobre pagos relacionados con facturas de clientes y proveedores donde el valor **Código de esquema especial** se establece en **07** e información adicional relacionada con las facturas intracomunitarias. |
| CollectionInCash | Suministro inmediato de información (SII): cobros en efectivo | Este procesamiento admite la interoperación con el sistema SII para enviar información sobre cobros en informes de efectivo. Esta información se agrupa por importes de pago del cliente que se evalúan desde una cuenta específica que se configura como una cuenta de efectivo, y que exceden la cantidad de 6000 euros durante el período del informe.             |

Para revisar el procesamiento importado, vaya a **Impuesto** \> **Configuración** \> **Mensajes electrónicos** \> **Procesamiento de mensajes electrónicos**.

El procesamiento de mensajes electrónicos de la tabla anterior funciona con los siguientes tipos de elementos de mensajes electrónicos.

| **Tipo de elemento de mensaje electrónico** | **Descripción**                                                                                                                                                                                                                                                                                                                                                                                                               | **En procesamiento**   |
|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------|
| FacturasProveedores               | **Facturas de proveedores**                                                                                                                                                                                                                                                                                                                                                                                                           | SII              |
| FacturasСliente                   | **Facturas del cliente**                                                                                                                                                                                                                                                                                                                                                                                                         | SII              |
| PagosCliente                      | **Pagos de clientes**: los elementos de mensaje de este tipo se crean para facturas de clientes existentes donde el valor **Código de esquema especial** se establece en **07**.                                                                                                                                                                                                                                                             | SII              |
| PagosProveedores                  | **Pagos de proveedores**: los elementos de mensaje de este tipo se crean para facturas de proveedores existentes donde el valor **Código de esquema especial** se establece en **07**.                                                                                                                                                                                                                                                                  | SII              |
| Operaciones intracomunitarias      | **Operaciones intracomunitarias**: los elementos de mensaje de este tipo se crean para facturas de proveedores existentes que cumplen con criterios específicos dentro de la comunidad. Para obtener más información, consulte la descripción en la sección [Algoritmo para definir el campo adicional TipoOperación (tipo de operación intracomunitaria)](#algorithm-to-define-the-tipooperacion-intra-community-operation-type-additional-field) más adelante en este tema. | SII              |
| CobrosEnMetálico                  | **Cobros en metálico**: los elementos de mensaje de este tipo se completan a partir de la información preliminar que se recopila sobre las transacciones de pago que se registran de los clientes en cuentas de efectivo específicas.                                                                                                                                                                                                                 | CollectionInCash |

Para revisar los tipos de mensaje electrónico, vaya a **Impuesto** \> **Configuración** \> **Mensajes electrónicos** \> **Tipos de elementos de mensaje**.

## <a name="set-up-the-internet-address-and-certificates-for-the-sii-system"></a>Configurar la dirección de Internet y los certificados para el sistema SII

Para interactuar con el sistema SII, debe usar un certificado de seguridad proporcionado por la AEAT. Hay dos opciones para almacenar estos datos confidenciales:

-   Almacenamiento de Azure Key Vault
-   Almacenamiento local

Para obtener más información sobre cómo configurar Key Vault, vea [Configurar el cliente Azure Key Vault](https://support.microsoft.com/help/4040305/setting-up-azure-key-vault-client) y [Realizar el mantenimiento del almacenamiento de Azure Key Vault](https://support.microsoft.com/help/4040294/maintaining-azure-key-vault-storage).

1.  Vaya a **Administración del sistema** \> **Configuración** \> **Parámetros del sistema**.
2.  Establezca la opción **Usar almacén de certificados avanzado** en **No** para almacenar datos confidenciales localmente. Establezca la opción en **Sí** para utilizar el almacenamiento de Key Vault.
3.  Si establece la opción **Usar almacén de certificados avanzado** en **Sí**, vaya a **Administración del sistema \> Configurar \> Parámetros de Key Vault** para configurar los parámetros de Key Vault.
4.  Vaya a **Impuesto** \> **Configuación** \> **Parámetros** \> **Mensajes electrónicos** \> **Configuración del servicio Web**.
5.  Especifique la siguiente información para definir la dirección de Internet para los servicios Web.

| **Nombre del servicio Web** | **Descripción**                                                                                                                                                                                                                 | **Probar la dirección de Internet**                               |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------|
| Factura clie.         | Este servicio web es proporcionado por la AEAT. Se utiliza para enviar información sobre facturas emitidas, y envía una respuesta que contiene información sobre el procesamiento de facturas en el lado del sistema SII.                            | `https://www7.aeat.es/wlpl/SSII-FACT/ws/fe/SiiFactFEV1SOAP`  |
| Factura de prov.         | Este servicio web es proporcionado por la AEAT. Se utiliza para enviar información sobre facturas recibidas, y envía una respuesta que contiene información sobre el procesamiento de facturas en el lado del sistema SII.                          | `https://www7.aeat.es/wlpl/SSII-FACT/ws/fr/SiiFactFRV1SOAP`  |
| Intracomunitario      | Este servicio web es proporcionado por la AEAT. Se utiliza para enviar información sobre facturas intracomunitarias y envía una respuesta que contiene información sobre el procesamiento de facturas en el lado del sistema SII.                   | `https://www7.aeat.es/wlpl/SSII-FACT/ws/oi/SiiFactOIV1SOAP`  |
| Pago de clie.         | Este servicio web es proporcionado por la AEAT. Se utiliza para enviar información sobre pagos de clientes para tipos de factura específicos y envía una respuesta que contiene información sobre el procesamiento en el lado del sistema SII. | `https://www7.aeat.es/wlpl/SSII-FACT/ws/fe/SiiFactCOBV1SOAP` |
| Pago de prov.         | Este servicio web es proporcionado por la AEAT. Se utiliza para enviar información sobre pagos a proveedores para tipos de factura específicos y envía una respuesta que contiene información sobre el procesamiento en el lado del sistema SII.     | `https://www7.aeat.es/wlpl/SSII-FACT/ws/fr/SiiFactPAGV1SOAP` |
| CollectionInCash     | Este servicio web es proporcionado por la AEAT. Se utiliza para enviar información sobre transacciones de pagos en efectivo de clientes y envía una respuesta que contiene información sobre el procesamiento en el lado del sistema SII.        | `https://www7.aeat.es/wlpl/SSII-FACT/ws/pm/SiiFactCMV1SOAP`  |

Las direcciones de Internet están sujetas a cambios por la AEAT. Por lo tanto, le recomendamos que compruebe las direcciones de Internet reales en el [sitio web oficial del sistema SII](https://www.agenciatributaria.es/AEAT.internet/en_gb/SII.html). La documentación oficial también tiene información sobre las direcciones de Internet de *producción* reales que debe configurar.

6.  En la pestaña **General**, en el campo **Certificado de Key Vault** seleccione el certificado de seguridad que configuró para todos los servicios Web que utilizará para la interactuación con el sistema SII: **Factura de clie.**, **Factura de prov.**, **Intracomunitario**, **Pago de clie.**, **Pago de prov.** y **CollectionInCash**.

![Página de configuración de los servicios Web](media/emea-esp-sii-setup-key-vault-certificate.png)

## <a name="set-up-em-parameters-for-the-sii-system"></a>Configurar los parámetros de EM para el sistema SII

Después de importar las entidades de datos a la base de datos, complete las siguientes tareas. Cuando los haya completado, la funcionalidad de la mensajería electrónica estará lista para usar.

1.  Configure los parámetros de clase ejecutables.
2.  Configure los campos adicionales y reglas definidas automáticamente.
3.  Configure secuencias numéricas para mensajes electrónicos.
4.  Configure la configuración por lotes para el procesamiento automatizado de la interoperación con el sistema SII.
5.  Configure los roles de seguridad para el procesamiento de mensajes electrónicos.

## <a name="set-up-executable-class-parameters"></a>Configurar los parámetros de clase ejecutables

Se incluyen tres clases ejecutables en los dos tipos de procesamiento de mensajería electrónica (**SII** y **CollectionInCash**) que se utilizan para interactuar con el sistema SII e importados al sistema mediante un paquete de entidades de datos.

| **Nombre de la clase ejecutable**    | **Descripción**                                                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SIIGenerateItems             | Esta clase completa elementos de EM de los siguientes tipos:                                                                                                        |
| EvaluaciónAtributosParteSII | Para elementos EM rellenados (en estado **Creado**), esta clase evalúa los valores para los siguientes campos adicionales:                                         |
| MonitorCollectionInCash      | Esta clase supervisa los cambios en los datos de los registros del informe **Cobro en efectivo** y luego actualiza el estado de los elementos de EM de la manera adecuada. |

-   Factura de cliente (FacturasСliente)
-   Factura de proveedor (FacturasProveedores)
-   Pago de cliente (PagosCliente)
-   Pago de proveedor (PagosProveedores)
-   Operaciones intracomunitarias (OperacionesIntracomunitarias)

Para elementos EM rellenados, esta clase evalúa los valores para los siguientes campos adicionales:

-   Tipo de factura (TipoFactura)
-   Referencia de resumen (NumSerieFactura)
-   Código de esquema especial (ClaveRegimenEspecialOTrascendencia)
-   Id. de transacción intracomunitaria (TipoOperacion)
-   Número de registro (ID)
-   Tipo Id. de impuesto (TipoID)
-   Código ISO de la parte (CodigoPaís)

### <a name="set-up-the-siigenerateitems-executable-class"></a>Configurar la clase ejecutable SIIGenerateItems

1.  Para configurar los parámetros de la clase ejecutable **SIIGenerateItems**, vaya a **Impuesto \> Configuración \> Mensajería electrónica \> Configuración de clase ejecutable**.
2.  En la página **Configuración de clase ejecutable**, seleccione la clase ejecutable **SIIGenerateItems** que está asociada con el nombre de clase ejecutable **EMCreateItemsController**.
3.  En el Panel de acciones, seleccione **Parámetros** y, luego, en el cuadro de diálogo que aparece, establezca los siguientes valores para los parámetros de la clase ejecutable.

| **Nombre del parámetro**            | **Valor**                          |
|-------------------------------|------------------------------------|
| Tipo de factura                  | TipoFactura                        |
| Referencia de resumen             | NumSerieFactura                    |
| Código especial del esquema           | ClaveRegimenEspecialOTrascendencia |
| El Id. de la operación intracomunitaria | TipoOperacion                      |
| Facturas del cliente             | FacturasСliente                    |
| Pagos del cliente             | PagosCliente                       |
| Facturas de proveedores               | FacturasProveedores                |
| Pagos a proveedores               | PagosProveedores                   |
| Operaciones intracomunitarias     | Operaciones intracomunitarias       |

4.  Seleccione **Aceptar** para iniciar la clase ejecutable.

![Agregar nuevo panel de elementos de mensajería electrónica](media/emea-esp-sii-siigenerateitems-executable-class.png)

### <a name="set-up-the-siipartyattributesevaluation-executable-class"></a>Configurar la clase ejecutable SIIPartyAttributesEvaluation

1.  Para configurar los parámetros de la clase ejecutable **SIIPartyAttributesEvaluation**, vaya a **Impuesto \> Configuración \> Mensajería electrónica \> Configuración de clase ejecutable**.
2.  En la página **Configuración de clase ejecutable**, seleccione la clase ejecutable **SIIPartyAttributesEvaluation** que está asociada con el nombre de clase ejecutable **EMAdditionalFieldsEvaluationController_ES**.
3.  En el Panel de acciones, seleccione **Parámetros** y, luego, en el cuadro de diálogo que aparece, establezca los siguientes valores para los parámetros de la clase ejecutable.

| **Nombre del parámetro**  | **Valor**  |
|---------------------|------------|
| Número de registro | Id         |
| Tipo de id. de impuesto         | IDType     |
| Código ISO de parte      | CodigoPaís |

4.  Seleccione **Aceptar** para iniciar la clase ejecutable.

![Agregar el panel de parámetros de evaluación de campos](media/emea-esp-sii-siipartyattributesevaluation-executable-class.png)

### <a name="set-up-the-monitorcollectionincash-executable-class"></a>Configurar la clase ejecutable MonitorCollectionInCash

1.  Para configurar los parámetros de la clase ejecutable **MonitorCollectionInCash**, vaya a **Impuesto \> Configuración \> Mensajería electrónica \> Configuración de clase ejecutable**.
2.  En la página **Configuración de clase ejecutable**, seleccione la clase ejecutable **MonitorCollectionInCash** que está asociada con el nombre de clase ejecutable **EMCheckChangesCollectionInCashController_ES**.
3.  En el Panel de acciones, seleccione **Parámetros** y, luego, en el cuadro de diálogo que aparece, establezca los siguientes valores para los parámetros de la clase ejecutable.

| **Nombre del parámetro** | **Valor**            |
|--------------------|----------------------|
| Cancelación pendiente     | CancelaciónPendiente |
| Corregido          | Corregido            |

4.  Seleccione **Aceptar** para iniciar la clase ejecutable.

![Cobros de SII en el panel de parámetros de supervisión de efectivo](media/emea-esp-sii-monitorcollectionincash-executable-class.png)

## <a name="set-up-additional-fields-and-automatically-defined-rules"></a>Configurar los campos adicionales y reglas definidas automáticamente

Los elementos de EM tienen campos adicionales que se incluyen tres clases ejecutables en los dos tipos de procesamiento de mensajería electrónica (**SII** y **CollectionInCash**) que se utilizan para interactuar con el sistema SII e importados al sistema mediante un paquete de entidades de datos. Los campos adicionales están asociados con elementos de EM y son necesarios para su procesamiento. El sistema establece automáticamente valores para campos adicionales cuando se ejecutan acciones, pero puede establecer y ajustar manualmente los valores de campos adicionales antes de enviar la información al sistema de SII. Los campos adicionales se nombran de acuerdo con elementos relacionados del informe. Para obtener más información sobre qué es cada elemento de informe relacionado, consulte la [documentación oficial para el sistema SII](https://www.agenciatributaria.es/AEAT.internet/en_gb/SII.html).

| **Campo adicional**               | **Descripción**                | **Tipo de procesamiento donde se usa el campo**                                                                                                                                                 | **Clase de acción o clase ejecutable según la se que establece el campo**                                                                                                                                                                                                                                                               |
|------------------------------------|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| TipoComunicacion                   | Tipo de comunicación             | **SII** y **CollectionInCash**. Este campo solo es aplicable a los tipos de elemento de EM **FacturasСliente**, **FacturasProveedores**, **Operaciones intracomunitarias** y **CobrosEnMetálico**. | Acción **GenerateMessageItem** para el procesamiento de **SII**. El valor predeterminado es **A0**. El valor se actualiza a **A1** durante la importación de la respuesta por la acción **ImportResponse** cuando la factura es aceptada con éxito por el sistema SII. Acción **PopulateMessageItem** para el procesamiento **CollectionInCash**. |
| Id                                 | Id. de registro                | **SII** y **CollectionInCash**. Este campo adicional es aplicable a todos los tipos de elementos de EM.                                                                                                    | Acción **Campos de evaluación**, clase ejecutable **SIIPartyAttributesEvaluation**.                                                                                                                                                                                                                                    |
| IDType                             | Tipo de ID de contrapartida           | **SII** y **CollectionInCash**. Este campo es aplicable a todos los tipos de elementos de EM.                                                                                                               | Acción **Campos de evaluación**, clase ejecutable **SIIPartyAttributesEvaluation**.                                                                                                                                                                                                                                    |
| CodigoPaís                         | Código ISO                       | **SII** y **CollectionInCash**. Este campo es aplicable a todos los tipos de elementos de EM.                                                                                                               | Acción **Campos de evaluación**, clase ejecutable **SIIPartyAttributesEvaluation**.                                                                                                                                                                                                                                    |
| ClaveRegimenEspecialOTrascendencia | Código especial del esquema            | Solo **SII**. Este campo solo es aplicable a los tipos de elemento de EM **FacturasСliente**, **FacturasProveedores**.                                                                              | Acción **GenerateMessageItem**, clase ejecutable **SIIGenerateItems**. El valor predeterminado es **01**. La configuración de las reglas definidas automáticamente está disponible.                                                                                                                                                                   |
| NumSerieFactura                    | Referencia de resumen              | Solo **SII**. Este campo solo es aplicable a los tipos de elemento de EM **FacturasСliente**, **FacturasProveedores**.                                                                              | Acción **GenerateMessageItem**, clase ejecutable **SIIGenerateItems**.                                                                                                                                                                                                                                             |
| TipoFactura                        | Tipo de factura                   | Solo **SII**. Este campo solo es aplicable a los tipos de elemento de EM **FacturasСliente**, **FacturasProveedores**.                                                                               | Acción **GenerateMessageItem**, clase ejecutable **SIIGenerateItems**. El valor predeterminado es **01**. La configuración de las reglas definidas automáticamente está disponible.                                                                                                                                                                   |
| TipoOperacion                      | Tipo de operación intracomunitaria | Solo **SII**. Este campo solo es aplicable al tipo de elemento de EM **Operaciones intracomunitarias**.                                                                                              | Definición manual. El valor predeterminado es **A**. La configuración de las reglas definidas automáticamente está disponible y se puede aplicar durante la ejecución de la acción **GenerateMessageItem**.                                                                                                                                              |
| EmitidaPorTerceros                 | Emitido por terceros        | Solo **SII**. Este campo solo es aplicable al tipo de elemento de EM **FacturasСliente**.                                                                                                           | Solo definición manual. El valor predeterminado es **N**. La configuración de las reglas definidas automáticamente está disponible.                                                                                                                                                                                                                   |
| EntidadSucedidaNIF                 | Id. de impuesto de entidad jurídica correcta  | Solo **SII**. Este campo solo es aplicable a los tipos de elemento de EM **FacturasСliente**, **FacturasProveedores** y **OperacionesIntracomunitarias**.                                           | Definición manual. La configuración de las reglas definidas automáticamente está disponible.                                                                                                                                                                                                                                                    |
| EntidadSucedidaNombreRazon         | Nombre de entidad jurídica correcta    | Solo **SII**. Este campo solo es aplicable a los tipos de elemento de EM **FacturasСliente**, **FacturasProveedores** y **OperacionesIntracomunitarias**.                                           | Definición manual. La configuración de las reglas definidas automáticamente está disponible.                                                                                                                                                                                                                                                    |
| ReferenciaCatastral                | Referencia catastral            | Solo **SII**. Este campo solo es aplicable al tipo de elemento de EM **FacturasСliente**.                                                                                                           | Definición manual. La configuración de las reglas definidas automáticamente está disponible.                                                                                                                                                                                                                                                    |
| SituacionInmueble                  | Ubicación de la propiedad              | Solo **SII**. Este campo solo es aplicable al tipo de elemento de EM **FacturasСliente**.                                                                                                           | Definición manual. La configuración de las reglas definidas automáticamente está disponible.                                                                                                                                                                                                                                                    |

### <a name="algorithm-to-define-the-value-of-the-tipocomunicacion-communication-type-additional-field"></a>Algoritmo para definir el valor del campo adicional TipoComunicacion (Tipo de comunicación)

El campo adicional **TipoComunicacion** (**Tipo de comunicación**) se define automáticamente por el sistema para los elementos de mensaje de los tipos **FacturasСliente**, **FacturasProveedores**, **Operaciones intracomunitarias** y **CobrosEnMetálico**. Para obtener una lista de los valores que se pueden asignar a **TipoComunicacion**, consulte la [documentación oficial para el sistema SII](https://www.agenciatributaria.es/AEAT.internet/en_gb/SII.html).

Los siguientes valores están disponibles para el campo adicional **TipoComunicacion** como parte de la configuración predefinida para la mensajería electrónica.

| **Valor de campo** | **Descripción (español)**                                | **Descripción (inglés)** |
|-----------------|----------------------------------------------------------|---------------------------|
| A0              | Alta de facturas y registro                                | Registro de factura      |
| A1              | Modificación de facturas y registros (errores registrales) | Modificación de facturas  |

El valor predeterminado del campo adicional **TipoComunicacion** se define como **A0** en la ficha desplegable **Campos adicionales del elemento de mensaje** en la definición del procesamieto de **SII** y **CollectionInCash** (**Impuesto \> Configuración \> Procesamiento de mensajería electrónica \>Procesamiento de mensajería electrónica**). Más tarde, cuando Finance recibe una respuesta del sistema SII de que la factura fue aceptada correctamente, el valor **TipoComunicacion** se actualiza a **A1** por la acción **ImportResponse**.

### <a name="algorithm-to-define-the-value-of-the-id-registration-id-additional-field"></a>Algoritmo para definir el valor del campo adicional ID (Id. de registro)

El campo adicional **ID** (**Id. de registro**) se define automáticamente por el sistema para elementos de EM de todo tipo durante la evaluación de campos adicionales. Para las contrapartidas que se registraron para el IVA fuera de España, el valor del campo adicional **ID** se notifica en la etiqueta **ID** etiqueta debajo de la etiqueta **IDOtro** del informe. Para las contrapartidas de España, el valor se informa en la etiqueta **NIF**.

El valor del campo adicional **ID** se define por la acción **EvaluationFields** que está asociada con la clase ejecutable **SIIPartyAttributesEvaluation**. Esta clase recupera el número de identificación fiscal que se especifica para la factura durante la contabilización de la factura. Si el número de identificación fiscal no se especifica para una factura antes de la contabilización, el sistema recopila e valor del campo adicional **ID** del campo **Número de identificación fiscal** en los datos maestros de la contrapartida.

Para las contrapartidas de la UE o fuera de la UE, el campo adicional **ID** se complementará con el código ISO relacionado.

### <a name="algorithm-to-define-the-idtype-counterparty-id-type-additional-field"></a>Algoritmo para definir el campo adicional IDType (tipo de Id. de la contrapartida)

El campo adicional **IDType** (**Tipo de Id. de la contrapartida**) se define automáticamente por el sistema para elementos de EM de todo tipo durante la evaluación de campos adicionales. Para la lista de los valores que se pueden establecer para **IDType**, consulte la [documentación oficial para el sistema SII](https://www.agenciatributaria.es/AEAT.internet/en_gb/SII.html).

Los siguientes valores están disponibles para el campo adicional **IDType** como parte de la configuración predefinida para la mensajería electrónica.

| **Valor de campo** | **Descripción**                                                                |
|-----------------|--------------------------------------------------------------------------------|
| 02              | NIF-IVA                                                                        |
| 03              | Pasaporte                                                                       |
| 04              | Documento de identificación oficial emitido por el país o región de residencia. |
| 05              | Certificado de residencia                                                          |
| 06              | Otro documento de apoyo                                                      |
| 07              | No registrado                                                                 |

El valor del campo adicional **IDType** se informa en la etiqueta **IDType** debajo de la etiqueta **IDOtro** del informe.

De forma predeterminada, para las contrapartidas fuera de España, cuando el **Id. de registro** no está definido en los datos maestros de la contrapartida, el sistema define los siguientes valores para el campo adicional **Tipo de identificación**:

-   **02** - Para contrapartidas de la UE
-   **04** - Para contrapartidas de terceros países

Cuando **Id. de registro** se define en los datos maestros de la contrapartida, el sistema analiza los siguientes tipos de **Id. de registro**:

1.  Para los contratistas españoles:

    `TaxRegistrationTypesList::NotCensused`

    `TaxRegistrationTypesList::TAXID`

2.  Para contratistas de la UE:

    `TaxRegistrationTypesList::TAXID`

    `TaxRegistrationTypesList::OfficialIdDoc`

    `TaxRegistrationTypesList::Passport`

    `TaxRegistrationTypesList::ResidenceCertificate`

    `TaxRegistrationTypesList::OtherIdDoc`

3.  El resto de contratistas:

    `TaxRegistrationTypesList::OfficialIdDoc`

    `TaxRegistrationTypesList::Passport`

    `TaxRegistrationTypesList::ResidenceCertificate`

    `TaxRegistrationTypesList::OtherIdDoc`

Como resultado de este análisis, el sistema define el **IDType** relacionado.

| **Tipo de registro de impuestos** | **IDType en el sistema SII**                                                                |
|-----------------|--------------------------------------------------------------------------------|
| `TaxRegistrationTypesList::TAXID`| 02                                                                         |
| `TaxRegistrationTypesList::Passpor`| 03                                                                       |
| `TaxRegistrationTypesList::OfficialIdDoc`| 04                                                                 |
| `TaxRegistrationTypesList::ResidenceCertificate`| 05                                                          |
| `TaxRegistrationTypesList::OtherIdDoc`| 06                                                                       |
| `TaxRegistrationTypesList::NotCensused`| 07                                                                       |

A veces, cuando el número de identificación fiscal (NIF) de un contratista español no se puede encontrar en la base de datos del sistema SII, el sistema SII no puede aceptar una factura. Al mismo tiempo, una factura de cliente donde el contratista no esté registrado en la base de datos del sistema SII se puede enviar al sistema SII cuando el número de identificación fiscal relacionado del contratistas aparezca en la etiqueta **IdOtro** usando un valor **Tipo de identificación** de **07**. En este caso, el sistema SII "aceptará con errores" la factura.

Puede ajustar manualmente el valor del campo adicional **IDType** antes de enviar la factura al sistema SII.

### <a name="algorithm-to-define-the-codigopais-iso-code-additional-field"></a>Algoritmo para definir el campo adicional CodigoPaís (código ISO)

El campo adicional **CodigoPaís** (**Código ISO**) se define automáticamente por el sistema para elementos de EM de todo tipo durante la evaluación de campos adicionales. El valor del campo adicional **CodigoPaís** se informa en la etiqueta **CodigoPaís** debajo de la etiqueta **IDOtro** del informe e identifica el país o región del número de registro de impuestos de la contrapartida del documento.

De forma predeterminada, el sistema define el valor del campo adicional **CodigoPaís** como código de condado o región de la Organización internacional de normalización (ISO) desde la dirección principal de la contrapartida.

### <a name="algorithm-to-define-the-numseriefactura-summary-reference-additional-field"></a>Algoritmo para definir el campo adicional NumSerieFactura (Resumen de referencia)

El camp adicional **NumSerieFactura** (**Resumen de referencia**) se define automáticamente por el sistema solo para los elementos de EM del tipo **FacturasСliente**. El valor del campo adicional **NumSerieFactura** se notifica en la etiqueta **NumSerieFacturaEmisorResumenFin** para facturas resumidas. Para las facturas de los clientes, recoge el valor del último vale (**Id. del recibo**) que está relacionado con la factura en el informe del módulo **Comercial**. Alternativamente, se rellena con el número de documento de la factura. (Por lo tanto, la factura no es una factura resumida). Si el valor del campo adicional **NumSerieFactura** difiere del valor en el número de documento del elemento del mensaje, la factura se notifica como resumida (es decir, **\<NumSerieFacturaEmisorResumenFin\>** se imprime). El valor del campo adicional **NumSerieFactura** se puede actualizar manualmente según sea necesario. Si informa de una factura como factura resumida, asegúrese de que el valor del campo **TipoFactura** se actualiza a **F4**.

### <a name="algorithm-to-define-the-tipofactura-invoice-type-additional-field"></a>Algoritmo para definir el campo adicional TipoFactura (tipo de la factura)

El camp adicional **TipoFactura** (**Tipo de la factura**) se define automáticamente por el sistema solo para los elementos de EM de los tipos **FacturasСliente** y **FacturasProveedores**. Para la lista de los valores que se pueden establecer para **TipoFactura**, consulte la [documentación oficial para el sistema SII](https://www.agenciatributaria.es/AEAT.internet/en_gb/SII.html).

Los siguientes valores están disponibles para el campo adicional **TipoFactura** como parte de la configuración predefinida para la mensajería electrónica.

| **Valor de campo** | **Descripción (español)**                                                        | **Descripción (inglés)**                                                | **Algoritmo**                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------|--------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| F1              | Factura                                                                          | Factura                                                                  | Este valor es el valor predeterminado para todas las facturas si no se aplica una lógica específica para una factura determinada. El valor se puede editar manualmente.  |
| F2              | Factura simplificada (vale)                                                    | Factura simplificada                                                       | Este valor se puede aplicar manualmente a una factura.\*.                                                                                      |
| F3              | Factura emitida en sustitución de facturas simplificadas facturadas y declaradas | Factura emitida para reemplazar las facturas simplificadas facturadas y declaradas      | Este valor se puede aplicar manualmente a una factura.\*.                                                                                      |
| F4              | Asiento resumen de facturas                                                      | Asiento de resume de factura                                                    | Si el sistema identifica que la factura se crea como una factura resumida del módulo **Comercial**. Este valor se puede editar manualmente. |
| F5              | Importaciones (DUA)                                                              | Importaciones (DUA)                                                            | Este valor se puede aplicar manualmente a una factura.\*.                                                                                      |
| F6              | Justificantes contables                                                          | Documentos justificativos contables                                          | Este valor se puede aplicar manualmente a una factura.\*.                                                                                      |
| LC              | Aduanas - Liquidación complementaria                                             | Aduanas - Liquidación complementaria                                        | Este valor se puede aplicar manualmente a una factura.\*.                                                                                      |
| R1              | Factura Rectificativa (Error fundado en derecho y Art. 80 uno, dos y seis LIVA)  | Factura rectificativa (error basado en la ley y el art. 80 uno, dos y seis LIVA) | Este valor se puede aplicar manualmente a una factura.\*.                                                                                      |
| R2              | Factura rectificativa (Art. 80.3)                                                | Factura rectificativa (Art. 80.3)                                           | Este valor se puede aplicar manualmente a una factura.\*.                                                                                      |
| R3              | Factura rectificativa (Art. 80.4)                                                | Factura rectificativa (Art. 80.4)                                           | Este valor se puede aplicar manualmente a una factura.\*.                                                                                      |
| R4              | Factura rectificativa (resto)                                                    | Factura rectificativa (rest)                                                | Este valor se puede aplicar manualmente a una factura.\*.                                                                                      |
| R5              | Factura rectificativa en facturas simplificadas                                  | Factura rectificativa en facturas simplificadas                                | Este valor se puede aplicar manualmente a una factura.\*.                                                                                      |

\* Hay tres formas de definir un tipo de factura específico:

-   Durante el registro de la factura, antes de contabilizarla, aplicando un motivo financiero a la factura
-   Estableciendo reglas para valores de campo adicionales
-   Durante la revisión de facturas manual en elementos de EM antes de que se envíen al sistema SII

El sistema define el valor del campo adicional **TipoFactura** de acuerdo con el siguiente algoritmo:

1.  Defina el tipo de factura de acuerdo con el código de razón financiera en el documento.
2.  Si el tipo de factura no está definido en el paso 1, verifique si el valor es **F4** (factura resumida).
3.  Si el tipo de factura no se define en el paso 2, defínalo de acuerdo con la configuración de los valores de campo adicionales.
4.  Si el tipo de factura no está definido en el paso 3, establezca el valor en **F1**.

Se pueden especificar razones financieras para las facturas que se contabilizan a partir de los siguientes documentos:

-   Pedido de ventas
-   Factura de servicios
-   Pedido de compra
-   Proyectos
-   Diario de proveedores (AP)
-   Contabilidad general (GL), diario general

Cuando puede crear una factura a partir de los tipos de documentos a partir de los cuales se pueden crear facturas, puede establecer un motivo específico para la factura. La acción **GenerateMessageItem** analizará este motivo y se establecerá el código de SII para el elemento del mensaje electrónico.

Siga estos pasos para configurar motivos financieros.

1.  Vaya a **Administración de la organización \> Configuración \> Motivos financieros**.
2.  Seleccione una línea existente o cree una nueva.
3.  En la columna **Tipo de factura**, seleccione el código que sea aplicable al sistema SII.
4.  En la columna **Descripción del código SII** agregue una descripción. Esta descripción no se utilizará en los informes, pero podría ayudar a los usuarios a seleccionar el motivo financiero apropiado.

Para permitir que el sistema defina el tipo de factura en función de la configuración de valores de campo adicionales, siga estos pasos para definir las reglas.

1.  Vaya a **Impuestos \> Configuración \> Mensajes electrónicos \> Campos adicionales**.
2.  En la lista de campos adicionales a la izquierda, seleccione **TipoFactura**.
3.  En la ficha desplegable **Valor**, especifique criterios:

    -   **Tipo de cuenta**: seleccione **Cliente** o **Proveedor**.
    -   **Código de cuenta**: seleccione **Todos**, **Grupo**, **Tabla**.
    -   **Número de grupo/cuenta**
    -   **Grupo de impuestos sobre las ventas**
    -   **Grupo de impuestos de artículos**

     También puede especificar fechas de vigencia y vencimiento para su regla.

### <a name="algorithm-to-define-the-tipooperacion-intra-community-operation-type-additional-field"></a>Algoritmo para definir el valor del campo adicional TipoOperacion (Tipo de operación intracomunitaria)

El camp adicional **TipoOperacion** (**Tipo de operación intracomunitaria**) se define automáticamente por el sistema solo para los elementos de EM del tipo **OperacionesIntracomunitarias**. Para la lista de los valores que se pueden establecer para **TipoOperacion**, consulte la [documentación oficial para el sistema SII](https://www.agenciatributaria.es/AEAT.internet/en_gb/SII.html).

Los siguientes valores están disponibles para el campo adicional **TipoOperacion** como parte de la configuración predefinida para la mensajería electrónica.

| **Valor de campo** | **Descripción (español)**                                                                                                                                                             | **Descripción (inglés)**                                                                                                                          |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| C               | El envío o recepción de bienes para la realización de los informes parciales o trabajos mencionados en el artículo 70, apartado uno, número 7º, de la Ley del Impuesto (Ley 37/1992). | El envío o recepción de bienes para la realización de los informes parciales o trabajos mencionados en el artículo 70, apartado 1, número 7º, de la Ley del Impuesto (Ley 37/1992). |
| mil millones               | Las transferencias de bienes y las adquisiciones intracomunitarias de bienes comprendidas en los artículos 9, apartado 3º, y 16, apartado 2º, de la Ley del Impuesto (Ley 37/1992).   | Las transferencias de bienes y las adquisiciones intracomunitarias de bienes comprendidas en los artículos 9, apartado 3º, y 16, apartado 2º, de la Ley del Impuesto (Ley 37/1992).   |

El valor predeterminado del campo adicional **TipoOperacion** se define como **A** en la ficha desplegable **Campos adicionales del elemento de mensaje** en la definición del procesamiento de **SII** y (**Impuesto \> Configuración \> Mensajería electrónica \> Procesamiento de mensajería electrónica**).

Para permitir que el sistema defina el tipo de operación intracomunitaria en función de la configuración de valores de campo adicionales, siga estos pasos para definir las reglas.

1.  Vaya a **Impuestos \> Configuración \> Mensajes electrónicos \> Campos adicionales**.
2.  En la lista de campos adicionales a la izquierda, seleccione **TipoOperacion**.
3.  En la ficha desplegable **Valor**, especifique criterios:

    -   **Tipo de cuenta**: seleccione **Cliente** o **Proveedor**.
    -   **Código de cuenta**: seleccione **Todos**, **Grupo** o **Tabla**.
    -   **Número de grupo/cuenta**
    -   **Grupo de impuestos sobre las ventas**
    -   **Grupo de impuestos de artículos**

    También puede especificar fechas de vigencia y vencimiento para su regla.

### <a name="set-up-automatically-defined-rules-for-the-claveregimenespecialotrascendencia-special-scheme-code-additional-field"></a>Configurar reglas definidas automáticamente para el campo adicional ClaveRegimenEspecialOTrascendencia (código de esquema especial)

El campo adicional **ClaveRegimenEspecialOTrascendencia** (**Código de esquema especial**) se define automáticamente por el sistema para los elementos de mensaje de los tipos **FacturasСliente** y **FacturasProveedores**. Para la lista de los valores que se pueden establecer para **ClaveRegimenEspecialOTrascendencia**, consulte la [documentación oficial para el sistema SII](https://www.agenciatributaria.es/AEAT.internet/en_gb/SII.html).

De acuerdo con la documentación oficial del sistema SII, los siguientes valores están disponibles para el campo adicional **ClaveRegimenEspecialOTrascendencia** como parte de la configuración predefinida de mensajes electrónicos.

| **Valor de campo** | **Descripción**                                                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 01              | Transacción general del sistema                                                                                                                                                                                                                   |
| 02              | Exportar                                                                                                                                                                                                                                       |
| 02              | Transacciones por las cuales los empresarios pagan una compensación por comprar a personas bajo el Sistema especial para actividades agrícolas, ganaderas y pesqueras.                                                                      |
| 03              | Transacciones a las que se aplica el sistema especial de bienes usados, obras de arte, antigüedades y coleccionables.                                                                                                                                 |
| 04              | Sistema especial para inversión de oro.                                                                                                                                                                                                          |
| 05              | Sistema especial para agencias de viajes.                                                                                                                                                                                                          |
| 06              | Sistema especial aplicable a grupos de entidades e IVA (avanzado).                                                                                                                                                                          |
| 07              | Sistema especial de efectivo.                                                                                                                                                                                                                   |
| 08              | Transacciones sujetas a IPSI/IGIC (Impuesto sobre Producción, Servicios e Importaciones/Impuesto General Indirecto de Canarias).                                                                                                                         |
| 09              | Facturación de la prestación de servicios de agencia de viajes que actúan como intermediarios en nombre de otras personas (Disposición adicional 4, RD1619/2012).                                                                           |
| 10              | Cobros en nombre de terceros de honorarios profesionales o propiedad industrial, derechos de autor u otros derechos similares por parte de socios, asociados o miembros realizados por empresas, asociaciones, organizaciones profesionales u otras entidades. |
| 11              | Actividades de arrendamiento de locales comerciales sujetos a retención.                                                                                                                                                                                   |
| 12              | Actividades de arrendamiento de locales comerciales no sujetos a retención.                                                                                                                                                                               |
| 13              | Actividades de arrendamiento de locales comerciales sujetas y no sujetas a retención/Factura correspondiente a una importación (notificada sin estar asociada con un DUA).                                                                                 |
| 14              | Factura con IVA pendiente de devengo sobre certificaciones de trabajo con destinatarios de la Administración Pública para el primer semestre de 2017.                                                                                                                    |
| 15              | Factura con IVA pendiente de devengo en transacciones de naturaleza consecutiva.                                                                                                                                                                    |
| 16              | Primer semestre de 2017.                                                                                                                                                                                                                             |

Puede configurar reglas definidas automáticamente para cualquier valor de la lista anterior. También puede ajustar la lista de posibles valores. Para las reglas definidas automáticamente, están disponibles los siguientes criterios:

-   **Tipo de cuenta**: seleccione **Todo**, **Cliente** o **Proveedor**.
-   **Código de cuenta**: seleccione **Todos**, **Grupo** o **Tabla**.

> [!NOTE]
> Puede especificar este criterio solo cuando **Tipo de cuenta** está configurado para **Cliente** o **Proveedor**.

-   **Número de grupo/cuenta**

> [!NOTE]
> Puede especificar este criterio solo cuando **Código de cuenta** está configurado para **Grupo** o **Tabla**.

-   **Grupo de impuestos sobre las ventas**

-   **Grupo de impuestos de artículos**

También puede especificar fechas de vigencia y vencimiento para su regla.

El algoritmo que se utiliza para buscar el código de esquema especial para el registro consta de tres etapas:

1.  Buscar entre registros donde **Código de cuenta** se establece en **Tabla** para el cliente o proveedor.
2.  Si el registro no se encuentra en la etapa 1, busque entre los registros donde **Código de cuenta** se establece en **Grupo** para el cliente o proveedor.
3.  Si el registro no se encuentra en la etapa 2, busque entre los registros donde **Código de cuenta** se establece en **Todo** para el cliente o proveedor.

Durante la búsqueda en cada etapa, se consideran las fechas válidas de los registros y solo se deben seleccionar los registros que sean válidos en la fecha de registro.

Cuando las columnas **Grupo de impuestos de ventas** y **Grupo de impuestos de ventas de artículos** se utilizan en la configuración, el algoritmo sigue siendo el mismo, ya que todavía contiene tres etapas principales. Sin embargo, la búsqueda durante cada etapa es diferente. Cuando el sistema busca el código de esquema especial para el registro en cada etapa, ahora se considera el grupo de impuestos de ventas y el grupo de impuestos de ventas de artículos. Para obtener el grupo de impuestos de ventas y el grupo de impuestos de ventas de artículos para la factura, el sistema selecciona la primera transacción de impuestos que está relacionada con la factura actual del cliente, proveedor o proyecto. El grupo de impuestos de ventas y el grupo de impuestos de ventas de artículos se pasan luego como parámetros al método para buscar códigos de esquema especiales.

La búsqueda por **Grupo de impuestos de ventas** y **Grupo de impuestos de ventas de artículos** se puede dividir en cuatro subetapas. Las cuatro subetapas se implementan para cada una de las tres etapas que se mencionaron anteriormente, hasta que se encuentre un registro adecuado.

1.  Busque un registro donde los campos **Grupo de impuestos de ventas** y **Grupo de impuestos de ventas de artículos** tengan un valor y los valores coincidan con los valores que se pasaron como parámetros.
2.  Si no se encuentra ningún registro en la subetapa 1, busque un registro donde el valor de **Grupo de impuestos de ventas** coincida con el grupo de impuestos sobre las ventas que se pasó como parámetro, pero que el campo **Grupo de impuestos de ventas de artículos**. (Un campo en blanco representa "cualquiera").
3.  Si no se encuentra ningún registro en la subetapa 2, busque un registro donde el valor de **Grupo de impuestos de ventas** esté vacío, pero que el valor de **Grupo de impuestos de ventas de artículos** coincida con el grupo de impuestos sobre las ventas que se pasó como parámetro.
4.  Si no se encuentra ningún registro en la subetapa 3, busque un registro donde ambos campos **Grupo de impuestos de ventas** y el **Grupo de impuestos de ventas de artículos** estén en blanco.

La siguiente ilustración muestra el esquema del algoritmo para cada una de estas cuatro subetapas.

![Esquema de algoritmo para las subetapas](media/emea-esp-sii-claveregimenespecialotrascendencia-additional-field.png)

## <a name="set-up-number-sequences-for-electronic-messages"></a>Configurar secuencias numéricas para mensajes electrónicos

Para trabajar con la funcionalidad de mensajes electrónicos, debe definir secuencias numéricas relacionadas.

1.  Vaya a **Impuestos** \> **Configuración** \> **Parámetros de contabilidad general**.
2.  En la pestaña **Secuencias numéricas**, configure dos secuencias numéricas:

-   Mensaje
-   Elemento de mensaje

## <a name="set-up-batch-settings-for-automated-processing-of-interoperation-with-the-sii-system"></a>Configurar la configuración por lotes para el procesamiento automatizado de la interoperación con el sistema SII

1.  Vaya a **Impuestos \> Configuración \> Mensajes electrónicos \> Procesamiento de mensaje electrónico**.
2.  Seleccionar bien el procesamiento **SII** o **CollectionInCash**.
3.  En la ficha desplegable **Lote**, seleccione **Crear lote**, y luego defina los parámetros requeridos.

## <a name="set-up-security-roles-for-electronic-message-processing"></a>Configure los roles de seguridad para el procesamiento de mensajes electrónicos

Diferentes grupos de usuarios pueden requerir acceso al procesamiento **SII** y **CollectionInCash**. Puede limitar el acceso al procesamiento en función de los grupos de seguridad definidos en el sistema.

Para limitar el acceso al procesamiento **SII** y **CollectionInCash**, siga estos pasos.

1.  Vaya a **Impuestos \> Configuración \> Mensajes electrónicos \> Procesamiento de mensaje electrónico**.
2.  Seleccione el procesamiento **SII** o **CollectionInCash** y luego agregue los grupos de seguridad que deben trabajar con ese procesamiento. Si no se define un grupo de seguridad para el procesamiento, solo un administrador del sistema puede ver el procesamiento en la página **Mensajes electrónicos**.

## <a name="additional-setup-in-finance-for-reporting-to-the-sii-system"></a>Configuración adicional en Finance para informar al sistema SII

### <a name="exclude-transactions-that-have-a-negative-sales-tax-percentage-from-sii-processing"></a>Excluir las transacciones que tienen un porcentaje de impuesto a las ventas negativo del procesamiento de SII

A veces, las empresas en España establecen códigos de impuestos a las ventas que permiten porcentajes de impuestos negativos y que no deben informarse al sistema SII como IVA. Para excluir la presentación de facturas al sistema SII si tienen transacciones fiscales en las que el código de impuesto sobre las ventas permite porcentajes de impuestos negativos, en la sección **Informes** en la pestaña **Libro mayor** de la página **Parámetros del libro mayor** (**Libro mayor \> Preparar \> Parámetros del libro mayor**), seleccione la casilla **Porcentaje de impuestos negativo**.

Si la casilla **Porcentaje de impuestos negativo** está desactivada en la página **Parámetros del libro mayor**, se produce el siguiente comportamiento:

-   Las facturas que solo tienen transacciones de impuestos con porcentajes negativos de impuestos a las ventas no se completarán como elementos de mensajes electrónicos para el procesamiento SII.
-   Solo transacciones de impuestos que tienen códigos de impuestos a las ventas donde cuando la casilla **Porcentaje negativo de impuesto** está desactivada se incluirá en el archivo XML que se informa al sistema SII.

![Página de parámetros del libro mayor, pestaña Libro mayor](media/emea-esp-sii-negative-sales-tax-percentage.png)

La casilla **Porcentaje negativo de impuesto** en la página **Parámetros del libro mayor** no afecta el informe de transacciones de cambio inverso.

### <a name="sales-tax-code-setup-to-identify-different-types-of-000-percent-vat-rates"></a>Configuración del código de impuestos sobre las ventas para identificar diferentes tipos de tasas de IVA del 0,00 por ciento

En España, los códigos de impuestos sobre las ventas que tienen una tasa del 0,00 por ciento se utilizan en algunos escenarios. Los siguientes escenarios deben diferenciarse para poder registrarlos correctamente en el sistema SII:

-   **ImporteTAIReglasLocalizacion**: transacciones en euros que se realizan con otras áreas españolas que no tienen IVA, pero que sí tienen algún otro impuesto indirecto interno (por ejemplo, Canarias, Ceuta y Melilla).
-   I **mportePorArticulos7_14_Otros**: otras transacciones específicas en euros que están sujetas al art. 7.14.

Para informar correctamente los dos escenarios anteriores que involucran una tasa de IVA del 0,00 por ciento, establezca el valor de **Tipo de impuesto** campo para códigos de impuestos de ventas (**Impuesto \> Impuestos indirectos \> Impuesto \> Códigos de impuestos de ventas**) como se explica en la siguiente tabla.

| **Etiqueta en el sistema SII**         | **Tipo de valor impositivo** |
|-------------------------------|-----------------------|
| ImportePorArticulos7_14_Otros | IVA 0 %                |
| ImporteTAIReglasLocalización  | Otros                 |

![Página de códigos de impuestos](media/emea-esp-sii-zero-percent-vat-rates.png)

### <a name="intra-community-sales-tax-reporting-to-the-sii-system"></a>Registrar impuestos de ventas intracomunitarios en el sistema SII

De acuerdo con las reglas del sistema SII, se debe usar un conjunto extendido de parámetros cuando las facturas intracomunitarias se informan al sistema SII. Para enviar información adicional en un formato específico para facturas intracomunitarias, el procesamiento de **SII** Finance llena en el tipo de elemento de mensaje **Operaciones intracomunitarias** para facturas que se informaron previamente como facturas estándar. La acción **GenerateMessageItem** ejecuta la clase ejecutable **SIIGenerateItems**. Según los siguientes criterios, identifica las facturas como facturas del tipo de elemento de mensaje **Operaciones intracomunitarias**:

-   La casilla **Intracomunitario** está seleccionada para el grupo de impuestos sobre las ventas (**Impuesto \> Impuestos \> Grupo de impuestos**) que se utiliza en la transacción del impuesto que está relacionada con la factura. Compruebe que la característica [IVA intracomunitario para España](https://docs.microsoft.com/dynamics365/finance/localizations/emea-esp-intra-community-vat) esté configurada y se utiliza en su sistema.
-   El país o región de la dirección principal de la contrapartida de la factura se identifica como **UE** en la sección **Propiedades del país o región** de la página **Parámetros de comercio exterior** (**Impuesto \> Configuración \> Comercio Exterior \> Parámetros de comercio exterior**).
-   La contrapartida está incluida en la configuración intracomunitaria de SII (vaya a **Impuesto \> Configuración \> Mensajes electrónicos \> Campos adicionales del elemento de mensaje**, y luego, en el campo **TipoOperación**, especifique aquellas contrapartidas para las que las facturas deben registrarse como facturas intracomunitarias).

Para comprobar que configuró correctamente los parámetros para la clase ejecutable **SIIGenerateItes** para el campo adicional **TipoOperación**, siga estos pasos.

1.  Vaya a **Impuesto \> Configuración \> Mensajes electrónicos \> Configuraciones de clase ejecutables**.
2.  Seleccione la clase ejecutable **SIIGenerateItems** que está asociada con el nombre de clase ejecutable **EMCreateItemsController**.
3.  En el Panel de acciones, seleccione **Parámetros**, y luego configure el valor **TipoOperación** para el campo adicional **Id. de operación intracomunitaria**.

## <a name="use-em-functionality-to-report-to-the-sii-system"></a>Usar la funcionalidad EM para notificar al sistema SII

La funcionalidad EM ejecuta automáticamente acciones que se incluyen en el procesamiento (**SII** o **CollectionInCash**), según el estado de los mensajes y los elementos del mensaje.

### <a name="process-for-reporting-invoices-to-the-sii-system"></a>Proceso para registrar facturas en el sistema SII

El paquete **ES SII setup.zip** proporciona la configuración para el procesamiento **SII** en la funcionalidad EM que admite la interactuación con el sistema SII. La siguiente ilustración muestra el esquema general del procesamiento **SII**. Las acciones manuales del usuario no se incluyen en esta ilustración, pero se explican más adelante en este tema.

![Esquema para el procesamiento general de SII](media/emea-esp-sii-process.png)

### <a name="actions-of-sii-processing"></a>Acciones de procesamiento de SII

La siguiente tabla describe las acciones generales del procesamiento **SII**.

| **Acción**           | **Tipo de acción**              | **Descripción**                                                                                                                                                                                                                                                                                                                                  |
|----------------------|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| GenerateMessageItem  | Nivel de ejecución de mensaje      | Esta acción ejecuta la clase ejecutable **SIIGenerateItems** para generar elementos EM para facturas emitidas y recibidas, elementos EM para facturas intracomunitarias y elementos EM relacionados con facturas emitidas y recibidas donde **Código de esquema especial** se establece en **07**. Se requiere la configuración del parámetro clase ejecutable **SIIGenerateItems**. |
| EvaluationFields     | Nivel de ejecución de artículo de mensaje | Esta acción ejecuta la clase ejecutable **SIIPartyAttributesEvaluation** para calcular los valores de los campos adicionales **ID**, **IDType** y **CódigoPaís** para elementos de EM. Se requiere la configuración del parámetro clase ejecutable **SIIPartyAttributesEvaluation**.                                                                              |
| GenerateMessageCI    | Exportación de informes electrónicos  | Esta acción ejecuta el **Formato de factura emitida SII (ES)** para crear un paquete de facturas (elementos EM del tipo **FacturasСliente**) que se puede enviar al sistema SII. De forma predeterminada, el paquete contiene 10 000 facturas.                                                                                                             |
| GenerateMessageVI    | Exportación de informes electrónicos  | Esta acción ejecuta el **Formato de factura recibida SII (ES)** para crear un paquete de facturas (elementos EM del tipo **FacturasProveedores**) que se puede enviar al sistema SII. De forma predeterminada, el paquete contiene 10 000 facturas.                                                                                                       |
| GenerateMessageIC    | Exportación de informes electrónicos  | Esta acción ejecuta el **Formato de factura intracomunitaria SII (ES)** para crear un paquete de facturas (elementos EM del tipo **OperacionesIntracomunitarias**) que se puede enviar al sistema SII. De forma predeterminada, el paquete contiene 10 000 facturas.                                                                                               |
| GenerateMessageCP    | Exportación de informes electrónicos  | Esta acción ejecuta el **Formato de pago de cliene SII (ES)** para crear un paquete de facturas (elementos EM del tipo **PagosCliente**) que se puede enviar al sistema SII. De forma predeterminada, el paquete contiene 10 000 facturas.                                                                                                              |
| GenerateMessageVP    | Exportación de informes electrónicos  | Esta acción ejecuta el **Formato pago de proveedor SII (ES)** para crear un paquete de facturas (elementos EM del tipo **PagosProveedores**) que se puede enviar al sistema SII. De forma predeterminada, el paquete contiene 10 000 facturas.                                                                                                            |
| SendMessageCI        | Servicio web                  | Esta acción envía el archivo XML generado por la acción **GenerateMessageCI** al sitio web **Factura de clie.**.                                                                                                                                                                                                                          |
| SendMessageVI        | Servicio web                  | Esta acción envía el archivo XML generado por la acción **GenerateMessageVI** al sitio web **Factura de prov.**.                                                                                                                                                                                                                          |
| SendMessageIC        | Servicio web                  | Esta acción envía el archivo XML generado por la acción **GenerateMessageIC** al sitio web **Intracomunitario**.                                                                                                                                                                                                                       |
| SendMessageCP        | Servicio web                  | Esta acción envía el archivo XML generado por la acción **GenerateMessageCP** al sitio web **Factura de clie.**.                                                                                                                                                                                                                          |
| SendMessageVP        | Servicio web                  | Esta acción envía el archivo XML generado por la acción **GenerateMessageVP** al sitio web **Factura de prov.**.                                                                                                                                                                                                                          |
| Re-GenerateMessageCI | GERExport                    | Esta acción ejecuta el **Formato de factura emitida SII (ES)** para crear un paquete de facturas (elementos de mensaje del tipo **FacturasСliente**) que tiene estado de **Elemento reenviado** y se puede volver a enviar al sistema SII. De forma predeterminada, el paquete contiene 10 000 facturas.                                                                |
| Re-GenerateMessageVI | GERExport                    | Esta acción ejecuta el **Formato de factura recibida SII (ES)** para crear un paquete de facturas (elementos de mensaje del tipo **FacturasProveedores**) que tiene estado de **Elemento reenviado** y se puede volver a enviar al sistema SII. De forma predeterminada, el paquete contiene 10 000 facturas.                                                               |
| Re-GenerateMessageIC | GERExport                    | Esta acción ejecuta el **Formato intracomunitario SII (ES)** para crear un paquete de facturas (elementos de mensaje del tipo **OperacionesIntracomunitarias**) que tiene estado de **Elemento reenviado** y se puede volver a enviar al sistema SII. De forma predeterminada, el paquete contiene 10 000 facturas.                                                       |
| ImportResponse       | GERImport                    | Esta acción importa la respuesta del sistema SII, actualiza los mensajes y los estados de los elementos de EM (**Correcto**, **AceptadoConErrores** e **Incorrecto**) y registra información de la acción relacionada con las entidades actualizadas.                                                                                                                     |

Además, la siguiente tabla describe las acciones manuales del usuario que se incluyen en el procesamiento **SII** para ayudarlo a administrar el informe de mensajes específicos y elementos de EM a través del cambio de estado.

| **Acción**               | **Tipo de acción**               | **Descripción**                                                                                                                                                                                    |
|--------------------------|-------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| UpdateMessageStatus      | Procesamiento de usuario de nivel de mensaje | Esta acción manual del usuario restablece el estado del mensaje electrónico de **ErTecnico_Generado** a **ToBeDeleted** para que pueda identificar y eliminar los mensajes con error.                      |
| ExcludeMessageItem       | Procesamiento de usuarios               | Esta acción manual del usuario restablece el estado del elemento de EM de **Creado**, **Incorrecto**, **NoIncluido** o **Preparado** a **Excluido** y excluye el artículo del procesamiento.                 |
| Actualizar al estado inicial | Procesamiento de usuarios               | Esta acción manual del usuario restablece el estado del elemento de EM de **Excluido**, **Creado**, **EnProceso**, **Error**, **Incorrecto**, **NoIncluido** o **Preparado** a **Creado** o **Preparado**. |
| Usuario                     | Procesamiento de usuarios               | Esta acción manual del usuario restablece el estado del elemento de EM de **AceptadoConErrores**, **Correcto**, **Excluido** o **Incorrecto** a **Creado** o **ResentirseDe**.                             |

> [!NOTE]
> Si un elemento EM se envía correctamente al sistema SII (es decir, si tiene estado **Correcto** o **AceptadoConErrores**), su campo adicional **TipoComunicación** se establece en **A1**. Cuando un elemento de EM que se envía al sistema SII tiene un campo adicional **TipoComunicación** establecido en **A**, el sistema SII actualiza el registro relacionado que se envió anteriormente.

### <a name="run-sii-processing-to-report-invoices"></a>Ejecutar el procesamiento SII para registrar facturas

Para registrar facturas al sistema SII, siga estos pasos.

1.  Vaya a **Impuestos \> Consultas e informes \> Mensajes electrónicos \> Elementos de mensajes electrónicos**.
2.  En el panel de acciones, seleccione **Ejecutar procesamiento**.
3.  En el cuadro de diálogo, en campo **Procesamiento**, seleccione **SII**.
4.  Si desea ejecutar todas las acciones posibles para el procesamiento de **SII**, anule la selección de la casilla **Elegir acción**. Si desea ejecutar solo una acción específica, seleccione la casilla **Elegir acción** y luego, en el campo **Acción**, seleccione la acción a ejecutar.

### <a name="exclude-an-invoice-from-reporting-to-the-sii-system"></a>Excluir una factura de su registro en el sistema SII

Para excluir una factura de su registro en el sistema SII, siga estos pasos.

1.  Vaya a **Impuestos \> Consultas e informes \> Mensajes electrónicos \> Elementos de mensajes electrónicos**.
2.  En el Panel de acciones, seleccione **Actualizar estado** para actualizar el estado de los elementos de EM a **Excluido**. Las facturas que tienen un estado de **Excluido** no se incluirá en el informe.
3.  En el cuadro de diálogo **Actualizar estado**, seleccione procesamiento de **SII**. A continuación, en el campo **Acción**, seleccione **ExcludeMessageItem**.
4.  En el campo **Nuevo estado**, seleccione **Excluido**.
5.  En la ficha desplegable **Registros para incluir**, defina criterios adicionales para especificar qué facturas deben excluirse de un procesamiento posterior.

Puede revertir el estado **Excluido** de los elementos del mensaje seleccionando **Actualizar al estado inicial**.

## <a name="reporting-collections-in-cash-to-the-sii-system"></a>Informe de cobros en efectivo al sistema SII

Según la documentación oficial del sistema SII, las empresas en España deben transmitir el informe de **Cobros en efectivo** del año anterior al sistema SII al comienzo de cada año natural. El informe debe incluir información sobre cualquier importe superior a 6000 euros que se recibiera en efectivo del mismo cliente para las transacciones que se realizaron durante el año natural.

### <a name="additional-setup-in-finance-for-reporting-collections-in-cash-to-the-sii-system"></a>Configuración adicional en Finance para informar al sistema SII sobre los cobros en efectivo

Para seleccionar las transacciones de pago de clientes relacionadas con efectivo que deben informarse al sistema SII en el informe **Cobro en efectivo**, debe configurar las cuentas principales donde se reflejan esas transacciones.

Para configurar cuentas para transacciones de pago relacionadas con efectivo, vaya a **Impuesto \> Configurar \> Impuesto \> Cuentas contables de efectivo**. La página **Cuentas contables de efectivo** también se usa con el mismo propósito para el Modelo 347.

### <a name="prepare-data-to-report-collections-in-cash-to-the-sii-system"></a>Preparar datos para registrar cobros en efectivo en el sistema SII

Antes de registrar los cobros en los datos de efectivo, los importes relacionados deben agregarse en el sistema.

Para preparar los datos para registrar cobros en efectivo en el sistema SII, siga estos pasos.

1.  Vaya a **Impuesto \> Declaraciones \> Impuesto \> Cobros en informes de efectivo**. Cada informe de **Cobro en efectivo** debe haberse creado y registrado para un año natural.
2.  En el Panel de acciones, seleccione **Generar** para crear un informe ara un año.
3.  En el campo **Ejercicio**, especifique el año para el que desea registrar los cobros en efectivo.
4.  Seleccione el campo **Cantidad mínima de pagos en efectivo** y luego seleccione **Aceptar** para generar el informe.

Después de que se genere el informe **Cobros en efectivo**, seleccione **Líneas** para revisar las líneas del informe.

No puede eliminar el informe **Cobros en efectivo**, pero puede volver a ejecutar un informe para el mismo año. Si el informe **Cobros en efectivo** ya se ha generado durante un período, cuando comience a generar datos del informe para el mismo período, las cantidades para cada cliente en el informe se actualizan de acuerdo con los datos actualmente registrados en la base de datos. Si se revierten las cantidades liquidadas previamente y ya no se debe registrar una cantidad en efectivo de un cliente, la línea relacionada se eliminará del informe. Al mismo tiempo, si se produjo una liquidación adicional por parte de un cliente en el año seleccionado, el cliente se agregará al informe, junto con el importe relacionado en efectivo.

> [!NOTE]
> Cuando haya informes para varios años, si vuelve a ejecutar un informe para un año anterior, la información de años posteriores podría dejar de ser válida. El sistema le advierte sobre este hecho, pero no le impide continuar. Si espera realizar cambios en un informe para un período posterior, debe volver a ejecutarlo.

### <a name="em-processing-for-reporting-collections-in-cash-to-the-sii-system"></a>Procesamiento de EM para registrar cobros en efectivo en el sistema SII

Utilice la funcionalidad de EM para generar un informe XML de datos que se generan en la página **Informe de cobros en efectivo** y enviarlo al sistema SII.

El paquete **ES SII setup.zip** proporciona la configuración para el procesamiento **SCollectionInCash** en la funcionalidad EM que admite la interactuación con el sistema SII. La siguiente ilustración muestra el esquema general del procesamiento **CollectionInCash**.

![Esquema para el procesamiento general de CollectionInCash](media/emea-esp-sii-collection-in-cash-process.png)

### <a name="actions-of-collectionincash-processing"></a>Acciones de procesamiento de CollectionInCash

La siguiente tabla describe las acciones generales del procesamiento **CollectionInCash**.

| **Acción**               | **Tipo de acción**              | **Descripción**                                                                                                                                                                                                                                                                                                                                                                         |
|--------------------------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PopulateMessageItem      | Rellenar registros             | Esta acción ejecuta la acción **PopulateCollectionInCash** del tipo **Rellenar registros** para agregar registros preparados de la página **Cobros en informes de caja** para la página **Elemento del mensaje**.                                                                                                                                                                                           |
| EvaluationFields         | Nivel de ejecución de artículo de mensaje | Esta acción ejecuta la clase ejecutable **SIIPartyAttributesEvaluation** para calcular los valores de los campos adicionales **ID**, **IDType** y **CódigoPaís** para elementos de EM.                                                                                                                                                                                                            |
| GenerateMessageCIC       | Exportación de informes electrónicos  | Esta acción ejecuta el **Formato de cobros en efectivo de SII (ES)** para crear un paquete de facturas (elementos EM del tipo **CobrosEnMetálico**) que se puede enviar al sistema SII.                                                                                                                                                                                                            |
| SendMessageCIC           | Servicio web                  | Esta acción envía el archivo XML generado por la acción **GenerateMessageCIC** al sitio web **CollectionInCash**.                                                                                                                                                                                                                                                        |
| ImportResponse           | Importación de informes electrónicos  | Esta acción ejecuta el **Formato para importar a SII (ES)** para importar la respuesta del sistema SII, actualizar el mensaje y los estados de los elementos de EM (**Correcto**, **AceptadoConErrores** e **Incorrecto**) y registra información de la acción relacionada con las entidades actualizadas.                                                                                                                 |
| MonitorCollectInCash     | Nivel de ejecución de artículo de mensaje | Esta acción ejecuta la clase ejecutable **MonitorCollectionInCash** para verificar si hay algún cambio en las líneas del informe **Cobro en efectivo** para el período de informe relacionado. El estado de los elementos de mensaje afectados se cambia a **CancelaciónPendiente** o **Corregido**. Se requiere la configuración adicional del parámetro clase ejecutable **MonitorCollectionInCash**. |
| Re-SendMessageCIC        | Exportación de informes electrónicos  | Esta acción ejecuta el **Formato de cobro en efectivo SII (ES)** para crear un paquete de facturas (elementos de mensaje del tipo **CobrosEnMetálico**) que tiene estado de **Elemento reenviado** y se puede volver a enviar al sistema SII.                                                                                                                                                                    |
| ExcludeMessageItem       | Procesamiento de usuarios              | Esta acción manual del usuario restablece el estado del elemento de EM de **Creado**, **Incorrecto**, **NoIncluido** o **Preparado** a **Excluido** y excluye el elemento de EM del procesamiento.                                                                                                                                                                                                   |
| Actualizar al estado inicial | Procesamiento de usuarios              | Esta acción manual del usuario restablece el estado del elemento de EM de **Excluido**, **Creado**, **EnProceso**, **Error**, **Incorrecto**, **NoIncluido** o **Preparado** a **Creado** o **Preparado**.                                                                                                                                                                                      |
| Actualizar a Cancelado       | Procesamiento de usuarios              | Esta acción manual del usuario restablece el estado del elemento de EM desde **CancelaciónPendiente** a **Cancelado**.                                                                                                                                                                                                                                                                                |

### <a name="run-collectionincash-em-processing-to-report-invoices"></a>Ejecutar el procesamiento de EM con CollectionInCash para registrar facturas

Para usar el procesamiento **CollectionInCash** para informar facturas, siga estos pasos.

1.  Vaya a **Impuestos \> Consultas e informes \> Mensajes electrónicos \> Elementos de mensajes electrónicos**.
2.  En el panel de acciones, seleccione **Ejecutar procesamiento**.
3.  En el cuadro de diálogo, en campo **Procesamiento**, seleccione **CollectionInCash**.
4.  Si desea ejecutar todas las acciones posibles para el procesamiento de **CollectionInCash**, anule la selección de la casilla **Elegir acción**. Si desea ejecutar solo una acción específica, seleccione la casilla **Elegir acción** y luego, en el campo **Acción**, seleccione la acción a ejecutar.

### <a name="exclude-a-collection-in-cash-record-from-reporting-to-the-sii-system"></a>Excluir un cobro en el registro de efectivo de su notificación en el sistema SII

Para excluir un cobro en el registro de efectivo de su notificación en el sistema SII, siga estos pasos.

1.  Vaya a **Impuestos \> Consultas e informes \> Mensajes electrónicos \> Elementos de mensajes electrónicos**.
2.  En el Panel de acciones, seleccione **Actualizar estado** para actualizar el estado de los elementos de EM a **Excluido**. Los elementos de EM que tienen un estado de **Excluido** no se incluirá en el informe.
3.  En el cuadro de diálogo **Actualizar estado**, seleccione procesamiento de **CollectionInCash**. A continuación, en el campo **Acción**, seleccione **Excluir elemento de mensaje**.
4.  En el campo **Nuevo estado**, seleccione **Excluido**.
5.  En la ficha desplegable **Registros para incluir**, defina criterios adicionales para especificar qué elementos de EM deben excluirse de un procesamiento posterior.

Puede revertir el estado **Excluido** de los elementos de EM seleccionando **Actualizar al estado inicial**.

### <a name="how-the-collections-in-cash-report-affects-electronic-message-items"></a>Cómo el informe de cobros en efectivo afecta a los elementos de mensajes electrónicos

Los elementos de mensajes electrónicos del tipo **Cobros en efectivo** (**CobrosEnMetálico**) están relacionados con líneas en el informe **Cobros en efectivo**.

Para mantener la integridad de los datos entre estos elementos de mensajes electrónicos y las líneas de informes, el sistema supervisa los cambios en el informe de **Cobros en efectivo** y refleja automáticamente los cambios de la siguiente manera.

| **Acción en el informe de cobros en efectivo** | **Reflejo en el registro SII**                                                                                                                                                                                                                                       |
|----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se actualiza un importe en efectivo durante la función **Generación** | Si un elemento de mensaje electrónico relacionado ya estaba registrado, su estado cambia de nuevo a **Corregido** (**Elemento corregido**). Por lo tanto, este registro debe volver a enviarse al sistema SII.                                                                               |
| Una línea de informe se elimina durante la función **Generación**.                    | Si una línea SII relacionada ya estaba registrada, su estado cambia de nuevo a **Pendiente de cancelar**. Por lo tanto, debe eliminar el registro relacionado en la base de datos del sistema SII y luego actualizar el estado de la línea a **Cancelado** seleccionando **Estado \> Cancelado**. |
| Una línea de informe se agrega durante la función **Generación**.                      | Este será un nuevo elemento de mensaje electrónico. Use el proceso estándar para registrarlo en el sistema SII.                                                                                                                                                                   |

Para mantener la integridad de los datos, líneas en el informe **Cobro en efectivo** el informe no se puede eliminar manualmente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]