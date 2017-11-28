---
title: Configurar pagos centralizados
description: "Siga estos pasos para preparar el procesamiento de pagos de una entidad jurídica en nombre de otras entidades jurídicas de la organización."
author: kweekley
manager: AnnBe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 62243
ms.assetid: ffd17b5f-9aea-40e0-be49-d8702f615256
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2e309655bbc1d0fe7a088062b90fab34c642ab29
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-centralized-payments"></a>Configurar pagos centralizados

[!include[banner](../includes/banner.md)]


Siga estos pasos para preparar el procesamiento de pagos de una entidad jurídica en nombre de otras entidades jurídicas de la organización. Antes de comenzar, se deberán completar los siguientes procedimientos de configuración:

-   Crear entidades jurídicas.
-   Configurar Parámetros de Contabilidad general y plan de cuentas.
-   Configurar parámetros de Proveedores y parámetros de Clientes (en función de los módulos que usan pagos centralizados).
-   Configurar la contabilidad de empresas vinculadas.

## <a name="set-up-an-organizational-hierarchy-for-centralized-payments"></a>Configurar jerarquías organizativas para pagos centralizados
Es necesario configurar una jerarquía organizativa para los pagos centralizados. Dicha jerarquía se usará para procesar los pagos de proveedor y de cliente centralizados. **Nota:** Para los pagos centralizados, la estructura de la jerarquía no es relevante. Cualquier entidad jurídica de la jerarquía podrá procesar pagos en nombre de cualquier otra entidad jurídica de la jerarquía. En la página **Jerarquías organizativas**, puede crear una nueva jerarquía organizativa. En el campo **Propósito** debe seleccionar **Pagos centralizados**. 

## <a name="set-up-an-intercompany-account-for-centralized-payments"></a>Configuración de una cuenta de empresas vinculadas para pagos centralizados
Cuando las transacciones de pago de la entidad jurídica actual se liquidan con facturas de otras entidades jurídicas, se crean para cada entidad jurídica las transacciones de destinatario de pago y de remitente de pago correspondientes. Debe especificar la entidad jurídica en la que se registran los descuentos por pronto pago y los importes de pérdidas o beneficios realizados. Antes de empezar, decida qué entidad jurídica usará para procesar los pagos de proveedor y cliente. Si una entidad jurídica procesa los pagos de proveedor pero otra entidad jurídica procesa los pagos de cliente, tendrá que cambiar a cada entidad jurídica. En la página **Contabilidad de empresas vinculadas** puede seleccionar un registro de relaciones de empresas vinculadas para la entidad jurídica en cuyo nombre va a procesar los pagos. 

En la pestaña **Pagos centralizados** puede seleccionar si se deben registrar descuentos por pronto pago en la entidad jurídica de pago (u otra transacción que disminuya el saldo de la cuenta de proveedor) o la de la facturación (u otra transacción que incremente el saldo de la cuenta de proveedor). Esta selección funciona junto con el campo **Administración del descuento por pronto pago** en las páginas **Parámetros de proveedores** y **Parámetros de clientes**. Para las tolerancias de sobrepago y de diferencias de decimales, se usa la configuración de la entidad jurídica de pago. Para las tolerancias de pagos insuficientes y diferencias de decimales, se usa la configuración de la entidad jurídica de facturación.

## <a name="map-vendor-accounts-across-legal-entities"></a>Asignación de cuentas de proveedor entre entidades jurídicas
Si paga a un proveedor de una entidad jurídica y desea seleccionar facturas de ese proveedor en otras entidades jurídicas, deberá asegurarse de que todas las cuentas de proveedor correspondientes de cada entidad jurídica usen el mismo identificador de libreta de direcciones. Si recibe un pago de un cliente que paga facturas en más de una entidad jurídica, deberá asegurarse de que todas las cuentas de cliente correspondientes de cada entidad jurídica utilizan todas el mismo identificador de libreta de direcciones.

## <a name="set-up-posting-profiles-for-centralized-payments"></a>Configuración de perfiles de registro para pagos centralizados
Al crear un pago en una entidad jurídica que liquida facturas de otras entidades jurídicas, los identificadores del perfil de contabilización de ambas entidades jurídicas deben coincidir. Para ayudar a garantizar que los pagos se creen correctamente, en cada entidad jurídica de la factura, configure un perfil de contabilización que se corresponda con los perfiles de contabilización que se usan en la entidad jurídica de pago. Cambie a la primera entidad jurídica de la factura y, a continuación, en la página **Perfiles de contabilización del proveedor**, puede crear un nuevo perfil de contabilización o editar un perfil de contabilización existente. No es necesario que las opciones seleccionadas para el perfil de contabilización de la entidad jurídica de facturación coincidan con la configuración del perfil de contabilización en la entidad jurídica de pago.

## <a name="set-up-methods-of-payment-for-centralized-payments"></a>Configurar métodos de pago para pagos centralizados
Al crear un pago en una entidad jurídica que liquida facturas de otras entidades jurídicas, los identificadores de forma de pago de ambas entidades jurídicas deben coincidir. Para ayudar a garantizar que los pagos se creen correctamente, en cada entidad jurídica de la factura, configure una forma de pago en cada entidad jurídica de facturación que se corresponda con las formas de pago que se usan en la entidad jurídica de pago. Cambie a la primera entidad jurídica de la factura y, a continuación, en la página **Métodos de pago**, puede crear un nuevo método de pago o editar un método existente de pago. No es necesario que las selecciones que realice para la forma de pago de la entidad jurídica de facturación coincidan con la configuración de la forma de pago de la entidad jurídica de pago.

## <a name="set-up-default-descriptions"></a>Configurar descripciones predeterminadas
Se pueden definir descripciones predeterminadas para los asientos de liquidación de empresas vinculadas. La descripción predeterminada se incluye en las transacciones de inicio y fin de vencimiento durante el proceso de liquidación entre empresas. En la página **Descripciones Predeterminadas**, puede crear nuevas descripciones tanto para **Liquidación de cliente de empresas vinculadas** como para **Liquidación de proveedor de empresas vinculadas** seleccionando un idioma y después especificando el texto.




