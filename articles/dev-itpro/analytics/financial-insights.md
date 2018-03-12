---
title: Financial Insights
description: "Financial Insights utiliza Microsoft Power BI para reunir los indicadores clave de rendimiento financieros (KPI), los gráficos y los informes financieros."
author: kweekley
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 8075abccdcdde21df967dcc9948a738895f35cef
ms.openlocfilehash: 3da5344ec6edec0af28aa21d45af962307231e67
ms.contentlocale: es-es
ms.lasthandoff: 01/25/2018

---

# <a name="financial-insights"></a>Financial Insights

[!include[banner](../includes/banner.md)]

**Financial Insights** utiliza Microsoft Power BI para reunir los indicadores clave de rendimiento financieros (KPI), los gráficos y los informes financieros. Power BI está incrustado en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.
El enfoque de **Financial Insights** es un informe analítico. Las personas de una organización pueden ver, investigar, entender y actuar. 

**Financial Insights** combina datos de la contabilidad general y las auxiliares para dar una imagen más completa del estado financiero de una organización.

> [!NOTE] 
> Este documento utiliza la siguiente terminología de Power BI:                                                                           
**Informe**: un único archivo .pbix en el que se guardan todos los elementos visuales en todas las pestañas.                                                          
**Página**: una pestaña en un único archivo .pbix. Cada página puede contener uno o más elementos visuales.                                                     
**Elemento visual**: una única fuente de datos, como una tarjeta, un KPI, un gráfico, una matriz o un informe financiero. Una página que tiene un informe financiero como un elemento visual no puede tener otros elementos visuales debido al tamaño de los datos que se están notificando.


Actualmente, **Financial Insights** se emplea para ver los datos de la entidad jurídica activa o de todas las entidades jurídicas. En versiones futuras, el espacio de trabajo evolucionará hasta convertirse en el lugar en el que puede usar Power BI para editar y crear elementos visuales.

El espacio de trabajo **Visión general de director financiero (CFO)** muestra los mismos elementos visuales que la **Financial Insights**, pero se centra en permitirle visualizar y filtrar los datos en informes existentes. En versiones futuras, podrá agregar nuevos elementos visuales al espacio de trabajo **Financial Insights** . Los nuevos elementos visuales también pueden estar disponibles en espacios de trabajo que se centran en otros roles, como gestores de proyectos o administradores de proveedores. El espacio de trabajo **Visión general de director financiero (CFO)** sigue mostrando los datos de todas las entidades jurídicas, independientemente de las entidades jurídicas a las que el rol tiene acceso.

## <a name="finance-and-operations-setup"></a>Configuración en Finance and Operations
**Contabilidad general**

El tipo de cuenta principal y las categorías de cuenta principal se emplean para rellenar las cuentas principales predeterminadas adecuadas en el informe financiero **Balance de situación** y los distintos informes financieros **Informe de ingresos** en **Infomación financiera**.

En la página **Cuentas principales**, debe definir la cuenta principal para que se le asigne uno de los siguientes tipos:

•   Ingreso

•   Gasto

•   Activos

•   Pasivos

•   Recursos propios

No asigne ningún otro tipo de cuenta principal, como **Balance de situación** o **Pérdidas y ganancias** a sus cuentas principales. El informe no puede determinar el tipo de cuenta principal cuando se asignan otros tipos de cuenta principal, ya que no son lo suficientemente granulares. Debe determinarse el tipo de cuenta principal para mostrar pasivos e ingresos como importes positivos en informes financieros.

Para que aparezca en los informes financieros y ser incluida en distintos elementos visuales, como los KPI, cada cuenta principal se debe asignar una categoría de cuenta principal. Se han ampliado las categorías de cuenta principal para que incluyan un orden de visualización. El orden de visualización se utiliza específicamente en informes financieros en **Financial Insights**. Tras editar o agregar una nueva categoría de cuenta principal, puede cambiar el valor **Orden de visualización** para definir el orden en que se deben mostrar las categorías de cuenta principal en un informe financiero. Si debe cambiar el orden de visualización para muchas categorías de cuenta principal, puede usar la función Abrir en Excel para volver a editar y publicar rápidamente los cambios en Finance and Operations.


## <a name="entity-store"></a>Almacén de entidades
Los datos para **Financial Insights** se extraen del almacén de entidades (**Administración del sistema** > **Configuración** > **Almacén de entidades**). Si abre el espacio de trabajo **Visión general de director financiero (CFO)** o **Financial Insights** y aparece el siguiente mensaje de advertencia en los elementos visuales, debe actualizar las entidades.
 
