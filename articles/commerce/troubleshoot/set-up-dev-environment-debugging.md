---
title: Configurar un ambiente de desarrollo de comercio electrónico para depurar frente a una máquina virtual de servidor minorista de nivel 1
description: Este artículo explica cómo configurar un ambiente de desarrollo de comercio electrónico para depurar frente a una máquina virtual (VM) de servidor minorista de nivel 1.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 64e03c742f7095e2e485f32ad534f2a755ddd062
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277889"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a>Configurar un ambiente de desarrollo de comercio electrónico para depurar frente a una máquina virtual de servidor minorista de nivel 1

[!include [banner](../../includes/banner.md)]

Este artículo explica cómo configurar un ambiente de desarrollo de comercio electrónico para depurar frente a una máquina virtual (VM) de servidor minorista de nivel 1.

## <a name="description"></a>Descripción

Los ambientes de nivel 1 de Microsoft Dynamics 365 Commerce se implementan normalmente para el tiempo de ejecución de Commerce (CRT) y el desarrollo de extensión de punto de venta (POS). Son ambientes independientes. Debido a la naturaleza de software como servicio (SaaS) de la arquitectura, no incluyen componentes de comercio electrónico.

En algunos escenarios, es posible que desee probar las llamadas a extensiones en un entorno de nivel 1, para poder depurar extensiones de componentes de comercio electrónico. Para conocer las instrucciones generales, consulte [Depurar con un entorno de desarrollo de Commerce de nivel 1](../e-commerce-extensibility/debug-tier-1.md).

Cuando depura frente en un entorno de nivel 1, debido a que el sitio ahora llama a un Retail Server diferente, las llamadas entre servidores pueden causar varios errores relacionados con la directiva de seguridad del contenido.

La siguiente ilustración muestra un ejemplo de error que puede ocurrir cuando se selecciona una variante en la página de detalles de un producto.

![Error cuando se selecciona una variante en la página de detalles de un producto.](media/unhandled-rejection-error.jpg)

La siguiente ilustración muestra un ejemplo de un error similar en las herramientas de depuración de un navegador (Herramientas de desarrollo F12). El mensaje de error menciona la violación de la directiva de directiva de seguridad de contenido.

![Error de las herramientas del depurador.](media/debugger-tools-error.JPG)

## <a name="resolution"></a>Resolución

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a>Deshabilite la directiva de seguridad de contenido para el sitio en el creador de sitios de Commerce

1. Seleccione el sitio en el que está trabajando.
1. Seleccione **Configuración** y después seleccione **Extensiones**.
1. En la pestaña **Directiva de seguridad de contenido**, seleccione **Deshabilitar la directiva de seguridad de contenido**.
1. Seleccione **Guardar y publicar**.

> [!NOTE]
> El inicio de sesión de empresa a consumidor (B2C) no funcionará en un entorno de desarrollo local. Sin embargo, puede utilizar los pagos de invitados o crear simulaciones de página para simular el inicio de sesión de un usuario, según sea necesario.

## <a name="additional-resources"></a>Recursos adicionales

[Introducción al desarrollo de extensibilidad en línea de comercio electrónico](../e-commerce-extensibility/sdk-getting-started.md)

[Administrar la directiva de seguridad de contenido (CSP) en el sitio de comercio electrónico](../manage-csp.md)
