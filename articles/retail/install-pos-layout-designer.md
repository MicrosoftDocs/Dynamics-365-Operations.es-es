---
title: Instalar el diseñador de punto de venta (TPV) de Retail
description: Puede usar el diseñador de un solo clic para diseñar diferentes estructuras de Retail Modern POS (MPOS) y Cloud POS, tanto en modo horizontal como vertical, para tiendas, registros, cajeros y directores.
author: athinesh99
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 219684
ms.assetid: 2e2c4eea-c6e2-4912-9832-a6b22416e39f
ms.search.region: Global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7fc5b48b71816b662f016f4a2d909526da0595f4
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "327651"
---
# <a name="install-the-retail-point-of-sale-pos-layout-designer"></a>Instalar el diseñador de punto de venta (TPV) de Retail

[!include [banner](includes/banner.md)]

Puede usar el diseñador de un solo clic para diseñar diferentes estructuras de Retail Modern POS (MPOS) y Cloud POS, tanto en modo horizontal como vertical, para tiendas, registros, cajeros y directores.

La interfaz de diseño gráfico del PDV moderno (MPOS) o PDV en la Nube (Cloud POS) se controla mediante el diseño de caja registradora. Un diseño controla la posición de los diversos objetos. Entre los ejemplos se incluyen el diseño total, de cuadrícula de artículos, de cliente, de pago y el de varios botones de menú. Los diseños incluyen también el aspecto general de la interfaz de ventas que se muestra a los trabajadores.

## <a name="install-the-one-click-designer"></a>Instalar el diseñador de un solo clic

1. En Microsoft Dynamics 365 for Retail, utilice el menú de la parte superior izquierda para ir a **Venta al por menor** **y comercio** &gt; **Instalación de canal** &gt; **Instalación del PDV** &gt; **PDV** &gt; **Diseños de pantalla**.
2. Seleccione cualquier diseño que tenga el tipo de aplicación de **PDV moderno para Windows** o **PDV en la Nube**, y haga clic en **Diseñador de estructura**.
3. En la barra de notificación que aparece en la parte inferior de la ventana de Internet Explorer, haga clic en **Abrir** para empezar a instalar el diseñador de un solo clic. (La barra de notificación puede aparecer en un lugar diferente en otros exploradores.)
4. En el cuadro de mensaje **Ejecución de la aplicación: advertencia de seguridad** que aparece, haga clic en **Ejecutar** para instalar el host del diseñador de ventas al por menor. Un indicador de progreso muestra el progreso de la instalación.
5. Después de que la instalación esté completada, en la página **Iniciar sesión** escriba el nombre de usuario y la contraseña de Microsoft Dynamics 365 for Retail y haga clic en **Iniciar sesión** para iniciar el diseñador.
6. Cuando se lleve a cabo una validación de sus credenciales y se inicie el diseñador, puede empezar a diseñar su propia estructura o a modificar el diseño existente.

    [![Diseño en el diseñador de un solo clic](./media/screenlayoutdesign_mposdownload-1024x664.png)](./media/screenlayoutdesign_mposdownload.png)

## <a name="troubleshoot-the-installation-of-the-layout-designer"></a>Solución de problemas de la configuración del Diseñador

- Al hacer clic en **Diseñador**, el indicador para descargar (o ejecutar) el instalador no aparece, o los ajustes actuales de seguridad no le permiten descargar el archivo. 

    **Soluciones:**

    - En Internet Explorer, asegúrese de que el bloqueador de elementos emergentes está deshabilitado para este sitio. Haga clic en **Ajustes** &gt; **Opciones** &gt; **Privacidad** &gt; **Buscar bloqueador de elementos emergentes**, y cambie los ajustes, si es necesario.
    - En Internet Explorer, agregue la dirección URL Dynamics 365 for Retail a sus sitios de confianza. Haga clic en **Ajustes** &gt; **Opciones** &gt; **Seguridad** &gt; **Sitios de confianza** &gt; **Sitios** &gt; **Añadir**.

- El programa no se inicia y le ha indicado que se ponga en contacto con el proveedor.

    **Solución:** en Internet Explorer, agregue la dirección URL Dynamics 365 for Retail a sus sitios de confianza. Haga clic en **Ajuste** &gt; **Opciones** &gt; **Seguridad** &gt; **Sitios de confianza** &gt; **Sitios** &gt; **Añadir**.

**Problema conocido:** El diseñador no funciona correctamente en los navegadores Google Chrome y Mozilla Firefox. Estamos trabajando para solucionar este problema.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar, descargar, instalar y activar Retail Modern POS](retail-modern-pos-device-activation.md)
