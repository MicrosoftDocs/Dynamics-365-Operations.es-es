---
title: Configurar un entorno para la búsqueda de datos maestros
description: Este tema explica cómo configurar su entorno para utilizar la función de búsqueda de datos maestros de cálculo de impuestos.
author: kai-cloud
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9f9b385df1db60b27698d90281c43fabb574af49
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924163"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Configurar un entorno para la búsqueda de datos maestros

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar su entorno para utilizar la función de búsqueda de datos maestros de cálculo de impuestos.

1. Configure la integración de Power Platform en Lifecycle Services (LCS). Para obtener más información, consulte [Integración de Microsoft Power Platform - Información general de complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
2. Configuración de Dynamics 365 Finance y Microsoft Dataverse. Para más información, vea [Obteniendo la solución](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) y [Autenticacion y autorizacion](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
3. Configure las entidades siguientes. Para obtener más información, consulte [Habilitar entidades virtuales](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#enabling-virtual-entities).
      - CompanyInfoEntity
      - CurrencyEntity
      - CustCustomerV3Entity
      - DeliveryTermsEntity
      - EcoResProductCategoryEntity
      - EcoResReleasedProductV2Entity
      - LogisticsAddressCityEntity
      - LogisticsAddressCountryRegionTranslationEntity
      - LogisticsAddressStateEntity
      - PurchProcurementChargeCDSEntity
      - SalesChargeCDSEntity
      - TaxGroupEntity
      - TaxItemGroupHeadingEntity
      - VendVendorV2Entity
4. Configure Regulatory Configuration Service (RCS) de Dynamics 365. 
5. Cree una solicitud de servicio para que Microsoft habilite la distribución de las siguientes características:

      - ERCdsFeature
      - TaxServiceCDSFeature

6. Vaya al espacio de trabajo **Administración de funciones** y habilite las funciones siguientes:

      - (Vista previa) Compatibilidad con orígenes de datos de Informes electrónicos de Dataverse
      - (Versión preliminar) Soporte para orígenes de datos de Dataverse del servicio de impuestos
      - Características de globalización (vista previa)

5. Inicie sesión en RCS con una cuenta de administrador de inquilinos.
6. Ir a **Informes electrónicos** > **Aplicaciones conectadas**. 
7. Seleccione **Nuevo** para agregar un registro e ingrese la siguiente información de campo. 

   - Escriba un nombre en el campo **Nombre**.
   - En el campo **Tipo**, seleccione **Dataverse**.
   - En el campo **Aplicación**, introduzca la URL de Dataverse.
   - En el campo **Inquilino**, ingrese su inquilino.
   - En el campo **URL personalizada**, ingrese su URL de Dataverse y adjúntela con "/api/data/v9.1".

8. Seleccione **Verificar la conexión** y finalice el proceso de conexión. 

   [![Compruebe el botón de conexión](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

9. Ir a **Informes electrónicos** > **Configuraciones de impuestos** e importar configuraciones de impuestos desde [Configuraciones de impuestos](https://go.microsoft.com/fwlink/?linkid=2158352).

   [![Página de configuraciones de impuestos, árbol del modelo de datos de impuestos](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

10. Ve a **Mapeo del modelo de documento imponible** o **Mapeo de modelos de Dataverse** si está utilizando una configuración de Microsoft y, en el campo **Aplicación conectada**, seleccione el registro que creó en el paso 7.
11. Establezca **Predeterminado para la asignación de modelo** en **Sí**.

   [![Página de asignación de modelos](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
