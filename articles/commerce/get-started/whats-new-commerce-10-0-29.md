---
title: Versión preliminar de Dynamics 365 Commerce 10.0.29 (octubre de 2022)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Commerce 10.0.29.
author: josaw1
ms.date: 08/02/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c1f85fcd8f79106a3af93489d3bef608b9840bf3
ms.sourcegitcommit: 91f58a9863f4e8f30ac787c2a9771c1ff6a05f72
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224248"
---
# <a name="preview-of-dynamics-365-commerce-10029-october-2022"></a>Versión preliminar de Dynamics 365 Commerce 10.0.29 (octubre de 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este artículo se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Commerce versión de vista previa 10.0.29. Esta versión tiene el número de compilación 10.0.1326 y está disponible con la siguiente programación:

- **Versión preliminar de la versión:** agosto de 2022
- **Disponibilidad general de la versión (actualización automática):** septiembre de 2022
- **Disponibilidad general de la versión (actualización automática):** octubre de 2022

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. Puede que haya actualizaciones de este artículo para incluir características que se agregaron a la compilación después de la publicación original del artículo.

| Área de características | Característica | Más información | Habilitada por   |
|---------|------------------|----------------|--------------| 
| B2B | [Habilitar la compatibilidad con el acuerdo de venta entre canales](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-b2b-sales-agreement-contract-based-pricing) | Esta función permite a las organizaciones de vendedores de empresa a empresa (B2B) utilizar acuerdos de venta en Commerce headquarters para definir precios basados en contratos para sus compradores. Cuando un comprador B2B compra en el sitio web de comercio electrónico, el precio basado en el contrato que se configura para la organización del comprador B2B se aplica automáticamente a toda la experiencia de descubrimiento, compra y pago del producto. | Administración de características<p>*Compatibilidad con el acuerdo de venta entre canales comerciales* |
| Customer Service | [Habilitar el servicio al cliente con Dynamics 365 Omnichannel for Customer Service](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/chat-dynamics-365-commerce-omnichannel-customer-service) | Una experiencia de soporte al cliente de primera clase es clave para brindar una experiencia comercial personalizada y placentera para los consumidores. Actualmente existen múltiples puntos de contacto de comercio, como tiendas físicas, canales en línea y canales sociales. Los consumidores esperan una experiencia de soporte personalizada en todos estos puntos de contacto. Esta característica lo ayuda a aumentar las conversiones de carritos en ventas, aumentar el compromiso personalizado con los consumidores y mejorar el servicio al cliente mediante la integración con Dynamics 365 Omnichannel for Customer Service. | Habilitado por administradores/fabricantes |
| Comercio electrónico | Soporte para la comparación de productos en el comercio electrónico | Permita que los compradores comparen productos en una amplia gama de categorías para que puedan tomar la decisión de compra correcta por sí mismos. Esta función está disponible tanto para sitios de empresa a consumidor (B2C) como B2B. | Generador de sitios | 
| Tarjetas regalo | Compatibilidad con tablas de tarjetas de regalo minoristas para compartir datos entre empresas | La sede central de Dynamics admite la capacidad de habilitar el uso compartido de datos entre empresas para tablas específicas en la arquitectura de Dynamics. En esta característica, Dynamics 365 Commerce agrega compatibilidad con tablas de tarjetas de regalo minoristas para compartir datos entre empresas. Por lo tanto, una tarjeta de regalo en una empresa ahora puede tener sus datos duplicados en otra empresa del entorno. Los cambios realizados en la tabla de tarjetas de regalo de la empresa de origen se compartirán con la tabla de tarjetas de regalo de la empresa duplicada. | Desarrolladores |
| Rendimiento | Eliminar la dependencia de RTS para escenarios de "editar cliente" | La alta disponibilidad y el alto rendimiento son expectativas predeterminadas para el punto de venta (POS) y los canales de comercio electrónico. Para ayudar a cumplir con estas expectativas, los canales de Dynamics 365 Commerce ya no tienen que depender de la comunicación en tiempo real con Commerce headquarters cuando se edita la información del cliente. La capacidad de editar la información del cliente de forma asíncrona para clientes asíncronos y no asíncronos puede ayudar a reducir las llamadas en tiempo real a Commerce headquarters. | Habilitado por administradores/fabricantes |

## <a name="feature-state-changes-in-this-release"></a>Cambios de estado de características en esta versión

