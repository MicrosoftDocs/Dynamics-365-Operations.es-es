---
title: Procesamiento de recibos de gastos
description: Este tema proporciona información sobre el procesamiento de recibos mediante reconocimiento óptico de caracteres (OCR). Esta característica está diseñada para mejorar la experiencia del usuario cuando se crean informes de gastos en Microsoft Dynamics 365 Finance.
author: stsporen
manager: AnnBe
ms.date: 11/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 2e819521828b054f70476b1eb061ee08c486d09f
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113695"
---
# <a name="public-preview-expense-receipt-processing"></a>Versión preliminar pública: procesamiento de recibos de gastos

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


La entrada de gastos se ha mejorado mediante la introducción del procesamiento de reconocimiento óptico de caracteres (OCR) para los recibos. Esta característica está diseñada para mejorar la experiencia del usuario cuando se crean informes de gastos.

## <a name="key-features"></a>Funciones principales

- El nombre del comerciante, la fecha y el importe total se extraen de los recibos.
- La función intenta hacer coincidir los recibos no vinculados con las transacciones de gastos no vinculados.
- Los usuarios pueden crear transacciones de gastos ingresadas manualmente a partir de recibos.

## <a name="usage-examples"></a>Ejemplos de uso

- **Adjuntar automáticamente recibos que incluyan transacciones con tarjeta de crédito cuando se cree un informe de gastos**

    1. Abra el espacio de trabajo **Administración de gastos**.
    2. En la pestaña **Recibos**, verifique que haya recibos sin adjuntar. También puede cargar recibos en la pestaña **Ingresos**.
    3. En la pestaña **Gastos**, verifique que haya gastos sin adjuntar. Por lo general, el administrador de gastos importa estos gastos del proveedor de la tarjeta de crédito.
    4. Seleccione **Nuevo informe de gastos**. Tenga en cuenta que ahora también puede incluir gastos y recibos cuando cree un informe de gastos. Si agrega gastos y recibos, se activa la comparación automática de los recibos con los gastos.

- **Crear un gasto o conciliar un gasto de un recibo**

    1. En un informe de gastos, en la pestaña **Recibos**, adjunte un recibo seleccionando **Agregar recibos**.
    2. Debajo de la imagen cargada del recibo, observe las opciones **Crear** y **Conciliar**.

        - Seleccione **Crear** para crear una transacción de gastos introducida manualmente y completar los valores que se extraen del recibo.
        - Si selecciona **Conciliar**, el sistema intenta hacer coincidir un gasto existente con el recibo.

## <a name="installation"></a>Instalación

Esta característica funciona en combinación con **Informes de gastos reinventados** para ayudar a simplificar la experiencia de los gastos.

Para usar estas capacidades avanzadas de gastos, instale el complemento del Servicio de administración de gastos para Microsoft Dynamics 365 Finance y active las funciones en su instancia. Puede acceder al complemento desde su proyecto en Microsoft Dynamics Lifecycle Services (LCS).

1. Inicie sesión en LCS y abra el entorno deseado.
2. Vaya a **Detalles completos**.
3. Seleccione **Mantener** o descienda hasta la ficha desplegable **Complementos del entorno**.
4. Seleccione **Instalar un nuevo complemento**.
5. Seleccione **Servicio de administración de gastos**.
6. Siga la guía de instalación y acepte los términos y condiciones.
7. Seleccione **Instalar**.

En el espacio de trabajo **Administración de características**, active las siguientes características:

- Informes de gastos reinventados
- Conciliar automáticamente y crear gasto del recibo

Al activar estas características, ocurren las acciones siguientes:

- El espacio de trabajo **Gestión de gastos** existente se reemplaza con el nuevo espacio de trabajo.
- Un nuevo elemento de menú para la visibilidad del campo de gastos se agrega.
- Todavía puedes abrir la antigua página **Informes de gastos** yendo a **Gestión de gastos > Mis gastos > Informes de gastos**.
- Los flujos de trabajo y la aprobación aún le llevan a la página existente de los informes de gastos.
- Los recibos serán procesados a través de Microsoft Azure Cognitive Services y los metadatos se extraerán y agregarán.
- Se agrega una opción que le permite crear un informe de gastos que incluye recibos no asociados coincidentes.
- Una opción que se agrega a los informes de gastos permite crear una línea de gastos a partir de un recibo o intenta conciliar un recibo existente con una línea de gastos existente.

Para obtener más información sobre la función de informes de gastos reinventada, consulte [Informes de gastos reinventados](ExpenseWorkspaceNew.md).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Microsoft usa mis datos para sus modelos?**

No, Microsoft ha creado un modelo general de aprendizaje automático para su servicio de procesamiento de recibos. Este modelo no se basa en los recibos que carga.

**¿Dónde está disponible y se procesa esta función?**

Actualmente, solo en los Estados Unidos.

**¿Dónde van mis recibos?**

Finance se pondrá en contacto con Cognitive Services para extraer los datos de campo. Cognitive Services retendrá una copia de su recibo por hasta 24 horas mientras se procesa. Una vez completado el procesamiento, Cognitive Services eliminará el recibo. Los recibos todavía se almacenan en Finanzas.

Para más información, vea [Habilitar la comprensión de los recibos con la nueva funcionalidad del reconocedor de formularios](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).
