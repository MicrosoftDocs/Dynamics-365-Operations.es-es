---
title: Información general de la configuración de proveedores
description: Este tema describe las páginas que usa para configurar la funcionalidad básica y opcional para Proveedores. También describen los pasos de configuración que debe completar antes de comenzar a configurar Proveedores.
author: abruer
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable, DeliveryReason, DeliveryTerms, DestinationCode
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "24671"
- intro-internal
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6cbc800d7ae4d566fddb111b7ee9d67234e3cf8c
ms.sourcegitcommit: 43d0555c17a0643c9e5ba3bc2da3ce5f80754642
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2022
ms.locfileid: "8326003"
---
# <a name="configure-accounts-payable-overview"></a>Visión general de la configuración de proveedores

[!include [banner](../includes/banner.md)]

Este artículo describe las páginas que usa para configurar la funcionalidad básica y opcional para Proveedores. También describen los pasos de configuración que debe completar antes de comenzar a configurar Proveedores.

## <a name="prerequisites-for-accounts-payable-setup"></a>Requisitos previos para la configuración de proveedores

Para poder configurar los proveedores, debe completar la configuración siguiente:

-   En contabilidad general:
    -   Si pretende usar diarios de pagos, debe configurarlos.
    -   Si pretende ejecutar ajustes del tipo de cambio, configure los códigos de divisa en la página de **Divisas**, los tipos de cambio en la página de **Tipos de cambio** y los tipos de cambio de divisa puesto en la página de **Tipos de cambio de divisa**.
-   En Gestión de efectivo y bancos, configure cuentas bancarias para usarlas con formas de pago.

## <a name="setup-pages-for-accounts-payable"></a>Configurar páginas para proveedores

Utilice las páginas siguientes para configurar la funcionalidad básica de Proveedores para cada entidad jurídica. Las páginas se enumeran en el orden de configuración recomendado. Para simplificar el proceso de configuración, puede crear plantillas a partir de los primeros registros que cree. En una plantilla, normalmente suelen introducirse valores en muchos campos para reflejar las características que la organización desea implantar para un tipo concreto de proveedor.
1.  En la página de **términos de pago**, defina las condiciones de pago que va a asignar a los pedidos de ventas, pedidos de compra, clientes y proveedores, que determinan las fechas de vencimiento de las facturas. Para obtener más información, consulte [Definir tarifas de pago del proveedor](tasks/define-vendor-payment-fees.md).
2.  En la página **Métodos de pago - Proveedor**, cree y mantenga la información sobre cómo paga la organización a sus proveedores.
3.  En la página de **grupos de proveedores**, cree y mantenga grupos de proveedores que comparten los principales parámetros para el registro, liquidación y pago, informes y previsiones.
4.  En la página de **perfiles de contabilización de proveedores**, defina cómo se registran las transacciones del proveedor en la contabilidad general.
5.  En la página de **parámetros de proveedores**, configure los parámetros predeterminados que se aplican si no se especifica una configuración más concreta, parámetros para varios tipos de funciones y varias secuencias numéricas para proveedores.
6.  En la página de **configuración de formulario**, defina el formato de varios documentos relacionados con proveedores y que la organización usa para realizar un seguimiento de las recepciones de los proveedores y para indicar motivos del flujo de pagos a los proveedores.
7.  En la página **Proveedores**, cree y mantenga las cuentas de proveedor y también las de autoridades fiscales a las que su organización paga impuestos.

## <a name="optional-setup-pages-for-accounts-payable"></a>Páginas de configuración opcionales de proveedores
Además de la funcionalidad básica, los proveedores tienen otra funcionalidad que puede configurar.

Las páginas de configuración adicionales están organizadas por funciones.

**Directivas**
-   En la página de la **directiva de facturas de proveedor**, configure las directivas de facturas de proveedor.

**Conciliación de facturas**

-   En la página de **tolerancias de totales de facturas**, configure las tolerancias para los totales de factura.
-   En la página de **directiva de conciliación**, configure directivas de triple y doble conciliación.
-   En la página de **tolerancias de precios**, configure las tolerancias para los precios por unidad.
-   En la página de grupos de **tolerancias para los precios de artículos**, configure grupos de tolerancia para los precios de artículos.
-   En la página de **grupos de tolerancias para los precios de proveedor**, configure grupos de tolerancia para los precios de proveedor.
-   En la página de **tolerancias de gastos**, configure las tolerancias para gastos.

