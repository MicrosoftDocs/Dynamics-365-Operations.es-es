---
title: "Características en desuso"
description: "Este tema describe las funciones que se han eliminado, o que está previsto que se eliminen."
author: sericks007
manager: AnnBe
ms.date: 07/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Platform, UnifiedOperations
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 6
ms.translationtype: HT
ms.sourcegitcommit: c73eeaaf28df8db720431d4bcd317c9721baa99d
ms.openlocfilehash: 3ebe8f2869b93050d320456ff457c0b5692c5eae
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="deprecated-features"></a>Características en desuso

[!include[banner](../includes/banner.md)]

Este tema describe las características que se han quitado o que cuya eliminación de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition se ha planificado.

## <a name="features-that-have-been-deprecated-in-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Funciones que se han dejado de utilizar en Dynamics 365 for Finance and Operations, Enterprise Edition (julio de 2017) con actualización de plataforma 8

### <a name="warehouse-mobile-devices-portal"></a>Portal de dispositivos móviles de almacén

El portal de dispositivos móviles de almacén (WMDP) era componente independiente pensando para la implementación propia localmente. Este componente ya no se admite en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Una aplicación nativa que mejora la experiencia del usuario ha sustituido a la funcionalidad de WMDP. 

|                                  |                                                 |
|----------------------------------|-------------------------------------------------|
| **Motivo de la eliminación**       | Funcionalidad duplicada.                        |
| **¿Reemplazado por otra característica?** | Sí. Esta función se ha sustituido por Finance and Operations - Warehousing. Para obtener más información sobre la configuración y requisitos previos, consulte [Instalar y configurar Microsoft Dynamics 365 for Finance and Operations - Warehousing](../../supply-chain/warehousing/install-configure-warehousing-app.md). |
| **Módulos afectados**             | Gestión de almacenes y administración de transporte |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Regla de correspondencia de conciliación bancaria para coincidencia manual

Una regla de coincidencia se utilizó para seleccionar y marcar un documento bancario cuando los documentos se conciliaron manualmente en la hoja de cálculo de conciliación.

|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Uso limitado.                                                                         |
| **¿Reemplazado por otra característica?** | N. º Las capacidades de filtro de columnas se deben usar para buscar los documentos de la conciliación. |
| **Módulos afectados**             | Gestión de efectivo y bancos                                                               |

### <a name="windows-8-tablet-app"></a>Aplicación para tabletas con Windows 8

La aplicación para tabletas con Windows 8 ofrecía funcionalidad para la entrada y la aprobación de gastos.

|                                  |                                                                                          |
|----------------------------------|------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Finance and Operations es compatible con las tabletas. La aplicación para tabletas ya no se requiere. |
| **¿Reemplazado por otra característica?** | N. º                                                                                      |
| **Módulos afectados**             | Gestión de gastos                                                                       |


## <a name="features-that-have-been-deprecated-in-dynamics-365-for-operations-1611-with-platform-update-3"></a>Funciones que se han dejado de utilizar en Dynamics 365 for Operations 1611 con la actualización de la plataforma 3

### <a name="aeb-payment-formats-for-spain"></a>Formatos de pago de AEB para España

Los formatos de pago del Consejo Superior Bancario se usan para enviar remesas al banco de los pagos de cliente y proveedor. El contenido de estos formatos lo determina aa Asociación Española de Banca. Cubre Cuadernos 19, 32, 58, 34.

|                              |                                                                          |
|------------------------------|--------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Los formatos de pago ya no se usan.                                  |
| **¿Reemplazado por otra característica?** | Sí, transferencia de crédito ISO20022 y formatos de pago de domiciliación bancaria para España |
| **Módulos afectados**             | Cuentas de proveedores, cuentas de clientes                                    |

### <a name="bank-payments-transfer-for-lithuania"></a>Transferencia de pagos bancarios para Lituania

Las transferencias de los pagos bancarios se generan e imprimen mediante el formato de exportación de Transferencia de pagos (LT) para Lituania. El mercado lituano empezó a usar LITAS, el sistema unificado de banca electrónica, en 2005.

|                              |                                                            |
|------------------------------|------------------------------------------------------------|
| **Motivo de la eliminación**       | Los formatos de pago ya no se usan.                    |
| **¿Reemplazado por otra característica?** | Sí, formato de pago de transferencia de crédito ISO20022 para Lituania |
| **Módulos afectados**             | Proveedores                                           |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>Formatos de pago de BBS Direkte Remittering para Noruega

Los formatos de pago de BBS Direkte Remittering incluyen la exportación del cobro de pago de cliente (domiciliación bancaria) y la importación de la devolución del mensaje.

|                              |                                                                                                                                                                |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Los formatos de pago ya no se usan.                                                                                                                        |
| **¿Reemplazado por otra característica?** | El formato de pago de un cliente de AvtaleGiro para Noruega se puede usar para generar los mensajes de domiciliación bancaria. La importación de la devolución del mensaje será implementada en próximas versiones. |
| **Módulos afectados**             | Cuentas de proveedores, cuentas de clientes                                                                                                                          |

### <a name="chart-of-accounts-tool-for-spain"></a>Herramienta para el plan de cuentas para España

Se utiliza esta herramienta cuando un plan de cuentas en España requiere cambios importantes. Los usuarios pueden importar un nuevo plan de cuentas en Microsoft Excel o en formato de texto, y también pueden importar los informes financieros.

|                              |                |
|------------------------------|----------------|
| **Motivo de la eliminación**       | Uso limitado  |
| **¿Reemplazado por otra característica?** | Nº             |
| **Módulos afectados**             | Contabilidad general |

### <a name="dom80-payment-format-for-belgium"></a>Formato de pago Dom80 para Bélgica

Formato de pago Legacy Belga para cobro de pago (domiciliación bancaria).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Motivo de la eliminación**      | El formato de pago ya no se usa.                  |
| **¿Reemplazado por otra característica?** | Sí, formato de pago de domiciliación bancaria ISO 20022 para Bélgica. |
| **Módulos afectados**            | Clientes                                    |

### <a name="dtaezag-payment-formats-for-switzerland"></a>Formatos de pago DTA/EZAG para Suiza

Los formatos DTA/EZAG se integran en el sistema ESR, ya que pueden contener un número de referencia. Puesto que el número de referencia no es obligatorio, los formatos se pueden usar para procesar los pagos de proveedor. Estos formatos los usan las empresas con una cuenta bancaria en una ubicación diferente de “Postfinance.”

