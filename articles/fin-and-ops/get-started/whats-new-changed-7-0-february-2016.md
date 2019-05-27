---
title: Novedades o cambios en Dynamics AX 7.0 (febrero de 2016)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics AX 7.0. Esta versión contiene características tanto de plataforma como de aplicación y se publicó en febrero de 2016.
author: sericks007
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 91243
ms.assetid: 515bc6e7-a85d-4995-95c6-6cab6c8aa0f9
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cdd8acea22fb3298d1d0e7ccce0ca42c1427fe80
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561819"
---
# <a name="whats-new-or-changed-in-dynamics-ax-70-february-2016"></a>Novedades o cambios en Dynamics AX 7.0 (febrero de 2016)

[!include [banner](../includes/banner.md)]

Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics AX 7.0. Esta versión contiene características tanto de plataforma como de aplicación y se publicó en febrero de 2016.

## <a name="cost-management"></a>Gestión de costes

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Obtenga una visión general rápida del saldo de inventario, el saldo de inventario del trabajo en curso y cuál ha sido el flujo de entrada y salida del inventario durante el ejercicio seleccionado.</td>
<td>No aplicable</td>
<td>El espacio de trabajo <strong>Administración de costes</strong> contiene una sección donde se presenta el extracto de inventario o el extracto de inventario del trabajo en curso para el período fiscal seleccionado. El extracto se basa en una caché de un conjunto de datos que, de forma predeterminada, se actualiza cada 24 horas. La caché del conjunto de datos se puede configurar para que los usuarios puedan actualizarla manualmente para informes en tiempo real. La tarjeta de <strong>Estado de actualización de datos</strong> del espacio de trabajo <strong>Administración de costes</strong> muestra cuándo se actualizó la caché por última vez.</td>
<td>A los controladores de costes les interesa saber si el inventario o el saldo del extracto del inventario del trabajo en curso aumenta o disminuye con el tiempo. Al clasificar eventos operativos en el extracto, el controlador de costes puede obtener una visión general de cómo fluye el inventario. Si el inventario o el inventario del trabajo en curso se evalúa por costes estándar, también se puede ver la desviación general registrada.</td>
</tr>
<tr>
<td>Utilice el módulo <strong>Gestión de costes</strong>.</td>
<td>No aplicable</td>
<td>La gestión de costes se introduce como área de dominio. La configuración y la información relativas a los costes estaban dispersas por Administración de inventario, Control de producción y Proveedores.</td>
<td>Dado que todas las tareas relacionadas con la gestión de costes se centralizan en un módulo, será más fácil que los controladores de costes mantengan el sistema.</td>
</tr>
<tr>
<td>Se han actualizado los tipos de registro relacionados con la contabilidad de inventario y la contabilidad de producción.</td>
<td>Las etiquetas en los formularios <strong>Registro de inventario</strong>, <strong>Recurso</strong>, <strong>Grupo de recursos</strong> y <strong>Grupo de producción</strong>no se alinean siempre con las etiquetas <strong>Tipo de registro contable</strong> que se usan realmente. No es fácil comprender la terminología que se usa en las etiquetas.</td>
<td>Las etiquetas se han actualizado de modo que las etiquetas en las páginas <strong>Registro de inventario</strong>, <strong>Recurso</strong>, <strong>Grupo de recursos</strong> y <strong>Grupo de producción</strong>coinciden con las etiquetas <strong>Tipo de registro contable</strong> reales. También se ha cambiado el nombre de todas las etiquetas, de modo que las etiquetas coincidan con los eventos operativos. Tenga en cuenta que la lógica de registro en sí no se ha cambiado.</td>
<td>Resulta más fácil configurar el sistema, ya que las nuevas etiquetas están relacionadas con eventos operativos que usan este tipo de registro.</td>
</tr>
<tr>
<td>Importe o exporte el precio de compra, el coste o el precio de venta desde Microsoft Excel a o desde una versión de gestión de costes.</td>
<td>No es posible importar correctamente precios o costes a una versión de gestión de costes, ya que el modelo de datos requiere una identificación InventDim.</td>
<td>La introducción de entidades de datos permite implementar una función de importación o exportación. Esta función permite a los usuarios importar o exportar precios o costes en una versión de gestión de costes.
<ul>
<li>Importe una lista completa de precios de compra del año siguiente transferida desde el departamento de compras.</li>
<li>Transfiera los costes y los precios de ventas estándar desde las centrales a una o más compañías de ventas en una operación.</li>
</ul></td>
<td>Puede ahorrar a los controladores de costes un tiempo significativo en el mantenimiento del sistema, especialmente cuando deben mantener costes predeterminados para el ejercicio siguiente.</td>
</tr>
<tr>
<td>Obtenga una visión general rápida del saldo de inventario y el coste unitario medio de un objeto de coste.</td>
<td>El usuario debe abrir el formulario disponible y seleccionar las dimensiones de inventario que reflejan el objeto de coste. Por lo tanto, el usuario debe saber qué dimensiones de inventario se han marcado para el inventario financiero para el producto específico.</td>
<td>Hay una nueva página <strong>Objeto de coste</strong>. De forma predeterminada, esta página muestra todos los objetos de coste relacionados con el producto. La página muestra la cantidad de inventario, el valor y el coste unitario medio actuales por objeto de coste.</td>
<td>Acaba con parte de la complejidad y facilita la tarea del controlador de costes.</td>
</tr>
<tr>
<td>Utilice la nueva página <strong>Entradas de costes</strong> durante el control de inventario.</td>
<td>Puede ser complicado realizar un control de inventario en transacciones de inventario registradas y liquidaciones relacionadas, ya que las mismas transacciones pueden ser físicas o financieras.</td>
<td>La página <strong>Entradas de costes</strong> ofrece una nueva forma de ver transacciones de inventario.
<ul>
<li>Las transacciones se ven en orden cronológico.</li>
<li>Solo se incluyen transacciones que contribuyen a los costes.</li>
<li>No hay noción de costes físicos o de coste financiero.</li>
<li>No hay noción de cantidad física o de cantidad financiera.</li>
<li>Los costes se agregan de modo incremental.</li>
</ul></td>
<td>Puede ahorrar a los controladores de coste un tiempo significativo cuando deben realizar un control de inventario en el nivel de la transacción.</td>
</tr>
<tr>
<td>Use el nuevo cuadro de diálogo <strong>Informe de trabajo en curso de producción</strong> para ver una vista resumida de los costes acumulados para un producto específico.</td>
<td>No aplicable</td>
<td>El informe de trabajo en proceso muestra saldos de trabajos en proceso resumidos del pedido de producción específico, agrupados en clasificaciones de costes adecuadas. Un gráfico muestra, en orden cronológico, el efecto de registros operativos en el saldo del trabajo en curso.</td>
<td>Puede ahorrar a los controladores de costes un tiempo significativo cuando necesiten saber cuál es el saldo actual del trabajo en curso en un pedido de producción específico, o cuánto material se ha consumido en el pedido.</td>
</tr>
<tr>
<td>Use la función Ver comparación del coste nueva en los pedidos de producción. La función facilita la comparación de costes relacionados con un pedido de producción.</td>
<td>El usuario puede comparar solo costes estimados y costes realizados. La comparación se pueden realizar en el nivel inferior.</td>
<td>La función de comparación de costes permite a los controladores de costes comparar los datos siguientes:
<ul>
<li>Coste activo frente a coste estimado = Desviación de la planificación</li>
<li>Coste estimado frente a coste realizado = Desviación de la producción</li>
<li>Desviación de la planificación + Desviación de la producción = Desviación total</li>
</ul>
Esta función es independiente de los métodos de costes asignados al artículo producido. De forma predeterminada, un gráfico muestra la comparación de costes por tipo de grupo de costes. El gráfico permite a los usuarios explorar en niveles más detallados.</td>
<td>Los controladores de costes o los gerentes de producción pueden analizar de dónde proceden las desviaciones de producción y qué las causa.</td>
</tr>
</tbody>
</table>

## <a name="developer"></a>Desarrollador

| ¿Qué se puede hacer? | Dynamics AX 2012 | Dynamics AX 7.0 | ¿Por qué esto es importante? |
|------------------|------------------|-----------------|------------------------|
| Cree soluciones basadas en web en la nube accesibles en muchos dispositivos. | No disponible | La versión actual de Dynamics AX se basa en un nuevo cliente basado en web y en un marco de cliente. | Puede ofrecer soluciones de nueva generación a sus usuarios finales. |
| Use Microsoft Visual Studio para desarrollar sus soluciones. | Microsoft MorphX es el entorno de desarrollo principal, si bien se produce algún desarrollo en Visual Studio. | Visual Studio es el único entorno de desarrollo. | Mantiene la familiarización con los conceptos de Dynamics AX 2012 y los adapta perfectamente al marco y los paradigmas de Visual Studio. Permite una interoperabilidad estándar con otros lenguajes y proyectos de .NET. |
| Compile el lenguaje CIL (Common Intermediate Language) para todas las funciones. | X++ se compila en código de programa. | El nuevo compilador X++ genera CIL para todas las funciones. CIL es el mismo lenguaje intermedio que usan otros lenguajes basados en .NET. | CIL es más rápido, puede hacer referencia eficientemente a las clases en bibliotecas de vínculos dinámicos (DLL) gestionadas y puede ejecutarse con muchas herramientas de utilidades .NET. |
| Incruste informes de inteligencia empresarial (BI) y visualizaciones en el cliente de Microsoft Dynamics AX. | No disponible | Cree visualizaciones muy intuitivas y fluidas. | Proporcione información para la toma de decisiones basada en inteligencia empresarial. |
| Intégrese con Microsoft Office. | No disponible | Las nuevas capacidades incluyen la aplicación de conector de datos de Excel, la página **Diseñador de libros**, Exportar API y Gestión de documentos. | Puede crear soluciones de productividad de sus usuarios finales. |
| Automatice la creación, las pruebas y la implementación. | Disponible parcialmente | Implemente la topología de desarrollador mediante Developer y Build VM. Configurar automáticamente Build VM para detectar, crear módulos desde Visual Studio Online (VSO) y ejecutar pruebas. También se admiten referencias y compilaciones de módulo C\# y X++. | Aumenta la productividad del desarrollador reduciendo el coste y el esfuerzo asociado a las pruebas y validaciones. |
| Personalice con superposiciones y extensiones. | No hay extensiones disponibles. | La versión actual de Dynamics AX tiene un nuevo modelo de personalización. | Puede personalizar código de origen y metadatos de elementos de modelo proporcionados por Microsoft o terceros. |
| Genere nuevos controles y elementos de interfaz de usuario mediante X++ y un moderno marco web. | Los controles personalizados se basan en marcos externos como Microsoft ActiveX y Windows Presentation Foundation (WPF). | Resulta más fácil crear controles en la versión actual. El marco X++ se puede usar para dirigir el comportamiento de la aplicación y la lógica empresarial, y un cliente basado en HTML/JavaScript permite utilizar modernas visualizaciones. | Sus controles se pueden diseñar para parecer y para comportarse como los controles integrados de Dynamics AX. |
| Evalúe y adapte el rendimiento mediante nuevas herramientas. | PerfSDK, Data Expansion Toolkit, la aplicación Trace Parser WEb y PerfTimer no están disponibles. | PerfSDK, Data Expansion Toolkit, la aplicación Trace Parser Web y PerfTimer son nuevos. | El kit de desarrollo de software (SDK) le permite probar y validar el rendimiento de todos los procesos empresariales críticos en una prueba de un usuario y, si procede, de varios usuarios. El conjunto de herramientas Data Expansion le permite ampliar correctamente todas las pruebas de rendimiento que deben tener datos maestros y datos transaccionales correctamente expandidos. Trace Parser le permite validar una prueba de rendimiento de un solo usuario o varios usuarios. PerfTimer le permite ver si hay alguna pregunta o llamada de método específica que esté causando un problema de rendimiento. Por lo tanto, no tiene que hacer un seguimiento y analizar todo detalladamente. |
| Muestre una vista actualizable con OData. | No disponible | La versión actual de Dynamics AX presenta un terminal de servicio OData público que permite acceder a los datos de Dynamics AX de manera coherente a través de una amplia gama de clientes. | Sus soluciones pueden interactuar con los servicios RESTful, compartir datos de manera detectable y habilitar una amplia integración mediante el protocolo de pila HTTP. |
| Aproveche Business Connector para crear lógica empresarial y admitir escenarios de integración. | Business Connector está disponible para llamar al código X++ desde código administrado. Se recomienda usar Business Connector solo para crear lógica empresarial en C\#, no para los escenarios de integración. | Business connector ya no es compatible. El requisito de creación proviene del hecho de que X++ está compilado en código administrado. Por lo tanto, es más fácil interoperar. Los escenarios de integración se cumplen con OData. | No puede usar Business Connector hacia delante. |
| Elija la escala (es decir, el número de decimales) en los campos de base de datos reales y tipos de datos ampliados. | La escala 16 es la escala predeterminada y no la puede cambiar el desarrollador. | Los tipos de datos ampliados y los campos tienen ahora una propiedad de escala aplicable al campo individuales y al tipo de datos ampliados. El valor predeterminado es 6, no 16. | El rendimiento con tablas NCCI (compatibilidad dentro de la memoria en SQL) es más rápido por pedidos de magnitud cuando se utiliza la escala más pequeña. Cambie la escala según exija el uso de campos individuales. |

