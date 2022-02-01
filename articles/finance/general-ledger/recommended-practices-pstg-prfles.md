---
title: Prácticas recomendadas para perfiles de contabilización
description: Este tema describe las prácticas recomendadas para configurar perfiles de contabilización.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, MainAccount, SysDatabaseLogSetup, CustGroup, VendGroup, InventItemGroup
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 097d1c6d1fbe64dadc69cdb275a0aef38922036d
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2022
ms.locfileid: "8014072"
---
# <a name="recommended-practices-for-posting-profiles"></a>Prácticas recomendadas para perfiles de contabilización

Hay varias prácticas recomendadas que debe seguir al configurar perfiles de contabilización en todo el sistema. Este tema describe diferentes escenarios y las prácticas recomendadas correspondientes.

## <a name="setting-the-do-not-allow-manual-entry-flag"></a>Configuración del indicador No permitir entrada manual

En la página **Cuentas principales**, la casilla **No permitir entrada manual** debe estar seleccionada para cualquier cuenta principal que se utilice para un perfil de contabilización. Esta configuración evita que los usuarios publiquen manualmente una entrada de diario en la cuenta principal. Por lo tanto, ayuda a garantizar que el libro auxiliar permanezca en equilibrio con la contabilidad general y ayuda a facilitar el proceso de conciliación.

Si se requieren ajustes en una cuenta controlada por el sistema y contabilizada automáticamente, puede utilizar uno de estos enfoques:

- Cree una cuenta principal secundaria donde se puedan contabilizar los ajustes. Luego use una cuenta Total o una fila especial en sus informes financieros para agrupar y sumar las cuentas.
- Invierta las transacciones originales en el libro auxiliar apropiado, realice las correcciones necesarias y luego vuelva a contabilizar la transacción a través del mismo libro auxiliar.

## <a name="changing-posting-profiles-after-transactions-exist"></a>Cambio de perfiles de contabilización después de que existan transacciones

Si cambia un perfil de contabilización después de que existen transacciones, la reconciliación puede fallar y su libro auxiliar y su contabilidad general pueden quedar fuera de saldo. En general, le recomendamos que **no** cambie el perfil de contabilización después de que existan transacciones.

Si se requieren cambios, use las siguientes pautas para ayudar a garantizar la integridad del sistema:

- Realice los cambios durante un cierre de periodo.
- Realice los cambios cuando no se produzcan otras transacciones en el sistema.
- Valide el libro mayor y concilie con el libro auxiliar antes y después de realizar los cambios.
- Las transacciones registradas no se actualizan si cambia el perfil de contabilización. Piense en detalle si se requieren entradas de ajuste para su cambio.
- Si está cambiando los perfiles de contabilización de inventario, tenga en cuenta cómo los cambios afectarán su inventario disponible y los saldos del libro mayor. Algunos cambios pueden requerir que lleve el inventario a 0 (cero), cierre el inventario y luego lo recupere después de realizar los cambios.
- Siempre pruebe sus cambios en un entorno que no sea de producción antes de realizarlos en producción.

## <a name="using-database-logging-to-audit-changes-to-posting-profiles"></a>Uso del registro de la base de datos para auditar los cambios en los perfiles de contabilización

Piense en configurar el registro de la base de datos para cada perfil de contabilización y las tablas de parámetros que controlan la contabilización. Después, si se cambia un parámetro o perfil, tendrá un registro de auditoría completo de qué valor se cambió, quién lo cambió, cuándo se cambió y cuál era el valor anterior. Esta información puede ser crítica durante su proceso de conciliación y su auditor podría requerir la documentación de respaldo.

Para más información, consulte [Configurar el registro de bases de datos](../../fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log.md).

Utilice la siguiente tabla como referencia para los nombres de tabla comunes que están relacionados con los perfiles de contabilización y los parámetros de contabilización relacionados.

