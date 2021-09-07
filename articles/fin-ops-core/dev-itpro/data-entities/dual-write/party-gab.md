---
title: Libreta de direcciones de partes y global
description: Este tema describe la funcionalidad de libreta de direcciones de partes y global de escritura dual.
author: RamaKrishnamoorthy
ms.date: 08/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: da5ca16ed87108f8046348c831d37085f6f780d7
ms.sourcegitcommit: 822aea26c5da259efe11ff3b3dc4cf1598425689
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2021
ms.locfileid: "7386694"
---
# <a name="party-and-global-address-book"></a>Libreta de direcciones de partes y global

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

*Libreta de direcciones de partes* y *libreta de direcciones global* son conceptos de aplicaciones de Finance and Operations. Una parte puede ser una persona u organización. Es conveniente almacenar y administrar globalmente las propiedades de una parte, como el nombre, el idioma, los contactos y las direcciones. Luego, cuando el valor de una propiedad se cambie en un lugar, el cambio se refleja en todos los lugares donde está involucrada la parte.

## <a name="party"></a>Parte

Una parte es una persona u organización involucrada en un negocio. Al utilizar el concepto de parte, una persona u organización puede desempeñar más de un rol en un negocio (trabajador, cliente, proveedor o contacto). El rol se basa en el contexto y el propósito. A continuación, se muestran algunos ejemplos de roles de dos empresas ficticias, Contoso y Fabrikam:

+ **Trabajador**: un empleado. Un ejemplo es un empleado de Contoso.
+ **Proveedor**: una organización proveedora o un propietario único que suministra bienes o servicios a una empresa. Por ejemplo, si Fabrikam vende suministros a Contoso, Fabrikam es un proveedor de Contoso.
+ **Contacto**: una persona para contactar. Por ejemplo, si Contoso compra suministros de Fabrikam, los empleados de Contoso se pondán en contacto con el contacto de Fabrikam.
+ **Cliente**: una persona o empresa que compra cosas a una empresa. Por ejemplo, si Contoso compra suministros de Fabrikam, Contoso es un cliente de Fabrikam.

El modelo de parte se utiliza a menudo para representar relaciones de medianas a complejas entre organizaciones y personas, especialmente cuando una parte desempeña más de un rol. A continuación aparecen ejemplos habituales:

+ Una parte puede ser tanto un cliente como un proveedor. Por ejemplo, en Norteamérica, Fabrikam vende cables eléctricos a Contoso y compra altavoces ensamblados a Contoso. En Europa, Fabrikam vende piezas a Contoso, pero no compra nada a Contoso.
+ Una parte puede ser tanto un empleado como un cliente. Por ejemplo, un empleado de Contoso compra productos electrónicos de Contoso para uso personal.
+ Puede haber una relación de varios a varios (N:N) entre una persona y una organización. Por ejemplo, Fabrikam ofrece especialistas de servicio y emplea a un coordinador de colocación. El coordinador de colocación pone en contacto a los especialistas de servicio para las solicitudes de trabajo de varios de los clientes de Fabrikam. Contoso es uno de los clientes de Fabrikam. Cuando Contoso necesita un especialista de servivio, se pone en contacto con el coordinador de colocación, quien luego facilita la solicitud. Debido a que el coordinador de colocación maneja las solicitudes de todos los clientes, se involucra una relación de N:N.

La siguiente ilustración muestra el modelo de datos de parte:

![Modelo de datos de parte.](media/party-gab-image1.png)

> [!TIP]
> Cuando intente crear un nuevo registro de cuenta, utilice el campo **Parte** para buscar el registro por nombre. Así, en caso de que encuentre el registro, solo necesita seleccionarlo. El sistema rellena luego automáticamente todos los datos de la parte. No es necesario introducir manualmente todos los campos obligatorios. Este comportamiento se puede encontrar en las páginas listas para usar de **Cuenta**, **Contacto** y **Proveedor**.

