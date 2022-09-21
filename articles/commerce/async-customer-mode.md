---
title: Modo de creación de clientes asincrónico
description: Este artículo describe el modo de creación de clientes asincrónico en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 95102936871e15f8e525abca736fa75927569b34
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473716"
---
# <a name="asynchronous-customer-creation-mode"></a>Modo de creación de clientes asincrónico

[!include [banner](includes/banner.md)]

Este artículo describe el modo de creación de clientes asincrónico en Microsoft Dynamics 365 Commerce.

En Commerce, hay dos modos de creación de clientes: sincrónico (o síncrono) y asincrónico (o asíncrono). De forma predeterminada, los clientes se crean de forma sincrónica. Es decir, se crean en Commerce headquarters en tiempo real. El modo de creación de clientes sincrónico es beneficioso porque los nuevos clientes se pueden buscar inmediatamente en todos los canales. Sin embargo, también tiene un inconveniente. Porque genera llamadas de [Commerce Data Exchange: servicio en tiempo real](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) a la sede de Commerce, el rendimiento puede verse afectado si se realizan muchas llamadas simultáneas de creación de clientes.

Si la opción **Crear cliente en modo asíncrono** está configurada en **Sí** en el perfil de funcionalidad de la tienda (**Comercio minorista y Commerce \> Configuración de canal \> Configuración de la tienda en línea \> Perfiles de funcionalidad**), las llamadas de servicio en tiempo real no se utilizan para crear registros de clientes en la base de datos. El modo de creación de clientes asincrónico no afecta el rendimiento de la sede de Commerce. Se asigna un identificador único global temporal (GUID) a cada nuevo registro de cliente asincrónico y se utiliza como id. de cuenta de cliente. Este GUID no se muestra a los usuarios de punto de venta (PDV). En cambio, esos usuarios verán **Pendiente de sincronización** como id. de la cuenta del cliente.

> [!IMPORTANT]
> Siempre que el PDV se desconecta, el sistema crea los clientes automáticamente de forma asincrónica, incluso si el modo de creación de clientes asincrónico está deshabilitado. Por lo tanto, independientement de la selección entre la creación sincrónica y asincrónica de clientes, los administradores de Commerce headquarters deben crear y programar un trabajo por lotes periódico para el **trabajo P**, el trabajo **Sincronizar clientes y socios comerciales desde el modo asincrónico** y el trabajo **1010**, de modo que los clientes asincrónicos se conviertan en clientes sincrónicos en Commerce headquarters.

## <a name="async-customer-limitations"></a>Limitaciones del cliente asíncrono

La funcionalidad del cliente asíncrono tiene actualmente la siguiente limitación:

- No se pueden emitir tarjetas de fidelización a los clientes asincrónicos a menos que el nuevo id. de cuenta de cliente se haya vuelto a sincronizar con el canal.

## <a name="async-customer-enhancements"></a>Mejoras del cliente asíncrono

Para ayudar a las organizaciones a usar el modo de creación de clientes asíncrono para administrar clientes y para ayudar a reducir las comunicaciones en tiempo real con Commerce headquarters, se implementaron las siguientes mejoras para brindar paridad entre los modos de sincronización y asíncrono en los canales. 

