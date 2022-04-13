---
title: Características quitadas u obsoletas de Dynamics 365 Finance
description: En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Finance.
author: kfend
ms.date: 03/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 6df84e5c2d530e708560495bceaeb23e2ee0dd4b
ms.sourcegitcommit: acac5e59be7c8f4e9a7ae9be58c636c70342e784
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8466845"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Características quitadas u obsoletas de Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Finance.

- Una función *quitada* dejará de estar disponible en el producto.
- Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación. 

> [!NOTE]
> La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](/dynamics/s-e/global/axtechrefrep_61). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.

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

### <a name="elster-declaration-for-germany-design-based-on-reporting-codes"></a>Declaración ELSTER para Alemania (diseño basado en códigos de notificación)

[Declaración de IVA](../localizations/emea-de-vat-declaration.md)</br>
[Configuración de la declaración de impuestos electrónica para Alemania](../../fin-ops-core/dev-itpro/analytics/tasks/setup-electronic-tax-declaration-germany.md)</br>
[Transmisión electrónica de la declaración de IVA (ELSTER)](../localizations/tasks/de-00003-electronic-transmission-elster.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Sustituido por un nuevo diseño de declaración del IVA, [Declaración de IVA para Alemania](../localizations/emea-deu-vat-declaration-germany.md) |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: para el 1 de diciembre de 2022, tenemos previsto dejar de admitir los formatos de informes electrónicos (ER) **Elster (DE)** y **Modelo Elster**. Se introducen los nuevos formatos **XML de declaración de IVA (DE)** y **Excel de declaración de IVA (DE)** en el modelo **Declaración de impuestos**. |

### <a name="ob-declaration-for-netherlands-design-based-on-reporting-codes"></a>Declaración OB para los Países Bajos (diseño basado en códigos de notificación)

[Declaración OB](../localizations/emea-nl-vat-declaration.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Sustituido por un nuevo diseño de declaración del IVA, [Declaración de IVA para los Países Bajos](../localizations/emea-nl-vat-declaration-netherlands.md) |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todo |
| **Status**                         | En desuso: para el 1 de diciembre de 2022, tenemos previsto dejar de admitir los formatos de informes electrónicos (ER) **Declaración OB (NL)** y **Modelo de declaración OB**. Se introducen los nuevos formatos **XML de declaración de IVA (NL)** y **Excel de declaración de IVA (NL)** en el modelo **Declaración de impuestos**. |

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
