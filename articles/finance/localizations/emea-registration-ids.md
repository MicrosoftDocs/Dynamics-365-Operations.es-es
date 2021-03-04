---
title: Id. de registro
description: Este tema proporciona información acerca de la configuración y el uso de Id. de registro.
author: ShylaThompson
manager: AnnBe
ms.date: 11/08/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 264824
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7a0b978228e26ec70457a4bcb1c064070953909b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447755"
---
# <a name="registration-ids"></a>Id. de registro

[!include [banner](../includes/banner.md)]

Este tema proporciona información acerca de la configuración y el uso de Id. de registro.

Muchos países y regiones tienen diferentes normativas y requisitos para registrar números de registro o Id. Este tema proporciona una visión general de la configuración y el procesamiento requeridos para los tipos de registro admitidos para las partes en los distintos países/regiones europeos. Todos los países/regiones tienen requisitos propios para admitir las distintas funciones específicas del país relacionadas con los números de registro suministrados por las distintas oficinas de Estado. Ejemplos de los números de registro son: el número de la Seguridad Social (SSN), el número de identificación fiscal (TIN), y la identificación Europea de IVA (identificador de IVA de la UE). Esta característica proporciona un marco unificado para todos los países en todas las regiones y tiene en cuenta los requisitos específicos de algunos países europeos. Las siguientes secciones describen el flujo general de información que se utiliza para configurar y procesar los Id. de registro.

## <a name="registration-type-creation"></a>Creación de tipo de registro
Para poder especificar el Id. de registro, debe configurar tipos de registro para los diversos tipos de números de registro a los que está sujeta cada parte. Vaya a la página **Administración de la organización** &gt; **Libreta de direcciones global** &gt; **Tipos de registro** &gt; **Tipos de registro** para crear y gestionar los tipos de registro para proveedores, clientes, trabajadores, y entidades jurídicas en distintos países o regiones.

|Campo                 |Descripción      |
|------------------------------|----------------------------|                                                                           
| Nombre                | El nombre del tipo de registro. |                                                                           
| Descripción         | La descripción del tipo de registro. |
| País o región      | El identificador único del país/región.|
| Autoridad fiscal       | La autoridad fiscal asociada al tipo de registro.|
| Restringido a       | La clase de restricción que se aplica al tipo de registro de impuestos: Ninguno, persona, organización.|
| Formato              | El formato de validación del tipo de registro.|
| Se puede actualizar      | Indica si el número de registro del tipo de registro se puede actualizar después de especificarlo.|
| Único              | Indica si el número de registro del tipo de registro es único. |
| Principal para país o región | Si una parte está asociada a una o varias direcciones en un país determinado y el identificador del registro es válido para todas estas direcciones, debe designar una de las direcciones como la dirección principal en dicho país. Solo puede registrar un identificador como principal. Define si el número de registro se puede especificar solo para la dirección principal del país. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Asignar un tipo de registro a una categoría de registro
La categoría del registro es un identificador de registro de país/región aprobado en un país/región determinado para impuestos, aduanas y otros propósitos. Esta categoría define reglas de validación de un identificador determinado de registro (dígitos de control incluidos etc.) y de un identificador del registro de inclusión en diversos informes. Use la página **Administración de la organización** &gt; **Libreta de direcciones global** &gt; **Tipos de registro** &gt; **Categorías de registro** para asignar el tipo de registro de un determinado país a la categoría compatible del registro.

| Campo            | Descripción|
|-----------------------|----------------|
| Tipo de registro     | El tipo de registro en un país/región particular.|
| Restringido a         | La clase de restricción que se aplica al tipo de registro de impuestos: Ninguno, persona, organización.|
| Categoría de registro | El identificador único de registro aprobado para usar en el país. La lista completa de categorías admitidas se muestra más adelante en este tema. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Especificar el identificador del registro de los registros de la libreta de direcciones global

La libreta de direcciones global (GAB) contiene información de dirección consolidada para clientes, proveedores, contactos, relaciones empresariales y entidades jurídicas. Para obtener más información, consulte la [visión global de la libreta de direcciones global](../../fin-and-ops/organization-administration/overview-global-address-book.md). Los registros de partes que se almacenan en la libreta de direcciones global pueden contener uno o varios registros de dirección. Estas direcciones se usan para distintos fines, por ejemplo la facturación o entrega. Puede configurar los identificadores de registro de la información de dirección de clientes, proveedores, trabajadores y entidades jurídicas. Encuentre el registro de la parte (entidad jurídica, proveedor, cliente, trabajador) cuyo identificador de registro quiera especificar y haga clic en **Id. de registro** en los formularios relacionados con la parte, entidad jurídica, proveedor, cliente, trabajador, para abrir la página **Administrar direcciones**. En la ficha **Registro de impuestos**, haga clic en **Agregar** y especifique la siguiente información sobre el identificador del registro.


