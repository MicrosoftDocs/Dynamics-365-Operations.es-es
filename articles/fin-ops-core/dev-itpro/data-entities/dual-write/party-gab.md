---
title: Libreta de direcciones de partes y global
description: Este tema describe la funcionalidad de libreta de direcciones de partes y global de escritura dual.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: e7bec58f8094a1448017822e7d8840368cc482b8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750797"
---
# <a name="party-and-global-address-book"></a>Libreta de direcciones de partes y global

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

La libreta de direcciones de partes y global es un concepto de als aplicaciones de Finance and Operations. Una parteo puede ser una persona u organización. Es conveniente almacenar y administrar globalmente las propiedades de una **Parte**, como el nombre, el idioma, los contactos y las direcciones. Cuando el valor de una propiedad cambia en un lugar, se refleja en todos los lugares donde está involucrada la **Parte**.

## <a name="party"></a>Parte

Una *Parte* es una persona u organización involucrada en el negocio. Al utilizar el concepto de parte, una persona u organización puede desempeñar más de un rol (trabajador, cliente, proveedor o contacto) en una empresa. El rol se basa en el contexto y el propósito. A continuación, se muestran algunos ejemplos de dos empresas ficticias, Contoso y Fabrikam.

+ **Trabajador**: un empleado. Por ejemplo, un empleado de Contoso.
+ **Proveedor**: una organización proveedora o un propietario único que suministra bienes o servicios a una empresa. Por ejemplo, si Fabrikam vende suministros a Contoso, entonces Fabrikam tiene el rol de proveedor.
+ **Contacto**: una persona para contactar. Por ejemplo, si Contoso compra suministros de Fabrikam, un empleado de Contoso se pondría en contacto con el contacto de Fabrikam.
+ **Cliente**: un cliente es una persona o empresa que compra cosas a una empresa. Por ejemplo, si Contoso compra suministros de Fabrikam, entonces Contoso es un cliente de Fabrikam.

El modelo de parte se utiliza a menudo para representar relaciones de medianas a complejas entre organizaciones y personas, especialmente cuando una parte desempeña más de un rol. A continuación aparecen ejemplos habituales:

+ Una parte puede ser tanto un cliente como un proveedor. Por ejemplo, en Norteamérica, Fabrikam vende cables eléctricos a Contoso y compra altavoces ensamblados a Contoso. En Europa, Fabrikam vende piezas a Contoso, pero no compra nada a Contoso.
+ Una parte puede ser tanto un empleado como un cliente. Por ejemplo, un empleado de Contoso compra productos electrónicos de Contoso para uso personal.
+ Puede haber una relación de varios a varios entre una persona y una organización. Por ejemplo, Fabrikam proporciona especialistas de servicio y emplea a un coordinador de colocación. El coordinador pone en contacto a los especialistas de servicio para las solicitudes de trabajo de varios de los clientes de Fabrikam. Contoso es una de las cuentas de cliente. Cuando Contoso necesita un especialista, Contoso se pone en contacto con el coordinador, quien luego facilita la solicitud. El coordinador maneja las solicitudes de todos los clientes, creando una relación de varios a varios.

La siguiente imagen muestra el modelo de datos de parte:

![Modelo de datos de parte](media/party-gab-image1.png)

> [!Tip]
> Cuando intente crear un nuevo registro de cuenta, utilice el campo “Parte” para buscar el registro por nombre. En caso de que encuentre el registro, solo necesita seleccionarlo. El sistema rellena automáticamente todos los datos de la parte. No es necesario que introduzca manualmente todos los campos obligatorios. Este comportamiento se puede encontrar en los formularios de Cuenta, Contacto y Proveedor que se envían para uso inmediato.

