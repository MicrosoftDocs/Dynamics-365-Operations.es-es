---
title: Características quitadas u obsoletas de Dynamics 365 Finance
description: En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Finance.
author: roschlom
ms.date: 04/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: e0db5c35e58ab7a7cbf31642072d25ee5d8ba868
ms.sourcegitcommit: 04817103dc8e87a679d371575927284b8ce080b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2021
ms.locfileid: "5898296"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Características quitadas u obsoletas de Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Finance.

- Una función *quitada* dejará de estar disponible en el producto.
- Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación. 

> [!NOTE]
> La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](/dynamics/s-e/global/axtechrefrep_61). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Características quitadas o en desuso en la versión Finance 10.0.20

### <a name="rtir-query-invoice-data-request-hu-format-configuration"></a>Configuración de formato de solicitud de datos de factura (HU) de consulta RTIR

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Excluido del procesamiento de mensajes electrónicos de interoperación con el sistema de facturación en línea de Hungría |
| **¿Reemplazado por otra característica?**   | N.º |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: para el 15 de abril de 2022, planeamos dejar de admitir la configuración del formato "Solicitud de datos de facturas (HU) de consulta RTIR". |


## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Características quitadas o en desuso en la versión Finance 10.0.17

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>Repositorio LCS como opción de almacenamiento para configuraciones de informes electrónicos

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Reemplazado con el nuevo repositorio global del Servicio de configuración regulatoria (RCS) |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Dynamics 365 Finance, Supply Chain Management y productos de Project Operations|
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: para el 1 de abril de 2022, planeamos dejar de ofrecer soporte al repositorio de Microsoft Dynamics Lifecycle Services (LCS) como opción de almacenamiento para configuraciones de informes electrónicos (ER). Las nuevas configuraciones de Microsoft ER se publicarán para su descarga exclusivamente desde el repositorio global. Se puede acceder al repositorio global desde los productos Dynamics 365 y RCS. Para obtener más información, consulte [Importar configuraciones de ER desde RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md). |

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

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Informes de SSRS polacos: registro de IVA diferido, registro de IVA soportado, registro de resumen de IVA de la UE - Referencia de características PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Legalmente no requerido.  |
| **¿Reemplazado por otra característica?**   | Sí (formato Excel para el archivo de auditoría estándar con declaración de IVA - JPK_VDEK) |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: está previsto que el 1 de julio de 2021 se retiren los informes de SSRS: **Registro de IVA diferido, Registro de IVA soportado, Registro de resumen de IVA de la UE - Referencia de características PL-00014**. En su lugar se incluirá el ejemplo con formato Excel del archivo de auditoría estándar con declaración de IVA (JPK_VDEK). |

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
