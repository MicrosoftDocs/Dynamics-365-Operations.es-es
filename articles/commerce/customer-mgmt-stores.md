---
title: Gestión de clientes en tiendas
description: Este tema explica cómo los minoristas pueden habilitar las capacidades de gestión de clientes en el punto de venta (PDV) en Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4fd6039843be09ec706e45746d5724faa99a95e6
ms.sourcegitcommit: 3f59b15ba7b4c3050f95f2b32f5ae6d7b96e1392
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7563070"
---
# <a name="customer-management-in-stores"></a>Gestión de clientes en tiendas

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tema explica cómo los minoristas pueden habilitar las capacidades de gestión de clientes en el punto de venta (PDV) en Microsoft Dynamics 365 Commerce.

Es importante que los empleados de la tienda puedan crear y editar registros de clientes en el PDV. De esa manera, pueden capturar cualquier actualización de la información del cliente, como la dirección de correo electrónico, el número de teléfono y la dirección. Esta información es útil en sistemas posteriores, como el marketing, porque la efectividad de esos sistemas depende de la precisión de los datos de sus clientes.

Los asociados de ventas pueden activar el flujo de trabajo de creación de clientes desde dos puntos de entrada de PDV. Pueden seleccionar un botón que esté asignado a la operación **Agregar cliente**, o pueden seleccionar **Crear cliente** en la barra de la aplicación, en la página de resultados de búsqueda. En ambos casos, aparece el cuadro de diálogo **Nuevo cliente**, donde los asociados de ventas pueden introducir los detalles requeridos del cliente, como el nombre del cliente, la dirección de correo electrónico, el número de teléfono, la dirección y cualquier información adicional que sea relevante para la empresa. Esa información adicional se puede capturar utilizando los atributos del cliente que están asociados con el cliente. Para obtener más información sobre los atributos del cliente, consulte [Atributos del cliente](dev-itpro/customer-attributes.md).

Los asociados de ventas también pueden capturar direcciones de correo electrónico y números de teléfono secundarios. Además, pueden capturar la preferencia del cliente sobre la recepción de información de marketing a través de cualquiera de esas direcciones de correo electrónico o números de teléfono secundarios. Para habilitar esta capacidad, los minoristas deben activar la característica **Capturar varios correos electrónicos y números de teléfono y dar consentimiento para la comercialización de estos contactos** en el característica en el espacio de trabajo **Gestión de funciones** en la sede de Commerce (**Administración de sistemas \> Espacios de trabajo \> Gestión de funciones**).

## <a name="default-customer-properties"></a>Propiedades de cliente predeterminadas

Los minoristas pueden utilizar la página **Todas las tiendas** en la sede de Commerce (**Comercio minorista \> Canales \> Tiendas**) para asociar un cliente predeterminado a cada tienda. A continuación, Commerce copia las propiedades definidas para el cliente predeterminado en todos los registros de clientes nuevos que se crean. Por ejemplo, el cuadro de diálogo **Crear cliente** muestra las propiedades que se heredan del cliente predeterminado asociado con la tienda. Esas propiedades incluyen el **tipo de cliente**, el **grupo de clientes**, la **preferencia de recibo**, el **correo de recibo** la **divisa** y el **idioma**. Las **afiliaciones** (agrupaciones de clientes) también se heredan del cliente predeterminado. Sin embargo, las **dimensiones financieras** se heredan del grupo de clientes asociado con el cliente predeterminado, no del propio cliente predeterminado.

> [!NOTE]
> El valor **correo electrónico de recibo** se copia del cliente predeterminado solo si no se proporciona el ID de correo electrónico del recibo para los clientes recién creados. Esto significa que si el ID del correo electrónico del recibo está presente en el cliente predeterminado, todos los clientes creados desde el sitio de comercio electrónico obtendrán el mismo ID del correo electrónico del recibo, ya que no hay una interfaz de usuario para capturar el ID del correo electrónico del recibo del cliente. Le recomendamos que deje el campo **correo electrónico de recibo** en blanco para el cliente predeterminado de la tienda y solo utilícelo si tiene un proceso comercial que depende de la presencia de una dirección de correo electrónico de recibo. 

Los asociados de ventas pueden capturar varias direcciones para un cliente. El nombre y el número de teléfono del cliente se heredan de la información de contacto asociada a cada dirección. La ficha desplegable **Direcciones** de un registro de cliente incluye un campo **Objetivo** que los asociados de ventas pueden editar. Si el tipo de cliente es **Persona**, el valor predeterminado es **Inicio**. Si el tipo de cliente es **Organización**, el valor predeterminado es **Empresa**. Entre otros valores que admite este campo se encuentran **Hogar**, **Oficina** y **Buzón**. El valor del campo **País** de una dirección se hereda de la dirección principal que se especifica en la página **Unidad Operativa** en la sede de Commerce en **Administración de la organización \> Organizaciones \> Unidades operativas**.

## <a name="sync-customers-and-async-customers"></a>Clientes de modo sincrónico y de modo asincrónico

> [!IMPORTANT]
> Siempre que el PDV se desconecta, el sistema crea los clientes automáticamente de forma asincrónica, incluso si el modo de creación de clientes asincrónica está deshabilitado. Por lo tanto, independientemente de su selección entre la creación de clientes Sync y Async, los administradores de la sede de Commerce deben crear y programar un trabajo por lotes recurrente para el **P-trabajo**, el trabajo **Sincronice clientes y socios comerciales desde el modo asíncrono** (anteriormente llamado **Sincronice clientes y socios comerciales desde el modo asíncrono**) y el trabajo **1010**, de modo que los clientes de Async se conviertan en clientes de Sync en la sede de Commerce.