|                              |                                                              |
|------------------------------|--------------------------------------------------------------|
| **Motivo de la eliminación**       | Los formatos de pago ya no se usan.                      |
| **¿Reemplazado por otra característica?** | Sí, formato de pago de transferencia de crédito ISO20022 para Suiza |
| **Módulos afectados**             | Proveedores                                             |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>Formato de pago de EDIFACT-DIRDEB para Austria

Formato de pago de EDIFACT-DIRDEB para cobro de pago (domiciliación bancaria).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Motivo de la eliminación**       | El formato de pago ya no se usa.                  |
| **¿Reemplazado por otra característica?** | Sí, formato de pago de domiciliación bancaria ISO 20022 para Austria |
| **Módulos afectados**             | Clientes                                    |

### <a name="edivat-for-belgium"></a>EDIVAT para Bélgica

EDIVAT es una norma belga obsoleta para la declaración electrónica a través de correo seguro. Microsoft Dynamics AX 2012 conserva la opción de sólo lectura para habilitar el acceso a los datos históricos.

|                              |                                      |
|------------------------------|--------------------------------------|
| **Motivo de la eliminación**       | La función ya no se usa. |
| **¿Reemplazado por otra característica?** | Nº                                   |
| **Módulos afectados**             | Contabilidad general                       |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>Formato de importación de pago de eGiro EDIFACT CREMUL para Noruega

eGiro se basa en la norma internacional UN EDIFACT CREMUL (Mensaje de aviso de crédito múltiple), que se usa para el registro automático de pagos del cliente. En Microsoft Dynamics AX, eGiro se implementa como formato de importación de pago de cliente.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | El formato de pago ya no se usa.                                                     |
| **¿Reemplazado por otra característica?** | N. º El formato se sustituirá por formatos ISO 20022 de importación de criterio en próximas versiones. |
| **Módulos afectados**             | Clientes                                                                       |

### <a name="external-inventory-for-poland"></a>Inventario externo para Polonia

Pruebas de mercancías que se toman de un proveedor para las venta sin compra. Las mercancías que son gestionadas en un inventario externo, no afectan al inventario estándar y se pueden vender y comprar después automáticamente. Este proceso crea los movimientos de inventario reales.

|                              |                                                 |
|------------------------------|-------------------------------------------------|
| **Motivo de la eliminación**       | Reemplazado por otra característica                     |
| **¿Reemplazado por otra característica?** | Sí, la funcionalidad básica de entrada de envío |
| **Módulos afectados**             | Cuentas de proveedores, gestión de inventario          |

### <a name="financial-reports-generator-for-eastern-europe"></a>Generador de informes financieros para Europa Oriental

Se utiliza una herramienta para configurar la recopilación de datos para los informes de contabilidad e impuestos, y para exportar datos a plantillas de informes XLS y DOC.

|                              |                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Uso limitado                                                                            |
| **¿Reemplazado por otra característica?** | N. º La herramienta se reemplazará por las configuraciones de informes electrónicas en próximas versiones. |
| **Módulos afectados**             | Contabilidad general                                                                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Importación de las transacciones de pago del cliente para Finlandia

Puede seleccionar un formato de importación para los pagos finlandeses para importar las transacciones de pago del cliente desde un archivo externo proporcionado por el banco.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | El formato de pago ya no se usa.                                                     |
| **¿Reemplazado por otra característica?** | N. º El formato se sustituirá por formatos ISO 20022 de importación de criterio en próximas versiones. |
| **Módulos afectados**             | Clientes                                                                       |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Importación de transacciones de pago en un diario de contabilidad general para Finlandia

Se usa un formato específico para Finlandia para importar las transacciones de contabilidad en la contabilidad general.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | El formato de pago ya no se usa.                                                     |
| **¿Reemplazado por otra característica?** | N. º El formato se sustituirá por formatos ISO 20022 de importación de criterio en próximas versiones. |
| **Módulos afectados**             | Clientes                                                                       |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integración con el software Isabel sincronizado (CIS) para Bélgica

Isabel es el marco de trabajo de la banca electrónica en Europa y es una norma de hecho en Bélgica.

|                              |                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La integración con el cliente Isabel se ha interrumpido.                                                                |
| **¿Reemplazado por otra característica?** | N. º Los formatos de pago que ya no se usan son reemplazados por el formato de pago de transferencia de crédito ISO20022 para Bélgica. |
| **Módulos afectados**             | Proveedores                                                                                                     |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Modificaciones del plan de cuentas y reglas de contabilidad para España

Esta característica se usa para los cambios en el plan de cuentas y en las reglas de contabilidad de España. Asigna cuentas para ayudar a transformar el antiguo plan de cuentas en el nuevo plan contable, y compara el ejercicio anterior con el nuevo ejercicio, incluso si se han registrado en números de cuenta distintos.

|                              |                |
|------------------------------|----------------|
| **Motivo de la eliminación**       | Uso limitado  |
| **¿Reemplazado por otra característica?** | Nº             |
| **Módulos afectados**             | Contabilidad general |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Formato de pago de proveedor de Pagamento Fornittori

Formato de pago de transferencia de crédito de Legacy italiano.

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Motivo de la eliminación**       | El formato de pago ya no se usa.                  |
| **¿Reemplazado por otra característica?** | Sí, formato de pago de transferencia de crédito ISO20022 para Italia |
| **Módulos afectados**             | Proveedores                                       |

### <a name="payment-export-formats-for-estonia"></a>Formatos de exportación de pagos para Estonia

Los formatos de Telehansa y Teleservicio se usan para la exportación de pago bancario.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Motivo de la eliminación**      | Los formatos de pago ya no se usan.                  |
| **¿Reemplazado por otra característica?** | Sí, formato de pago de transferencia de crédito ISO20022 para Estonia |
| **Módulos afectados**             | Proveedores                                         |

### <a name="payment-file-archive-for-norway"></a>Archivo de pago para Noruega

Cuando se generan los archivos de pago, el archivo almacena automáticamente todos los archivos que se crean, incluso los que se han escrito o leído con anterioridad.

|                              |                                                                    |
|------------------------------|--------------------------------------------------------------------|
| **Motivo de la eliminación**       | Reemplazado por otra característica                                        |
| **¿Reemplazado por otra característica?** | Sí, trabajos archivados de informes electrónicos                            |
| **Módulos afectados**             | Cuentas de proveedores, cuentas de clientes, administración de la empresa |