No todos los roles de partido de las aplicaciones de Finance and Operations son compatibles con escritura dual. Para obtener una lista completa de los roles de parte, consulte [Descripción general de la libreta de direcciones global](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Libreta de direcciones global

La libreta de direcciones global es un directorio de direcciones postales y electrónicas de las organizaciones y personas que participan en una empresa.

La libreta de direcciones global almacena y maneja tantas direcciones postales y direcciones electrónicas como sea necesario. Por ejemplo, suponga que Fabrikam tiene gasolineras en 50 ubicaciones. Cada ubicación tiene una dirección postal, un correo electrónico y un número de teléfono diferentes. Todas las compras comerciales se facturan a la gasolinera principal, pero las compras se envían directamente a la gasolinera específica que solicitó la compra. La libreta de direcciones global almacena la gasolinera principal como dirección de facturación y cada estación de servicio como una dirección de envío para Fabrikam. Las direcciones se pueden almacenar una vez y recuperarse según sea necesario para presupuestos y pedidos.

Una persona u organización puede desempeñar más de un rol según el contexto empresarial. Cuando lo hagan, sus direcciones postales y direcciones electrónicas podrían ser las mismas. En este caso, un cambio de dirección en un rol debería aparecer en el otro rol y viceversa. La libreta de direcciones global almacena y gestiona las direcciones de forma global.

![Modelo de datos para la libreta de direcciones global](media/party-gab-image2.png)

## <a name="contacts"></a>Contactos

En las aplicaciones de interacción con el cliente, un *Contacto* es una persona. Sin embargo, la tabla **Contacto** se ha sobrecargado para representar a una persona, un usuario del portal, un cliente B2C o un proveedor. La representación es implícita y no se puede notar la diferencia sin investigar las transacciones relacionadas. La tabla **Contacto** se ha limitado a tener una relación 1:1 con la tabla **Cuenta**. Como parte del modelo de libreta de direcciones global y de partes, la escritura dual introduce propiedades explícitas para la clasificación y permite relaciones N:N entre una persona de **Contacto** y una organización (entidad de cuenta o entidad de proveedor).

Existen dos tipos de filas de **Contacto**:

+ Contacto rayado: fila de contacto con un valor obligatorio en el campo **Empresa**.
+ Contacto sin rayas: fila de contacto con campo **Empresa** en blanco.

La tabla **Contacto** puede almacenar estos tipos de filas:

Tipo de fila | Descripción
---|---
Una persona que es un cliente, por ejemplo, un contacto al que se puede vender o un cliente B2C. | Un registro de contacto rayado donde el campo **Empresa** no está en blanco y el campo **Es cliente** está configurado en **Sí**.
Una persona que es un proveedor, por ejemplo, un propietario único como proveedor. | Un registro de contacto rayado donde el campo **Empresa** no está en blanco y el campo **Es proveedor** está configurado en **Sí**.
Una persona que es tanto un cliente como un proveedor. | Un registro de contacto rayado donde el campo **Empresa** no está en blanco, el campo **Es cliente** está configurado en **Sí** y el campo **Es proveedor** está configurado en **Sí**. Una persona puede ser tanto productor de un producto como consumidor de otro. Ambas aplicaciones de Finance and Operations y la escritura dual admiten esta relación.
Una persona que es la persona de contacto de una organización, pero que no es ni cliente ni proveedor. | Un registro de contacto no rayado donde el campo **Empresa** no está en blanco, el campo **Es cliente** está configurado en **No** y el campo **Es proveedor** está configurado en **No**.

## <a name="contact-for-party"></a>Contacto de parte

**Contacto de parte** almacena y maneja relaciones N:N entre filas de **Cuenta** y filas de **Contacto**. Puede filtrar las filas rayadas **Contacto** para separarlas de las filas sin rayas y asociar solo las filas sin rayas de **Contacto** a filas de **Cuenta** o **Proveedor**.

Por ejemplo, Natasha Jones y Miguel Reyes son veterinarios que brindan atención a las granjas de sus zonas. Natasha atiende el área de Seattle y Miguel atiende el área de Kent. En la aplicación de participación del cliente, las granjas se representan como clientes y los veterinarios son personas de contacto. Un solo registro de **Contacto** de Natasha está asociado con todas las granjas con las que trabaja Natasha. De forma similar, un solo registro de **Contacto** de Miguel está asociado con todas las granjas con las que trabaja Miguel.

Estas relaciones se almacenan en la tabla **Contacto de parte**. Puede encontrar la información en los formularios listos para usar:

+ Cuando está en el formulario **Cuenta**, hay una pestaña llamada **Contactos asociados**. Utilice esta pestaña para asociar uno o más contactos a la fila **Cuenta**. En este formulario, está asignando una persona de contacto para una organización. Después de asignar contactos, puede elegir uno como contacto principal para esa cuenta. Utilizando el formulario **Creación rápida**, solo puede elegir una persona de contacto. El comportamiento es el mismo cuando usa el formulario **Proveedor** y el tipo de registro es **Organización**.
+ Cuando está en el formulario **Contacto** y la fila es un cliente o proveedor, o ambos (un contacto rayado), hay una pestaña llamada **Contactos asociados**. Utilice esta pestaña para asociar uno o más contactos. En este formulario, está asignando una persona de contacto al cliente o proveedor B2C. Después de asignar contactos, puede elegir uno como contacto principal. Utilizando el formulario **Creación rápida**, solo puede elegir una persona de contacto.
+ Cuando está en el formulario **Contacto** y la fila es una persona de contacto (un contacto no rayado), hay una pestaña llamada **Organizaciones asociadas**. Utilice esta pestaña para asociar uno o más clientes o proveedores. En este formulario, está asignando una persona de contacto o proveedor a la persona de contacto subyacente. El cliente o proveedor puede ser una organización, una persona o ambas. Puede elegir solo un valor de los cuatro campos en un momento determinado.

    ![Pestaña Organizaciones asociadas](media/party-gab-image3.png)

    + Si elige **Id. de parte**, el contacto subyacente se asigna a todos los roles de la parte elegida.
    + Si elige **Contacto asociado**, entonces está seleccionando el contacto rayado que es de tipo persona.
    + Si elige **Cuenta asociada** o **Proveedor**, entonces está seleccionando una organización.

    Independientemente de su elección, la asociación se crea a nivel de partido y se aplica a todos los roles del partido y se almacena en la entidad “Contacto de parte”.

> [!Note]
> El nombre para mostrar de la tabla **Contacto de parte** en la aplicación de interacción con el cliente es **Contacto de cliente/proveedor**.

Cuando abre una fila de **Contacto** donde **Es cliente** es **No** y **Es proveedor** es **No**, verá la pestaña **Organizaciones asociadas**. Utilice esta pestaña para asociar una o más organizaciones de clientes o proveedores al contacto.

Cuando abre una fila de **Contacto** donde **Es cliente** es **Sí** o **Es proveedor** es **Sí**, verá la pestaña **Contactos asociados**. Utilice esta pestaña para asociar uno o más contactos.

## <a name="postal-address"></a>Dirección postal

Una nueva pestaña llamada **Direcciones** se ha introducido en los formularios **Cuenta**, **Contacto** y **Proveedor**. Las **Direcciones** admiten N direcciones mediante el uso de una cuadrícula, como se muestra en esta imagen:

![Cuadrícula para dirección postal](media/party-gab-image4.png)

+ La columna **Roles de dirección postal** enumera el propósito de la dirección.
+ La columna **Es principal** enumera la dirección principal.
+ La columna **Número de dirección** enumera el orden de las direcciones.
+ El botón **+ Nueva dirección** le permite crear una nueva dirección. Puede crear tantas direcciones como quiera.

Los campos **Dirección 1** y **Dirección 2** de la pestaña **Resumen** del formulario **Cuenta** corresponden a las direcciones **Entrega** y **Factura**, respectivamente.

![Pestaña Resumen para dirección postal](media/party-gab-image5.png)

Los campos **Dirección 1**, **Dirección 2** y **Dirección 3** de la pestaña **Resumen** del formulario **Contacto** corresponden a las direcciones **Empresa**, **Entrega** y **Factura**, respectivamente.

## <a name="electronic-address"></a>Dirección electrónica

Una nueva pestaña llamada **Direcciones eléctronicas** se ha introducido en los formularios **Cuenta**, **Contacto** y **Proveedor**. Las **Direcciones** admiten N direcciones mediante el uso de una cuadrícula, como se muestra en esta imagen:

![Cuadrícula para direcciones electrónicas](media/party-gab-image6.png)

+ La columna **Tipo** enumera el tipo de dirección.
+ La columna **Es principal** enumera la dirección principal.
+ La columna **Finalidad** enumera el propósito de la dirección electrónica.
+ El botón **+ Nueva dirección electrónica** le permite crear una nueva dirección. Puede crear tantas direcciones como quiera.

Las direcciones electrónicas están disponibles solo en esta cuadrícula. En versiones futuras, todos los campos de direcciones electrónicas y postales se eliminarán de otras pestañas, por ejemplo, las pestañas **Resumen** y **Detalles**.

## <a name="setup-instructions"></a>Instrucciones de instalación

Si ya es un cliente de escritura dual, son necesarias las siguientes instrucciones de configuración. De lo contrario, puede omitir esta sección.

1. Detenga los siguientes mapas, porque ya no son necesarios. En su lugar, ejecute el mapa Contactos V2 (msdyn_contactforparties).

    + Contactos CDS V2 y Contactos (se refiere a los contactos del cliente)
    + Contactos CDS V2 y Contactos (se refiere a los contactos del proveedor)

2. Las siguientes asignaciones de entidades se actualizan para la funcionalidad de las partes, por lo que se debe aplicar la última versión a estas asignaciones.

Mapa | Actualizar a esta versión | Cambios
---|---|---
Clientes V3 (cuentas) | 1.0.0.5 |Se eliminó PartyNumber y otros campos relacionados con la parte como el nombre, los datos personales, los campos de dirección postal, los campos de dirección de contacto electrónica, etc.
Cliente V3 (contactos) | 1.0.0.5 | Se eliminó PartyNumber y otros campos relacionados con la parte como el nombre, los datos personales, los campos de dirección postal, los campos de dirección de contacto electrónica, etc.
Proveedores V2 (msdyn_vendors) | 1.0.0.6 | Se eliminó PartyNumber y otros campos relacionados con la parte como el nombre, los datos personales, los campos de dirección postal, los campos de dirección de contacto electrónica, etc.
Encabezados de presupuestos de ventas de CDS (ofertas) | 1.0.0.6 | Se reemplazó a la persona de contacto con la referencia ContactforParty.
Encabezados de factura de ventas V2 (facturas) | 1.0.0.4 | Se reemplazó a la persona de contacto con la referencia ContactforParty.
Encabezados de pedidos de ventas de CDS (pedidos de ventas) | 1.0.0.5 | Se reemplazó a la persona de contacto con la referencia ContactforParty.
Contactos V2 (msdyn_contactforparties) | 1.0.0.2 | Este es un mapa nuevo. Si tiene una versión anterior de la solución para partes, asegúrese de actualizar este mapa a la última versión como se mencionó.
Ubicaciones de direcciones postales de parte de CDS (msdyn_partypostaladdresses) | 1.0.0.1  | Este es un nuevo mapa agregado como parte de la versión preliminar de la parte anterior.
Historial de direcciones postales de CDS V2 (msdyn_postaladdresses) | | Este es un nuevo mapa agregado como parte de la versión preliminar de la parte anterior.
Ubicaciones de direcciones postales de CDS (msdyn_postaladdresscollections) | | Este es un nuevo mapa agregado como parte de la versión preliminar de la parte anterior.
Contactos de parte V3 (msdyn_partyelectronicaddresses) | | Este es un nuevo mapa agregado como parte de esta versión.

## <a name="templates"></a>Plantillas

Una colección de mapas de tabla funciona conjuntamente para la interacción de partes y la libreta de direcciones global, como se muestra en la tabla siguiente.

Aplicación de Finance and Operations | Aplicación Customer Engagement     | Descripción
----------------------------|-----------------------------|------------
[Cargos de persona de contacto](mapping-reference.md#223) | msdyn_salescontactpersontitles |
[Clientes V3](mapping-reference.md#101) | cuentas |
[Clientes V3](mapping-reference.md#116) | contactos |
[Partes de CDS](mapping-reference.md#220) | msdyn_parties |
[Ubicaciones de dirección postal de entidad CDS](mapping-reference.md#233) | msdyn_partypostaladdresses |
[Historial de dirección postal de CDS V2](mapping-reference.md#235) | msdyn_postaladdresses |
[Ubicaciones de dirección postal de CDS](mapping-reference.md#234) | msdyn_postaladdresscollections |
[Encabezado de presupuesto de ventas de CDS](mapping-reference.md#215) | presupuestos |
[Encabezado de pedidos de ventas de CDS](mapping-reference.md#217) | salesorders |
[Despedidas de agradecimiento](mapping-reference.md#222) | msdyn_complimentaryclosings |
[Contactos V2](mapping-reference.md#221) | msdyn_contactforparties |
[Roles de toma de decisiones](mapping-reference.md#224) | msdyn_decisionmakingroles |
[Funciones de trabajo de empleo](mapping-reference.md#225) | msdyn_employmentjobfunctions |
[Niveles de fidelización](mapping-reference.md#226) | msdyn_loyaltylevels |
[Contactos de parte V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses |
[Tipos de carácter personal](mapping-reference.md#227) | msdyn_personalcharactertypes |
[Encabezados de factura de ventas V2](mapping-reference.md#118) | facturas |
[Formas de saludo](mapping-reference.md#228) | msdyn_salutations |
[Proveedores V2](mapping-reference.md#202) | msdyn_vendors |

Para más información, consulte [Referencia de asignación de escritura doble](mapping-reference.md).