En Commerce, hay dos modos de creación de clientes: Sincrónico (o síncrono) y Asincrónico (o asíncrono). De forma predeterminada, los clientes se crean de forma sincrónica. Es decir, se crean en la sede de Commerce en tiempo real. El modo de creación de clientes Sincrónico es beneficioso porque los nuevos clientes se pueden buscar inmediatamente en todos los canales. Sin embargo, también tiene un inconveniente. Porque genera llamadas de [Commerce Data Exchange: servicio en tiempo real](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) a la sede de Commerce, el rendimiento puede verse afectado si se realizan muchas llamadas simultáneas de creación de clientes.

Si la opción **Crear cliente en modo asíncrono** está configurada en **Sí** en el perfil de funcionalidad de la tienda (**Comercio minorista y Commerce \> Configuración de canal \> Configuración de la tienda en línea \> Perfiles de funcionalidad**), las llamadas de servicio en tiempo real no se utilizan para crear registros de clientes en la base de datos. El modo de creación de clientes Asincrónico no afecta el rendimiento de la sede de Commerce. Se asigna un identificador único global temporal (GUID) a cada nuevo registro de cliente asincrónico y se utiliza como id. de cuenta de cliente. Este GUID no se muestra a los usuarios de PDV. En cambio, esos usuarios verán **Pendiente de sincronización** como id. de la cuenta del cliente. 

### <a name="convert-async-customers-to-sync-customers"></a>Convertir clientes de modo asincrónico y en clientes de modo sincrónico

Para convertir los clientes asincrónicos en clientes sincrónicos, primero debe ejecutar el **trabajo P** para enviar a los clientes asincrónicos a la sede de Commerce. Entonces ejecuta el trabajo **Sincronice clientes y socios comerciales desde el modo asíncrono** (anteriormente llamado **Sincronice clientes y socios comerciales desde el modo asíncrono**) para crear ID de cuenta de cliente. Finalmente, ejecute el trabajo **1010** para sincronizar los nuevos id. de cuenta de cliente con los canales.

### <a name="async-customer-limitations"></a>Limitaciones del cliente asíncrono

La funcionalidad del cliente asíncrono tiene actualmente las siguientes limitaciones:

- Los registros de clientes asíncronos no se pueden editar a menos que el cliente se haya creado en la sede de Commerce y el nuevo id. de cuenta de cliente se haya vuelto a sincronizar con el canal. Por lo tanto, la dirección no se puede guardar para un cliente Async hasta que ese cliente esté sincronizado con la sede de Commerce, porque la adición de una dirección de cliente se implementa internamente como una operación de edición en el perfil del cliente. Sin embargo, si **Habilite la creación asincrónica de direcciones de clientes.** está habilitado, las direcciones de los clientes también se pueden guardar para los clientes de Async.
- Las afiliaciones no se pueden asociar con clientes asincrónicos. Por lo tanto, los nuevos clientes asincrónicos no heredan las afiliaciones del cliente predeterminado.
- No se pueden emitir tarjetas de fidelización a los clientes asincrónicos a menos que el nuevo id. de cuenta de cliente se haya vuelto a sincronizar con el canal.
- Las direcciones de correo electrónico y los números de teléfono secundarios no se pueden capturar para los clientes asíncronos.

Aunque algunas de las limitaciones mencionadas anteriormente pueden hacer que se sienta inclinado a elegir la opción de cliente Sync para su negocio, el equipo de Commerce está trabajando para hacer que las capacidades del cliente de Async coincidan más estrechamente con las capacidades del cliente de Sync. Por ejemplo, a partir de la versión 10.0.22 de Commerce, una nueva función **Habilite la creación asincrónica de direcciones de clientes** que puede habilitar en el espacio de trabajo **Gestión de funciones** guarda de forma asincrónica las direcciones de clientes recién creadas tanto para los clientes de Sync como para los de Async. Para guardar estas direcciones en el perfil del cliente en la sede de Commerce, debe programar un trabajo por lotes periódico para el **trabajo P**, el trabajo **Sincronizar clientes y socios comerciales desde el modo asincrónico** y el trabajo **1010**, de modo que los clientes asincrónicos se conviertan en clientes sincrónicos en la sede de Commerce.

### <a name="customer-creation-in-pos-offline-mode"></a>Creación de clientes en modo sin conexión del PDV

Siempre que el PDV se desconecta, el sistema crea los clientes automáticamente de forma asincrónica, incluso si el modo de creación de clientes asincrónica está deshabilitado. Por lo tanto, como ya hemos mencionado, los administradores de la sede de Commerce deben crear y programar un trabajo por lotes periódico para el **trabajo P**, el trabajo **Sincronizar clientes y socios comerciales desde el modo asincrónico** y el trabajo **1010**, de modo que los clientes asincrónicos se conviertan en clientes sincrónicos en la sede de Commerce.

> [!NOTE]
> Si la opción **Filtrar tablas de datos de clientes compartidos** está configurada en **Sí** en la página **Esquema de canal de Commerce** (**Comercio minorista y Commerce \> Configuración de la sede \> Programador de Commerce \> Grupo de base de datos de canales**), los registros de clientes no se crean en el modo POS sin conexión. Para obtener más información, consulte [Exclusión de datos sin conexión](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Recursos adicionales

[Atributos de cliente](dev-itpro/customer-attributes.md)

[Exclusión de datos sin conexión](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