## <a name="financial-management"></a>Administración financiera

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Exporte las estructuras contables a Microsoft Excel.</td>
<td>No disponible</td>
<td>Ahora puede seleccionar una estructura contable y exportarla a Excel.</td>
<td>Muchos clientes han solicitado la capacidad de exportar estructuras contables a Excel para un filtrado más fácil.</td>
</tr>
<tr>
<td>Vea los libros mayores y las estructuras de reglas avanzadas asociados con una estructura contable en una sola página.</td>
<td> El usuario debe desplazarse a varios formularios para ver el libro mayor y la estructura contable utilizados.</td>
<td>Se han agregado cuadros informativos a la página de la estructura contable.</td>
<td>Resulta más fácil acceder a información importante cuando se definen y editan las estructuras contables.</td>
</tr>
<tr>
<td>Vea libros mayores asociados con un plan contable en una sola página.</td>
<td>El usuario debe desplazarse a cada empresa y abrir el formulario del libro mayor para ver el plan de cuentas asignado al libro mayor.</td>
<td>Se han agregado cuadros informativos a la página <strong>Plan de cuentas</strong>.</td>
<td> Resulta más fácil acceder a información importante cuando se define y asigna un plan de cuentas.</td>
</tr>
<tr>
<td>Vea ajustes de hoja de cierre y transacciones de cierre en columnas aparte en la página de lista <strong>Saldo de comprobación</strong>.</td>
<td>El usuario ve ambos tipos de transacciones en una columna.</td>
<td>Se ha agregado un parámetro adicional a la página de lista <strong>Saldo de comprobación</strong>.</td>
<td>Permite analizar de manera más concisa los datos y también es necesario para emitir informes reglamentarios en algunos países o regiones.</td>
</tr>
<tr>
<td>Utilice la nueva página <strong>Diarios generales globales</strong>.</td>
<td>No disponible</td>
<td>Nueva página <strong>Diarios generales globales</strong> para especificar diarios generales. Se agregan privilegios para esta página en el rol <strong>Contable</strong>.</td>
<td>Hace posible que un contable de servicios compartidos introduzca diarios generales en empresas sin tener que salir del formulario ni cambiar el contexto de la empresa.</td>
</tr> 
<tr>
<td>Utilice la nueva página <strong>Explorador de origen de contabilidad</strong>.</td>
<td>Disponible desde Dynamics AX 2012 R3 CU10.</td>
<td>Nueva página <strong>Explorador de origen de contabilidad</strong> y acciones para navegar allí desde la página de lista <strong>Saldo de comprobación</strong> y la página <strong>Transacciones de asiento</strong>.</td>
<td>Hace posible ver la información más detallada sobre el origen de un saldo de comprobación o un asiento contable en la contabilidad general, o para análisis ad hoc.</td>
</tr>
<tr>
<td>Agregue capas de registro adicionales.</td>
<td>La adición de capas de registro adicionales fue una experiencia de desarrollador.</td>
<td>Ahora hay diez capas de registro disponibles.</td>
<td>La mayoría de los clientes agregan capas de registro adicionales.</td>
</tr>
<tr>
<td>Utilice la opción Asiento relacionado.</td>
<td>No disponible</td>
<td>La opción Asiento relacionado está disponible para que los usuarios vean el asiento en la empresa de contrapartida al registrar transacciones de empresas vinculadas. De los asientos relacionados, los usuarios pueden hacer clic en los detalles y saltar rápidamente el asiento de compensación de la empresa.</td>
<td>Al registrar transacciones entre empresas vinculadas, los usuarios no tenían ninguna visibilidad o seguimiento para el asiento que se registró en la empresa de contrapartida.</td>
</tr>
<tr>
<td>Cierre del período financiero masivo</td>
<td>No disponible</td>
<td>Los usuarios pueden actualizar el acceso al módulo y cambiar el estado del período para varias empresas al mismo tiempo.</td>
<td>Antes de la característica, los usuarios debían cambiar en qué empresa habían iniciado sesión, navegar hasta el formulario de calendario contable y actualizar manualmente el acceso al módulo y el estado del período.</td>
</tr>
<tr>
<td>Tenga tipos de cambio con tecnología Oanda.</td>
<td>La configuración del proveedor de tipos de cambio para importar tipos de Oanda fue una experiencia de desarrollador.</td>
<td>Si los usuarios tienen una clave para Oanda, pueden especificarla al configurar el proveedor de tipos de cambio.</td>
<td>Los usuarios pueden beneficiarse de la funcionalidad lista para usar teniendo tipos de cambio con tecnología Oanda importados de modo programado.</td>
</tr>
<tr>
<td>Filtre informes financieros (Management Reporter) basados en dimensiones, atributos, fechas y escenarios.</td>
<td> Todos los informes de filtrado de Management Reporter se gestionan a través del diseño del informe. Por ejemplo, si un usuario que tenga privilegios de visualización desea ver un informe para una fecha diferente, un diseñador de informe debe realizar la modificación.</td>
<td>Se han agregado opciones de informe de modo que se puedan aplicar distintos filtros cuando un usuario está viendo un informe. Después se genera un nuevo informe en función de esos filtros.</td>
<td>Los consumidores de informes financieros pueden aplicar distintos filtros para dimensiones, fechas, atributos y escenarios sin requerir actualizaciones para informar sobre diseños.</td>
</tr>
<tr>
<td>Vea informes financieros (Management Reporter) dentro del cliente de Microsoft Dynamics AX.</td>
<td>Se usó un cliente web aparte para ver informes de Management Reporter.</td>
<td>En el cliente de Dynamics AX se puede acceder a todos los informes financieros. El usuario selecciona un informe para verlo y el informe se muestra en el cliente.</td>
<td>Ahora puede ver informes financieros sin tener que acceder a un cliente o una aplicación diferente.</td>
</tr>
<tr>
<td>Imprima informes financieros (Management Reporter) desde el cliente de Microsoft Dynamics AX.</td>
<td>La impresión de un informe utilizaría las opciones de impresión del explorador para impresión y solo imprime lo que el usuario puede ver en la pantalla.</td>
<td>El usuario puede elegir la configuración de página y nivel de detalle de un informe mediante la opción de impresión en el informe financiero en el cliente de Dynamics AX.</td>
<td>Los informes impresos se imprimen como los usuario esperan en lugar de imprimir una página web.</td>
</tr><tr>
<td>Analice datos financieros mediante el contenido de supervisión del rendimiento financiero para Power BI.</td>
<td>No disponible</td>
<td>En PowerBI.com, seleccione <strong>Obtener datos</strong> y, a continuación, seleccione el paquete de contenido <strong>Dynamics AX – Rendimiento financiero</strong>. Especifique la dirección URL del terminal de Dynamics AX para ver sus datos reflejados en el panel de información.</td>
<td>En de tres a cuatro clics, las organizaciones pueden implementar un panel de información de Power BI con datos financieros importantes. La organización puede personalizar el contenido.</td>
</tr>
<tr>
<td>Haga un seguimiento de los procesos de cierre del período financiero.</td>
<td>No disponible</td>
<td>Se pueden crear plantillas y programaciones de cierre mediante la configuración del cierre del período financiero. Use el espacio de trabajo <strong>Cierre del periodo financiero</strong> para realizar un seguimiento del progreso de las programaciones de cierre en varias empresas.</td>
<td>Este espacio de trabajo acaba con los sistemas manuales para definir, programar y comunicar actividades de cierre. Por lo tanto, se reduce el número de días para cerrar.</td>
</tr>
<tr>
<td>Supervise los datos presupuestarios frente a los reales y cree previsiones de contabilidad mediante el espacio de trabajo <strong>Presupuestos y previsiones contables</strong> y formularios de consulta adicionales.</td>
<td>No disponible</td>
<td> Al espacio de trabajo se puede acceder mediante el panel de información de Dynamics AX. Incluye vínculos a varias nuevas páginas de consulta: <strong>Resumen de datos reales frente a presupuestados</strong>, <strong>Resumen de estadísticas de control presupuestario</strong>, <strong>Entradas de registro presupuestario</strong> y <strong>Planes presupuestarios</strong>.</td>
<td>Las nuevas páginas de consulta permiten acceder fácilmente a la información presupuestaria. El espacio de trabajo combina todas las tareas de mantenimiento y supervisión del presupuesto en un lugar donde resulta fácil de usar para los administradores de presupuestos o los gerentes de contabilidad.</td>
</tr>
<tr>
<td>Cree diseños para planes y previsiones de presupuesto.</td>
<td>El documento <strong>Plan presupuestario</strong> se ve como una lista de líneas que tienen fechas de vigencia e importes para combinaciones de dimensiones financieras. El usuario debe crear y usar plantillas de Excel para ver los datos del plan presupuestario en una tabla dinámica.</td>
<td>Existe un número ilimitado de diseños disponibles para los planes y las previsiones presupuestarias. Puede combinar dimensiones financieras seleccionadas, columnas definidas por el usuario y otros atributos de fila (como comentarios, proyectos y activos) en el diseño. Los usuarios pueden cambiar el diseño del documento del plan presupuestario sobre la marcha y editar datos seleccionando cualquier diseño. La configuración de la planificación presupuestaria se ha simplificado gracias a la eliminación de restricciones de situaciones y el uso de diseños para definir qué datos se pueden ver y editar en cada etapa del documento del plan presupuestario.</td>
<td>Proporciona la flexibilidad para crear y editar planes presupuestarios mediante Excel y el cliente de Dynamics AX. Las plantillas para libros de Excel pueden generarse mediante la configuración del diseño del plan presupuestario.</td>
</tr>
<tr>
<td>Imprima el informe <strong>Transacciones de factura de proveedor</strong> utilizando la información del informe<strong>Lista de días de vencimiento detallada</strong>, que incluye los días de retraso.</td>
<td>Debe imprimir dos informes distintos: <strong>Lista de días de vencimiento detallada</strong> y <strong>Transacciones de factura de proveedor</strong>.</td>
<td>La información acerca de los dos informes se ha consolidado en el informe <strong>Transacciones de factura de proveedor</strong>. El informe <strong>Lista de días de vencimiento detallada</strong> ha quedado en desuso.</td>
<td>Elimina la necesidad de imprimir dos informes independientes pero relacionados.</td>
</tr>
<tr>
<td>Genere informes reglamentarios directamente en formato PDF.</td>
<td>Primero debe generar un informe reglamentario en un formato y a continuación exportarlo a formato PDF.</td>
<td>El formato PDF es el formato predeterminado para los informes reglamentarios.</td>
<td>Proporciona una experiencia unificada de visualización en el monitor del equipo y una copia de papel impresa.</td>
</tr>
<tr>
<td>Ejecute el proceso de liquidación de impuestos como un proceso por lotes.</td>
<td>No disponible</td>
<td>En la página <strong>Período de liquidación de impuestos</strong> puede especificar que el proceso de liquidación se debe ejecutar en modo por lotes.</td>
<td>Para los períodos que tienen varias transacciones de impuestos, el proceso de liquidación puede ser largo, y puede ser mejor ejecutar el proceso en segundo plano como un proceso por lotes.</td>
</tr>
</tbody>
</table>

