---
title: Modo de creación de clientes asincrónico
description: Este artículo describe el modo de creación de clientes asincrónico en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 4ca63fe06a804035e976a3432454078c1cca0020
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880149"
---
# <a name="asynchronous-customer-creation-mode"></a>Modo de creación de clientes asincrónico

[!include [banner](includes/banner.md)]

Este artículo describe el modo de creación de clientes asincrónico en Microsoft Dynamics 365 Commerce.

En Commerce, hay dos modos de creación de clientes: sincrónico (o síncrono) y asincrónico (o asíncrono). De forma predeterminada, los clientes se crean de forma sincrónica. Es decir, se crean en la sede de Commerce en tiempo real. El modo de creación de clientes sincrónico es beneficioso porque los nuevos clientes se pueden buscar inmediatamente en todos los canales. Sin embargo, también tiene un inconveniente. Porque genera llamadas de [Commerce Data Exchange: servicio en tiempo real](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) a la sede de Commerce, el rendimiento puede verse afectado si se realizan muchas llamadas simultáneas de creación de clientes.

Si la opción **Crear cliente en modo asíncrono** está configurada en **Sí** en el perfil de funcionalidad de la tienda (**Comercio minorista y Commerce \> Configuración de canal \> Configuración de la tienda en línea \> Perfiles de funcionalidad**), las llamadas de servicio en tiempo real no se utilizan para crear registros de clientes en la base de datos. El modo de creación de clientes asincrónico no afecta el rendimiento de la sede de Commerce. Se asigna un identificador único global temporal (GUID) a cada nuevo registro de cliente asincrónico y se utiliza como id. de cuenta de cliente. Este GUID no se muestra a los usuarios de punto de venta (PDV). En cambio, esos usuarios verán **Pendiente de sincronización** como id. de la cuenta del cliente.

> [!IMPORTANT]
> Siempre que el PDV se desconecta, el sistema crea los clientes automáticamente de forma asincrónica, incluso si el modo de creación de clientes asincrónico está deshabilitado. Por lo tanto, independientemente de su selección entre la creación de clientes sincrónica o asincrónica, los administradores de la sede de Commerce deben crear y programar un trabajo por lotes recurrente para el **Trabajo P**, el trabajo **Sincronice clientes y socios comerciales desde el modo asíncrono** (anteriormente llamado **Sincronice clientes y socios comerciales desde el modo asíncrono**) y el trabajo **1010**, de modo que los clientes asincrónicos se conviertan en clientes de sincrónicos en la sede de Commerce.

## <a name="async-customer-limitations"></a>Limitaciones del cliente asíncrono

La funcionalidad del cliente asíncrono tiene actualmente las siguientes limitaciones:

- Los registros de clientes asíncronos no se pueden editar a menos que el cliente se haya creado en la sede de Commerce y el nuevo id. de cuenta de cliente se haya vuelto a sincronizar con el canal.
- No se pueden emitir tarjetas de fidelización a los clientes asincrónicos a menos que el nuevo id. de cuenta de cliente se haya vuelto a sincronizar con el canal.

## <a name="async-customer-enhancements"></a>Mejoras del cliente asíncrono

A partir de la versión 10.0.24 de Commerce, puede habilitar la característica **Habilitar la creación de clientes asíncronos mejorada** en el espacio de trabajo **Administración de características**. Esta característica cierra la brecha entre los modos de creación de clientes asíncronos y síncronos en el PDV y comercio electrónico de las siguientes maneras:

- Las afiliaciones no se pueden asociar con clientes asincrónicos.
- Se puede agregar títulos a los clientes asincrónicos.
- Las direcciones de correo electrónico y los números de teléfono secundarios se pueden capturar para los clientes asíncronos.

A partir de la versión 10.0.22 de Commerce, puede habilitar la característica **Habilite la creación asincrónica de direcciones de clientes** en el espacio de trabajo **Administración de características**. Esta característica permite que las direcciones de clientes recién creadas se guarden de forma asincrónica tanto para los clientes síncronos como para los clientes asíncronos.

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
