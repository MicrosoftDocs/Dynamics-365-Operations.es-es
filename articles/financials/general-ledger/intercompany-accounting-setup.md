---
title: Configurar la contabilidad de empresas vinculadas
description: "Este tema explica cómo configurar la contabilidad de empresas vinculadas de manera que pueda usar los diarios de empresas vinculadas para las asignaciones de contabilidad y los diarios financieros, como diarios, diarios de facturas de proveedor y diarios de pagos."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerInterCompany
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15761
ms.assetid: 1362297b-7a51-4930-b822-2b204a2e3c37
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 506c7958a90bd5a891ea9859c679fcadb64a64d4
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017

---

# <a name="intercompany-accounting-setup"></a>Configurar la contabilidad de empresas vinculadas

[!include[banner](../includes/banner.md)]


Este tema explica cómo configurar la contabilidad de empresas vinculadas de manera que pueda usar los diarios de empresas vinculadas para las asignaciones de contabilidad y los diarios financieros, como diarios, diarios de facturas de proveedor y diarios de pagos.

Los diarios de empresas vinculadas se pueden crear en diversos escenarios, como diarios, diarios de facturas de proveedor, asignaciones de contabilidad y pagos centralizados. Para habilitar estos escenarios, debe configurar la contabilidad de empresas vinculadas.

## <a name="define-main-accounts"></a>Definir cuentas principales
En primer lugar, debe crear las cuentas principales de empresas vinculadas para usarlas para los asientos contables Vencido hasta y Vencido desde. Es una buena idea usar las cuentas principales únicas para cada empresa, para simplificar la conciliación y la eliminación de los asientos contables de empresas vinculadas. Si usa una dimensión de socio comercial u homóloga para identificar la parte de empresas vinculadas, puede definir esta dimensión como dimensión fija en la cuenta principal definida en la contabilidad de empresas vinculadas. Al configurar las cuentas principales, debe definir el campo **Tipo de cuenta principal** en **Balance de situación** en la página **Cuentas principales**.

## <a name="define-journal-names"></a>Definir nombres de diarios
A continuación, debe definir un nombre de diario. Establezca el campo **Tipo de diario** en **Diario** en la página **Nombres de diario**. Es una buena idea usar un nombre de diario específico para la contabilidad de empresas vinculadas.

## <a name="define-intercompany-accounting-setup"></a>Definir configuración de contabilidad de empresas vinculadas
La página **Contabilidad de empresas vinculadas** se utiliza para crear los pares de entidades jurídicas que pueden tramitar entre sí. Se debe compartir la configuración de contabilidad de empresas vinculadas, por lo que la configuración es visible dentro de todas las entidades jurídicas. Al crear un nuevo par de entidades jurídicas, asegúrese de que conoce la entidad jurídica que se define como empresa de origen frente a empresa de destino. Al introducir transacciones de empresas vinculadas, la transacción determina qué entidad jurídica inicia u origina la transacción. Por ejemplo, la contabilidad de empresas vinculadas está configurada para USMF (origen) y USSI (destino). Si un usuario está activo en USSI e introduce una transacción de empresas vinculadas con USMF, la transacción no se registrará porque la contabilidad de empresas vinculadas solo está definida para que USMF sea el originador. Si una empresa puede originar una transacción, tendrá que crear un segundo par de entidades jurídicas para la configuración recíproca. 

Seleccione **Cuenta de débito (debido de)** y **Cuenta de (debido a)** para la entidad jurídica de origen y de destino. Defina qué **Nombre de diario** se utilizará cuando se cree la transacción en la empresa de destino. El diario para la empresa de origen ya se conoce porque ya ha sido seleccionado por el usuario al crear la transacción de empresas vinculadas. 

Por último, seleccione qué entidad jurídica recibirá la contabilidad para admitir los importes, como el descuento por pronto pago o los beneficios/pérdidas realizados para los pagos centralizados. 

Una relación recíproca se puede configurar con facilidad en la página **Contabilidad de empresas vinculadas** mediante el botón **Crear relación recíproca** tras crear el primer par de entidades jurídicas. Cuando se crea un par recíproco, la información para la empresa de destino se copia en la empresa de origen y viceversa. El diario definido para la empresa de destino permanecerá. La mayoría de organizaciones utilizan la misma convención de nomenclatura para los nombres de diario, por lo que el nombre de diario es el mismo. Si el nombre de diario es diferente, aparecerá una advertencia en el campo para notificarle que el diario no existe y que puede seleccionar un diario diferente.