## <a name="foundation"></a>Fundación

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Obtenga acceso al cliente en cualquier momento y en cualquier lugar.</td>
<td>El cliente de escritorio AX 2012 proporciona un completo conjunto de formularios, pero solo se puede ejecutar en equipos con Microsoft Windows y es necesario instalarlo. Terminal Server se usa a menudo con el cliente de escritorio para permitir acceso a una red área amplia (WAN). La cliente web Enterprise Portal ofrece un conjunto reducido de formularios.</td>
<td>Los dos clientes AX 2012 han sido sustituidos por un cliente web único basado en estándares que proporciona el conjunto completo de funciones del cliente de escritorio junto con las del cliente Enterprise Portal.</td>
<td>Evita dividir esfuerzos de desarrollo entre dos plataformas de interfaz de usuario. Al usar interfaces web estándar, elimina la necesidad de usar Terminal Server.</td>
</tr>
<tr>
<td>Sea productivo mediante el nuevo grabador de tareas.</td>
<td>El grabador de tareas de AX 2012 requiere acceso directo a un equipo servidor de objetos de aplicaciones (AOS) y privilegios elevados, y no ofrece opciones de edición.</td>
<td>El nuevo grabador de tareas se puede usar directamente desde el cliente web. El acceso al grabador de tareas no requiere privilegios de administración. Los pasos grabados se pueden ver en directo a medida que se graba, se han introducido nuevas opciones de edición y el grabador de tareas admite más situaciones, además de las situaciones existentes del modelador de procesos empresariales (BPM).</td>
<td>El nuevo grabador de tareas proporciona una experiencia fluida y abre nuevas capacidades en Dynamics AX. Algunas de estas capacidades están disponibles ahora, y habrá más en el futuro.</td>
</tr>
<tr>
<td>Ayude a los usuarios a comprender mejor sus próximos trabajos con espacios de trabajo.</td>
<td>Las áreas de trabajo proporcionan una visión general de la información que pertenezca a la función de trabajo de un usuario en la empresa u organización.</td>
<td>Los espacios de trabajo son un nuevo concepto de Dynamics AX que están pensados para reemplazar áreas de trabajo como la manera principal de navegar hasta tareas y páginas específicas. Proporcionan una visión general de una página de una actividad empresarial y ayudan a los usuarios a comprender el estado actual, la próxima carga de trabajo y el rendimiento del proceso o del usuario. Los espacios de trabajo son más granulares que las áreas de trabajo de AX 2012 y un usuario puede tener acceso a varios espacios de trabajo.</td>
<td>Los espacios de trabajo están pensados para aumentar la productividad de los usuarios. Los desarrolladores deberán crear un espacio de trabajo para cada "actividad" importante admitida en el producto. Un área de trabajo heredada de AX 2012 normalmente se reemplazará por varias áreas de trabajo en la versión actual de Dynamics AX.</td>
</tr>
<tr>
<td>Haga que los formularios sean dinámicos a la ventanilla del explorador o al tamaño del dispositivo.</td>
<td>En AX 2012, el contenido del formulario se disponía estrictamente mediante columnas y el alto o ancho del formulario general se determinaba en gran medida basándose en los controles del formulario.</td>
<td>Con el cambio a la web en la versión más reciente de Dynamics AX, las dimensiones de un formulario se basan ahora en el tamaño de la ventanilla del explorador o en el dispositivo. Se han modificado o agregado controles y parámetros de diseño para responder mejor a los cambios en el tamaño de la ventanilla.</td>
<td>El contenido del formulario debe ser más dinámico para optimizar el uso del ancho o el alto disponible del explorador o dispositivo. Para lograr la capacidad de respuesta es posible que se requieran cambios en la forma en que se modela un formulario.</td>
</tr>
<tr>
<td>Utilice patrones para una lograr una experiencia de desarrollo de formularios mejorada.</td>
<td>Las plantillas de formularios estaban disponibles como punto de partida para el desarrollo de formularios en AX 2012 basándose en un estilo de formulario. El corrector de estilos de formularios, un complemento adicional, proporciona información sobre cómo se ha desviado un formulario de su plantilla correspondiente.</td>
<td>En la versión actual de Dynamics AX, se han introducido modelos de formulario. Los patrones de formularios representan una combinación de plantillas de formulario y el corrector de estilos de formularios estrechamente integrados en la experiencia de desarrollo. Los patrones se han definido en el nivel de formulario (como AX 2012) con subpatrones adicionales disponibles ahora en el nivel de página de fichas y grupo.</td>
<td>Los formularios que se ajusten a los patrones tienen muchas ventajas, incluyendo una interfaz de usuario más coherente, una experiencia de desarrollo más sencilla, una ruta de actualización de formularios más sencilla y una aumento de la confianza de la capacidad de respuesta del diseño de formularios.</td>
</tr>
</tbody>
</table>

