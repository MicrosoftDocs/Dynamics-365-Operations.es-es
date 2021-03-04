---
title: Configurar un entorno de evaluación de Dynamics 365 Commerce
description: Este tema explica cómo configurar un entorno de evaluación de Microsoft Dynamics 365 Commerce tras aprovisionarse.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6a1ae960f0f530104af7bdea9a8fcb78b01571f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415428"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a>Configurar un entorno de evaluación de Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tema explica cómo configurar un entorno de evaluación de Microsoft Dynamics 365 Commerce tras aprovisionarse.

## <a name="overview"></a>Información general

Complete los procedimientos de este tema solo después de aprovisionar el entorno de evaluación de Commerce. Para obtener información sobre cómo aprovisionar su entorno de evaluación de Commerce, vea [Provisión de un entorno de evaluación de Commerce](provisioning-guide.md).

Después de que su entorno de evaluación de Commerce se haya aprovisionado de principio a fin, se deben completar pasos de configuración posteriores al aprovisionamiento para poder comenzar a evaluar el entorno. Para completar estos pasos, debe usar Microsoft Dynamics Lifecycle Services (LCS) y Dynamics 365 Commerce.

## <a name="before-you-start"></a>Antes de comenzar

1. Inicie sesión en el [portal de LCS](https://lcs.dynamics.com).
1. Vaya a su proyecto.
1. En el menú superior, seleccione **Entornos hospedados en la nube**.
1. Seleccione el entorno en la lista.
1. En la información del entorno, a la derecha, seleccione **Iniciar sesión en entorno**. Se le enviará a la sede de Commerce.
1. Asegúrese de que la entidad jurídica **USRT** está seleccionada en la esquina superior derecha.

Durante las actividades posteriores al aprovisionamiento en la sede de Commerce, asegúrese de que la entidad jurídica **USRT** siempre esté seleccionada.

## <a name="configure-the-point-of-sale"></a>Configurar el punto de venta

### <a name="associate-a-worker-with-your-identity"></a>Asociar un trabajador con su identidad

Para asociar un trabajador con su identidad, siga estos pasos la central de Commerce.

1. Use el menú de la izquierda para ir a **Módulos \> Retail y Commerce \> Empleados \> Trabajadores**.
1. En la lista, busque y seleccione el registro siguiente: **000713 - Andrew Collette**.
1. En el panel Acciones, seleccione **Commerce**.
1. Seleccione **Asociar identidad existente**.
1. En el campo **Correo electrónico** a la derecha de **Buscar mediante correo electrónico**, escriba su dirección de correo electrónico.
1. Selección **Buscar**.
1. Seleccione el registro con su nombre.
1. Seleccione **Aceptar**.
1. Seleccione **Guardar**.

### <a name="activate-cloud-pos"></a>Activar PDV en la nube

Para activar Cloud PDV, siga estos pasos en LCS.

1. En el menú superior, seleccione **Entornos hospedados en la nube**.
1. Seleccione el entorno en la lista.
1. En la información del entorno, a la derecha, seleccione **Iniciar sesión punto de venta en la nube**.
1. Seleccione **Siguiente** para abrir el cuadro de diálogo **Antes de empezar**.
1. Deje el campo **URL de servidor** tal cual. Seleccione **Siguiente**.
1. Inicie sesión utilizando su cuenta de Microsoft Azure Active Directory ( Azure AD).
1. Debajo de **Nombre de la tienda**, seleccione **San Francisco** y luego **Siguiente**.
1. En **Caja registradora y dispositivo**, seleccione **SANFRAN-1**.
1. Seleccione **Activar**. Ha cerrado sesión y ha sido llevado a la página de inicio de sesión de POS.
1. Ahora puede iniciar sesión en la experiencia de Cloud PDV mediante el id. de operador **000713** y contraseña **123**.

## <a name="set-up-your-site-in-commerce"></a>Configurar su sitio en Commerce

Para comenzar a configurar su sitio de evaluación en Commerce, siga estos pasos.

1. Inicie sesión en el generador de sitios utilizando la URL de la que tomó nota cuando inicializó el comercio electrónico durante el aprovisionamiento (consulte [Inicializar comercio electrónico](provisioning-guide.md#initialize-e-commerce)).
1. Seleccione el sitio de **Fabrikam** para abrir el cuadro de diálogo de configuración del sitio.
1. Seleccione el dominio que ingresó cuando inicializó el comercio electrónico.
1. Como canal predeterminado seleccione **Tienda en línea extendida de Fabrikam**. (Asegúrese de seleccionar la tienda en línea **extendida**).
1. Seleccione **es-es** como idioma predeterminado.
1. Deje el valor del campo **Ruta** tal cual está.
1. Seleccione **Aceptar**. Aparece la lista de páginas del sitio.

## <a name="enable-jobs"></a>Habilitar trabajos

Para activar la gestión de trabajos en Commerce, siga estos pasos.

1. Inicie sesión en el entorno (sede).
1. Use el menú de la izquierda, para ir a **Retail y Commerce \> Consultas e informes \> Trabajos por lotes**.

    Los pasos restantes de este procedimiento deben completarse para cada uno de los siguientes trabajos:

    * Procesar notificación por correo electrónico de pedido comercial
    * Disponibilidad del producto
    * P-0001
    * Trabajo de sincronización de pedidos

1. Use el filtro rápido para buscar el trabajo por su nombre.
1. Si el estado del trabajo es **En ejecución**, siga estos pasos:

    1. Seleccione el registro.
    1. En el panel de acciones, en la pestaña **Trabajo por lotes**, seleccione **Cambiar estado**.
    1. Haga clic en **Cancelar** y, a continuación, en **Aceptar**.

Opcionalmente, también puede establecer el intervalo de recurrencia en un (1) minuto para los siguientes trabajos:

* Procesar trabajo de notificación por correo electrónico de pedido comercial
* Trabajo P-0001
* Trabajo de sincronización de pedidos

### <a name="run-full-data-synchronization"></a>Ejecutar sincronización de datos completa

Para ejecutar la sincronización de datos completa en Commerce, siga estos pasos en la central de Commerce.

1. Use el menú de la izquierda, para ir a **Módulos \> Retail y Commerce \> Configuración de sede central \> Programador de Commerce \> Base de datos de canales**.
1. Seleccione el canal denominado **scXXXXXXXXX**.
1. En el panel de acciones, seleccione **Sincronización de datos completa**.
1. Introduzca **9999** como la programación de distribución.
1. Seleccione **Aceptar**.
1. Seleccione **Aceptar**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Probar la información de la tarjeta de crédito para realizar compras de prueba

Para realizar transacciones de prueba en el sitio, puede usar esta información de la tarjeta de crédito de prueba:

- **Número de tarjeta:** 4111-1111-1111-1111
- **Fecha de vencimiento:** 10/20
- **Código de seguridad de la tarjeta (CVV):** 737

> [!IMPORTANT]
> Bajo ninguna circunstancia intente usar la información de un tarjeta de crédito real en el sitio de prueba.

## <a name="next-steps"></a>Pasos siguientes

Después de completar los pasos de aprovisionamiento y configuración, podrá comenzar a usar su entorno de evaluación. Use la URL del creador de sitios de Commerce para acceder a la experiencia de creación. Use la URL del sitio de Commerce para ir la experiencia del sitio de cliente minorista.

Para configurar características opcionales para su entorno de evaluación de Commerce, consulte [Configurar características opcionales para un entorno de evaluación de Commerce](cpe-optional-features.md).

## <a name="additional-resources"></a>Recursos adicionales

[Información general del entorno de evaluación de Dynamics 365 Commerce](cpe-overview.md)

[Aprovisionar un entorno de evaluación de Dynamics 365 Commerce](provisioning-guide.md)

[Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce](cpe-optional-features.md)

[Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce](cpe-bopis.md)

[Preguntas frecuentes sobre el entorno de evaluación de Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal de Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sitio web de Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]