---
title: "Características en desuso"
description: "Este tema describe las funciones que se han eliminado, o que está previsto que se eliminen."
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Platform
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 6
ms.translationtype: Human Translation
ms.sourcegitcommit: 3267bd1cbd738b5ced9996fc3b28eee211627591
ms.openlocfilehash: 8feffb27b5d08a9c90e97ac0d7e00abf0448d0df
ms.contentlocale: es-es
ms.lasthandoff: 06/16/2017


---

# Características en desuso
<a id="deprecated-features" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Este tema describe las funciones que se han eliminado, o que está previsto que se eliminen.

## Funciones que se han dejado de utilizar en Dynamics 365 for Finance and Operations, Enterprise Edition (actualización de julio de 2017)
<a id="features-that-have-been-deprecated-in-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update" class="xliff"></a>

### Portal de dispositivos móviles de almacén
<a id="warehouse-mobile-devices-portal" class="xliff"></a>

El portal de dispositivos móviles de almacén (WMDP) era componente independiente pensando para la implementación propia localmente. Este componente ya no se admite en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Una aplicación nativa que mejora la experiencia del usuario ha sustituido a la funcionalidad de WMDP. 

|                                  |                                                 |
|----------------------------------|-------------------------------------------------|
| **Motivo de la eliminación**       | Funcionalidad duplicada.                        |
| **¿Reemplazado por otra característica?** | Sí. Esta función se ha sustituido por Finance and Operations - Warehousing. Para obtener más información sobre la configuración y requisitos previos, consulte [Instalar y configurar Microsoft Dynamics 365 for Finance and Operations - Warehousing](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/install-configure-warehousing-app). |
| **Módulos afectados**             | Gestión de almacenes y administración de transporte |

### Regla de correspondencia de conciliación bancaria para coincidencia manual
<a id="advanced-bank-reconciliation-matching-rule-for-manual-matching" class="xliff"></a>

Una regla de coincidencia se utilizó para seleccionar y marcar un documento bancario cuando los documentos se conciliaron manualmente en la hoja de cálculo de conciliación.

|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Uso limitado.                                                                         |
| **¿Reemplazado por otra característica?** | N. º Las capacidades de filtro de columnas se deben usar para buscar los documentos de la conciliación. |
| **Módulos afectados**             | Gestión de efectivo y bancos                                                               |

### Aplicación para tabletas con Windows 8
<a id="windows-8-tablet-app" class="xliff"></a>

La aplicación para tabletas con Windows 8 ofrecía funcionalidad para la entrada y la aprobación de gastos.

|                                  |                                                                                          |
|----------------------------------|------------------------------------------------------------------------------------------|
| **Motivo de la eliminación**       | Finance and Operations es compatible con las tabletas. La aplicación para tabletas ya no se requiere. |
| **¿Reemplazado por otra característica?** | N. º                                                                                      |
| **Módulos afectados**             | Gestión de gastos                                                                       |


Funciones que se han dejado de utilizar en Dynamics 365 for Operations 1611 con la actualización de la plataforma 3
<a id="features-that-have-been-deprecated-in-dynamics-365-for-operations-1611-with-platform-update-3" class="xliff"></a>
---------------------------------------------------------------------------------------------

### Formatos de pago de AEB para España
<a id="aeb-payment-formats-for-spain" class="xliff"></a>

Los formatos de pago del Consejo Superior Bancario se usan para enviar remesas al banco de los pagos de cliente y proveedor. El contenido de estos formatos lo determina aa Asociación Española de Banca. Cubre Cuadernos 19, 32, 58, 34.

|                              |                                                                          |
|------------------------------|--------------------------------------------------------------------------|
| Motivo de la eliminación       | Los formatos de pago ya no se usan.                                  |
| ¿Reemplazado por otra característica? | Sí, transferencia de crédito ISO20022 y formatos de pago de domiciliación bancaria para España |
| Módulos afectados             | Cuentas de proveedores, cuentas de clientes                                    |

### Transferencia de pagos bancarios para Lituania
<a id="bank-payments-transfer-for-lithuania" class="xliff"></a>

Las transferencias de los pagos bancarios se generan e imprimen mediante el formato de exportación de Transferencia de pagos (LT) para Lituania. El mercado lituano empezó a usar LITAS, el sistema unificado de banca electrónica, en 2005.

|                              |                                                            |
|------------------------------|------------------------------------------------------------|
| Motivo de la eliminación       | Los formatos de pago ya no se usan.                    |
| ¿Reemplazado por otra característica? | Sí, formato de pago de transferencia de crédito ISO20022 para Lituania |
| Módulos afectados             | Proveedores                                           |

### Formatos de pago de BBS Direkte Remittering para Noruega
<a id="bbs-direkte-remittering-payment-formats-for-norway" class="xliff"></a>

Los formatos de pago de BBS Direkte Remittering incluyen la exportación del cobro de pago de cliente (domiciliación bancaria) y la importación de la devolución del mensaje.

|                              |                                                                                                                                                                |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Los formatos de pago ya no se usan.                                                                                                                        |
| ¿Reemplazado por otra característica? | El formato de pago de un cliente de AvtaleGiro para Noruega se puede usar para generar los mensajes de domiciliación bancaria. La importación de la devolución del mensaje será implementada en próximas versiones. |
| Módulos afectados             | Cuentas de proveedores, cuentas de clientes                                                                                                                          |

### Herramienta para el plan de cuentas para España
<a id="chart-of-accounts-tool-for-spain" class="xliff"></a>

Se utiliza esta herramienta cuando un plan de cuentas en España requiere cambios importantes. Los usuarios pueden importar un nuevo plan de cuentas en Microsoft Excel o en formato de texto, y también pueden importar los informes financieros.

|                              |                |
|------------------------------|----------------|
| Motivo de la eliminación       | Uso limitado  |
| ¿Reemplazado por otra característica? | Nº             |
| Módulos afectados             | Contabilidad general |

### Formato de pago Dom80 para Bélgica
<a id="dom80-payment-format-for-belgium" class="xliff"></a>

Formato de pago Legacy Belga para cobro de pago (domiciliación bancaria).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Motivo de la eliminación       | El formato de pago ya no se usa.                  |
| ¿Reemplazado por otra característica? | Sí, formato de pago de domiciliación bancaria ISO 20022 para Bélgica. |
| Módulos afectados             | Clientes                                    |

### Formatos de pago DTA/EZAG para Suiza
<a id="dtaezag-payment-formats-for-switzerland" class="xliff"></a>