## <a name="help"></a>Ayuda

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Obtenga acceso a la Ayuda guiada para procedimientos (guías de tarea) y temas sobre conceptos haciendo clic en <strong>Ayuda</strong>.</td>
<td>El sistema de ayuda de AX 2012 apunta a temas HTML almacenados en un servidor web local. Los clientes y los socios pueden crear su propio sistema de ayuda.</td>
<td>El sistema de ayuda en la versión actual de Dynamics AX muestra guías de tarea que se almacenan en el BPM de Microsoft Dynamics Lifecycle Services (LCS). El sistema de ayuda también muestra temas del sitio de documentos de Microsoft. Para obtener más información, consulte <a href="help-overview.md" data-raw-source="[Dynamics AX Help - Getting Started](help-overview.md)">Ayuda de Dynamics AX - Introducción</a> y <a href="new-task-guides-available-february-2016.md" data-raw-source="[New task guides available (February 2016)](new-task-guides-available-february-2016.md)">Nuevas guías de tareas disponibles (febrero de 2016)</a>.</td>
<td>Las guías de tarea proporcionan una experiencia guiada e interactiva que le lleva por los pasos de una tarea o de un proceso empresarial. Puede descargar y personalizar las guías de tareas que proporciona Microsoft. El tema proporciona una forma más rápida y flexible de crear, entregar y actualizar la documentación del producto. Por lo tanto, ayuda a garantizar que puede acceder a la información técnica más reciente.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Gestión del capital humano

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Transfiera aptitudes y certificados a los participantes en una clase tras finalizar el curso.</td>
<td>Este es un proceso manual.</td>
<td>Cuando se completa un curso, aparece una nueva opción disponible para actualizar los registros de los participantes con nuevas aptitudes y certificados.</td>
<td>Proporciona una nueva y eficiente manera de actualizar los registros de los empleados.</td>
</tr>
<tr>
<td>Verifique rápidamente los datos de empleo.</td>
<td>Este es un proceso manual.</td>
<td>Su departamento Recursos humanos podrá comprobar rápidamente los datos de empleo a través de un espacio de trabajo o la página del empleado.</td>
<td>Su departamento de Recursos humanos ya no tiene que acceder a varias páginas para comprobar la fecha de inicio, el gerente, los meses en el puesto y los datos de compensación.</td>
</tr>
<tr>
<td>Deje que los empleados vean, actualicen y eliminen información en el sistema.</td>
<td>Disponible, pero con capacidades limitadas de visualización y actualización.</td>
<td>Esta función está habilitada y permite a los empleados y los contratistas ver una amplia gama de datos personales. Opcionalmente se puede usar un flujo de trabajo cuando se crea, se actualiza o se elimina información.</td>
<td>Permite a los empleados asumir el control de su información, tanto actualizar la dirección o la información de contacto, solicitar un trabajo, realizar un cuestionario o actualizar su imagen. Cuando se habilita un flujo de trabajo, la información la puede revisar un aprobador o se puede aprobar automáticamente, en función de sus procesos empresariales.</td>
</tr>
<tr>
<td>Permita que los gerentes vean o editen la información del empleado.</td>
<td>Disponible, pero con capacidades limitadas de visualización y actualización.</td>
<td>En función de la configuración y de la seguridad, los gerentes pueden ver o editar la información del empleado.</td>
<td>Esto permite a los gerentes acceder a datos importantes del empleado, de modo que puedan tomar mejores decisiones sobre recursos, rendimiento y desarrollo del empleado.</td>
</tr>
<tr>
<td>Aproveche la funcionalidad de autoservicio del director.</td>
<td>No disponible</td>
<td>Los directores pueden enviar ahora solicitudes de nuevas contrataciones (empleados y contratistas), transferencias y terminación (cese del empleo). Los directores también pueden solicitar un nuevo puesto, ampliar la duración de los puestos o solicitar cambios de posición.</td>
<td>Estos escenarios solo se exponían anteriormente a Recursos Humanos. Habilitar estos escenarios proporciona eficaces herramientas para los directores de una organización. Los flujos de trabajo opcionales se pueden habilitar para proporcionar el nivel adecuado de revisión y aprobaciones.</td>
</tr>
<tr>
<td>Acceda a los resultados del proceso de compensación.</td>
<td>Los resultados solo están disponibles en el momento de procesamiento.</td>
<td>Ahora se puede acceder a los resultados de los procesos de compensación en cualquier momento tras ejecutar el proceso.</td>
<td>Proporciona una auditoría excelente del proceso y el resultado del proceso. También proporciona una vista completa de los datos antes de que los registros de empleados se actualicen.</td>
</tr>
<tr>
<td>Acceda a los resultados del proceso de prestaciones.</td>
<td>Los resultados solo están disponibles en el momento de procesamiento.</td>
<td>Ahora se puede acceder a los resultados de los procesos de prestaciones en cualquier momento tras ejecutar el proceso.</td>
<td>Ofrece una visión completa de los datos que se actualizan por inscripción en prestaciones y cambios de costes.</td>
</tr>
<tr>
<td>Vea cambios de línea de tiempo "Fecha de vigencia".</td>
<td>No disponible</td>
<td>Esta herramienta de comparación está disponible para empleados, puestos y trabajos. Ofrece una visión completa de cambios de una versión de un registro a otra.</td>
<td>Le ahorra tiempo al ver los cambios que se han producido con el tiempo en los empleados, los puestos y los registros de trabajo. Permite comparar rápidamente dos versiones de un registro, todos los registros o con el transcurso del tiempo.</td>
</tr>
<tr>
<td>Vea empleados por empresa.</td>
<td>Este es un proceso manual que se lleva a cabo mediante filtrado.</td>
<td>Las listas de empleados y contratistas se filtran automáticamente según la empresa con la que haya iniciado sesión.</td>
<td>Proporciona una vista filtrada de los empleados de la empresa desde la que se ha abierto sesión. Para ver una vista sin filtro de todos los empleados y los contratistas, dispone de la lista de trabajadores. En la versión actual de Dynamics AX, el sistema no cambia la empresa en función del empleado seleccionado en la lista.</td>
</tr>
<tr>
<td>Actualice la lista de participantes en un curso.</td>
<td>No disponible</td>
<td>Los participantes del curso se pueden quitar de la lista de participantes.</td>
<td>Proporciona una manera fácil de actualizar los participantes en el curso registrados por error.</td>
</tr>
<tr>
<td>Gestione eventos de compensación en un grupo.</td>
<td>No disponible</td>
<td>Esta función racionaliza el proceso de cambios de compensación para los empleados.</td>
<td>Proporciona un proceso simple y fluido para actualizar los registros de los empleados a través del espacio de trabajo de compensación y las páginas relacionadas.</td>
</tr>
</tbody>
</table>

## <a name="inventory-management"></a>Gestión del inventario

No se han agregado funciones nuevas.

## <a name="localization"></a>Localización

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Configure y genere documentos electrónicos para cumplir con los requisitos legales en distintos países/regiones.</td>
<td>Los documentos electrónicos se cifran en X++ o como transformaciones en lenguaje de transformación basado en hojas de estilo (XSLT). Cualquier ajuste de formato requiere un trabajo de desarrollo. El acceso a los datos y el formato no es un acceso aislado. Para implementar un ajuste de formato es necesario contar con un nuevo paquete de revisión de Microsoft Dynamics AX que sustituye al formato existente. Las modificaciones personalizadas de cada formato se deben transferir manualmente al código fuente de un nuevo paquete de revisión de Microsoft Dynamics AX.</td>
<td>Electronic Reporting (ER) es una nueva herramienta para configurar y generar documentos electrónicos para usuarios empresariales en lugar de programadores. ER le permite configurar modelos de datos específicos del dominio e independientes de la base de datos de Microsoft Dynamics AX como orígenes de datos para formatos de documento. Un usuario empresarial puede configurar los formatos en función de estos modelos de datos específicos del dominio (por ejemplo, para pagos, informes Intrastat o informes fiscales). El usuario configura los formatos mediante herramientas visuales simples similares a Excel. ER permite actualmente generar documentos electrónicos en texto, XML y formatos de Excel. Estos documentos se pueden generar simultáneamente y empaquetar en archivos zip. Los modelos y los formatos de datos admiten distintas versiones. Las versiones de formato pueden tener períodos de vigencia. Cada versión de modelo o formato de datos se almacena en una configuración independiente y se distribuye a los socios y los clientes a través de LCS. Los socios y los clientes pueden personalizar los modelos y formatos de datos de Microsoft, o crear los suyos propios. ER guarda los cambios de la configuración del socio y el cliente como versiones delta de las configuraciones de Microsoft, lo que simplifica la actualización a nuevas versiones de las configuraciones de Microsoft. Mediante el uso de LCS, los socios también pueden compartir sus configuraciones de modelo y formato de datos con otros socios y clientes, quienes pueden personalizarlos y compartirlos. La personalización delta y la fácil actualización son posibles en toda la cadena de personalización.</td>
<td>ER simplifica la creación, el mantenimiento y la actualización de formatos de documentos electrónicos para cumplir con los requisitos legales en distintos países/regiones. ER realiza el proceso de crear o cambiar los formatos de documentos electrónicos más rápidamente y más fácilmente. Estos cambios los pueden llevar a cabo los usuarios empresariales en lugar de los desarrolladores. ER hace más rápido y más fácil para los socios y los clientes actualizar sus personalizaciones de formato a nuevas versiones de formatos emitidos por Microsoft u otros socios. ER proporciona una forma común (mediante CD) en la que Microsoft y sus socios pueden distribuir las configuraciones de documentos electrónicos a otros socios y clientes. ER también facilita a los socios y los clientes la personalización, actualización y distribución de formatos de documentos electrónicos según sus requisitos específicos de empresa.</td>
</tr>
<tr>
<td>(MEX) Genere informes reglamentarios de impuesto sobre el valor añadido mexicano (IVA).</td>
<td>Debe generar informes de <strong>IVA de ventas y compras</strong> mediante la función de IVA no realizado para que los usuarios puedan identificar las transacciones que pertenecen a las secciones realizadas y no realizadas en función del estado.</td>
<td>Los informes de <strong>IVA de ventas y compras</strong> se han modificado, y ahora tienen en cuenta la función de impuestos condicionales solo mediante el uso de períodos de liquidación específicos para la definición de códigos de impuestos sin realizar y realizados.</td>
<td>Es necesario aplicar cambios en la configuración de los códigos de impuestos para que los usuarios puedan generar estos informes correctamente. Se requiere una función de impuestos condicionales, y el usuario debe configurar períodos de liquidación individuales, sin realizar y realizados, para identificar las transacciones en las áreas de sección relacionadas.</td>
</tr>
<tr>
<td>(JPN) Gestione el documento de declaración de depreciación acelerada de activos fijos japonés.</td>
<td>No disponible</td>
<td>La información importante de la declaración se almacena centralmente en un único documento para un mejor mantenimiento.</td>
<td>El cumplimiento normativo del documento y la facilidad de la ayuda de gestión reducen problemas durante auditorías y otras revisiones.</td>
</tr>
<tr>
<td>(JPN) compruebe los caracteres JBA en la cuenta bancaria.</td>
<td>No disponible</td>
<td>Puede comprobar que los campos de nombre kana contengan solo los caracteres que admita el formato bancario JBA.</td>
<td>Ayuda a reducir interrupciones para los usuarios durante la generación de archivos de pago debido a caracteres no válidos.</td>
</tr>
<tr>
<td>(JPN) Ponga al día la diferencia de decimales en activos fijos en Japón al final del ejercicio fiscal.</td>
<td>No disponible</td>
<td>En la página <strong>Parámetros de activos fijos</strong> puede elegir poner al día los datos al final del período o del ejercicio fiscal.</td>
<td>Proporciona más flexibilidad para conciliar prácticas locales.</td>
</tr>
<tr>
<td>(JPN) Genere la serie 16 de tablas de declaración adjunta de impuestos corporativos para Japón en importes resumidos por tipo principal de activos fijos.</td>
<td>No disponible</td>
<td>En los modelos de valor de un activo fijo puede elegir resumir por tipo principal. De forma predeterminada, esta función se usa para los activos fijos recién creados.</td>
<td>Para corporaciones grandes que tienen miles de activos fijos, los informes resumidos reducen mucho el tamaño del informe generado.</td>
</tr>
<tr>
<td>(JPN) Empiece a asignar reservas especiales de depreciación a partir del próximo ejercicio fiscal para activos fijos en Japón.</td>
<td>No disponible</td>
<td>En los modelos de valor de un activo fijo con un método de depreciación extraordinaria adecuado, puede elegir iniciar la asignación a partir del período fiscal siguiente o del ejercicio fiscal siguiente.</td>
<td>Proporciona más flexibilidad para conciliar prácticas locales.</td>
</tr>
<tr>
<td>(JPN) Genere un informe de impuestos al consumo para Japón que incluya las imposiciones fiscales revisadas.</td>
<td>El informe del impuesto al consumo está disponible para un índice de impuestos del 5 por ciento.</td>
<td>El informe de impuesto al consumo contiene una sección para el índice de impuestos revisado (por ejemplo, el 8 por ciento).</td>
<td>El diseño ha sido recién anunciado por el gobierno.</td>
</tr>
<tr>
<td>(UE) Configure las opciones de redondeo para la lista de ventas de la UE.</td>
<td>Las opciones de redondeo de los informes de la lista de ventas de la UE para varios países o regiones está codificadas en X++ o en Lenguaje de transformación basado en hojas de estilo (XSLT).</td>
<td>Las opciones de redondeo se agregan a los parámetros de comercio exterior. Puede configurar la precisión de redondeo, el método de redondeo, la precisión de la salida y el comportamiento de los importes menores a la precisión de redondeo.</td>
<td>Esto unifica y simplifica la configuración de los informes de lista de ventas de la UE. El ajuste de las opciones de redondeo ya no requiere esfuerzos de desarrollo.</td>
</tr>
<tr>
<td>(UE) Configure las reglas de aplicabilidad de cargo invertido.</td>
<td>Las reglas de aplicabilidad de cargo invertido están codificadas para el escenario de cargo invertido nacional. El umbral de aplicabilidad puede configurarse por grupo de artículos. La función solo está disponible en Gran Bretaña.</td>
<td>Puede configurar las reglas de aplicabilidad de cargo invertido por tipo de documento (pedido de compra o de ventas, factura de proveedor, facturas de servicios, etc.) y un grupo de cargos invertidos que combina artículos, grupos de artículos y categorías de compras o de venta. Las reglas de aplicabilidad tienen fecha de vigencia. También puede marcar los códigos individuales de impuestos en grupos de impuestos como aplicables para el cargo invertido. El informe de factura de ventas se ajusta para representar los detalles del cargo invertido aplicado. La funcionalidad está disponible para todos los países o regiones europeos.</td>
<td>Este cambio unifica la configuración de las reglas de aplicabilidad de cargo invertido y admite la adopción de reglamentos nacionales de cargos invertidos por países o regiones europeos.</td>
</tr>
<tr>
<td>(DE) Generar el archivo de auditoría alemán - GDPdUGoBD</td>
<td>Los usuarios pueden configurar la definición de tablas que contienen datos financieros para exportarlos en un formato aceptado por las autoridades y auditores alemanes.</td>
<td>La característica se ha implementado como una configuración de informes electrónicos. La función está disponible para Alemania y Austria.</td>
<td>Este cambio ofrece al usuario muchas más posibilidades en el formato de datos y las transformaciones, además de proporcionar todos los beneficios derivados de la gestión del ciclo de vida de configuración de informes electrónicos, como el intercambio de configuración sencilla, control de versiones, etc.</td>
</tr>
<tr>
<td>(FR) Informe de la lista de saldo con cuentas totales de grupo</td>
<td>La lista de saldo con el informe de cuentas totales de grupo se implementa como informe SSRS (LedgerAccountSum_FR).</td>
<td>El informe de la lista de saldo con el informe de cuentas totales de grupo se implementa como informe de Management Reporter disponible en la carpeta de informes financieros localizados de biblioteca de activos de LCS.</td>
<td>Esto permite a los usuarios obtener todos los beneficios y libertad en las personalizaciones del uso de informes financieros en Management Reporter.</td>
</tr>
<tr>
<td>(UE) Aviso de pago, nota adjunta e informes de control para pagos.</td>
<td>Se implementan todos esos informes e informes de SSRS.</td>
<td>Estos informes se han implementado como plantillas de Open XML para utilizarse en Microsoft Excel.</td>
<td>Las configuraciones de pago electrónico contienen plantillas y configuración de formato de archivos de pago. Esto permite a los usuarios obtener todos los beneficios y libertad en las personalizaciones de informe del uso de informes electrónicos.</td>
</tr>
<tr>
<td>(UE) Configure las opciones de redondeo para intrastat.</td>
<td>Las opciones de redondeo de los informes de intrastat para varios países o regiones está codificadas en X++ o en Lenguaje de transformación basado en hojas de estilo (XSLT).</td>
<td>Las opciones de redondeo se agregan a los parámetros de comercio exterior. Puede configurar la precisión de redondeo, el método de redondeo, la precisión de la salida y el comportamiento de los importes menores a la precisión de redondeo.</td>
<td>Esto unifica y simplifica la configuración de los informes de intrastat. El ajuste de las opciones de redondeo ya no requiere esfuerzos de desarrollo.</td>
</tr>
<tr>
<td>(UE) Configure códigos de mercancías de intrastat en jerarquías de categorías.</td>
<td>Los códigos de mercancías de intrastat forman una lista independiente. Mientras haya una jerarquía de categorías de tipo Código de mercancía, estos códigos de mercancía podrían tomarse como predeterminados en las categorías de ventas y Retail HQent.</td>
<td>La lista independiente de códigos de mercancía intrastat se combinan con la jerarquía de productos del tipo Código de mercancía.</td>
<td>Esto unifica el enfoque para asignar códigos de mercancía para categorías y productos emitidos de documentos de compra y de venta.</td>
</tr>
<tr>
<td>(UE) Elabore informes de la cantidad de unidades adicionales para intrastat mediante la opción de conversión de unidades.</td>
<td>El código de mercancía de intrastat tiene un campo de texto para identificar unidades adicionales y la tarjeta <strong>Producto</strong> tiene un campo para identificar la cantidad de unidades adicionales en kilogramos.</td>
<td>Las unidades adicionales para el código de mercancía de intrastat se eligen de la lista de unidades. La cantidad de unidades adicionales se calcula a través de la configuración de la conversión de unidades.</td>
<td>Esto unifica el enfoque del recálculo de las unidades de transacción a unidades adicionales.</td>
</tr>
<tr>
<td>(UE) Asigne el método de transporte de intrastat predeterminado al modo de entrega.</td>
<td>No disponible</td>
<td>Se agrega un campo para el método de transporte predeterminado al modo de entrega.</td>
<td>Esto simplifica la preparación de los informes intrastat.</td>
</tr>
<tr>
<td>(UE) Marque el producto emitido que se no se va a notificar en intrastat.</td>
<td>No disponible</td>
<td>Una opción para excluir el artículo de los informes intrastat se agrega al producto liberado.</td>
<td>Esto simplifica la preparación de los informes intrastat.</td>
</tr>
</tbody>
</table>

