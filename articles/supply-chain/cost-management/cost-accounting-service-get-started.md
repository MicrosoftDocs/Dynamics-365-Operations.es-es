---
title: Introducción al servicio de contabilidad de costes (vista previa privada)
description: Este tema proporciona detalles sobre licencias e instrucciones de instalación para el servicio de contabilidad de costes.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: a82af9e8ec1806f470103897389d0316d33a4a06
ms.sourcegitcommit: 7fec9dc5297ed6e687d4a0dff099922d59d6a830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "3372745"
---
# <a name="get-started-with-the-cost-accounting-service-private-preview"></a>Introducción al servicio de contabilidad de costes (vista previa privada)

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> La funcionalidad que se describe en este tema está disponible como parte de una versión preliminar privada. El contenido de este tema y la funcionalidad que describe están sujetos a cambios. Para obtener más información acerca las versiones preliminares, consulte [Preguntas frecuentes sobre actualizaciones del servicio de una versión](../../fin-ops-core/fin-ops/get-started/one-version.md).

El servicio de contabilidad de costos le permite realizar múltiples inventarios en los libros de contabilidad de costos que ha configurado. Usted asocia cada libro de contabilidad de costos a una *convención*. Una convención es una colección de los siguientes tipos de directivas contables:

- Objeto de coste
- Base de medida de entrada
- Suposición de flujo de costes
- Elemento de coste

> [!NOTE]
> Incluso después de haber activado el servicio de contabilidad de costos, aún puede hacer contabilidad de inventario en Microsoft Dynamics 365 Supply Chain Management, como siempre.

El servicio de contabilidad de costos es un complemento. Para que sus funciones estén disponibles, debe instalarlo desde Microsoft Dynamics Lifecycle Services (LCS). Por lo tanto, puede elegir evaluarlo en un entorno de prueba antes de activarlo para entornos de producción.

El servicio de contabilidad de costos no admite actualmente todas las funciones de administración de costos integradas en Dynamics 365 Supply Chain Management. Por lo tanto, es importante que evalúe si el conjunto de funciones que están disponibles actualmente cumplirá sus requisitos.

## <a name="how-to-get-the-cost-accounting-service-private-preview"></a><a name="sign-up"></a>Cómo obtener el servicio de contabilidad de costes (vista previa privada)

> [!IMPORTANT]
> Para usar el servicio de contabilidad de costos, debe tener un entorno de alta disponibilidad habilitado para LCS (no un entorno OneBox), y debe estar ejecutando Dynamics 365 Supply Chain Management versión 10.0.11 o posterior.

Para suscribirse a la vista previa privada del servicio de contabilidad de costes, envíe su id. de entorno LCS por correo electrónico a [Servicio de contabilidad de costes (vista previa privada)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29). Al admitirle en el programa, le enviaremos un correo electrónico de seguimiento que contendrá una clave beta del servicio de contabilidad de costes. Al recibir la clave beta, puede continuar [instalando el complemento](#install).

## <a name="licensing"></a>Licencias

El servicio de contabilidad de costos tiene licencia junto con las funciones estándar de la contabilidad de inventario que están disponibles para Supply Chain Management. No tiene que comprar una licencia adicional para usar el servicio de contabilidad de costos.

## <a name="install-the-add-in"></a><a name="install"></a>Instalar el complemento

Para usar el servicio de contabilidad de costos, instale el complemento de servicio de contabilidad de costos para Supply Chain Management como se describe en el siguiente procedimiento.

1. [Registrarse](#sign-up) para obtener el servicio de contabilidad de costes (vista previa privada).

1. Inicie sesión en LCS.

1. Vaya a **Administración de funciones de vista previa**.

1. Seleccione el signo más (**+**).

1. En el campo **Código**, introduzca su clave beta de complemento para el servicio de contabilidad de costos. (Debería haber recibido su clave por correo electrónico).

1. Seleccione **Desbloquear**.

1. Abra el entorno LCS donde desea agregar el servicio.

1. Vaya a **Detalles completos**.

1. Desplácese hacia abajo hasta la ficha desplegable **Complementos del entorno**.

1. Seleccione **Instalar un nuevo complemento**.

1. Seleccione **Servicio de contabilidad de costos**.

1. Siga la guía de instalación y acepte los términos y condiciones.

1. Seleccione **Instalar**.

1. En la ficha desplegable **Complementos de entorno**, debería ver que se está instalando el servicio de contabilidad de costos. Después de unos minutos, el estado debería cambiar de **Instalando** a **Instalado**. (Es posible que tenga que actualizar la página para ver este cambio). En ese momento, el servicio de contabilidad de costos está listo para usar.

## <a name="set-up-the-integration"></a>Configuración de la integración

Para configurar la integración entre el servicio de contabilidad de costos y Dynamics 365 Supply Chain Management:

1. Vaya a **Administración del sistema > Administración de funciones**.

1. Seleccione **Buscar actualizaciones**.

1. Abra la pestaña **Todas** y busque la función denominada *Servicio de contabilidad de costos*.

1. Seleccione **Habilitar ahora**.

1. Vaya a **Gestión de costes > Servicio de contabilidad de costes > Configuración > Parámetros del servicio de contabilidad de costes > Parámetros de integración**.

1. En el campo **ID de aplicación**, introduzca el siguiente código:<br> 08231eb2-a501-4edb-b3c5-aede5e5e0c3f

1. En el campo **Punto final del servicio de datos**, introduzca la siguiente URL:<br>https://operationsdataservice.operations365.dynamics.com/

1. En el campo **Punto final de contabilidad de costes**, introduzca la siguiente URL:<br>https://costaccountingservice.operations365.dynamics.com/

1. El servicio de contabilidad de costos ahora está listo para usar.

## <a name="related-resources"></a>Recursos relacionados

[Página principal del servicio de contabilidad de costes](cost-accounting-service-home.md)
