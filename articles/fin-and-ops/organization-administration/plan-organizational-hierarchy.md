---
title: "Planificación de su jerarquía organizativa"
description: "Antes de configurar las organizaciones y las jerarquías organizativas, asegúrese de saber cómo se modelará la empresa."
author: sericks007
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17404
ms.assetid: babde0c6-bb5d-45ae-95ca-2af75a0ea292
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 45a00f03519679f07c95a669727ecd2fa1a91c41
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="plan-your-organizational-hierarchy"></a>Planificación de su jerarquía organizativa

[!include[banner](../includes/banner.md)]


Antes de configurar las organizaciones y las jerarquías organizativas en Microsoft Dynamics 365 for Finance and Operations, asegúrese de tener previsto cómo se modelará la empresa. El modelo organizativo tiene un importante efecto en la implementación de Finance and Operations y en los procesos empresariales. 

Las jerarquías organizativas representan las relaciones que hay entre las organizaciones que componen un negocio. Por lo tanto, la consideración más importante a la hora de modelar las organizaciones es la estructura de la empresa. Se recomienda definir las estructuras de la organización basándose en los comentarios de los ejecutivos y directores sénior de áreas funcionales, como finanzas y contabilidad, recursos humanos, operaciones, compras y ventas y marketing. 

Al planificar jerarquías, también es importante tener en cuenta la relación entre la jerarquía organizativa y las dimensiones financieras. Puede configurar varias jerarquías organizativas para representar distintas vistas de la empresa. Al utilizar dimensiones financieras, puede crear informes basados en estas vistas. Trabaje con su socio Microsoft Dynamics 365 for Finance and Operations para crear las jerarquías que se ajusten a las necesidades de informes tanto organizativas y como estatutarias. 

> [!Note]
> Aunque puede usar dimensiones financieras para representar entidades jurídicas sin crear entidades jurídicas en Finance and Operations, las dimensiones financieras no están diseñadas para satisfacer las necesidades operativas o empresariales de las entidades jurídicas. La funcionalidad de contabilidad de interunidad de Finance and Operations está diseñada para tratar solo los asientos contables creados por cada transacción. 

> [!Caution]
> No debe decidir cómo modelar organizaciones en función de solo la información que se proporciona en este artículo. Esta documentación es una guía de orientación. Puede colaborar su socio de Finance and Operations para obtener asistencia adicional. Su socio de Finance and Operations ha obtenido experiencia en diversos sectores y en la base de clientes.

## <a name="decide-whether-to-model-internal-organizations-as-legal-entities-or-operating-units"></a>Decidir si modelar organizaciones internas como entidades jurídicas o unidades operativas

Debe tener al menos una entidad jurídica para representar su empresa en Finance and Operations. Una entidad jurídica puede realizar contratos legales y tiene la obligación de preparar informes financieros que informan sobre su rendimiento. 

En Finance and Operations, las entidades jurídicas pueden usarse para el negocio transaccional o para la consolidación. Esto significa que una entidad jurídica en Finance and Operations no representa necesariamente una entidad real en la empresa. Por ejemplo, una empresa que participa en transacciones puede ser propietaria de entidades jurídicas subsidiarias. En esta situación, se requiere a una entidad jurídica para las transacciones y se requiere una entidad jurídica virtual para consolidar los resultados y los saldos de las entidades jurídicas subsidiarias. 

Las organizaciones internas de la empresa, tales como las oficinas regionales, se pueden representar como entidades jurídicas adicionales o como unidades operativas de la entidad jurídica principal. No es necesario que una unidad operativa sea una organización legalmente definida. Las unidades operativas se usan para controlar los recursos económicos y los procesos operativos de la empresa. Por ejemplo, los departamentos y los centros de coste son unidades operativas. 

Parte de la funcionalidad de Finance and Operations opera de manera diferente en función de si la organización es una entidad jurídica o una unidad operativa. Tenga en cuenta la posibilidad de usar al funcionalidad que se describe a continuación mientras toma una decisión. 


### <a name="master-data"></a>Datos maestros
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica      
Algunos datos maestros, como clientes, condiciones de pago, autoridades fiscales y pedidos de existencias de sito específico, se deben configurar para cada entidad jurídica. Algunos datos maestros, como usuarios, productos y la mayoría de los datos de recursos humanos, se comparten entre todas las entidades jurídicas. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Los datos maestros se comparten entre las unidades operativas. 

