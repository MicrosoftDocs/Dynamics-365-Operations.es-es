---
title: Cancelar recomendaciones personalizadas
description: Este tema explica cómo puede permitir que los clientes opten por no recibir recomendaciones personalizadas en Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e822d0097443d7da347c29ebfa63ad6a2d7cbf8b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000646"
---
# <a name="opt-out-of-personalized-recommendations"></a>Cancelar recomendaciones personalizadas

[!include [banner](includes/banner.md)]

Este tema explica cómo puede permitir que los clientes opten por no recibir recomendaciones personalizadas en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Durante la creación de la cuenta, los nuevos clientes se configuran automáticamente para recibir recomendaciones personalizadas. Sin embargo, Dynamics 365 Commerce proporciona diversas formas para que los minoristas permitan a los usuarios optar por no recibir estas recomendaciones y restringir el procesamiento de sus datos personales. Los usuarios autenticados que opten por no recibir recomendaciones personalizadas dejarán de ver inmediatamente listas personalizadas. Además, todos los datos personales que se recopilan para la personalización se eliminarán de los modelos de recomendaciones personalizadas.

Para obtener más información acerca de las recomendaciones de producto personalizadas, consulte [Habilitar recomendaciones personalizadas](personalized-recommendations.md).

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a>Maneras para que los minoristas implementen una experiencia de exclusión voluntaria

Los minoristas tienen tres maneras de implementar una experiencia de exclusión voluntaria.

### <a name="opting-out-on-behalf-of-users"></a>Optar por no recibir en nombre de los usuarios

En la gestión de cuentas de la oficina administrativa de Commerce, los minoristas pueden optar por no participar en nombre de los usuarios.

1. Desde la página de inicio del área de operaciones, busque **todos los clientes**.
1. Busque y seleccione un cliente, y luego seleccione la ficha desplegable **Retail**.

    ![Ficha desplegable Retail](./media/Disablepersonalizationpart1.png)

1. Debajo de **Privacidad**, establezca la opción **Deshabilitar personalización** en **Sí**.

    ![Configuración de privacidad](./media/Disablepersonalizationpart2.png)

1. Seleccione **Guardar** y cierre la página.

### <a name="module-based-opt-out-experience"></a>Experiencia de exclusión voluntaria basada en módulos

Los minoristas pueden permitir a los usuarios autenticados optar por no recibir recomendaciones personalizadas. Para proporcionar esta experiencia de exclusión, agregue el módulo de exclusión del usuario a las páginas de perfil de la cuenta del cliente.

### <a name="custom-extensions"></a>Extensiones personalizadas

Los minoristas pueden crear sus propias extensiones para administrar la experiencia de exclusión voluntaria para los usuarios. Para más información, consulte [Llamar a las API de Retail Server](e-commerce-extensibility/call-retail-server-apis.md) y [Extensibilidad de canal en línea](e-commerce-extensibility/overview.md).

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a>Obtener una copia digital de datos de recomendaciones personalizadas en nombre de un usuario autenticado

Los clientes pueden querer obtener una copia digital de sus datos personales y también ver una vista exportada de los resultados de sus recomendaciones. Si un cliente solicita esta información, el minorista debe crear una extensión personalizada que llame a la interfaz de programación de aplicaciones (API) de Retail Server y solicite los resultados completos de la lista **Picking para usted**, en función del id. del cliente. Los resultados se pueden exportar en formato de valores separados por comas (CSV) y compartir con el cliente.

El siguiente ejemplo muestra cómo un minorista puede realizar esta tarea.

1. El minorista crea una extensión personalizada para extraer datos de recomendaciones personales en nombre del usuario. Para obtener información acerca de cómo crear módulos, clonar módulos existentes, llamar a las API de Retail Server y llamar a acciones de datos, consulte [Extensibilidad de canal en línea](e-commerce-extensibility/overview.md).
2. La extensión personalizada realiza una llamada a la acción de datos principal **get-recommendations** y le pasa la información requerida, de acuerdo con los requisitos de la lista. En el caso de la lista **Picking para usted**, la extensión debe pasar el nombre correcto de la lista y el id. del cliente a la acción de datos.

    Una forma de crear la extensión personalizada es clonar el módulo de colección de productos existente que se utiliza para devolver los resultados de las recomendaciones. Al clonar este módulo existente, un minorista puede modificar el código existente y agregar un nuevo botón que exporte los resultados de las recomendaciones a un archivo CSV. Para obtener más información, consulte [Clonar un módulo de biblioteca de módulos](e-commerce-extensibility/clone-starter-module.md) y [Módulos de colección de productos](product-collection-module-overview.md).

    Para obtener una vista completa de la biblioteca API de Retail Server, consulte [API de cliente y de consumidor de Retail Server](dev-itpro/retail-server-customer-consumer-api.md).

3. Después de crear la extensión personalizada, el minorista puede exportar un archivo CSV de todos los resultados de las recomendaciones, en función del id. de cliente único del usuario autenticado.
4. El minorista puede compartir el archivo CSV exportado que contiene la lista personalizada completa de productos recomendados con el usuario autenticado.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)
