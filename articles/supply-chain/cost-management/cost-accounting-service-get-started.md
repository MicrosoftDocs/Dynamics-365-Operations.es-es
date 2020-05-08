---
title: Introducción al servicio de contabilidad de costes
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
ms.openlocfilehash: cbbce7eaac264973bf0b95ad5175bf70ed2b4ae9
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "3276960"
---
# <a name="get-started-with-the-cost-accounting-service"></a>Introducción al servicio de contabilidad de costes

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> La funcionalidad que se describe en este tema está disponible como parte de una versión preliminar privada. El contenido de este tema y la funcionalidad que describe están sujetos a cambios. Para obtener más información acerca las versiones preliminares, consulte [Preguntas frecuentes sobre actualizaciones del servicio de una versión](../../fin-ops-core/fin-ops/get-started/one-version.md).

El servicio de contabilidad de costos le permite realizar múltiples inventarios en los libros de contabilidad de costos que ha configurado. Usted asocia cada libro de contabilidad de costos a una *convención*. Una convención es una colección de los siguientes tipos de políticas contables:

- Objeto de coste
- Base de medida de entrada
- Suposición de flujo de costes
- Elemento de coste

> [!NOTE]
> Incluso después de haber activado el servicio de contabilidad de costos, aún puede hacer contabilidad de inventario en Microsoft Dynamics 365 Supply Chain Management, como siempre.

El servicio de contabilidad de costos es un complemento. Para que sus funciones estén disponibles, debe instalarlo desde Microsoft Dynamics Lifecycle Services (LCS). Por lo tanto, puede elegir evaluarlo en un entorno de prueba antes de activarlo para entornos de producción.

El servicio de contabilidad de costos no admite actualmente todas las funciones de administración de costos integradas en Dynamics 365 Supply Chain Management. Por lo tanto, es importante que evalúe si el conjunto de funciones que están disponibles actualmente cumplirá sus requisitos.

## <a name="licensing"></a>Licencias

El servicio de contabilidad de costos tiene licencia junto con las características estándar de la contabilidad de inventario que están disponibles para Supply Chain Management. No tiene que comprar una licencia adicional para usar el servicio de contabilidad de costos.

## <a name="install-the-add-in"></a>Instalar el complemento

> [!IMPORTANT]
> Para usar el servicio de contabilidad de costos, debe tener un entorno de alta disponibilidad habilitado para LCS (no un entorno OneBox), y debe estar ejecutando Dynamics 365 Supply Chain Management versión 10.0.11 o posterior.

Para usar el servicio de contabilidad de costos, instale el complemento de servicio de contabilidad de costos para Supply Chain Management como se describe en el siguiente procedimiento.

1. Inicie sesión en LCS.

1. Vaya a **Administración de características de vista previa**.

1. Seleccione el signo más (**+**).

1. En el campo **Código**, ingrese su clave beta de complemento para el servicio de contabilidad de costos. (Debería haber recibido su clave por correo electrónico).

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

1. Vaya a **Administración del sistema > Administración de características**.

1. Seleccione **Buscar actualizaciones**.

1. Abra la pestaña **Todas** y busque la función denominada *Servicio de contabilidad de costos*.

1. Seleccione **Habilitar ahora**.

1. Vaya a **Gestión de costes > Servicio de contabilidad de costes > Configuración > Parámetros del servicio de contabilidad de costes > Parámetros de integración**.

1. En el campo **ID de aplicación**, ingrese el siguiente código:<br> 08231eb2-a501-4edb-b3c5-aede5e5e0c3f

1. En el campo **Punto final del servicio de datos**, ingrese la siguiente URL:<br>https://operationsdataservice.operations365.dynamics.com/

1. En el campo **Punto final de contabilidad de costes**, ingrese la siguiente URL:<br>https://costaccountingservice.operations365.dynamics.com/

1. El servicio de contabilidad de costos ahora está listo para usar.

## <a name="related-resources"></a>Recursos relacionados

[Página principal del servicio de contabilidad de costes](cost-accounting-service-home.md)
