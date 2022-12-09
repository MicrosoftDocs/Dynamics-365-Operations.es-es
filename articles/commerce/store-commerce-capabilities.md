---
title: Capacidades de la aplicación Store Commerce
description: Este artículo describe la funcionalidad que está disponible en la aplicación Store Commerce para Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2022-09-30
ms.openlocfilehash: 58f2ab1f913d3629de7971c8eeb2d1821161e44f
ms.sourcegitcommit: 29d9a7573bdac004726da88a9d7b2cc9c383e9ca
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2022
ms.locfileid: "9788523"
---
# <a name="store-commerce-app-capabilities"></a>Capacidades de la aplicación Store Commerce

[!include [banner](includes/banner.md)]

La aplicación Store Commerce es la experiencia de punto de venta (PDV) moderno de Microsoft Dynamics 365 Commerce. Permite que las empresas procesen transacciones en la tienda y gestionen las operaciones del área de operaciones, como el inventario y el procesamiento de pedidos. La aplicación también permite a las empresas gestionar las relaciones con los clientes mediante la fidelización y la clientela. 

Gracias a la tecnología de Commerce Scale Unit (CSU), la aplicación Store Commerce proporciona una solución omnicanal completa. Por ejemplo, un cliente puede comprar un producto en línea y recogerlo en una tienda cercana, prosiguiendo así su día de compras a través de los canales sin perder ningún dato. 

Este artículo proporciona una visión general de las capacidades de la aplicación Store Commerce.

