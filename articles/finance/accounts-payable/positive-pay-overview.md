---
title: Visión general de pago positivo
description: Este artículo proporciona información acerca del pago positivo, que se usa para generar una lista electrónica de cheques que se pueden presentar a un banco.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 49fe8369fce599d16134541b1c968727f38ebff9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189646"
---
# <a name="positive-pay-overview"></a>Visión general de pago positivo

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca del pago positivo, que se usa para generar una lista electrónica de cheques que se pueden presentar a un banco. 

El pago positivo se usa para generar una lista electrónica de cheques que se pueden presentar a un banco. Los archivos de pago positivo pueden ayudar a los bancos a evitar fraude de cheques. Configure los pagos positivos para generar una lista electrónica de cheques cada vez que se impriman cheques. A continuación, cuando un cheque se envía al banco, el banco compara el cheque con la lista de cheques que envió anteriormente. Si el cheque coincide con un cheque de la lista, el banco lo compensa. Si el cheque no coincide con un cheque en la lista, el banco lo retiene para su revisión.

El pago positivo también se conoce como Pago seguro. 

Los archivos de pago positivo pueden contener información confidencial acerca de los beneficiarios y los importes del cheque. Por lo tanto, asegúrese de usar medidas de seguridad adecuadas desde el momento en que los archivos se generan, hasta que los reciba el banco. Los archivos de pago positivo se descargan en función de las instrucciones de descarga para el explorador web. 

Los archivos de pago positivo se crean mediante entidades de datos. Para generar un archivo de pago positivo, debe configurar los formatos de transformación para el XML que traduce los datos en un formato que el banco puede usar. 

Para cada cuenta bancaria para la que desea generar información de pago positivo, debe asignar el formato de pago positivo. Tras generar pagos, puede generar un archivo de pago positivo para una única entidad jurídica y una única cuenta bancaria. También puede generar archivos de pago positivo para varias entidades jurídicas y cuentas bancarias al mismo tiempo. 

Después de que se hayan pagado los cheques que aparecen en un archivo de pago positivo, recibirá un número de confirmación del banco. A continuación, puede confirmar el archivo de pago positivo en el sistema. 

Si debe cambiar un archivo de pago positivo, puede recuperarlo. A continuación, para cada cheque del archivo de pago positivo, se restablece el campo que indica si el cheque se ha incluido en un archivo de pago positivo.

Para obtener más información, consulte [Configurar y generar archivos de pago positivo](set-up-generate-positive-pay-files.md).