### <a name="payment-import-formats-for-estonia"></a>Formatos de importación de pagos para Estonia

Los formatos de Telehansa y TeleTeenus se usan para la importación de pago bancario.

|                              |                                                                                            |
|------------------------------|--------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Los formatos de pago ya no se usan.                                                    |
| **¿Reemplazado por otra característica?** | N. º Los formatos se sustituirán por formatos ISO 20022 de importación de criterio en próximas versiones. |
| **Módulos afectados**             | Clientes                                                                        |

### <a name="performance-management-goal-workflow"></a>Flujo de trabajo de objetivo de gestión del rendimiento

La gestión del rendimiento incluye la administración y la integración del objetivo con las evaluaciones de rendimiento.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La gestión del rendimiento se diseñó de nuevo y el número de páginas de objetivos se redujo para simplificar el proceso.                 |
| **¿Reemplazado por otra característica?** | N. º Los objetivos son visibles para los administradores a través del portal Manager Self Service, y se pueden ver y cambiar por el administrador. |
| **Módulos afectados**             | Gestión del capital humano                                                                                                 |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Formatos de pago de Postgirot y Postgirot Utland para Suecia

Formatos de pago de Postgirot y Postgirot Utland para Suecia.

|                              |                                                         |
|------------------------------|---------------------------------------------------------|
| **Motivo de la eliminación**       | Los formatos de pago ya no se usan.                 |
| **¿Reemplazado por otra característica?** | Sí, formato de pago de transferencia de crédito ISO20022 para Suecia |
| **Módulos afectados**             | Proveedores                                        |

### <a name="radio-frequency-identifier"></a>Identificador por radiofrecuencia

La identificación por radiofrecuencia (RFID) es una tecnología de recopilación de datos que utiliza etiquetas electrónicas para almacenar datos de identificación y no precisa ningún lector de requisitos visuales para capturarlos.

|                              |                                               |
|------------------------------|-----------------------------------------------|
| **Motivo de la eliminación**       | Poco uso de cliente y conjunto limitado de funciones. |
| **¿Reemplazado por otra característica?** | No                                            |
| **Módulos afectados**             | Gestión del inventario                          |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Informe sobre la numeración del estado de las facturas para Letonia

La legislación letona proporciona reglas específicas acerca de la numeración de las facturas de ventas. Dicha funcionalidad le permite asignar números específicos a las facturas de ventas, en función del usuario o del grupo de usuarios. A continuación puede generar un informe o un archivo XML. También puede imprimir un informe sobre los números de factura que se usan.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La numeración de la factura de estado ya no tiene que mantenerse. El informe sobre números de factura utilizados ya no es necesario. |
| **¿Reemplazado por otra característica?** | Nº                                                                                                                       |
| **Módulos afectados**             | Clientes                                                                                                      |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Configuración de los nombres del administrador y el contable general de una empresa para Lituania

Los nombres del administrador y el contable general de una empresa se pueden especificar en la información de la empresa y usar en distintas copias impresas locales del informe.

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| **Motivo de la eliminación**       | Reemplazado por otra característica                                     |
| **¿Reemplazado por otra característica?** | Sí, la configuración de funcionarios se puede usar con el mismo propósito.   |
| **Módulos afectados**             | Clientes, Proveedores, Gestión de efectivo y bancos |

### <a name="telepay-payment-formats-for-norway"></a>Formatos de pago Telepay para Noruega

Los formatos de pago Telepay incluyen la exportación del pago de proveedor (transferencia de crédito) y el cobro de pago del cliente (domiciliación bancaria).

|                              |                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Los formatos de pago ya no se usan.                                                        |
| **¿Reemplazado por otra característica?** | Sí, formato de pago de transferencia de crédito ISO20022 y formato de pago del cliente de AvtaleGiro para Noruega |
| **Módulos afectados**            | Cuentas de proveedores, cuentas de clientes                                                          |

### <a name="vendor-payment-export-formats-for-finland"></a>Formatos de exportación de pago de proveedores para Finlandia

Dos formatos para exportar pagos están disponibles para Finlandia. LM02 (FI) se usa para pagos nacionales y LUM2 (FI) se usa para pagos extranjeros.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Motivo de la eliminación**       | Los formatos de pago ya no se usan.                  |
| **¿Reemplazado por otra característica?** | Sí, formato de pago de transferencia de crédito ISO20022 para Finlandia |
| **Módulos afectados**            | Proveedores                                         |

### <a name="workflow-for-creating-goals"></a>Flujo de trabajo para crear objetivos

Un flujo de trabajo para gestionar la creación de los objetivos del empleado es uno de varios flujos de trabajo que estaban disponibles para ayudar a coordinar el proceso de gestión del rendimiento.

|                              |                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La gestión del rendimiento se ha vuelto a diseñar por completo en Microsoft Dynamics 365 for Finance and Operations.                                                                                                                                                                                                                                        |
| **¿Reemplazado por otra característica?** | La característica de Gestión del rendimiento que se ha diseñado de nuevo proporciona más control sobre el contenido de los objetivos, las medidas que se utilizan para realizar el seguimiento del progreso y los datos adjuntos de la documentación correspondiente. Los objetivos se pueden almacenar como plantillas y volverse a utilizar. Esta función puede ayudarle a configurar los objetivos adicionales para sus empleados con más rapidez. |
| **Módulos afectados**            | Gestión del capital humano                                                                                                                                                                                                                                                                                                               |

## <a name="features-that-have-been-deprecated-in-dynamics-ax-70-releases"></a>Funciones que ya no se utilizan en las versiones de Dynamics AX 7.0

### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Capacidad para cancelar cambios en una factura de proveedor

|                              |                         |
|------------------------------|-------------------------|
| **Motivo de la eliminación**       | Mejora del rendimiento |
| **¿Reemplazado por otra característica?** | No                      |
| **Módulos afectados**            | Proveedores        |

### <a name="aif-axd-and-axbc-integrations"></a>Integración de AIF, Axd y AxBC