### <a name="module-parameters"></a>Parámetros de módulo
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica    
Los parámetros para módulos, como Clientes, Proveedores y los de gestión de efectivo y bancos, se deben establecer por entidad jurídica. Dado que la configuración del módulo para las entidades jurídicas es independiente, cada filial puede cumplir con los requisitos estatutarios y las prácticas empresariales locales. Por ejemplo, una entidad jurídica de servicios profesionales y una entidad jurídica de fabricación pueden tener distintos parámetros de módulo, aunque informen sobre la misma empresa matriz. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Los parámetros del módulo se comparten entre las unidades operativas. 

### <a name="data-security"></a>Seguridad de los datos
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica    
La mayoría de los datos se protegen automáticamente por el identificador de la empresa. Un identificador de empresa es un identificador exclusivo para los datos asociados a una entidad jurídica. Una empresa puede estar asociada solo a una entidad jurídica y una entidad jurídica puede estar asociada a una sola empresa. Los usuarios solo pueden acceder a los datos de las empresas a las que tengan acceso. No es necesario personalizar Finance and Operations para proteger los datos por identificador de la empresa. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Los datos se pueden proteger por unidad operativa mediante la creación de directivas de seguridad de datos personalizadas. Las directivas de seguridad de datos se usan para limitar el acceso a los datos. Por ejemplo, supongamos que se permite a un usuario crear pedidos de compra solo en una unidad operativa concreta. Las directivas de seguridad de datos se pueden crear para evitar que el usuario de datos acceda a los datos del pedido de compra de cualquier otra unidad operativa. El volumen de transacciones y el número de directivas de seguridad pueden afectar al rendimiento. Cuando se diseñan directivas de seguridad, tenga en cuenta el rendimiento. 

### <a name="ledgers"></a>Libros mayores
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica    
Cada entidad jurídica requiere un libro mayor que proporcione un plan de cuentas, la divisa de contabilidad, la divisa de notificación y el calendario fiscal. Un balance de situación se puede crear solo para una entidad jurídica. Las cuentas principales, las dimensiones, las estructuras contables, los planes contables y las reglas contables las pueden usar varias entidades jurídicas.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Una unidad operativa no puede tener su propia información de libro mayor. Si las organizaciones internas no requieren libros mayores únicos, puede modelarlos como unidades operativas. La información del libro mayor se configurará para la entidad jurídica principal de la jerarquía. Los extractos de ingresos se pueden crear para las unidades operativas en una entidad jurídica o para la entidad jurídica principal. 

### <a name="fiscal-calendars"></a>Calendarios fiscales 
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica    
Cada entidad jurídica tiene su propio calendario fiscal. Si las organizaciones internas usan distintos ejercicios y calendarios fiscales, debe modelar las organizaciones como entidades jurídicas. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Las unidades operativas deben compartir un calendario fiscal. Si las organizaciones internas pueden usar los mismos ejercicios y calendarios fiscales, puede modelar las organizaciones como unidades operativas. 

### <a name="consolidation"></a>Consolidación
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica    
Debe consolidar los resultados financieros de las oficinas regionales en una sola empresa consolidada para preparar informes financieros. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
La consolidación no es necesaria, ya que los datos se comparten entre unidades operativas. 

### <a name="centralized-payments"></a>Pagos centralizados
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica 
Los pagos centralizados deben configurarse para que las facturas de todas las entidades jurídicas secundarias se puedan pagar a una sola entidad jurídica principal o desde ella. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Los pagos centralizados no se requieren porque todas las facturas se registran en una única entidad jurídica.

### <a name="intercompany-transactions"></a>Transacciones de empresas vinculadas
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica 
Los pedidos de ventas, los pedidos de compra, los pagos o las recepciones de empresas vinculadas se pueden aplicar entre sí. No es necesario utilizar asientos del diario. Puede ver transacciones de empresas vinculadas en el nivel del subdiario (clientes, proveedores). Los ejemplos siguientes muestran cómo se administrarán las transacciones de empresas vinculadas. 

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Ejemplo 1: la sede central proporciona servicios a las oficinas regionales y deben cobrar los costes de dichos servicios a las oficinas regionales.
Si modeló la oficina regional como entidad jurídica, tiene las siguientes opciones: 
- La sede central crea una entrada del diario para realizar el cobro cruzado a la oficina regional en concepto del gasto. Las transacciones no se pueden vencer.
- La sede central envía un pedido de compra para los servicios a la oficina regional. Un pedido de ventas se crea automáticamente en la entidad jurídica para la oficina regional, con transacciones de subdiario de empresas vinculadas. 

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Ejemplo 2: la sede central procura y paga el servicio que se entrega a una oficina regional.
Si modeló la oficina regional como entidad jurídica, tiene las siguientes opciones: 
- La factura y el pago siguen las normas legales de la sede central. La sede central puede crear una entrada del diario para realizar el cobro cruzado a la oficina regional en concepto del gasto. Las transacciones no se pueden vencer. 
- La factura y el pago siguen las normas legales de la sede central. La sede central puede crear una transacción de subdiario de empresas vinculadas.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Las transacciones de empresas vinculadas entre las unidades operativas se admiten solo a través de asientos del diario. Una unidad operativa no puede emitir o recibir un pedido de compra, un pedido de ventas o una factura de otra unidad operativa en la misma entidad jurídica. No puede ver transacciones de empresas vinculadas en el nivel del subdiario (clientes, proveedores). Los ejemplos siguientes muestran cómo se administrarán las transacciones de empresas vinculadas. 

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Ejemplo 1: la sede central proporciona servicios a las oficinas regionales y deben cobrar los costes de dichos servicios a las oficinas regionales.
Si ha modelo la oficina regional como unidad operativa, la sede especifica una transacción de gastos y la codifica en la oficina regional. 

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Ejemplo 2: la sede central procura y paga el servicio que se entrega a una oficina regional.
Si ha modelo la oficina regional como unidad operativa, la factura y el pago siguen las normas legales de la sede. La factura se puede codificar en la oficina regional. En el informe de ingresos, use una dimensión financiera de equilibrio para informar sobre los costes de la oficina regional.