Los formatos DTA/EZAG se integran en el sistema ESR, ya que pueden contener un número de referencia. Puesto que el número de referencia no es obligatorio, los formatos se pueden usar para procesar los pagos de proveedor. Estos formatos los usan las empresas con una cuenta bancaria en una ubicación diferente de “Postfinance.”

|                              |                                                              |
|------------------------------|--------------------------------------------------------------|
| Motivo de la eliminación       | Los formatos de pago ya no se usan.                      |
| ¿Reemplazado por otra característica? | Sí, formato de pago de transferencia de crédito ISO20022 para Suiza |
| Módulos afectados             | Proveedores                                             |

### Formato de pago de EDIFACT-DIRDEB para Austria
<a id="edifact-dirdeb-payment-format-for-austria" class="xliff"></a>

Formato de pago de EDIFACT-DIRDEB para cobro de pago (domiciliación bancaria).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Motivo de la eliminación       | El formato de pago ya no se usa.                  |
| ¿Reemplazado por otra característica? | Sí, formato de pago de domiciliación bancaria ISO 20022 para Austria |
| Módulos afectados             | Clientes                                    |

### EDIVAT para Bélgica
<a id="edivat-for-belgium" class="xliff"></a>

EDIVAT es una norma belga obsoleta para la declaración electrónica a través de correo seguro. Microsoft Dynamics AX 2012 conserva la opción de sólo lectura para habilitar el acceso a los datos históricos.

|                              |                                      |
|------------------------------|--------------------------------------|
| Motivo de la eliminación       | La función ya no se usa. |
| ¿Reemplazado por otra característica? | Nº                                   |
| Módulos afectados             | Contabilidad general                       |

### Formato de importación de pago de eGiro EDIFACT CREMUL para Noruega
<a id="egiro-edifact-cremul-payment-import-format-for-norway" class="xliff"></a>

eGiro se basa en la norma internacional UN EDIFACT CREMUL (Mensaje de aviso de crédito múltiple), que se usa para el registro automático de pagos del cliente. En Microsoft Dynamics AX, eGiro se implementa como formato de importación de pago de cliente.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | El formato de pago ya no se usa.                                                     |
| ¿Reemplazado por otra característica? | N. º El formato se sustituirá por formatos ISO 20022 de importación de criterio en próximas versiones. |
| Módulos afectados             | Clientes                                                                       |

### Inventario externo para Polonia
<a id="external-inventory-for-poland" class="xliff"></a>

Pruebas de mercancías que se toman de un proveedor para las venta sin compra. Las mercancías que son gestionadas en un inventario externo, no afectan al inventario estándar y se pueden vender y comprar después automáticamente. Este proceso crea los movimientos de inventario reales.

|                              |                                                 |
|------------------------------|-------------------------------------------------|
| Motivo de la eliminación       | Reemplazado por otra característica                     |
| ¿Reemplazado por otra característica? | Sí, la funcionalidad básica de entrada de envío |
| Módulos afectados             | Cuentas de proveedores, gestión de inventario          |

### Generador de informes financieros para Europa Oriental
<a id="financial-reports-generator-for-eastern-europe" class="xliff"></a>

Se utiliza una herramienta para configurar la recopilación de datos para los informes de contabilidad e impuestos, y para exportar datos a plantillas de informes XLS y DOC.

|                              |                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Uso limitado                                                                            |
| ¿Reemplazado por otra característica? | N. º La herramienta se reemplazará por las configuraciones de informes electrónicas en próximas versiones. |
| Módulos afectados             | Contabilidad general                                                                           |

### Importación de las transacciones de pago del cliente para Finlandia
<a id="import-of-customer-payment-transactions-for-finland" class="xliff"></a>

Puede seleccionar un formato de importación para los pagos finlandeses para importar las transacciones de pago del cliente desde un archivo externo proporcionado por el banco.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | El formato de pago ya no se usa.                                                     |
| ¿Reemplazado por otra característica? | N. º El formato se sustituirá por formatos ISO 20022 de importación de criterio en próximas versiones. |
| Módulos afectados             | Clientes                                                                       |

### Importación de transacciones de pago en un diario de contabilidad general para Finlandia
<a id="import-of-payment-transactions-into-a-general-ledger-journal-for-finland" class="xliff"></a>

Se usa un formato específico para Finlandia para importar las transacciones de contabilidad en la contabilidad general.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | El formato de pago ya no se usa.                                                     |
| ¿Reemplazado por otra característica? | N. º El formato se sustituirá por formatos ISO 20022 de importación de criterio en próximas versiones. |
| Módulos afectados             | Clientes                                                                       |

### Integración con el software Isabel sincronizado (CIS) para Bélgica
<a id="integration-with-isabel-synchronized-cis-for-belgium" class="xliff"></a>

Isabel es el marco de trabajo de la banca electrónica en Europa y es una norma de hecho en Bélgica.

|                              |                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | La integración con el cliente Isabel se ha interrumpido.                                                                |
| ¿Reemplazado por otra característica? | N. º Los formatos de pago que ya no se usan son reemplazados por el formato de pago de transferencia de crédito ISO20022 para Bélgica. |
| Módulos afectados             | Proveedores                                                                                                     |

### Modificaciones del plan de cuentas y reglas de contabilidad para España
<a id="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain" class="xliff"></a>

Esta característica se usa para los cambios en el plan de cuentas y en las reglas de contabilidad de España. Asigna cuentas para ayudar a transformar el antiguo plan de cuentas en el nuevo plan contable, y compara el ejercicio anterior con el nuevo ejercicio, incluso si se han registrado en números de cuenta distintos.

|                              |                |
|------------------------------|----------------|
| Motivo de la eliminación       | Uso limitado  |
| ¿Reemplazado por otra característica? | Nº             |
| Módulos afectados             | Contabilidad general |

### Formato de pago de proveedor de Pagamento Fornittori
<a id="pagamento-fornittori-vendor-payment-format" class="xliff"></a>

Formato de pago de transferencia de crédito de Legacy italiano.

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Motivo de la eliminación       | El formato de pago ya no se usa.                  |
| ¿Reemplazado por otra característica? | Sí, formato de pago de transferencia de crédito ISO20022 para Italia |
| Módulos afectados             | Proveedores                                       |

### Formatos de exportación de pagos para Estonia
<a id="payment-export-formats-for-estonia" class="xliff"></a>

Los formatos de Telehansa y Teleservicio se usan para la exportación de pago bancario.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Motivo de la eliminación       | Los formatos de pago ya no se usan.                  |
| ¿Reemplazado por otra característica? | Sí, formato de pago de transferencia de crédito ISO20022 para Estonia |
| Módulos afectados             | Proveedores                                         |