|Campo                |Descripción                                                |
|---------------------|-----------------------------------------------------------|
| Tipo de registro   | El tipo de registro en el país/región seleccionado.     |
| Número de registro | El identificador del registro de parte.                                |
| Descripción         | La descripción del número de registro.               |
| Grupo             | La información adicional sobre el número de registro. |
| Agencia emisora      | La autoridad que emitió el número de registro.        |
| Fecha de emisión         | La fecha de emisión del número de registro.              |
| Vigente           | La fecha efectiva del número de registro.           |
| Caducidad          | La fecha de vencimiento del número de registro.          |

> [!NOTE]
> El número de identificación fiscal de la entidad jurídica, proveedor, cliente puede ser seleccionado a partir de los identificadores de registro relacionados con el identificador del IVA y especificados para la parte.

## <a name="search-for-records-by-registration-id"></a>Buscar registros por el identificador de registro
La búsqueda de registros de partes en función de un identificador de registro está disponible en los formularios relacionados con la parte, la entidad jurídica, el proveedor, el cliente, y el trabajador. Haga clic en **Búsqueda de id. de registro** para abrir la página **Criterios de búsqueda de id. de registro**. Especifique los criterios de búsqueda y haga clic en **Buscar**. El sistema mostrará los registros seleccionados de la libreta de direcciones global y los tipos asociados de registro de parte.

## <a name="supported-registration-categories"></a>Categorías de registro admitidas
La tabla siguiente muestra los tipos de registro admitidos. Si está familiarizado con los campos de Microsoft Dynamics AX 2012 para los Id. de registro, esta tabla también asigna dichos campos a las categorías de registro de Dynamics 365 Finance.

| Categoría de registro de Finance         |País/región  | Término/campo de Dynamics AX 2012|
|---------------------------------------------------------------|---------------------|---------------------------------|
| Id. de IVA                                                        | Todos los países de la Unión Europea (EU)|  Número de identificación fiscal (ID DE IMPUESTO de tipo legislativo en AX 2012 R3)|
| Id. de empresa (COID)                                          | Bélgica, República Checa, Estonia, Hungría, Letonia, Lituania, Polonia, Suiza | Número de empresa (EnterpriseNumber) Número de registro (RegNum\_W) Número de registro (RegNum\_W) Número de registro (RegNum\_W) Número de registro (RegNum\_W) Código de empresa (EnterpriseCode) Número de registro (RegNum\_W) UID (UID de tipo legislativo en AX 2012 R3) |
| Id. de sucursal                                                     | Bélgica            | Número de sucursal (BranchNumber)|
| Spisová značka (número de registro, agencia emisora, sección) | República Checa     | Número de bajorrelieve (CommercialRegisterInsetNumber) en la sección de registro comercial (CommercialRegisterSection) del registro comercial (CommercialRegister)|
| Id. de cliente de aduanas                                           | Finlandia | Número de cliente de aduanas (CustomsCustomerNumber\_FI)|
| INN                                                           | Federación Rusa| INN (tipo legislativo INN en AX 2012 R3)|
| RRC                                                           | Federación Rusa| RRC (tipo legislativo RRC en AX 2012 R3)|
| OKDP                                                          | Federación Rusa| OKDP (tipo legislativo OKDP en AX 2012 R3)|
| OKPO                                                          | Federación Rusa| OKPO (tipo legislativo OKPO en AX 2012 R3)|
| RCOAD                                                         | Federación Rusa| RCOAD (tipo legislativo RCOAD en AX 2012 R3)|
| OGRN                                                          | Federación Rusa| OGRN (tipo legislativo OGRN en AX 2012 R3) |
| SNILS                                                         | Federación Rusa| SNILS (tipo legislativo en SNILS AX 2012 R3)|
| CIFTS                                                         | Federación Rusa| CIFTS (tipo legislativo CIFTS en AX 2012 R3)|
| Pasaporte                                                      | España             | Pasaporte|
| Documento de identificación oficial                              | España             | Documento de identificación oficial|
| Certificado de residencia                                         | España             | Certificado de residencia|
| Otro documento de identificación                                 | España             | Otro documento de identificación|
| Sin censar                                                  | España             | No disponible en AX 2012 R3|


Para obtener más información acerca del procesamiento de los id. de registro, incluidos requisitos previos necesarios, consulte las grabaciones de tareas para el identificador de IVA en Lifecycle Services (LCS):

-   Configuración del Id. de IVA
-   Registro de ID de IVA del proveedor
-    Búsqueda de la parte mediante el Id. de IVA






[!INCLUDE[footer-include](../../includes/footer-banner.md)]