**Flujo de trabajo**

-   En la página de **flujos de trabajo de proveedores**, configure los parámetros de flujos de trabajo para las aprobaciones del diario y las solicitudes de compra.

**Motivos**

-   En la página de **motivos de proveedor**, configure los códigos de motivo.

**Gastos**

-   En la página de **código de gastos**, configure los códigos para los gastos que se usan en los pedidos de compra.
-   En la página de **grupo de gastos del proveedor**, cree y mantenga grupos de gastos para los proveedores.
-   En la página de **grupos de gastos de artículos**, cree y mantenga grupos de gastos para los artículos.
-   En la página de **gastos automáticos**, defina los gastos que se asignan automáticamente a pedidos.

**Artículos adicionales**

-   En la página **Grupos de artículos adicionales - Proveedor**, cree y mantenga grupos de artículos adicionales para proveedores.
-   En la página **Grupos de artículos adicionales - Inventario**, cree y mantenga grupos de artículos adicionales para artículos.

**Distribución**

-   En la página de **condiciones de entrega**, cree y mantenga las condiciones de la transferencia de artículos de vendedor a comprador.
-   En la página de **modos de entrega**, cree y mantenga los métodos de transporte que se usan cuando un pedido se entrega del vendedor al comprador.
-   En la página de **códigos de destino**, cree y mantenga los identificadores y las descripciones de los destinos de entrega.

**Formularios**

-   En la página de **notas de formulario**, cree el texto estándar que aparece en varias páginas.
-   En la página de **parámetros de ordenación del formulario**, configure el orden de clasificación para solicitudes, listas de recepciones, albaranes y facturas.
-   En función de la página **configuración de la gestión de impresión**, configure la información de la gestión de impresión para originales y copias de páginas.

**Pagos**

-   En la página **descuentos por pronto pago**, configure y gestione las condiciones para obtener descuentos por pronto pago. Los códigos de descuento por pronto pago se vinculan a los proveedores y se aplican a los pedidos de compra.
-   En la página de **multivencimientos**, configure los multivencimientos que se usan para gestionar los pagos de plazo a los proveedores.
-   En la página de **días de pago**, defina los días de pago que se utilizan para calcular las fechas de vencimiento y especificar los días de pago para un día concreto de la semana o del mes.
-   En la página de **cuota de pago**, cree y mantenga las cuotas de pago asociadas con los proveedores.
-   En la página de **instrucción de pago**, cree y mantenga las instrucciones de pago.

**Estadísticas**

-   En la página de **definiciones de período de vencimiento**, configure los intervalos definidos por el usuario que se usan para analizar la distribución de vencimiento de las cuentas de proveedor.
-   En la página de **línea de negocio**, cree los códigos de línea de negocio (LOB) que se asignan a los proveedores.

**IRPF**

-   En la página de **campos de IRPF**, compruebe y actualice los importes mínimos que se deben notificar a la agencia tributaria en función de los últimos requisitos fiscales.

## <a name="optional-setup-for-other-modules"></a>**Configuración opcional para otros módulos**
**Administración de la organización**

-   En la página de **secuencias numéricas**, configure los grupos de secuencias numéricas para los números de factura.
-   En las siguientes páginas, configure la información de dirección:
    -   **Configuración de dirección**
    -   **Códigos NAF**
    -   **Importar códigos postales**

**Contabilidad general**

-   En la página **dimensiones financieras**, configure las dimensiones financieras.
-   En las páginas siguientes, configure la información de impuestos:
    -   **Códigos de impuestos**
    -   **Grupos de impuestos**
    -   **Grupos de impuestos de artículos**
    -   **Grupo de cuentas**
    -   **Códigos de exención de impuestos**
    -   **Jurisdicciones de impuestos**
    -   **Autoridades fiscales**
    -   **Períodos de liquidación de impuestos**

**Gestión de efectivo y bancos**

-   En la página de **códigos de propósito de pago**, configure el **código de propósito del banco central**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
