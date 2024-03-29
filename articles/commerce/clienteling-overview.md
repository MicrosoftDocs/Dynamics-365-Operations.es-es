---
title: Información general de relación con los clientes
description: En este artículo se proporciona una visión general de las nuevas capacidades de clienteling disponibles en la aplicación de tienda.
author: bebeale
ms.date: 11/16/2022
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom:
- "260624"
- intro-internal
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-01
ms.openlocfilehash: fc7daeb27c25efa21fd34b0456af8892074056d5
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785055"
---
# <a name="clienteling-overview"></a>Visión general de relación con los clientes

[!include [banner](includes/banner.md)]


Muchos minoristas, especialmente los minoristas especializados de alta gama, desean que sus socios de ventas formen relaciones a largo plazo con sus clientes principales. Se espera que los socios sepan los gustos y las aversiones, el historial de compras, las preferencias de productos, y las fechas importantes de estos clientes, como aniversarios y cumpleaños. Los socios necesitan un lugar en el que pueden obtener esta información y fácilmente encontrarla cuando sea necesario. Si esta información está disponible en una única vista, los asociados pueden dedicarse fácilmente a los clientes que cumplan criterios específicos. Por ejemplo, pueden encontrar todos los clientes que prefieran adquirir mochilas, o los clientes que tengan un evento importante que se aproxime, por ejemplo un cumpleaños o un aniversario.

El siguiente video recorre un escenario de ejemplo de clientelización en Dynamics 365 Commerce.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5bMSP]

## <a name="client-book"></a>Libro de clientes

En Microsoft Dynamics 365 Commerce, los minoristas pueden usar la funcionalidad del libro de clientes para ayudar a los socios de la tienda a crear relaciones a largo plazo con los clientes principales.

El libro de clientes incluye tarjetas de clientes que muestran la información de contacto para cada cliente, así como tres propiedades más definidas por el distribuidor y configuradas en la sede central. Los minoristas pueden decidir los tres aspectos más importantes que los socios de ventas deben saber sobre los clientes. Por ejemplo, un minoristas de joyería puede que desee incluir fechas importantes como aniversarios o cumpleaños, ya que estas fechas son oportunidades en que las personas pueden comprar más joyas. Igualmente, un minorista de moda puede que desee incluir los intereses y las marcas preferidos del cliente.

El libro de clientes también permite a los socios de ventas filtrar la lista de modo que muestre solo a los clientes que cumplan criterios específicos. Por ejemplo, una nueva colección de zapatos ha llegado al almacén, y un socio desea informar a los clientes a quienes les gusta comprar zapatos. En este caso, el socio puede filtrar el libro de clientes para encontrar los clientes relevantes y después adoptar otras medidas.

Si algunos clientes ya no se consideran principales por algún motivo, y, por consiguiente, no se gestionan estrechamente, los socios de ventas pueden quitarlos del libro de clientes.

Algunos minoristas no desean administrar a los clientes en el nivel de socio de ventas. En su lugar, desean administrar una lista de clientes principales en el nivel de la tienda. Estos minoristas pueden ver los clientes desde libros de clientes de la tienda. Con esta opción, los minoristas pueden ver los clientes de los libros de clientes de todos los socios de ventas cuyas libretas de direcciones coincidan con la libreta de direcciones de la tienda actual. De esta manera, si un socio opera en varias tiendas de la entidad jurídica, el libro de clientes muestran los clientes de todas las tiendas. Esta funcionalidad admite capacidades adicionales. Por ejemplo, los clientes pueden ser reasignados desde un socio a otro socio. Esta capacidad es útil cuando se transfieren socios o salen socios de la empresa.

Cada socio de ventas puede tener un libro de clientes por entidad jurídica, y los socios pueden agregar uno o más clientes a su libro de clientes. En Commerce, cada cliente se puede agregar actualmente solo a un libro de clientes. Sin embargo, los planes de Microsoft son agregar funcionalidad que permita a un único cliente ser agregado a varios libros de clientes.

> [!NOTE]
> A diferencia de la búsqueda de clientes, el libro de clientes no filtra registros de clientes basados en las libretas de direcciones de la tienda.

## <a name="activities-and-notes"></a>Actividades y notas