En Application Integration Framework (AIF), los datos se pueden intercambiar con sistemas externos por medio de lógica de negocios expuesta como servicios. Dynamics AX incluye servicios que se basan en documentos y en .NET Business Connector (AxBC). Los documentos se crean mediante XML. El XML incluye información de encabezado que se agrega para crear un *mensaje* que se puede transferir a o de Dynamics AX. Algunos ejemplos de documentos son los pedidos de compra y venta. No obstante, casi cualquier entidad, como un cliente, puede ser representado por un documento. Los servicios que se basan en documentos usan las clases **Axd &lt;*Documento*&gt;**.

|                              |                                                                                                                                                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La arquitectura de AIF y de AxDs no se podría escalar un servicio de nube. Ha habido problemas de rendimiento en la importación masiva.                                                                               |
| **¿Reemplazado por otra característica?** | En la versión actual de Dynamics AX, esta característica se sustituye por el marco de importación y exportación de datos, compatible con la importación y exportación masiva recurrente. Para AxBC, se recomienda usar las tablas reales. |
| **Módulos afectados**             | AxDs, AxBC y AIF                                                                                                                                                                                     |

### <a name="boms-without-bom-versions"></a>L. MAT sin versiones de L. MAT

Cuando la clave de configuración **Versiones de L. MAT.** se deshabilita, las versiones de la lista de materiales se ocultan en todos los formularios, y el sistema fuerza una relación 1:1 entre los productos liberados y las listas de materiales. En la versión actual de Dynamics AX, no se puede deshabilitar la clave de configuración **Versiones de L. MAT**.

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| **Motivo de la eliminación**      | El uso de una clave de configuración para controlar las versiones de listas de materiales no se escala en un entorno de nube. |
| **¿Reemplazado por otra característica?** | No                                                                                      |
| **Módulos afectados**            | Gestión de información de productos, Gestión de inventarios                                    |

### <a name="brazilian-bordero"></a>Bordero brasileño

Forma de pago específica para las empresas brasileñas

|                              |                                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La ayuda de la forma de pago para el Bordero brasileño se ha interrumpido para la ubicación brasileña |
| **¿Reemplazado por otra característica?** | Nº                                                                                                    |
| **Módulos afectados**             | Proveedores                                                                                      |

### <a name="brazilian-sintegra-statement"></a>Extracto de Sintegra brasileño

Extracto del impuesto federal para el impuesto de ICMS

|                              |                                                                                                                       |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Este extracto ya no se aplica en algunos estados brasileños.                                                     |
| **¿Reemplazado por otra característica?** | N. º Los usuarios pueden utilizar la herramienta de informes electrónica genérica para configurar el extracto si es necesario de acuerdo a situaciones específicas. |
| **Módulos afectados**             | Libros fiscales                                                                                                          |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Modo brasileño de contingencia SCAN brasileña para NF-e

El entorno de contingencia de (SCAN) se usa para generar, exportar e importar el estado de una Nota fiscal electrónica (NF-e) cuando el entorno de la Secretaría de Hacienda (SEFAZ) no está disponible.

|                              |                                                                             |
|------------------------------|-----------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Este método de contingencia ya no es un aplicable en todos los estados brasileños |
| **¿Reemplazado por otra característica?** | Nº                                                                          |
| **Módulos afectados**             | Clientes                                                         |

### <a name="business-analyzer"></a>Analizador de negocio

Esta aplicación móvil permite a los usuarios revisar métricas de negocio clave.

|                              |                                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Esta funcionalidad se ha reemplazado por otra característica.                                                                                                      |
| **¿Reemplazado por otra característica?** | El paquete de contenido de supervisión del rendimiento financiero para Microsoft Power BI incluirá métricas financieras clave anteriormente disponibles en Business Analyzer. |
| **Módulos afectados**             | Contabilidad general                                                                                                                                                |

### <a name="business-statistics"></a>Estadísticas comerciales

La configuración de consultas de estadísticas comerciales que le pueden ayudar a analizar el rendimiento de la organización

|                              |                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Método de herencia para la inteligencia empresarial (BI), poco uso por parte del cliente y un conjunto limitado de características |
| **¿Reemplazado por otra característica?** | Nuevas soluciones de inteligencia empresarial para la versión actual de Dynamics AX                                      |
| **Módulos afectados**             | Adquisición y abastecimiento, Proveedores, Ventas y marketing, Clientes.         |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Cambio de la función de fecha de documento en el diario de aprobación de facturas

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Poco uso                                                               |
| **¿Reemplazado por otra característica?** | Sí. La fecha de documento en la transacción de proveedor registrada puede cambiarse. |
| **Módulos afectados**             | Proveedores                                                        |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Formato de pago ClieOp03 para Países Bajos

|                              |                                                                                                            |
|------------------------------|------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | El formato ya no es aplicable en los Países bajos, ya que se ha sustituido por la funcionalidad SEPA. |
| **¿Reemplazado por otra característica?** | Exportación de pagos SEPA                                                                                       |
| **Módulos afectados**             | Todas                                                                                                        |

### <a name="compliance-center"></a>Centro de cumplimiento

El Centro de cumplimiento era un sitio de Enterprise Portal para gestionar los requisitos de documentación para las iniciativas de conformidad relacionadas con la ley Sarbanes-Oxley.

|                              |                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Falta de uso del cliente. Microsoft SharePoint incluye la misma capacidad que estaba disponible en el Centro de cumplimiento. |
| **¿Reemplazado por otra característica?** | No                                                                                                                     |
| **Módulos afectados**             | Cumplimiento y controles internos                                                                                       |

### <a name="connector-for-microsoft-dynamics"></a>Conector para Microsoft Dynamics

Esta herramienta se usó para integrar datos clave de Microsoft Dynamics CRM en las aplicaciones de Microsoft Dynamics ERP.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Motivo de la eliminación**       | Esta funcionalidad se ha reemplazado por otra característica. |
| **¿Reemplazado por otra característica?** | Integrador de Dynamics                                      |
| **Módulos afectados**             | Conector para Microsoft Dynamics                         |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Unidad de contenedor y multidimensión disponibles

|                              |                                                                                                                                                                 |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Funcionalidad duplicada                                                                                                                                         |
| **¿Reemplazado por otra característica?** | Sí. Desde AX 2012, esta funcionalidad se ha reemplazado por el conjunto de características de pedidos de lotes consolidados. Este conjunto de características incluye la vista disponible consolidada. |
| **Módulos afectados**             | Gestión de información de productos, Control de producción, Administración de inventario, Ventas y marketing                                                                   |

### <a name="cue-group-metadata"></a>Metadatos de grupo de pilas

