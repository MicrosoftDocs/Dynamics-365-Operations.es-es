---
title: Cartas de garantía
description: Este artículo proporciona información acerca de las cartas de garantía. En una carta de garantía, un banco acepta pagar una cierta cantidad de dinero a una persona si uno de los clientes del banco se retrasa en un pago o en la obligación a dicha persona.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankLGGuarantee
audience: Application User
ms.reviewer: roschlom
ms.custom: 18291
ms.assetid: 5c0b5e37-d51d-4a01-bb37-1882173abb9f
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b86ccc46475babb302cdbf82f5c99c26e2091501
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978798"
---
# <a name="letters-of-guarantee"></a>Cartas de garantía

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de las cartas de garantía. En una carta de garantía, un banco acepta pagar una cierta cantidad de dinero a una persona si uno de los clientes del banco se retrasa en un pago o en la obligación a dicha persona. 

Una carta de garantía es un contrato mediante el cual un banco (el garante) paga una cierta cantidad de dinero a alguna persona (el beneficiario) si un cliente del banco (la entidad de seguridad) lo establece en un pago o una obligación al beneficiario. Las cartas de garantía no son transferibles. Solo se aplican al beneficiario nombrado en el acuerdo. La entidad de seguridad puede aplicar un aumento o una reducción del valor de una colección de la garantía, sujeto a las condiciones del contrato. 

Para liquidar una carta de garantía, el beneficiario debe enviar la carta de garantía original e informar al banco del valor predeterminado de la entidad de seguridad antes de la fecha de vencimiento. El banco paga al importe debido a la cuenta del beneficiario, según las condiciones de la carta de garantía. El banco reserva un porcentaje de pago como margen. El porcentaje se conviene y se especifica en las condiciones del contrato. 

Puede crear un código para realizar un seguimiento del propósito de una carta de garantía. También puede especificar los motivos que se pueden asociar a una carta de garantía cuando se cancela la carta. Puede ver los códigos de propósito y los motivos del banco en las páginas **Códigos de propósito de pago** y **Motivos de banco**. 

Puede usar la página **Carta de garantía** para completar estas tareas:

-   Crear las entradas del libro mayor correctas y eliminar la entrada manual.
-   Registrar todas las transacciones monetarias y no monetarias y realizar un seguimiento de los saldos de la carta de garantía.
-   Registrar y realizar un seguimiento del vencimiento y el estado de las cartas de garantía.
-   Generar un informe que enumere los bancos que usan cartas de garantía.

En la tabla siguiente se describen las acciones que se pueden realizar en una carta de garantía.

| Acción              | Propósito                                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| Enviar al banco      | Mostrar la solicitud de carta de garantía al banco.                                                                       |
| Recibir del banco   | Una vez que el banco acepta la solicitud enviada, recoger la carta de garantía del banco.                            |
| Darla al beneficiario | Una vez que reciba la carta de garantía del banco, proporcionar la carta de garantía al beneficiario.              |
| Aumentar el valor      | Si el beneficiario y la entidad de seguridad están de acuerdo, aumentar el valor monetario.                                                  |
| Reducir el valor      | Si el beneficiario y la entidad de seguridad están de acuerdo, reducir el valor monetario.                                                  |
| Ampliar              | Una vez que proporcione la carta de garantía al beneficiario, ampliar el período de validez si es necesaria una ampliación. |
| Cancelar              | Cuando ya no se aplica el propósito para el que la carta de garantía se ha solicitado, cancelar el contrato.                  |
| Liquidar           | Cuando el beneficiario muestra la carta de garantía al banco, cobrar la carta de garantía.                      |


Para obtener más información, consulte los siguientes temas:

[Transacción de carta de garantía](tasks/letter-guarantee-transaction.md)

[Configuración de créditos bancarios y perfiles de contabilización para cartas de garantía](tasks/set-up-bank-facilities-posting-profiles.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]