### Archivo de pago para Noruega
<a id="payment-file-archive-for-norway" class="xliff"></a>

Cuando se generan los archivos de pago, el archivo almacena automáticamente todos los archivos que se crean, incluso los que se han escrito o leído con anterioridad.

|                              |                                                                    |
|------------------------------|--------------------------------------------------------------------|
| Motivo de la eliminación       | Reemplazado por otra característica                                        |
| ¿Reemplazado por otra característica? | Sí, trabajos archivados de informes electrónicos                            |
| Módulos afectados             | Cuentas de proveedores, cuentas de clientes, administración de la empresa |

### Formatos de importación de pagos para Estonia
<a id="payment-import-formats-for-estonia" class="xliff"></a>

Los formatos de Telehansa y TeleTeenus se usan para la importación de pago bancario.

|                              |                                                                                            |
|------------------------------|--------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Los formatos de pago ya no se usan.                                                    |
| ¿Reemplazado por otra característica? | N. º Los formatos se sustituirán por formatos ISO 20022 de importación de criterio en próximas versiones. |
| Módulos afectados             | Clientes                                                                        |

### Flujo de trabajo de objetivo de gestión del rendimiento
<a id="performance-management-goal-workflow" class="xliff"></a>

La gestión del rendimiento incluye la administración y la integración del objetivo con las evaluaciones de rendimiento.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | La gestión del rendimiento se diseñó de nuevo y el número de páginas de objetivos se redujo para simplificar el proceso.                 |
| ¿Reemplazado por otra característica? | N. º Los objetivos son visibles para los administradores a través del portal Manager Self Service, y se pueden ver y cambiar por el administrador. |
| Módulos afectados             | Gestión del capital humano                                                                                                 |

### Formatos de pago de Postgirot y Postgirot Utland para Suecia
<a id="postgirot-and-postgirot-utland-payment-formats-for-sweden" class="xliff"></a>

Formatos de pago de Postgirot y Postgirot Utland para Suecia.

|                              |                                                         |
|------------------------------|---------------------------------------------------------|
| Motivo de la eliminación       | Los formatos de pago ya no se usan.                 |
| ¿Reemplazado por otra característica? | Sí, formato de pago de transferencia de crédito ISO20022 para Suecia |
| Módulos afectados             | Proveedores                                        |

### Identificador por radiofrecuencia
<a id="radio-frequency-identifier" class="xliff"></a>

La identificación por radiofrecuencia (RFID) es una tecnología de recopilación de datos que utiliza etiquetas electrónicas para almacenar datos de identificación y no precisa ningún lector de requisitos visuales para capturarlos.

|                              |                                               |
|------------------------------|-----------------------------------------------|
| Motivo de la eliminación       | Poco uso de cliente y conjunto limitado de funciones. |
| ¿Reemplazado por otra característica? | No                                            |
| Módulos afectados             | Gestión del inventario                          |

### Informe sobre la numeración del estado de las facturas para Letonia
<a id="report-about-state-invoices-numbering-for-latvia" class="xliff"></a>

La legislación letona proporciona reglas específicas acerca de la numeración de las facturas de ventas. Dicha funcionalidad le permite asignar números específicos a las facturas de ventas, en función del usuario o del grupo de usuarios. A continuación puede generar un informe o un archivo XML. También puede imprimir un informe sobre los números de factura que se usan.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | La numeración de la factura de estado ya no tiene que mantenerse. El informe sobre números de factura utilizados ya no es necesario. |
| ¿Reemplazado por otra característica? | Nº                                                                                                                       |
| Módulos afectados             | Clientes                                                                                                      |

### Configuración de los nombres del administrador y el contable general de una empresa para Lituania
<a id="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania" class="xliff"></a>

Los nombres del administrador y el contable general de una empresa se pueden especificar en la información de la empresa y usar en distintas copias impresas locales del informe.

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Motivo de la eliminación       | Reemplazado por otra característica                                     |
| ¿Reemplazado por otra característica? | Sí, la configuración de funcionarios se puede usar con el mismo propósito.   |
| Módulos afectados             | Clientes, Proveedores, Gestión de efectivo y bancos |

### Formatos de pago Telepay para Noruega
<a id="telepay-payment-formats-for-norway" class="xliff"></a>

Los formatos de pago Telepay incluyen la exportación del pago de proveedor (transferencia de crédito) y el cobro de pago del cliente (domiciliación bancaria).

|                              |                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Los formatos de pago ya no se usan.                                                        |
| ¿Reemplazado por otra característica? | Sí, formato de pago de transferencia de crédito ISO20022 y formato de pago del cliente de AvtaleGiro para Noruega |
| Módulos afectados             | Cuentas de proveedores, cuentas de clientes                                                          |

### Formatos de exportación de pago de proveedores para Finlandia
<a id="vendor-payment-export-formats-for-finland" class="xliff"></a>

Dos formatos para exportar pagos están disponibles para Finlandia. LM02 (FI) se usa para pagos nacionales y LUM2 (FI) se usa para pagos extranjeros.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Motivo de la eliminación       | Los formatos de pago ya no se usan.                  |
| ¿Reemplazado por otra característica? | Sí, formato de pago de transferencia de crédito ISO20022 para Finlandia |
| Módulos afectados             | Proveedores                                         |

### Flujo de trabajo para crear objetivos
<a id="workflow-for-creating-goals" class="xliff"></a>

Un flujo de trabajo para gestionar la creación de los objetivos del empleado es uno de varios flujos de trabajo que estaban disponibles para ayudar a coordinar el proceso de gestión del rendimiento.

|                              |                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | La gestión del rendimiento se ha vuelto a diseñar por completo en Microsoft Dynamics 365 for Finance and Operations.                                                                                                                                                                                                                                        |
| ¿Reemplazado por otra característica? | La característica de Gestión del rendimiento que se ha diseñado de nuevo proporciona más control sobre el contenido de los objetivos, las medidas que se utilizan para realizar el seguimiento del progreso y los datos adjuntos de la documentación correspondiente. Los objetivos se pueden almacenar como plantillas y volverse a utilizar. Esta función puede ayudarle a configurar los objetivos adicionales para sus empleados con más rapidez. |
| Módulos afectados             | Gestión del capital humano                                                                                                                                                                                                                                                                                                               |

## Funciones que ya no se utilizan en las versiones de Dynamics AX 7.0
<a id="features-deprecated-in-dynamics-ax-70-releases" class="xliff"></a>
### Capacidad para cancelar cambios en una factura de proveedor
<a id="ability-to-cancel-changes-to-a-vendor-invoice" class="xliff"></a>