## <a name="platform"></a>Plataforma

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Omnicanal | Dynamics 365 Commerce ofrece una completa solución omnicanal que unifica las experiencias del área de operaciones, la tienda, el centro de llamadas y digitales. | [Información general](index.md) | [Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/dynamics-365-commerce-overview-november-2-2020) |
| Commerce sin periféricos | Commerce Scale Unit hospeda el motor de comercio sin periféricos. El motor de comercio sin periféricos sirve de punto central para toda la lógica de negocio comercial y es la base de una solución omnicanal completa. | <p>[Información general de la arquitectura](commerce-architecture.md)</p><p>[Arquitectura sin periféricos](dev-itpro/retail-server-architecture.md)</p> | [Charla técnica](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-commerce-architecture-overview-december-4-2020) |
| Commerce Headquarters | Commerce headquarters brinda capacidades de área de operaciones que permiten la configuración de productos, empleados, procesos de negocio, precios y otras funcionalidades que se requieren para el negocio. | [Información general de la arquitectura](commerce-architecture.md) | |
| Punto de venta (PDV) | La aplicación Store Commerce es la experiencia de PDV de Dynamics 365 Commerce. Ofrece capacidades de PDV completas y de gran riqueza de funciones que ayudan a los asociados de ventas, cajeros y gerentes a brindar un servicio al cliente de calidad superior. Además, proporciona varias opciones de implementación a los minoristas, ayuda a mejorar el rendimiento y ofrece una mejor gestión del ciclo de vida de las aplicaciones (ALM). | [Aplicación Store Commerce](dev-itpro/store-commerce.md) | <p>[Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/modernize-the-dynamics-365-commerce-in-store-technology-using-the-new-store-commerce-app-march-30-2022)</p><p>[Vídeo](https://youtu.be/7B332XH_zfs)</p><p>[Migración desde MPOS a Store Commerce](dev-itpro/pos-extension/migrate-mpos-store-commerce.md)</p> |
| Implementación en la nube | Se pueden implementar varias instancias de Commerce Scale Units para distribución de carga y proximidad geográfica. | [Implementación en la nube](../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md) | |
| Implementación local | Con una implementación de datos empresariales local, los clientes de Commerce pueden tener más capacidad de control y administración de los entornos de Dynamics 365. | [Implementación local](../fin-ops-core/dev-itpro/deployment/deploy-retail-onprem.md) | |

## <a name="device-management"></a>Administración de dispositivos

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Múltiples factores de forma | La aplicación Store Commerce es compatible con múltiples factores de forma de dispositivos, como equipos, tabletas y dispositivos móviles. La interfaz de usuario (UI) receptiva permite que el diseño se redimensione automáticamente y se ajuste al tamaño de la pantalla. | [Configuraciones visuales](pos-screen-layouts.md) |  |
| Multiplataforma | La aplicación Store Commerce es compatible con plataformas web, Windows, iOS y Android. | [Plataformas](dev-itpro/hybridapp.md) | |
| Marca | El diseñador de pantalla le permite personalizar los diseños de pantalla para cumplir los requisitos de su negocio. Además, se pueden crear temas, diseños, colores e imágenes en función de los roles de los empleados, y luego se pueden compartir entre los usuarios para lograr coherencia de marca y facilidad de uso. | [Configuraciones visuales](pos-screen-layouts.md) | [Vídeo](https://www.youtube.com/watch?v=ldqCw2wf5fY) |
| Topología | Se admiten diferentes topologías en la tienda, según la disponibilidad de la red. | <p>[Topología](dev-itpro/retail-modern-pos-architecture.md)</p><p>[Infografía](dev-itpro/retail-in-store-topology.md)</p> | |
| Administración de varios dispositivos | Se pueden administrar fácilmente múltiples dispositivos en las tiendas desde Commerce headquarters. | [Activación](set-up-activation-accounts-validate-devices-hq.md) | [Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/commerce-mass-deployment-with-sccm-system-center-configuration-manager-october-6-2022) |

## <a name="employee-management"></a>Administración de empleados

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Iniciar sesión | Cada empleado de la tienda puede tener un inicio de sesión exclusivo. Los tipos de inicio de sesión incluyen nombre de usuario, código de barras, lector de bandas magnéticas (MSR), datos biométricos y Azure Active Directory (Azure AD). | <p>[Azure AD](aad-pos-logon.md)</p><p>[Inicio de sesión extendido](extended-logon.md)</p> | |
| Permisos | Se admiten diferentes niveles de permisos para los empleados, como el permiso para crear pedidos y el permiso para editar pedidos. | [Permisos](tasks/create-pos-permission-groups.md) | |
| Administración del tiempo y la asistencia | La asistencia se puede gestionar mediante la función de reloj de tiempo. Los datos de asistencia se pueden procesar en la nómina utilizando la aplicación Dynamics 365 Human Resources. | [Administración de tiempo](retail-time-attendance.md) | |
| Comisión de ventas | Las ventas pueden ser seguidas por el representante de ventas para calcular las comisiones u otros incentivos. | [Comisión](pos-sales-groups-track-commissions.md) | |

## <a name="merchandising"></a>Comercialización

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Administración de selecciones | Los responsables de comercialización pueden clasificar los productos para que estén disponibles para la venta en un canal específico y durante un período específico. | [Varios](assortments.md) | |
| Catálogos | Los responsables de comercialización pueden administrar catálogos para identificar los productos que desea ofrecer con precios específicos del catálogo. | [Catálogos](/dynamicsax-2012/appuser-itpro/about-retail-product-catalogs) | |
| Administración de categorías y productos | En Commerce headquarters, los responsables de comercialización pueden crear productos que tengan variantes, atributos, una unidad de medida, etc. También pueden definir una jerarquía de categorías para organizar productos. | [Producto](retail-hierarchies.md) | |
| Agrupaciones | Los responsables de comercialización pueden agrupar productos para que se vendan como un paquete o kit. | [Kits](/dynamicsax-2012/appuser-itpro/about-setting-up-retail-product-kits) | |
| Códigos de información | Use códigos de información para solicitar al cajero que especifique información en diferentes acciones realizadas en el PDV, como las ventas del artículo, las devoluciones de artículos o la selección de clientes. | [Códigos de información](/dynamicsax-2012/appuser-itpro/about-info-codes-retail) | |
| Artículos vinculados | Use artículos vinculados para mejorar la venta de un producto cuando se agrega un artículo a la transacción. | [Artículos vinculados](/dynamicsax-2012/appuser-itpro/set-up-products-for-cross-selling-and-up-selling) | |
| Garantías | Las garantías extendidas se pueden vender junto con los productos. | [Garantía](extended-warranty.md) | |
| Impresión de etiquetas | Se puede generar etiquetas que contienen información del producto como el número de lote, el número de serie o la fecha de vencimiento. | [Impresión de etiquetas](/dynamicsax-2012/appuser-itpro/create-and-print-labels-overview) | |

## <a name="assisted-selling"></a>Venta asistida

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Exploración de productos | Examine productos por categoría. | [Jerarquía de productos](retail-hierarchies.md) | |
| Búsqueda de productos | Busque productos por nombre y refine las búsquedas utilizando atributos de productos como la marca, el precio y el material. Esta capacidad usa tecnología de Azure Cognitive Search. | [Búsqueda con tecnología de nube](cloud-powered-search-overview.md) | |
| Página Detalles de producto | Las páginas de detalles de productos, de gran riqueza, pueden incluir imágenes, una descripción, atributos de productos y productos recomendados. Las recomendaciones funcionan con tecnología de Recommendations Service. | | |
| Comparación de productos | Compare varios productos y ayude a los clientes a elegir uno y agregarlo a una transacción. | | |
| Pasillo sin fin | Busque fácilmente en el inventario de otras tiendas y cree pedidos. | [Búsqueda de inventario](pos-inventory-lookup-operation.md) | <p>[Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |
| Recomendaciones | Realice ventas adicionales y cruzadas de productos mediante Recommendations Service. Este servicio utiliza tecnología patentada para sugerir recomendaciones, basadas en tendencias de compra y características tales como recién llegados, apariencia similar y superventas. Estas recomendaciones están disponibles en las páginas de detalles del producto, la página **Detalles del cliente** y la página **Transacciones**. | [Recomendaciones](product-recommendations.md) | [Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-recommendations-march-2-2021) |

## <a name="customer-relationship"></a>Relación con el cliente

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Gestión de clientes | Cree, edite y gestione cuentas de clientes. Las cuentas de los clientes se pueden administrar en modo asíncrono para evitar el procesamiento en tiempo real. | [Gestión](customer-mgmt-stores.md) | |
| Atributos de clientes | El marco de atributos del cliente permite capturar datos adicionales del cliente en función de los requisitos empresariales. | [Atributos](dev-itpro/customer-attributes.md) | |
| Página de detalles del cliente | Una página de detalles del cliente, de gran riqueza, proporciona una vista omnicanal de las interacciones del cliente en todos los canales. Estas interacciones incluyen compras, listas de deseos y puntos de fidelidad. | | |
| Búsqueda de clientes con tecnología de nube | Busque clientes por nombre, número de teléfono, dirección de correo electrónico, tarjeta de fidelización, dirección, etc. | [Búsqueda con tecnología de nube](pos-search-improvements.md#customer-search) | |
| Fidelización y recompensas | Los clientes pueden unirse a programas de fidelización y ganar y canjear puntos de fidelidad en todos los canales. | [Fidelidad](set-up-customer-loyalty-program.md) | [Vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE5c2wW) |
| Relación con los clientes | Administre clientes clave usando un libro de clientes, y realice un seguimiento de las actividades y notas en el perfil del cliente. La integración de Dynamics 365 Customer Insights permite que los empleados de la tienda obtengan pistas sobre la siguiente mejor acción posible para cada cliente. | [Relación con los clientes](clienteling-overview.md#activities-and-notes) | [Vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSP) |

## <a name="pricing-and-discounts"></a>Precios y descuentos

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Contratos comerciales | Los administradores de precios pueden usar contratos comerciales para definir precios especiales, basados en acuerdos a largo plazo con clientes específicos. | [Precio](price-management.md)| [Vídeo](https://www.youtube.com/watch?v=r2VD8IxHesM) |
| Acuerdos de venta | Los administradores de precios pueden usar contratos de venta para definir precios basados en contratos en escenarios de comercio de negocio a negocio (B2B). | [Precio](price-management.md) | |
| Ajustes de precio | Los administradores de precios pueden usar la capacidad de ajuste de precios para crear, supervisar y administrar las reducciones de precios para sus productos a lo largo del tiempo. | [Ajustes de precio](price-adjustments-discounts.md) | |
| Descuentos | Los administradores de precios pueden configurar varios tipos de descuentos para ejecutar una variedad de promociones. Estos descuentos incluyen simples descuentos, descuentos por cantidad, descuentos por umbral, descuentos combinados, descuentos basados en forma de pago y descuentos de envíos. | [Descuentos](retail-discounts-overview.md) | |
| Vales | Los administradores de precios pueden configurar códigos de cupones o códigos de barras, vincularlos a descuentos y distribuirlos a los clientes. Los asociados de ventas pueden agregar cupones a las transacciones de ventas o eliminarlos. | [Vales](coupons.md) | |
| Grupos de precios | Los administradores de precios pueden usar la capacidad de grupos de precios para definir precios contextuales, basados en canales, catálogos, afiliaciones o programas de fidelización. | [Precio](price-management.md) | |
| Promociones disponibles | Los asociados de ventas pueden buscar fácilmente las promociones disponibles para productos de la tienda, productos que se agregaron a una transacción, etc. | [Funciones de precios](pos-pricing-functions.md) | |
| Comprobaciones de precio | Los asociados de ventas pueden verificar rápidamente los precios de venta activos de los productos de la tienda. | [Funciones de precios](pos-pricing-functions.md) | |
| Anulaciones de precios | Los asociados de ventas que tienen los permisos necesarios pueden anular los precios calculados o configurados por el sistema. | [Funciones de precios](pos-pricing-functions.md) | |
| Descuentos manuales | Los asociados de ventas que tengan los permisos necesarios pueden aplicar descuentos manuales a transacciones de ventas o líneas de ventas. | [Funciones de precios](pos-pricing-functions.md) | |

## <a name="electronic-payments"></a>Pagos electrónicos

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Crédito y débito | La aplicación Store Commerce admite los principales pagos con tarjeta de crédito y débito a través de Adyen Payment Gateway y el cumplimiento de pedidos a través de PayPal. El SDK de pagos permite conexiones de puerta de enlace externas compatibles con integraciones de proveedores de software independientes (ISV). | <p>[Adyen](dev-itpro/adyen-connector.md?tabs=10-0-23)</p><p>[PayPal](paypal.md)</p><p>[Pagos](payment-methods.md)</p> | <p>[Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-configuration-february-9-2021)</p><p>[Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-omni-channel-payment-overview-processing-february-4-2021)</p> |
| Soporte de la cartera digital | La aplicación Store Commerce admite pagos usando métodos de pago de la cartera digital que no utilizan rangos de números de identificación bancaria (BIN) como lo hacen las tarjetas de crédito y débito tradicionales. Los métodos de pago se pueden asignar a pagos de cartera digital como Adyen. | [Cartera](wallets.md) | |
| Soporte de tarjetas regalo | Número de identificación bancaria, tarjeta regalo de Dynamics 365, soluciones de valor almacenado (SVS) y tarjetas regalo de Givex. Las tarjetas regalo se pueden comprar y canjear en un pedido. | [Tarjetas regalo](dev-itpro/gift-card.md) | [Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/d365-commerce-internal-gift-cards-november-16-2021) |
| Fraud Protection | Dynamics 365 Fraud Protection lo ayuda a prevenir las actividades fraudulentas y detectar lugares donde el fraude podría pasar desapercibido. | [Fraud Protection](dev-itpro/dfp.md) | [Vídeo](https://www.youtube.com/watch?v=j_1nEiq3LfM) |

## <a name="taxes-and-charges"></a>Impuestos y cargos

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Impuestos | La aplicación Store Commerce admite muchos tipos de impuestos indirectos, como impuestos sobre las ventas, impuesto sobre el valor añadido (IVA), impuesto de bienes y servicios (GST), cuotas basadas en unidad y retención de impuestos. | [Impuestos](/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json) | |
| Gastos | Los cargos se pueden configurar en el nivel de la línea, en la cabecera, como cobros automáticos, por canal, etc. | [Gastos](omni-auto-charges.md) | |

## <a name="order-processing-and-fulfillment"></a>Procesamiento y proceso de entrega de pedidos

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Creación de pedido | Se puede crear un pedido para envarlo o para recogerlo en una tienda cercana. Se pueden proporcionar franjas horarias para la recogida. | [Información general](customer-orders-overview.md) | |
| Modificación de pedidos | Un pedido puede ser modificado, devuelto, cancelado, etc. | <p>[Cancelar](customer-orders-overview.md#cancel-a-customer-order)</p><p>[Devoluciones](pos-returns.md)</p> | |
| Búsqueda | Busque y filtre pedidos utilizando información específica del pedido. | [Búsqueda](enhancedorderrecall.md) | |
| Atributos de pedidos | El marco de atributos del pedido permite capturar información adicional relacionada con pedidos en función de los requisitos empresariales. | [Atributos](dev-itpro/order-attributes.md) | |
| Entrega directa | Los artículos se pueden marcar para que los entregue directamente un proveedor a la dirección de un cliente. La entrega directa también se conoce como envío de punto de recogida. | [Entrega directa](/dynamics365/supply-chain/sales-marketing/tasks/ship-orders-direct-deliveries) | |
| Presupuesto | Los empleados de la tienda pueden crear presupuestos para los clientes y pueden especificar un precio especial, descuentos manuales y una fecha de validez del presupuesto. | [Presupuesto](/dynamics365/supply-chain/sales-marketing/tasks/create-edit-sales-quotations) | |
| Proceso de entrega | Las tiendas pueden recoger, empaquetar y enviar pedidos. Se puede agregar un albarán a los paquetes que están listos para el envío. | [Proceso de entrega](order-fulfillment-overview.md) | <p>[Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/unlock-the-power-of-dynamics-365-commerce-supporting-buy-online-pickup-in-store-curbside-with-dynamics-365-commerce-pos-february-3-2021)</p> <p>[Vídeo](https://www.microsoft.com/videoplayer/embed/RE5bRXE)</p>|
| Gestión de pedidos distribuida | La aplicación Store Commerce admite la optimización del proceso de entrega de pedidos inteligente donde las estrategias empresariales se pueden configurar en función de la naturaleza del negocio, el tipo de cliente, el origen de un pedido y el método de entrega de un pedido. | [DOM](dom.md) | [Vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bRYl)|

## <a name="inventory-management"></a>Administración de inventario

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Estrategia de presión | Agilice la distribución del inventario disponible de un centro de distribución a varias tiendas o almacenes. | [Estrategia de presión](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Tránsito directo | Optimice la distribución del inventario en los pedidos de compra entrantes a varias tiendas o almacenes. | [Tránsito directo](tasks/set-up-rules-parameters-cross-docking-buyers-push.md) | [Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021) |
| Inventario de entrada | Reciba inventario de un proveedor a través de un pedido de compra o desde otro almacén a través de un pedido de transferencia. Cree un pedido de compra entrante o una solicitud de pedido de transferencia. | [Entrada](pos-inbound-inventory-operation.md) | <p>[Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p>  <p>[Vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p>|
| Inventario de salida | Envíe el inventario a otro almacén a través de un pedido de transferencia y cree una solicitud de pedido de transferencia saliente. | [Salida](pos-outbound-inventory-operation.md) | <p>[Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p>  <p>[Vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |
| Búsqueda de inventario | Compruebe el inventario disponible de productos en tiendas y almacenes, y compruebe el inventario neto no comprometido (NNC) en fechas futuras. | [Búsqueda de inventario](pos-inventory-lookup-operation.md) | <p>[Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |
| Ajuste de inventario | Ajuste el inventario dentro o fuera del almacén de una tienda para cumplir requisitos empresariales específicos sin usar una venta, una recepción o un recuento. | [Ajuste de inventario](work-with-store-inventory.md) | <p>[Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p>|
| Recuentos de existencias | Cuente el inventario físico y ajuste el inventario de contabilidad del sistema para que coincida. | [Recuento](work-with-store-inventory.md) | <p>[Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)<p> |
| Movimiento de inventario | Mueva el inventario entre ubicaciones de una tienda. | [Movimiento](work-with-store-inventory.md) | <p>[Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-dynamics-365-commerce---store-inventory-may-13-2021)</p> <p>[Vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RE5bMSx)</p> |

## <a name="financials"></a>Operaciones financieras

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Gestión de efectivo | La aplicación Store Commerce admite la gestión de efectivo y otras formas de pago específicas de la tienda. Además, se puede habilitar la conciliación de turnos en la tienda, en las capacidades avanzadas de gestión de efectivo. | [Efectivo](cash-mgmt.md) | |
| Conciliación e informes financieros | Las transacciones en efectivo y transaccionales de una tienda se registran en Commerce headquarters a través de los procesos de publicación de instrucciones. | [Informes](retail-statements.md) | |
| Transacciones de ingresos y gastos | Procese transacciones de gastos menores en la tienda y registre los ingresos que no se obtienen de la manera tradicional, como el dinero perdido y encontrado, la participación en los ingresos de una cafetería en su vestíbulo y los servicios de limpieza de alfombras. | [Informes](retail-statements.md) | |
| Pagos de facturas | Capture pagos de facturas. | [Factura](payinvoice.md) | |

## <a name="employee-productivity"></a>Productividad del empleado

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Administración de tareas | Cree listas de tareas y tareas, y asígnelas a tiendas y empleados. Realice un seguimiento del estado de las tareas en las tiendas. Se proporciona una perfecta integración con Microsoft Teams. | <p>[Administración de tareas](task-mgmt-overview.md)</p><p>[Microsoft Teams](commerce-teams-integration.md)</p> | [Vídeo](https://www.youtube.com/watch?v=ES1whB4C2lU) |

## <a name="hardware-and-peripherals"></a>Hardware y periféricos

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Conectar periféricos | Conecte periféricos como impresoras, cajas registradoras, escáneres o dispositivos de pago a un terminal del PDV. | [Periféricos](retail-peripherals-overview.md) ||
| Compartir periféricos | Las impresoras de recibos, las cajas registradoras y los dispositivos de pago se pueden compartir entre muchos terminales conectándolos a una estación de hardware compartida. | <p>[Estación de hardware](retail-peripherals-overview.md) ||
| El PDV y el simulador de periféricos | El simulador de periféricos admite la realización de pruebas de escenarios que suelen requerir dispositivos periféricos del PDV físicos. También incluyen un simulador del PDV que se puede usar para probar la compatibilidad de dispositivos periféricos físicos sin requerir la implementación del cliente del PDV. | [Simulador](dev-itpro/retail-peripheral-simulator.md) | |

## <a name="receipts"></a>Recepciones

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Imprimir recibos | Los recibos de varios tipos, como recibos de ventas, recibos de tarjetas de crédito, recibos de regalos y facturas, se pueden imprimir de forma predeterminada o después de la confirmación del cajero al finalizar la compra. También se pueden volver a imprimir desde el diario. | [Impresión](receipt-templates-printing.md) | |
| Enviar recibos por correo electrónico | Los recibos se pueden enviar por correo electrónico desde el PDV después de que finalice la compra. | [Correo](email-receipts.md) | |
| Diseñar recibos | Los recibos de las tiendas se pueden personalizar para que muestren datos y diseños apropiados para el minorista y el tipo de transacción. Los recibos también se pueden ampliar para que muestren los datos personalizados que requiere el minorista. | [Diseño](receipt-templates-printing.md) | |

## <a name="offline-support"></a>Soporte sin conexión

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Modo sin conexión perfecto | El modo sin conexión perfecto le permite continuar realizando transacciones incluso cuando la conectividad a Internet es limitada o no está disponible. La exclusión de datos lo ayuda a reducir el tamaño de los datos de las bases de datos sin conexión y maximizar el rendimiento. | [Sin conexión](pos-operations.md) | |
| Conmutación basada en el rendimiento | Cambie al modo fuera de línea cuando se detecte una degradación del rendimiento. | [Sin conexión](dev-itpro/implementation-considerations-offline.md) | [Vídeo](https://youtu.be/sQU-2pgHToI) |
| Panel de información sin conexión | El panel de información **Estado sin conexión** muestra el estado sin conexión, los errores y los detalles de los datos de cada dispositivo. Por lo tanto, es fácil administrar el estado de muchos dispositivos. | [Sin conexión](dev-itpro/implementation-considerations-offline.md) | [Vídeo](https://youtu.be/sQU-2pgHToI)|

## <a name="extensibility"></a>Extensibilidad

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Commerce Headquarters | Las soluciones de Commerce headquarters se pueden personalizar agregando o modificando procesos de negocio. Commerce headquarters admite el uso de metadatos y un modelo de extensión basado en código para agregar funcionalidad personalizada. Se puede integrar fácilmente en soluciones externas. | [Información general](dev-itpro/extend-customer-cdx-package.md) | [Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-unlock-the-power-of-dynamics-365-commerce-commerce-extensibility-overview-february-23-2021) |
| Commerce sin periféricos | El marco de API omnicanal ampliable se puede utilizar para personalizar o agregar lógica de negocios. Las API que tienen controladores de solicitudes y patrones de extensión previos y posteriores a la activación. | [CSU](dev-itpro/retail-server-customer-consumer-api.md) | [Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| SKD de Commerce | El SDK de Commerce incluye el código, las muestras de código, las plantillas y las herramientas necesarias para ampliar o personalizar las funcionalidad de Dynamics 365 Commerce. El SDK se publica en diferentes repositorios (repos) en GitHub, según los componentes de la extensión. | [SDK](dev-itpro/retail-sdk/sdk-github.md) | [Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |
| Punto de venta | La aplicación Store Commerce se puede ampliar de forma independiente mediante la función de extensión del PDV del SDK de Commerce. El marco admite la personalización de la experiencia del usuario (UX), los flujos de trabajo y la lógica de negocio. | [PDV](dev-itpro/pos-extension/pos-extension-overview.md) | [Charla técnica](https://community.dynamics.com/365/dynamics-365-fasttrack/b/techtalks/posts/techtalk-series-commerce-extensions) |

## <a name="reporting"></a>Notificación

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Informes de ventas | Los informes de ventas por personal, registro, tipo de pago, devoluciones, producto, etc., están disponibles para los gerentes de la tienda. Los gerentes pueden ver estos informes y usarlos para asignar comisiones e identificar tendencias de productos. | | |

## <a name="diagnostics"></a>Diagnóstico

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Operational Insights | Las métricas de rendimiento y confiabilidad del estado del servicio seleccionadas por la tienda están disponibles en la suscripción de Application Insights del cliente. Dispone de funcionalidades de alerta y supervisión avanzadas. | | |
| Comprobación de estado | La disponibilidad de los periféricos que están conectados a un PDV se puede verificar ejecutando la operación de comprobación del estado. Los problemas de periféricos individuales pueden corregirse y verificarse. | [Comprobación de estado](pos-healthcheck.md) | [Vídeo](https://www.youtube.com/watch?v=RfPDNmnqYvY) |

## <a name="globalization"></a>Globalización

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Soporte multimercado | Las funciones específicas del mercado, como la integración fiscal, el GST, la facturación avanzada y los prepagos, se admiten de forma inmediata. Esta capacidad cubre varios mercados de Europa, las Américas, Rusia, Asia, Arabia Saudí, etc. | [Globalización](localizations/fiscal-integration-for-retail-channel.md) | |

## <a name="compliance"></a>Conformidad

| Capacidad | Description | Documentación | Contenido suplementario |
|---|---|---|---|
| Estándares de Microsoft | La aplicación Store Commerce cumple los estándares de Microsoft en materia de seguridad, privacidad, accesibilidad, el Reglamento general de protección de datos (GDPR), el límite de datos de la Unión Europea (UE), etc. | | |