|                              |                                                                                                                                                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Los grupos de pilas se usaban para mostrar una o más pilas en el área de cuadro informativo. La capacidad era limitada y había también problemas de rendimiento, porque un cambio de registro en un formulario principal generaba una consulta por pila en el grupo de pilas. |
| **¿Reemplazado por otra característica?** | No                                                                                                                                                                                                                            |
| **Módulos afectados**             | Todas                                                                                                                                                                                                                           |

### <a name="cue-metadata"></a>Metadatos de pila

|                              |                                                                                                                                                                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Los metadatos de pila estaban limitados a contar o sumar información.                                                                                                                                                                                   |
| **¿Reemplazado por otra característica?** | Los metadatos de icono se introdujeron para proporcionar más flexibilidad para modelar. Por ejemplo, puede modelar recuentos actuales, navegación e indicadores de rendimiento clave (KPI). Los metadatos de icono de recuento sustituyen directamente a los metadatos de pila. |
| **Módulos afectados**             | Todas                                                                                                                                                                                                                                     |

### <a name="danish-check-format"></a>Formato de cheque danés

|                              |                                                                                                                         |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Se ha dejado de permitir usar el diseño de formato de cheque danés, y el informe se ha retirado de la localización DK. |
| **¿Reemplazado por otra característica?** | No                                                                                                                      |
| **Módulos afectados**             | Todas                                                                                                                     |

### <a name="data-partitions"></a>Particiones de datos

Las particiones de los datos proporcionan una separación lógica de datos en la base de datos de Microsoft Dynamics AX.

|   |   |
|---|---|
| **Motivo de la eliminación**       | Las particiones de datos se introdujeron en Microsoft Dynamics AX 2012 R2 para habilitar el aislamiento de los datos. En un escenario común, una compañía tiene filiales y los datos de una filial no deben ser visibles para otra, aunque el mismo departamento de TI administre ambas filiales. Sin embargo, se requerían gastos generales de administración y scripts adicionales en todo el programa para crear nuevas particiones y rellenarlas con datos y hacer copia de seguridad de los datos de partición. En la nube, donde tenemos acceso a la plataforma como servicios de base de datos (Base de datos SQL de Microsoft Azure) de un servicio (PaaS), es mucho más eficaz utilizar una base de datos como el contenedor de aislamiento para realizar el aislamiento en el programa. Con independencia de si se requiere la partición de datos para filiales, para varios inquilinos o simplemente para escala, creemos que los escenarios se pueden controlar mejor a través de varias bases de datos o varias instancias de Dynamics AX. |
| **¿Reemplazado por otra característica?** | Se reemplazarán las particiones de datos mediante el soporte para múltiples bases de datos o instancias de Dynamics AX en una versión futura.    |
| **Módulos afectados**             | Todas  |

### <a name="database-and-file-share-storage-for-attachments"></a>Almacenamiento de recursos compartidos de archivo y base de datos para los datos adjuntos
Microsoft Dynamics AX 2012 permitía el almacenamiento de datos adjuntos en los recursos compartidos de archivos y la base de datos. Ambas opciones ya no se admiten.

|                              |                                        |
|------------------------------|----------------------------------------|
| **Motivo de la eliminación**       | El almacenamiento de recurso compartido de archivos ya no se admite ya que los entornos hospedados en la nube no pueden comunicarse con los recursos compartidos de archivos. El almacenamiento de base de datos se ha dejado de utilizar en favor del almacenamiento de blobs de Azure. El almacenamiento de blobs de Azure es equivalente al almacenamiento en la base de datos, ya que solo se puede tener acceso a los documentos a través de formularios cliente de Dynamics 365 for Finance and Operations. Esto ofrece la ventaja adicional de proporcionar almacenamiento que no afecte negativamente al rendimiento de la base de datos. El almacenamiento de blobs es el mecanismo predeterminado de almacenamiento para la gestión de documentos y funciona inmediatamente. |
| **¿Reemplazado por otra característica?** | El almacenamiento de base de datos se ha dejado de utilizar en favor del almacenamiento de blobs de Azure.       |
| **Módulos afectados**             | Todas                   |

### <a name="delimitation"></a>Delimitación

|                              |                                        |
|------------------------------|----------------------------------------|
| **Motivo de la eliminación**       | No se ha encontrado ningún uso de la función. |
| **¿Reemplazado por otra característica?** | No                                     |
| **Módulos afectados**             | Tiempo y asistencia                    |

### <a name="desktop-client"></a>Cliente de escritorio

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La experiencia de cliente de Dynamics AX se ha rediseñado para mejorar la capacidad de uso en varias plataformas y dispositivos.                      |
| **¿Reemplazado por otra característica?** | El nuevo cliente web se basa en los metadatos de formulario de escritorio y el modelo de programación que se han modificado para proporcionar una plataforma web enriquecida. |
| **Módulos afectados**             | Todas                                                                                                                                    |

### <a name="direct-database-connection"></a>Conexión con base de datos directa

En Dynamics AX 2012 R3, Retail Modern POS podía conectarse directamente a la base de datos de canales de forma parecida a la de Enterprise POS. Esto se añadía al método de comunicación estándar en que Retail Modern POS se comunicaba mediante Retail Server.  

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La conectividad directa de la base de datos requería protocolos de seguridad inferiores y se usaba principalmente para alcanzar niveles de rendimiento más altos. Debido a las mejoras del rendimiento y de seguridad que se han producido en Finance and Operations, esta funcionalidad ahora está dando más problemas que soluciones. |
| **¿Reemplazado por otra característica?** | N. º Ahora solo se da soporte a la comunicación de Retail Server estándar.    |
| **Módulos afectados**             | Base de datos de canales/Retail Modern POS                                    |

### <a name="dutch-swift-mt940"></a>SWIFT MT940 holandés

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Ahora se utiliza la función genérica en lugar de la función localizada.                                                                                                                                                                 |
| **¿Reemplazado por otra característica?** | Sí, esta función se ha reemplazado por la funcionalidad avanzada de conciliación bancaria. |
| **Módulos afectados**             | Todas                                                                                                                                                                                                                                   |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL para Alemania)

Esta funcionalidad proporcionaba salida en el lenguaje eXtensible Business Reporting Language (XBRL) pensada específicamente para la taxonomía alemana eBilanz.

