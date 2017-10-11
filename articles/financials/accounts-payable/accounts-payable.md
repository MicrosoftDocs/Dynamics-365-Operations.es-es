---
title: "Página principal de proveedores"
description: "Este tema proporciona una visión general de los proveedores."
author: twheeloc
manager: AnnBe
ms.date: 08/18/2017
ms.topic: index-page
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 21901
ms.assetid: 1e4c2ac4-077b-4678-8733-5cec8f6ff659
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 741166608de504512cc0ad48cb7cd4b2d50b6c80
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="accounts-payable-home-page"></a>Página principal de proveedores

[!include[banner](../includes/banner.md)]


Este tema proporciona una visión general de los proveedores. 

Puede especificar facturas de proveedor manualmente o recibirlas electrónicamente a través de una entidad de datos. Después de que las facturas se especifican o se reciben, puede revisar y aprobar las facturas mediante un diario de aprobación de facturas o la página **Factura de proveedor**. Puede usar la conciliación de facturas, las directivas de facturas de proveedor y el flujo de trabajo para automatizar el proceso de revisión de manera que las facturas que cumplan determinados criterios se aprueben automáticamente y las facturas restantes se marquen para revisión por parte de un usuario autorizado.

**Procesos empresariales**

[![Proceso empresarial](./media/AP-process.PNG)](./media/AP-process.PNG)

## <a name="set-up-accounts-payable"></a>Configurar proveedores

Establezca grupos de proveedores, proveedores, perfiles de contabilización, varias opciones de pago, parámetros relacionados con los proveedores, cargos, entregas y destinos, pagarés y otros tipos de información de Proveedores. 

[Configuración de proveedores](accounts-payable-overview.md)

[Distribuciones contables y asientos del subdiario contable para las facturas de proveedor](accounting-distributions-subledger-journal-entries-vendor-invoices.md) 

[Revalorización de divisa extranjera para clientes y proveedores](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md)

## <a name="configure-vendor-invoices"></a>Configurar las facturas de proveedor

Use Proveedores para realizar el seguimiento de las facturas y gastos de salida de los proveedores.

[Conciliación de facturas de proveedores](accounts-payable-invoice-matching.md)

[Perfiles de contabilización del proveedor](vendor-posting-profiles.md)

[Configuración de la validación de conciliación de facturas de proveedores](tasks/set-up-accounts-payable-invoice-matching-validation.md)

[Directivas de triple conciliación](three-way-matching-policies.md)

[Conciliación de facturas y pedidos de compra de empresas vinculadas](invoice-matching-intercompany-purchase-orders.md)

[Resolver las discrepancias durante la conciliación de los totales de las facturas](resolve-invoice-totals-invoice-matching-discrepancies.md)

[Cuentas de contrapartida predeterminadas para diarios de factura de proveedor y diarios de aprobación de facturas](default-offset-accounts-vendor-invoice-journals.md)

[Aprobaciones de factura móvil](mobile-invoice-approvals.md)

[Espacio de trabajo de facturación de colaboración de proveedor](vendor-portal-invoicing-workspace.md)

[Automatización de factura de proveedor](vendor-invoice-automation.md)

## <a name="configure-vendor-payments"></a>Configurar pagos de proveedor 

Asigne un tipo de pago definido por el sistema, como cheque, pago electrónico o pagaré, a cualquier método de pago definido por el usuario. Los tipos de pago son opcionales, pero son de utilidad a la hora de validar los pagos electrónicos, así como cuando desea poder determinar rápidamente el tipo de pago que se usa. 

[Espacio de trabajo de pagos de proveedor](vendor-payments-workspace.md)

[Definir cuotas de pagos a proveedores](tasks/define-vendor-payment-fees.md)

[Definir condiciones de pagos a proveedores](tasks/define-vendor-payment-terms.md)

[Visión general de pago positivo](positive-pay-overview.md)

[Configurar y generar archivos de pago positivo](set-up-generate-positive-pay-files.md)

[Creación de pagos de proveedor mediante una propuesta de pago](create-vendor-payments-payment-proposal.md)

[Pagos de proveedor para un importe parcial](vendor-payments-partial-amount.md)

[Aprovechar un descuento superior al calculado para un pago de proveedor](take-discount-more-calculated-discount-vendor-payment.md)

[Obtener un descuento por pronto pago fuera del período de descuento por pronto pago](take-cash-discount-outside-cash-discount-timeframe.md)

[Informes electrónicos para cheques de proveedor](electronic-reporting-sample-vendor-checks.md)

[Inversión de un pago de proveedor](reverse-vendor-payment.md)

[Facturas de anticipo y visión general de anticipos](prepayments-invoices-vs-prepayments.md)

[Pagos centralizados para proveedores](centralized-payments-accounts-payable.md)

## <a name="settlements"></a>Liquidaciones

En los temas siguientes se proporciona información acerca de las liquidaciones. La liquidación es el proceso de liquidar pagos con facturas. 

[Configurar liquidación](../cash-bank-management/configure-settlement.md)

[Establecer un pago parcial de proveedor antes de la fecha de descuento](settle-partial-vendor-payment-before-discount-or-final-payment-after.md)

[Liquidar un pago de proveedor parcial con descuentos en notas de abono de proveedor](settle-partial-vendor-payment-discounts-vendor-credit-notes.md)

[Liquidar un pago de proveedor parcial con varios períodos de descuento](settle-partial-vendor-payment-multiple-discount-periods.md)

[Establecer un pago parcial de proveedor o un pago final antes del descuento](settle-partial-vendor-payment-or-final-payment-before-discount.md)

[Asiento único con varios registros de cliente o proveedor](single-voucher-multiple-customer-vendor-records.md)



### <a name="additional-resources"></a>Recursos adicionales

#### <a name="whats-new-and-in-development"></a>Novedades y características en desarrollo

Consulte [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) (Guía básica de Microsoft Dynamics 365) para ver qué características nuevas hemos lanzado y cuáles están en desarrollo. 

#### <a name="blogs"></a>Blogs

Puede encontrar opiniones, noticias y otra información sobre Proveedores y otras soluciones en el [blog Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).

Hay muchas publicaciones sobre Proveedores en el [blog del equipo del producto Microsoft Dynamics AX](https://blogs.msdn.microsoft.com/dax/). Aunque la mayoría de ellos se escribieron para la versión anterior de Proveedores, aún se aplican los mismos conceptos y, en la versión actual, los procedimientos son también similares.

El [blog de la comunidad Microsoft Dynamics Operations Partner](https://community.dynamics.com/partner/b/operationspartnercommunityblog) proporciona a los socios de Microsoft Dynamics un único recurso desde el que obtener información sobre las novedades y tendencias de MBS Operations.

#### <a name="task-guides"></a>Guías de tareas
Hay ayuda adicional disponible como guías de tareas en Finance and Operations. Para tener acceso a las guías de tareas, haga clic en el botón Ayuda en cualquier página.

#### <a name="videos"></a>Vídeos

Consulte los vídeos de procedimientos que se encuentran ahora disponibles en el [canal de YouTube de Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).