| Nombre de página | Ruta de navegación | Nombre de la tabla |
|-----------|-----------------|------------|
| Parámetros de proveedores | Proveedores &gt; Configuración &gt; Parámetros de proveedores | VendParm |
| Perfil de contabilización del proveedor | Proveedores &gt; Configuración &gt; Perfil de contabilización del proveedor | VendPosting |
| Código de gastos | Proveedores &gt; Configuración de cargos &gt; Código de cargos o Clientes &gt; Configuración de cargos &gt; Código de cargos | MarkupTable |
| Formas de pago | Proveedores &gt; Configuración de pagos &gt; Formas de pago | VendPaymMode |
| Descuentos por pronto pago | Proveedores &gt; Configuración de pago &gt; Descuentos por pronto pago o Clientes &gt; Configuración de pago &gt; Descuentos por pronto pago | CashDisc |
| Cuota de pago (proveedor) | Proveedores &gt; Configuración de pagos &gt; Cuota de pago | VendPaymFee |
| Parámetros de clientes | Clientes &gt; Configuración &gt; Parámetros de clientes | CustParm |
| Perfiles de contabilización del cliente | Clientes &gt; Configuración &gt; Perfil de contabilización del cliente | CustPosting |
| Formas de pago | Clientes &gt; Configuración de pagos &gt; Formas de pago | CustPaymMode |
| Cuota de pago (cliente) | Clientes &gt; Configuración de pagos &gt; Métodos de pago | CustPaymFee |
| Parámetros de arrendamiento de activos | Arrendamiento de activos &gt; Configuración &gt; Parámetros de arrendamiento de activos | AssetLeasePostingAccounts<br>AssetLeaseJournalParameters<br>AssetLeaseExecutoryCostPostingAccounts |
| Cuentas bancarias | Gestión de efectivo y de banco &gt; Cuentas bancarias &gt; Cuentas bancarias | BankAccountsTable |
| Tipos de transacciones bancarias | Gestión de efectivo y bancos &gt; Configuración &gt; Tipos de transacción bancaria | BankTransType |
| Reglas de eliminación | Consolidaciones &gt; Configuración &gt; Regla de eliminación | LedgerEliminationRule<br>LedgerEliminationRuleLines |
| Categorías de gasto | Gestión de gastos &gt; Configurar &gt; General &gt; Categorías de gastos | ProjCategories |
| Parámetros del activo fijo | Activos fijos &gt; Configuración &gt; Parámetros de activos fijos | AssetParameters |
| Perfiles de contabilización de activos fijos | Activos fijos &gt; Configuración &gt; Perfiles de contabilización de activos fijos | AssetLedgerAccounts<br>AssetDisposalParameters |
| Cuentas de revalorización de divisa | Contabilidad general &gt; Divisas &gt; Cuentas de revalorización de divisas | CurrencyLedgerGainLossAccount |
| Cuentas para transacciones automáticas | Contabilidad general &gt; Configuración de contabilidad &gt; Cuentas para transacciones automáticas | LedgerSystemAccounts |
| Contabilidad de empresas vinculadas | Contabilidad general &gt; Configuración de contabilización &gt; Cuentas de empresas vinculadas | LedgerIntercompany |
| Definiciones de contabilización de transacciones | Contabilidad general &gt; Configuración de contabilización &gt; Definiciones de contabilización de transacciones | JournalizingDefinitionTrans |
| Definiciones de contabilización | Contabilidad general &gt; Configuración de contabilización &gt; Definiciones de contabilización | JournalizingDefintion |
| Contabilización (inventario) | Gestión de inventarios &gt; Configuración &gt; Contabilización &gt; Contabilización | InventPosting |
| Códigos de tipo de coste | Coste descargado &gt; Configuración de costes &gt; Códigos de tipo de coste | ITMCostTypeTable |
| Recursos | Control de producción &gt; Configuración &gt; Recursos &gt; Recursos | WrkCtrTable |
| Grupos de recursos | Control de producción &gt; Configuración &gt; Recursos &gt; Grupos de recursos | WrkCtrResourceGroup |
| Grupos de producción | Control de producción &gt; Configuración &gt; Producción &gt; Grupo de producción | ProdGroup |
| Categorías de coste | Control de producción &gt; Configuración &gt; Rutas &gt; Categorías de costes | ProjCategory |
| Grupos de proyectos | Gestión de proyectos y contabilidad &gt; Configuración &gt; Contabilización &gt; Grupos de proyectos | ProjGroup |
| Configuración de registro (proyectos) | Administración de proyectos y contabilidad &gt; Configuración &gt; Registro &gt; Configuración de registro contable | ProjPosting |
| Cuentas de contrapartida predeterminadas para gastos | Administración de proyectos y contabilidad &gt; Configuración &gt; Contabilización &gt; Cuentas de contrapartida predeterminadas para gastos | ProjDefaultOffsetSetup |
| Perfiles de contabilización de gestión de devoluciones | Gestión de devoluciones &gt; Configuración de contabilización de gestión de devoluciones &gt; Perfiles de contabilización de gestión de devoluciones | TAMRebatePosting |
| Grupo de registro (impuesto) | Impuestos &gt; Configuración &gt; Impuestos &gt; Grupo de registro | TaxAccountGroup |