## <a name="manufacturing"></a>Fabricación

| ¿Qué se puede hacer? | Dynamics AX 2012 |
|------------------|------------------|
| Realice una comprobación de la disponibilidad de material para los pedidos de producción en una página aparte que se abre desde el espacio de trabajo **Gestión de planta de producción**. | No disponible |
| Inicie trabajos de producción e informe de su progreso mediante la nueva página **Dispositivo de tarjetas de trabajo**. | El formulario **Registro del trabajo**se genera sobre todo para pantallas de terminales grandes, y a la interfaz de usuario normalmente se accede mediante clics del ratón. |

## <a name="master-planning-and-forecasting"></a>Previsión y planificación maestra

| ¿Qué se puede hacer? | Dynamics AX 2012 | Dynamics AX 7.0 | ¿Por qué esto es importante? |
|------------------|------------------|-----------------|------------------------|
| Advierta al usuario de si un pedido de ventas o un pedido de producción no está listo para su entrega para la fecha programada. | Las advertencias creadas por la planificación se llaman *mensajes de futuros*. *Futuros* es un contrato entre dos partes para comprar o para vender un activo a un precio convenido hoy (el *precio de futuros*), aunque la entrega y el pago se produzcan en un futuro (la *fecha de entrega*). | El nombre de los *mensajes de futuros* y las *fechas de futuros* se ha cambiado a *retrasos calculados* y *fechas retrasadas* respectivamente. | La terminología que se usaba en AX 2012 no era precisa y llevaba a traducciones incorrectas. |
| Consiga una rápida información sobre el estado de la ejecución de una planificación maestra, los pedidos planificados urgentes y los pedidos planificados que causan retrasos. | La información está disponible, pero dispersa en varios formularios. | El espacio de trabajo **Planificación maestra** proporciona la información rápida acerca de cuándo se completó la última ejecución de la planificación maestra, si se han producido errores, cuáles son los pedidos planificados urgentes y qué pedidos planificados causan retrasos. | Usted se beneficia de la descripción que el espacio de trabajo proporciona. La información pertinente se coloca junta para guiar la planificación maestra y para ayudar a mejorar la productividad. |
| Use Excel para actualizar las previsiones de demanda. | No disponible | Puede aprovechar la integración fluida con Excel al especificar previsiones de demanda, realizar actualizaciones y eliminar previsiones de demanda. | Esto ayuda a aumentar la eficacia y la productividad. |
| Calcule la demanda futura y cree previsiones de demanda en función de los datos de transacción históricos. | En Microsoft Dynamics AX 2012 R3, los modelos de previsión en el servicio de análisis de Microsoft SQL Server se usan para crear predicciones de previsión de la demanda. | Estime la demanda futura mediante la capacidad y la extensibilidad de un servicio de nube de aprendizaje automático de Microsoft Azure. Es fácil de usar y expande los modelos de previsión en Aprendizaje automático para atender a los requisitos del cliente. El servicio realiza la selección del modelo de mejor coincidencia y ofrece indicadores de rendimiento clave (KPI) que se pueden usar para calcular la precisión de la previsión. | Genere previsiones más exactas mediante las técnicas de aprendizaje automático. |
| Optimice la fecha y la cantidad del pedido en función de una visión general gráfica de acciones relacionadas desde la ejecución de la planificación maestra. | El gráfico de visión general de acciones está disponible pero muestra todas las acciones relacionadas. Cuando se aplican las acciones, desaparecen inmediatamente de la vista. | El gráfico de acciones proporciona una visión general mejor. Incluye opciones que le permiten mostrar solo acciones aplicadas y acciones directamente relacionadas. Cuando se aplican acciones, aparecen atenuadas, pero se muestran. Por tanto, se conserva la visión general. Se agrega información adicional al gráfico de acciones para mostrar los datos en una página. | Usted se beneficia de una mejora en la productividad, ya que se centra solo en las acciones relevantes. |

## <a name="procurement-and-sourcing"></a>Adquisición y abastecimiento