Los canales conectados proporcionan a los minoristas formas de obtener información sobre las preferencias de los clientes sin requerir que los clientes explícitamente proporcionen esta información. Por el contrario, cuando los clientes interactúan con los socios de ventas en la tienda, comparten información explícitamente sobre sus preferencias. Desafortunadamente, esta información puede perderse después de que la venta haya finalizado. Sin embargo, si se ha registrado esta información, puede ayudar a los minoristas a comprender mejor los a clientes, y por tanto los ayuda a proporcionar mejores recomendaciones y una mejor experiencia total de compras.

Para tomar la información crítica que los clientes comparten, los socios de ventas pueden usar no sólo los atributos del libro de clientes, sino también la funcionalidad de actividades y comentarios. Los minoristas pueden configurar los tipos de actividad, tales como información sobre la visita a la tienda, la dirección de correo electrónico, el número de teléfono, y las citas. Las actividades que los socios crean se pueden ver en un formato de escala de tiempo en el punto de venta (PDV). También pueden verse en la pestaña **Actividades** de la página **Todos los clientes \> General** en la sede central.

Los socios de ventas también pueden usar notas para capturar información de cliente genérica que se consultar antes de cada interacción. Estas notas se guardan en la sede central y se pueden ver en el perfil del cliente o en la página de detalles del cliente del centro de llamadas.

> [!NOTE]
> Actualmente, todas las notas y actividades se pueden ver por cualquier socio de ventas que trabaje para la entidad jurídica y puedan ver las páginas de detalles del cliente. Las notas y actividades no se limitan al socio que agregó a un cliente al libro de clientes.

## <a name="integration-with-dynamics-365-customer-insights"></a>Integración con Dynamics 365 Customer Insights

Mediante la aplicación Dynamics 365 Customer Insights, los minoristas pueden agregar datos de varios sistemas que los clientes usen para interactuar con la marca del minorista. Entonces pueden utilizar estos datos para generar una única vista del cliente y obtener conclusiones. La integración de Customer Insights con Commerce permite a los minoristas seleccionar una o más medidas que se deben mostrar en la tarjeta de cliente en el libro de clientes. Por ejemplo, los minoristas pueden usar los datos de Customer Insights para calcular la “probabilidad de abandono de un cliente y definir la "mejor acción siguiente". Si estos valores se definen como medidas, se pueden mostrar en la tarjeta de cliente y pueden proporcionar información esencial a los socios de ventas. Para obtener más información acerca de Customer Insights, consulte la documentación de [Dynamics 365 Customer Insights](/dynamics365/ai/customer-insights/overview). Para obtener información acerca de las medidas, vea [Medidas](/dynamics365/ai/customer-insights/pm-measures).

## <a name="set-up-clienteling"></a>Configurar el clienteling

Para activar la funcionalidad de clienteling en su entorno, siga estos pasos.

1. En el espacio de trabajo **Administración de características**, filtre las características por el módulo **Retail y Commerce**.

    ![Clienteling en la lista de características del módulo Commerce.](./media/Enable_clienteling.png "Clienteling en la lista de características del módulo Retail y Commerce")

