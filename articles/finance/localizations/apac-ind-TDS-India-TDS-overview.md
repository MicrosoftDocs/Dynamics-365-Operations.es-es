---
title: Información general de impuestos deducidos en el origen (TDS) de la India
description: Este tema proporciona información detallada sobre el impuesto deducido en el origen (TDS) de la India. La documentación de TDS cubre la funcionalidad de esta capacidad.
author: kailiang
ms.date: 03/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 0947481f27323a53d5ef9c7295d8dda078fb4254
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720207"
---
# <a name="indian-tax-deducted-at-source-tds-overview"></a>Información general de impuestos deducidos en el origen (TDS) de la India

[!include [banner](../includes/banner.md)]

Este tema proporciona información detallada sobre el impuesto deducido en el origen (TDS) de la India.

La documentación de TDS cubre la funcionalidad de esta capacidad. También explica cómo realizar la configuración básica de TDS, calcular TDS en transacciones, completar el proceso de liquidación de TDS, registrar números de certificado de TDS y generar consultas de TDS, declaraciones de TDS y certificados de TDS. La documentación incluye los siguientes temas:

- [Configuración básica para TDS](apac-ind-TDS-TDS-ledger-accounts-setup.md)
- [Diseñador de fórmulas y funcionalidad de límite de umbral utilizada para el cálculo de TDS](apac-ind-TDS-Formula-designer.md)
- [Cálculo de TDS en facturas, pagos, pagarés y transacciones entre empresas](apac-ind-TDS-Calculate-TDS-on-invoices-using-journals.md)
- [Proceso de liquidación periódica de TDS y liquidación de importes de TDS a proveedores de autoridad de TDS](apac-ind-TDS-Run-the-periodic-TDS-settlement-process.md)
- [Registro y actualización de números y fechas de certificados TDS](apac-ind-TDS-Record-TDS-concession-certificate-numbers.md)

## <a name="introduction-to-tds"></a>Introducción a TDS

De acuerdo con la Ley de impuestos sobre la renta de 1961, el receptor del servicio deduce el impuesto sobre la renta en el origen en el momento del pago anticipado o la contabilización del crédito, lo que ocurra primero. La persona que realiza el pago debe deducir el importe del impuesto y pagar solo el saldo neto al proveedor del servicio. Los TDS se aplican a los servicios que especifica el gobierno y el impuesto se deduce utilizando las tasas que el gobierno especifica para un periodo. La tasa de deducción se basa en el estado de la entidad que recibe el pago o presta el servicio. Los estados incluyen **Individual**, **Familia indivisa hindú** (**HUF**), **Empresa**, **Firma**, **Asociación de personas** (**AOP**), **Cuerpo de individuos** (**BOI**) y **Autoridad local**.

Las siguientes secciones enumeran los servicios en los que se aplican los TDS, según lo especificado por el gobierno de la India.

**Residentes**

- Ingresos por sueldos (según la sección 192)
- Ingresos por intereses sobre valores (según la sección 193)
- Ingresos por dividendo (según la sección 194)
- Ingresos por interés (según la sección 194A)
- Ingresos de loterías o juegos (según la sección 194B)
- Ganar en carreras de caballos, etc. (según la sección 194BB)
- Contratistas y subcontratistas (según la sección 194C)
- Comisión de seguros (según la sección 194D)
- Ingresos por depósito en el marco del plan de ahorro nacional (según la sección 194EE)
- Ingresos de fondos mutuos o UTI (según la sección 194F)
- Comisión, remuneración, premio, etc. en venta o lotería (según la sección 194G)
- Pago de comisión o correduría (según la sección 194H)
- Alquiler (según la sección 194I)
- Servicio profesional (según la sección 194J)
- Ingresos por unidades (según la sección 194K)
- Pago de compensación por la adquisición de determinadas propiedades inmuebles (según la sección 194LA)

**No residentes**

