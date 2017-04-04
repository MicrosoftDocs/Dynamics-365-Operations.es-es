---
title: "Configuración de la contabilidad de empresas vinculadas"
description: "Este tema explica cómo configurar la contabilidad de empresas vinculadas de manera que pueda usar los diarios empresas vinculadas para las asignaciones de contabilidad y los diarios financieros, como diarios, diarios de facturas de proveedor, y diarios de pagos."
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
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5fd279327013f26230146be38e23e9955c6f12c7
ms.lasthandoff: 03/31/2017


---

# <a name="intercompany-accounting-setup"></a>Configuración de la contabilidad de empresas vinculadas

Este tema explica cómo configurar la contabilidad de empresas vinculadas de manera que pueda usar los diarios empresas vinculadas para las asignaciones de contabilidad y los diarios financieros, como diarios, diarios de facturas de proveedor, y diarios de pagos.

Los diarios empresas vinculadas pueden crear en distintos escenarios, como para los diarios, los diarios de facturas de proveedor, las asignaciones de contabilidad, y los pagos centralizados. Para habilitar estos escenarios, debe configurar la contabilidad de empresas vinculadas.

## <a name="define-main-accounts"></a>Defina las cuentas principales
En primer lugar, debe crear las cuentas principales de empresas vinculadas para usarlas para los asientos contables Vencido hasta y Vencido desde. Es una buena idea usar las cuentas principales únicas para cada empresa, para simplificar la conciliación y la eliminación de los asientos contables de empresas vinculadas. Si utiliza una dimensión del socio comercial o duplicados para identificar la parte empresas vinculadas, puede definir esta dimensión como dimensión fija en la cuenta principal definida en la contabilidad de empresas vinculadas. Al configurar las cuentas principales, debe establecer el balance de situación ** tipo de cuenta principal ** del campo ** ** ** en las cuentas principales ** la página.

## <a name="define-journal-names"></a>Definir los nombres de diario
A continuación, debe definir un nombre de diario. Defina el diario ** tipo de diario del campo ** ** ** ** en los nombres de diario ** la página. Es una buena idea usar un nombre de diario específico para la contabilidad de empresas vinculadas.

## <a name="define-intercompany-accounting-setup"></a>Definir la configuración de la contabilidad de empresas vinculadas
** Contabilidad de empresas vinculadas ** la página se utiliza para crear los pares de entidades jurídicas que puedan tramitar entre sí. Se debe compartir la configuración de la contabilidad de empresas vinculadas, por lo que la configuración es visible dentro de todas las entidades jurídicas. Al crear un nuevo par de la entidad jurídica, asegúrese de que conozca cuyo definen en la entidad jurídica como la empresa la de origen con la empresa de destino. Al especificar transacciones de empresas vinculadas, la transacción que determina la entidad jurídica es que inicia o derivado la transacción. Por ejemplo, la contabilidad de empresas vinculadas se configuran para el USMF (origen) y USSI destino (). Si un usuario está activo en USSI y especifique una transacción de empresas vinculadas con USMF, la transacción no se registrará porque la contabilidad de empresas vinculadas se define solo para USMF que es el originador. Si una empresa puede originar una transacción, deberá crear un segundo par de la entidad jurídica para la configuración recíproca. 

Seleccione ** cuenta de débito (derecho de **) y ** cuenta de (crédito debido a) para ** origen y la entidad jurídica de destino. Permite definir ** el nombre de diario ** se usará cuando se crea la transacción en la empresa de destino. El diario para la empresa la de origen se conoce porque ya ha seleccionado por el usuario al crear la transacción de empresas vinculadas. 

Finalmente, seleccione qué entidad jurídica recibirá los importes que admiten que explican, como el descuento por pronto pago o beneficios realizados/pérdidas para los pagos centralizados. 

Una relación recíproca se puede configurar con facilidad en ** contabilidad de empresas vinculadas ** la página usando ** crear la relación recíproca ** el botón una vez creado el primer par de la entidad jurídica. Cuando se crea un par recíproco, la información para la empresa de destino se copia en la empresa la de origen y viceversa. El diario definido para la empresa de destino permanecerá. La mayoría de las organizaciones usan a la misma convención de nomenclatura para los nombres de diario, de modo que el nombre de diario es el mismo. Si el nombre de diario es diferente, una advertencia aparecerá en el campo para notificarle que no existe el diario y otro diario se puede activar.