### <a name="local-tax-requirements"></a>Requisitos de impuestos locales
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica
Una entidad jurídica está sujeta a la legislación fiscal de la autoridad fiscal para el país o región donde está registrada la entidad jurídica. Por ejemplo, una entidad jurídica registrada en Dinamarca está sujeta a la legislación fiscal y las normas danesas. En Finance and Operations, una entidad jurídica puede pertenecer a un sola país o región. El país o región que seleccione como dirección principal de la entidad jurídica controla las características específicas de dicho país o región que están disponibles para esa entidad jurídica. Por ejemplo, si la dirección principal de la entidad jurídica se encuentra en Dinamarca, están disponibles las características relacionadas con la legislación fiscal y las normas danesas. Por lo tanto, si las organizaciones se encuentran en diferentes países o regiones, y requieren diferentes opciones de impuestos locales, debe configurar las organizaciones como entidades jurídicas independientes.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Las unidades operativas usan el contexto del país o región de la entidad jurídica principal. Las unidades operativas de la misma entidad jurídica no pueden tener varios requisitos específicos del país o región. Si las organizaciones se encuentran en el mismo país o región y usan las mismas opciones de impuestos, se pueden configurarlas como unidades operativas.


### <a name="statutory-reporting-for-a-countryregion"></a>Informes estatutarios para un país o región 
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica
Para los países o regiones admitidos por Finance and Operations, se puede crear la mayoría de los informes estatutarios. Para obtener más información acerca de qué informes están disponibles para cada país o región, vea el [Microsoft Dynamics Localization Portal](https://mbs.microsoft.com/customersource/global/ax/support/support-news/GFMLocalizationPortalMC) para Finance and Operations. (Se requiere un inicio de sesión en CustomerSource). 

> [!Note]
> En Finance and Operations, una capa de registro en la contabilidad general permite realizar entradas de ajuste a una empresa matriz que usa un estándar de contabilidad distinto del de la empresa secundaria. Por ejemplo, para una empresa que usa prácticas de contabilidad normalmente aceptadas en el Reino Unido (GAAP de Reino Unido), puede crear entradas de ajuste en la capa de registro. Estas entradas se pueden consolidar en una empresa matriz que usa los principios contables generalmente aceptados (GAAP) en Estados Unidos. Las entradas de ajuste no afectan a los informes de GAAP de Reino Unido.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Los informes estatutarios se deben crear utilizando otra aplicación. Debe asegurarse de que los datos se capturen en Finance and Operations para admitir los requisitos de cada unidad operativa, donde difieren de los requisitos de la sede central. 

### <a name="currency"></a>Divisa
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica
Si las organizaciones deben utilizar distintas divisas funcionales, debe modelarlas como entidades jurídicas. Las divisas funcionales se configuran por entidad jurídica. Sin embargo, puede especificar transacciones en varias divisas. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Si las organizaciones pueden usar una sola divisa funcional, puede modelarlas como unidades operativas. Las unidades operativas deben compartir una divisa funcional. Sin embargo, puede especificar transacciones y crear informes en varias divisas. 


### <a name="year-end-closing"></a>Cierre de fin de año
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica
Si las leyes y las prácticas de contabilidad difieren los países o regiones donde se encuentran las organizaciones, es posible que necesite distintos procedimientos de fin de año por organización. Esto significa que debe modelar las organizaciones como entidades jurídicas. Cada entidad jurídica tiene sus propios procedimientos de cierre de fin de año. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Si las leyes y las prácticas de contabilidad son las mismas entre los países o regiones donde se encuentran las organizaciones, puede utilizar un único conjunto de procedimientos de fin de año. Esto significa que puede modelar las organizaciones como unidades operativas. Todas las unidades operativas deben usar el mismo procedimiento de cierre de fin de año. 
   
### <a name="number-sequences"></a>Secuencias numéricas
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica
Las secuencias numéricas para algunas referencias se pueden configurar por entidad jurídica. Algunas secuencias numéricas se pueden compartir. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Las secuencias numéricas para algunas referencias se pueden configurar por unidad operativa. Algunas secuencias numéricas se pueden compartir.

### <a name="products"></a>Productos 
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica
Las definiciones de producto se comparten y se deben lanzar a las entidades jurídicas individuales para que se puedan incluir en las transacciones. Cada entidad jurídica tiene su propio conjunto de productos lanzados que se pueden incluir en los documentos de transacción. Si las organizaciones internas deben utilizar distintos conjuntos de productos, debe modelarlas como entidades jurídicas. 

> [!Note]
> Aunque las definiciones de producto se comparten, en cada entidad jurídica en la que se ha lanzado un producto, puede especificar distintos parámetros de ventas, compra e inventario para el artículo en cada sitio de inventario. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
Todas las unidades operativas comparten el mismo conjunto de productos. Si las organizaciones internas pueden compartir el mismo conjunto de productos, puede modelar las organizaciones como unidades operativas. 

### <a name="inquiry-and-reporting"></a>Consulta e informes  
#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Si la organización se ha modelado como entidad jurídica
Debe cambiar manualmente las empresas para especificar transacciones y realizar consultas en varias entidades jurídicas. Debido a los límites de seguridad de datos, la consulta consolidada y los informes pueden emplear un gran número de recursos y llevar mucho tiempo. 

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Si la organización se ha modelado como unidad operativa 
No es necesario cambiar las empresas para acceder a los datos de varias unidades operativas. La consulta y los informes consolidados y la consulta regional individual son más fáciles y más rápidas.

## <a name="best-practices-for-modeling-organizations-and-hierarchies"></a>Prácticas recomendadas para modelar organizaciones y jerarquías
Tenga en cuenta las siguientes prácticas recomendadas al implementar una jerarquía organizativa:
-   Cree un departamento para modelar la intersección entre una entidad jurídica y una unidad de negocio. A continuación, puede acumular datos de un departamento a una entidad jurídica para informes estatutarios, y desde un departamento a una unidad de negocio para informes internos. Los departamentos pueden servir como centros de ganancias. Si usa departamentos, no tiene que usar entidades jurídicas y unidades de negocio como dimensiones en la estructura contable. Puede usar únicamente departamentos como una dimensión. Sin embargo, debe usar centros de costes y departamentos como dimensiones en la estructura contable si los centros de costes solo se usan como acumuladores de costes y los departamentos se usan como aprobación de ingresos.
-   Modele varias jerarquías para unidades operativas si tiene requisitos complejos para notificar pérdidas y ganancias.
-   En una única entidad jurídica, no modele varias jerarquías para el mismo propósito de la jerarquía.
-   No cree una jerarquía para cada propósito. Por lo general, puede usar una jerarquía para distintos fines. Por ejemplo, se puede asignar una jerarquía de unidades operativas a todos los propósitos relacionados con directivas.
-   Crea jerarquías equilibradas. En una jerarquía, todos los nodos que tienen la misma distancia del nodo raíz se definen como un nivel. En una jerarquía equilibrada, solo se puede producir un tipo de unidad operativa en cada nivel, y la distancia del nodo raíz hasta cada uno de los niveles es coherente. Si hay niveles intermedios entre un departamento y una entidad jurídica o una unidad de negocio, las organizaciones de marcador de posición pueden ser necesarias para crear una jerarquía equilibrada.
-   No modele una jerarquía independiente de las unidades operativas si la estructura para las entidades jurídicas también es su estructura operativa. Una jerarquía mixta de entidades jurídicas y unidades operativas puede servir a ambos propósitos.
-   Antes de modelar los escenarios de reestructuración principales, use las fechas de vigencia de la jerarquía para llevar a cabo un análisis de impacto y una prueba de validación.
-   Use el modo de borrador para cambiar una jerarquía antes de publicar una nueva versión en un entorno de producción.
-   Limite el número de personas con permisos para agregar o quitar organizaciones de una jerarquía en un entorno de producción. Un número más pequeño reduce la posibilidad de que se puedan producir costosos errores y de que se deban realizar correcciones.