| ¿Qué se puede hacer? | Dynamics AX 2012 | Dynamics AX 7.0 | ¿Por qué esto es importante? |
|------------------|------------------|-----------------|------------------------|
| Use el espacio de trabajo **Preparación de pedidos de compra** para conseguir información rápida sobre el estado de los pedidos de compra se están preparando. | No admitido | El espacio de trabajo **Preparación de pedidos de compra** proporciona una visión general de los pedidos desde el momento en que se crean como borrador y se delinean, pasando por los estados de aprobación de flujo de trabajo y hasta su confirmación. | Su departamento de compras ya no tiene que buscar información en varias páginas, sino que ahora se beneficia de una visión general en el espacio de trabajo. |
| Use el espacio de trabajo **Recepción y seguimiento de pedidos de compra** para conseguir información rápidamente sobre los pedidos de compra pendientes de recepción y facilitar así su seguimiento. | No admitido | El espacio de trabajo **Recepción y seguimiento de pedidos de compra** proporciona una visión general de los pedidos de compra confirmados con recepciones o envíos pendientes. El espacio de trabajo incluye listas de recepciones vencidas y pendientes para ayudar a revisar proactivamente y hacer un seguimiento del proveedor. El espacio de trabajo también lista los pedidos de compra con registro de llegada en el almacén para ayudar a garantizar que la recepción quede registrada. Las devoluciones de los pedidos de compra que aún no se han enviado también están disponibles para su revisión. | El departamento de compras disfruta de la visión general que ofrece el espacio de trabajo. La información pertinente se coloca junta para hacer un seguimiento y ayudar a mejorar la productividad. |
| Envíe pedidos de compra para su confirmación al portal de proveedores alojado en el cliente de Dynamics AX. Deje el proveedor confirme o rechace. | No admitido | La interfaz del portal de proveedores permite a los proveedores recibir pedidos de compra para confirmar o rechazar. También permite al proveedor tener una visión general de todos los pedidos de compra confirmados para una cuenta. El agente de compras puede enviar un pedido de compra solicitando confirmación del proveedor. El proveedor debe ser un usuario registrado de Microsoft Azure Active Directory (Azure AD) en Dynamics AX, una persona de contacto para el proveedor y tener un rol de seguridad dedicado. | El departamento de compras se podrá beneficiar de la reducción del trabajo en papel y de las respuestas de seguimiento manual de los pedidos de compra a medida que fluyen directamente en el sistema. Tener una fuente de información verdadera reduce los malentendidos entre el cliente y el proveedor. |

## <a name="projects"></a>Proyectos

| ¿Qué se puede hacer? | Dynamics AX 2012 | Dynamics AX 7.0 | ¿Por qué esto es importante? |
|------------------|------------------|-----------------|------------------------|
| Reserve trabajadores como recursos en proyectos. | Similar a los recursos, los trabajadores se reservan directamente en proyectos, además de recursos. | La tabla del centro de trabajo donde se almacenan los recursos para fabricación y producción puede ahora usarse para reservar a trabajadores como recursos en un proyecto. | Al reservar proyectos, solo tiene que reservar recursos. |

## <a name="retail-sales-marketing-and-customer-service"></a>Ventas al por menor, marketing y servicio al cliente

### <a name="retail-hq"></a>Retail HQ

Retail HQ alojado en Microsoft Azure ofrece gestión centralizada y una visibilidad completa de todos los aspectos de las operaciones comerciales a través de un cliente web.

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Realice operaciones de comercialización.</td>
<td>Los usuarios deben acceder a varios formularios para gestionar estos datos:
<ul>
<li>Gestión de categorías</li>
<li>Gestión de productos</li>
<li>Atributos de producto del canal</li>
<li>Varios</li>
<li>Administración de catálogos</li>
<li>kits</li>
<li>Precios y descuentos</li>
</ul></td>
<td>El espacio de trabajo <strong>Administración de categorías y productos</strong> habilita la funcionalidad siguiente:
<ul>
<li>Administración de surtidos.</li>
<li>Seguimiento de ciclos de vida de surtidos.</li>
<li>Administración de productos emitidos.</li>
</ul>
El espacio de trabajo <strong>Administración de precios y descuentos</strong> habilita la funcionalidad siguiente:
<ul>
<li>Administración de precios y descuentos para un canal y una categoría dados.</li>
<li>Administración de reglas de precios de categorías.</li>
<li>Prioridades de precios y descuentos, que le permiten asignar prioridades a grupos de precios y descuentos para que pueda controlar el orden en que se aplican.</li>
<li>Administración de descuentos en catálogos y afiliaciones.</li>
</ul>
El espacio de trabajo <strong>Administración de catálogos</strong> habilita la funcionalidad siguiente:
<ul>
<li>Resumen de catálogos activos.</li>
<li>Seguimiento de ciclos de vida de catálogos en una única ubicación.</li>
</ul></td>
<td><ul>
<li>Los espacios de trabajo mejoran la eficacia y la productividad de los trabajadores permitiéndoles gestionar centralmente las tareas y las acciones relacionadas con el rol de comercialización.</li>
<li>La función de prioridades de precio y descuento otorga a los clientes más control sobre cómo se usan los precios y los descuentos. La función también permite nuevas situaciones donde los precios más altos en la tienda ganan a los precios estándar.</li>
</ul></td>
</tr>
<tr>
<td>Gestione las implementaciones y las operaciones del canal de venta minorista.</td>
<td>El usuario debe tener acceso a varios formularios para realizar las tareas siguientes:
<ul>
<li>Crear y configurar nuevos canales y entidades relacionadas.</li>
<li>Gestionar actividades diarias en la tienda.</li>
<li>Las transacciones comerciales de proceso en Microsoft Dynamics AX, generar instrucciones al por menor, y actualiza el inventario y los operaciones financieras Microsoft Dynamics AX.</li>
</ul>
</td>
<td>El espacio de trabajo <strong>Implementación de canales</strong> le permite realizar las tareas siguientes:
<ul>
<li>Crear nuevos canales y entidades relacionadas.</li>
<li>Hacer un seguimiento del progreso de la configuración de la tienda de venta minorista.</li>
<li>Realizar los pasos necesarios para completar una tarea o proporcionar información para completar la tarea.</li>
<li>Hacer un seguimiento del estado de los dispositivos y validar y descargar directamente la instalación del programa Retail Modern POS (MPOS) en las tiendas.</li>
<li>Acceder a todas las páginas relacionadas.</li>
</ul>El espacio de trabajo 
<strong>Gestión de tienda comercial</strong> le permite realizar las tareas siguientes:
<ul>
<li>Administrar a los trabajadores y los permisos de los puntos de venta de los trabajadores (PDV).</li>
<li>Hacer un seguimiento del estado de los turnos para una tienda determinada o un grupo de tiendas.</li>
<li>Validar y descargar directamente la instalación del programa MPOS en las tiendas.</li>
<li>Imprimir informes y acceder a páginas relacionadas.</li>
</ul>El espacio de trabajo 
<strong>Operaciones financieras de tienda</strong> le permite realizar las tareas siguientes:
<ul>
<li>Crear, calcular y registrar extractos para un canal concreto.</li>
<li>Programar trabajos por lotes para actualizar el inventario y calcular y registrar extractos.</li>
<li>Hacer un seguimiento de los extractos abiertos.</li>
<li>Hacer un seguimiento del estado de los turnos para una tienda determinada o un grupo de tiendas.</li>
<li>Imprimir informes y acceder rápidamente a todas las páginas relacionadas.</li>
</ul></td>
<td>Los espacios de trabajo mejoran la eficacia y la productividad de los trabajadores permitiéndoles gestionar centralmente la mayoría de las tareas y las acciones relacionadas con la implementación del canal, la gestión de tiendas y las operaciones financieras.</td>
</tr>
<tr>
<td>Gestione operaciones comerciales de TI.</td>
<td>El usuario debe tener acceso a varios formularios.</td>
<td>El espacio de trabajo <strong>TI de venta minorista</strong> habilita las consultas de Commerce Data Exchange en un único lugar para un canal determinado, de manera que pueda realizar las tareas siguientes:
<ul>
<li>Descargar sesiones.</li>
<li>Cargar sesiones.</li>
<li>Hacer un seguimiento de sesiones fallidas y volver a iniciarlas o ejecutarlas de nuevo.</li>
<li>Ver o ejecutar trabajos próximos.</li>
</ul></td>
<td>Los espacios de trabajo mejoran la eficacia y la productividad de los trabajadores permitiéndoles gestionar centralmente las tareas y las acciones relacionadas con las operaciones de venta minorista de TI.</td>
</tr>
<tr>
<td>Importe o exporte datos mediante entidades de datos.</td>
<td>AX 2012 permite migrar Microsoft Dynamics Retail Management System (RMS) desde el principio mediante el marco de importación e exportación de datos.</td>
<td>Las entidades de datos se han expandido para admitir todos los datos de referencia y maestros relacionados con la venta minorista. También se ha mejorado la compatibilidad con entidades de datos en toda la solución de Dynamics AX.</td>
<td>Las entidades de datos permiten a los clientes importar y exportar datos basados en metadatos. Las entidades OData también permiten a los clientes integrar Dynamics AX con programas de terceros.</td>
</tr>
<tr>
<td>Realice análisis inteligentes mediante informes de inteligencia empresarial desde Dynamics Microsoft AX y el cliente del PDV.</td>
<td>Más de 25 informes administrativos y cinco informes de canal disponibles.</td>
<td>Más de 30 informes administrativos y 10 informes de canal disponibles.</td>
<td>Estos informes permiten a los clientes disponer de más inteligencia artificial para predecir tendencias, detectar información y operar con un rendimiento máximo continuo.</td>
</tr>
<tr>
<td>Analice datos de las ventas del canal de venta minorista mediante el contenido de "supervisión de Retail Channel Performance" de Power BI.</td>
<td>No disponible</td>
<td>En PowerBI.com, seleccione <strong>Obtener datos</strong> y, a continuación, seleccione el paquete de contenido <strong>Dynamics AX – Retail Channel Performance</strong>. Especifique la dirección URL del terminal de Dynamics AX para ver sus datos reflejados en el panel de información.</td>
<td>En de tres a cuatro clics, las organizaciones pueden implementar un panel de información de Power BI con datos financieros importantes. La organización puede personalizar el contenido. Además, los usuarios pueden incrustar iconos del panel de información de Power BI en sus espacios de trabajo personalizados en Dynamics AX, de modo que puedan ver la información analítica de inmediato.</td>
</tr>
<tr>
<td>Configure permisos de usuario.</td>
<td>No disponible</td>
<td>Los clientes pueden elegir si las operaciones del PDV pueden estar disponibles para los consumidores. Retail Server usa permisos para las llamadas de interfaz de programación de aplicaciones (API).</td>
<td>Proporciona la capacidad de configurar permisos de consumidor.</td>
</tr>
<tr>
<td>Gestione y valide configuraciones de entidad.</td>
<td>No disponible</td>
<td>La función de administrador de la configuración y validador habilita la funcionalidad siguiente:
<ul>
<li>Carga masiva de los datos de configuración.</li>
<li>Validación de entidades empresariales.</li>
</ul></td>
<td>Proporciona la capacidad de adjuntar la configuración de arranque y de validar el estado y el grado de finalización de la configuración de distintos elementos de configuración.</td>
</tr>
</tbody>
</table>

### <a name="retail-hardware-station"></a>Estación de hardware para Retail

| ¿Qué se puede hacer? | Dynamics AX 2012 | Dynamics AX 7.0 | ¿Por qué esto es importante? |
|------------------|------------------|-----------------|------------------------|
| Habilite los dispositivos del PDV para conectarse a periféricos como impresoras, cajas registradoras o dispositivos de pago. | El perfil de hardware de MPOS se usa para especificar los dispositivos utilizados. | Un perfil de hardware agregado admite hardware más diverso de una estación a la siguiente. Un nuevo perfil de estación de hardware permite disponer de una identificación única de terminal para cada estación de hardware cuando se procesan transacciones de transferencia electrónica de fondos (EFT). La compatibilidad con EFT se ha combinado en la estación de hardware para reducir la participación de MPOS en el proceso de pago EFT. | Proporciona mayor flexibilidad para las implementaciones. También proporciona seguridad mejorada y menos exposición a los datos de tarjetas de crédito. |

