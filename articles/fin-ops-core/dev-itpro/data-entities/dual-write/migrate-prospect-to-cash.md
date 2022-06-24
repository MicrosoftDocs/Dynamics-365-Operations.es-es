---
title: Migrar datos de cliente potencial a efectivo desde el integrador de datos a doble escritura
description: Este artículo describe cómo migrar un cliente potencial a efectivo desde Integrador de datos a escritura dual.
author: RamaKrishnamoorthy
ms.date: 02/01/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-26
ms.openlocfilehash: 8e5c11e535bd61e9955a4abf1491e88991ee40f1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894277"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Migrar datos de cliente potencial a efectivo desde el integrador de datos a doble escritura

[!include [banner](../../includes/banner.md)]

La solución Prospect to cash disponible para Data Integrator no es compatible con escritura dual. La razón de esto es el índice msdynce_AccountNumber en la tabla de cuentas que vino como parte de la solución Prospect to cash. Si este índice existe, no puede crear el mismo número de cuenta de cliente en dos entidades legales diferentes. Puede elegir comenzar de cero con doble escritura migrando los datos de Prospect to cash de Data Integrator a dual-write o puede instalar la última versión "dorman" de la solución Prospect to cash. Este artículo cubre ambos enfoques.

## <a name="install-the-last-dorman-version-of-the-data-integrator-prospect-to-cash-solution"></a>Instale la última versión "dorman" de Data Integrator Prospect to cash solution

**Versión P2C 15.0.0.2** se considera la última versión "dorman" del integrador de datos Prospect to cash solution. Puede descargarlo desde [FastTrack for Dynamics 365](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/P2C).

Necesita instalarlo manualmente. Después de la instalación, todo permanece exactamente igual, excepto que se elimina el índice msdynce_AccountNumber.

## <a name="steps-to-migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Pasos para migrar datos de cliente potencial a efectivo desde el integrador de datos a doble escritura

Para migrar su cliente potencial a efectivo desde Integrador de datos a escritura dual, siga estos pasos.