|                              |                         |
|------------------------------|-------------------------|
| Motivo de la eliminación       | Mejora del rendimiento |
| ¿Reemplazado por otra característica? | No                      |
| Módulos afectados             | Proveedores        |

### Integración de AIF, Axd y AxBC
<a id="aif-axd-and-axbc-integrations" class="xliff"></a>

En Application Integration Framework (AIF), los datos se pueden intercambiar con sistemas externos por medio de lógica de negocios expuesta como servicios. Dynamics AX incluye servicios que se basan en documentos y en .NET Business Connector (AxBC). Los documentos se crean mediante XML. El XML incluye información de encabezado que se agrega para crear un *mensaje* que se puede transferir a o de Dynamics AX. Algunos ejemplos de documentos son los pedidos de compra y venta. No obstante, casi cualquier entidad, como un cliente, puede ser representado por un documento. Los servicios que se basan en documentos usan las clases **Axd &lt;*Documento*&gt;.

|                              |                                                                                                                                                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | La arquitectura de AIF y de AxDs no se podría escalar un servicio de nube. Ha habido problemas de rendimiento en la importación masiva.                                                                               |
| ¿Reemplazado por otra característica? | En la versión actual de Dynamics AX, esta característica se sustituye por el marco de importación y exportación de datos, compatible con la importación y exportación masiva recurrente. Para AxBC, se recomienda usar las tablas reales. |
| Módulos afectados             | AxDs, AxBC y AIF                                                                                                                                                                                     |

### L. MAT sin versiones de L. MAT
<a id="boms-without-bom-versions" class="xliff"></a>

Cuando la clave de configuración **Versiones de L. MAT.** se deshabilita, las versiones de la lista de materiales se ocultan en todos los formularios, y el sistema fuerza una relación 1:1 entre los productos liberados y las listas de materiales. En la versión actual de Dynamics AX, no se puede deshabilitar la clave de configuración **Versiones de L. MAT**.

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| Motivo de la eliminación       | El uso de una clave de configuración para controlar las versiones de listas de materiales no se escala en un entorno de nube. |
| ¿Reemplazado por otra característica? | No                                                                                      |
| Módulos afectados             | Gestión de información de productos, Gestión de inventarios                                    |

### Bordero brasileño
<a id="brazilian-bordero" class="xliff"></a>

Forma de pago específica para las empresas brasileñas

|                              |                                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | La ayuda de la forma de pago para el Bordero brasileño se ha interrumpido para la ubicación brasileña |
| ¿Reemplazado por otra característica? | Nº                                                                                                    |
| Módulos afectados             | Proveedores                                                                                      |

### Extracto de Sintegra brasileño
<a id="brazilian-sintegra-statement" class="xliff"></a>

Extracto del impuesto federal para el impuesto de ICMS

|                              |                                                                                                                       |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Este extracto ya no se aplica en algunos estados brasileños.                                                     |
| ¿Reemplazado por otra característica? | N. º Los usuarios pueden utilizar la herramienta de informes electrónica genérica para configurar el extracto si es necesario de acuerdo a situaciones específicas. |
| Módulos afectados             | Libros fiscales                                                                                                          |

### Modo brasileño de contingencia SCAN brasileña para NF-e
<a id="brazilian-scan-contingency-mode-for-nf-e" class="xliff"></a>

El entorno de contingencia de (SCAN) se usa para generar, exportar e importar el estado de una Nota fiscal electrónica (NF-e) cuando el entorno de la Secretaría de Hacienda (SEFAZ) no está disponible.

|                              |                                                                             |
|------------------------------|-----------------------------------------------------------------------------|
| Motivo de la eliminación       | Este método de contingencia ya no es un aplicable en todos los estados brasileños |
| ¿Reemplazado por otra característica? | Nº                                                                          |
| Módulos afectados             | Clientes                                                         |

### Analizador de negocio
<a id="business-analyzer" class="xliff"></a>

Esta aplicación móvil permite a los usuarios revisar métricas de negocio clave.

|                              |                                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Esta funcionalidad se ha reemplazado por otra característica.                                                                                                      |
| ¿Reemplazado por otra característica? | El paquete de contenido de supervisión del rendimiento financiero para Microsoft Power BI incluirá métricas financieras clave anteriormente disponibles en Business Analyzer. |
| Módulos afectados             | Contabilidad general                                                                                                                                                |

### Estadísticas comerciales
<a id="business-statistics" class="xliff"></a>

La configuración de consultas de estadísticas comerciales que le pueden ayudar a analizar el rendimiento de la organización

|                              |                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Método de herencia para la inteligencia empresarial (BI), poco uso por parte del cliente y un conjunto limitado de características |
| ¿Reemplazado por otra característica? | Nuevas soluciones de inteligencia empresarial para la versión actual de Dynamics AX                                      |
| Módulos afectados             | Adquisición y abastecimiento, Proveedores, Ventas y marketing, Clientes.         |

### Cambio de la función de fecha de documento en el diario de aprobación de facturas
<a id="change-document-date-function-in-invoice-approval-journal" class="xliff"></a>

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Motivo de la eliminación       | Poco uso                                                               |
| ¿Reemplazado por otra característica? | Sí. La fecha de documento en la transacción de proveedor registrada puede cambiarse. |
| Módulos afectados             | Proveedores                                                        |

### Formato de pago ClieOp03 para Países Bajos
<a id="clieop03-payment-format-for-the-netherlands" class="xliff"></a>

|                              |                                                                                                            |
|------------------------------|------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | El formato ya no es aplicable en los Países bajos, ya que se ha sustituido por la funcionalidad SEPA. |
| ¿Reemplazado por otra característica? | Exportación de pagos SEPA                                                                                       |
| Módulos afectados             | Todas                                                                                                        |

### Centro de cumplimiento
<a id="compliance-center" class="xliff"></a>

El Centro de cumplimiento era un sitio de Enterprise Portal para gestionar los requisitos de documentación para las iniciativas de conformidad relacionadas con la ley Sarbanes-Oxley.

|                              |                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Falta de uso del cliente. Microsoft SharePoint incluye la misma capacidad que estaba disponible en el Centro de cumplimiento. |
| ¿Reemplazado por otra característica? | No                                                                                                                     |
| Módulos afectados             | Cumplimiento y controles internos                                                                                       |

### Conector para Microsoft Dynamics
<a id="connector-for-microsoft-dynamics" class="xliff"></a>

Esta herramienta se usó para integrar datos clave de Microsoft Dynamics CRM en las aplicaciones de Microsoft Dynamics ERP.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Motivo de la eliminación       | Esta funcionalidad se ha reemplazado por otra característica. |
| ¿Reemplazado por otra característica? | Integrador de Dynamics                                      |
| Módulos afectados             | Conector para Microsoft Dynamics                         |