| Mejora de características | Versión de Commerce | Detalles de la característica |
|---|---|---|
| Mejoras en el rendimiento cuando la información del cliente se recupera de la base de datos del canal | 10.0.20 y posteriores | Para ayudar a mejorar el rendimiento, la entidad del cliente se divide en entidades más pequeñas. Luego, el sistema recupera solo la información requerida de la base de datos del canal. |
| Capacidad para crear una dirección de forma asíncrona durante el pago | 10.0.22 y posteriores | <p>Conmutador de características: **Habilitar creación asincrónica para direcciones de clientes**</p><p>Detalles de la característica:</p><ul><li>Capacidad para agregar direcciones sin realizar llamadas de servicio en tiempo real a Commerce headquarters</li><li>Capacidad para identificar direcciones de manera única en la base de datos del canal sin usar una ID de registro (valor **RecId**)</li><li>Seguimiento de marcas de tiempo para la creación de direcciones</li><li>Sincronización de direcciones en Commerce headquarters</li></ul><p>Esta función afecta tanto a los clientes de sincronización como a los clientes asíncronos. Para editar direcciones de forma asíncrona además de crearlas de forma asíncrona, debe habilitar la característica **Edición de clientes en modo asíncrono**.</p> |
| Habilite la paridad entre la creación de clientes sincrónicos y asincrónicos. | 10.0.24 y posteriores | <p>Conmutador de características: **Habilite la creación mejorada de clientes asincrónicos**</p><p>Detalles de la función: capacidad de capturar información adicional, como el título, las afiliaciones del cliente predeterminado y la información de contacto secundaria (número de teléfono y dirección de correo electrónico), mientras crea clientes de forma asíncrona</p> |
| Mensajes de error fáciles de usar | 10.0.28 y posteriores | Estas mejoras ayudan a mejorar los mensajes de error fáciles de usar si un usuario no puede editar información inmediatamente mientras la sincronización está en proceso. Usted habilita estas mejoras usando el ajuste **Permitir que ciertos elementos de la interfaz de usuario no puedan ser modificados por un cliente asíncrono** en **Configuración del sitio \> Extensiones** en el creador de sitios de Commerce. |
| Capacidad para editar la información del cliente de forma asíncrona | 10.0.29 y posteriores | <p>Conmutador de características: **Habilitar la edición de clientes en modo asincrónico**</p><p>Detalles de la función: capacidad para editar datos de clientes de forma asíncrona</p><p>Para obtener respuestas a preguntas comunes sobre problemas relacionados con la edición asincrónica de la información del cliente, consulte [Preguntas frecuentes sobre el modo de creación de clientes asíncrono](async-customer-mode-faq.md).</p> |

### <a name="feature-switch-hierarchy"></a>Jerarquía de conmutador de características

Debido a la jerarquía de los interruptores de función, antes de habilitar la característica **Habilitar la edición de clientes en modo asíncrono**, debe habilitar las siguientes características: 

- **Mejoras de rendimiento para pedidos de clientes y transacciones de clientes** – Esta característica ha sido obligatoria desde el lanzamiento de la versión 10.0.28 de Commerce. 
- **Habilitar la creación mejorada de clientes asincrónicos**
- **Habilitar creación asincrónica para direcciones de clientes**

Para obtener respuestas a preguntas comunes sobre solución de problemas, consulte [Preguntas frecuentes sobre el modo de creación de clientes asíncrono](async-customer-mode-faq.md). 

Después de habilitar las características mencionadas anteriormente, debe crear y programar un trabajo por lotes periódico para el **trabajo P**, el trabajo **Sincronizar clientes y socios comerciales desde el modo asincrónico** y el trabajo **1010**, de modo que los clientes asincrónicos se conviertan en clientes sincrónicos en la sede de Commerce.

### <a name="customer-creation-in-pos-offline-mode"></a>Creación de clientes en modo sin conexión del PDV

Como se ha mencionado anteriormente, siempre que el PDV se desconecta, el sistema crea los clientes automáticamente de forma asincrónica, incluso si el modo de creación de clientes asincrónica está deshabilitado. Por lo tanto, los administradores de la sede de Commerce deben crear y programar un trabajo por lotes periódico para el **trabajo P**, el trabajo **Sincronizar clientes y socios comerciales desde el modo asincrónico** y el trabajo **1010**, de modo que los clientes asincrónicos se conviertan en clientes sincrónicos en la sede de Commerce.

> [!NOTE]
> Si la opción **Filtrar tablas de datos de clientes compartidos** está configurada en **Sí** en la página **Esquema de canal de Commerce** (**Comercio minorista y Commerce \> Configuración de la sede \> Programador de Commerce \> Grupo de base de datos de canales**), los registros de clientes no se crean en el modo POS sin conexión. Para obtener más información, consulte [Exclusión de datos sin conexión](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Recursos adicionales

[Gestión de clientes en tiendas](customer-mgmt-stores.md)

[Convertir clientes de modo asincrónico y en clientes de modo sincrónico](convert-async-to-sync.md)

[Atributos de cliente](dev-itpro/customer-attributes.md)

[Exclusión de datos sin conexión](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
