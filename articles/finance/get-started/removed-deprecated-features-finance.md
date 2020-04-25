---
title: Características quitadas u obsoletas de Dynamics 365 Finance
description: En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: aebce032d7d780b296ba74fea4467425a3cbe1a7
ms.sourcegitcommit: 4e9b3746790355f9f72bbfddc099c4065a49ad63
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "3175117"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Características quitadas u obsoletas de Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Finance.

- Una función *quitada* dejará de estar disponible en el producto.
- Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación. 

> [!NOTE]
> La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Características quitadas o en desuso en la versión Finance 10.0.12

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Informes de SSRS polacos: registro de IVA diferido, registro de IVA soportado, registro de resumen de IVA de la UE - Referencia de características PL-00014

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Legalmente no requerido.  |
| **¿Reemplazado por otra característica?**   | Sí (formato Excel para el archivo de auditoría estándar con declaración de IVA - JPK_VDEK) |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: está previsto que el 1 de julio de 2021 se retiren los informes de SSRS: **Registro de IVA diferido, Registro de IVA soportado, Registro de resumen de IVA de la UE - Referencia de características PL-00014**. En su lugar se incluirá el ejemplo con formato Excel del archivo de auditoría estándar con declaración de IVA (JPK_VDEK). |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Características quitadas o en desuso en la versión Finance 10.0.11

### <a name="norwegian-standard-main-accounts"></a>Cuentas principales noruegas estándar

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Rediseño  |
| **¿Reemplazado por otra característica?**   | Sí (reemplazado con parámetros específicos de la aplicación en formato ER) |
| **Áreas de producto afectadas**         | Solicitud |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: para el 1 de abril de 2021, planeamos dejar de admitir la funcionalidad relacionada con las cuentas principales estándar: campo de referencia, tabla relacionada, entidad de datos. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Características quitadas o en desuso en la versión Finance 10.0.7

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>El cuadro de diálogo de cambio de solicitud de flujo de trabajo ya no incluye la lista desplegable de selección de usuario
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Cambiado a la característica con la selección de grupos de cuentas.  |
| **¿Reemplazado por otra característica?**   | Sí |
| **Áreas de producto afectadas**         | Flujo de trabajo |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: El 1 de diciembre de 2020, planeamos dejar de admitir la configuración de tipos de asiento para China sin selección de grupos de cuentas. Para obtener más detalles sobre el nuevo diseño, consulte [Novedades en 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Anuncios anteriores sobre funciones quitadas u obsoletas
Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).
