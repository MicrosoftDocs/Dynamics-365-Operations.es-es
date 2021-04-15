---
title: Configuraciones de solicitud de proveedor
description: Este tema describe los campos que hay que rellenar en una nueva solicitud del proveedor.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: a78ec681ff9bfe9f7792da04553e4b543bf4a183
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809311"
---
# <a name="vendor-request-configurations"></a>Configuraciones de solicitud de proveedor
[!include [banner](../includes/banner.md)]

Para completar una solicitud del proveedor, una persona de contacto del proveedor debe completar el asistente de registro del proveedor potencial.

En el formulario **Configuraciones de la solicitud del proveedor**, puede crear perfiles que especifiquen campos necesarios y campos visibles en el asistente de registro del proveedor potencial.

El asistente de registro del proveedor comenzará por preguntar al usuario del proveedor potencial en qué país/región opera el proveedor. Esta información determina la configuración aplicable. Si no se define ninguna configuración específica para un país o región, se usará una configuración predeterminada.

### <a name="set-up-a-vendor-request-configuration"></a>Establecer la configuración de la solicitud del proveedor

De forma predeterminada, hay una configuración del proveedor disponible en el formulario Configuraciones de la solicitud del proveedor.

No es posible selecionar el país/regiones para la configuración predeterminada, por lo que la sección **Países o regiones** no se puede cambiar.

1. Haga click en **Adquisición y abastecimiento** > **Configuración** > **Proveedores** y, a continuación haga click en **Configuraciones de la solicitud del proveedor**.
2. Haga clic en la pestaña **Campos** para establecer el estado de los campos mencionados.
3. Oculto (no visible)
4. Se muestra (visible pero no obligatorio)
5. Necesario (visible y obligatorio)
6. Haga clic en la pestaña **Contenido** para especificar si el texto se va a mostrar en el asistente y si debe haber una confirmación que el usuario del proveedor potencial deba aceptar antes de ir al paso siguiente del asistente. Se solicitará la aceptación de los términos y condiciones para que el usuario pueda continuar.

También puede introducir un mensaje de confirmación que se mostrará cuando concluya el asistente y puede agregar uno o varios cuestionarios.

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a>Creación de una configuración de proveedor para un país o región específicos
1.  Haga click en **Adquisición y abastecimiento** > **Configuración** > **Proveedores** y, a continuación haga click en **Configuraciones de la solicitud del proveedor**.
2.  Haga click en **Nuevo** para crear una nueva configuración y proporcione un nombre para la configuración.
3.  Haga clic en **Guardar**.
4.  Abra la pestaña **País/regiones** para seleccionar el país/región para el que se usará la configuración.
5.  Complete la configuración siguiendo las directrices para la configuración predeterminada.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]