![Advertencia](./media/Cantdisplay.png)

Debe actualizar las siguientes entidades para ver datos en los espacios de trabajo **Financial Insights** y **Visión general de director financiero (CFO)**:

•   CustCollectionsBIMeasurements

•   FinancialReportingOtherData

•   FinancialReportingReferenceData

•   FinancialReportingTransactionData

•   LedgerCovLiquidityMeasurement

•   Cubo de compra

•   Cubo de venta

En la versión anterior, las entidades LedgerActivityMeasure y VendPaymentBIMeasure se utilizaron para los datos en el espacio de trabajo **Visión general de director financiero (CFO)** . Sin embargo, ya no se emplean en la versión actual.

Puede definir un lote periódico para actualizar con frecuencia los datos en las entidades. Puesto que cada entidad se reconstruye por completo durante una actualización, seleccione cuidadosamente la hora y la frecuencia de las actualizaciones de entidades. La entidad principal que se emplea para informes financieros es la entidad FinancialReportingTransactionData. Por lo tanto, puede que decida actualizar dicha entidad con mayor frecuencia.

## <a name="security"></a>Seguridad
Actualmente, los datos en informes incrustados de Power BI no pueden limitarse a las entidades jurídicas a las que tiene acceso el usuario. Por lo tanto, los informes incrustados de Power BI se controlan a través de derechos en la configuración de seguridad. Los derechos que se definen permiten el acceso a los datos a todas las entidades jurídicas o solo a la empresa activa. La tabla siguiente muestra los derechos que existen y los roles a los que están asignados. Los derechos se pueden quitar o asignar a distintos roles en función de los requisitos de su organización.

| **Deber**                     | **Roles**                                       | Descripción                     |
|------------------------------|-------------------------------------------------|-----------------|
| Ver espacio de trabajo de la visión general del director financiero  | Director financiero                         | •    Este derecho proporciona acceso al espacio de trabajo de la visión general de director financiero (CFO). •  De forma predeterminada, la empresa activa se usa como filtro. Sin embargo, puede agregar todas las entidades jurídicas, independientemente de si el usuario tiene acceso a otras entidades jurídicas.               |
| Ver información financiera de la empresa actual | •   Contable •    Administrador contable •    Supervisor contable • Auditor •   Administrador presupuestario •    Director general •   Director financiero •   Controlador financiero  |   • Este derecho proporciona acceso a Financial Insights. •  De forma predeterminada, la empresa activa se usa como filtro. No puede agregar otras entidades jurídicas.            |
| Ver información financiera entre empresas   | •   En Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, este derecho no se asigna a un rol. • En la siguiente versión, este derecho se asignará al rol del director financiero. | •    Este derecho proporciona acceso al elemento del menú para el espacio de trabajo de la visión general de director financiero (CFO). •    De forma predeterminada, la empresa activa se usa como filtro. Sin embargo, puede agregar todas las entidades jurídicas, independientemente de si el usuario tiene acceso a otras entidades jurídicas.             |


## <a name="how-financial-statements-work"></a>Cómo funcionan los informes financieros
Aunque **Financial Insights** contiene informes financieros, no es una sustitución del informe financiero en Finance and Operations. Los informes financieros predeterminados en **Financial Insights** tienen un alcance limitado y no incluyen todos los tipos de informes financieros. El informe financiero sigue siendo la herramienta principal para diseñar, crear y generar informes financieros estatutarios.

Además de los elementos visuales del espacio de trabajo original **Visión general de director financiero (CFO)**, ahora están disponibles nuevos KPI, gráficos e informes financieros. Están disponibles los siguientes informes financieros:

•   Saldo de comprobación

•   Balance de situación

•   Informe de ingresos por región

•   Informe de ingresos real freten a presupuesto

•   Informe de ingresos con desviaciones

•   Informe de ingresos de tendencias de 12 meses

•   Tendencia de tres años de gastos

•   Gastos por proveedor

•   Ventas por cliente

## <a name="edit-visuals"></a>Editar elementos visuales
En la versión inicial **Financial Insights**, no se puede editar ninguno de los elementos visuales. En versiones futuras, los usuarios que dispongan de la seguridad adecuada podrán crear nuevos elementos visuales, copiar elementos visuales existentes y editar elementos visuales. Aunque los archivos .pbix que contienen los informes están disponibles como recursos, no se recomienda editar los informes predeterminados. Se harán cambios adicionales en el modelo de datos, los informes predeterminados y el elemento visual del informe financiero personalizado que se utilizan para crear los informes financieros. Por lo tanto, para aprovechar las nuevas funciones y cambios en el modelo de datos en el siguiente versión, tendrá que volver a realizar los cambios que hizo en los informes predeterminados mediante Microsoft Power BI Desktop.