|                              |                                                                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Falta de uso del cliente                                                                                                                                                 |
| **¿Reemplazado por otra característica?** | Esta característica no se ha sustituido por otra, pero hay disponibles varios paquetes XBRL especializados que proporcionan funcionalidad XBRL enriquecida para el mercado alemán. |
| **Módulos afectados**             | Management Reporter                                                                                                                                                    |

### <a name="enterprise-portal-client"></a>Cliente de Enterprise Portal

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Se ha proporcionado una sola plataforma de cliente.                                                                                            |
| **¿Reemplazado por otra característica?** | El nuevo cliente web se basa en los metadatos del formulario de escritorio y el modelo de programación que se han modificado para proporcionar una plataforma web enriquecida. |
| **Módulos afectados**             | Todas                                                                                                                                    |

### <a name="environmental-sustainability"></a>Sustentabilidad ambiental

|                              |                                                    |
|------------------------------|----------------------------------------------------|
| **Motivo de la eliminación**       | Poco uso de cliente y conjunto limitado de funciones       |
| **¿Reemplazado por otra característica?** | No                                                 |
| **Módulos afectados**             | Cumplimiento y controles internos, Proveedores |

### <a name="form-activex-and-managed-host-controls"></a>Controles de formulario de host administrados y ActiveX

|                              |                                                                                                                                                                                               |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Los controles ActiveX y de host administrados se basan en el cliente de escritorio obsoleto.                                                                                                             |
| **¿Reemplazado por otra característica?** | El marco de controles extensibles admite la creación de nuevos controles que se basan en HTML, CSS y Javascript, y es un control de primera clase en el entorno de Microsoft Visual Studio Tooling. |
| **Módulos afectados**             | Todas                                                                                                                                                                                           |

### <a name="generate-prenotes-by-using-a-batch"></a>Generación de prenotas mediante un lote

La generación de prenotas no se puede hacer mediante un lote pero sí la puede realizar un usuario.

|                              |                                                                                                        |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | No hay manera de persistir y mostrar el archivo de prenota resultante cuando se genera mediante un lote. |
| **¿Reemplazado por otra característica?** | Aún se pueden generar prenotas y el usuario tiene control sobre la ubicación en la que se guarda el archivo.   |
| **Módulos afectados**             | Clientes, Proveedores, Gestión de efectivo y bancos                                        |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Exportación de pagos DTAUS alemanes e importación de extractos de cuentas (totales y transacciones)

|                              |                                                                                                                                                                                                                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | El formato ya no es aplicable en Alemania, ya que se ha sustituido por la funcionalidad SEPA (zona única de pagos en euros).                                                                                                                                                                 |
| **¿Reemplazado por otra característica?** | Sí, esta funcionalidad se ha reemplazado por la funcionalidad de exportación de pagos SEPA y conciliación bancaria avanzada para importar extractos de cuenta. |
| **Módulos afectados**             | Todas                                                                                                                                                                                                                                                                                            |

### <a name="german-dtazv-payment-format"></a>Formato de pago DTAZV para Alemania

|                              |                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | El formato ya no es aplicable en Alemania, ya que se ha sustituido por la funcionalidad SEPA. |
| **¿Reemplazado por otra característica?** | Exportación de pagos SEPA                                                                               |
| **Módulos afectados**             | Todas                                                                                                |

### <a name="german-mt940-import"></a>Importación MT940 alemana

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Ahora se utiliza la función genérica en lugar de la función localizada.                                                                                                                                                                 |
| **¿Reemplazado por otra característica?** | Sí, esta función se ha reemplazado por la funcionalidad avanzada de conciliación bancaria. |
| **Módulos afectados**             | Todas                                                                                                                                                                                                                                   |

### <a name="german-xml-eu-sales-list"></a>Lista de ventas UE XML para Alemania

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Ya no se admite el formato XML para los informes de Lista de ventas de la UE para Alemania. Solo se puede usar el formato de archivo de texto ELMA5 para enviar el informe de la Lista de ventas de la UE a la delegación de hacienda alemana. |
| **¿Reemplazado por otra característica?** | No                                                                                                                                                                                 |
| **Módulos afectados**             | Impuesto                                                                                                                                                                                |

### <a name="gl-ssrs-reports"></a>Informes GL SSRS

Se han retirado los informes que incluyen los siguientes elementos de menú: **Resumen de saldo de comprobación**, **Saldo de comprobación detallado**, **Plan contable**, **Traza de auditoría**, **Saldos** y **Lista de saldo**.

|                              |                                                                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Los informes de Financial Microsoft SQL Server Reporting Services (SSRS) han sido reemplazados con capacidades de Management Reporter e informes predeterminados. |
| **¿Reemplazado por otra característica?** | Management Reporter (etiquetado **Informes financieros** en la versión actual de Dynamics AX)                                                  |
| **Módulos afectados**            | Contabilidad general                                                                                                                               |

### <a name="infopart-and-formpart-metadata"></a>Metadatos de InfoPart y FormPart

|                              |                                                                                                                                                                                                                                |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Los metadatos de InfoPart y de FormPart permitieron la creación de cuadros informativos para dos clientes diferentes.                                                                                                                                    |
| **¿Reemplazado por otra característica?** | Los metadatos de InfoPart, que eran una definición simplificada de formulario, se han convertido a un formulario mediante herramientas de actualización. Los metadatos de FormPart, con un formulario al que se hace referencia, se han sustituido por una referencia más directa creada mediante herramientas de actualización. |
| **Módulos afectados**             | Todas                                                                                                                                                                                                                            |

### <a name="main-account-list-page"></a>Página de lista Cuenta principal

Una lista de cuentas para la entidad jurídica y la información relacionada de saldo

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La información del saldo está disponible en la página de lista **Saldo de comprobación** por cuenta y dimensión.                                                                                      |
| **¿Reemplazado por otra característica?** | **Cuentas principales** contiene la misma lista de cuentas que contenía la página de lista **Cuenta principal**. La vista de cuadrícula en **Cuentas principales** también muestra una vista más pequeña tipo cuadrícula. |
| **Módulos afectados**             | Contabilidad general                                                                                                                                                                     |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Informe de flujo de efectivo bancario de Malasia y Singapur

Esta función permite al usuario imprimir un informe de flujo de efectivo que muestra transacciones y detalles de flujos de entrada y de salida de efectivo para un intervalo específico de fechas para las cuentas bancarias seleccionadas.

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La misma información se puede obtener desde la transacción bancaria de consulta. |
| **¿Reemplazado por otra característica?** | La transacción bancaria de consulta                                            |
| **Módulos afectados**             | Gestión de efectivo y bancos                                                |