- Pagos a deportistas o asociaciones deportivas no residentes (según la sección 194E)
- Otras sumas (en la sección 195)
- Ingresos por unidades de no residentes (según la sección 196A)

    - Ingresos de pólizas en divisa extranjera o acciones de una empresa india (según la sección 196C)
    - Ingresos de inversores institucionales extranjeros procedentes de valores (según la sección 196D)
    - Salario y todos los demás ingresos positivos en cualquier categoría de ingresos (sección 192)
    - Intereses sobre valores (sección 193)
    - Intereses distintos de los intereses sobre valores (sección 194A)
    - Pagos a contratistas y subcontratistas (sección 194C)
    - Ganancias de lotería o crucigramas (sección 194B)
    - Ganancias en carreras de caballos (sección 194BB)
    - Comisión de seguros que cubre todos los pagos para la adquisición de negocios de seguros (sección 194D)
    - Cualquier interés que no sea el interés sobre valores pagaderos a no residentes que no sean una empresa o una empresa extranjera (sección 195)
    - Pago al deportista no residente incluido deportista, asociación o institución deportiva. En el caso de deportistas no residentes, se incluyen pagos con respecto a anuncios y artículos sobre cualquier juego o deporte en la India en periódicos, revistas, etc. (sección 194E)
    - Pago con respecto a depósitos bajo NSS \[Plan nacional de ahorro\] (sección 194EE)
    - Pago a cuenta de recompra de Participaciones por Fondo Mutuo o UTI (Sección 194F)
    - Pago para comisión o correduría (sección 194H)
    - Pago del alquiler (sección 194I)
    - Pago de cuotas por servicios profesionales o técnicos (sección 194J)
    - Comisión a Stockiest, distribuidores, compradores y vendedores de boletos de lotería, incluida la remuneración o el premio de dichos boletos (sección 194G)
    - Ingresos de unidades compradas en divisa extranjera o ganancias de capital a largo plazo que surjan de la transferencia de dichas unidades compradas en divisa extranjera (sección 196B)
    - Pago de cualquier ingreso a no residentes con respecto a intereses o dividendos sobre pólizas y acciones (sección 196C)

Los TDS se calculan sobre compras, ventas, devoluciones de ventas, notas de crédito, adquisiciones de activos fijos, pagos anticipados, pagos por adelantado, pagarés, impuestos sobre obras y transacciones entre empresas.

> [!NOTE]
> En el escenario fiscal actual de la India, los TDS no se calculan sobre las transacciones de ventas. Sin embargo, el sistema incluye una provisión para calcular los TDS recuperables en transacciones de ventas, especialmente para transacciones entre empresas.

El cálculo de TDS siempre tiene en cuenta el umbral y el umbral de excepción que se definen para el componente TDS.

Se debe ejecutar el proceso de liquidación periódica de TDS y los pagos de TDS deben liquidarse a los proveedores de la autoridad de TDS.

Los números de certificado y las fechas de los certificados TDS que se reciben de proveedores o clientes se pueden registrar y actualizar. Además, los extractos de cuenta trimestrales del formulario 26Q y del formulario 27Q, además del certificado del formulario 16A para TDS, se pueden generar en Finance.

## <a name="setting-up-and-working-with-tds"></a>Configurar y trabajar con TDS

Aquí hay una descripción general del proceso para configurar y trabajar con TDS:

1. **Configuración de TDS:**

    - Configuración de parámetros:

        - En los parámetros de contabilidad general, active los parámetros relacionados con TDS.
        - En los parámetros de contabilidad general, configure la secuencia numérica para los pagos de retención de impuestos.
        - Configure los parámetros en proveedores y clientes.

    - Configuración básica:

        - Configure los números de registro de TDS para una empresa, clientes y proveedores.
        - Configure los grupos de componentes de TDS.
        - Configure los componentes de TDS, adjunte los grupos de componentes de TDS y defina el umbral y el umbral de excepción para los mismos.
        - Configure las autoridades de TDS.
        - Configure los periodos de liquidación de TDS.
        - Configure los códigos de impuestos de TDS y adjunte los componentes de TDS.
        - Configure los grupos de impuestos de TDS y adjunte los códigos de impuestos de TDS.
        - En el diseñador de fórmulas, defina una fórmula para calcular TDS para un grupo de TDS.
        - Registre los números de los certificados de concesión de TDS.

    - Cuenta contable y configuración de la empresa:

        - Configure cuentas de proveedor y cliente de TDS.
        - Configure un número de cuenta de deducción y recaudación de impuestos (TAN) y una categoría de tipo de deductor para la empresa.

    - Otra configuración:

        - Configure una programación de pagos que incluya la asignación de TDS.
        - Configure un tipo de cuota de pago para pagos a la autoridad de TDS.
        - Configure información sobre grupos de TDS, números de cuenta permanentes (PAN) y TAN para proveedores y clientes.

2. **Cálculo de TDS en transacciones:**

    - Facturas y pagos
    - Pagarés
    - Anticipos
    - Pagos por adelantado

3. **Liquidación de TDS:**

    - Proceso de liquidación periódica de TDS
    - Liquidación de pagos de TDS a proveedores de autoridad de TDS y generación de challan de TDS

4. **Consultas, extractos y certificado de TDS:**

    - Registre y actualice los números y fechas de certificados TDS.
    - Genere una consulta de TDS y una consulta de TDS registrada.
    - Genere el formulario 27A, el formulario 26Q y el formulario 27Q TDS y extractos de cuenta trimestrales de e-TDS.
    - Genere un certificado de TDS del formulario 16A.