La escritura doble no admite todos los roles de parte de las aplicaciones de Finance and Operations. Para obtener una lista completa de los roles de parte, consulte [Descripción general de la libreta de direcciones global](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Libreta de direcciones global

La libreta de direcciones global es un directorio de direcciones postales y electrónicas de las organizaciones y personas que participan en un negocio.

La libreta de direcciones global almacena y maneja tantas direcciones postales y direcciones electrónicas como se requiera. Por ejemplo, Fabrikam tiene gasolineras en 50 ubicaciones. Cada ubicación tiene una dirección postal, una dirección de correo electrónico y un número de teléfono diferentes. Todas las compras comerciales se facturan a la gasolinera principal, pero se envían directamente a la gasolinera específica que solicitó la compra. La libreta de direcciones global almacena la gasolinera principal como dirección de Fabrikam y almacena cada estación de servicio como una dirección de envío. Las direcciones se pueden almacenar una vez y luego recuperarse según sea necesario para presupuestos y pedidos.

Dependiendo del contexto empresarial, una persona u organización puede desempeñar más de un rol, y la misma dirección postal y dirección electrónica puede usarse para todos los roles. En este caso, un cambio de dirección en un rol debería aparecer en todos los demás roles. La libreta de direcciones global almacena y gestiona las direcciones de forma global.

La ilustración siguiente muestra el modelo de datos para la libreta de direcciones global.

![Modelo de datos para la libreta de direcciones global.](media/party-gab-image2.png)

## <a name="contact"></a>Contacto

En las aplicaciones de interacción con el cliente, un contacto es una persona. Sin embargo, la tabla **Contacto** se ha sobrecargado para representar a una persona, un usuario del portal, un cliente de empresa a particular (B2C) o un proveedor. La representación es implícita y no se puede notar la diferencia sin examinar las transacciones relacionadas. La tabla **Contacto** se ha limitado a una relación 1:1 con la tabla **Cuenta**. Como parte del modelo de libreta de direcciones global y de partes, la escritura dual introduce propiedades explícitas para la clasificación y permite relaciones N:N entre un contacto que es una persona y una organización (entidad de **Cuenta** o **Proveedor**).

Existen dos tipos de filas de **Contacto**:

+ **Contacto marcado**: una fila de **Contacto** en la que el campo **Empresa** tiene un valor obligatorio.
+ **Contacto sin marcar**: una fila de **Contacto** con el campo **Empresa** en blanco.

La tabla **Contacto** puede almacenar los siguientes tipos de filas.

| Tipo de fila | Descripción |
|----------|-------------|
| Una persona que es un cliente (por ejemplo, un contacto al que se puede vender o un cliente B2C) | Un registro de contacto marcado donde el campo **Empresa** no está en blanco y el campo **Es cliente** está configurado en **Sí**. |
| Una persona que es un proveedor (por ejemplo, un propietario único, como un proveedor) | Un registro de contacto marcado donde el campo **Empresa** no está en blanco y el campo **Es proveedor** está configurado en **Sí**. |
| Una persona que es tanto un cliente como un proveedor | Un registro de contacto marcado donde el campo **Empresa** no está en blanco, el campo **Es cliente** está configurado en **Sí** y el campo **Es proveedor** está configurado en **Sí**. Una persona puede ser tanto productor de un producto como consumidor de otro. Ambas aplicaciones de Finance and Operations y la escritura dual admiten esta relación. |
| Una persona que es la persona de contacto de una organización, pero que no es ni cliente ni proveedor | Un registro de contacto no marcado donde el campo **Empresa** está en blanco, el campo **Es cliente** está configurado en **No** y el campo **Es proveedor** está configurado en **No**. |

## <a name="contact-for-party-table"></a>Contacto de tabla de partes

La tabla **Contacto de parte** almacena y maneja relaciones N:N entre filas de **Cuenta** y filas de **Contacto**. Puede filtrar las filas marcadas **Contacto** para separarlas de las filas sin marcar y asociar solo las filas sin marcas de **Contacto** a filas de **Cuenta** o **Proveedor**.

Por ejemplo, Natasha Jones y Miguel Reyes son veterinarios que brindan atención a las granjas de sus zonas. Natasha atiende el área de Seattle y Miguel atiende el área de Kent. En la aplicación de participación del cliente, las granjas se representan como clientes y los veterinarios se representan como personas de contacto. Un solo registro de **Contacto** de Natasha está asociado con todas las granjas con las que trabaja Natasha. Igualmente, un solo registro de **Contacto** de Miguel está asociado con todas las granjas con las que trabaja Miguel.

Estas relaciones se almacenan en la tabla **Contacto de parte**. Puede encontrar la información en las páginas listas para usar de **Cuenta**, **Contacto** y **Proveedor**:

+ En la página **Cuenta**, puede utilizar la ficha **Contactos asociados** para asociar uno o más contactos con la fila **Cuenta**. De esta manera, está asignando personas de contacto para una organización. A continuación, puede seleccionar un contacto como contacto principal de la cuenta. Si usa la página **Creación rápida**, solo puede seleccionar una persona de contacto. El comportamiento es el mismo cuando usa la página **Proveedor** y el tipo de registro es **Organización**.
+ En la página **Contacto**, cuando la fila es un cliente, un proveedor o ambos (un contacto marcado), puede utilizar la ficha **Contactos asociados** para asociar uno o más contactos. De esta forma, está asignando personas de contacto al cliente o proveedor B2C. A continuación, puede seleccionar un contacto como contacto principal. Si usa la página **Creación rápida**, solo puede seleccionar una persona de contacto.
+ En la página **Contacto**, cuando la fila es una persona de contacto (un contacto no marcado), puede utilizar la ficha **Organizaciones asociadas** para asociar uno o más clientes o proveedores. De esta manera, puede asignar clientes o proveedores a la persona de contacto subyacente. El cliente o proveedor puede ser una organización, una persona o ambas. Puede seleccionar un valor cada vez en solo uno de los cuatro campos:

    + Si selecciona un valor en e campo **Id. de parte**, el contacto subyacente se asigna a todos los roles de la parte seleccionada.
    + Si selecciona un valor en el campo **Contacto asociado**, entonces está seleccionando el contacto macado del tipo **Persona**.
    + Si selecciona un valor en el campo **Cuenta asociada** o **Proveedor asociado**, está seleccionando una organización.

    ![Ficha Organizaciones asociadas en la página Contacto.](media/party-gab-image3.png)

    Independientemente de su selección, la asociación se crea a nivel de parte, se aplica a todos los roles de parte y se almacena en la entidad **Contacto de parte**.

> [!NOTE]
> El nombre para mostrar de la tabla **Contacto de parte** en las aplicaciones de interacción con el cliente es **Contacto de cliente/proveedor**.

Cuando abre una fila de **Contacto** donde el campo **Es cliente** y **Es proveedor** están configurados en **No**, se muestra la ficha **Organizaciones asociadas**. Utilice esta ficha para asociar una o más organizaciones de clientes o proveedores con el contacto.

Cuando abre una fila de **Contacto** donde el campo **Es cliente** o el campo **Es proveedor** está configurados en **Sí**, se muestra la ficha **Contactos asociados**. Utilice esta pestaña para asociar uno o más contactos.

## <a name="postal-addresses"></a>Direcciones postales

Una nueva pestaña **Direcciones** se ha introducido en las páginas **Cuenta**, **Contacto** y **Proveedor**. Esta pestaña admite varias direcciones postales mediante el uso de una cuadrícula, como se muestra en la siguiente ilustración.

![Cuadrícula para direcciones postales.](media/party-gab-image4.png)

La cuadrícula incluye las siguientes columnas:

+ **Roles de dirección postal**: la finalidad de la dirección postal.
+ **Es primaria**: un valor que indica si la dirección es la dirección principal.
+ **Número de dirección**: el orden de la dirección.

Puede usar el botón **Nueva direccion** de encima de la cuadrícula para crear tantas direcciones postales como desee.

Los campos **Dirección 1** y **Dirección 2** de la pestaña **Resumen** de la página **Cuenta** corresponden a las direcciones **Entrega** y **Factura**, respectivamente.

![Pestaña Resumen para direcciones postales.](media/party-gab-image5.png)

Los campos **Dirección 1**, **Dirección 2** y **Dirección 3** de la página **Resumen** del formulario **Contacto** corresponden a las direcciones **Empresa**, **Entrega** y **Factura**, respectivamente.

## <a name="electronic-addresses"></a>Direcciones electrónicas

Una nueva pestaña **Direcciones electrónicas** se ha introducido en las páginas **Cuenta**, **Contacto** y **Proveedor**. Esta pestaña admite varias direcciones electrónicas mediante el uso de una cuadrícula, como se muestra en la siguiente ilustración.

![Cuadrícula para direcciones electrónicas.](media/party-gab-image6.png)

La cuadrícula incluye las siguientes columnas:

+ **Tipo**: el tipo de dirección electrónica.
+ **Es principal**: un valor que indica si la dirección es la dirección principal.
+ **Propósito**: la finalidad de la dirección electrónica.

Puede usar el botón **Nueva direccion electrónica** de encima de la cuadrícula para crear tantas direcciones como desee.

Las direcciones electrónicas están disponibles solo en esta cuadrícula. En versiones futuras, todos los campos de direcciones electrónicas y postales se eliminarán de otras fichas (por ejemplo, las fichas **Resumen** y **Detalles**). Los datos de contacto que se muestran en la ficha **Detalles** son copias de solo lectura de la dirección electrónica principal, como el teléfono principal, el correo electrónico principal, el teléfono principal, el fax principal y el Id. de Twitter principal. Durante el proceso de calificación de clientes potenciales, puede proporcionar tanto un número de teléfono comercial como un número de teléfono móvil. El número de teléfono comercial se considera el teléfono principal si **IsMobile=No** y el número de teléfono móvil se considera el teléfono secundario si **IsMobile=Yes**.

> [!TIP]
> Use las fichas **Direcciones** y **Direcciones electrónicas** de los formularios **Cuenta** y **Contacto** para gestionar direcciones postales y electrónicas. Esto asegura que los datos de la dirección se sincronicen con las aplicaciones de Finance and Operations.

## <a name="setup"></a>Configurar

1. Abra el entorno de su aplicación de interacción con el cliente.

2. Instale la última versión (2.2.2.60 o posterior) de [Solución de orquestación de aplicaciones de doble escritura](https://aka.ms/dual-write-app).

3. Instale [Soluciones de libreta de direcciones global y de parte de escritura dual](https://aka.ms/dual-write-gab).

4. Abra la aplicación Finance and Operations. Navegue hasta el módulo Gestión de datos y seleccione la ficha Escritura dual. Se abre la página de administración de escritura dual.

5. Aplique las dos soluciones instaladas en los pasos 2 y 3 utilizando la función [Aplicar solución](link-your-environment.md).

6. Detenga los siguientes mapas, porque ya no son necesarios. En su lugar, ejecute la asignación `Contacts V2 (msdyn_contactforparties)`.

    + Contactos CDS V2 y Contactos (se refiere a los contactos del cliente)
    + Contactos CDS V2 y Contactos (se refiere a los contactos del proveedor)

7. Las siguientes asignaciones de entidades se actualizan para la funcionalidad de las partes, por lo que se debe aplicar la última versión a estas asignaciones.

    Mapa | Actualizar a esta versión | Cambios
    ---|---|---
    `CDS Parties (msdyn_parties)`| 1.0.0.0 | Este es un nuevo mapa agregado como parte de esta versión.
    `Contacts V2 (msdyn_contactforparties)`| 1.0.0.5 | Este es un nuevo mapa agregado como parte de esta versión.
    `Customers V3 (accounts)` | 1.0.0.5 |Se eliminó `PartyNumber` y otros campos relacionados con la parte como el nombre, los datos personales, los campos de dirección postal y, los campos de dirección de contacto electrónica.
    `Customer V3 (contacts)` | 1.0.0.5 | Se eliminó `PartyNumber` y otros campos relacionados con la parte como el nombre, los datos personales, los campos de dirección postal y, los campos de dirección de contacto electrónica.
    `Vendors V2 (msdyn_vendors)` | 1.0.0.6 | Se eliminó `PartyNumber` y otros campos relacionados con la parte como el nombre, los datos personales, los campos de dirección postal y, los campos de dirección de contacto electrónica.
    `CDS Sales quotation headers (quotes)` | 1.0.0.7 | Se reemplazó a la persona de contacto con la referencia `ContactforParty`.
    `Sales invoice headers V2 (invoices)` | 1.0.0.4 | Se reemplazó a la persona de contacto con la referencia `ContactforParty`.
    `CDS Sales order headers (salesorders)` | 1.0.0.5 | Se reemplazó a la persona de contacto con la referencia `ContactforParty`.
    `CDS Party postal address locations (msdyn_partypostaladdresses)` | 1.0.0.1  | Este es un nuevo mapa agregado como parte de esta versión.
    `CDS postal address history V2 (msdyn_postaladdresses)` | 1.0.0.1 | Este es un nuevo mapa agregado como parte de esta versión.
    `CDS postal address locations (msdyn_postaladdresscollections)` | 1.0.0.0 | Este es un nuevo mapa agregado como parte de esta versión.
    `Party Contacts V3 (msdyn_partyelectronicaddresses)` | 1.0.0.0 | Este es un nuevo mapa agregado como parte de esta versión.
    `Complimentary Closings ( msdyn_compliemntaryclosings)` | 1.0.0.0 | Este es un nuevo mapa agregado como parte de esta versión.
    `Decision making roles (msdyn_decisionmakingroles)` | 1.0.0.0 | Este es un nuevo mapa agregado como parte de esta versión.
    `Loyalty levels (msdyn_loyaltylevels)` | 1.0.0.0 | Este es un nuevo mapa agregado como parte de esta versión.
    `Contact person titles (msdyn_salescontactpersontitles)` | 1.0.0.0 | Este es un nuevo mapa agregado como parte de esta versión.
    `Personal character types (msdyn_personalcharactertypes)` | 1.0.0.0 | Este es un nuevo mapa agregado como parte de esta versión.
    `Salutations (msdyn_salutations)` | 1.0.0.0 | Este es un nuevo mapa agregado como parte de esta versión.
    `Employment job functions (msdyn_employmentjobfunctions)` | 1.0.0.0 | Este es un nuevo mapa agregado como parte de esta versión.

8. Antes de ejecutar los mapas anteriores, debe actualizar las claves de integración manualmente como se describe en los siguientes pasos. A continuación, seleccione **Guardar**.

    | Mapa | Claves |
    |-----|------|
    | Cuenta |  accountnumber [Número de cuenta]<br>msdyn_company.cdm_companycode [Empresa (código de empresa)] |
    | Contacto | msdyn_contactpersonid [Número de cuenta/Id. de persona de contacto]<br>msdyn_company.cdm_companycode [Empresa (código de empresa)] |
    | Contacto para cliente/proveedor | msdyn_contactforpartynumber [Contacto de número de parte]<br>msdyn_associatedcompanyid.cdm_companycode [Empresa asociada (código de empresa)] |
    | Proveedor | msdyn_vendoraccountnumber [Número de cuenta de proveedor]<br>msdyn_company.cdm_companycode [Empresa (código de empresa)]|

9. En Dataverse, los límites de caracteres de las reglas de detección de duplicados han aumentado de 450 a 700 caracteres. Este límite le permite agregar una o más claves a las reglas de detección de duplicados. Expanda la regla de detección de duplicados para la tabla **Cuentas** configurando los siguientes campos.

    | Campo | Valor |
    |-------|-------|
    | Nombre | Cuentas con el mismo nombre de cuenta. |
    | Descripción | Detecta registros de cuenta que tienen el mismo valor en el atributo Nombre de cuenta. |
    | Tipo de registro base | Cuenta |
    | Tipo de registro coincidente | Cuenta |
    | Nombre de cuenta (campo) | Coincidencia exacta |
    | Empresa (campo) | Coincidencia exacta |
    | Tipo de relación (campo) | Coincidencia exacta |
    | Id. de parte (campo) | Coincidencia exacta |
    | Seleccionar (campo) | (en blanco) |

    ![Regla de duplicados para Cuentas.](media/duplicate-rule-1.PNG)

10. Expanda la regla de detección de duplicados para la tabla **Contactos** configurando los siguientes campos.

    | Campo | Valor |
    |-------|-------|
    | Nombre | Contactos con el mismo nombre y apellido. |
    | Descripción | Detecta registros de contactos que tienen los mismos valores en los campos Nombre y Apellido. |
    | Tipo de registro base | Contacto |
    | Tipo de registro coincidente | Contacto |
    | Nombre (campo) | Coincidencia exacta |
    | Apellido (campo) | Coincidencia exacta |
    | Empresa (campo) | Coincidencia exacta |
    | Id. de parte (campo) | Coincidencia exacta |
    | Seleccionar (campo) | (en blanco) |

    ![Regla de duplicados para Contactos.](media/duplicate-rule-2.PNG)

11. Si ya es usuario de escritura dual, siga las instrucciones en [Actualizar al modelo de libreta de direcciones global y de parte](upgrade-party-gab.md) y actualice sus datos.

12. Ejecute las asignaciones en el orden siguiente. Si recibe un error que dice "Error en la validación del proyecto. Falta el campo de destino... ", entonces abra el mapa y seleccione **Actualizar tablas**. Luego ejecute la asignación.

    Aplicación de Finance and Operations | Aplicación Customer Engagement  
    ----------------------------|------------------------
    [Partes de CDS](mapping-reference.md#220) | msdyn_parties
    [Ubicaciones de dirección postal de CDS](mapping-reference.md#234) | msdyn_postaladdresscollections
    [Historial de dirección postal de CDS V2](mapping-reference.md#235) | msdyn_postaladdresses
    [Ubicaciones de dirección postal de entidad CDS](mapping-reference.md#233) | msdyn_partypostaladdresses
    [Contactos de parte V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses
    [Clientes V3](mapping-reference.md#101) | cuentas
    [Clientes V3](mapping-reference.md#116) | contactos
    [Proveedores V2](mapping-reference.md#202) | msdyn_vendors
    [Cargos de persona de contacto](mapping-reference.md#223) | msdyn_salescontactpersontitles
    [Despedidas de agradecimiento](mapping-reference.md#222) | msdyn_complimentaryclosings
    [Formas de saludo](mapping-reference.md#228) | msdyn_salutations
    [Roles de toma de decisiones](mapping-reference.md#224) | msdyn_decisionmakingroles
    [Funciones de trabajo de empleo](mapping-reference.md#225) | msdyn_employmentjobfunctions
    [Niveles de fidelización](mapping-reference.md#226) | msdyn_loyaltylevels
    [Tipos de carácter personal](mapping-reference.md#227) | msdyn_personalcharactertypes
    [Contactos V2](mapping-reference.md#221) | msdyn_contactforparties
    [Encabezado de presupuesto de ventas de CDS](mapping-reference.md#215) | presupuestos
    [Encabezado de pedidos de ventas de CDS](mapping-reference.md#217) | salesorders
    [Encabezados de factura de ventas V2](mapping-reference.md#118) | facturas

> [!NOTE]
> La asignación `CDS Contacts V2 (contacts)` es la asignación que detuvo en el paso 1. Cuando intenta ejecutar otras asignaciones, estas 2 asignaciones pueden aparecer en la lista de dependientes. No ejecute estas asignaciones.
>
> Si la solución de libreta de direcciones global y de parte está instalada, debe deshabilitar el complemento denominado `Microsoft.Dynamics.SCMExtended.Plugins.Plugins.LeadPrimaryContactPostCreate: QualifyLead of lead`. Si desinstala la solución de libreta de direcciones global y de parte, entonces debe volver a habilitar el complemento.
>
> El campo `msdyn_*partynumber` (un campo de texto de una sola línea) que se incluye en las tablas **Cuenta**, **Contacto** y **Proveedor** no debe utilizarse en el futuro. El nombre de la etiqueta tiene un prefijo de **(En desuso)** para mayor claridad. En su lugar, use el campo **msdyn_partyid**. El campo es una búsqueda de la tabla **msdyn_party**.

> Nombre de la tabla | Campo antiguo | Nuevo campo
> --------|-------|--------
> Cuenta | `msdyn_partynumber` | `msdyn_partyid`
> Contacto | `msdyn_partynumber` | `msdyn_partyid`
> msdyn_vendor | `msdyn_vendorpartynumber` | `msdyn_partyid`

## <a name="templates"></a>Plantillas

Una colección de mapas de tabla funciona conjuntamente para la interacción de partes y la libreta de direcciones global, como se muestra en la tabla siguiente.

| Aplicación de Finance and Operations | Aplicación Customer Engagement | Descripción |
|----------------------------|-------------------------|-------------|
| [Cargos de persona de contacto](mapping-reference.md#223) | msdyn\_salescontactpersontitles |
| [Clientes V3](mapping-reference.md#101) | cuentas |
| [Clientes V3](mapping-reference.md#116) | contactos |
| [Partes de CDS](mapping-reference.md#220) | msdyn\_parties |
| [Ubicaciones de dirección postal de entidad CDS](mapping-reference.md#233) | msdyn\_partypostaladdresses |
| [Historial de dirección postal de CDS V2](mapping-reference.md#235) | msdyn\_postaladdresses |
| [Ubicaciones de dirección postal de CDS](mapping-reference.md#234) | msdyn\_postaladdresscollections |
| [Encabezado de presupuesto de ventas de CDS](mapping-reference.md#215) | presupuestos |
| [Encabezado de pedidos de ventas de CDS](mapping-reference.md#217) | salesorders |
| [Despedidas de agradecimiento](mapping-reference.md#222) | msdyn\_complimentaryclosings |
| [Contactos V2](mapping-reference.md#221) | msdyn\_contactforparties |
| [Roles de toma de decisiones](mapping-reference.md#224) | msdyn\_decisionmakingroles |
| [Funciones de trabajo de empleo](mapping-reference.md#225) | msdyn\_employmentjobfunctions |
| [Niveles de fidelización](mapping-reference.md#226) | msdyn\_loyaltylevels |
| [Contactos de parte V3](mapping-reference.md#236) | msdyn\_partyelectronicaddresses |
| [Tipos de carácter personal](mapping-reference.md#227) | msdyn\_personalcharactertypes |
| [Encabezados de factura de ventas V2](mapping-reference.md#118) | facturas |
| [Formas de saludo](mapping-reference.md#228) | msdyn\_salutations |
| [Proveedores V2](mapping-reference.md#202) | msdyn\_vendors |

Para más información, consulte [Referencia de asignación de escritura doble](mapping-reference.md).

## <a name="known-issues-and-limitations"></a>Limitaciones y problemas conocidos

+ En aplicaciones de Finance and Operations, cuando crea un cliente junto con la dirección y lo guarda, es posible que la dirección no se sincronice con la tabla **Direcciones**. Esto se debe a un problema de secuenciación de la plataforma de escritura dual. Como solución alternativa, cree el cliente primero y guárdelo. Luego agregue la dirección.
+ En aplicaciones de Finance and Operations, cuando un registro de cliente tiene una dirección principal y usted crea un nuevo contacto para ese cliente, entonces el registro de contacto hereda una dirección principal del registro de cliente asociado. Esto también sucede con el contacto del proveedor. Dataverse actualmente no admite este comportamiento. Si la escritura dual está habilitada, los contactos de cliente heredados con una dirección principal de la aplicación Finance and Operations se sincronizan con Dataverse junto con su dirección.
+ Las direcciones electrónicas establecidas en la ficha de direcciones electrónicas de los formularios **Cuenta**, **Contacto** y **Proveedor** provienen de la tabla `msdyn_partyelectronicaddress`. Esta información no fluye a sus transacciones asociadas como pedido de ventas, presupuesto y orden de compra. Planeamos solucionar este problema en una versión incremental. Los datos existentes en los campos de dirección electrónica de la cuenta y los registros de contacto seguirán funcionando en transacciones como pedidos de venta, presupuesto y pedido de compra.
+ En aplicaciones de Finance and Operations, puede crear un registro de contacto desde el formulario **Agregar contacto**. Cuando intenta crear un nuevo contacto desde el formulario **Ver contacto**, la acción falla. Este es un problema conocido.

    ![Problema conocido con Agregar contacto.](media/party-gab-contact-issue.png)

+ **Sincronización inicial** no es compatible con los campos de tiempo **Disponible de** y **Disponible para** en **ContactForParty**, porque DIXF convierte el valor en una cadena en lugar de un número entero. La conversión desencadena el error `Cannot convert the literal '<say 08:00:00>’ to the expected type edm.int32`.
+ Cuando una dirección postal se utiliza por más de un motivo, por ejemplo, la dirección de comunicación comercial y la dirección de facturación, debe aparecer como `Business;Invoice`, como se muestra en la siguiente imagen. Si agrega un espacio entre los valores, obtendrá un error.

    ![Problema conocido con la dirección.](media/party-gab-address-issue.png)

+ No puede introducir una dirección postal con fecha anticipada usando una aplicación de Finance and Operations con escritura dual, porque Dataverse no es compatible con la fecha de vigencia. Si introduce una dirección postal con fecha futura usando una aplicación Finance and Operations, se sincroniza con Dataverse completamente y verá la dirección en la interfaz de usuario inmediatamente. Cualquier actualización de este registro resultará en un error, ya que está fechado en el futuro y no está actualizado en la aplicación de Finance and Operations.