### Unidad de contenedor y multidimensión disponibles
<a id="container-unit-and-multi-dimension-on-hand" class="xliff"></a>

|                              |                                                                                                                                                                 |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Funcionalidad duplicada                                                                                                                                         |
| ¿Reemplazado por otra característica? | Sí. Desde AX 2012, esta funcionalidad se ha reemplazado por el conjunto de características de pedidos de lotes consolidados. Este conjunto de características incluye la vista disponible consolidada. |
| Módulos afectados             | Gestión de información de productos, Control de producción, Administración de inventario, Ventas y marketing                                                                   |

### Metadatos de grupo de pilas
<a id="cue-group-metadata" class="xliff"></a>

|                              |                                                                                                                                                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Los grupos de pilas se usaban para mostrar una o más pilas en el área de cuadro informativo. La capacidad era limitada y había también problemas de rendimiento, porque un cambio de registro en un formulario principal generaba una consulta por pila en el grupo de pilas. |
| ¿Reemplazado por otra característica? | No                                                                                                                                                                                                                            |
| Módulos afectados             | Todas                                                                                                                                                                                                                           |

### Metadatos de pila
<a id="cue-metadata" class="xliff"></a>

|                              |                                                                                                                                                                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Los metadatos de pila estaban limitados a contar o sumar información.                                                                                                                                                                                   |
| ¿Reemplazado por otra característica? | Los metadatos de icono se introdujeron para proporcionar más flexibilidad para modelar. Por ejemplo, puede modelar recuentos actuales, navegación e indicadores de rendimiento clave (KPI). Los metadatos de icono de recuento sustituyen directamente a los metadatos de pila. |
| Módulos afectados             | Todas                                                                                                                                                                                                                                     |

### Formato de cheque danés
<a id="danish-check-format" class="xliff"></a>

|                              |                                                                                                                         |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Se ha dejado de permitir usar el diseño de formato de cheque danés, y el informe se ha retirado de la localización DK. |
| ¿Reemplazado por otra característica? | No                                                                                                                      |
| Módulos afectados             | Todas                                                                                                                     |

### Particiones de datos
<a id="data-partitions" class="xliff"></a>

Las particiones de los datos proporcionan una separación lógica de datos en la base de datos de Microsoft Dynamics AX.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Las particiones de datos se introdujeron en Microsoft Dynamics AX 2012 R2 para habilitar el aislamiento de los datos. En un escenario común, una compañía tiene filiales y los datos de una filial no deben ser visibles para otra, aunque el mismo departamento de TI administre ambas filiales. Sin embargo, se requerían gastos generales de administración y scripts adicionales en todo el programa para crear nuevas particiones y rellenarlas con datos y hacer copia de seguridad de los datos de partición. En la nube, donde tenemos acceso a la plataforma como servicios de base de datos (Base de datos SQL de Microsoft Azure) de un servicio (PaaS), es mucho más eficaz utilizar una base de datos como el contenedor de aislamiento para realizar el aislamiento en el programa. Con independencia de si se requiere la partición de datos para filiales, para varios inquilinos o simplemente para escala, creemos que los escenarios se pueden controlar mejor a través de varias bases de datos o varias instancias de Dynamics AX. |
| ¿Reemplazado por otra característica? | Se reemplazarán las particiones de datos mediante el soporte para múltiples bases de datos o instancias de Dynamics AX en una versión futura.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Módulos afectados             | Todas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

### Delimitación
<a id="delimitation" class="xliff"></a>

|                              |                                        |
|------------------------------|----------------------------------------|
| Motivo de la eliminación       | No se ha encontrado ningún uso de la función. |
| ¿Reemplazado por otra característica? | No                                     |
| Módulos afectados             | Tiempo y asistencia                    |

### Cliente de escritorio
<a id="desktop-client" class="xliff"></a>

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | La experiencia de cliente de Dynamics AX se ha rediseñado para mejorar la capacidad de uso en varias plataformas y dispositivos.                      |
| ¿Reemplazado por otra característica? | El nuevo cliente web se basa en los metadatos de formulario de escritorio y el modelo de programación que se han modificado para proporcionar una plataforma web enriquecida. |
| Módulos afectados             | Todas                                                                                                                                    |

### Conexión con base de datos directa
<a id="direct-database-connection" class="xliff"></a>

En Dynamics AX 2012 R3, Retail Modern POS podía conectarse directamente a la base de datos de canales de forma parecida a la de Enterprise POS. Esto se añadía al método de comunicación estándar en que Retail Modern POS se comunicaba mediante Retail Server.  

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| Motivo de la eliminación       | La conectividad directa de la base de datos requería protocolos de seguridad inferiores y se usaba principalmente para alcanzar niveles de rendimiento más altos. Debido a las mejoras del rendimiento y de seguridad que se han producido en Finance and Operations, esta funcionalidad ahora está dando más problemas que soluciones. |
| ¿Reemplazado por otra característica? | N. º Ahora solo se da soporte a la comunicación de Retail Server estándar.    |
| Módulos afectados             | Base de datos de canales/Retail Modern POS                                    |

### SWIFT MT940 holandés
<a id="dutch-swift-mt940" class="xliff"></a>

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Ahora se utiliza la función genérica en lugar de la función localizada.                                                                                                                                                                 |
| ¿Reemplazado por otra característica? | Sí, esta función se ha reemplazado por la funcionalidad avanzada de conciliación bancaria. Además, se prevé la implementación de la importación de extractos de cuenta camt.053 ISO20022 para el Diario general en la siguiente actualización de Dynamics AX. |
| Módulos afectados             | Todas                                                                                                                                                                                                                                   |

### eBilanz (XBRL para Alemania)
<a id="ebilanz-xbrl-for-germany" class="xliff"></a>

Esta funcionalidad proporcionaba salida en el lenguaje eXtensible Business Reporting Language (XBRL) pensada específicamente para la taxonomía alemana eBilanz.

|                              |                                                                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Falta de uso del cliente                                                                                                                                                 |
| ¿Reemplazado por otra característica? | Esta característica no se ha sustituido por otra, pero hay disponibles varios paquetes XBRL especializados que proporcionan funcionalidad XBRL enriquecida para el mercado alemán. |
| Módulos afectados             | Management Reporter                                                                                                                                                    |

### Cliente de Enterprise Portal
<a id="enterprise-portal-client" class="xliff"></a>

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Se ha proporcionado una sola plataforma de cliente.                                                                                            |
| ¿Reemplazado por otra característica? | El nuevo cliente web se basa en los metadatos del formulario de escritorio y el modelo de programación que se han modificado para proporcionar una plataforma web enriquecida. |
| Módulos afectados             | Todas                                                                                                                                    |