### <a name="retail-server-and-data-management"></a>Retail Server y gestión de datos

Retail Server y la gestión de datos permite a los consumidores y las empresas crear una experiencia de compras en canales simultáneos en los canales línea, en la tienda y en los centros de llamadas.

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Conecte con una base de datos comercial de tiempo de ejecución (CRT) que almacena datos empresariales para el canal mediante servicios CRT.</td>
<td>OData V3 es compatible.</td>
<td>OData V4 es compatible.</td>
<td>Ayuda al cliente a permanecer al día con los estándares OData. También crea una experiencia robusta en todos los canales integrando las ventas en los canales de tienda, móviles y en línea.</td>
</tr>
<tr>
<td>Admita servicios minoristas como un conjunto de servicios alojables.</td>
<td>La API de E-commerce no es compatible en Retail Server.</td>
<td>La API de E-commerce está ahora disponible a través de Retail Server para admitir el contexto en línea.</td>
<td>Proporciona servicios de comercio electrónico alojados y escalables que se pueden usar con tiendas en línea de terceros.</td>
</tr>
<tr>
<td>Mueva los datos entre la oficina administrativa de Microsoft Dynamics AX y los canales mediante Commerce Data Exchange.</td>
<td>Commerce Data Exchange es un sistema que transfiere datos entre Microsoft Dynamics AX y canales minoristas, como tiendas en línea o tiendas físicas. Para obtener más información, consulte <a href="https://technet.microsoft.com/library/dn741440.aspx">Commerce Data Exchange [AX 2012]</a>.</td>
<td>Hay una paridad funcional con Microsoft Dynamics AX 2012 CU8. No obstante, tenga en cuenta los siguientes detalles:
<ul>
<li>Commerce Data Exchange se ha rediseñado para la nube.</li>
<li>El servicio Async usa acceso directo de base de datos a la base de datos del canal.</li>
<li>Commerce Data Exchange: Real-time Service se hospeda como un servicio personalizado de Microsoft Dynamics AX.</li>
<li>MPOS gestiona la sincronización entre las bases de datos sin conexión y Retail Server.</li>
</ul></td>
<td>Commerce Data Exchange se ha rediseñado para la plataforma de la nube. Sigue gestionando la transferencia de datos entre Microsoft Dynamics AX y los canales de venta minorista, como tiendas en línea o tiendas físicas.</td>
</tr>
<tr>
<td>Admita el procesamiento de pagos plug and play semi-integrado a través de varios canales mediante el pago SDK.</td>
<td>AX 2012 proporciona las funcionalidades siguientes:
<ul>
<li>Compatibilidad con todos los canales: PDV, comercio electrónico y centros de llamadas.</li>
<li>Soporte para operaciones con tarjeta y sin tarjeta.</li>
<li>Página para aceptar pagos.</li>
<li>Soporte de periféricos para LS5300 y MX925 como código de ejemplo en SDK de Retail.</li>
</ul></td>
<td>La versión actual de Dynamics AX admite todas las funciones de tarjeta de crédito y débito existentes de Microsoft Dynamics AX for Retail 2012 y cuatro nuevas mejoras.</td>
<td>Permite al cliente procesar transacciones de tarjeta de crédito y débito para pagos.</td>
</tr>
<tr>
<td>Active los dispositivos mediante una cuenta de Microsoft (Microsoft Azure Active Directory (Azure AD)).</td>
<td>No disponible</td>
<td>Se proporcionan las funcionalidades siguientes:
<ul>
<li>Seguridad mejorada mediante activación basada en Azure AD para la nube.</li>
<li>Seguridad mejorada para gestión de tokens.</li>
<li>Fiabilidad mejorada, solución de problemas y mensajes de error durante la activación.</li>
<li>Tareas de administración de TI simplificadas relacionadas con la activación.</li>
<li>Modelo de riesgos revisado y problemas de seguridad arreglados.</li>
</ul></td>
<td>Proporciona las prestaciones siguientes:
<ul>
<li>La seguridad se ha mejorado a través de Azure AD y el identificador/token de dispositivos (llamadas RS que usan token y almacenamiento de aplicaciones según usuarios específicos).</li>
<li>Detiene usos no autorizados remotos de MPOS (bloqueo del dispositivo).</li>
<li>Hace seguimientos de los dispositivos MPOS para fines de conformidad PCI.</li>
<li>Asigna dispositivos físicos con una entidad de negocio (registro) mediante un token de dispositivo.</li>
<li>Inicializa las opciones para funcionalidad MPOS suave (secuencias numéricas y perfiles de hardware) como el primer punto de contacto de MPOS.</li>
<li>Transfiere información del dispositivo desde las centrales.</li>
</ul></td>
</tr>
<tr>
<td>Gestione contenido de medios enriquecidos para crear y servir a través de la galería multimedia.</td>
<td>No disponible</td>
<td><ul>
<li>Admita la carga de imágenes y también ver, gestionar y eliminar desde la galería multimedia para imágenes alojadas externamente y en Retail.</li>
<li>Admita la carga y visualización de imágenes desde páginas de la entidad (<strong>Productos</strong>, <strong>Catálogos</strong>, etc.) vinculando una imagen desde la galería y cargando una imagen desde el escritorio.</li>
<li>Optimice las imágenes para miniatura, tamaño personalizado y original.</li>
<li>Vincule de forma masiva entidades mediante una plantilla y trabajos en segundo plano para hacer asociaciones masivas.</li>
<li>La integración de Microsoft Excel sobrescribe la limitación del grupo de atributos de las convenciones de nomenclatura y las rutas predefinidas.</li>
<li>Admita imágenes sin conexión e imágenes seguras para el contenido de información personalmente identificable (PII), como imágenes de clientes y empleados alojadas en Retail.</li>
</ul></td>
<td><ul>
<li>Aborda puntos débiles en las imágenes alojadas externamente, de modo que pueda evitar ir adelante y atrás y en su lugar gestionarlo todo en un único lugar.</li>
<li>Proporciona una potente gestión de contenidos a través de la galería multimedia para imágenes cargadas y recibidas externamente, y también proporciona filtrado para ayudarle a encontrar imágenes.</li>
<li>Permite crear fácilmente asociaciones de forma masiva entre las imágenes y las entidades alojadas externamente como productos y catálogos.</li>
<li>Admite el almacenamiento de imágenes alojado en Retail y la integración de Excel para fáciles actualizaciones.</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="rich-clientele-experience"></a>Rica experiencia de la clientela

Retail ofrece experiencias móviles inmersivas en cualquier lugar, en cualquier momento y en cualquier dispositivo. Esta funcionalidad permite disfrutar de experiencias mejoradas de compra y en la tienda en todos los canales.

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Busque, navegue o escanee productos, agregue productos a un carro, acepte pagos y registre su salida mediante una experiencia de usuario intuitiva, táctil, rica e inmersiva en MPOS.</td>
<td>AX 2012 habilita las siguientes características:
<ul>
<li>Realizar ventas, devoluciones y anulaciones.</li>
<li>Crear, modificar y seleccionar pedidos del cliente.</li>
<li>Realizar operaciones de caja registradora y de turno.</li>
<li>Seleccionar y recibir pedidos, y realizar recuentos de existencias.</li>
<li>Ver informes de la tienda.</li>
</ul></td>
<td>Se proporciona paridad funcional con AX 2012 MPOS. Esto incluye la siguiente funcionalidad:
<ul>
<li>Búsqueda de clientes en tiendas y canales.</li>
<li>Capacidad para crear pedidos de cliente sin obtener acceso a Real-time Service.</li>
<li>Activación de dispositivos mejorada y mensajes de error y estado.</li>
<li>Mejoras en extensibilidad, como activadores prerregistro y soporte de actividades para mejorar la personalización.</li>
</ul></td>
<td>El personal de ventas puede procesar las transacciones de venta y los pedidos de cliente, así como realizar operaciones diarias y gestionar inventarios mediante dispositivos móviles en cualquier lugar de la tienda.</td>
</tr>
<tr>
<td>Iniciar el PDV como aplicación web a través de Cloud POS.</td>
<td>No disponible</td>
<td>Se proporciona paridad funcional con MPOS. Esto incluye la siguiente funcionalidad:
<ul>
<li>Activación de dispositivos mediante AAD.</li>
<li>Diseño con capacidad de respuesta.</li>
<li>Compatibilidad con exploradores Edge, Internet Explorer y Chrome.</li>
</ul></td>
<td>Proporciona un PDV mediante aplicación web con funcionalidad compatible con MPOS y que se puede usar en todas las plataformas y los exploradores sin ningún coste de implementación.</td>
</tr>
<tr>
<td>Se integra con sistemas de gestión de contenidos para crear un sitio web de comercio electrónico en todos los canales.</td>
<td>Se admite Microsoft SharePoint y escaparates de terceros.</td>
<td>Se proporciona una plataforma de comercio electrónico compatible con escaparates de terceros. La plataforma incluye las siguientes características:
<ul>
<li>Una rica API de usuario.</li>
<li>Integración de autenticación con proveedores terceros de identificación abierta.</li>
<li>Integración de pagos.</li>
</ul></td>
<td>Los clientes ahora tienen la flexibilidad de usar el sistema de gestión de contenidos que elijan.</td>
</tr>
<tr>
<td>Llegue a los clientes a través de catálogos de venta por correo y racionalice las operaciones mediante una rápida introducción de pedidos, venta asistida y cumplimiento por medio del centro de llamadas.</td>
<td><ul>
<li>Canal de centro de llamadas.</li>
<li>Catálogos de venta por correo.</li>
<li>Introducción de pedidos rápida y venta asistida.</li>
<li>Satisfacción de pedidos mejorada.</li>
<li>Servicio al cliente</li>
<li>Precios y promociones o descuentos integrados.</li>
</ul></td>
<td>Paridad de funciones con la solución de centro de llamadas de AX 2012 disponible, excepto para anulaciones de precios.</td>
<td>Los centros de llamadas son un tipo de canal de venta minorista que permiten a los trabajadores tomar pedidos de clientes por teléfono y crear pedidos de ventas.</td>
</tr>
</tbody>
</table>

### <a name="commerce-essentials"></a>Conceptos básicos de Commerce

Una opción de configuración centrada en la venta minorista y el comercio ayuda a agilizar las implementaciones específicas de la venta al por menor.