## <a name="filtering"></a>Filtrado
Los usuarios pueden filtrar el informe mediante el panel **Filtro** a la izquierda. Este panel es el mismo panel que está disponible mediante Power BI Desktop.
Existen varios niveles de filtrado, algunos pueden no estar disponibles, en función de lo que haya seleccionado en una página (pestaña) o de si usa las capacidades de exploración:

•   **Filtros a nivel de informe:** estos filtros se aplican a todos los elementos visuales en todas las páginas (pestañas).

•   **Filtros a nivel de página:** estos filtros se aplican a todos los elementos visuales en la pestaña activa. Estos filtros se aplican encima de los filtros a nivel de informe.

•   **Filtros a nivel visual:** estos filtros solo se aplican al elemento visual seleccionado. Estos filtros se aplican encima de los filtros a nivel de página.

•   **Filtro de exploración:** este filtro filtra desde un elemento visual "de origen" que se aplica al elemento visual actual cuando se explora del elemento visual de origen al elemento visual actual.

![Filtrar](./media/filter.png)


Para quitar un valor específico de filtro, seleccione el símbolo de la goma situado junto a él. No quite un filtro seleccionando la X. Si selecciona la X, el campo sobre el que se está filtrando se quita como opción de filtro. Si quita accidentalmente un campo del filtro, cierre el espacio de trabajo y, a continuación, vuelva a abrirlo. Los parámetros de filtro predeterminado se volverán a aplicar.

De forma predeterminada, cuando abre espacios de trabajo por primera vez, la entidad jurídica activa se utiliza como filtro a nivel de informe. En función de su seguridad, los usuarios puede agregar otras entidades jurídicas o cambiar la entidad jurídica predeterminada que está seleccionada en el filtro.

Se requiere el filtro **Calendario fiscal** para usar el calendario correcto para el elemento visual. De forma predeterminada, el filtro a nivel de informe se establece para el calendario fiscal de la entidad jurídica activa. Si cambia el filtro a un calendario fiscal con otra fecha de inicio o fin, los saldos iniciales no se incluirán. Por lo tanto, los informes financieros **Balance de situación** no mostrarán los saldos correctos. Si selecciona un calendario fiscal adicional en el filtro, tendrá un conjunto adicional de columnas. Cada conjunto adicional de columnas muestra los importes para otro calendario fiscal.

También se requiere el filtro **Capa de registro**. De forma predeterminada, el filtro se establece en Actual. Puede seleccionar las capas de registro adicionales en el filtro para mostrar los importes agregados.

Los filtros también están disponibles para los campos **Fecha** y **Ejercicio**. Normalmente, estos filtros se aplican a nivel de página. De forma predeterminada, el filtro **Fecha** usa una fecha relacional que puede cambiar. También puede quitar el filtro relacional de fecha y usar el filtro **Ejercicio** en su lugar.

## <a name="currency"></a>Divisa

Todos los elementos visuales que informan de datos de contabilidad general muestran importes en la divisa de contabilidad. Por lo tanto, cuando filtra en la entidad jurídica, debe tener cuidado de incluir solo las entidades jurídicas que tienen la misma divisa de contabilidad. De lo contrario, agregará datos en diferentes divisas.

Todos los elementos visuales que informan sobre datos de subdiario contable, como los elementos visuales **Previsión de flujo de efectivo** y **Los 10 mejores** , muestran importes en la divisa del sistema. La divisa del sistema y el tipo de cambio del sistema se definen en la página **Parámetros del sistema**.

El elemento visual **Saldo por cuenta bancaria** emplea importes en la divisa de las cuentas bancarias.

## <a name="dimensions"></a>Dimensiones

Los informes financieros predeterminados no incluyen ninguna dimensión financiera pero se centran únicamente en la cuenta principal. La compatibilidad para las dimensiones financieras estará disponible en versiones futuras, cuando los informes pasen a ser editables. Posteriormente, las organizaciones podrán filtrar por valores de dimensión financiera.

Algunos informes financieros contienen dimensiones que se basan en transacciones del subdiario contable. El objetivo de los nuevos informes financieros es habilitar el filtrado en dimensioens que no están configuradas como dimensiones financieras. Por ejemplo, los gastos predeterminados por informe del proveedor le permiten expandir más allá de la cuenta principal, por lo que puede ver los saldos desglosados por el proveedor. El proveedor no está configurado como dimensión financiera. En su lugar, el sistema devuelve a la transacción de subdiario contable de origen para encontrar el proveedor.