### Sustentabilidad ambiental
<a id="environmental-sustainability" class="xliff"></a>

|                              |                                                    |
|------------------------------|----------------------------------------------------|
| Motivo de la eliminación       | Poco uso de cliente y conjunto limitado de funciones       |
| ¿Reemplazado por otra característica? | No                                                 |
| Módulos afectados             | Cumplimiento y controles internos, Proveedores |

### Controles de formulario de host administrados y ActiveX
<a id="form-activex-and-managed-host-controls" class="xliff"></a>

|                              |                                                                                                                                                                                               |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Los controles ActiveX y de host administrados se basan en el cliente de escritorio obsoleto.                                                                                                             |
| ¿Reemplazado por otra característica? | El marco de controles extensibles admite la creación de nuevos controles que se basan en HTML, CSS y Javascript, y es un control de primera clase en el entorno de Microsoft Visual Studio Tooling. |
| Módulos afectados             | Todas                                                                                                                                                                                           |

### Generación de prenotas mediante un lote
<a id="generate-prenotes-by-using-a-batch" class="xliff"></a>

La generación de prenotas no se puede hacer mediante un lote pero sí la puede realizar un usuario.

|                              |                                                                                                        |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | No hay manera de persistir y mostrar el archivo de prenota resultante cuando se genera mediante un lote. |
| ¿Reemplazado por otra característica? | Aún se pueden generar prenotas y el usuario tiene control sobre la ubicación en la que se guarda el archivo.   |
| Módulos afectados             | Clientes, Proveedores, Gestión de efectivo y bancos                                        |

### Exportación de pagos DTAUS alemanes e importación de extractos de cuentas (totales y transacciones)
<a id="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions" class="xliff"></a>

|                              |                                                                                                                                                                                                                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | El formato ya no es aplicable en Alemania, ya que se ha sustituido por la funcionalidad SEPA (zona única de pagos en euros).                                                                                                                                                                 |
| ¿Reemplazado por otra característica? | Sí, esta funcionalidad se ha reemplazado por la funcionalidad de exportación de pagos SEPA y conciliación bancaria avanzada para importar extractos de cuenta. Además, se prevé la implementación de la importación de extractos de cuenta camt.053 ISO20022 para el Diario general en la siguiente actualización de Dynamics AX. |
| Módulos afectados             | Todas                                                                                                                                                                                                                                                                                            |

### Formato de pago DTAZV para Alemania
<a id="german-dtazv-payment-format" class="xliff"></a>

|                              |                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | El formato ya no es aplicable en Alemania, ya que se ha sustituido por la funcionalidad SEPA. |
| ¿Reemplazado por otra característica? | Exportación de pagos SEPA                                                                               |
| Módulos afectados             | Todas                                                                                                |

### Importación MT940 alemana
<a id="german-mt940-import" class="xliff"></a>

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Ahora se utiliza la función genérica en lugar de la función localizada.                                                                                                                                                                 |
| ¿Reemplazado por otra característica? | Sí, esta función se ha reemplazado por la funcionalidad avanzada de conciliación bancaria. Además, se prevé la implementación de la importación de extractos de cuenta camt.053 ISO20022 para el Diario general en la siguiente actualización de Dynamics AX. |
| Módulos afectados             | Todas                                                                                                                                                                                                                                   |

### Lista de ventas UE XML para Alemania
<a id="german-xml-eu-sales-list" class="xliff"></a>

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Ya no se admite el formato XML para los informes de Lista de ventas de la UE para Alemania. Solo se puede usar el formato de archivo de texto ELMA5 para enviar el informe de la Lista de ventas de la UE a la delegación de hacienda alemana. |
| ¿Reemplazado por otra característica? | No                                                                                                                                                                                 |
| Módulos afectados             | Impuesto                                                                                                                                                                                |

### Informes GL SSRS
<a id="gl-ssrs-reports" class="xliff"></a>

Se han retirado los informes que incluyen los siguientes elementos de menú: **Resumen de saldo de comprobación**, **Saldo de comprobación detallado**, **Plan contable**, **Traza de auditoría**, **Saldos** y **Lista de saldo**.

|                              |                                                                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Los informes de Financial Microsoft SQL Server Reporting Services (SSRS) han sido reemplazados con capacidades de Management Reporter e informes predeterminados. |
| ¿Reemplazado por otra característica? | Management Reporter (etiquetado **Informes financieros** en la versión actual de Dynamics AX)                                                  |
| Módulos afectados             | Contabilidad general                                                                                                                               |

### Metadatos de InfoPart y FormPart
<a id="infopart-and-formpart-metadata" class="xliff"></a>

|                              |                                                                                                                                                                                                                                |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Los metadatos de InfoPart y de FormPart permitieron la creación de cuadros informativos para dos clientes diferentes.                                                                                                                                    |
| ¿Reemplazado por otra característica? | Los metadatos de InfoPart, que eran una definición simplificada de formulario, se han convertido a un formulario mediante herramientas de actualización. Los metadatos de FormPart, con un formulario al que se hace referencia, se han sustituido por una referencia más directa creada mediante herramientas de actualización. |
| Módulos afectados             | Todas                                                                                                                                                                                                                            |

### Página de lista Cuenta principal
<a id="main-account-list-page" class="xliff"></a>

Una lista de cuentas para la entidad jurídica y la información relacionada de saldo

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | La información del saldo está disponible en la página de lista **Saldo de comprobación** por cuenta y dimensión.                                                                                      |
| ¿Reemplazado por otra característica? | **Cuentas principales** contiene la misma lista de cuentas que contenía la página de lista **Cuenta principal**. La vista de cuadrícula en **Cuentas principales** también muestra una vista más pequeña tipo cuadrícula. |
| Módulos afectados             | Contabilidad general                                                                                                                                                                     |

### Informe de flujo de efectivo bancario de Malasia y Singapur
<a id="malaysia-and-singapore-bank-cash-flow-report" class="xliff"></a>

Esta función permite al usuario imprimir un informe de flujo de efectivo que muestra transacciones y detalles de flujos de entrada y de salida de efectivo para un intervalo específico de fechas para las cuentas bancarias seleccionadas.

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Motivo de la eliminación       | La misma información se puede obtener desde la transacción bancaria de consulta. |
| ¿Reemplazado por otra característica? | La transacción bancaria de consulta                                            |
| Módulos afectados             | Gestión de efectivo y bancos                                                |

