---
title: Un asiento
description: "Un asiento para diarios financieros (diario, diario de activos fijos, diario de pago del proveedor, etc.) le permite especificar varias transacciones de subcontabilidad en el contexto de un asiento único."
author: kweekley
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9f996131830f9bd4efd534143b3fb761c5ccc756
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="one-voucher"></a>Un asiento

[!include [banner](../includes/banner.md)]

> [!NOTE]
>  Esta funcionalidad estará disponible en Dynamics 365 for Finance and Operations versión 8.0, que estará disponible en el lanzamiento de la versión de primavera de 2018.   

<a name="what-is-one-voucher"></a>¿Qué es “un asiento"?
======================

La funcionalidad existente para los diarios financieros (diario, diario de activos fijos, diario de pago del proveedor, etc.) le permite especificar varias transacciones de subcontabilidad en el contexto de un asiento único. Nos referimos a esta funcionalidad "un asiento.” Puede crear un asiento con uno de los siguientes métodos:

-   Configure el nombre de diario (**contabilidad general** \> **Configuración del diario** \>**Nombres de diario**) para que el campo **Nuevo asiento** esté establecido en **Solo un número de asiento**. * Cada línea que agrega al diario ahora se incluye en el mismo asiento. Como cada línea se agrega al mismo asiento, el asiento se puede introducir como asiento multilínea, como una cuenta/cuenta de contrapartida en la misma línea o como una combinación.

[![Una línea](./media/same-line.png)](./media/same-line.png)
 
> [!IMPORTANT] 
> *  Tenga en cuenta que la definición de "un asiento" NO incluye los nombres de diario configurados como **Número de asiento** y sólo el usuario escribe un asiento que incluya solo tipos de cuenta contable.  En este documento "un asiento" significa que hay un asiento que contiene más de un proveedor, cliente, banco, activo fijo o proyecto. 

-   Especifique un asiento multilínea donde no haya cuenta de contrapartida.

[![Asiento multilínea](./media/Multi-line.png)](./media/Multi-line.png)

-   Introduzca un asiento en el que tanto la cuenta como la cuenta de contrapartida contengan un tipo de cuenta de subdiario contable, como proveedor/proveedor, cliente/cliente, proveedor/cliente o banco/banco.

[![Asiento de subdiario](./media/subledger.png)](./media/subledger.png)

<a name="issues-with-one-voucher"></a>Problemas con un comprobante
=======================

