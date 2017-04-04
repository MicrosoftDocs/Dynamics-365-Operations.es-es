---
title: Configurar pagos centralizados
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62243
ms.assetid: ffd17b5f-9aea-40e0-be49-d8702f615256
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 44d51807cd6bb64ae2c4bef58d8a445417ffa3a9
ms.openlocfilehash: 815282422a6d7b8eef7d0628cf10b715449e1d1d
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-centralized-payments"></a>Configurar pagos centralizados



Siga estos pasos para prepararse para procesar pagos en una entidad jurídica en nombre de otras entidades jurídicas de la organización. Antes de empezar, la siguiente configuración debe estar completa:

-   Crear entidades jurídicas.
-   Configurar Parámetros de Contabilidad general y plan de cuentas.
-   Configurar parámetros de Proveedores y parámetros de Clientes (en función de los módulos que usan pagos centralizados).
-   Configurar la contabilidad de empresas vinculadas.

## <a name="set-up-an-organizational-hierarchy-for-centralized-payments"></a>Configurar jerarquías organizativas para pagos centralizados
Es necesario configurar una jerarquía organizativa para los pagos centralizados. Dicha jerarquía se usará para procesar los pagos de proveedor y de cliente centralizados. **Nota:** Para los pagos centralizados, la estructura de la jerarquía no es relevante. Cualquier entidad jurídica de la jerarquía podrá procesar pagos en nombre de cualquier otra entidad jurídica de la jerarquía. En la página **Jerarquías organizativas**, puede crear una nueva jerarquía organizativa.

## <a name="set-up-an-intercompany-account-for-centralized-payments"></a>Configuración de una cuenta de empresas vinculadas para pagos centralizados
Cuando las transacciones de pago de la entidad jurídica actual se liquidan con facturas de otras entidades jurídicas, se crean para cada entidad jurídica las transacciones de destinatario de pago y de remitente de pago correspondientes. Debe especificar la entidad jurídica en la que se registran los descuentos por pronto pago y los importes de pérdidas o beneficios realizados. Antes de empezar, decida qué entidad jurídica usará para procesar los pagos de proveedor y cliente. Si una entidad jurídica procesa los pagos de proveedor pero otra entidad jurídica procesa los pagos de cliente, tendrá que cambiar a cada entidad jurídica. En ** contabilidad de empresas vinculadas ** la página, puede seleccionar un registro de relaciones de empresas vinculadas para una entidad jurídica que va a procesar pagos en nombre de. En ** pagos centralizados ** la ficha, puede seleccionar si se deben registrar descuentos por pronto pago en la entidad jurídica de pago (u otra transacción que disminuya el saldo de la cuenta de proveedor) o a la entidad jurídica de facturación (u otra transacción que aumenta el saldo de la cuenta de proveedor). Esta selección funciona junto con el campo **Administración del descuento por pronto pago** en las páginas **Parámetros de proveedores** y **Parámetros de clientes**. Para las tolerancias de sobrepago y de diferencias de decimales, se usa la configuración de la entidad jurídica de pago. Para las tolerancias de pagos insuficientes y diferencias de decimales, se usa la configuración de la entidad jurídica de facturación.

## <a name="map-vendor-accounts-across-legal-entities"></a>Asignación de cuentas de proveedor entre entidades jurídicas
Si paga a un proveedor de una entidad jurídica y desea seleccionar facturas de ese proveedor en otras entidades jurídicas, deberá asegurarse de que todas las cuentas de proveedor correspondientes de cada entidad jurídica usen el mismo identificador de libreta de direcciones. Si recibe un pago de un cliente que paga facturas en más de una entidad jurídica, deberá asegurarse de que todas las cuentas de cliente correspondientes de cada entidad jurídica utilizan todas el mismo identificador de libreta de direcciones.

## <a name="set-up-posting-profiles-for-centralized-payments"></a>Configuración de perfiles de registro para pagos centralizados
Al crear un pago en una entidad jurídica que liquida facturas de otras entidades jurídicas, los identificadores del perfil de contabilización de ambas entidades jurídicas deben coincidir. Para ayudar a garantizar que los pagos se creen correctamente, en cada entidad jurídica de la factura, configure un perfil de contabilización que se corresponda con los perfiles de contabilización que se usan en la entidad jurídica de pago. Cambie a la primera entidad jurídica de facturación y, a continuación, en ** los perfiles de registro de proveedor ** la página, puede crear un nuevo perfil de contabilización o editar un perfil de registro existente. Las selecciones que cree para el perfil de contabilización de la entidad jurídica de facturación coincidan con la configuración del perfil de contabilización de la entidad jurídica de pago.

## <a name="set-up-methods-of-payment-for-centralized-payments"></a>Configurar métodos de pago para pagos centralizados
Al crear un pago en una entidad jurídica que liquida facturas de otras entidades jurídicas, los identificadores de forma de pago de ambas entidades jurídicas deben coincidir. Para ayudar a garantizar que los pagos se creen correctamente, en cada entidad jurídica de la factura, configure una forma de pago en cada entidad jurídica de facturación que se corresponda con las formas de pago que se usan en la entidad jurídica de pago. Cambie a la primera entidad jurídica de la factura y, a continuación, en la página **Métodos de pago **, puede crear un nuevo método de pago o editar un método existente de pago. No es necesario que las selecciones que realice para la forma de pago de la entidad jurídica de facturación coincidan con la configuración de la forma de pago de la entidad jurídica de pago.

## <a name="set-up-default-descriptions"></a>Configurar descripciones predeterminadas
Se pueden definir descripciones predeterminadas para los asientos de liquidación de empresas vinculadas. La descripción predeterminada se incluye en las transacciones de inicio y fin de vencimiento durante el proceso de liquidación entre empresas. En la página **Descripciones Predeterminadas**, puede crear nuevas descripciones tanto para **Liquidación de cliente de empresas vinculadas **como para **Liquidación de proveedor de empresas vinculadas** seleccionando un idioma y después especificando el texto.