### <a name="mexican-cfd-electronic-invoice"></a>Factura electrónica CFD mexicana

Esta función habilitó la generación de facturas electrónicas mexicanas mediante el método Comprobante Fiscal Digital (CFD), donde la empresa firma la factura solicitando el permiso correspondiente del gobierno. Esta función también proporciona un informe mensual con todas las facturas electrónicas emitidas en el período.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                           |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | El método ya no es aplicable. La generación de facturas electrónicas usando el método CFD ha sido derogada por las autoridades fiscales y se ha sustituido por el Comprobante Fiscal Digital a través de Internet (CFDI), donde la firma se delega al tercer proveedor (PAC). Se ha quitado el informe mensual, y una opción de consulta permite a los usuarios consultar transacciones históricas. |
| **¿Reemplazado por otra característica?** | No                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Módulos afectados**             | Clientes, Proyecto                                                                                                                                                                                                                                                                                                                                                                              |

### <a name="mexico-realized-and-unrealized-vat"></a>IVA realizado y sin realizar en México

Microsoft Dynamics AX 2012 gestionaba el impuesto sobre el valor añadido (IVA) sin realizar mediante la funcionalidad específica para México de “impuestos sin realizar”.

|                              |                                                                                                                     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Funcionalidad duplicada                                                                                             |
| **¿Reemplazado por otra característica?** | Sí, esta funcionalidad se ha reemplazado por la funcionalidad estándar de impuestos condicional proporcionada por Core. |
| **Módulos afectados**             | Impuesto                                                                                                                 |

### <a name="microsoft-outlook-integration"></a>Integración de Microsoft Outlook

|                              |                                                                                |
|------------------------------|--------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Esta funcionalidad se ha reemplazado por la integración de Microsoft Exchange Server. |
| **¿Reemplazado por otra característica?** | Sí                                                                            |
| **Módulos afectados**             | Ventas y marketing                                                            |

### <a name="payroll-information-in-human-resources"></a>Información de nómina en Recursos humanos

Información de nómina en Recursos humanos

|                              |                                                                                                                                                                                                                                                                                                                              |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Esta funcionalidad se ha sustituido por páginas principales de nóminas y Recursos Humanos.                                                                                                                                                                                                                                              |
| **¿Reemplazado por otra característica?** | Se han reconfigurado las páginas **Prestaciones**, **Ganancias** y otras páginas relacionadas que estaban anteriormente en nóminas de Estados Unidos y ahora forman parte de la configuración de Recursos humanos base para ayudar con el procesamiento externo de nóminas. A esta función se accede mediante la clave de configuración **Recursos humanos 1** &gt; **Nómina**. |
| **Módulos afectados**             | Recursos humanos, Nómina                                                                                                                                                                                                                                                                                                     |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Bloqueo privado de los diarios de gestión de almacenes e inventarios

Los diarios de almacén e inventario ya no admiten la opción de marcar un diario como privado para un usuario seleccionado. Solo se admite el proceso de bloqueo de diarios como privado para grupos de usuarios y bloqueo durante la edición.

|                              |                                        |
|------------------------------|----------------------------------------|
| **Motivo de la eliminación**       | No se ha encontrado ningún uso de la función. |
| **¿Reemplazado por otra característica?** | No                                     |
| **Módulos afectados**             | Gestión de inventarios                   |

### <a name="product-builder"></a>Configurador de productos

El configurador de productos se usaba para configurar dinámicamente artículos desde un pedido de ventas, presupuesto de ventas, pedido de compra, orden de producción, presupuesto de venta, presupuesto del proyecto o petición de artículo. De acuerdo con un modelo de producto que tenía variables de modelo, el usuario podía seleccionar valores para cumplir con los requisitos del cliente y obtener una variante del producto única con una lista de materiales y una ruta.

|                              |                                                                                                                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | El configurador de productos exponía el código X++ a los usuarios finales y no se admite en la versión actual de Dynamics AX. Se ha retirado para evitar esfuerzos duplicados en bases de código superpuestas y cuantiosas. |
| **¿Reemplazado por otra característica?** | Configuración del producto                                                                                                                                                                                   |
| **Módulos afectados**             | Gestión de información de productos, Ventas y marketing                                                                                                                                                     |

### <a name="rename-product-dimension"></a>Asignar un nuevo nombre a la dimensión del producto

Esta función le permite cambiar el nombre de una de las tres dimensiones de producto estándar (tamaño, color o estilo) a un nombre que cumpla mejor con sus requisitos empresariales. El cambio de nombre incluía todas las etiquetas donde se aislaba el nombre de la dimensión de producto.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La versión actual de Dynamics AX no admite cambios de etiqueta en tiempo de ejecución. |
| **¿Reemplazado por otra característica?** | No                                                                            |
| **Módulos afectados**             | Gestión de información de productos                                                |

### <a name="retail-server-connectivity-using-http"></a>Conectividad de Retail Server mediante HTTP

En Dynamics AX 2012 R3, Retail Server podía trabajar usando la comunicación HTTP (sin seguridad). Esto estaba además de la comunicación estándar mediante HTTPS.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Debido a los nuevos requisitos de seguridad, ahora solo se admite la comunicación segura mediante TLS 1.2 (o un número superior, si está disponible). El instalador de autoservicio configurará automáticamente el equipo para esta comunicación. |
| **¿Reemplazado por otra característica?** | N. º Ahora solo se da soporte a la comunicación de HTTPS estándar.                                                                           |
| **Módulos afectados**             | Retail Server                                                |

### <a name="role-center-pages"></a>Páginas de áreas de trabajo

|                              |                                                                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Las páginas de área de trabajo se crearon en la plataforma de Enterprise Portal obsoleta, la cual se ha actualizado mediante la nueva plataforma de cliente web en la versión actual de Dynamics AX. |
| **¿Reemplazado por otra característica?** | El nuevo patrón del formulario de espacio de trabajo proporciona a los usuarios un diseño centrado en el proceso de fácil acceso a las tareas de uso general dentro de dicho proceso.                       |
| **Módulos afectados**             | Todas                                                                                                                                                                      |

### <a name="sales-tax-jurisdictions"></a>Jurisdicciones de impuestos