### Factura electrónica CFD mexicana
<a id="mexican-cfd-electronic-invoice" class="xliff"></a>

Esta función habilitó la generación de facturas electrónicas mexicanas mediante el método Comprobante Fiscal Digital (CFD), donde la empresa firma la factura solicitando el permiso correspondiente del gobierno. Esta función también proporciona un informe mensual con todas las facturas electrónicas emitidas en el período.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                           |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | El método ya no es aplicable. La generación de facturas electrónicas usando el método CFD ha sido derogada por las autoridades fiscales y se ha sustituido por el Comprobante Fiscal Digital a través de Internet (CFDI), donde la firma se delega al tercer proveedor (PAC). Se ha quitado el informe mensual, y una opción de consulta permite a los usuarios consultar transacciones históricas. |
| ¿Reemplazado por otra característica? | No                                                                                                                                                                                                                                                                                                                                                                                                        |
| Módulos afectados             | Clientes, Proyecto                                                                                                                                                                                                                                                                                                                                                                              |

### IVA realizado y sin realizar en México
<a id="mexico-realized-and-unrealized-vat" class="xliff"></a>

Microsoft Dynamics AX 2012 gestionaba el impuesto sobre el valor añadido (IVA) sin realizar mediante la funcionalidad específica para México de “impuestos sin realizar”.

|                              |                                                                                                                     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Funcionalidad duplicada                                                                                             |
| ¿Reemplazado por otra característica? | Sí, esta funcionalidad se ha reemplazado por la funcionalidad estándar de impuestos condicional proporcionada por Core. |
| Módulos afectados             | Impuesto                                                                                                                 |

### Integración de Microsoft Outlook
<a id="microsoft-outlook-integration" class="xliff"></a>

|                              |                                                                                |
|------------------------------|--------------------------------------------------------------------------------|
| Motivo de la eliminación       | Esta funcionalidad se ha reemplazado por la integración de Microsoft Exchange Server. |
| ¿Reemplazado por otra característica? | Sí                                                                            |
| Módulos afectados             | Ventas y marketing                                                            |

### Información de nómina en Recursos humanos
<a id="payroll-information-in-human-resources" class="xliff"></a>

Información de nómina en Recursos humanos

|                              |                                                                                                                                                                                                                                                                                                                              |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Esta funcionalidad se ha sustituido por páginas principales de nóminas y Recursos Humanos.                                                                                                                                                                                                                                              |
| ¿Reemplazado por otra característica? | Se han reconfigurado las páginas **Prestaciones**, **Ganancias** y otras páginas relacionadas que estaban anteriormente en nóminas de Estados Unidos y ahora forman parte de la configuración de Recursos humanos base para ayudar con el procesamiento externo de nóminas. A esta función se accede mediante la clave de configuración **Recursos humanos 1** &gt; **Nómina**. |
| Módulos afectados             | Recursos humanos, Nómina                                                                                                                                                                                                                                                                                                     |

### Bloqueo privado de los diarios de gestión de almacenes e inventarios
<a id="private-blocking-of-inventory-and-warehouse-management-journals" class="xliff"></a>

Los diarios de almacén e inventario ya no admiten la opción de marcar un diario como privado para un usuario seleccionado. Solo se admite el proceso de bloqueo de diarios como privado para grupos de usuarios y bloqueo durante la edición.

|                              |                                        |
|------------------------------|----------------------------------------|
| Motivo de la eliminación       | No se ha encontrado ningún uso de la función. |
| ¿Reemplazado por otra característica? | No                                     |
| Módulos afectados             | Gestión de inventarios                   |

### Configurador de productos
<a id="product-builder" class="xliff"></a>

El configurador de productos se usaba para configurar dinámicamente artículos desde un pedido de ventas, presupuesto de ventas, pedido de compra, orden de producción, presupuesto de venta, presupuesto del proyecto o petición de artículo. De acuerdo con un modelo de producto que tenía variables de modelo, el usuario podía seleccionar valores para cumplir con los requisitos del cliente y obtener una variante del producto única con una lista de materiales y una ruta.

|                              |                                                                                                                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | El configurador de productos exponía el código X++ a los usuarios finales y no se admite en la versión actual de Dynamics AX. Se ha retirado para evitar esfuerzos duplicados en bases de código superpuestas y cuantiosas. |
| ¿Reemplazado por otra característica? | Configuración del producto                                                                                                                                                                                   |
| Módulos afectados             | Gestión de información de productos, Ventas y marketing                                                                                                                                                     |

### Asignar un nuevo nombre a la dimensión del producto
<a id="rename-product-dimension" class="xliff"></a>

Esta función le permite cambiar el nombre de una de las tres dimensiones de producto estándar (tamaño, color o estilo) a un nombre que cumpla mejor con sus requisitos empresariales. El cambio de nombre incluía todas las etiquetas donde se aislaba el nombre de la dimensión de producto.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| Motivo de la eliminación       | La versión actual de Dynamics AX no admite cambios de etiqueta en tiempo de ejecución. |
| ¿Reemplazado por otra característica? | No                                                                            |
| Módulos afectados             | Gestión de información de productos                                                |

### Conectividad de Retail Server mediante HTTP
<a id="retail-server-connectivity-using-http" class="xliff"></a>

En Dynamics AX 2012 R3, Retail Server podía trabajar usando la comunicación HTTP (sin seguridad). Esto estaba además de la comunicación estándar mediante HTTPS.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| Motivo de la eliminación       | Debido a los nuevos requisitos de seguridad, ahora solo se admite la comunicación segura mediante TLS 1.2 (o un número superior, si está disponible). El instalador de autoservicio configurará automáticamente el equipo para esta comunicación. |
| ¿Reemplazado por otra característica? | N. º Ahora solo se da soporte a la comunicación de HTTPS estándar.                                                                           |
| Módulos afectados             | Retail Server                                                |

### Páginas de áreas de trabajo
<a id="role-center-pages" class="xliff"></a>

|                              |                                                                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Las páginas de área de trabajo se crearon en la plataforma de Enterprise Portal obsoleta, la cual se ha actualizado mediante la nueva plataforma de cliente web en la versión actual de Dynamics AX. |
| ¿Reemplazado por otra característica? | El nuevo patrón del formulario de espacio de trabajo proporciona a los usuarios un diseño centrado en el proceso de fácil acceso a las tareas de uso general dentro de dicho proceso.                       |
| Módulos afectados             | Todas                                                                                                                                                                      |

### Jurisdicciones de impuestos
<a id="sales-tax-jurisdictions" class="xliff"></a>

