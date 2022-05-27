---
title: Tipos de diarios contables
description: En este tema se describen los tipos de diarios que se pueden configurar para los diarios financieros.
author: kweekley
ms.date: 10/10/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup
audience: Application User
ms.reviewer: kfend
ms.custom: 15631
ms.assetid: 81613b31-bc3c-43a0-8474-e01c9a482c40
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e49d101bbbe576e0fcf2e9b243f4f29124fbd85
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722280"
---
# <a name="ledger-journal-types"></a>Tipos de diarios contables

[!include [banner](../includes/banner.md)]

En este tema se describen los tipos de diarios que se pueden configurar para los diarios financieros. Use la página **Nombres de diarios** para configurar diarios que puede usar en todo Dynamics 365 Finance.

| Tipo de diario                      | Propósito                       | Especificar las transacciones en esta página                                |
|-----------------------------------|-------------------------------|----------------------------------------------------------------|
| Asignación                        | Crear transacciones de asignación en un diario de asignaciones. Para poder crear un diario de asignaciones, deberá crear previamente una regla en la página **Regla de asignaciones de libro mayor**.      | Solicitud de asignación de proceso             |
| Aprobación                          | Registrar facturas de proveedor que se han aprobado en las cuentas contables adecuadas.  | Diario de aprobación de facturas                                       |
| Inversión de cheque bancario               | Invertir un cheque registrado. Para usar este tipo de diario, seleccione la opción **Usar el proceso de revisión para las inversiones de pagos** en la página **Parámetros de gestión de efectivo y bancos**.   | Inversiones de cheques, inversión de pago                   |
| Cancelación de resguardo de depósito bancario    | Cancelar un resguardo de depósito. Para usar este tipo de diario, seleccione la opción **Usar el proceso de revisión para las cancelaciones de pagos de resguardos de depósitos** en la página **Parámetros de gestión de efectivo y bancos**.   | Cancelaciones de pago de resguardos de depósito            |
| Presupuesto                            | Apropiaciones presupuestarias del proceso. Para usar este tipo de diario, seleccione la opción **Habilitar la apropiación presupuestaria** en la página **Parámetros de contabilidad general**. Las entradas del diario de presupuesto incluyen la información que se basa en las cuentas contables que se definen en la página **Definiciones de contabilización**.                                                        |                                                                |
| Aceptación de letra de cambio  | Crear transacciones de aceptación de cliente para letras de cambio.             | Diario de negociación de letras de cambio, Diario de renegociación de letras de cambio |
| Remesa bancaria del cliente          | Crear un archivo de envío de letra de cambio que se puede enviar al banco de su organización. Para usar este tipo de diario, desactive la opción **Liquidación automática** en la página **Cuentas** **parámetros soportados**.            | Remesa                                                     |
| Librado de letra de cambio del cliente    | Crear transacciones de librado de letra de cambio de cliente Para usar este tipo de diario, desactive la opción **Crear y registrar diario negociado automáticamente al registrar facturas** en la página **Métodos de pago: clientes**.   | Diario de creación de letra de cambio                                  |
| Cobros                  | Crear transacciones de pagos de cliente.                             | Diario de pagos             |
| Impago de letra de cambio | Crear transacciones de impago de letra de cambio de cliente.                    | Diario de impago de letras de cambio                               |
| Renegociación de letra de cambio  | Crear transacciones de letra de cambio de renegociación de cliente.                     | Diario de renegociación de letras de cambio                                |
| Liquidación de letras de cambio del cliente  | Crear transacciones de liquidación de letra de cambio de cliente.                       | Diario de liquidación de letra de cambio                                |
| Diariamente                             | Crear transacciones diarias en un diario general.                          | Diario general                                                |
| Eliminación                       | Crear transacciones de eliminación en un diario de eliminaciones. Para usar este tipo de diario, active las opciones **Usar para el proceso financiero de eliminación** y **Usar para el proceso financiero de consolidación** en la página **Entidades jurídicas**. Para poder usar este tipo de diario, debe crear una regla de eliminación contable en la página **Regla de eliminación contable**. | Eliminación                                                    |
| Presupuesto de activos fijos                | Crear las entradas de registro de presupuestos de activos fijos.                                                                                                                                                                                                                                                                                                                 | Presupuesto de activos fijos                                             |
| Registro de facturas                  | Registrar información básica acerca de las facturas de proveedor.                                                                                                                                                                                                                                                                                                           | Registro de facturas                                               |
| Desembolso de nómina              | Emitir pagos basados en extractos de pago de nóminas. No puede especificar transacciones manualmente en este diario. Debe generar extractos de pagos y, después, enviarlos para el pago.                                                                                                                                                              |                                                                |
| Periódico                          | Crear transacciones periódicas para el diario periódico.                                                                                                                                                                                                                                                                                                      | Diarios periódicos                                              |
| Registrar activos fijos                 | Registrar transacciones de activos fijos.                                                                                                                                                                                                                                                                                                                              | Activos fijos                                                   |
| Proyecto - Gastos                | Crear transacciones de gastos del proyecto.                                                                                                                                                                                                                                                                                                                        | Expense                                                        |
| Ajuste de divisa de notificación     | Cree ajustes en la divisa de notificación para saldos en cuentas contables.               | Diarios de ajuste de divisa de notificación                         |
| Transacciones de estadísticas            | Crear transacciones estadísticas.                                                                                                                                                                                                                                                                                                                            |                                                                |
| Remesa bancaria del proveedor            | Crear un archivo de envío de pagaré que se puede enviar al banco de su organización.                                                                                                                                                                                                                                                                      | Diario de envíos                                             |
| Pagos del proveedor               | Crear transacciones de pagos de proveedor.                                                                                                                                                                                                                                                                                                                    | Diario de pagos                                                |
| Librar pagaré del proveedor       | Librar un pagaré de proveedor como método de pago. Para usar este tipo de diario, desactive la opción **Crear y registrar diario negociado automáticamente al registrar facturas** en la página **Métodos de pago: proveedores**.                                                                                                                                          | Diario de creación de pagarés                                   |
| Grupo de factura del proveedor excluidos los registros | Crear transacciones de factura de proveedor que todavía no se han registrado en una cuenta temporal de llegada.                                                                                                                                                                                                                                                             | Ver detalles de grupo de facturas de proveedor excluidas del registro                  |
| Grupo de factura del proveedor               | Crear transacciones de grupo de facturas de proveedor.                                                                                                                                                                                                                                                                                                                    |                                                                |
| Diario de facturas          | Registrar facturas de proveedor que se encuentran en un diario.                                                                                                                                                                                                                                                                                                                 | Diario de facturas                                                |
| Renegociación de pagarés     | Volver a librar un pagaré ya liquidado por el banco de su organización.                                                                                                                                                                                                                                                                      | Diario de renegociación de pagarés                                 |
| Liquidación de pagarés     | Crear una transacciones de pagaré de liquidación de proveedor.                                                                                                                                                                                                                                                                                                          | Diario de liquidación de pagarés                                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
