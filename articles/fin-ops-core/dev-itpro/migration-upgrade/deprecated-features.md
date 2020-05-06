---
title: Funciones quitadas u obsoletas de versiones anteriores
description: Este tema describe las características que se eliminaron o que se planearon eliminar de Dynamics 365 for Finance and Operations y versiones anteriores de ese producto.
author: sericks007
manager: AnnBe
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be266f838c5e6cd10655546179e9075e36570bfc
ms.sourcegitcommit: 399f128d90b71bd836a1c8c0c8c257b7f9eeb39a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284023"
---
# <a name="removed-or-deprecated-features-in-previous-releases"></a>Funciones quitadas u obsoletas de versiones anteriores

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Este tema ya no se actualiza. Para ver una lista actual de características que se han eliminado o desaprobado de las aplicaciones de Finance and Operations, busque el contenido **"Funciones eliminadas o en desuso"** relacionado con la aplicación que está utilizando.

Este tema describe las características que se eliminaron o que están en desuso de Dynamics 365 for Finance and Operations y versiones anteriores de ese producto.

- Una función *quitada* dejará de estar disponible en el producto.
- Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación. 

La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.

## <a name="finance-1007-with-platform-update-31"></a>Finance 10.0.7 con Platform update 31

### <a name="chinese-voucher-types-without-account-groups-selection"></a>Tipos de asiento para China sin selección de grupos de cuentas
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Cambiado a la característica con la selección de grupos de cuentas. |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todas |
| **Estado**                         | En desuso: El 1 de diciembre de 2020, planeamos dejar de admitir la configuración de tipos de asiento para China sin selección de grupos de cuentas. Encuentre más detalles sobre el nuevo diseño de la característica en Novedades en 10.0.7 |

## <a name="finance-and-operations-1006-with-platform-update-30"></a>Finance and Operations 10.0.6 con Platform update 30


### <a name="dimensionhashgethashstr-_message"></a>DimensionHash.getHash (str _message)

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Windows va a dejar de usar SHA1, como se documenta en [Aplicación de Windows de certificados SHA1](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx).  |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todas |
| **Estado**                         | Desusado: El 1 de abril de 2020, los desarrolladores deben usar la nueva API. |

### <a name="hashcomputesha1hashstring-message"></a>Hash.ComputeSHA1Hash(string message)

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Windows va a dejar de usar SHA1, como se documenta en [Aplicación de Windows de certificados SHA1](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx).  |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Plataforma |
| **Opción de implementación**              | Todas |
| **Estado**                         | Desusado: El 1 de abril de 2020, los desarrolladores deben usar la nueva API. |


### <a name="formdatetimecontrolsetutcstring"></a>FormDateTimeControl.setUtcString()

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Estamos retirando el método **setUtcString()**, ya que un mejor método de sustitución está disponible. |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Plataforma |
| **Opción de implementación**              | Todas |
| **Estado**                         | En desuso: El 1 de octubre de 2020, planificamos no admitir más el método **setUtcString()**. Los programadores deben usar el método **setUtcDateTime()** en su lugar. |

### <a name="blacklist-report-it--feature-reference-it-00001"></a>Informe de la lista negra (TI) - Referencia de funcionalidad IT-00001

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Legalmente no requerido. |
| **¿Reemplazado por otra característica?**   | No |
| **Áreas de producto afectadas**         | Localización italiana |
| **Opción de implementación**              | Todas |
| **Estado**                         | Desusado: El 1 de octubre de 2020, planificamos dejar de admitir el **Informe de la lista negra (TI) - Referencia de funcionalidad IT-00001**. |

### <a name="domestic-tax-report--feature-reference-it-00003"></a>Informe de impuestos nacional – Referencia de funcionalidad IT-00003

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Legalmente no requerido. |
| **¿Reemplazado por otra característica?**   | No |
| **Áreas de producto afectadas**         | Localización italiana |
| **Opción de implementación**              | Todas |
| **Estado**                         | Desusado: El 1 de octubre de 2020, planificamos dejar de admitir el **Informe sobre impuestos nacionales - Referencia de funcionalidad IT-00003**. |


## <a name="finance-and-operations-1005-with-platform-update-29"></a>Finance and Operations 10.0.5 con Platform update 29

