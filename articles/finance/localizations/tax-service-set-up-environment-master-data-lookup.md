---
title: Configurar un entorno para la búsqueda de datos maestros
description: Este tema explica cómo configurar su entorno para utilizar la función de búsqueda de datos maestros de cálculo de impuestos.
author: kai-cloud
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 901f8bcb0220355866952b68e92bc2dd906bb430
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2021
ms.locfileid: "7700413"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Configurar un entorno para la búsqueda de datos maestros

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar su entorno para utilizar la función de búsqueda de datos maestros de cálculo de impuestos.

1. Configure la integración de Microsoft Power Platform en Microsoft Dynamics Lifecycle Services (LCS). Para obtener más información, consulte [Integración de Microsoft Power Platform - Información general de complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Después de completar este paso, el nombre de un entorno de Microsoft Power Platform aparecerá en la sección **Integración de Power Platform**.
2. Vaya al [Centro de administración de Microsoft Power Platform](https://admin.powerplatform.microsoft.com/environments) y seleccione el nombre del entorno. Se proporciona la URL del entorno.
3. Configuración de Dynamics 365 Finance y Dataverse. Para más información, vea [Obteniendo la solución de entidad virtual](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution) y [Autenticacion y autorizacion](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
4. Configure las entidades siguientes. Para obtener más información, [Consulte las entidades virtuales de Microsoft Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

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

5. Configurar Regulatory Configuration Service (RCS). Abra el espacio de trabajo **Administración de características** y habilite las funciones siguientes:

    - Compatibilidad con orígenes de datos de Informes electrónicos de Dataverse
    - Soporte de orígenes de datos de Dataverse de servicio de impuestos
    - Características de globalización

6. Inicie sesión en RCS con una cuenta de administrador de inquilinos.
7. Ir a **Informes electrónicos** > **Aplicaciones conectadas**. 
8. Seleccione **Nuevo** para agregar un registro e ingrese la siguiente información de campo. 

    - Escriba un nombre en el campo **Nombre**.
    - En el campo **Tipo**, seleccione **Dataverse**.
    - En el campo **Aplicación**, introduzca la URL de Dataverse.
    - En el campo **Inquilino**, ingrese su inquilino.
    - En el campo **URL personalizada**, ingrese su URL de Dataverse y adjúntela con "/api/data/v9.1".

9. Seleccione **Verificar la conexión** y finalice el proceso de conexión. 

    [![Compruebe el botón de conexión.](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

10. Ir a **Informes electrónicos** > **Configuraciones de impuestos** e importar configuraciones de impuestos desde [Configuraciones de impuestos](https://go.microsoft.com/fwlink/?linkid=2158352).

    [![Página de configuraciones de impuestos, árbol del modelo de datos de impuestos.](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

11. Ve a **Mapeo del modelo de documento imponible** o **Mapeo de modelos de Dataverse** si está utilizando una configuración de Microsoft y, en el campo **Aplicación conectada**, seleccione el registro que creó en el paso 7.
12. Establezca **Predeterminado para la asignación de modelo** en **Sí**.

    [![Página de asignación de modelos.](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
