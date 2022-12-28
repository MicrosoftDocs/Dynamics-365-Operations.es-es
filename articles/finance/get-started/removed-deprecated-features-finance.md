---
title: Características quitadas o en desuso de Dynamics 365 Finance
description: En este artículo se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Finance.
author: kfend
ms.date: 10/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 25d13aa26565e5753b87c843b43cf46f8276b642
ms.sourcegitcommit: 6c05bcd27e6ee72f01cb66e2cfd1e929e0365830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2022
ms.locfileid: "9854089"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Características quitadas o en desuso de Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

En este artículo se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Finance.

- Una función *quitada* dejará de estar disponible en el producto.
- Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación. 

> [!NOTE]
> La información detallada sobre los objetos de aplicaciones de finanzas y operaciones se puede encontrar en los [Informes de referencia técnica](/dynamics/s-e/global/axtechrefrep_61). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones de finanzas y operaciones.

## <a name="features-removed-or-deprecated-in-the-finance-10031-release"></a>Características quitadas o en desuso en la versión Finance 10.0.31

### <a name="edifact-paymul-at-configuration-under-payment-model"></a>Configuración de EDIFACT PAYMUL (AT) bajo Modelo de pago

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo de la depreciación/eliminación** | Reemplazado con un nuevo formato basado en ISO 20022 pain.001.001.09. | 
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Aplicación |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: los bancos en Austria dejarán de usar EDICFACT-PAYMUL para pagos transfronterizos en noviembre de 2022 y lo reemplazarán con la versión XML pain.001.001.09N. Se ha agregado una nueva configuración en el repositorio de configuración global que permite a los usuarios completar la solicitud de pago transfronterizo. |

## <a name="features-removed-or-deprecated-in-the-finance-10030-release"></a>Características quitadas o en desuso en la versión Finance 10.0.30

### <a name="revenue-recognition"></a>Reconocimiento de ingresos