|                              |                                              |
|------------------------------|----------------------------------------------|
| Motivo de la eliminación       | Poco uso de cliente y conjunto limitado de funciones |
| ¿Reemplazado por otra característica? | No                                           |
| Módulos afectados             | Impuestos de EE.UU                                 |

### Interfaz de transportistas de envío
<a id="shipping-carrier-interface" class="xliff"></a>

|                              |                                                                                                                                                 |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Funcionalidad duplicada                                                                                                                         |
| ¿Reemplazado por otra característica? | Sí, esta característica se ha sustituido parcialmente por Administración de transporte, pero aún no se ha reemplazado por Administración de almacenes básico (WMS I). |
| Módulos afectados             | Ventas y marketing, Gestión de inventarios                                                                                                       |

### Sites Service
<a id="sites-services" class="xliff"></a>

Servicios de sitios le permite crear sitios web que amplía sus procesos empresariales a Internet sin el soporte técnico de TI.

|                              |                                                                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | La infraestructura de Microsoft Azure que se usa por Dynamics AX tiene nuevas capacidades que se pueden usar en su lugar (por ejemplo, sitios de Azure). |
| ¿Reemplazado por otra característica? | No                                                                                                                                       |
| Módulos afectados             | Contratación de RR. HH., gestión de casos, solicitud de presupuestos, registro de proveedor                                                                  |

### Estrategia de previsión de la demanda de SSAS
<a id="ssas-demand-forecasting-strategy" class="xliff"></a>

|                              |                                                                              |
|------------------------------|------------------------------------------------------------------------------|
| Motivo de la eliminación       | El diseño de la característica no se admite en la nueva arquitectura de la nube. |
| ¿Reemplazado por otra característica? | Estrategia de previsión de demanda de Aprendizaje automático de Azure                           |
| Módulos afectados             | Planificada                                                                     |

### Pedidos de viaje
<a id="travel-requisitions" class="xliff"></a>

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Motivo de la eliminación       | Poco uso, y la mayoría de la funcionalidad existían en Enterprise Portal. |
| ¿Reemplazado por otra característica? | No                                                              |
| Módulos afectados             | Gestión de gastos                                              |

### Ver detalles de grupo de facturas de proveedor excluidas del registro
<a id="vendor-invoice-pool-excluding-posting-details" class="xliff"></a>

|                              |                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Poco uso. Esta funcionalidad se ha reemplazado por el Diario de facturas que tiene la funcionalidad del flujo de trabajo. |
| ¿Reemplazado por otra característica? | Capacidades del flujo de trabajo del Diario de facturas.                                                           |
| Módulos afectados             | Proveedores                                                                                        |

### Cuentas de empresa virtuales
<a id="virtual-company-accounts" class="xliff"></a>

La característica de empresas virtuales ya no se admite en Dynamics AX. La característica de empresas virtuales permite a los usuarios configurar tablas que se puedan compartidas por un conjunto de empresas. Puede obtener una descripción de la función, vea [Cuentas de empresa y cuentas de empresa virtuales](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). La función trabaja agrupando tablas en recopilaciones que se asignan a empresas virtuales, que son grupos de empresas “reales” existentes. Se crean consultas de modo que todas las empresas de la empresa virtual puedan obtener acceso a los datos de las tablas de las recopilaciones de tablas asociadas.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Motivo de la eliminación</td>
<td><ul>
<li>Las empresas virtuales deben configurarse antes de que los datos se puedan guardar en las tablas. La retroadaptación de las empresas virtuales en la implementación existente es muy difícil.</li>
<li>Dado que se han normalizado tantos datos en la versión actual de Microsoft Dynamics AX, se ha vuelto difícil saber qué agregar a las colecciones de tablas. Por ejemplo, es difícil saber qué tablas compartir. Todas las tablas a las que se hace referencia desde las tablas en una empresa virtual también se deben agregar. Debido a la normalización de la tabla, incluso los datos maestros sencillos que se extienden en múltiples tablas deben formar parte de la empresa virtual. Cualquier error que se realice producirá problemas funcionales.</li>
<li>Cuando una tabla forma parte de una empresa virtual, pierde la información acerca del origen de los datos, y solo se registra la empresa virtual.</li>
</ul></td>
</tr>
<tr class="even">
<td>¿Reemplazado por otra característica?</td>
<td>Se pueden usar tablas globales para que las tablas sean accesibles desde todas las empresas. Actualmente no hay ninguna sustitución.</td>
</tr>
<tr class="odd">
<td>Módulos afectados</td>
<td>No aplicable</td>
</tr>
</tbody>
</table>

### Gestión de almacenes II
<a id="warehouse-management-ii" class="xliff"></a>

|                              |                                                                                                                                                                                                                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | La solución Gestión de almacenes II (WMS II) que estaba disponible en el módulo **Gestión de inventarios** duplica la funcionalidad en el módulo **Gestión de almacenes** que se lanzó en Microsoft Dynamics AX 2012 R3.                                                                         |
| ¿Reemplazado por otra característica? | El módulo **Administración de almacenes** lanzado en AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8 y Dynamics AX 2012 R3 CU9 reemplaza las funciones de Gestión de almacenes II. El nuevo módulo dispone de características más avanzadas y procesos más flexibles de gestión de almacenes que Gestión de almacenes II. |
| Módulos afectados             | Gestión del inventario, ventas y marketing, adquisición y abastecimiento                                                                                                                                                                                                                                         |

### Recordatorios de trabajador en Recursos humanos
<a id="worker-reminders-in-human-resources" class="xliff"></a>

Información de nómina en Recursos humanos

|                              |                 |
|------------------------------|-----------------|
| Motivo de la eliminación       | Poco uso       |
| ¿Reemplazado por otra característica? | No              |
| Módulos afectados             | Recursos humanos |

### Planificador de trabajo
<a id="workplanner" class="xliff"></a>

|                              |                                                                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Poco uso                                                                                                                                                            |
| ¿Reemplazado por otra característica? | No, pero la página **Relación de perfiles**, que se abre desde la página **Grupos de perfiles**, admite el mismo escenario empresarial que la página **Planificador de trabajo** desaprobada. |
| Módulos afectados             | Tiempo y asistencia                                                                                                                                                  |

### Informes financieros de X++
<a id="x-financial-statements" class="xliff"></a>

|                              |                                                                                             |
|------------------------------|---------------------------------------------------------------------------------------------|
| Motivo de la eliminación       | Esta funcionalidad se ha reemplazado por otra característica.                                    |
| ¿Reemplazado por otra característica? | Management Reporter (etiquetado **Informes financieros** en la versión actual de Dynamics AX) |
| Módulos afectados             | Contabilidad general                                                                              |