La tabla siguiente enumera las características que se han convertido en obligatorias o activadas de forma predeterminada en la versión 10.0.29. Todas estas funciones se activarán automáticamente para su sistema tan pronto como actualice a la versión 10.0.29. Las funciones obligatorias no se pueden desactivar, pero las funciones que están activadas de forma predeterminada aún se pueden desactivar usando [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

La tabla también enumera las funciones que anteriormente estaban en versión preliminar pública, pero que cambiaron para estar disponibles de forma general en la versión 10.0.29. Este cambio indica que las funciones ahora se recomiendan para su uso en entornos de producción. Estas funciones están desactivadas de forma predeterminada a menos que se indique lo contrario. Por lo tanto, debe utilizar [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitarlas si desea usarlas.

| Característica | Título | Nuevo estado de la característica |
| --- | --- | --- |
| BrazilRetailLocalizationFeature_BR |(Brasil) Funcionalidad de Commerce específica de Brasil | Activado de forma predeterminada |
| RetailAdvancedGTETaxAdjustmentFeature | (India) Aplicar el GST calculado para transacciones comerciales en extractos comerciales de Retail POS | Activado de forma predeterminada |
| RetailChronologicalInvoicePostingFeature_IT | (Italia) Habilitar el registro de facturas minoristas sin orden cronológico | Activado de forma predeterminada |
| RetailDiscountWithoutTaxAdjustingFeature_MX | (México) Ajuste del descuento en el CFDI global para minoristas | Activado de forma predeterminada |
| RetailFiscalIntegrationConfigurationEnhancementFeature | Anulaciones de perfiles técnicos de integración fiscal | Activado de forma predeterminada |
| RetailFiscalIntegrationConnectorLocationFeature | Integración fiscal directa desde los registros de PDV | Activado de forma predeterminada |
| RetailFiscalIntegrationLocalStorageBackupEnableFeature | Copia de seguridad del almacenamiento de datos local | Activado de forma predeterminada |
| RetailFiscalIntegrationPostponeFiscalRegistrationFeature | Registro de documentos pospuesto | Activado de forma predeterminada |
| RetailFiscalIntegrationRegistrationProcessTerminalExceptionFeature | Estado de registro fiscal de los registros de PDV | Activado de forma predeterminada |
| RetailGSTInvoiceAddressTaxCalculationFeature_IN | (India) Calcular el GST en función de la dirección de la factura para los pedidos de comercio electrónico | Activado de forma predeterminada |
| RetailInvoicesDefaultSalesDocumentStatusFeature_PL | (Polonia) Estado de documento de ventas predeterminado para facturas comerciales | Activado de forma predeterminada |
| RetailRecalculateRoundingOfTaxBaseAmountsFeature_MX | (México) Nuevo cálculo de redondeo para importes base de impuestos en global CFDI de Retail. | Activado de forma predeterminada |
| RetailSupplementaryInvoiceFeature | Habilitar facturas adicionales para transacciones de pago al contado sin entrega a domicilio completadas en tiendas | Activado de forma predeterminada |
| RetailInventoryBufferAndInventoryLevelEnableFeature   |  Habilitar búferes de inventario y niveles de inventario    |  Activado de forma predeterminada|
|RetailInboundOutboundInventoryValidationFeature|   Habilitar validación en operación de inventario de entrada y salida de PDV   |   Activado de forma predeterminada   |
|  RetailInventoryChannelCalculationConsolidationFeature    |  Lógica mejorada de cálculo de inventario del canal de comercio electrónico |   Activado de forma predeterminada   |
|RetailInventoryAdjustmentsInPointOfSaleFeature|    Ajustes de inventario en punto de venta   |  Activado de forma predeterminada  |
| RetailMultiplePickupDeliveryModeFeature |  Soporte para varios modos de entrega de recogida     |   Obligatoria    |
|  RetailProductAvailabilityOptimizationFeature |   Cálculo de disponibilidad de producto optimizado  |  Obligatoria |
|   RetailPricingDataManagerV2Feature   |   Mejorar el rendimiento del motor de precios de Commerce |   Obligatoria |
|  RetailPricingPreventUnintendedRecalculationFeature   | Evitar el cálculo de precios no intencionado para pedidos de comercio    |  Obligatoria  |
| RetailTeamsIntegration    |   Habilitar la integración de Microsoft Teams| Obligatoria   |  
| ConsumerEFDSyncProcessFeature_BR | Procesamiento sincrónico NFC-e (Brasil) | Activado de forma predeterminada |
| RetailFiscalIntegrationInternalAndExternalServicesEnableFeature | Soporte para conectores internos y externos en el marco de integración fiscal | Obligatoria |
| RetailTaxRegistrationIdEnableFeature_BR | (Brasil) Buscar clientes en Retail POS por números de registro de impuestos | Obligatoria |
| RetailTaxRegistrationIdEnableFeature_IN | (India) Buscar clientes en Retail POS por números de registro de impuestos | Obligatoria |
| RetailTaxRegistrationIdEnableFeature_IT | (Italia) Administración de información de clientes en Retail POS | Obligatoria |
| RetailTaxRegistrationIdEnableFeature_PL | (Polonia) Gestión de información de cliente en Retail POS | Obligatoria |
| RetailUpdateReturnOriginalTransactionIdGlobalEnableFeature_IN | (GST de productos minoristas de la India) Actualizar notas de abono con referencias a las facturas originales | Obligatoria |
| RetailUserDefinedCertificateProfileFeature | Perfiles de certificado definidos por el usuario para tiendas | Obligatoria |
  

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform update para aplicaciones de Finanzas y Operaciones

Microsoft Dynamics 365 Commerce 10.0.29 incluye Platform updates. Para obtener más información, consulte [Platform updates para la versión 10.0.29 de aplicaciones de Finanzas y Operaciones (octubre de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md). 

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.29, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559&dbType=3&qc=ec3e3846199f5d3a27a0c4949e3902ffdbc87560f0cf928c4838b3bdd421633c). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2022

¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2022](/dynamics365-release-plan/2022wave2/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-features"></a>Características quitadas y obsoletas

El artículo [Funciones eliminadas o obsoletas en Dynamics 365 Commerce](removed-deprecated-features-commerce.md) describe las características que se han eliminado o están obsoletas para Commerce.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el artículo [Características quitadas o en desuso en Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 meses antes de su eliminación.

Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