|                              |                                              |
|------------------------------|----------------------------------------------|
| **Motivo de la eliminación**       | Poco uso de cliente y conjunto limitado de funciones |
| **¿Reemplazado por otra característica?** | No                                           |
| **Módulos afectados**             | Impuestos de EE.UU                                 |

### <a name="shipping-carrier-interface"></a>Interfaz de transportistas de envío

|                              |                                                                                                                                                 |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Funcionalidad duplicada                                                                                                                         |
| **¿Reemplazado por otra característica?** | Sí, esta característica se ha sustituido parcialmente por Administración de transporte, pero aún no se ha reemplazado por Administración de almacenes básico (WMS I). |
| **Módulos afectados**             | Ventas y marketing, Gestión de inventarios                                                                                                       |

### <a name="sites-services"></a>Sites Service

Servicios de sitios le permite crear sitios web que amplía sus procesos empresariales a Internet sin el soporte técnico de TI.

|                              |                                                                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La infraestructura de Microsoft Azure que se usa por Dynamics AX tiene nuevas capacidades que se pueden usar en su lugar (por ejemplo, sitios de Azure). |
| **¿Reemplazado por otra característica?** | No                                                                                                                                       |
| **Módulos afectados**             | Contratación de RR. HH., gestión de casos, solicitud de presupuestos, registro de proveedor                                                                  |

### <a name="ssas-demand-forecasting-strategy"></a>Estrategia de previsión de la demanda de SSAS

|                              |                                                                              |
|------------------------------|------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | El diseño de la característica no se admite en la nueva arquitectura de la nube. |
| **¿Reemplazado por otra característica?** | Estrategia de previsión de demanda de Aprendizaje automático de Azure                           |
| **Módulos afectados**             | Planificada                                                                     |

### <a name="travel-requisitions"></a>Pedidos de viaje

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| **Motivo de la eliminación**       | Poco uso, y la mayoría de la funcionalidad existían en Enterprise Portal. |
| **¿Reemplazado por otra característica?** | No                                                              |
| **Módulos afectados**             | Gestión de gastos                                              |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Ver detalles de grupo de facturas de proveedor excluidas del registro

|                              |                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Poco uso. Esta funcionalidad se ha reemplazado por el Diario de facturas que tiene la funcionalidad del flujo de trabajo. |
| **¿Reemplazado por otra característica?** | Capacidades del flujo de trabajo del Diario de facturas.                                                           |
| **Módulos afectados**             | Proveedores                                                                                        |

### <a name="virtual-company-accounts"></a>Cuentas de empresa virtuales

La característica de empresas virtuales ya no se admite en Dynamics AX. La característica de empresas virtuales permite a los usuarios configurar tablas que se puedan compartidas por un conjunto de empresas. Puede obtener una descripción de la función, vea [Cuentas de empresa y cuentas de empresa virtuales](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). La función trabaja agrupando tablas en recopilaciones que se asignan a empresas virtuales, que son grupos de empresas “reales” existentes. Se crean consultas de modo que todas las empresas de la empresa virtual puedan obtener acceso a los datos de las tablas de las recopilaciones de tablas asociadas.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><b>Motivo de la eliminación</b></td>
<td><ul>
<li>Las empresas virtuales deben configurarse antes de que los datos se puedan guardar en las tablas. La retroadaptación de las empresas virtuales en la implementación existente es muy difícil.</li>
<li>Dado que se han normalizado tantos datos en la versión actual de Microsoft Dynamics AX, se ha vuelto difícil saber qué agregar a las colecciones de tablas. Por ejemplo, es difícil saber qué tablas compartir. Todas las tablas a las que se hace referencia desde las tablas en una empresa virtual también se deben agregar. Debido a la normalización de la tabla, incluso los datos maestros sencillos que se extienden en múltiples tablas deben formar parte de la empresa virtual. Cualquier error que se realice producirá problemas funcionales.</li>
<li>Cuando una tabla forma parte de una empresa virtual, pierde la información acerca del origen de los datos, y solo se registra la empresa virtual.</li>
</ul></td>
</tr>
<tr class="even">
<td><b>¿Reemplazado por otra característica?</b></td>
<td>Se pueden usar tablas globales para que las tablas sean accesibles desde todas las empresas. Actualmente no hay ninguna sustitución.</td>
</tr>
<tr class="odd">
<td><b>Módulos afectados</b></td>
<td>No aplicable</td>
</tr>
</tbody>
</table>

### <a name="warehouse-management-ii"></a>Gestión de almacenes II

|                              |                                                                                                                                                                                                                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | La solución Gestión de almacenes II (WMS II) que estaba disponible en el módulo **Gestión de inventarios** duplica la funcionalidad en el módulo **Gestión de almacenes** que se lanzó en Microsoft Dynamics AX 2012 R3.                                                                         |
| **¿Reemplazado por otra característica?** | El módulo **Administración de almacenes** lanzado en AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8 y Dynamics AX 2012 R3 CU9 reemplaza las funciones de Gestión de almacenes II. El nuevo módulo dispone de características más avanzadas y procesos más flexibles de gestión de almacenes que Gestión de almacenes II. |
| **Módulos afectados**             | Gestión del inventario, ventas y marketing, adquisición y abastecimiento                                                                                                                                                                                                                                         |

### <a name="worker-reminders-in-human-resources"></a>Recordatorios de trabajador en Recursos humanos

Información de nómina en Recursos humanos

|                              |                 |
|------------------------------|-----------------|
| **Motivo de la eliminación**       | Poco uso       |
| **¿Reemplazado por otra característica?** | No              |
| **Módulos afectados**             | Recursos humanos |

### <a name="workplanner"></a>Planificador de trabajo

|                              |                                                                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Poco uso                                                                                                                                                            |
| **¿Reemplazado por otra característica?** | No, pero la página **Relación de perfiles**, que se abre desde la página **Grupos de perfiles**, admite el mismo escenario empresarial que la página **Planificador de trabajo** desaprobada. |
| **Módulos afectados**             | Tiempo y asistencia                                                                                                                                                  |

### <a name="x-financial-statements"></a>Informes financieros de X++

|                              |                                                                                             |
|------------------------------|---------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Esta funcionalidad se ha reemplazado por otra característica.                                    |
| **¿Reemplazado por otra característica?** | Management Reporter (etiquetado **Informes financieros** en la versión actual de Dynamics AX) |
| **Módulos afectados**             | Contabilidad general                                                                              |