| ¿Qué se puede hacer? | Dynamics AX 2012 | Dynamics AX 7.0 | ¿Por qué esto es importante? |
|------------------|------------------|-----------------|------------------------|
| Use el panel de información de Commerce essentials. | Dispone de una página de área con vínculos a elementos de menú. | El panel de información de conceptos básicos de Commerce ofrece vínculos a tareas frecuentes, como vínculos a espacios de trabajo, el control web de Power BI, favoritos, páginas recientes y elementos de trabajo actual. | El panel de información mejorado aporta capacidad a los trabajadores haciéndolos más eficaces y proporcionando un punto de partida flexible para cualquier tarea de venta al por menor. |
| Use entidades de datos para acceder a cambios de cuenta. | Los cambios de cuenta se exportan a una carpeta en el sistema de archivos. | Los cambios de cuenta son accesibles a través de entidades de datos. | Esta función proporciona una mayor flexibilidad al transferir datos entre sistemas dispares. Esta función se puede mejorar con aplicaciones OData también. |
| Use Cloud POS y MPOS. | Desde el inicio solo se admite Enterprise POS (EPOS). | MPOS y Cloud POS sustituyen al cliente EPOS. El canal de comercio electrónico también se ha agregado a Commerce essentials de forma predeterminada. | Esta función permite disfrutar de más compatibilidad de canal desde el inicio con clientes de punto de venta rápidamente desplegables. |
| Implemente y mantenga una arquitectura de dos niveles. | El marco de importación o exportación de datos proporciona la capacidad de mover datos entre AX 2012 y sistemas de terceros. | Entidades de datos creadas para mejorar la compatibilidad para arquitecturas de dos niveles. | Las entidades de datos y las aplicaciones OData proporcionan una capa de abstracción para que los escenarios de dos niveles sean más fáciles de implementar y mantener. |
| Simplifique los formularios. | Se requieren códigos personalizados para simplificar la interfaz de usuario. | Las extensiones de menús y formularios proporcionan una simplificación estandarizada de la interfaz de usuario. | Esta función proporciona una forma más rápida y más fácil de ajustar los formularios basados en las necesidades del minorista. |

### <a name="pos-task-recorder"></a>Grabador de tareas de PDV

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Cree y comparta guías de tareas y documentos para Modern POS.</td>
<td>No disponible</td>
<td>El grabador de tareas de MPOS admite las siguientes características:
<ul>
<li>Cree grabaciones de tareas para varias tareas realizadas en MPOS.</li>
<li>Genere un documento que incluya pasos y capturas de pantalla, y asócielo a un nodo en el modelo del proceso empresarial.</li>
</ul></td>
<td>Los socios y los fabricantes de software independiente (ISV) pueden personalizar MPOS y proporcionar documentos de apoyo para formar a sus usuarios.</td>
</tr>
</tbody>
</table>

### <a name="extensibility"></a>Extensibilidad

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Admita componentes de Retail extensibles y fácilmente desplegables a través de HQ, el centro de llamadas, comercio electrónico y el PDV.</td>
<td>Los componentes se pueden extender mediante el SDK de Retail. No se dispone de capacidades de empaquetado e implementación.</td>
<td>Los ganchos de extensibilidad han mejorado en los distintos componentes para admitir mejor el aislamiento y la capacidad de servicio del código. Estas son algunas de las funciones incluidas:
<ul>
<li>Flujo de trabajo, actividad y operación.</li>
<li>Preactivadores y postactivadores que permiten extender fácilmente un flujo de trabajo.</li>
<li>Activadores de aplicaciones y operaciones.</li>
</ul>
Además, dispone de un marco que le permite crear y empaquetar estos componentes mediante MSBuild y, a continuación, implementar sin problemas su personalización con Microsoft Dynamics Lifecycle Services (LCS).</td>
<td>Los minoristas tienen requisitos muy específicos, según verticales y geografías de operación. Al ofrecer una plataforma fácilmente extensible, permitimos su uso en todos los verticales y mercados. Dado que Retail también tiene una arquitectura muy distribuida, la capacidad de implementarse fluidamente aumenta enormemente la productividad.</td>
</tr>
</tbody>
</table>

### <a name="lifecycle-management"></a>Administración del ciclo de vida

Lifecycle Services (LCS) ofrece un conjunto de servicios que los clientes y los socios pueden usar para gestionar el ciclo de vida del sistema, desde la inscripción en los servicios a las operaciones diarias.

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Gestione el programa mediante servicios de implementación en la nube.</td>
<td>No disponible</td>
<td>Las topologías siguientes se pueden implementar a la nube:
<ul>
<li>Topología de prueba de Retail para una caja.</li>
<li>Topología de gran disponibilidad de Retail para varias cajas.</li>
<li>Topología de desarrollador con SDK de Retail.</li>
</ul>
Hay una instalación mejorada del componente de cliente de “baja participación” a través de la instalación de autoservicio:
<ul>
<li>Retail Modern POS.</li>
<li>Retail Hardware Station.</li>
<li>Ayuda para la carga y distribución de paquetes personalizados a través de la instalación de autoservicio.</li>
</ul></td>
<td>Los servicios de implementación en la nube proporcionan las prestaciones siguientes:
<ul>
<li>Esfuerzo de implementación y complejidad significativamente menores para componentes de Retail HQ.</li>
<li>Implementación nativa en la nube pública de Microsoft Azure.</li>
<li>Instalación de autoservicio mejorada de los componentes en la tienda para facilitar la configuración y hacerla más intuitiva.</li>
</ul></td>
</tr>
<tr>
<td>Supervise el estado del sistema y diagnostique errores y problemas.</td>
<td>Esta función requiere el <a href="http://www.microsoft.com/download/details.aspx?id=42636">paquete de System Center 2012 Management para Microsoft Dynamics AX 2012 R3 CU8 Retail</a>.</td>
<td>Dispone ahora de supervisión y diagnóstico de componentes de Retail a través del panel de información <strong>Detalles de funcionamiento</strong> en LCS.</td>
<td>El panel de información <strong>Detalles de funcionamiento</strong> es un portal de supervisión basado en la nube que sustituye la necesidad de instalar la infraestructura de System Center Operations Manager (SCOM).</td>
</tr>
<tr>
<td>Cree, configure, descargue e instale la estación de hardware para Retail y dispositivos mediante autoservicio.</td>
<td>Al usar el empaquetador de instalación y Enterprise Portal, el usuario puede realizar una instalación y una configuración automatizadas de todos los componentes que se requieren en un equipo concreto, en función de un topología definida.</td>
<td>Dado que solo hay dos paquetes de instalación, uno para el cliente MPOS y el otro para el componente de estación de hardware de Retail, el autoservicio ha reducido la cantidad de trabajo requerida en todos los niveles para instalar estos componentes de cliente.</td>
<td>El autoservicio pretende minimizar los requisitos y facilitar al usuario la instalación.</td>
</tr>
</tbody>
</table>

## <a name="sales"></a>Ventas

<table>
<thead>
<tr>
<th>¿Qué se puede hacer?</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>¿Por qué esto es importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Obtenga una visión general rápida de las alternativas de entrega cuando prometa pedidos a los clientes.</td>
<td>Cuando hay restricciones de disponibilidad de producto y la fecha de entrega solicitada por el cliente para uno o varios productos del pedido no se puede satisfacer, la tarea de garantización del pedido se convierte en un reto. Para encontrar alternativas que pueden compensar los problemas de disponibilidad y tiempos de envío para poder cumplir con la fecha solicitada por el cliente, o proporcionar a los clientes una solución de entrega que pueden aceptar y de confianza, el procesador del pedido puede tener que abrir varios formularios, cada uno de los cuales ofrece solo un subconjunto de la información necesaria. Más concretamente, un formulario muestra la cantidad disponible en todos los sitios, otro formulario muestra la cantidad disponible en las empresas vinculadas, un tercer formulario permite a los usuarios calcular la fecha disponible más temprana para un sitio o una variante a la vez, y un cuarto muestra los pedidos de suministro. Por lo tanto, los usuarios no se sienten seguros de haber tenido en cuenta todas las opciones relevantes en lugar de elegir una solución inmediata pero por debajo de la óptima. Los usuarios tampoco se sienten efectivos, ya que se producen numerosas interrupciones durante el flujo de garantización del pedido a medida que abren y cierran varias páginas, y combinan la información y las opciones.</td>
<td>De acuerdo con los algoritmos existentes para el cálculo de la fecha de entrega, la página <strong>Alternativas de entrega </strong>ofrece una nueva experiencia de usuario para la garantización de pedidos:
<ul>
<li>Consolida la información pertinente desde varios formularios en un espacio.</li>
<li>Ofrece paquetes de entrega alternativos “preconfeccionados”, como un modo combinado de sitio/almacén/variante/transporte, en función del criterio de entrega más rápida (la fecha disponible más temprana) que el usuario puede elegir.</li>
<li>Permite al usuario seleccionar opciones de la interfaz de simulación y transferirlas a la línea del pedido de ventas.</li>
</ul></td>
<td>Las empresas que aspiran a proporcionar un elevado servicio al cliente comprometiéndose con una estrategia de optimización de inventario deben poder garantizar pedidos de forma fiable y competitiva. Después de todo, el propio negocio de sus clientes requiere que los productos estén disponibles a tiempo. La página de tarea <strong>Alternativas de entrega</strong> acelera la tarea de garantización del pedido, así como la hace más fácil y más sistemática identificando y recomendando las fechas de entrega alternativas mejores para el pedido en un lugar interactivo.</td>
</tr>
</tbody>
</table>

## <a name="service-management"></a>Gestión de servicios

No se han agregado funciones nuevas.

## <a name="transportation-management"></a>Administración de transporte

No se han agregado funciones nuevas.

## <a name="travel-and-expense"></a>Viajes y gastos

No se han agregado funciones nuevas.

## <a name="warehouse-management"></a>Administración de almacenes

| ¿Qué se puede hacer? | Dynamics AX 2012 | Dynamics AX 7.0 | ¿Por qué esto es importante? |
|------------------|------------------|-----------------|------------------------|
| Descargue, instale y configure el portal de dispositivos móviles de almacén. | Puede descargar, instalar y configurar el portal durante el proceso de instalación de Microsoft Dynamics AX, a través de una configuración estándar. Se ha diseñado para una implementación y configuración propias de manera local. | Puede descargar un instalador independiente a través de un elemento de menú en la gestión de almacenes. Se ha diseñado para una implementación y configuración propias de manera local. | Cuando configure la funcionalidad de dispositivo móvil, debe instalar y configurar el portal de dispositivos móviles de almacén de forma local y conectar con Dynamics AX en la nube. |

## <a name="additional-resources"></a>Recursos adicionales

[Novedades y cambios](whats-new-changed.md)

[Nuevas guías de tareas disponibles (febrero de 2016)](new-task-guides-available-february-2016.md)