Las siguientes dimensiones se utilizan en los informes predeterminados. Ninguna de estas dimensiones son dimensiones financieras.

•   Proveedor

•   Grupo de proveedores

•   Cliente

•   Grupo de clientes

•   País/región

•   Estado/provincia

•   Ciudad

> [!IMPORTANT] 
> Si resume las transacciones para varios proveedores o clientes en un único asiento mediante los diarios financieros, los datos serán incorrectos. Los informes no pueden determinar qué proveedor o cliente está relacionado con una cuenta contable específica en un movimiento de diario, dado que la información no se mantiene en ningún lugar. Por lo tanto, no se recomienda introducir varios proveedores, clientes, activos fijos o proyectos en un único asiento.

## <a name="drill-on-data"></a>Explorar en datos

Los distintos niveles de exploración están disponibles mediante Power BI. Cada nivel tiene un nombre y una funcionalidad diferentes. También puede explorar en filas y columnas. Esta sección trata las distintas opciones al usar el informe financiero **Saldo de comprobación** como un ejemplo y mostrando cómo puede explorar en las filas. La misma funcionalidad existe para las columnas. Solo tiene que cambiar la configuración **Explorar en**.

En la siguiente ilustración, el informe **Saldo de comprobación** se contrae al máximo nivel de la jerarquía de la fila, el tipo de cuenta principal.

![Saldo de comprobación](./media/trial-balance.png)

 
Para ver el siguiente nivel de la jerarquía, las categorías de cuenta principal, puede establecer el campo **Explorar en** para **Filas** y luego seleccionar el botón **Expandir** (el tercer botón después del campo Explorar en). Ahora verá todas las categorías de cuenta principal ampliadas. Actualmente, Power BI no le permite expandir una sola fila o columna pero puede seguir viendo el resto de filas o columnas.
 
![Saldo de comprobación](./media/trial-balance2.png)
 
  
Para ampliar a la cuenta principal para todas las filas, puede volver a utilizar el botón **Expandir** . Sin embargo, para explorar a fondo las cuentas principales para una sola fila, seleccione primero el botón **Explorar a fondo** (una sola flecha apuntando hacia abajo a la derecha de la ventana) y luego seleccione la fila que desea explorar a fondo. La siguiente ilustración muestra el resultado cuando se selecciona la fila **Ventas** después de que se seleccione el botón **Explorar a fondo** .

![Saldo de comprobación](./media/trial-balance3.png)

Tras explorar a fondo una sola fila, se requieren múltiples clics para volver al saldo de comprobación completo. El botón **Explorar a fondo** (el primer botón después del campo **Explorar en**) explora a fondo solo en el contexto de la categoría **Ventas**, como se muestra en la siguiente ilustración.
 
![Saldo de comprobación](./media/trial-balance4.png)
 
 
Puede seguir usando el botón **Explorar a fondo** para volver al máximo nivel de resumen de las filas.

Power BI también dispone de un botón que le permite ir al siguiente nivel de la jerarquía (el segundo botón después del campo **Explorar en**). El efecto de este botón es diferente al efecto del botón **Expandir** (el tercer botón después del campo **Explorar en** ), que se utiliza para expandir la jerarquía. Cuando expanda la jerarquía, la jerarquía se mantiene en el informe. Por ejemplo, como se mostró anteriormente, si expande en el tipo de cuenta principal, todavía puede ver el tipo de cuenta principal en el informe. Sin embargo, cuando va al siguiente nivel de la jerarquía, el informe ya no muestra la principal en la jerarquía, como se muestra en la siguiente ilustración.

![Saldo de comprobación](./media/trial-balance5.png)

 
Para ver los detalles de transacción detrás de los saldos resumidos, puede seleccionar algunas importes para volver a explorar en Finance and Operations.

La exploración inversa desde los informes financieros le lleva al Explorador de origen de contabilidad (ASE), no a las transacciones de asiento. El ASE no muestra solo los asientos contables en la contabilidad general. En su lugar, se muestran los detalles de la transacción de subdiario contable. Por lo tanto, obtiene mucho más detalle acerca de la transacción de origen y puede utilizarla para el análisis. Por ejemplo, puede consultar quién era el proveedor o cliente, qué compró el cliente o que vendió el proveedor, e incluso qué proyecto figuraba en la transacción.

Los filtros siguientes de los informes financieros se envían al ASE, de modo que el ASE muestra las transacciones que se agregan:

Campos necesarios para filtrar:

  - Entidad jurídica
 
  - Calendario fiscal
 
  - Año
 
  - Id. de la cuenta principal