[Reconocimiento de ingresos](../../finance/accounts-receivable/revenue-recognition-overview.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo de la depreciación/eliminación** |Reemplazado por una funcionalidad mejorada, [Facturación de suscripción](../../finance/accounts-receivable/subscription-billing-summary.md)
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas** | Aplicación |
| **Opción de implementación** | Todo |
| **Status** | En desuso: después de abril de 2023, la funcionalidad de reconocimiento de ingresos en Dynamics 365 Finance ya no recibirá soporte con correcciones de errores. Se les pedirá a los clientes que utilicen la funcionalidad mejorada, [Facturación de suscripciones](../../finance/accounts-receivable/subscription-billing-summary.md). En octubre de 2023, la función de reconocimiento de ingresos ya no estará disponible. Se les pedirá a los clientes que cambien a la funcionalidad mejorada de Facturación de suscripciones. Para la característica de paquete como parte del reconocimiento de ingresos, no hay una funcionalidad de reemplazo planificada en este momento.|

## <a name="features-removed-or-deprecated-in-the-finance-10029-release"></a>Características quitadas o en desuso en la versión Finance 10.0.29

### <a name="stock-transfer-orders-that-have-tax-on-the-transfer-price"></a>Pedidos de transferencia de existencias que tienen impuesto sobre el precio de transferencia

[Pedidos de transferencia de existencias que tienen impuesto sobre el precio de transferencia](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo de la depreciación/eliminación** | Reemplazado por una funcionalidad mejorada, [Órdenes de traslado de stock para India](../../finance/localizations/apac-ind-stock-transfer.md)|
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas** | Aplicación |
| **Opción de implementación** | Todo |
| **Status** | En desuso: después de abril de 2023, la funcionalidad **Órdenes de transferencia de acciones que tienen impuesto sobre el precio de transferencia** no recibirá soporte con correcciones de errores y correcciones de seguridad. Se les pedirá a los clientes que utilicen la funcionalidad mejorada, [Órdenes de traslado de stock para India](../../finance/localizations/apac-ind-stock-transfer.md). Después de octubre de 2023, la funcionalidad **Órdenes de transferencia de acciones que tienen impuesto sobre el precio de transferencia** ya no estará disponible y se les pedirá a los clientes que pasen a la funcionalidad mejorada Órdenes de traslado de stock para India. |

### <a name="bank-statement-import-and-export-of-positive-pay-file"></a>Extracto bancario importación y exportación de archivo de pago positivo

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo de la depreciación/eliminación** |Reemplazado por una funcionalidad mejorada, importa extractos bancarios y exporta archivos de pago positivos.| 
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Aplicación |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: la funcionalidad XSLT para importar y exportar archivos ya no recibirá soporte con correcciones de errores y correcciones de seguridad. Se pedirá a los clientes que utilicen la funcionalidad mejorada: [Configurar archivos de pago positivo mediante el uso de informes electrónicos](../../finance/accounts-payable/set-up-positive-pay-er.md) y [Configure la importación avanzada de conciliaciones bancarias mediante informes electrónicos](../../finance/accounts-payable/import-bai2-er.md). Después de septiembre de 2022, la funcionalidad XSLT ya no estará disponible y se les pedirá a los clientes que cambien a la funcionalidad mejorada.|


## <a name="features-removed-or-deprecated-in-the-finance-10026-release"></a>Características quitadas o en desuso en la versión Finance 10.0.26

### <a name="sales-tax-report-for-finland-design-based-on-reporting-codes"></a>Informe del impuesto sobre las ventas en Finlandia (diseño basado en los códigos de notificación)

[Informe fiscal de ventas para Finlandia](../localizations/emea-fin-sales-tax-payment-report-finland.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Sustituido por un nuevo diseño de declaración del IVA, [Declaración de IVA para Finlandia](../localizations/emea-fin-vat-declaration.md). |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Aplicación |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: para el 1 de marzo de 2023, tenemos previsto dejar de dar soporte al informe de impuestos sobre las ventas para Finlandia (diseño de informe para Finlandia). Se introducen los nuevos formatos de informes electrónicos (ER) **Declaración de IVA en TXT (FI**) y **Declaración de IVA en Excel (FI)** en el modelo **Declaración de impuestos**. |

## <a name="features-removed-or-deprecated-in-the-finance-10024-release"></a>Características quitadas o en desuso en la versión Finance 10.0.24

### <a name="sales-tax-report-for-sweden-design-based-on-reporting-codes"></a>Informe del impuesto sobre las ventas en Suecia (diseño basado en los códigos de notificación)

[Informe del impuesto sobre las ventas en Suecia](../localizations/emea-swe-sales-tax-payment-report-sweden.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Sustituido por un nuevo diseño de declaración del IVA, [Declaración de IVA para Suecia](../localizations/emea-swe-vat-declaration-sweden.md) |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: para el 1 de diciembre de 2022, tenemos previsto dejar de dar soporte al informe de impuestos sobre las ventas para Suecia (diseño de informe para Suecia). Se introducen los nuevos formatos de informes electrónicos (ER) **XML de declaración de IVA (SE**) y **Excel de declaración de IVA (SE)** en el modelo **Declaración de impuestos**. |

### <a name="vat-statement-for-austria-design-based-on-reporting-codes"></a>Declaración de IVA para Austria (diseño basado en códigos de notificación)

[Detalles de la declaración de IVA para Austria](../localizations/emea-aut-vat-statement-details.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Sustituido por un nuevo diseño de declaración del IVA, [Declaración de IVA para Austria](../localizations/emea-aut-vat-declaration-austria.md) |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: para el 1 de diciembre de 2022, tenemos previsto dejar de admitir el formato de informes electrónicos (ER) **Declaración de IVA (AT)** en el **Modelo de declaración de IVA**. Se introducen los nuevos formatos **XML de declaración de IVA (AT)** y **Excel de declaración de IVA (AT)** en el modelo **Declaración de impuestos**. |

### <a name="elster-declaration-for-germany-design-based-on-reporting-codes-electronic-tax-declaration-log-menu-item-and-page-electronic-tax-declaration-setup-menu-item-and-page-german-report-layout-taxreport_de-ssrs-format"></a>Declaración ELSTER para Alemania (diseño basado en códigos de informe), \"Registro de declaración de impuestos electrónica\" menu item and page, elemento de menú y página \"Configuración de declaración fiscal electrónica\", diseño de informe alemán (TaxReport_DE) formato SSRS

[Declaración de IVA](../localizations/emea-de-vat-declaration.md)</br>
[Configuración de la declaración de impuestos electrónica para Alemania](../../fin-ops-core/dev-itpro/analytics/tasks/setup-electronic-tax-declaration-germany.md)</br>

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Sustituido por un nuevo diseño de declaración del IVA, [Declaración de IVA para Alemania](../localizations/emea-deu-vat-declaration-germany.md) |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: para el 1 de diciembre de 2022, tenemos previsto dejar de admitir el formato de informes electrónicos (ER) **Elster (DE)** y **Modelo Elster**. Se introducen los nuevos formatos ER **XML de declaración de IVA (DE)** y **Excel de declaración de IVA (DE)** en el modelo **Declaración de impuestos**. Tampoco admitiremos las **Impuestos** \> **Declaraciones** \> **Impuesto sobre las ventas** \> **Registro electrónico de declaración de impuestos** elemento de menú y página, el menú **Impuestos** \> **Configuración** \> **Impuesto sobre las ventas** \> **Configuración de la declaración electrónica de impuestos** y la página, el elemento de menú **Impuestos** \> **Configuración** \> **Impuesto sobre las ventas** \> **Certificados fiscales electrónicos** y y el formato de diseño de informe alemán (TaxReport\_DE) SQL Server Reporting Services (SSRS). El proceso de declaración del IVA en Alemania es compatible con la función [Mensajería electrónica](../general-ledger/electronic-messaging.md). Para obtener más información, vea la [declaración de IVA de Alemania](../localizations/emea-deu-vat-declaration-germany.md). |

### <a name="ob-declaration-for-netherlands-design-based-on-reporting-codes-electronic-ob-declaration-menu-item-and-page-dutch-report-layout-taxreport_nl-ssrs-format"></a>Declaración OB para Países Bajos (diseño basado en códigos de informes), elemento de menú y página \"Declaración OB electrónica\", diseño de informe holandés (TaxReport_NL) formato SSRS

[Declaración OB](../localizations/emea-nl-vat-declaration.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Sustituido por un nuevo diseño de declaración del IVA, [Declaración de IVA para los Países Bajos](../localizations/emea-nl-vat-declaration-netherlands.md) |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: para el 1 de diciembre de 2022, dejaremos de admitir el formato de informes electrónicos (ER) **Declaración OB (NL)** y **Modelo de declaración OB**. Se introducen los nuevos formatos ER **XML de declaración de IVA (NL)** y **Excel de declaración de IVA (NL)** en el modelo **Declaración de impuestos**. Tampoco admitiremos el menú **Impuestos** \> **Declaraciones** \> **Impuesto sobre las ventas** \> elemento y página **Declaración OB electrónica**, y el formato SSRS del diseño del informe holandés (TaxReport_NL). El proceso de declaración del IVA en Países Bajos es compatible con la función [Mensajería electrónica](../general-ledger/electronic-messaging.md). Para obtener más información, vea la [declaración de IVA de Países Bajos](../localizations/emea-nl-vat-declaration-netherlands.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Características quitadas o en desuso en la versión Finance 10.0.20

### <a name="rtir-query-invoice-data-request-hu-electronic-reporting-er-format-configuration"></a>Configuración de formato de informes electrónicos de "solicitud de datos de factura (HU) de consulta RTIR"

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Excluido del procesamiento de mensajes electrónicos de interoperación con el sistema de facturación en línea de Hungría |
| **¿Reemplazado por otra característica?**   | No |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: para el 15 de abril de 2022, planeamos dejar de admitir la configuración del formato "Solicitud de datos de facturas (HU) de consulta RTIR". |

### <a name="french-fec-audit-file-electronic-reporting-er-format-for-france-under-german-audit-file-output-format"></a>Formato de informes electrónicos "Archivo de auditoría francés de FEC" para Francia en el formato "Salida de archivo de auditoría alemán"

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Reemplazado con el nuevo formato de "Archivo de auditoría para Francia (FEC)" |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: para el 1 de mayo de 2022, planeamos dejar de admitir el formato de informes electrónicos de "Archivo de auditoría francés de FEC" para Francia en el formato de "Salida de archivo de auditoría alemán". En su lugar, se introduce el nuevo formato de archivo de auditoría para Francia (FEC) bajo el "Modelo de exportación de datos". |

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Características quitadas o en desuso en la versión Finance 10.0.17

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>Repositorio LCS como opción de almacenamiento para configuraciones de informes electrónicos

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Reemplazado con el nuevo repositorio global del Servicio de configuración regulatoria (RCS) |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Dynamics 365 Finance, Supply Chain Management y productos de Project Operations|
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: para el 1 de abril de 2022, planeamos dejar de ofrecer soporte al repositorio de Microsoft Dynamics Lifecycle Services (LCS) como opción de almacenamiento para configuraciones de informes electrónicos (ER). Las nuevas configuraciones de Microsoft ER se publicarán para su descarga exclusivamente desde el repositorio global. Se puede acceder al repositorio global desde los productos Dynamics 365 y RCS. Para más información, consulte [Importar configuraciones de ER desde RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md) y [Regulatory Configuration Service: desactivación del almacenamiento de Lifecycle Services](../localizations/rcs-lcs-repo-dep-faq.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Características quitadas o en desuso en la versión Finance 10.0.16

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>Formatos de informes electrónicos "Declaración de IVA (CZ)" y "Exportación de declaración de control (CZ)" para la República Checa

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Se han reemplazado con nuevos formatos |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir del 22 de enero de 2022 dejaremos de ofrecer soporte para los formatos de informes electrónicos (ER) "Declaración de IVA (CZ)" y "Exportación de declaración de control (CZ)". En su lugar, se introducen los nuevos formatos XML de declaración de IVA (CZ), Excel de declaración de IVA (CZ) y XML de declaración de control de IVA (CZ) en el modelo "Declaración de impuestos". |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>Formato de informes electrónicos "Formato de exportación de transacciones contables (BE)" y modelo respectivo de "Exportación de transacciones contables (BE)" para Bélgica

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Reemplazado con el nuevo formato ER bajo el modelo "Archivo de auditoría estándar (SAF-T)".  |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: para el 1 de diciembre de 2021, planeamos dejar de admitir el formato de informe electrónico (ER) "Formato de exportación de transacciones contables (BE)" y el modelo correspondiente de "Exportación de transacciones contables (BE)". En su lugar, se introducen un nuevo formato de "Exportación de datos del libro mayor (BE)" junto con "Mapeo del modelo de datos del libro mayor" en el modelo "Archivo de auditoría estándar (SAF-T)". |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>Informe "VAT 100" para el Reino Unido en formato SSRS

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Reemplazado con el nuevo formato ER: formato "Declaración de IVA en Excel (Reino Unido)" en "Modelo de declaración de impuestos".  |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: para el 1 de diciembre de 2021, planeamos dejar de admitir el "Informe VAT 100" en formato SSRS. Se introdujo un nuevo formato de "Declaración de IVA en Excel (Reino Unido)" en el "Modelo de declaración de impuestos", en la [Característica MTD IVA](../localizations/emea-gbr-mtd-vat-integration.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Características quitadas o en desuso en la versión Finance 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>La compatibilidad de Internet Explorer 11 con Dynamics 365 está en desuso

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | A partir de diciembre de 2020, queda en desuso la compatibilidad de Microsoft Internet Explorer 11 con todos los productos de Dynamics 365 e Internet Explorer 11 no se admitirá después de agosto de 2021.<br><br>Esto afectará a los clientes que usan productos Dynamics 365 que están diseñados para usarse a través de una interfaz de Internet Explorer 11. Después de agosto de 2021, Internet Explorer 11 no será compatible con dichos productos de Dynamics 365. |
| **¿Reemplazado por otra característica?**   | Recomendamos que los clientes hagan la transición a Microsoft Edge.|
| **Áreas de producto afectadas**         | Todos los productos Dynamics 365 |
| **Opción de implementación**              | Todos|
| **Estado**                         | En desuso. Internet Explorer 11 no se admitirá después de agosto de 2021.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Características quitadas o en desuso en la versión Finance 10.0.12

### <a name="not-deprecated-polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>No en desuso: Informes de SSRS polacos de registro de IVA devengado, registro de IVA soportado, registro de resumen de IVA de la UE, referencia de características PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Legalmente no requerido.  |
| **¿Reemplazado por otra característica?**   | Sí (formato Excel para el archivo de auditoría estándar con declaración de IVA - JPK_VDEK) |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir del 27 de abril de 2021 está pensado continuar soportando los informes de SSRS: **Registro de IVA devengado, Registro de IVA soportado, Registro de resumen de IVA de la UE, referencia de características PL-00014**. El ejemplo con formato Excel del archivo de auditoría estándar con declaración de IVA (JPK_VDEK) también se ha introducido. |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Características quitadas o en desuso en la versión Finance 10.0.11

### <a name="norwegian-standard-main-accounts"></a>Cuentas principales noruegas estándar

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Rediseño  |
| **¿Reemplazado por otra característica?**   | Sí (reemplazado con parámetros específicos de la aplicación en formato ER) |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: para el 1 de abril de 2021, planeamos dejar de admitir la funcionalidad relacionada con las cuentas principales estándar: campo de referencia, tabla relacionada, entidad de datos. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Características quitadas o en desuso en la versión Finance 10.0.7

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>El cuadro de diálogo de cambio de solicitud de flujo de trabajo ya no incluye la lista desplegable de selección de usuario

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Cambiado a la característica con la selección de grupos de cuentas.  |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Flujo de trabajo |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: El 1 de diciembre de 2020, planeamos dejar de admitir la configuración de tipos de asiento para China sin selección de grupos de cuentas. Para obtener más detalles sobre el nuevo diseño, consulte [Novedades en 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Anuncios anteriores sobre funciones quitadas u obsoletas
Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