1. Ejecute los trabajos de integrador de datos de cliente potencial a efectivo para realizar una sincronización completa final. De esta forma, se asegura de que ambos sistemas (aplicaciones de Finance and Operations y de interacción con el cliente) tienen todos los datos.
2. Para ayudar a evitar una posible pérdida de datos, exporte el cliente potencial a datos de caja desde Microsoft Dynamics 365 Sales a un archivo de Excel o un archivo de valores separados por comas (CSV). Exportar datos de las siguientes entidades:

    - [Cuenta](#account-table)
    - [Contacto](#contact-table)
    - [Factura](#invoice-table)
    - Productos de facturación
    - [Pedido](#order-table)
    - [Pedir productos](#order-products-table)
    - [Productos](#products-table)
    - [Presupuesto](#quote-and-quote-product-tables)
    - [Cotizar productos](#quote-and-quote-product-tables)

3. Desinstale la solución cliente potencial a efectivo del entorno de Sales. Este paso elimina las columnas y los datos correspondientes que introdujo la solución Cliente potencial a efectivo.
4. Instale la solución de escritura dual.
5. Cree una conexión de escritura dual entre la aplicación Finance and Operations y la aplicación de interacción con el cliente para una o más entidades legales.
6. Habilite mapas de tabla de escritura dual y ejecute la sincronización inicial para los datos de referencia necesarios. (Para más información, ver [Consideraciones para la sincronización inicial](initial-sync-guidance.md).) Ejemplos de datos requeridos incluyen grupos de clientes, condiciones de pago y programas de pago. No habilite los mapas de escritura dual para las tablas que requieren inicialización, como las tablas de cuenta, cotización, línea de cotización, pedido y línea de pedido.
7. En la aplicación de interacción con el cliente, vaya a **Ajustes avanzados \> Ajustes del sistema \> Gestión de datos \> Reglas de detección duplicadas** y deshabilite todas las reglas.
8. Inicialice las tablas que se enumeran en el paso 2. Para obtener instrucciones, consulte las secciones restantes de este artículo.
9. Abra la aplicación Finance and Operations y habilite los mapas de tabla, como los mapas de tabla de cuenta, cotización, línea de cotización, pedido y línea de pedido. A continuación ejecute la sincronización inicial. (Para más información, ver [Consideraciones para la sincronización inicial](initial-sync-guidance.md).) Este proceso sincronizará información adicional de la aplicación Finance and Operations, como el estado de procesamiento, las direcciones de envío y facturación, los sitios y los almacenes.

## <a name="account-table"></a>Tabla Cuenta

1. En la columna **Empresa**, ingrese el nombre de la compañía, como **USMF**.
2. En la columna **Tipo de relación**, ingrese **Cliente** como valor estático. Es posible que no desee clasificar todos los registros de cuenta como clientes en su lógica empresarial.
3. En la columna **ID de grupo de clientes**, ingrese el número de grupo de clientes de la aplicación Finance and Operations. El valor predeterminado de la solución Cliente potencial a efectivo es **10**.
4. Si está utilizando la solución Cliente potencial a efectivo sin ninguna personalización de **Número de cuenta**, ingrese un valor de **Número de cuenta** en la columna **Número de parte**. Si hay personalizaciones y no conoce el número del grupo, extraiga esta información de la aplicación Finance and Operations.

## <a name="contact-table"></a>Mesa de contacto

1. En la columna **Empresa**, ingrese el nombre de la compañía, como **USMF**.
2. Establezca las siguientes columnas, según el valor **IsActiveCustomer** en el archivo CSV:

    - Si **IsActiveCustomer** se establece en **Sí** en el archivo CSV, configure la columna **Vendible** en **Sí**. En la columna **ID de grupo de clientes**, ingrese el número de grupo de clientes de la aplicación Finance and Operations. El valor predeterminado de la solución Cliente potencial a efectivo es **10**.
    - Si **IsActiveCustomer** se establece en **No** en el archivo CSV, configure la columna **Vendible** en **No** y configure la columna **Contacto para** en **Cliente**.

3. Si está utilizando la solución Cliente potencial a efectivo sin ninguna personalización de **Número de contacto**, establezca las siguientes columnas:

    - Migre el número de contacto del archivo CSV (**msdynce\_contactnumber**) al número de contacto en la tabla **Contacto** (**msdyn\_contactnumber**).
    - Utilice valores de la tabla **Número de contacto** en la columna **Número de parte**.
    - Utilice valores de la tabla **Número de contacto** en la columna **Número de cuenta/Id. de la persona de contacto**.

## <a name="invoice-table"></a>Tabla de facturación

Ya que los datos de la tabla de **Facturación** están diseñados para fluir en una dirección, desde la aplicación Finance and Operations a la aplicación de interacción con el cliente, no se requiere inicialización. Ejecute la sincronización inicial para migrar todos los datos necesarios de la aplicación Finance and Operations a la aplicación de interacción con el cliente. Para más información, ver [Consideraciones para la sincronización inicial](initial-sync-guidance.md).

## <a name="order-table"></a>Tabla Pedidos

1. En la columna **Empresa**, ingrese el nombre de la compañía, como **USMF**.
2. Copie el valor de la columna **Solicitar ID** en el archivo CSV a la columna **Número de pedidos de ventas**.
3. Copie el valor de la columna **Cliente** en el archivo CSV a la columna **Número de factura del cliente**.
4. Copie el valor de la columna **Enviar a país/región** en el archivo CSV a la columna **Enviar a país/región**. Ejemplos de este valor incluyen **EE. UU.** y **Estados Unidos**.
5. Seleccione la columna **Fecha de recepción solicitada**. Si no está usando una fecha de recibo, use las columnas **Fecha de entrega requerida**, **Fecha de cumplimiento** y **Fecha de envío** en el archivo CSV. Un ejemplo de este valor es **2020-03-27T00:00:00Z**.
6. Establezca la columna **Idioma**. Un ejemplo de este valor es **en-us**.
7. Seleccione la columna **Tipo de orden** usando la columna **Basado en artículos**.

## <a name="order-products-table"></a>Tabla Productos de pedido

- En la columna **Empresa**, ingrese el nombre de la compañía, como **USMF**.

## <a name="products-table"></a>Tabla Productos

Ya que los datos de la tabla **Productos** están diseñados para fluir en una dirección, desde la aplicación Finance and Operations a la aplicación de interacción con el cliente, no se requiere inicialización. Ejecute la sincronización inicial para migrar todos los datos necesarios de la aplicación Finance and Operations a la aplicación de interacción con el cliente. Para más información, ver [Consideraciones para la sincronización inicial](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Tablas de cotización y producto de cotización

Para la tabla **Cotización**, siga las instrucciones de la sección anterior de este artículo, [Tabla de pedidos](#order-table). Para la tabla **Producto de cotización**, siga las instrucciones de la sección anterior de este tema, [Tabla de productos de pedido](#order-products-table).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
