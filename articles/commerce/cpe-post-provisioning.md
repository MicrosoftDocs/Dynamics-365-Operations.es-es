---
title: Configurar un entorno de espacio aislado de Dynamics 365 Commerce
description: Este artículo explica cómo configurar un entorno de espacio aislado de Microsoft Dynamics 365 Commerce tras aprovisionarlo.
author: josaw1
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: ae6a8c63721ac32f525e1846a10c0b2caeb08f9f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270382"
---
# <a name="configure-a-dynamics-365-commerce-sandbox-environment"></a>Configurar un entorno de espacio aislado de Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este artículo explica cómo configurar un entorno de espacio aislado de Microsoft Dynamics 365 Commerce tras aprovisionarlo.

Complete los procedimientos de este artículo solo después de aprovisionar el entorno de espacio aislado de Commerce. Para obtener información sobre cómo aprovisionar su entorno de espacio aislado de Commerce, vea [Provisión de un entorno de espacio aislado de Commerce](provisioning-guide.md).

Después de que su entorno de espacio aislado de Commerce se haya aprovisionado de principio a fin, se deben completar pasos de configuración posteriores al aprovisionamiento antes de que pueda comenzar a usar el entorno. Para completar estos pasos, debe usar Microsoft Dynamics Lifecycle Services (LCS) y Dynamics 365 Commerce.

## <a name="before-you-start"></a>Antes de comenzar