## <a name="changing-groups-after-transactions-exist"></a>Cambio de grupos después de que existan transacciones

Tenga cuidado al cambiar de grupo en los datos maestros. Si usa grupos para definir sus perfiles de contabilización, cualquier cambio en un grupo en un registro maestro puede tener un impacto negativo en la capacidad de conciliar el libro mayor con el libro auxiliar. Por ejemplo, puede configurar el perfil de registro de inventario para los ingresos por pedidos de ventas de modo que se use una cuenta de ingresos diferente para cada grupo de artículos. Si cambia el grupo de artículos que se asigna a un artículo después de que existan transacciones, los ingresos de las nuevas transacciones se contabilizarán en la cuenta actualizada. Sin embargo, cualquier ingreso que se registró antes del cambio permanecerá en la cuenta original.

## <a name="testing-posting-profiles"></a>Probar perfiles de contabilización

Antes de la puesta en marcha y después de realizar cualquier cambio o adición a sus perfiles de contabilización o parámetros relacionados, debe probar cada escenario. Como mínimo, debe probar cada tipo de registro para validar que la contabilización funciona correctamente. Sin embargo, el enfoque recomendado es probar cada transacción y combinación del perfil de contabilización.

Por ejemplo, tiene dos perfiles de contabilización de clientes, cada uno de los cuales tiene tres registros que son específicos de los grupos de clientes. En este caso, debe probar cada tipo de transacción.

**Perfiles de contabilización:**

- **GEN**: el perfil de contabilización general que tiene un grupo para empleados, uno para clientes y otro para empresas vinculadas. Cada grupo indica una cuenta comercial de Clientes diferente.
- **PRE**: el perfil de contabilización de prepago que tiene un registro para todos los prepagos que indica las cuentas de prepago del Cliente.

### <a name="testing-scenarios"></a>Escenarios de prueba

- Factura de servicios para un cliente en el grupo **Empleado** que utiliza el perfil de contabilización **GEN**
- Factura de servicios para un cliente en el grupo **Empleado** que utiliza el perfil de contabilización **PRE**
- Factura de pedido de venta para un cliente en el grupo **Empleado** que utiliza el perfil de contabilización **GEN**
- Factura de pedido de venta para un cliente en el grupo **Empleado** que utiliza el perfil de contabilización **PRE**
- Diario de pagos de cliente para un cliente en el grupo **Empleado** que utiliza el perfil de contabilización **GEN**
- Diario de pagos de cliente para un cliente en el grupo **Empleado** que utiliza el perfil de contabilización **PRE**

Para el ejemplo anterior, repita un escenario de prueba para cada grupo de clientes y repita cada grupo de escenarios de prueba para cada tipo de transacción adicional (por ejemplo, facturas de proyectos y administración de servicios).

## <a name="reconciling-the-ledger-to-the-subledger"></a>Conciliar el libro mayor con el libro auxiliar

El libro mayor debe conciliarse con el libro auxiliar en cada periodo. Muchos módulos contienen informes listos para usar que se pueden usar para ayudar a hacer esta conciliación. Sin embargo, según sus requisitos locales, es posible que deba desarrollar informes personalizados o ampliar los informes existentes para cumplir con sus requisitos de informes.

Le recomendamos que realice un cierre de periodo simulado y concilie cada uno de sus libros auxiliares con el libro mayor antes de la puesta en marcha. También le recomendamos que realice una transición de todos los saldos abiertos y transacciones abiertas antes de su puesta en marcha inicial. Como parte de este proceso, debe ejecutar una conciliación completa para garantizar que la migración de saldos y las transacciones abiertas concuerden con los sistemas heredados, y que todos los libros auxiliares concuerden con el libro mayor antes de que se creen nuevas transacciones.