La funcionalidad de asiento único produce problemas durante el acuerdo, el cálculo de impuestos, la conciliación de un subdiario contable en la contabilidad general, el informe financiero, etc. (Por ejemplo, para obtener más información acerca de problemas que pueden ocurrir durante el acuerdo, consulte [Asiento único con varios clientes o registros de proveedores](https://docs.microsoft.com/en-us/dynamics365/unified-operations/financials/accounts-payable/single-voucher-multiple-customer-vendor-records).) Para trabajar y notificar correctamente, estos procesos e informes requieren detalles de la transacción. Aunque algunos escenarios pudieran funcionar correctamente, en función de la configuración de la organización, a menudo hay problemas cuando varias transacciones se introducen en un asiento.

Por ejemplo, registra el siguiente asiento múltiple.

[![Ejemplo ](./media/example.png)](./media/example.png)

A continuación, genere el informe **Gastos por proveedor** en el espacio de trabajo **Información financiera**. Los saldos de cuenta de gastos de los grupos de informe en el grupo de proveedores y el proveedor. Al generar el informe, el sistema no puede determinar qué grupos de proveedores/proveedores incurrieron en el gasto de 250.00. Dado que faltan detalles de la transacción, el sistema supone que el primer proveedor que se encuentra en el asiento incurrió la totalidad de los 250,00. Los 250.00, que se incluye en el saldo de la cuenta principal 600120, se muestra en ese grupo de proveedores/proveedor. Es muy probable que el primer proveedor del asiento no fuera el proveedor correcto, por lo que el informe es incorrecto.

[![Gastos](./media/expenses.png)](./media/expenses.png)

<a name="the-future-of-one-voucher"></a>El futuro de un asiento
=========================

Debido a los problemas mencionados previamente, la funcionalidad de Un asiento quedará obsoleta. Sin embargo, dado que hay espacios funcionales que dependen de esta funcionalidad, la funcionalidad no quedará obsoleta de una vez. En su lugar, utilizaremos la programación siguiente: 

- **Versión de primavera 2018** La funcionalidad se desactivará de manera predeterminada a través de un parámetro de contabilidad general. Sin embargo, puede activar la funcionalidad si su organización tiene un escenario que caiga en los espacios del escenario empresarial que aparecen más adelante en este tema.

  -   Si un cliente tiene un escenario empresarial que no requiere Un asiento, no vuelva a activar la funcionalidad. No corregiremos los "errores“ en las áreas que se identificaron más adelante en este tema si esta funcionalidad se usa aunque exista otra solución.

  -   Deje de usar un asiento para las integraciones en Microsoft Dynamics 365 Finance and Operations, a menos que la funcionalidad sea necesaria para una de las lagunas funcionales.

- **Versiones de otoño de 2018 y posteriores** Los espacios funcionales se rellenarán. Una vez que se rellenen espacios funcionales, la funcionalidad del asiento se desactivará permanentemente.

- > [!IMPORTANT]
  > Tenga en cuenta que la opción **Número de asiento sólo** no se ha quitado de la configuración del nombre de diario.  Esta opción aún se admite cuando el asiento contiene solo tipos de cuenta contable.  Los clientes deben tener cuidado al utilizar este valor porque el asiento no se registrará si se usa **Número de asiento sólo** pero por otro lado especifica más de un cliente, proveedor, banco, activo fijo, o proyecto.  Además, los clientes pueden introducir una combinación de tipos de cuenta del subdiario contable, como un pago en un asiento único que contenga tipos de cuenta de proveedor o del banco.  

<a name="why-use-one-voucher"></a>¿Por qué usar un asiento?
====================

Basado en conversaciones con clientes, hemos compilado la siguiente lista de escenarios donde los clientes usan la funcionalidad de Un asiento o motivos por los que la usan. Algunos de estos requisitos empresariales se pueden cumplir solo con un asiento. Sin embargo, para muchos casos, las opciones alternativas pueden cumplir los mismos requisitos empresariales.

<a name="scenarios-that-require-one-voucher"></a>Situaciones que requieren un asiento
----------------------------------

Las situaciones siguientes se pueden realizar solo con la funcionalidad de asiento único. Estas lagunas funcionales se abordarán con otras características en otoño 2018 y posteriores lanzamientos.

-   **Registrar los pagos de cliente o de proveedor en formulario resumen en una cuenta bancaria**

    -   Una organización comunica una lista de proveedores e importes al banco y el banco usa esta lista para pagar a los proveedores en nombre la organización. El banco registra la suma de los pagos como una sola retirada en la cuenta bancaria.

>   La recapitulación de pagos de proveedor se admite solo a través de un asiento. Cada proveedor se introduce como una línea independiente para mantener el detalle en el subdiario contable de los proveedores, pero el importe total de todos los pagos se compensa a una única línea para la cuenta bancaria. Por lo tanto, la retirada se muestra como un solo importe resumido en el subdiario de banco.

-   Una organización deposita pagos de cliente o el banco deposita los pagos de cliente en nombre de la organización y el depósito se muestra como suma total en la cuenta bancaria.

>   La recapitulación de pagos de cliente se admite normalmente con la funcionalidad de depósito. Sin embargo, si utiliza "puente" en la forma de pago, este escenario se admite sólo a través de Un asiento. Los pagos de cliente se especifican de la misma forma que se describe para la recapitulación de pago de proveedor.

-   **Mecanismo para agrupar transacciones de un evento de negocio**

    -   Una organización tiene un solo evento de negocio que activa varias transacciones. Sin embargo, el departamento de contabilidad desea ver las entradas contables de forma conjunta para una mejor auditabilidad.

>   Si una organización debe ver los asientos contables de un evento de negocio de forma conjunta, debe usar Un asiento. 

- **Funciones específicas de un país o región**

  -   La característica de (SAD) de Documento Único Administrativo para Polonia requiere actualmente que se use un asiento único. Hasta que una opción de agrupación esté disponible para esta función, debe continuar utilizando la funcionalidad de asiento único. Puede haber características específicas del país adicionales que requieran la funcionalidad de asiento.

- **Diario de pagos de anticipo del cliente que tiene impuestos sobre las varias "líneas"**

  -   Un cliente realiza un anticipo para un pedido y las líneas del pedido tienen diferentes impuestos que se deben registrar para el anticipo. El anticipo de cliente es una transacción que simula las líneas de pedido, para poder registrar los impuestos adecuados para el importe de cada línea.

En esta situación, los clientes del asiento único son el mismo cliente, porque la transacción simula las líneas de un pedido de cliente. El anticipo se debe especificar en un asiento único, ya que el cálculo de impuestos se debe crear en las “líneas” del pago único que realizó el cliente.

-   **Mantenimiento de activos fijos: La recuperación de la depreciación, división de activos, calcula la depreciación en la cancelación**

Las siguientes transacciones de activos fijos también crean varias transacciones dentro de un asiento único:
-   Se crea una adquisición adicional en un activo y se calcula la "actualización" de la depreciación.
-   Un activo está dividido.
-   Un parámetro para calcular la depreciación en la disposición se habilita y finalmente el activo se cancela.

<a name="scenarios-that-dont-require-one-voucher"></a>Situaciones que no requieren un asiento
----------------------------------------

Las situaciones siguientes pueden ser realizadas con otros medios y no deberían usar un asiento.

-   **Registrar los pagos de cliente en formulario resumen en la cuenta bancaria**

Una organización deposita pagos de cliente o el banco deposita los pagos de cliente en nombre de la organización y el depósito se muestra como suma total en la cuenta bancaria.

La recapitulación de pagos de cliente se admite con la funcionalidad de depósito cuando no se usa el puente en la forma de pago.

-   **Compensación**

En la red, los saldos para un proveedor y el cliente están uno junto al otro porque el proveedor y el cliente son la misma parte. Este enfoque minimiza el intercambio de dinero entre una organización y la parte del cliente o proveedor.

El trabajo en red se logra especificando el aumento y la reducción de asientos independientes, y enviando la contrapartida a una cuenta contable de eliminación.

-   **Registrar en resumen en la contabilidad general.**

Las organizaciones a menudo desean registrar en la contabilidad general en resumen para minimizar la cantidad de datos. Sin embargo, las organizaciones normalmente requieren que mantengan los detalles de transacción. Cuando el registro se realiza en resumen mediante un asiento único, no se conoce el detalle de la transacción y no se puede mantener.

   -   Dado que el detalle de transacción no puede mantenerse actualmente, se recomienda no usar Un asiento para registrar de forma resumida.
   -   Una vez que el soporte de un asiento se elimine, podemos implementar marcos del documento de origen y de contabilidad en los diarios. Estos marcos mantendrán entonces los detalles de la transacción y admitirán el resumen en la contabilidad general.

-   **Liquidar varios pagos no contabilizados en la misma factura**

Este escenario se encuentra normalmente en las organizaciones al por menor en las que los clientes pueden usar varias formas de pago para pagar compras. En este escenario, la organización debe poder registrar varios pagos sin registrar y liquidarlos con la factura de cliente.

Una nueva función que se ha agregado en Microsoft Dynamics 365 for Operations versión 1611 (noviembre de 2016) permite liquidar varios pagos no registrados contra una única factura. Los pagos de varios clientes ya no tienen que especificarse en un asiento único.

-   **Importar transacciones de extracto bancario**

Los bancos a menudo pagan y reciben pagos en nombre una organización y estas transacciones se registran en Finance and Operations a través de un archivo que se recibe del banco. Las organizaciones a menudo desean agrupar juntas esas transacciones mediante el número de extracto bancario en el archivo. Como cada transacción se muestra en detalle en el extracto bancario, no se requiere ninguna recapitulación en el subdiario de banco.

Las transacciones se pueden agrupar con otros campos del diario, como el número de lote del diario en sí o el número de documento.

-   **Transferir saldos**

Una organización podría tener que transferir un saldo de un proveedor a otro proveedor, ya sea debido a un error o debido a que otro proveedor ha asumido el pasivo. Las transferencias de este tipo también se producen para los tipos de cuenta como clientes y cuentas bancarias.

Las transferencias de saldo a partir de una cuenta (proveedor, cliente, cuenta bancaria, etc.) a otra cuenta se pueden realizar a través de los asientos independientes y la contrapartida se puede registrar en una cuenta contable de compensación.

-   **Introducir saldos iniciales**

Las organizaciones a menudo especifican saldos iniciales para cuentas de subcontabilidad (proveedores, clientes, activos fijos, etc.) como una transacción de asiento. Los saldos iniciales para cada cuenta de subcontabilidad se pueden especificar como asientos independientes y la contrapartida se puede registrar en una cuenta contable de compensación.

-   **Corregir el asiento contable de un documento registrado del cliente o de proveedor**

Una organización puede tener que corregir la cuenta contable de los clientes o de los proveedores para una entrada contable de una factura registrada, pero dicha factura no se puede invertir o corregir a través de otro mecanismo.

Si ha de realizarse una corrección en la cuenta contable de clientes o de proveedores, se debe realizar un ajuste directamente en la cuenta contable. El ajuste no puede realizarse registrando a través del proveedor o el cliente. Este enfoque requiere que el ajuste se efectúe durante un "tiempo de inactividad”, de modo que la cuenta contable pueda permitir temporalmente la entrada manual.

-   **"El sistema lo permite"**

Las organizaciones a menudo usan la funcionalidad de un asiento simplemente porque el sistema les permite utilizarla, sin comprender las implicaciones.