1. Inicie sesión en el [portal de LCS](https://lcs.dynamics.com).
1. Vaya a su proyecto.
1. Seleccione el entorno en la lista.
1. En la información del entorno, a la derecha, seleccione **Iniciar sesión en entorno**. Se le enviará a la sede de Commerce.
1. Asegúrese de que la entidad jurídica **USRT** está seleccionada en la esquina superior derecha. Esta entidad jurídica se ha preconfigurado en los datos de demostración.
1. Vaya a **Parámetros de Commerce \> Parámetros de configuración** y asegúrese de que hay una entrada para **ProductSearch.UseAzureSearch** y que el valor está establecido en **verdadero**. Si falta esta entrada, agréguela y establezca el valor en **verdadero**.
1. Vaya a **Retail y Commerce \> Configuración de sede central \> Programador de Commerce \> Inicializar programador de Commerce**. En el menú flotante **Inicializar programador de Commerce**, establezca la opción **Eliminar configuración existente** en **Sí** y, a continuación, seleccione **Aceptar**.
1. Para que los canales de tienda y comercio electrónico funcionen correctamente, deben agregarse a Commerce Scale Unit. Vaya a **Venta minorista y comercio \> Configuración de sede central \> Planificador de comercio \> Base de datos de canales** y seleccione Commerce Scale Unit en el panel izquierdo. En la ficha desplegable **Canal comercial**, agregue los canales **Tienda en línea AW**, **Tienda en línea AW Business** y **Tienda en línea ampliada de Fabrikam** si planea usar esos canales de comercio electrónico. También puede agregar tiendas minoristas si va a utilizar puntos de venta (PDV) (por ejemplo, **Seattle**, **San Francisco** o **San Jose**).
1. Para asegurarse de que todos los cambios estén sincronizados con la base de datos de canales, seleccione **Base de datos de canales \> Sincronización de datos completa** para Commerce Scale Unit.

Durante las actividades posteriores al aprovisionamiento en la sede de Commerce, asegúrese de que la entidad jurídica **USRT** siempre esté seleccionada.

## <a name="configure-the-point-of-sale"></a>Configurar el punto de venta

### <a name="associate-a-worker-with-your-identity"></a>Asociar un trabajador con su identidad

Para asociar un trabajador con su identidad, siga estos pasos la central de Commerce.

1. Use el menú de la izquierda para ir a **Módulos \> Retail y Commerce \> Empleados \> Trabajadores**.
1. En la lista, busque y seleccione el registro siguiente: **000713 - Andrew Collette**. Este usuario de ejemplo está asociado con la tienda de San Francisco que se usará en la siguiente sección.
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

## <a name="set-up-your-e-commerce-sites"></a>Configurar sus sitios de comercio electrónico

Hay tres sitios de demostración de comercio electrónico disponibles: Fabrikam, Adventure Works y Adventure Works Business. Siga los pasos a continuación para configurar cada sitio de demostración.

1. Inicie sesión en el generador de sitios utilizando la URL de la que tomó nota cuando inicializó el comercio electrónico durante el aprovisionamiento (consulte [Inicializar comercio electrónico](provisioning-guide.md#initialize-e-commerce)).
1. Seleccione el sitio (**Fabrikam**, **Adventure Works** o **Adventure Works Business**) para abrir el cuadro de diálogo de configuración del sitio.
1. Seleccione el dominio que ingresó cuando inicializó Commerce.
1. En la sede, seleccione el canal de tienda en línea preconfigurado (**Tienda en línea ampliada de Fabrikam**, **Tienda en línea AW** o **Tienda en línea AW Business**) que corresponde al canal predeterminado.
1. Seleccione **es-es** como idioma predeterminado.
1. Configure los campos de la ruta de acceso. Esto se puede dejar en blanco para un solo sitio, pero deberá configurarse si se usa el mismo nombre de dominio para varios sitios. Por ejemplo, si el nombre de dominio es `https://www.constoso.com`, puede usar una ruta en blanco para Fabrikam (`https://contoso.com`) y, luego, usar "aw" para Adventure Works (`https://contoso.com/aw`) y "awbusiness" para el sitio de negocios de Adventure Works (`https://contoso.com/awbusiness`).
1. Seleccione **Aceptar**. Aparece la lista de páginas del sitio.
1. También puede repetir los pasos 2 a 7 para configurar los otros sitios de demostración según sea necesario.

## <a name="enable-jobs"></a>Habilitar trabajos

Para activar la gestión de trabajos en Commerce, siga estos pasos.

1. Inicie sesión en el entorno de sede.
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

1. Si el estado del trabajo es **Retenido**, realice los siguientes pasos:

    1. Seleccione el registro.
    1. En el panel de acciones, en la pestaña **Trabajo por lotes**, seleccione **Cambiar estado**.
    1. Seleccione **Esperando** y, a continuación, seleccione **Aceptar**.

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
- **Fecha de vencimiento:** 10/30
- **Código de seguridad de la tarjeta (CVV):** 737

> [!IMPORTANT]
> Bajo ninguna circunstancia intente usar la información de un tarjeta de crédito real en el sitio de prueba.

## <a name="next-steps"></a>Pasos siguientes

Después de completar los pasos de aprovisionamiento y configuración, podrá comenzar a usar su entorno de espacio aislado. Use la URL del creador de sitios de Commerce para acceder a la experiencia de creación. Use la URL del sitio de Commerce para ir la experiencia del sitio de cliente minorista.

Para configurar características opcionales para su entorno de espacio aislado de Commerce, consulte [Configurar características opcionales para un entorno de espacio aislado de Commerce](cpe-optional-features.md).

Para permitir que los usuarios de comercio electrónico inicien sesión en el sitio de comercio electrónico, se requiere una configuración adicional para habilitar la autenticación del modelo B2C (empresa a consumidor) de Azure Active Directory. Para obtener instrucciones, consulte [Configurar un inquilino B2C en Commerce](set-up-b2c-tenant.md).

## <a name="troubleshooting"></a>Solución de problemas

### <a name="site-builder-channel-list-is-empty-when-configuring-site"></a>La lista de canales del generador de sitios está vacía al configurar el sitio

Si el generador de sitios no muestra ningún canal de tienda en línea, en la sede central asegúrese de que los canales se hayan agregado a la Commerce Scale Unit como se describe en la sección anterior [Antes de comenzar](#before-you-start). También, ejecute **Inicializar programador de Commerce** con el valor de **Eliminar configuración existente** establecido en **Sí**.  Una vez completados estos pasos, en la página **Base de datos de canales** (**Venta minorista y comercio \> Configuración de sede central \> Planificador de comercio \> Base de datos de canales**), ejecute el trabajo **9999** en la Commerce Scale Unit.

### <a name="color-swatches-are-not-rendering-on-the-category-page-but-are-rendering-on-the-product-details-page-pdp-page"></a>Las muestras de color no se muestran en la página de categoría, pero sí en la página de detalles del producto (PDP)

Siga estos pasos para asegurarse de que las muestras de color y tamaño estén configuradas para que se puedan refinar.

1. En la sede central, vaya a **Retail y Commerce \> Configuración de canal \> Categorías de canal y atributos de producto**.
1. En el panel izquierdo, seleccione el canal de la tienda en línea y luego seleccione **Configurar metadatos de atributos**.
1. Establezca la opción **Mostrar atributo en el canal** en **Sí**, establezca la opción **Se puede refinar** en **Sí** y luego seleccione **Guardar**. 
1. Regrese a la página del canal de la tienda en línea y luego seleccione **Publicar actualizaciones de canal**.
1. Vaya a **Venta minorista y comercio \> Configuración de sede central \> Planificador de comercio \> Base de datos de canales** y ejecute el trabajo **9999** en la Commerce Scale Unit.

### <a name="business-features-dont-appear-to-be-turned-on-for-the-adventureworks-business-site"></a>Las características comerciales no parecen estar activadas para el sitio empresarial de AdventureWorks

En la sede central, asegúrese de que el canal de la tienda en línea esté configurado con el **Tipo de cliente** establecido en **B2B**. Si el **Tipo de cliente** se establece en **B2C**, se debe crear un nuevo canal, ya que el canal existente no se puede editar. 

Los datos de demostración enviados en Commerce versión 10.0.26 y anteriores tenían un error en el que el canal de la **Tienda en línea AW Business** estaba mal configurado. La solución consiste en crear un nuevo canal con los mismos ajustes y configuraciones excepto para **Tipo de cliente**, que debe establecerse en **B2B**.

## <a name="additional-resources"></a>Recursos adicionales

[Aprovisionar un entorno de espacio aislado de Dynamics 365 Commerce](provisioning-guide.md)

[Configurar características opcionales para un entorno de espacio aislado de Dynamics 365 Commerce](cpe-optional-features.md)

[Configurar BOPIS en un entorno de espacio aislado de Dynamics 365 Commerce](cpe-bopis.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal de Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sitio web de Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
