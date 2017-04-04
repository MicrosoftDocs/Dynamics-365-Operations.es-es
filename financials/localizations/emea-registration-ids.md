---
title: Id. de registro
description: "Este tema proporciona información acerca de la configuración y el uso id. de registro."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirPartTaxRegistrationSearch, LogisticsPostalAddress, TaxRegistrationLegislationTypes, TaxRegistrationType
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264824
ms.assetid: e86f0a35-be58-4ef5-b5ab-bcfc495eaa13
ms.search.region: Global
ms.author: vlru
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 32cd09975861083b8940368ed53ae16e89bcd748
ms.lasthandoff: 03/31/2017


---

# <a name="registration-ids"></a>Id. de registro

Este tema proporciona información acerca de la configuración y el uso id. de registro.

Muchos países y regiones tienen diferentes normativas y requisitos para registrar los números o Id. de registro. Este tema proporciona una visión general de la configuración y de procesamiento requerirán a tipos de registro admitidos para las partes en los distintos países europeos/regiones. Todos los países/regiones tienen los requisitos para admitir las distintas funciones específicas del país relacionadas con números de registro suministrado por distintas la oficina de estado. Ejemplos de los números de registro, el número de la Seguridad Social (SSN), el número de identificación fiscal (TIN), y la identificación Europea de IVA (identificador de la UE IVA). Esta característica permite el marco unificado para todos los países en todas las regiones que tienen en cuenta los requisitos específicos de países de algunos países europeos. Las secciones siguientes describen el flujo de información total que se usa para capitalizar y procesar id. de registro.

## <a name="registration-type-creation"></a>Creación del tipo de registro
Antes de poder especificar el identificador del registro, debe configurar los tipos de registro para los tipos de números de registro que cada entidad está sujeto a. Retroceda ** Administración de organización ** &gt; ** la libreta de direcciones global ** &gt; ** los tipos de registro ** &gt; ** los tipos de registro ** página para crear y gestionar los tipos de registro para Proveedores, Clientes, los trabajadores, y las entidades jurídicas en distintos países o regiones.

|Campo                 |Descripción      |
|------------------------------|----------------------------|                                                                           
| Nombre                | El nombre del tipo de registro. |                                                                           
| Descripción         | La descripción del tipo de registro. |
| País o región      | El identificador único del país/región.|
| Autoridad fiscal       | La autoridad fiscal asociado al tipo de registro.|
| Restringido a       | La clase de restricción que se aplica al registro de impuestos escrito: Ninguno, persona, organización.|
| Formato              | El formato de la validación del tipo de registro.|
| Se puede actualizar      | Define si el número de registro para el tipo de registro se puede actualizar tras especificar.|
| Único              | Define si el número de registro para el tipo de registro es único. |
| Principal para país o región | Si está asociada una parte país de una o varias direcciones en particular y el identificador del registro es válida para todas estas direcciones, debe designar una dirección como principal del país. Puede registrar a un identificador como principal. Define si el número de registro se puede especificar solo para principal para la dirección del país. |

## <a name="assign-a-registration-type-to-a-registration-category"></a>Asignar un tipo de registro a una categoría de registro
La categoría del registro es identificador del registro del país/región aprobado para usar en particular el país/región para impuestos, aduanas y otros propósitos. Esta categoría define reglas de validación de identificador determinado de registro (dígitos de control incluidos etc.). y de identificador del registro de inclusión en diversos informes. Use la página ** Administración de organización ** &gt; ** libreta de direcciones global ** &gt; ** los tipos de registro ** &gt; ** las categorías de registro ** asignar el tipo de registro de determinado país a la categoría compatible del registro.

| Campo            | Descripción|
|-----------------------|----------------|
| Tipo de registro     | El país o región del tipo de registro en particular.|
| Restringido a         | La clase de restricción aplica al registro de impuestos escrito: Ninguno, persona, organización.|
| Categoría de registro | El identificador único de registro aprobado para usar en el país. La lista completa de admitido en las categorías AX7.1 está continuación. |

## <a name="enter-registration-ids-for-global-address-book-records"></a>Id. del registro de la información para los registros de la libreta de direcciones global
La libreta de direcciones global (GAB) en Microsoft Dynamics 365 para las operaciones contiene la información de dirección consolidada para clientes, proveedores, contactos, relaciones empresariales, y las entidades jurídicas. Para obtener más información, consulte la información [] general de la libreta de direcciones global (/dynamics365/operations/organization-administration/overview-global-address-book). Los registros de parte que se almacenan en la libreta de direcciones global pueden contener uno o varios registros de dirección. Estas direcciones se usan para distintos fines, por ejemplo la facturación o entrega. Puede configurar los id. de registro para la información de dirección para clientes, proveedores, los trabajadores, y las entidades jurídicas. Encuentre la parte (la entidad jurídica, proveedores, clientes, trabajador) que el registro para el que desea indicar el identificador de registro, haga clic en ** los id. de registro ** de los formularios relacionados con la parte, entidad jurídica, proveedores, clientes, trabajador para abrir ** gestionar direcciones ** la página. En ** registro de impuestos ** la ficha, haga clic ** agregue **, y especifique la siguiente información sobre el identificador del registro.

