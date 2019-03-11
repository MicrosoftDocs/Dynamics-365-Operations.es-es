---
title: Devolución de IVA en Gestión de gastos
description: En este tema se explica cómo recibir devoluciones en las transacciones aptas para el impuesto sobre el valor añadido (IVA).
author: saraschi2
manager: AnnBe
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPerDiems
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bc9e533de40aa8fe8ddfe422cfe0f4078a360c7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "359575"
---
# <a name="vat-recovery-in-expense-management"></a>Devolución de IVA en Gestión de gastos

[!include [banner](../includes/banner.md)]

Para recibir devoluciones en transacciones aptas para el impuesto sobre el valor añadido (IVA), una organización debe identificar, recopilar, comprobar y enviar información precisa. Este proceso incluye varias tareas y, en función del tamaño de la empresa, puede incluir varios empleados o roles.

Para recuperar el IVA mediante la Gestión de datos, es necesario completar los siguientes requisitos previos:

- Los códigos de impuestos se deben crear para países/regiones asignados a categorías de gastos.
- Debe crearse un grupo de impuestos sobre las ventas para cada código de impuestos.
- Debe crearse un código de impuestos sobre las ventas de artículos para cada grupo de impuestos sobre las ventas.

Una vez completados los requisitos previos, los empleados siguen estos pasos para solicitar devoluciones para transacciones de IVA.

1. En un informe de gastos, especifique la información fiscal sobre transacciones de tarjeta de crédito para identificar devoluciones de IVA aptas.
2. Asegúrese de que toda la información fiscal está completa y, a continuación, registre el informe de gastos.
3. Procesar los gastos aptos para la devolución de IVA internacional.
4. Envíe datos de recuperación de IVA al proveedor de terceros para archivar la devolución internacional.
5. Procese los gastos de recuperación de IVA nacional.

En las secciones siguientes se proporcionan ejemplos que muestran cómo los empleados de Contoso completan cada paso.

## <a name="on-an-expense-report-enter-tax-information-about-credit-card-transactions-to-identify-eligible-vat-refunds"></a>En un informe de gastos, especifique la información fiscal sobre transacciones de tarjeta de crédito para identificar devoluciones de IVA aptas

Nancy, una representante de ventas de Contoso con sede en los Estados Unidos, acaba de volver de un viaje de ventas al Reino Unido. Durante el viaje, ella incurrido en algunos gastos personales de tarjeta de crédito para comidas. Nancy debe crear ahora un informe de gastos para conciliar los gastos.

Cuando Nancy introduce información en su informe de gastos, ella selecciona **Reino Unido** en el campo **País/región** en la página **Editar informe de gastos**. La lista de grupos de impuestos se filtra de modo que muestre solo los grupos que se aplican al Reino Unido. Nancy selecciona el grupo de impuestos del **Reino Unido 001** y después selecciona el grupo de impuestos de artículos **Comidas**. Después, ella agrega una nueva transacción para el alojamiento. Dado que sólo hay un grupo de impuestos y un grupo de impuestos de artículos en el Reino Unido, esta información se completa automáticamente en el informe de gastos de Nancy.

De acuerdo con la directiva de Contoso, todos los gastos deben tener una recepción coincidente. Por lo tanto, cuando Nancy guarda el informe de gastos, recibe un mensaje que indica que debe adjuntar un recibo para cada transacción que aparece en el informe de gastos. Nancy comprueba que ha adjuntado una imagen digital de cada recibo de transacción a su informe de gastos y luego envía el informe para aprobación. A continuación, envía los recibos en papel al equipo de procesamiento de la oficina administrativa. Este equipo enviará los datos de devolución del IVA al proveedor de terceros que archiva las devoluciones de IVA internacional de Contoso.

## <a name="make-sure-that-all-tax-information-is-complete-and-then-post-the-expense-report"></a>Asegúrese de que toda la información fiscal está completa y, a continuación, registre el informe de gastos

April, la coordinadora de proveedores de Contoso, debe especificar la información fiscal que falta en un informe de gastos antes de que éste pueda registrarse. Ella abre la página **Detalles de informe de gastos** y ve el informe de gastos aprobado de Nancy. A continuación, April abre el informe de gastos para ver los detalles de las transacciones. Observa que Nancy no especificó un grupo de impuestos de artículos para una de las transacciones. Puesto que esa información no se ha proporcionado, April no puede enviar el informe de gastos. Por lo tanto, April busca en la página **Configuraciones de impuestos** en Gestión de gastos y encuentra el grupo apropiado de impuestos de artículos para el país o región y el tipo de transacción. Ahora, April puede registrar el informe de gastos en la contabilidad general.

Cuando April registra el informe de gastos, se crea un elemento de trabajo recuperable de IVA. Este elemento de trabajo se asigna a un miembro del equipo de procesamiento de la oficina administrativa. Abril recibe un mensaje que confirma que ese registro fue correcto. Este mensaje también muestra el número de transacciones de IVA que se identificaron para la devolución.

## <a name="process-expenses-that-are-eligible-for-international-vat-recovery"></a>Procesar los gastos aptos para la devolución de IVA internacional

Arnie, miembro del equipo de servicio de procesamiento administrativo de Contoso, es el responsable de confirmar que toda la información necesaria para la devolución de IVA se incluye en los informes de gastos. Abre la página **Devolución de impuestos de gastos** y selecciona el informe de gastos que Nancy envió. Arnie comprueba que todas las recepciones necesarias están adjuntadas y que se han especificado los códigos correctos de impuestos de artículos y del grupo de ventas.

Cuando Arnie recibe los recibos en papel de Nancy, los coteja con los recibos digitales y cambia el estado del informe de gastos a **Listo para devolución**.

## <a name="send-vat-recovery-data-to-the-third-party-vendor-to-file-international-recovery-returns"></a>Enviar datos de devolución de IVA al proveedor de terceros para archivar la devolución internacional

Cuando Arnie puede enviar los datos del informe de gastos al proveedor de terceros que archivará la devolución de IVA, abre la página **Devolución de impuestos de gastos**. Filtra la página para ver solo los informes de gastos marcados como **Listo para devolución**. A continuación, selecciona **Archivo** &gt; **Exportar a Excel**. La información de IVA de los informes de gastos se exporta a una hoja de cálculo de Microsoft Excel. Arnie muestra esta hoja de cálculo al proveedor de terceros e incluye un mensaje que indica que los recibos de papel se han enviado por mensajero.

## <a name="process-expenses-for-domestic-vat-recovery"></a>Procesar los gastos de devolución de IVA nacional

Arnie debe comprobar que las transacciones del informe de gastos son aptas para la devolución de IVA y que los recibos digitales se han adjuntado a los informes. Para empezar a procesar los gastos aptos para la devolución nacional, Arnie abre la página **Devolución de impuestos de gastos** y selecciona el informe de gastos que necesita comprobarse. Comprueba que los recibos figuran a nombre de la empresa en lugar del empleado. Para la devolución del IVA, los recibos deben estar a nombre de la empresa. Arnie confirma que se han aplicado los códigos correctos del grupo de impuestos sobre las ventas y de impuestos de ventas de artículos.

Cuando Arnie recibe los recibos en papel, cambia el estado del informe de gastos a **Listo para devolución**. A continuación, puede presentar la devolución ante la autoridad fiscal adecuada. En este caso, la autoridad fiscal adecuada de Estados Unidos es Internal Revenue Service (IRS).