2. Activa la función **Clienteling**; para ello seleccione **Habilitar ahora**.
3. En la página **Parámetros de Commerce**, en la pestaña **Secuencia numérica**, seleccione la fila **Identificador de libro de clientes**. Luego, en el campo **Código de secuencia numérica**, seleccione una secuencia numérica. El sistema utilizará esta secuencia numérica para asignar un Id a los libros de clientes.
4. Seleccione **Guardar**.
5. Cree un nuevo grupo de atributos que contenga los atributos que desea capturar de los clientes que se administran en los libros de clientes. Para consultar instrucciones, vea [Atributos y grupos de atributos](./attribute-attributegroups-lifecycle.md).

    - Defina los atributos requerido como **Se puede refinar**. Los socios de ventas pueden utilizar estos atributos para filtrar sus libros de clientes.
    - Establezca el orden de visualización de estos atributos. Este orden de visualización determina qué atributos se deben mostrar en la tarjeta de cliente del libro de clientes. Un orden de visualización de 1 se considera más alto que un orden de visualización de 2. Por lo tanto, el atributo que tiene un orden de visualización de 1 se mostrará antes que el atributo que tenga una orden de visualización de 2.

    > [!NOTE]
    > Puede hacer que Customer Insights esté disponible desde la misma página. Sin embargo, un identificador y un secreto de la aplicación de Azure se debe crear, por motivos de autenticación. (Para obtener información sobre los requisitos, consulte la sección [Activar la integración de Customer Insights con Commerce](#turn-on-the-integration-of-customer-insights-with-commerce) más adelante en este artículo). Si Customer Insights está activado y selecciona una o más medidas que se deben mostrar en la tarjeta de cliente, estas medidas se mostrarán primero. A continuación, los grupos de atributos del libro de clientes se mostrarán, según el orden de visualización. Por ejemplo, si selecciona dos medidas de Customer Insights, dichas dos medidas y un atributo del libro de clientes se mostrarán en la tarjeta del cliente. (El atributo de libro de clientes que se muestra será el atributo que tenga el orden de visualización más alto.)

6. En la página **Parámetros de Commerce**, en la pestaña **Clienteling**, en el campo **Grupo de atributos del libro de clientes**, seleccione el grupo de atributos que acaba de crear.

    ![Grupo de atributos del libro de clientes seleccionado.](./media/Client%20book%20attributes.png "Grupo de atributos del libro de clientes seleccionado")

7. Para capturar las actividades que se producen en el PDV, defina los tipos de actividad en la página **Tipos de actividad** (**Retail y Commerce \> Clientes \> Tipos de actividad**).

    > [!NOTE]
    > Los tipos de actividad son extraídos por Commerce Scale Unit cuando realiza una llamada en tiempo real por primera vez. Después de que las actividades se extraigan, se almacenan en la memoria caché durante algunas horas. Si cambia los tipos de actividad, espere hasta que la caché ya no sea válida. Como alternativa, para los entornos de no producción, reinicie el servicio Commerce Scale Unit.

8. Agregue dos botones en el diseño de pantalla de PDV adecuado, de modo que los socios de ventas puedan ver su propio libro de clientes y el libro de clientes de la tienda. (Los libros de clientes de la tienda incluyen clientes de todos los libros de clientes de todos los socios que compartan una libreta de direcciones con la tienda.) Las operaciones correspondientes se denominan **Ver clientes de libro de clientes** y **Ver los clientes de los libros de clientes de la tienda**, respectivamente. Tres operaciones adicionales relativas a los libros de clientes están disponibles. Estas operaciones determinan qué socios pueden agregar, quitar, y volver a asignar clientes del libro de clientes. Se denominan **Agregar cliente a libro de clientes**, **Quitar clientes del libro de clientes** y **Volver a asignar clientes a un libro de clientes**, respectivamente.
9. Ejecute los trabajos de programación de distribución siguientes: 1040, 1150, 1110, y 1090.

Cuando haya completado este procedimiento, los socios de ventas podrán abrir la página de detalles del cliente en el PDV y agregar clientes a su libro de clientes, ver y capturar actividades y notas para clientes, y seleccionar clientes como objetivo mediante atributos del libro de clientes y de cliente para filtrar el libro de clientes. En la ilustración siguiente se muestra un ejemplo de un libro de clientes.

![Ejemplo de un libro de clientes.](./media/client_book.png "Ejemplo de un libro de clientes")

## <a name="turn-on-the-integration-of-customer-insights-with-commerce"></a>Activar la integración de Customer Insights con Commerce

Para activar la integración de Customer Insights con Commerce, debe asegurarse de que tenga una instancia activa de Customer Insights en el inquilino donde Commerce está aprovisionado. También debe tener una cuenta de usuario de Azure Active Directory (Azure AD) que tenga una suscripción de Azure.

Siga estos pasos para configurar la integración.

1. En Azure Portal, registre una nueva aplicación y anote el nombre de la aplicación, el id. de la aplicación y el secreto. Esta información se utilizará para la autenticación de servicio a servicio entre Commerce y Customer Insights. Anote el secreto de forma segura, ya que será necesario guardarlo en el almacén de claves. Para el siguiente ejemplo, use CI_Access_name, CI_Access_AppID y CI_Access_Secret para el nombre de la aplicación, el id. de la aplicación y el secreto, respectivamente. Para más información, consulte [Inicio rápido: Registrar una aplicación en la plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app).

    > [!IMPORTANT]
    > Tome medidas de modo que se recuerde de cambiar el secreto antes de que caduque. Si no, la integración se detendrá inesperadamente.

2. Vaya a su instancia de Customer Insights y busque el nombre de la aplicación creada anteriormente (en este ejemplo, "CI_Access_name").
3. Cree un almacén de claves de Azure y anote el nombre y la URL (en este ejemplo, "KeyVaultName", "KeyVaultURL"). Para obtener instrucciones, consulte [Inicio rápido: Establecer y recuperar el Azure Key Vault mediante el portal de Azure](/azure/key-vault/quick-create-portal).
4. Guarde el secreto (en este ejemplo, "CI_Access_Secret") en el almacén. Cuando este secreto se almacena en el almacén, el secreto recibe un nombre. Anote el nombre del secreto (en este ejemplo, "SecretName").
5. Para acceder al secreto desde Azure Key Vault, debe crear otra aplicación con un id. de aplicación y un secreto (en este ejemplo, "KeyVault_Access_AppID" y "KeyVault_Access_Secret"). Anote el secreto de forma segura, ya que no se volverá a mostrar.
6. A continuación, debe otorgar permisos a la aplicación para acceder a Key Vault desde Commerce, usando las API. En Azure Portal, vaya a la página de aplicaciones. En la sección **Administrar**, seleccione **Permisos de API**. Agregue el permiso para acceder al **Almacén de claves de Azure**. Para obtener este permiso, seleccione **Política de acceso**. Seleccione la plantilla como **Administración de secretos** y seleccione las opciones **Obtener**, **Enumerar**, **Descifrar** y **Cifrar**. 
5. En la sede central de Commerce, vaya a **Administración del sistema \> Configuración \> Parámetros de Key Vault** e introduzca la información requerida para el almacén de claves. A continuación, en el campo **Cliente de Key Vault**, especifique el identificador de la aplicación que usó en el paso 4, de modo que Commerce pueda acceder a los secretos del almacén de claves.
6. Para agregar la aplicación que creó en el paso 1 a la lista de aplicaciones seguras (en ocasiones denominada lista segura), vaya a Customer Insights, y seleccione acceso de **Vista** a la aplicación. Para obtener instrucciones, consulte [Permisos](/dynamics365/ai/customer-insights/pm-permissions).
7. En la página **Administración del sistema > Configuración > Parámetros de Key Vault** de la sede central de Commerce, actualice los campos como se describe a continuación: 

- **URL de Key Vault**: "KeyVaultURL" (del paso 3 anterior).
- **Cliente de Key Vault**: "KeyVault_Access_AppID" (del paso 5 anterior).
- **Clave secreta de Key Vault**: "KeyVault_Access_Secret" (del paso 5 anterior).
- En la sección **Secretos**:
    - **Nombre**: cualquier nombre, por ejemplo "CISecret".
    - **Descripción**: cualquier valor.
    - **Secreto**: **bóveda** :`//<Name of key vault>/<name of secret>>` En este ejemplo será `vault://KeyVaultName/SecretName`.

Después de actualizar los campos, seleccione **Validar** para garantizar que la aplicación de Commerce pueda acceder al secreto.

8. En Commerce, en la página **Parámetros de Commerce**, en la pestaña **Clientelar**, en la ficha desplegable **Dynamics 365 Customer Insights** establezca el **Id. de aplicación** en "CI_Access_AppID" (del paso 1 anterior). Para **Nombre de secreto**, seleccione el nombre del secreto introducido en el paso 7 anterior ("CISecret"). Establezca la opción **Habilitar Customer Insights** en **Sí**. Si la configuración fracasa por algún motivo, aparecerá un mensaje de error, y esta opción se establecerá en **No**. 

Puede tener varios entornos en Customer Insights, como entornos de prueba y producción. En el campo **Id. de instancia del entorno**, especifique el entorno adecuado. En el campo **Id. de cliente alternativo**, especifique la propiedad de Customer Insights que esté asignada al número de cuenta del cliente. (En Commerce, el número de cuenta del cliente es el id. del cliente). Las tres propiedades restantes son las medidas que se mostrarán en la tarjeta del cliente en el libro del cliente. Puede seleccionar hasta tres medidas para mostrar en la tarjeta de cliente. Sin embargo, no es necesario que seleccione ninguna medida. Como se mencionó anteriormente, el sistema muestra estos valores primero y luego muestra los valores para el grupo de atributos del libro de clientes.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