|Campo                |Descripción                                                |
|---------------------|-----------------------------------------------------------|
| Tipo de registro   | El tipo de registro en el país o la región seleccionada.     |
| Número de registro | El identificador del registro de parte.                                |
| Descripción         | La descripción del número de registro.               |
| Grupo             | La información adicional sobre el número de registro. |
| Agencia emisora      | La autoridad que emitió el número de registro.        |
| Fecha de emisión         | La fecha emitida para el número de registro.              |
| Vigente           | La fecha de vigencia para el número de registro.           |
| Caducidad          | La fecha de caducidad para el número de registro.          |

> [!NOTE]
> El número de identificación fiscal de la entidad jurídica, proveedor, cliente puede ser seleccionado de los id. de registro relacionados con el identificador del IVA y especificados para la parte.

## <a name="search-for-records-by-registration-id"></a>Buscar para los registros por el identificador de registro
El Buscar para los registros de parte en función de un identificador de registro está disponible en los formularios relacionados con la parte, la entidad jurídica, el proveedor, el cliente, y el trabajador. Haga clic en ** búsqueda del identificador del registro ** a abrir ** criterios de búsqueda del identificador del registro ** la página. Especifique los criterios de búsqueda y haga clic en ** ** búsqueda. El sistema sólo mostrará los registros seleccionados de la libreta de direcciones global y de asociados los tipos de registro de parte.

## <a name="supported-registration-categories"></a>Categorías admitidas de registro
La tabla siguiente muestra los tipos de registro admitidos de Dynamics 365 para las operaciones. Si está familiarizado con Microsoft Dynamics AX 2012 campos para los Id. de registro, esta tabla asigna también dichos campos a Dynamics 365 para las categorías de registro de operaciones.

| Dinámica 365 para la categoría del registro de operaciones         |País/región  | Término/campo de AX 2012 Approvals|
|---------------------------------------------------------------|---------------------|---------------------------------|
| Id. de IVA                                                        | Todos los países de la Unión Europea (EU)|  Número de identificación fiscal (legales identificador de TAX del tipo en AX2012 R3)|
| Id. de empresa (COID)                                          | República Checa Estonia Hungría Letonia Lituania Polonia Suiza de Bélgica | Número de registro del número de empresa (EnterpriseNumber) (número de registro de RegNum\_W) (número de registro de RegNum\_W) (número de registro de RegNum\_W) (RegNum empresa de\_W) código el número de registro de EnterpriseCode () (RegNum\_W UID) (tipo legales UID en AX2012 R3) |
| Id. de sucursal                                                     | Bélgica            | Número de sucursal (BranchNumber)|
| Značka de Spisová (número de registro, enviando la agencia, la sección) | República Checa     | Número de inserción () CommercialRegisterInsetNumber retenerse en la sección de registro comercial (CommercialRegister) del registro comercial (CommercialRegisterSection)|
| Id. de cliente de aduanas                                           | Finlandia | Número de cliente de aduanas (CustomsCustomerNumber\_FI)|
| INN                                                           | Federación Rusa| INN (tipo legales en INN AX2012 R3)|
| RRC                                                           | Federación Rusa| RRC (tipo legales en RRC AX2012 R3)|
| OKDP                                                          | Federación Rusa| OKDP (tipo legales en OKDP AX2012 R3)|
| OKPO                                                          | Federación Rusa| OKPO (tipo legales en OKPO AX2012 R3)|
| RCOAD                                                         | Federación Rusa| RCOAD (tipo legales en RCOAD AX2012 R3)|
| OGRN                                                          | Federación Rusa| OGRN (tipo legales en OGRN AX2012 R3) |
| SNILS                                                         | Federación Rusa| SNILS (tipo legales en SNILS AX2012 R3)|
| CIFTS                                                         | Federación Rusa| CIFTS (tipo legales en CIFTS AX2012 R3)|

Para obtener más información acerca de los id. de registro que procesan, incluidos requisitos previos necesarios, consulte los registros de la siguiente tarea para el identificador de IVA en los servicios (LCS) del ciclo de vida:

-   Configuración del Id. de IVA
-   Registro del identificador de IVA del proveedor
-    Búsqueda de la parte mediante el Id. de IVA



