---
title: Configuración de las autoridades fiscales
description: Las autoridades fiscales son las entidades a las que tienen que notificarse y pagarse los impuestos cobrados.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f4847b5f3f50cc74c5b4854e1f0daedd64785baf
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994574"
---
# <a name="set-up-sales-tax-authorities"></a>Configuración de las autoridades fiscales

[!include [banner](../../includes/banner.md)]

Las autoridades fiscales son las entidades a las que tienen que notificarse y pagarse los impuestos cobrados. Puede pagar los impuestos a la autoridad directamente o a través de una cuenta de proveedor que cree para la autoridad fiscal. Si lo hace, la empresa puede usar sus rutinas de pago habituales para pagar a la autoridad fiscal puntualmente. Si no configura la autoridad fiscal como proveedor, una persona deberá prepararle un pago manual en la fecha de vencimiento correspondiente. Esta tarea usa la empresa de demostración USMF.

1. Vaya a Impuestos >Impuestos indirectos >Impuestos >Autoridades fiscales.
2. Haga clic en Nuevo.
3. En el campo Autoridad, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Seleccione el diseño del informe para su país o región si hay uno disponible. Si los diseños de informe no se corresponden con los requisitos de la autoridad fiscal, use el diseño predeterminado.
9. Especifique los valores en el formulario de redondeo y los campos Redondear para especificar cómo se debe redondear el importe total de impuestos que se debe pagar. Las diferencias de redondeo se registrarán en la configuración de Cuentas para transacciones automáticas en contabilidad general.
10. En el campo Redondear, escriba un número
11. Haga clic en Guardar.