### <a name="us-payroll-tax-updates"></a>Actualizaciones de impuestos de nómina en Estados Unidos.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Vamos a retirar la funcionalidad de actualizaciones de impuestos para nóminas de Estados Unidos porque se usa poco y porque ahora se ofrece funcionalidad mejorada mediante integraciones estratégicas.  |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Nómina |
| **Opción de implementación**              | Todas |
| **Estado**                         | En desuso: a partir del 1 de octubre de 2021 dejaremos de proporcionar actualizaciones de impuestos a los clientes de la característica Nómina de EE. UU. La funcionalidad se mantendrá en el producto, pero se dejarán de incluir mejoras para mantener la funcionalidad actualizada y los defectos del producto se evaluarán caso a caso. Para obtener más información, consulte [Actualizaciones de impuestos retiradas de la característica Nómina de EE. UU. en Microsoft Dynamics 365 for Finance and Operations](https://aka.ms/financepayrollfaq). |


### <a name="data-management-staging-clean-up"></a>Limpieza del almacenamiento provisional de administración de datos
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | No cumple los requisitos básicos necesarios para programar la limpieza periódica. |
| **¿Reemplazado por otra característica?**   | Sí, la característica de limpieza del historial de trabajos se agrega para afrontar las situaciones de forma integral. |
| **Áreas de producto afectadas**         | Administración de datos |
| **Opción de implementación**              | Todas  |
| **Estado**                         | En desuso: la fecha prevista para la eliminación de la funcionalidad es diciembre de 2020. |

## <a name="finance-and-operations-1004-with-platform-update-28"></a>Finance and Operations 10.0.4 con Platform update 28

### <a name="france-fec-accounting-data-export-in-xml"></a>Francia: Formato XML de exportación de datos contables FEC

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Reemplazado por el formato de TXT,  **Archivo de auditoría francés de FEC** está disponible en **Contabilidad general** \> **Tareas periódicas** \> **Exportación de datos**.
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Contabilidad general |
| **Opción de implementación**              | Todas |
| **Estado**                         | En desuso. La fecha prevista para la eliminación de la funcionalidad es julio de 2020. |


### <a name="legacy-navigation-bar"></a>Barra de navegación antigua

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Alineación de cabecera con otros productos de Dynamics y de Office. Para más información, consulte [Barra de exploración que se alinea con el encabezado de Office](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-finance-operations/updatednavbar).
| **¿Reemplazado por otra característica?**   | A partir de la Platform update 24 se introdujo una barra de navegación rediseñada que cuenta con búsqueda. |
| **Áreas de producto afectadas**         | Cliente web |
| **Opción de implementación**              | Todas |
| **Estado**                         | En desuso: a partir de abril de 2020, la antigua barra de navegación ya no estará disponible. Hasta que ese punto, los clientes puede volver a la antigua barra de navegación a través de la página **Opciones de rendimiento del cliente**. |


## <a name="finance-and-operations-1002-with-platform-update-26"></a>Finance and Operations 10.0.2 con Platform update 26


### <a name="legacy-default-action-behavior"></a>Comportamiento predeterminado de la acción de herencia

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El comportamiento heredado de las acciones predeterminadas de las cuadrículas resulta en una columna inesperada que tiene el vínculo predeterminado de la acción después de que las columnas de la cuadrícula se hayan reordenado a través de la personalización. La nueva función acción adhesiva predeterminada corrige esto. Para más información, consulte [Acciones adhesivas predeterminadas en cuadrículas](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/sticky-default-action). |
| **¿Reemplazado por otra característica?**   | A partir de Platform update 21 se añadió una función para "acciones adhesivas predeterminadas". Esta función se puede habilitar en la página **Opciones de rendimiento del cliente**. |
| **Áreas de producto afectadas**         | Cuadrículas en el cliente web |
| **Opción de implementación**              | Todas |
| **Estado**                         | Desusado: a partir en abril de 2020, las acciones predeterminados adhesivas serán el comportamiento predeterminado, sin un mecanismo para volver al antiguo comportamiento. |

### <a name="legacy-is-one-of-filtering-experience"></a>Heredado es una experiencia de filtrado "es uno de"

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La experiencia de filtrado "es uno de" se ha rediseñado en la Platform update 22, y se planea que acabe siendo la única experiencia de filtrado "es uno de". |
| **¿Reemplazado por otra característica?**   | A partir de la Platform update 22 tiene disponible una experiencia filtrado mejorada "es uno de" en la página **Opciones de rendimiento del cliente**. Para más información, consulte [Optimizado es una experiencia de filtrado es uno de](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering). |
| **Áreas de producto afectadas**         | Cliente web |
| **Opción de implementación**              | Todas |
| **Estado**                         | Desusado: a partir de abril de 2020, la experiencia mejorada "es uno de" será el comportamiento predeterminado, sin un mecanismo para volver al antiguo comportamiento. |

### <a name="parameter-to-enable-sales-orders-with-multiple-project-contract-funding-sources"></a>Parámetro para habilitar los pedidos de ventas con varias fuentes de financiación del contrato de proyecto
La compatibilidad para crear los pedidos de ventas basados en proyectos donde el contrato de proyecto tiene varias fuentes de financiación se habilita con la configuración **Parámetros de la gestión de proyectos** **Permitir pedidos de ventas del proyecto con varias fuentes de financiación**. De forma predeterminada, este parámetro no está habilitado. 

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La funcionalidad siempre será habilitada después de que se elimine el parámetro. |
| **¿Reemplazado por otra característica?**   | N. º La funcionalidad para admitir pedidos de ventas basados en proyectos con varias fuentes de financiación siempre estará habilitada.   |
| **Áreas de producto afectadas**         |El parámetro **Permitir pedidos de ventas para proyectos con varias fuentes de financiación** se eliminará. Los métodos siguientes estarán modificados cuando se quita el parámetro: el método **ctrlSalesOrderTable** en la clase **ProjStatusType**, el método **validar** para el campo **ProjId** y el método **ejecución** en el formulario **SalescreateOrder**. Los siguientes métodos se dejarán de usar cuando se quita el parámetro: **IsSalesOrderAllowedForMultipleFundingSources** en archivo de tabla **ProjTable**, el método **IsAllowSalesOrdersForMultipleFundingSourcesParamEnabled** en el archivo de tabla **ProjTable**, el campo de datos **AllowSalesOrdersForMultipleFundingSources** en el formulario **ProjParameters** y los archivos **ProjParameterEntity**, el método privado **IsAssociatedToMultipleFundingSourcesContract** en el archivo de tabla **ProjTable**. |
| **Opción de implementación**              | Todas  |
| **Estado**                         | La deprecación se planifica para la oleada liberada en abril de 2020. |

### <a name="legacy-workflow-reports-for-tracking-and-instance-status"></a>Informes de flujo de trabajo antiguos el estado y seguimiento de la instancia

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los antiguos informes del flujo de trabajo para el estado y seguimiento de la instancia se están dejando de utilizar porque ya no se referencian desde la navegación. Los nombres de informe son WorkflowWorkflowInstanceByStatusReport y WorkflowWorkflowTrackingReport. |
| **¿Reemplazado por otra característica?**   | El formulario Historial del flujo de trabajo se puede usar en su lugar. |
| **Áreas de producto afectadas**         | Cliente web |
| **Opción de implementación**              | Todas |
| **Estado**                         | En desuso: La fecha prevista para la eliminación de la funcionalidad es abril de 2020. |

## <a name="finance-and-operations-1001-with-platform-update-25"></a>Finance and Operations 10.0.1 con Platform update 25

### <a name="deprecated-apis-and-potential-breaking-changes"></a>API en desuso y potencial cambios que generan interrupciones


#### <a name="deriving-from-internal-classes-is-deprecated"></a>La derivación de clases internas se deja de utilizar

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | En las versiones anteriores a la Platform update 25, era posible crear una clase o tabla derivada de una clase o una tabla interna que está definida en otro paquete/módulo. No es una práctica segura de codificación. A partir de la Platform update 25, el compilador mostrará una advertencia. |
| **¿Reemplazado por otra característica?**   | La advertencia del compilador se reemplazará por un error en la Platform update 26. Este cambio es compatible con versiones anteriores en el tiempo de ejecución, lo que significa que si ejecuta la Platform update 25 o posterior, esto se puede implementar en cualquier espacio aislado o entorno de producción sin la necesidad de modificar código personalizado. Este cambio afecta únicamente al desarrollo y el tiempo de compilación.|
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todas |
| **Estado**                         | En desuso: la advertencia se convertirá en un error de compilación en la Platform update 26. |

#### <a name="overriding-internal-methods-is-deprecated"></a>La anulación de métodos internos se deja de utilizar

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Antes de la Platform update 25, era posible anular un método interno en una clase derivada que está definida en otro paquete/módulo. No es una práctica segura de codificación. A partir de la Platform update 25, el compilador mostrará una advertencia. |
| **¿Reemplazado por otra característica?**   | Esta advertencia del compilador se reemplazará por un error de compilación en la Platform update 26. Este cambio es compatible con versiones anteriores en el tiempo de ejecución, lo que significa que si ejecuta la Platform update 25 o posterior, esto se puede implementar en cualquier espacio aislado o entorno de producción sin la necesidad de modificar código personalizado. Este cambio afecta únicamente al desarrollo y el tiempo de compilación. |
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todas |
| **Estado**                         | En desuso: la advertencia se convertirá en un error de compilación en la Platform update 26. |

## <a name="finance-and-operations-1000-with-platform-update-24"></a>Finance and Operations 10.0.0 con Platform update 24

### <a name="renaming-released-products"></a>Cambiar el nombre de los productos emitidos 
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Al usar la función **Cambiar el nombre de clave principal** para cambiar el ItemId de un producto emitido, solo se actualizan las referencias directas de clave extranjera. Cualquier otra referencia para el producto emitido, por ejemplo, de pedidos de producción, se conservará el ItemId antiguo. Como resultado, podría haber datos incoherentes que podrían bloquear procesos empresariales. |
| **¿Reemplazado por otra característica?**   | N. º |
| **Áreas de producto afectadas**         | Gestión de información de productos |
| **Opción de implementación**              | Todos  |
| **Estado**                         | Eliminado desde Finance and Operations 10.0.0 con Platform update 24.|


## <a name="finance-and-operations-813-with-platform-update-23"></a>Finance and Operations 8.1.3 con Platform update 23

### <a name="sql-server-reporting-services-reportviewer-control"></a>Control ReportViewer de SQL Server Reporting Services
Los clientes pueden utilizar la acción **Exportar** proporcionada por el control incrustado SQL Server Reporting Services (SSRS) ReportViewer para descargar documentos producidos por las aplicaciones de Finance and Operations. Esta presentación basada en HTML del informe proporciona a los usuarios una vista previa no paginada del documento.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La naturaleza no paginada de la experiencia de vista previa basada en HTML **no** presta fidelidad a los documentos físicos elaborados en última instancia por Finance and Operations. Al abrazar completamente PDF como el formato estándar para documentos empresariales, los usuarios pueden aprovechar una experiencia moderna de visualización con rendimiento mejorado al generar informes de aplicación. |
| **¿Reemplazado por otra característica?**   | En adelante, los documentos de PDF serán el formato predeterminado para los informes generados por Finance and Operations.   |
| **Áreas de producto afectadas**         | Este cambio **no** repercute en los escenarios de cliente donde los informes se distribuyen electrónicamente o se envían directamente a impresoras.    |
| **Opción de implementación**              | Todas  |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. La funcionalidad de vista previa automática de informes de aplicaciones usando un visor de PDF incrustado se prevé para la Platform update de mayo de 2019. |

### <a name="client-kpi-controls"></a>Controles de KPI del cliente
Los indicadores de rendimiento clave incrustados (KPIs) podrían ser modelados en Visual Studio por un programador y personalizados aún más por el usuario final.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los controles de clientes nativos utilizados para definir los KPI tienen una respuesta del cliente baja y se basan en un desarrollador para agregar medidas rastreables. |
| **¿Reemplazado por otra característica?**   | El servicio de PowerBI.com proporciona herramientas de calidad mundial para definir y administrar KPI basados en datos de fuentes externas.  En una próxima versión, planeamos habilitar soluciones integradas alojadas en PowerBI.com en espacios de trabajo de aplicaciones.   |
| **Áreas de producto afectadas**         | Esta actualización impedirá que los programadores introduzcan nuevos controles de KPI en el diseñador de Visual Studio.    |
| **Opción de implementación**              | Todas  |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="deprecated-apis-and-future-breaking-changes"></a>API en desuso y futuros cambios que generan interrupciones

#### <a name="field-groups-containing-invalid-field-references"></a>Grupos de campos que contienen referencias de campo no válidas

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Es posible que las definiciones de metadatos de la tabla tengan grupos de campos que contienen referencias no válidas del campo. Si se implementa, esto puede provocar errores del tiempo de ejecución en Financial Reporting y SQL Server Reporting Services (SSRS). Este problema se categoriza actualmente como *advertencia del compilador* en lugar de *error*, lo que significa que la creación y la implementación de paquete desplegable puede continuar sin corregirse el problema. Para solucionar este problema:<br><br>1. Quite la referencia de campo no válida de la definición del grupo de campos de tabla.<br><br>2. Vuelva a compilar.<br><br>3. Asegúrese de que las advertencias o los errores se abordan. |
| **¿Reemplazado por otra característica?**   | Esta advertencia se reemplazará por un error de compilación en el futuro. |
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todos |
| **Estado**                         | Obsoleto: la advertencia es un error en tiempo de compilación con actualizaciones de plataforma para la versión 10.0.11 de aplicaciones de Finance and Operations. |

#### <a name="complete-list"></a>Lista completa
Para obtener acceso a la lista completa de API que se están dejando de utilizar, consulte [Deprecación de métodos y elementos de metadatos](deprecation-deletion-apis.md).

## <a name="finance-and-operations-81-with-platform-update-20"></a>Finance and Operations 8.1 con Platform update 20

### <a name="batch-transfer-rules-for-subledger-journal-account-entries"></a>Reglas de transferencia por lotes para los asientos contables del subdiario contable
El modo de transferencia sincrónico se está abandonando en los parámetros de contabilidad general.  Este modo se sustituye solo por el lote asincrónico y programado, que ya existe como opciones para la transferencia. Para obtener información adicional, consulte el blog [Parámetros de Contabilidad general – reglas de transferencia por lotes](https://community.dynamics.com/365/financeandoperations/b/financials/archive/2019/03/15/general-ledger-parameters-batch-transfer-rules).

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Estamos quitando la opción síncrona debido al impacto del rendimiento en el sistema. |
| **¿Reemplazado por otra característica?**   | El lote programado y el lote asincrónico son opciones que se utilizan en lugar de sincrónico.   |
| **Áreas de producto afectadas**         | Contabilidad general, proveedores, clientes, compra, gasto    |
| **Opción de implementación**              | Todas  |
| **Estado**                         | En desuso: La fecha prevista para la eliminación de la funcionalidad es la versión 10.0.|

### <a name="electronic-reporting-for-russia"></a>Informes electrónicos para Rusia
Característica para configurar formatos de archivo .txt y .xml de declaraciones. 

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Se reemplaza por informes electrónicos. |
| **¿Reemplazado por otra característica?**   | Sí. |
| **Áreas de producto afectadas**         | Libro mayor general |
| **Opción de implementación**              | Todos |
| **Estado**                         | Eliminado desde Finance and Operations 8.1 con Platform update 20. |

### <a name="financial-reports-generator-for-russia"></a>Generador de informes financieros para Rusia
Una herramienta para configurar recopilaciones de datos para los informes de contabilidad e impuestos y para exportar datos a plantillas de informes DOC y XLS. Partes funcionales: se eliminan la exportación de datos a plantillas de informes de XLS y de DOC, consultas, y requisitos fijos. 

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Las partes quitadas se reemplazan con los informes electrónicos. |
| **¿Reemplazado por otra característica?**   | Sí. La interfaz de usuario de configuración de informes financieros se debe usar para configurar reglas de recopilación de datos según cuentas de contabilidad general o registros de impuestos. La exportación de datos a distintos tipos de archivo, los requisitos y las consultas fijos, como las reglas de recopilación de datos, se deben configurar en el informe electrónico. |
| **Áreas de producto afectadas**         | Contabilidad general |
| **Opción de implementación**              | Todos |
| **Estado**                         | Eliminado desde Finance and Operations 8.1 con Platform update 20. |

### <a name="integration-with-external-providers-for-sending-electronic-reporting-through-communication-channels-for-russia"></a>Integración con los proveedores externos para enviar notificaciones electrónicas a través de los canales de comunicación para Rusia
Característica que exporta archivos electrónicos generados de declaraciones a la carpeta para el envío adicional a los proveedores oficiales de informes electrónicos así como su importación.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Reemplazada con la función configurable de los mensajes electrónicos. |
| **¿Reemplazado por otra característica?**   | Sí.  |
| **Áreas de producto afectadas**         | Contabilidad general, impuestos |
| **Opción de implementación**              | Todos |
| **Estado**                         | Eliminado desde Finance and Operations 8.1 con Platform update 20. |


### <a name="profit-tax-register-wizard"></a>Asistente del registro de impuesto de ganancias
Característica para crear plantillas para nuevos registros de impuestos sobre ganancias. Esta característica crea objetos X++ para nuevos registros, que se crean como plantillas con la lógica de cálculo apropiada agregada.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La característica no es compatible con el modelo de extensibilidad de Finance and Operations. |
| **¿Reemplazado por otra característica?**   | Nº |
| **Áreas de producto afectadas**         | Impuestos |
| **Opción de implementación**              | Todos |
| **Estado**                         | Eliminado desde Finance and Operations 8.1 con Platform update 20. |


## <a name="finance-and-operations-80-with-platform-update-15"></a>Finance and Operations 8.0 con Platform update 15
No se ha quitado ni se ha dejado de utilizar ninguna función con esta versión. La actualización de la plataforma 15 es acumulativa y contiene nuevas o mejoradas funciones de la actualización de la plataforma 13, la actualización de la plataforma 14 y la actualización de la plataforma 15.

## <a name="finance-and-operations-enterprise-edition-73-with-platform-update-12"></a>Finance and Operations, Enterprise edition 7.3 con Platform update 12

### <a name="personalized-product-recommendations"></a>Recomendaciones de productos personalizados 
A partir del 15 de febrero de 2018, los minoristas no podrán mostrar recomendaciones personalizadas de productos en un dispositivo de punto de venta (PDV). Para obtener más información, consulte [Visión general de las recomendaciones de producto](../../../commerce/product-recommendations.md).  

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Estamos retirando la versión actual del servicio de recomendación de productos ya que rediseñamos esta función con un algoritmo mejor y capacidades más nuevas orientadas a la venta minorista.  |
| **¿Reemplazado por otra característica?**   | N. º Sin embargo, después de la primavera de 2018, tenemos previsto volver a traer esta función para utilizar un nuevo servicio de recomendación.   |
| **Áreas de producto afectadas**         | Recomendaciones de productos personalizados en PDV.                                                    |
| **Opción de implementación**              | Todas                                                                                      |
| **Estado**                         |Se quitó el 15 de febrero de 2018. Esto afecta a los clientes que ejecutan Dynamics 365 for Operations 1611 y posteriores.  |

### <a name="extension-of-the-list-of-electronic-reporting-er-functions"></a>Ampliación de la lista de funciones de Informes electrónicos (ER)
La posibilidad de especificar las funciones personalizadas que se utilizarán en el generador de expresiones de ER (para obtener más información, consulte [Extiende la lista de funciones electrónicas de informes (ER)](../../dev-itpro/analytics/general-electronic-reporting-formulas-list-extension.md)) no se admite más. Debido a los cambios de ER API, API para llamar funciones integradas del generador de expresiones de ER se han hecho interno y ya no se puede extender.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Iniciativa de sellado de códigos  |
| **¿Reemplazado por otra característica?**   | Ninguno. Siempre que se necesite una nueva función integrada, se debe dirigir una nueva solicitud de extensión al equipo del marco de ER.<br><br>Como solución temporal mientras que la función solicitada está en proceso de desarrollo por equipo de ER, se puede programar la lógica necesaria como método de clase de aplicación personalizada. A este método se puede acceder en una expresión del ER como una propiedad del origen de datos agregado del ER del tipo de **Aplicación\clase** que hace referencia a esa clase de aplicación personalizada.  |
| **Áreas de producto afectadas**         | Parámetros de informes de marco                                                      |
| **Opción de implementación**              | Todas                                                                                      |
| **Estado**                         | Eliminado desde Finance and Operations, Enterprise edition 7.3.    |

### <a name="inventory-by-item-group-and-inventory-by-inventory-dimension-aging-reports"></a>Inventario por grupo de artículos e inventario por informes de antigüedad de dimensión de inventario

Estos dos informes ya no se admiten en Finance and Operations. En su lugar, el informe de **antigüedad de inventario** se puede usar para mejorar la experiencia del usuario.

|   |  |
|--------------|-----------------------|
| **Motivo de la eliminación**       | Funcionalidad duplicada  |
| **¿Reemplazado por otra característica?** | Sí. Los dos informes han sido reemplazados por el informe **Antigüedad de inventario**.     |
| **Áreas de producto afectadas**       | Gestión del inventario, administración de costes        |
| **Opción de implementación**        | Todas|
| **Estado**                       | En desuso: Los elementos de menú para los dos informes se han quitado en la versión 7.3. Sin embargo, el código para los informes permanece en el producto. El plan es quitar el código en una versión futura. |

### <a name="power-bi-content-packs-available-on-appsource"></a>Paquetes de contenido Power BI disponibles en AppSource
Los paquetes de contenido **Administración de costes**, **Rendimiento financiero** y **Retail Channel Performance**, disponibles en el sitio [Microsoft AppSource](https://appsource.microsoft.com) están en desuso como consecuencia de actualizaciones de producto en Microsoft Power BI. Los formularios de administración del sistema utilizados para implementar estos paquetes de contenido a PowerBI.com también se están a dejar de utilizar en Finance and Operations.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Actualizaciones de producto en Microsoft Power BI. |
| **¿Reemplazado por otra característica?**   | Los paquetes de contenido **Gestión de costes**, **Rendimiento financiero** y **Retail Channel Performance**, disponibles en el sitio [AppSource](https://appsource.microsoft.com), se van a sustituir por las aplicaciones analíticas que permiten integraciones de la solución en el nivel de la base de datos. Para obtener más información acerca de aplicaciones analíticas, consulte [Power BI incrustado en espacios de trabajo](../../dev-itpro/analytics/embed-power-bi-workspaces.md).    |
| **Áreas de producto afectadas**         | Administración de costes, Finanzas, y Retail                                                                                               |
| **Opción de implementación**              | Solo en la nube (la integración con PowerBI.com no se admite en implementaciones locales).                                                                                                            |
| **Estado**                         | En desuso: La fecha prevista para la eliminación de la funcionalidad es el segundo trimestre de 2018.    |

### <a name="standard-ui-in-data-management-workspace"></a>Interfaz de usuario estándar en área de trabajo de gestión de datos

La interfaz de usuario estándar en administración de datos es la antigua interfaz de usuario, que es la interfaz de usuario predeterminada que se muestra a los usuarios cuando visitan el espacio de trabajo de gestión de datos.

|   |  |
|------------------|-------------------------|
| **Motivo de la depreciación/eliminación** | Estamos invirtiendo en suministrar nuevas experiencias de usuario en la nueva interfaz de usuario.             |
| **¿Reemplazado por otra característica?**   | La nueva interfaz de usuario denominada *Vistas mejoradas* está reemplazando la interfaz de usuario antigua.            |
| **Áreas de producto afectadas**         | Espacio de trabajo para la gestión de datos                                                     |
| **Opción de implementación**              | Todas                                                                           |
| **Estado**                         | En desuso: La fecha prevista para la eliminación de la funcionalidad es el segundo trimestre de 2018. |

### <a name="excise-sales-tax-service-tax-for-india"></a>Impuestos especiales, impuestos sobre ventas, impuesto de servicios de la India

Estos impuestos se han incluido en el GST indio.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo de la eliminación o depreciación**       | Estos impuestos se han incluido en el GST indio.                          |
| **¿Reemplazado por otra característica?**            | GST indio                                                              |
| **Áreas de producto afectadas**                  | Impuesto                                                                     |
| **Opción de implementación**                       | Todos los módulos                                                   |
| **Estado**                                  | En desuso: No se ha establecido una fecha de eliminación para esta función. |    

### <a name="file-validation-utility-fvu-for-india"></a>File Validation Utility (FVU) para la India

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo de la eliminación o depreciación**       | Falta de uso del cliente                                                  |
| **¿Reemplazado por otra característica?**            | N.º                                                                      |
| **Áreas de producto afectadas**                  | Retención de impuestos de la India                                                  |
| **Opción de implementación**                       | Todos los módulos                                                                    |
| **Estado**                                  | En desuso: No se ha establecido una fecha de eliminación para esta función.   |        

### <a name="tdstcs-certificate-for-india"></a>Certificado de TDS/TCS para la India

Los usuarios pueden descargar esto del portal gubernamental.

|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo de la eliminación o depreciación**       | Falta de uso del cliente                                                  |
| **¿Reemplazado por otra característica?**            | N.º                                                                      |
| **Áreas de producto afectadas**                  | Retención de impuestos de la India                                                  |
| **Opción de implementación**                       | Todos los módulos                                                                   |
| **Estado**                                  | En desuso: No se ha establecido una fecha de eliminación para esta función.     |    

### <a name="exportimport-exim-incentive-scheme-for-india"></a>Esquema de incentivo de exportación/importación (EXIM) para la India


|                                             |                                                                         |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo de la eliminación o depreciación**       | Falta de uso del cliente                                                  |
| **¿Reemplazado por otra característica?**            | N.º                                                                      |
| **Áreas de producto afectadas**                  | Importar y exportar                                                       |
| **Opción de implementación**                       | Todos los módulos                                                                    |
| **Estado**                                  | En desuso: No se ha establecido una fecha de eliminación para esta función.  |    


## <a name="dynamics-365-for-retail-72"></a>Dynamics 365 for Retail 7.2

### <a name="personalized-product-recommendations"></a>Recomendaciones de productos personalizados 
A partir del 15 de febrero de 2018, los minoristas no podrán mostrar recomendaciones personalizadas de productos en un dispositivo de punto de venta (PDV). Para obtener más información, consulte [Visión general de las recomendaciones de producto](../../../commerce/product-recommendations.md).  

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Estamos retirando la versión actual del servicio de recomendación de productos ya que rediseñamos esta función con un algoritmo mejor y capacidades más nuevas orientadas a la venta minorista.  |
| **¿Reemplazado por otra característica?**   | N. º Sin embargo, después de la primavera de 2018, tenemos previsto volver a traer esta función para utilizar un nuevo servicio de recomendación.   |
| **Áreas de producto afectadas**         | Recomendaciones de productos personalizados en PDV.                                                    |
| **Opción de implementación**              | Todas                                                                                      |
| **Estado**                         |Se quitó el 15 de febrero de 2018. Esto afecta a los clientes que ejecutan Dynamics 365 for Retail 7.2 y posteriores. |


## <a name="finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Finance and Operations, Enterprise edition Julio 2017 con Platform update 8

### <a name="currency-conversion-for-accounting-and-reporting-currencies"></a>Conversión de divisa para contabilidad y divisas de notificación

La conversión de divisas para contabilidad y divisas de notificación se introdujo cuando se introdujo el euro.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Uso y adición limitados de la funcionalidad Copiar entidad jurídica como sustitución.      |
| **¿Reemplazado por otra característica?**   | No, pero las funciones Copiar entidad jurídica y Configuraciones se agregaron para facilitar el cambio a una empresa que tiene requisitos básicos cambiantes. |
| **Áreas de producto afectadas**         | Administración financiera     |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.   |


### <a name="warehouse-mobile-devices-portal"></a>Portal de dispositivos móviles de almacén

El portal de dispositivos móviles de almacén (WMDP) era componente independiente pensando para la implementación propia localmente. Este componente ya no es compatible con Finance and Operations. Una aplicación nativa que mejora la experiencia del usuario ha sustituido a la funcionalidad de WMDP.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Funcionalidad duplicada.       |
| **¿Reemplazado por otra característica?**   | Sí. Esta característica se ha reemplazado por Finance and Operations - Warehousing. Para obtener más información sobre la configuración y prerrequisitos, consulte [Información general de instalar y configurar la aplicación de almacenaje](../../../supply-chain/warehousing/install-configure-warehousing-app.md). |
| **Áreas de producto afectadas**         | Gestión de almacenes y administración de transporte     |
| **Opción de implementación**              | El portal de dispositivos móviles de almacén (WMDP) era componente independiente pensando para la implementación propia localmente.               |
| **Estado**                         | En desuso: La fecha prevista para la eliminación de la funcionalidad es el cuarto trimestre de 2019.   |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Regla de correspondencia de conciliación bancaria para coincidencia manual

Una regla de coincidencia se utilizó para seleccionar y marcar un documento bancario cuando los documentos se conciliaron manualmente en la hoja de cálculo de conciliación.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Uso limitado.                                                                         |
| **¿Reemplazado por otra característica?**   | N. º Las capacidades de filtro de columnas se deben usar para buscar los documentos de la conciliación. |
| **Áreas de producto afectadas**         | Gestión de efectivo y bancos                                                               |
| **Opción de implementación**              | Todas                                                                                    |
| **Estado**                         | Se quitó en julio 2017.                                                               |

## <a name="dynamics-365-for-operations-1611-with-platform-update-3"></a>Dynamics 365 for Operations 1611 con Platform update 3

### <a name="aeb-payment-formats-for-spain"></a>Formatos de pago de AEB para España

Los formatos de pago del Consejo Superior Bancario se usaron para enviar archivos de remesas al banco de los pagos de clientes y proveedores. El contenido de estos formatos lo determinaba la Asociación Española de Banca. Cubre Cuadernos 19, 32, 58, 34.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los formatos de pago ya no se usan.                                  |
| **¿Reemplazado por otra característica?**   | Sí, transferencia de crédito ISO20022 y formatos de pago de domiciliación bancaria para España |
| **Áreas de producto afectadas**         | Cuentas de proveedores, cuentas de clientes                                    |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.           |

### <a name="bank-payments-transfer-for-lithuania"></a>Transferencia de pagos bancarios para Lituania

Las transferencias de los pagos bancarios se generaban e imprimían mediante el formato de exportación de transferencia de pagos para Lituania (LT). El mercado lituano empezó a usar LITAS, el sistema unificado de banca electrónica, en 2005.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los formatos de pago ya no se usan.                        |
| **¿Reemplazado por otra característica?**   | Sí, formato de pago de transferencia de crédito ISO20022 para Lituania     |
| **Áreas de producto afectadas**         | Proveedores                                               |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>Formatos de pago de BBS Direkte Remittering para Noruega

Los formatos de pago de BBS Direkte Remittering incluyen la exportación del cobro de pago de cliente (domiciliación bancaria) y la importación de la devolución del mensaje.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los formatos de pago ya no se usan.  |
| **¿Reemplazado por otra característica?**   | El formato de pago de un cliente de AvtaleGiro para Noruega se puede usar para generar los mensajes de domiciliación bancaria. La importación de la devolución del mensaje será implementada en próximas versiones. |
| **Áreas de producto afectadas**         | Cuentas de proveedores, cuentas de clientes   |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.                                                                                                 |

### <a name="chart-of-accounts-tool-for-spain"></a>Herramienta para el plan de cuentas para España

Se utiliza esta herramienta cuando un plan de cuentas en España requiere cambios importantes. Los usuarios pueden importar un nuevo plan de cuentas en Microsoft Excel o en formato de texto, y también pueden importar los informes financieros.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Uso limitado                                                  |
| **¿Reemplazado por otra característica?**   | N.º                                                             |
| **Áreas de producto afectadas**         | Contabilidad general                                                 |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="dom80-payment-format-for-belgium"></a>Formato de pago Dom80 para Bélgica

Formato de pago Legacy Belga para cobro de pago (domiciliación bancaria).

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El formato de pago ya no se usa.                          |
| **¿Reemplazado por otra característica?**   | Sí, formato de pago de domiciliación bancaria ISO 20022 para Bélgica.         |
| **Áreas de producto afectadas**         | Clientes                                            |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="dtaezag-payment-formats-for-switzerland"></a>Formatos de pago DTA/EZAG para Suiza

Los formatos DTA/EZAG se integran en el sistema ESR, ya que pueden contener un número de referencia. Puesto que el número de referencia no es obligatorio, los formatos se pueden usar para procesar los pagos de cualquier proveedor. Estos formatos los usan las empresas con una cuenta bancaria en una ubicación diferente de “Postfinance.”

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los formatos de pago ya no se usan.                        |
| **¿Reemplazado por otra característica?**   | Sí, formato de pago de transferencia de crédito ISO20022 para Suiza   |
| **Áreas de producto afectadas**         | Proveedores                                               |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>Formato de pago de EDIFACT-DIRDEB para Austria

Formato de pago de EDIFACT-DIRDEB para cobro de pago (domiciliación bancaria).

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El formato de pago ya no se usa.                          |
| **¿Reemplazado por otra característica?**   | Sí, formato de pago de domiciliación bancaria ISO 20022 para Austria         |
| **Áreas de producto afectadas**         | Clientes                                            |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="edivat-for-belgium"></a>EDIVAT para Bélgica

EDIVAT es una norma belga obsoleta para la declaración electrónica a través de correo seguro. Dynamics AX 2012 conserva la opción de sólo lectura para habilitar el acceso a los datos históricos.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La función ya no se usa.                           |
| **¿Reemplazado por otra característica?**   | N.º                                                             |
| **Áreas de producto afectadas**         | Contabilidad general                                                 |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>Formato de importación de pago de eGiro EDIFACT CREMUL para Noruega

eGiro se basa en la norma internacional UN EDIFACT CREMUL (Mensaje de aviso de crédito múltiple), que se usa para el registro automático de pagos del cliente. En Dynamics AX, eGiro se implementa como formato de importación de pago de cliente.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El formato de pago ya no se usa.                                                     |
| **¿Reemplazado por otra característica?**   | N. º El formato se sustituirá por formatos ISO 20022 de importación de criterio en próximas versiones. |
| **Áreas de producto afectadas**         | Clientes                                                                       |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.                            |

### <a name="external-inventory-for-poland"></a>Inventario externo para Polonia

Pruebas de mercancías que se toman de un proveedor para las venta sin compra. Las mercancías que son gestionadas en un inventario externo no afectan al inventario estándar y se pueden vender y después comprar automáticamente. Este proceso crea los movimientos de inventario reales.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Reemplazado por otra característica                                    |
| **¿Reemplazado por otra característica?**   | Sí, la funcionalidad básica de entrada de envío                |
| **Áreas de producto afectadas**         | Cuentas de proveedores, gestión de inventario                         |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="financial-reports-generator-for-eastern-europe"></a>Generador de informes financieros para Europa Oriental

Se utiliza una herramienta para configurar la recopilación de datos para los informes de contabilidad e impuestos, y para exportar datos a plantillas de informes XLS y DOC.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Uso limitado                                                                            |
| **¿Reemplazado por otra característica?**   | N. º La herramienta se reemplazará por las configuraciones de informes electrónicas en próximas versiones. |
| **Áreas de producto afectadas**         | Libro mayor general                                                                           |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Importación de las transacciones de pago del cliente para Finlandia

Puede seleccionar un formato de importación para los pagos finlandeses para importar las transacciones de pago del cliente desde un archivo externo proporcionado por el banco.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El formato de pago ya no se usa.                                                     |
| **¿Reemplazado por otra característica?**   | N. º El formato se sustituirá por formatos ISO 20022 de importación de criterio en próximas versiones. |
| **Áreas de producto afectadas**         | Clientes                                                                       |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.                            |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Importación de transacciones de pago en un diario de contabilidad general para Finlandia

Se usa un formato específico para Finlandia para importar las transacciones de contabilidad en la contabilidad general.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El formato de pago ya no se usa.                                                     |
| **¿Reemplazado por otra característica?**   | N. º El formato se sustituirá por formatos ISO 20022 de importación de criterio en próximas versiones. |
| **Áreas de producto afectadas**         | Clientes                                                                       |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.                            |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integración con el software Isabel sincronizado (CIS) para Bélgica

Isabel es el marco de trabajo de la banca electrónica en Europa y es una norma de hecho en Bélgica.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La integración con el cliente Isabel se ha interrumpido.   |
| **¿Reemplazado por otra característica?**   | N. º Los formatos de pago que ya no se usan son reemplazados por el formato de pago de transferencia de crédito ISO20022 para Bélgica. |
| **Áreas de producto afectadas**         | Proveedores     |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.    |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Modificaciones del plan de cuentas y reglas de contabilidad para España

Esta característica se usa para los cambios en el plan de cuentas y en las reglas de contabilidad de España. Asigna cuentas para ayudar a transformar el antiguo plan de cuentas en el nuevo plan contable, y compara el ejercicio anterior con el nuevo ejercicio, incluso si se han registrado en números de cuenta distintos.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Uso limitado                                                  |
| **¿Reemplazado por otra característica?**   | N.º                                                             |
| **Áreas de producto afectadas**         | Contabilidad general                                                 |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Formato de pago de proveedor de Pagamento Fornittori

Formato de pago de transferencia de crédito de Legacy italiano.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El formato de pago ya no se usa.                          |
| **¿Reemplazado por otra característica?**   | Sí, formato de pago de transferencia de crédito ISO20022 para Italia         |
| **Áreas de producto afectadas**         | Proveedores                                               |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="payment-export-formats-for-estonia"></a>Formatos de exportación de pagos para Estonia

Los formatos de Telehansa y Teleservicio se usan para la exportación de pago bancario.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los formatos de pago ya no se usan.                        |
| **¿Reemplazado por otra característica?**   | Sí, formato de pago de transferencia de crédito ISO20022 para Estonia       |
| **Áreas de producto afectadas**         | Proveedores                                               |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="payment-file-archive-for-norway"></a>Archivo de pago para Noruega

Cuando se generan los archivos de pago, el archivo almacena automáticamente todos los archivos que se crean, incluso los que se han escrito o leído con anterioridad.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Reemplazado por otra característica                                        |
| **¿Reemplazado por otra característica?**   | Sí, trabajos archivados de informes electrónicos                            |
| **Áreas de producto afectadas**         | Cuentas de proveedores, cuentas de clientes, administración de la empresa |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.     |

### <a name="payment-import-formats-for-estonia"></a>Formatos de importación de pagos para Estonia

Los formatos de Telehansa y TeleTeenus se usan para la importación de pago bancario.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los formatos de pago ya no se usan.                                                    |
| **¿Reemplazado por otra característica?**   | N. º Los formatos se sustituirán por formatos ISO 20022 de importación de criterio en próximas versiones. |
| **Áreas de producto afectadas**         | Clientes                                                                        |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.                             |

### <a name="payroll-information-in-human-resources"></a>Información de nómina en Recursos humanos

Información de nómina en Recursos humanos

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Esta funcionalidad se ha sustituido por páginas principales de nóminas y Recursos Humanos.  |
| **¿Reemplazado por otra característica?**   | Se han reconfigurado las páginas **Prestaciones**, **Ganancias** y otras páginas relacionadas que estaban anteriormente en nóminas de Estados Unidos y ahora forman parte de la configuración de Recursos humanos base para ayudar con el procesamiento externo de nóminas. A esta función se accede mediante la clave de configuración **Recursos humanos 1** \> **Nómina**. |
| **Áreas de producto afectadas**         | Recursos humanos, Nómina   |
| **Estado**                         | Se quitó en Dynamics 365 for Operations versión 1611.    |

### <a name="performance-management-goal-workflow"></a>Flujo de trabajo de objetivo de gestión del rendimiento

La gestión del rendimiento incluye la administración y la integración del objetivo con las evaluaciones de rendimiento.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La gestión del rendimiento se diseñó de nuevo y el número de páginas de objetivos se redujo para simplificar el proceso.                 |
| **¿Reemplazado por otra característica?**   | N. º Los objetivos son visibles para los administradores a través del portal Manager Self Service, y se pueden ver y cambiar por el administrador. |
| **Áreas de producto afectadas**         | Gestión del capital humano       |
| **Estado**                         | Se quitó en Dynamics 365 for Operations versión 1611.    |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Formatos de pago de Postgirot y Postgirot Utland para Suecia

Formatos de pago de Postgirot y Postgirot Utland para Suecia.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los formatos de pago ya no se usan.                        |
| **¿Reemplazado por otra característica?**   | Sí, formato de pago de transferencia de crédito ISO20022 para Suecia        |
| **Áreas de producto afectadas**         | Proveedores                                               |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="radio-frequency-identifier"></a>Identificador por radiofrecuencia

La identificación por radiofrecuencia (RFID) es una tecnología de recopilación de datos que utiliza etiquetas electrónicas para almacenar datos de identificación y no precisa ningún lector de requisitos visuales para capturarlos.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Poco uso de cliente y conjunto limitado de funciones.   |
| **¿Reemplazado por otra característica?**   | N.º                                              |
| **Áreas de producto afectadas**         | Gestión de inventarios                            |
| **Estado**                         | Eliminado desde Dynamics 365 for Operations 1611. |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Informe sobre la numeración del estado de las facturas para Letonia

La legislación letona proporciona reglas específicas acerca de la numeración de las facturas de ventas. Dicha funcionalidad le permite asignar números específicos a las facturas de ventas, en función del usuario o del grupo de usuarios. A continuación puede generar un informe o un archivo XML. También puede imprimir un informe sobre los números de factura que se usan.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La numeración de la factura de estado ya no tiene que mantenerse. El informe sobre números de factura utilizados ya no es necesario. |
| **¿Reemplazado por otra característica?**   | N.º       |
| **Áreas de producto afectadas**         | Clientes    |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.  |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Configuración de los nombres del administrador y el contable general de una empresa para Lituania

Los nombres del administrador y el contable general de una empresa se pueden especificar en la información de la empresa y usar en distintas copias impresas locales del informe.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Reemplazado por otra característica                                     |
| **¿Reemplazado por otra característica?**   | Sí, la configuración de funcionarios se puede usar con el mismo propósito.   |
| **Áreas de producto afectadas**         | Clientes, Proveedores, Gestión de efectivo y bancos |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.  |

### <a name="shipping-carrier-interface"></a>Interfaz de transportistas de envío

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Funcionalidad duplicada   |
| **¿Reemplazado por otra característica?**   | Reemplazado parcialmente por la administración de transporte |
| **Áreas de producto afectadas**         | Ventas y marketing, Gestión de inventarios  |
| **Estado**                         | Se quitó en Dynamics 365 for Operations versión 1611.  |

### <a name="telepay-payment-formats-for-norway"></a>Formatos de pago Telepay para Noruega

Los formatos de pago Telepay incluyen la exportación del pago de proveedor (transferencia de crédito) y el cobro de pago del cliente (domiciliación bancaria).

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los formatos de pago ya no se usan.                                                        |
| **¿Reemplazado por otra característica?**   | Sí, formato de pago de transferencia de crédito ISO20022 y formato de pago del cliente de AvtaleGiro para Noruega |
| **Áreas de producto afectadas**         | Cuentas de proveedores, cuentas de clientes                                                          |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.                                 |

### <a name="vendor-payment-export-formats-for-finland"></a>Formatos de exportación de pago de proveedores para Finlandia

Dos formatos para exportar pagos están disponibles para Finlandia. LM02 (FI) se usa para pagos nacionales y LUM2 (FI) se usa para pagos extranjeros.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los formatos de pago ya no se usan.                        |
| **¿Reemplazado por otra característica?**   | Sí, formato de pago de transferencia de crédito ISO20022 para Finlandia       |
| **Áreas de producto afectadas**         | Proveedores                                               |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="warehouse-management-ii"></a>Gestión de almacenes II

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La solución Warehouse Management II (WMS II) que estaba disponible en el módulo **Gestión de inventarios** duplica la funcionalidad en el módulo de **Gestión de almacenes** que se lanzó en Dynamics AX 2012 R3.                                                                         |
| **¿Reemplazado por otra característica?**   | El módulo **Administración de almacenes** lanzado en AX 2012 R3, Dynamics AX 2012 R3 CU8 y Dynamics AX 2012 R3 CU9 reemplaza las funciones de Gestión de almacenes II. El nuevo módulo dispone de características más avanzadas y procesos más flexibles de gestión de almacenes que Gestión de almacenes II. |
| **Áreas de producto afectadas**         | Gestión del inventario, ventas y marketing, adquisición y abastecimiento   |
| **Estado**                         | Se quitó en Dynamics 365 for Operations versión 1611.    |

### <a name="worker-reminders-in-human-resources"></a>Recordatorios de trabajador en Recursos humanos

Información de nómina en Recursos humanos

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Poco uso                                                           |
| **¿Reemplazado por otra característica?**   | N.º                                                                  |
| **Áreas de producto afectadas**         | Recursos humanos                                                     |
| **Estado**                         | Se quitó en Dynamics 365 for Operations versión 1611 |

### <a name="workflow-for-creating-goals"></a>Flujo de trabajo para crear objetivos

Un flujo de trabajo para gestionar la creación de los objetivos del empleado es uno de varios flujos de trabajo que estaban disponibles para ayudar a coordinar el proceso de gestión del rendimiento.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | En Finance and Operations la administración del rendimiento se ha rediseñado por completo.     |
| **¿Reemplazado por otra característica?**   | La característica de Gestión del rendimiento que se ha diseñado de nuevo proporciona más control sobre el contenido de los objetivos, las medidas que se utilizan para realizar el seguimiento del progreso y los datos adjuntos de la documentación correspondiente. Los objetivos se pueden almacenar como plantillas y volverse a utilizar. Esta función puede ayudarle a configurar los objetivos adicionales para sus empleados con más rapidez. |
| **Áreas de producto afectadas**         | Gestión del capital humano                 |
| **Estado**                         | Se quitó en Dynamics 365 for Operations versión 1611. |

## <a name="dynamics-ax-70"></a>Dynamics AX 7.0 


### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Capacidad para cancelar cambios en una factura de proveedor

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Mejora del rendimiento        |
| **¿Reemplazado por otra característica?**   | N.º                             |
| **Áreas de producto afectadas**         | Proveedores               |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0. |

### <a name="aif-axd-and-axbc-integrations"></a>Integración de AIF, Axd y AxBC

En Application Integration Framework (AIF), los datos se pueden intercambiar con sistemas externos por medio de lógica de negocios expuesta como servicios. Dynamics AX incluye servicios que se basan en documentos y en .NET Business Connector (AxBC). Los documentos se crean mediante XML. El XML incluye información de encabezado que se agrega para crear un *mensaje* que se puede transferir a o de Dynamics AX. Algunos ejemplos de documentos son los pedidos de compra y venta. No obstante, casi cualquier entidad, como un cliente, puede ser representado por un documento. Los servicios que se basan en documentos usan las clases **Axd \<Documento\>**.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La arquitectura de AIF y de AxDs no se podría escalar un servicio de nube. Ha habido problemas de rendimiento en la importación masiva.                                        |
| **¿Reemplazado por otra característica?**   | Esta característica se sustituye por el marco de importación y exportación de datos, compatible con la importación y exportación masiva recurrente. Para AxBC, se recomienda usar las tablas reales. |
| **Áreas de producto afectadas**         | AxDs, AxBC y AIF   |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.   |

### <a name="billing-code-rate-scripts"></a>Secuencias de comandos de índice de código de facturación

Las secuencias de facturación se usaban para calcular aranceles de factura para los códigos de facturación. Estas secuencias de comandos requerían desarrollo personalizado en C# o el lenguaje de programación Visual Basic. En la versión actual de Dynamics AX, los **scripts de la tasa de código de facturación** no se admiten.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La compatibilidad para los scripts de C# o Visual Basic personalizados no se ha agregado a Dynamics AX 7.0. |
| **¿Reemplazado por otra característica?**   | No                                                                                      |
| **Áreas de producto afectadas**         | Sector público, clientes                                    |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.                                                          |

### <a name="boms-without-bom-versions"></a>L. MAT sin versiones de L. MAT

Cuando la clave de configuración **Versiones de L. MAT.** se deshabilita, las versiones de la lista de materiales se ocultan en todos los formularios, y el sistema fuerza una relación 1:1 entre los productos liberados y las listas de materiales. En la versión actual de Dynamics AX, no se puede deshabilitar la clave de configuración de las **versiones BOM**.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El uso de una clave de configuración para controlar las versiones de listas de materiales no se escala en un entorno de nube. |
| **¿Reemplazado por otra característica?**   | N.º                                                                                      |
| **Áreas de producto afectadas**         | Gestión de información de productos, Gestión de inventarios                                    |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.                                                          |

### <a name="brazilian-bordero"></a>Bordero brasileño

Forma de pago específica para las empresas brasileñas

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La ayuda de la forma de pago para el Bordero brasileño se ha interrumpido para la ubicación brasileña |
| **¿Reemplazado por otra característica?**   | N.º   |
| **Áreas de producto afectadas**         | Proveedores   |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="brazilian-sintegra-statement"></a>Extracto de Sintegra brasileño

Extracto del impuesto federal para el impuesto de ICMS

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Este extracto ya no se aplica en algunos estados brasileños. |
| **¿Reemplazado por otra característica?**   | N. º Los usuarios pueden utilizar la herramienta de informes electrónica genérica para configurar el extracto si es necesario de acuerdo a situaciones específicas. |
| **Áreas de producto afectadas**         | Libros fiscales    |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.   |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Modo brasileño de contingencia SCAN brasileña para NF-e

El entorno de contingencia de (SCAN) se usa para generar, exportar e importar el estado de una Nota fiscal electrónica (NF-e) cuando el entorno de la Secretaría de Hacienda (SEFAZ) no está disponible.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Este método de contingencia ya no es un aplicable en todos los estados brasileños |
| **¿Reemplazado por otra característica?**   | N.º                                                                          |
| **Áreas de producto afectadas**         | Clientes                                                         |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.              |

### <a name="business-analyzer"></a>Analizador de negocio

Esta aplicación móvil permite a los usuarios revisar métricas de negocio clave.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Esta funcionalidad se ha reemplazado por otra característica.   |
| **¿Reemplazado por otra característica?**   | El paquete de contenido de supervisión del rendimiento financiero para Microsoft Power BI incluirá métricas financieras clave anteriormente disponibles en Business Analyzer. |
| **Áreas de producto afectadas**         | Contabilidad general      |
| **Estado**                         | En desuso: El uso de un analizador de negocio está en desuso.    |

### <a name="business-statistics"></a>Estadísticas comerciales

La configuración de consultas de estadísticas comerciales que le pueden ayudar a analizar el rendimiento de la organización

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Método de herencia para la inteligencia empresarial (BI), poco uso por parte del cliente y un conjunto limitado de características |
| **¿Reemplazado por otra característica?**   | Nuevas soluciones de inteligencia empresarial para la versión actual de Dynamics AX                                      |
| **Áreas de producto afectadas**         | Adquisición y abastecimiento, Proveedores, Ventas y marketing, Clientes.         |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.                                                               |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Cambio de la función de fecha de documento en el diario de aprobación de facturas

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Poco uso                                                               |
| **¿Reemplazado por otra característica?**   | Sí. La fecha de documento en la transacción de proveedor registrada puede cambiarse. |
| **Áreas de producto afectadas**         | Proveedores                                                        |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.                                          |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Formato de pago ClieOp03 para Países Bajos

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El formato ya no es aplicable en los Países bajos, ya que se ha sustituido por la funcionalidad SEPA. |
| **¿Reemplazado por otra característica?**   | Exportación de pagos SEPA  |
| **Áreas de producto afectadas**         | Todos los módulos     |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.   |

### <a name="compliance-center"></a>Centro de cumplimiento

El Centro de cumplimiento era un sitio de Enterprise Portal para gestionar los requisitos de documentación para las iniciativas de conformidad relacionadas con la ley Sarbanes-Oxley.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Falta de uso del cliente. Microsoft SharePoint incluye la misma capacidad que estaba disponible en el Centro de cumplimiento. |
| **¿Reemplazado por otra característica?**   | N.º   |
| **Áreas de producto afectadas**         | Cumplimiento y controles internos  |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.    |

### <a name="connector-for-microsoft-dynamics"></a>Conector para Microsoft Dynamics

Esta herramienta se usó para integrar datos clave de Microsoft Dynamics CRM en las aplicaciones de Dynamics ERP.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Esta funcionalidad se ha reemplazado por otra característica. |
| **¿Reemplazado por otra característica?**   | Common Data Service                                      |
| **Áreas de producto afectadas**         | Conector para Dynamics                         |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.                           |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Unidad de contenedor y multidimensión disponibles

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Funcionalidad duplicada |
| **¿Reemplazado por otra característica?**   | Sí. Desde AX 2012, esta funcionalidad se ha reemplazado por el conjunto de características de pedidos de lotes consolidados. Este conjunto de características incluye la vista disponible consolidada. |
| **Áreas de producto afectadas**         | Gestión de información de productos, Control de producción, Administración de inventario, Ventas y marketing  |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0. |

### <a name="cue-group-metadata"></a>Metadatos de grupo de pilas

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los grupos de pilas se usaban para mostrar una o más pilas en el área de cuadro informativo. La capacidad era limitada y había también problemas de rendimiento, porque un cambio de registro en un formulario principal generaba una consulta por pila en el grupo de pilas. |
| **¿Reemplazado por otra característica?**   | N.º      |
| **Áreas de producto afectadas**         | Todos los módulos    |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.  |

### <a name="cue-metadata"></a>Metadatos de pila

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los metadatos de pila estaban limitados a contar o sumar información.    |
| **¿Reemplazado por otra característica?**   | Los metadatos de icono se introdujeron para proporcionar más flexibilidad para modelar. Por ejemplo, puede modelar recuentos actuales, navegación e indicadores de rendimiento clave (KPI). Los metadatos de icono de recuento sustituyen directamente a los metadatos de pila. |
| **Áreas de producto afectadas**         | Todos los módulos           |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0      |

### <a name="danish-check-format"></a>Formato de cheque danés

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Se ha dejado de permitir usar el diseño de formato de cheque danés, y el informe se ha retirado de la localización DK. |
| **¿Reemplazado por otra característica?**   | N.º    |
| **Áreas de producto afectadas**         | Todos los módulos    |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.  |

### <a name="data-partitions"></a>Particiones de datos

Las particiones de los datos proporcionan una separación lógica de datos en la base de datos de Dynamics AX.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Las particiones de datos se introdujeron en Dynamics AX 2012 R2 para habilitar el aislamiento de los datos. En un escenario común, una compañía tiene filiales y los datos de una filial no deben ser visibles para otra, aunque el mismo departamento de TI administre ambas filiales. Sin embargo, se requerían gastos generales de administración y scripts adicionales en todo el programa para crear nuevas particiones y rellenarlas con datos y hacer copia de seguridad de los datos de partición. En la nube, donde tenemos acceso a la plataforma como servicios de base de datos (Base de datos SQL Microsoft Azure) de un servicio (PaaS), es mucho más eficaz utilizar una base de datos como el contenedor de aislamiento para realizar el aislamiento en el programa. Con independencia de si se requiere la partición de datos para filiales, para varios inquilinos o simplemente para escala, creemos que los escenarios se pueden controlar mejor a través de varias instancias de Finance and Operations. |
| **¿Reemplazado por otra característica?**   | Los clientes que usan particiones de datos deben usar varias instancias de Finance and Operations si la separación de nivel de base de datos es un asunto crítico.    |
| **Áreas de producto afectadas**         | Todos los módulos  |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.  |


### <a name="database-and-file-share-storage-for-attachments"></a>Almacenamiento de recursos compartidos de archivo y base de datos para los datos adjuntos

Dynamics AX 2012 permitía el almacenamiento de datos adjuntos en los recursos compartidos de archivos y la base de datos. Ambas opciones ya no se admiten.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El almacenamiento de recurso compartido de archivos ya no se admite ya que los entornos hospedados en la nube no pueden comunicarse con los recursos compartidos de archivos. El almacenamiento de base de datos se ha dejado de utilizar en favor del almacenamiento de blobs de Azure. El almacenamiento de blobs de Azure es equivalente al almacenamiento en la base de datos, ya que solo se puede tener acceso a los documentos a través de formularios cliente de Finance and Operations. Esto ofrece la ventaja adicional de proporcionar almacenamiento que no afecte negativamente al rendimiento de la base de datos. El almacenamiento de blobs es el mecanismo predeterminado de almacenamiento para la gestión de documentos y funciona inmediatamente. |
| **¿Reemplazado por otra característica?**   | El almacenamiento de base de datos se ha dejado de utilizar en favor del almacenamiento de blobs de Azure.   |
| **Áreas de producto afectadas**         | Todos los módulos  |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.   |

### <a name="delimitation"></a>Delimitación

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | No se ha encontrado ningún uso de la función. |
| **¿Reemplazado por otra característica?**   | N.º                                     |
| **Áreas de producto afectadas**         | Tiempo y asistencia                    |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.         |

### <a name="desktop-client"></a>Cliente de escritorio

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La experiencia de cliente de Dynamics AX se ha rediseñado para mejorar la capacidad de uso en varias plataformas y dispositivos.                      |
| **¿Reemplazado por otra característica?**   | El nuevo cliente web se basa en los metadatos de formulario de escritorio y el modelo de programación que se han modificado para proporcionar una plataforma web enriquecida. |
| **Áreas de producto afectadas**         | Todos los módulos  |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.   |

### <a name="direct-database-connection"></a>Conexión con base de datos directa

En Dynamics AX 2012 R3, Retail Modern POS podía conectarse directamente a la base de datos de canales de forma parecida a la de Enterprise POS. Esto se añadía al método de comunicación estándar en que Retail Modern POS se comunicaba mediante Retail Server.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La conectividad directa de la base de datos requería protocolos de seguridad inferiores y se usaba principalmente para alcanzar niveles de rendimiento más altos. Debido a las mejoras del rendimiento y de seguridad que se han producido en Finance and Operations, esta funcionalidad ahora está dando más problemas que soluciones. |
| **¿Reemplazado por otra característica?**   | N. º Ahora solo se da soporte a la comunicación de Retail Server estándar.  |
| **Áreas de producto afectadas**         | Base de datos de canales/Retail Modern POS   |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.  |

### <a name="dutch-swift-mt940"></a>SWIFT MT940 holandés

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Ahora se utiliza la función genérica en lugar de la función localizada.                    |
| **¿Reemplazado por otra característica?**   | Sí, esta función se ha reemplazado por la funcionalidad avanzada de conciliación bancaria. |
| **Áreas de producto afectadas**         | Todos los módulos                                                                              |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.                           |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL para Alemania)

Esta funcionalidad proporcionaba salida en el lenguaje eXtensible Business Reporting Language (XBRL) pensada específicamente para la taxonomía alemana eBilanz.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Falta de uso del cliente  |
| **¿Reemplazado por otra característica?**   | Esta característica no se ha sustituido por otra, pero hay disponibles varios paquetes XBRL especializados que proporcionan funcionalidad XBRL enriquecida para el mercado alemán. |
| **Áreas de producto afectadas**         | Management Reporter      |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.  |

### <a name="enterprise-portal-client"></a>Cliente de Enterprise Portal

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Se ha proporcionado una sola plataforma de cliente.  |
| **¿Reemplazado por otra característica?**   | El nuevo cliente web se basa en los metadatos del formulario de escritorio y el modelo de programación que se han modificado para proporcionar una plataforma web enriquecida. |
| **Áreas de producto afectadas**         | Todos los módulos  |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.   |

### <a name="environmental-sustainability"></a>Sustentabilidad ambiental

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Poco uso de cliente y conjunto limitado de funciones  |
| **¿Reemplazado por otra característica?**   | N.º              |
| **Áreas de producto afectadas**         | Cumplimiento y controles internos, Proveedores  |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0. |

### <a name="form-activex-and-managed-host-controls"></a>Controles de formulario de host administrados y ActiveX

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los controles ActiveX y de host administrados se basan en el cliente de escritorio obsoleto. |
| **¿Reemplazado por otra característica?**   | El marco de controles extensibles admite la creación de nuevos controles que se basan en HTML, CSS y Javascript, y es un control de primera clase en el entorno de Microsoft Visual Studio Tooling. |
| **Áreas de producto afectadas**         | Todos los módulos     |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.       |

### <a name="generate-prenotes-by-using-a-batch"></a>Generación de prenotas mediante un lote

La generación de prenotas no se puede hacer mediante un lote pero sí la puede realizar un usuario.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | No hay manera de persistir y mostrar el archivo de prenota resultante cuando se genera mediante un lote. |
| **¿Reemplazado por otra característica?**   | Aún se pueden generar prenotas y el usuario tiene control sobre la ubicación en la que se guarda el archivo.   |
| **Áreas de producto afectadas**         | Clientes, Proveedores, Gestión de efectivo y bancos  |
| **Estado**                         | Eliminado desde AX 7.0.    |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Exportación de pagos DTAUS alemanes e importación de extractos de cuentas (totales y transacciones)

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El formato ya no es aplicable en Alemania, ya que se ha sustituido por la funcionalidad SEPA (zona única de pagos en euros).                    |
| **¿Reemplazado por otra característica?**   | Sí, esta funcionalidad se ha reemplazado por la funcionalidad de exportación de pagos SEPA y conciliación bancaria avanzada para importar extractos de cuenta. |
| **Áreas de producto afectadas**         | Todos los módulos  |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="german-dtazv-payment-format"></a>Formato de pago DTAZV para Alemania

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El formato ya no es aplicable en Alemania, ya que se ha sustituido por la funcionalidad SEPA. |
| **¿Reemplazado por otra característica?**   | Exportación de pagos SEPA    |
| **Áreas de producto afectadas**         | Todos los módulos   |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.    |

### <a name="german-mt940-import"></a>Importación MT940 alemana

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Ahora se utiliza la función genérica en lugar de la función localizada.                    |
| **¿Reemplazado por otra característica?**   | Sí, esta función se ha reemplazado por la funcionalidad avanzada de conciliación bancaria. |
| **Áreas de producto afectadas**         | Todos los módulos                                                                              |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.                           |

### <a name="german-xml-eu-sales-list"></a>Lista de ventas UE XML para Alemania

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Ya no se admite el formato XML para los informes de Lista de ventas de la UE para Alemania. Solo se puede usar el formato de archivo de texto ELMA5 para enviar el informe de la Lista de ventas de la UE a la delegación de hacienda alemana. |
| **¿Reemplazado por otra característica?**   | N.º         |
| **Áreas de producto afectadas**         | Impuesto        |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.   |

### <a name="gl-ssrs-reports"></a>Informes GL SSRS

Se han retirado los informes que incluyen los siguientes elementos de menú: **Resumen de saldo de comprobación**, **Saldo de comprobación detallado**, **Plan contable**, **Traza de auditoría**, **Saldos** y **Lista de saldo**.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los informes de Financial Microsoft SQL Server Reporting Services (SSRS) han sido reemplazados con capacidades de Management Reporter e informes predeterminados. |
| **¿Reemplazado por otra característica?**   | Management Reporter (etiquetado **Informes financieros** en la versión actual de Dynamics AX)    |
| **Áreas de producto afectadas**         | Contabilidad general   |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.   |

### <a name="infopart-and-formpart-metadata"></a>Metadatos de InfoPart y FormPart

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los metadatos de InfoPart y de FormPart permitieron la creación de cuadros informativos para dos clientes diferentes. |
| **¿Reemplazado por otra característica?**   | Los metadatos de InfoPart, que eran una definición simplificada de formulario, se han convertido a un formulario mediante herramientas de actualización. Los metadatos de FormPart, con un formulario al que se hace referencia, se han sustituido por una referencia más directa creada mediante herramientas de actualización. |
| **Áreas de producto afectadas**         | Todos los módulos    |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.        |

### <a name="main-account-list-page"></a>Página de lista Cuenta principal

Una lista de cuentas para la entidad jurídica y la información relacionada de saldo

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La información del saldo está disponible en la página de lista **Saldo de comprobación** por cuenta y dimensión.  |
| **¿Reemplazado por otra característica?**   | **Cuentas principales** contiene la misma lista de cuentas que contenía la página de lista **Cuenta principal**. La vista de cuadrícula en **Cuentas principales** también muestra una vista más pequeña tipo cuadrícula. |
| **Áreas de producto afectadas**         | Contabilidad general      |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.    |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Informe de flujo de efectivo bancario de Malasia y Singapur

Esta función permite al usuario imprimir un informe de flujo de efectivo que muestra transacciones y detalles de flujos de entrada y de salida de efectivo para un intervalo específico de fechas para las cuentas bancarias seleccionadas.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La misma información se puede obtener desde la transacción bancaria de consulta. |
| **¿Reemplazado por otra característica?**   | La transacción bancaria de consulta                                            |
| **Áreas de producto afectadas**         | Gestión de efectivo y bancos                                                |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función.          |

### <a name="mexican-cfd-electronic-invoice"></a>Factura electrónica CFD mexicana

Esta función habilitó la generación de facturas electrónicas mexicanas mediante el método Comprobante Fiscal Digital (CFD), donde la empresa firma la factura solicitando el permiso correspondiente del gobierno. Esta función también proporciona un informe mensual con todas las facturas electrónicas emitidas en el período.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El método ya no es aplicable. La generación de facturas electrónicas usando el método CFD ha sido derogada por las autoridades fiscales y se ha sustituido por el Comprobante Fiscal Digital a través de Internet (CFDI), donde la firma se delega al tercer proveedor (PAC). Se ha quitado el informe mensual, y una opción de consulta permite a los usuarios consultar transacciones históricas. |
| **¿Reemplazado por otra característica?**   | N.º    |
| **Áreas de producto afectadas**         | Clientes, Proyecto   |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="mexico-realized-and-unrealized-vat"></a>IVA realizado y sin realizar en México

Dynamics AX 2012 gestionaba el impuesto sobre el valor añadido (IVA) no realizado mediante la funcionalidad específica para México de impuestos no realizados.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Funcionalidad duplicada  |
| **¿Reemplazado por otra característica?**   | Sí, esta funcionalidad se ha reemplazado por la funcionalidad estándar de impuestos condicional proporcionada por Core. |
| **Áreas de producto afectadas**         | Impuesto   |
| **Estado**                         | En desuso: No se ha establecido una fecha de eliminación para esta función. |

### <a name="microsoft-outlook-integration"></a>Integración de Microsoft Outlook


|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Esta funcionalidad se ha reemplazado por la integración Microsoft Exchange Server. |
| **¿Reemplazado por otra característica?**   | Sí                                                                            |
| **Áreas de producto afectadas**         | Sales and Marketing                                                            |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.                                                 |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Bloqueo privado de los diarios de gestión de almacenes e inventarios

Los diarios de almacén e inventario ya no admiten la opción de marcar un diario como privado para un usuario seleccionado. Solo se admite el proceso de bloqueo de diarios como privado para grupos de usuarios y bloqueo durante la edición.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | No se ha encontrado ningún uso de la función. |
| **¿Reemplazado por otra característica?**   | N.º                                     |
| **Áreas de producto afectadas**         | Gestión de inventarios                   |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.         |

### <a name="product-builder"></a>Configurador de productos

El configurador de productos se usaba para configurar dinámicamente artículos desde un pedido de ventas, presupuesto de ventas, pedido de compra, orden de producción, presupuesto de venta, presupuesto del proyecto o petición de artículo. De acuerdo con un modelo de producto que tenía variables de modelo, el usuario podía seleccionar valores para cumplir con los requisitos del cliente y obtener una variante del producto única con una lista de materiales y una ruta.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El configurador de productos exponía el código X++ a los usuarios finales y no se admite en la versión actual de Dynamics AX. Se ha retirado para evitar esfuerzos duplicados en bases de código superpuestas y cuantiosas.  |
| **¿Reemplazado por otra característica?**   | Sí. La configuración basada en restricciones se introdujo en Dynamics AX 2012 donde ya se anunciaba la depreciación del generador de productos en futuras versiones. La tecnología de configuración basada restricciones se selecciona en los productos maestros para habilitar la configuración. Para obtener más información, consulte [Visión general de la configuración del producto](../../../supply-chain/pim/build-product-configuration-model.md). |
| **Áreas de producto afectadas**         | Gestión de información de productos, Ventas y marketing  |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.      |

### <a name="production-floor-app"></a>Aplicación de planta de producción
Esta es la aplicación de los dispositivos tabletas que ejecutan Windows 8.1 RT y Windows 8.1 Pro.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Con el cambio a un cliente basado en la red, es posible entregar funciones similares a través del cliente nativo de Dynamics AX 7.0. El dispositivo de tarjeta de trabajo proporciona una interfaz de usuario de planta de la producción que se optimiza para los factores de forma de contacto y tabletas. |
| **¿Reemplazado por otra característica?**   | Sí. El dispositivo de la tarjeta de trabajo, que es una parte nativa de Dynamics AX 7.0.                                                                           |
| **Áreas de producto afectadas**         | Control de producción                                                |
| **Estado**                         | Desusado: Una fecha de eliminación de la tienda de Microsoft todavía no se ha establecido para esta función.                                                |


### <a name="rename-product-dimension"></a>Asignar un nuevo nombre a la dimensión del producto

Esta función le permite cambiar el nombre de una de las tres dimensiones de producto estándar (tamaño, color o estilo) a un nombre que cumpla mejor con sus requisitos empresariales. El cambio de nombre incluía todas las etiquetas donde se aislaba el nombre de la dimensión de producto.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La versión actual de Dynamics AX no admite cambios de etiqueta en tiempo de ejecución. |
| **¿Reemplazado por otra característica?**   | N.º                                                                            |
| **Áreas de producto afectadas**         | Gestión de información de productos                                                |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.                                                |

### <a name="retail-server-connectivity-using-http"></a>Conectividad de Retail Server mediante HTTP

En Dynamics AX 2012 R3, Retail Server podía trabajar usando la comunicación HTTP (sin seguridad). Esto estaba además de la comunicación estándar mediante HTTPS.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Debido a los nuevos requisitos de seguridad, ahora solo se admite la comunicación segura mediante TLS 1.2 (o un número superior, si está disponible). El instalador de autoservicio configurará automáticamente el equipo para esta comunicación. |
| **¿Reemplazado por otra característica?**   | N. º Ahora solo se da soporte a la comunicación de HTTPS estándar. |
| **Áreas de producto afectadas**         | Retail Server  |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0. |

### <a name="role-center-pages"></a>Páginas de áreas de trabajo

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Las páginas de área de trabajo se crearon en la plataforma de Enterprise Portal obsoleta, la cual se ha actualizado mediante la nueva plataforma de cliente web en la versión actual de Dynamics AX. |
| **¿Reemplazado por otra característica?**   | El nuevo patrón del formulario de espacio de trabajo proporciona a los usuarios un diseño centrado en el proceso de fácil acceso a las tareas de uso general dentro de dicho proceso.                       |
| **Áreas de producto afectadas**         | Todos los módulos    |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0   |

### <a name="sales-tax-jurisdictions"></a>Jurisdicciones de impuestos

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Poco uso de cliente y conjunto limitado de funciones |
| **¿Reemplazado por otra característica?**   | N.º                                           |
| **Áreas de producto afectadas**         | Impuestos de EE.UU                                 |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.               |

### <a name="sites-services"></a>Sites Service

Servicios de sitios le permite crear sitios web que amplía sus procesos empresariales a Internet sin el soporte técnico de TI.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La infraestructura de Microsoft Azure que usa Dynamics AX tiene nuevas capacidades que se pueden usar en su lugar (por ejemplo, sitios de Azure). |
| **¿Reemplazado por otra característica?**   | N.º   |
| **Áreas de producto afectadas**         | Reclutamiento de recursos humanos, gestión de casos, solicitudes de presupuesto, registro de proveedores, áreas de trabajo colaborativas para oportunidades y campañas  |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.    |

### <a name="ssas-demand-forecasting-strategy"></a>Estrategia de previsión de la demanda de SSAS

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El diseño de la característica no se admite en la nueva arquitectura de la nube. |
| **¿Reemplazado por otra característica?**   | Estrategia de previsión de demanda de Aprendizaje automático de Azure                           |
| **Áreas de producto afectadas**         | Planificación maestra                                                              |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.                                               |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Ver detalles de grupo de facturas de proveedor excluidas del registro

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Poco uso. Esta funcionalidad se ha reemplazado por el Diario de facturas que tiene la funcionalidad del flujo de trabajo. |
| **¿Reemplazado por otra característica?**   | Capacidades del flujo de trabajo del Diario de facturas.     |
| **Áreas de producto afectadas**         | Proveedores |
| **Estado**                         | Eliminado a partir de Dynamics AX 7.0.    |


### <a name="virtual-company-accounts"></a>Cuentas de empresa virtuales

La característica de empresas virtuales ya no se admite en Dynamics AX. La característica de empresas virtuales permite a los usuarios configurar tablas que se puedan compartidas por un conjunto de empresas. Puede obtener una descripción de la función, vea [Cuentas de empresa y cuentas de empresa virtuales](https://msdn.microsoft.com/library/aa834382(v=ax.10).aspx). La función trabaja agrupando tablas en recopilaciones que se asignan a empresas virtuales, que son grupos de empresas “reales” existentes. Se crean consultas de modo que todas las empresas de la empresa virtual puedan obtener acceso a los datos de las tablas de las recopilaciones de tablas asociadas.

|   |  | 
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | - Las empresas virtuales deben configurarse antes de que los datos se almacenen en las tablas. La retroadaptación de las empresas virtuales en la implementación existente es muy difícil.<br><br>- Dado que se han normalizado tantos datos en la versión actual de Dynamics AX, se ha hecho difícil saber qué agregar a las colecciones de tablas. Por ejemplo, es difícil saber qué tablas compartir. Todas las tablas a las que se hace referencia desde las tablas en una empresa virtual también se deben agregar. Debido a la normalización de la tabla, incluso los datos maestros sencillos que se extienden en múltiples tablas deben formar parte de la empresa virtual. Cualquier error que se realice producirá problemas funcionales.<br><br>- Cuando una tabla forma parte de una empresa virtual, pierde la información acerca del origen de los datos y solo se registra la empresa virtual.   |
| **¿Reemplazado por otra característica?** | Se pueden usar tablas globales para que las tablas sean accesibles desde todas las empresas. Actualmente no hay ninguna sustitución. |   
| **Áreas de producto afectadas**       | Todos los módulos |   
| **Estado**                       | Eliminado a partir de Dynamics AX 7.0.   |   

### <a name="windows-8-tablet-app"></a>Aplicación para tabletas con Windows 8

La aplicación para tabletas con Windows 8 ofrecía funcionalidad para la entrada y la aprobación de gastos.

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Finance and Operations es compatible con tabletas. La aplicación para tabletas ya no se requiere.    |
| **¿Reemplazado por otra característica?**   | N. º          |
| **Áreas de producto afectadas**         | Gestión de gastos   |
| **Estado**                         | Quitado: Esta funcionalidad sólo está disponible para Dynamics AX 2012 R3. |

### <a name="workplanner"></a>Planificador de trabajo

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Poco uso |
| **¿Reemplazado por otra característica?**   | No, pero la página **Relación de perfiles**, que se abre desde la página **Grupos de perfiles**, admite el mismo escenario empresarial que la página **Planificador de trabajo** desaprobada. |
| **Áreas de producto afectadas**         | Tiempo y asistencia     |
| **Estado**                         | No se ha quitado el código. Sin embargo, el formulario, JmgWorkPlanner, no se ha migrado.    |

### <a name="x-financial-statements"></a>Informes financieros de X++

|                                                 |                                                                                                          |
|-------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| <strong>Motivo de la depreciación/eliminación</strong> |                         Esta funcionalidad se ha reemplazado por otra característica.                         |
|  <strong>¿Reemplazado por otra característica?</strong>  | Management Reporter (etiquetado <strong>Informes financieros</strong> en la versión actual de Dynamics AX) |
|     <strong>Áreas de producto afectadas</strong>     |                                              Contabilidad general                                              |
|             <strong>Estado</strong>             |                                      Eliminado a partir de Dynamics AX 2012                                      |