Campos opcionales para filtrar:

  - Trimestre

  - Mes

  - Período

Si no expande lo suficiente una fila, la exploración no funciona. Por ejemplo, si expande solo a la categoría de cuenta principal, no podrá explorar a fondo el ASE en el saldo, ya que la cuenta principal es un campo obligatorio para filtrar el ASE.

Si expande demasiado una fila, los filtros adicionales en los informes financieros no se envían al ASE. Por lo tanto, puede que vea una diferencia en sus números. Por ejemplo, si expande al país o la región en las filas del Informe de ingresos por informe financiero de la región, el país o región no se incluye como filtro en el ASE.

> [!NOTE]
> Puede explorar aún más las filas o columnas del informe financiero de lo que el ASE admite actualmente para el filtrado. Por tanto, en algunos casos, la suma de transacciones detalladas del ASE no coincidirá con el saldo que está volviendo a explorar. Esta funcionalidad se seguirá mejorando en el futuro.

## <a name="hierarchies"></a>Jerarquías

Los informes financieros predeterminados utilizan dos jerarquías para explorar y expandir los datos. Una jerarquía es para las filas y la otra jerarquía es para las columnas. Ambas jerarquías están predefinidas en el diseño del informe financiero. Para la mayoría de informes financieros, la jerarquía de la fila es **Tipo de cuenta principal** > **Categorías de cuenta principal** > **Cuenta principal**. Sin embargo, algunos informes tienen campos adicionales, como País y Región. Los nodos adicionales de la jerarquía se basan en los datos del subdiario contable para cada transacción.

Para las columnas, la jerarquía se centra en las entidades jurídicas y los períodos fiscales. Para la mayoría de los informes financieros, la jerarquía de la columna es **Entidad jurídica** > **Calendario fiscal** > **Ejercicio** > **Trimestre** > **Período**.

Actualmente, los informes financieros no admiten las jerarquías organizativas, lo que le permite agregar datos.

## <a name="data-limitations"></a>Limitaciones de datos
Los elementos visuales del informe financiero tienen un límite en el número de filas que se pueden mostrar. Actualmente, el límite se establece en 30 000. Si supera este límite, el elemento visual tendrá un símbolo de advertencia para notificarle sobre esta situación.
 
![Limitaciones de datos](./media/data-limit.png)


Si se supera el máximo, los totales que aparecen en el informe financiero serán incorrectos, ya que no se cargaron todas las filas en el elemento visual.

### <a name="empty-rows"></a>Filas vacías
Power BI no proporciona una opción para ocultar o mostrar filas vacías. Si una fila no tiene datos, la fila no aparecerá en el elemento visual.

## <a name="what-is-coming-in-future-releases"></a>¿Qué vendrá en versiones futuras?
Seguirán mejorándose los nuevos espacios de trabajo e informes financieros que usa Power BI. Estas son algunas de las nuevas funciones que se están considerando para las versiones futuras:

 - La capacidad de copiar, editar, eliminar y crear elementos visuales, incluso los informes financieros                                                  
 - Informes predeterminados adicionales                                                                                                            
    - Soporte para datos adicionales de subdiario contable                                                                                            
 - Soporte para una divisa de notificación                                                                                                      
 - Añadir cálculos personalizados para filas y columnas                                                                                          
 - La capacidad de exportar los informes financieros a Microsoft Excel                                                                     
   - Mantener el formato del informe financiero durante la exportación.                                                                          
   - Analizar datos en Excel al crear una tabla dinámica que use la información en el elemento visual.                                              
 - Soporte local                                                                                                                        
 - La capacidad de definir jerarquías de informes, de modo que pueda definir las jerarquías de la cuenta principal o una jerarquía organizativa que se pueden usar en informes financieros para el diseño, el filtrado y la seguridad.                                                                    
 - Soporte para impresión

Las nuevas funciones se comunicarán a través de la página web de la guía básica a medida que se inicie el trabajo: https://roadmap.dynamics.com/.

## <a name="additional-resources-for-power-bi"></a>Recursos adicionales para Power BI

No se requiere la información de los siguientes recursos para habilitar los informes incrustados para el espacio de trabajo **Visión general de director financiero (CFO)** o **Financial Insights** en un entorno de producción. En su lugar, son útiles para los cuadros de desarrollo y si desea incrustar sus propios informes de Power BI en Finance and Operations.

https://blogs.msdn.microsoft.com/dynamicsaxbi/2017/07/29/accessing-analytical-workspaces-on-1box-environment/

https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/add-analytics-tab-workspaces
