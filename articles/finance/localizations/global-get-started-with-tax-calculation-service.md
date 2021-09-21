---
title: Introducción al cálculo de impuestos
description: Este tema explica cómo configurar el cálculo de impuestos.
author: wangchen
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b180a8cee1c5b7e9dda837915e6fdf94af30d06a
ms.sourcegitcommit: 8246ba3872a1f3eaa18c8bb1ba86d3c2142a6e10
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2021
ms.locfileid: "7465086"
---
# <a name="get-started-with-tax-calculation"></a>Introducción al cálculo de impuestos

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tema proporciona información sobre cómo comenzar con el cálculo de impuestos. Le guía por los pasos de configuración en Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS), Dynamics 365 Finance y Dynamics 365 Supply Chain Management. A continuación, revisa el proceso común para utilizar las funcionalidades de cálculo de impuestos en las transacciones de Finance y Supply Chain Management.

La configuración consta de cuatro pasos principales:

1. En LCS, instale el complemento Cálculo de impuestos.
2. En RCS, configure la función de cálculo de impuestos. Esta configuración no es específica de una entidad jurídica. Se puede compartir entre entidades legales en Finance y Supply Chain Management.
3. En Finance y Supply Chain Management, configure los parámetros del cálculo de impuestos por entidad jurídica.
4. En Finance y Supply Chain Management, cree transacciones, como pedidos de venta, y utilice el cálculo de impuestos para determinar y calcular los impuestos.

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar los procedimientos de este tema, debe tener preparados los siguientes requisitos previos para cada tipo de entorno:

### <a name="for-a-production-environment"></a>Para un entorno de producción

Para un entorno de producción, se deben cumplir los siguientes requisitos previos:

- Debe tener acceso a su cuenta de LCS y haber implementado un proyecto de LCS que tenga un entorno de Nivel 2 (o superior) que ejecute la versión 10.0.21 de Dynamics 365 o una versión posterior.
- Debe crear un entorno de RCS para su organización y debe tener acceso a su cuenta. Para obtener más información sobre cómo crear un entorno de RCS, consulte [Información general de Regulatory Configuration Service](rcs-overview.md).
- Las siguientes funcionalidades deben estar activadas en el espacio de trabajo **Administración de características** de su entorno implementado de Finance o Supply Chain Management, según las necesidades de su negocio:

    - Servicio de cálculo de impuestos
    - Admitir varios números de registro de IVA
    - Impuesto en el pedido de transferencia

- Las siguientes funcionalidades deben estar activadas en el espacio de trabajo **Administración de características** de su entorno de RCS implementado.

    - Características de globalización

### <a name="for-a-test-environment-public-preview"></a>Para un entorno de prueba (versión preliminar pública)

Para un entorno de prueba, se deben cumplir los siguientes requisitos previos:

- Debe tener acceso a su cuenta de LCS y haber implementado un proyecto de LCS que tenga un entorno de Nivel 2 (o superior) que ejecute la versión 10.0.21 de Dynamics 365 o una versión posterior.
- Debe crear un entorno de RCS para su organización y debe tener acceso a su cuenta. Para obtener más información sobre cómo crear un entorno de RCS, consulte [Información general de Regulatory Configuration Service](rcs-overview.md).
- Debe haberse puesto en contacto con Microsoft, enviando un correo electrónico a <taxcalc@microsoft.com>, para habilitar la distribución de paquetes piloto en su entorno implementado de Finance o Supply Chain Management.
- Las siguientes funcionalidades deben estar activadas en el espacio de trabajo **Administración de características** de su entorno implementado de Finance o Supply Chain Management, según las necesidades de su negocio:

    - Servicio de cálculo de impuestos
    - Admitir varios números de registro de IVA
    - Impuesto en el pedido de transferencia

- Las siguientes funcionalidades deben estar activadas en el espacio de trabajo **Administración de características** de su entorno de RCS implementado.

    - Características de globalización

## <a name="set-up-tax-calculation-in-lcs"></a>Configurar el cálculo de impuestos en LCS

1. Iniciar sesión en [LCS](https://lcs.dynamics.com)
2. Complete la configuración para la integración de Microsoft Power Platform. Para obtener más información, consulte [Información general de complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Seleccione uno de sus entornos implementados y luego seleccione **Instalar un nuevo complemento**.
4. Seleccione **Cálculo de impuestos**.
5. Lea y acepte los términos y condiciones, y luego seleccione **Instalar**.

## <a name="set-up-tax-calculation-in-rcs"></a>Configurar el cálculo de impuestos en RCS

Los pasos de esta sección no están relacionados con una entidad jurídica específica. Debe completar este procedimiento solo una vez, y puede completarlo en cualquier entidad jurídica en RCS.

1. Inicie sesión en [RCS](https://marketing.configure.global.dynamics.com/).
2. En el área de trabajo **Informes electrónicos**, agregue un nuevo proveedor de configuración. Utilice el nombre de su empresa como el nombre del proveedor. Para obtener más información, consulte [Crear proveedores de la configuración y marcarlos como activos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Seleccione el proveedor de configuración que acaba de crear y luego seleccione **Establecer como activo**.
4. Seleccione el proveedor de configuración **Microsoft** y luego **Repositorios**.
5. En el campo **Tipo**, seleccione **Global**.
6. Seleccione **Abrir**.
7. Vaya a **Modelo de datos fiscales**, expanda el árbol de archivos y luego seleccione **Configuración fiscal**.
8. Seleccione la versión de configuración de impuestos correcta, según su versión de Finance, y después seleccione **Importar**.

    | Versión | Configuración de impuestos                       |
    | --------------- | --------------------------------------- |
    | 10.0.18         | Configuración de impuestos - Europa 30.12.82     |
    | 10.0.19         | Configuración de Cálculo de impuestos 36.38.193 |
    | 10.0.20         | Configuración de Cálculo de impuestos 40.43.208 |
    | 10.0.21         | Configuración de Cálculo de impuestos 40.46.212 |

9. En el espacio de trabajo **Características de globalización**, seleccione **Características**, elija el icono **Cálculo de impuestos** y finalmente **Agregar**.
10. Seleccione uno de los siguientes tipos de característica:

    - **Nueva caracteristica**: cree una configuración de característica con el contenido en blanco.
    - **Basada en una característica existente**: cree una función a partir de una función existente y copie el contenido de la configuración de la función existente.

11. Introduzca un nombre y una descripción de la característica, y luego seleccione **Crear característica**.

    Una vez creada la característica, se crea automáticamente una versión de borrador. Puede seleccionar **Obtener esta versión** para fusionar mediante cambio de base la versión de borrador en cualquier versión completada.

12. Seleccione la versión preliminar de la característica y luego elija **Editar**. Se rellena la página **Configuración de cálculo de impuestos**.
13. Seleccione **Crear configuración**. Debería ver la versión de configuración que importó en el paso 8.

    Microsoft proporciona una configuración de impuestos predeterminada para el cálculo de impuestos. Esta configuración cubre la mayoría de los requisitos de los comportamientos de cálculo de impuestos. Se actualizará en función de los comentarios del mercado. Si debe ampliar la configuración para cumplir requisitos específicos, consulte [Cómo construir extensiones en el servicio tributario](./tax-service-add-data-fields-tax-integration-by-extension.md) para obtener información sobre cómo generar y seleccionar su propia configuración de impuestos.

14. Después de seleccionar **Versión de configuración**, aparecen varias pestañas adicionales. Siga el orden que se muestra aquí para completar la configuración de pestañas obligatoria.

    **Configuración obligatoria**

    - **Códigos de impuestos**: mantener datos maestros para códigos de impuestos. Todos los códigos de impuestos que se crean en esta pestaña se sincronizan automáticamente con Finance al habilitar la versión actual.
    - **Grupo de impuestos**: definir los datos maestros del grupo de impuestos y los códigos de impuestos en el grupo.
    - **Grupo de impuestos de artículos**: definir los datos maestros del grupo de impuestos de artículos y los códigos de impuestos en el grupo.

    **Configuración opcional**

    - **Aplicabilidad del grupo de impuestos**: definir una matriz que determine el grupo de impuestos. Si ninguna regla de aplicabilidad de esta matriz coincide con el documento gravable de Dynamics 365, Cálculo de impuestos utiliza el valor predeterminado de la línea de documento gravable.
    - **Aplicabilidad del grupo de impuestos de artículos**: definir una matriz que determine el grupo de impuestos de artículos. Si ninguna regla de aplicabilidad de esta matriz coincide con el documento gravable de Dynamics 365, Cálculo de impuestos utiliza el valor predeterminado de la línea de documento gravable.
    - **Aplicabilidad del número de registro de impuestos del cliente**: si tiene varios números de registro de impuestos para un cliente, Cálculo de impuestos puede determinar automáticamente el número de registro de impuestos correcto. En la matriz de esta pestaña, defina las reglas que se deben utilizar para tomar la decisión. De lo contrario, Finance y Supply Chain Management continuarán usando el número de registro de impuestos predeterminado en los documentos imponibles para las transacciones de ventas.
    - **Aplicabilidad del número de registro de impuestos del proveedor**: si tiene varios números de registro de impuestos para un proveedor, Cálculo de impuestos puede determinar automáticamente el número de registro de impuestos correcto. En la matriz de esta pestaña, defina las reglas que se deben utilizar para tomar la decisión. De lo contrario, Finance y Supply Chain Management continuarán usando el número de registro de impuestos predeterminado en los documentos imponibles para las transacciones de compras.
    - **Aplicabilidad del código de lista**: determinar automáticamente el valor del campo **Código de lista** mediante reglas más flexibles y configurables. En la matriz de esta pestaña, defina las reglas que se deben utilizar para tomar la decisión. De lo contrario, Finance y Supply Chain Management continuarán usando el código predeterminado en los documentos imponibles para las transacciones de ventas.

14. En la pestaña **Códigos de impuestos**, seleccione **Agregar** e introduzca el código de impuestos y una descripción.
15. Seleccione **Componente de impuestos**. El componente de impuestos es un grupo de métodos de cálculo de impuestos que se definieron en la versión anterior de la configuración de impuestos seleccionada. Están disponibles los siguientes componentes de impuestos:

    - Por importe neto
    - Por importe bruto
    - Por cantidad
    - Por margen
    - Impuesto sobre impuesto

16. Seleccione **Guardar**. Hay más campos disponibles, según el componente de impuestos que haya seleccionado.
17. Utilice las siguientes opciones para identificar la naturaleza del código fiscal:

    - Está exento
    - Es IVA de importación
    - Cargo invertido
    - Excluir del cálculo del importe base

    Para un escenario de IVA de importación, configure un código de impuestos único que tenga un tipo impositivo positivo y márquelo como **Es IVA de importación**.

    Para un escenario de cargo invertido, configure dos códigos de impuestos, uno de los cuales tiene un tipo impositivo positivo y el otro tiene un tipo impositivo negativo pero el mismo valor absoluto del tipo. Marque el código impositivo negativo como **Es cargo invertido**. Para obtener más información sobre la solución de cargo invertido en Finance, consulte [Mecanismo de cargo invertido para esquema de IVA/GST](emea-reverse-charge.md).

    Para algunos tipos de impuestos que deben excluirse del cálculo del importe de la base fiscal para transacciones con precio incluido (por ejemplo, los derechos de aduana en algunos países o regiones), active la casilla **Excluir del cálculo del importe base**. Para obtener más información sobre este parámetro, consulte [Cálculo del impuesto a partir del precio cuando está habilitado que los precios incluyen impuestos](global-exclude-from-tax-base-amount-calculation.md).

    Mantenga los tipos impositivos y los límites de importe impositivo para este código impositivo.

18. Repita los pasos del 14 al 17 para agregar el resto de códigos de impuesto necesarios.
19. En la pestaña **Grupo de impuestos**, seleccione la columna **Grupo de impuestos**, agréguela a la matriz como condición de entrada y luego agregue líneas para mantener los datos maestros del grupo de impuestos.

    He aquí un ejemplo.

    | Grupo de impuestos    | Códigos impositivos           |
    | ------------ | ------------------- |
    | DEU_Nacional | DEU_VAT19; DEU_VAT7 |
    | DEU_UE       | DEU_Exento          |
    | BEL_Nacional | BEL_VAT21; BEL_VAT6 |
    | BEL_UE       | BEL_Exento          |

20. En la pestaña **Grupo de impuestos de artículos**, seleccione la columna **Grupo de impuestos de artículos**, agréguela a la matriz como condición de entrada y luego agregue líneas para mantener los datos maestros del grupo de impuestos de artículos.

    He aquí un ejemplo.

    | Grupo de impuestos de artículos | Códigos impositivos                                    |
    | -------------- | -------------------------------------------- |
    | Completa           | DEU_VAT19; BEL_VAT21; DEU_Exento; BEL_Exento |
    | Reducido        | DEU_VAT7; BEL_VAT6; DEU_Exento; BEL_Exento   |

21. En la pestaña **Aplicabilidad del grupo de impuestos**, seleccione las columnas necesarias para determinar el grupo de impuestos correcto y, a continuación, seleccione **Agregar**. Introduzca o seleccione valores para cada columna. El campo **Grupo de impuestos** será la salida de esta matriz. Si esta pestaña no está configurada, se utilizará el grupo de impuestos en la línea de transacción.

    He aquí un ejemplo.

    | Proceso empresarial | Enviar desde | Enviar a | Grupo de impuestos    |
    | ---------------- | --------- | ------- | ------------ |
    | Sales            | DEU       | DEU     | DEU_Nacional |
    | Sales            | DEU       | FRA     | DEU_UE       |
    | Sales            | BEL       | BEL     | BEL_Nacional |
    | Sales            | BEL       | FRA     | BEL_UE       |

22. En la pestaña **Aplicabilidad del grupo de impuestos de artículos**, seleccione las columnas necesarias para determinar el código de impuestos correcto y, a continuación, seleccione **Agregar**. Introduzca o seleccione valores para cada columna. El campo **Grupo de impuestos de artículos** será la salida de esta matriz. Si esta pestaña no está configurada, se utilizará el grupo de impuestos de artículos en la línea de transacción.

    He aquí un ejemplo.

    | Código de artículo | Grupo de impuestos de artículos |
    | --------- | -------------- |
    | D0001     | Completa           |
    | D0003     | Reducido        |

    Para obtener más información sobre cómo se determinan los códigos de impuestos en Cálculo de impuestos, consulte [Lógica de determinación del grupo de impuestos y el grupo de impuestos de artículos](global-sales-tax-group-determination.md).

23. Configure la aplicabilidad de los números de registro de impuestos de clientes, los números de registro de impuestos de proveedores y los códigos de lista según las necesidades de su negocio.
24. Haga clic en **Guardar** y, a continuación, cierre la página.
25. Seleccione **Cambiar estado** \> **Completada**. Una vez que el estado cambia a **Completo**, la versión ya no se puede editar.
26. Seleccione **Cambiar estado** \> **Publicar**. Esta versión de la configuración de la característica de impuestos se enviará al repositorio global y será visible para cada entidad legal en Finance.

## <a name="set-up-tax-calculation-in-dynamics-365"></a>Configurar Cálculo de impuestos en Dynamics 365

Después de completar la configuración en RCS, tendrá una versión publicada de la funcionalidad de impuestos. Siga estos pasos para configurar el cálculo de impuestos en Finance.

La configuración en esta sección se realiza por entidad jurídica. Debe configurarlo para cada entidad jurídica para la que desee habilitar el cálculo de impuestos en Finance.

1. En Finance, vaya a **Impuesto** \> **Configuración** \> **Configuración de impuestos** \> **Parámetros de cálculo de impuestos**.
2. En la pestaña **General**, establezca los campos siguientes:

    - **Habilitar el servicio Cálculo de impuestos**: active esta casilla para habilitar Cálculo de impuestos para la entidad jurídica. Si el complemento de cálculo de impuestos no está habilitado para la entidad jurídica actual, la entidad jurídica seguirá utilizando el motor de impuestos existente para determinar y calcular los impuestos.
    - **Configuración de características**: seleccione una configuración y versión de característica de impuestos publicada para la entidad jurídica. Para obtener más información sobre cómo configurar y completar una característica de impuestos publicada, consulte la sección anterior de este tema.
    - **Procesos de negocio** - Seleccione los procesos comerciales para habilitar.

3. En la pestaña **Cálculo**, defina la regla de redondeo esperada para la entidad jurídica. Para obtener más información sobre la lógica de redondeo, consulte [Reglas de redondeo del cálculo de impuestos](https://go.microsoft.com/fwlink/?linkid=2166988).
4. En la pestaña **Manejo de errores**, defina el método de manejo de errores esperado para la entidad jurídica. Hay tres opciones disponibles:

    - N.º
    - Advertencia
    - Error

    Puede configurar un método de control de errores para cada código de resultado en la sección **Detalles**. O bien, si algunos códigos de resultado no están sincronizados desde el servicio de cálculo de impuestos, puede configurar un método predeterminado en la sección **General**.

5. En la pestaña **Registro de IVA múltiple**, puede activar la declaración de IVA, la lista de ventas de la UE e Intrastat por separado para trabajar en un escenario de varios registros de IVA. Para obtener más información sobre la notificación de impuestos para varios registros de IVA, consulte [Informes de varios registros de IVA](emea-reporting-for-multiple-vat-registrations.md).
6. Guarde la configuración y repita los pasos anteriores para cada entidad jurídica adicional. Cuando se publique una versión nueva y desee que se aplique, configure el campo **Configuración de características** en la pestaña **General** de la página **Parámetros de cálculo de impuestos** (consulte el paso 2).

## <a name="transaction-processing"></a>Procesamiento de transacciones

Una vez que haya completado todos los procedimientos de configuración, puede usar Cálculo de impuestos para determinar y calcular impuestos en Finance. Los pasos para procesar transacciones siguen siendo los mismos. Las siguientes transacciones son compatibles con Finance, versión 10.0.21:

- Proceso de ventas

    - Presupuesto de ventas
    - Pedido de ventas
    - Confirmación
    - Lista de selección
    - Traslado
    - Factura de ventas
    - Factura rectificativa
    - Pedido de devolución
    - Cargo de encabezado
    - Cargo de línea

- Proceso de compra

    - Pedido de compra
    - Confirmación
    - Lista de recepciones
    - Recepción de producto
    - Factura de compra
    - Cargo de encabezado
    - Cargo de línea
    - Factura rectificativa
    - Pedido de devolución
    - Solicitud de compra
    - Cargo de línea de solicitud de compra
    - Solicitud de presupuesto
    - Cargo de encabezado de solicitud de presupuesto
    - Cargo de línea de solicitud de presupuesto

- Proceso de inventario

    - Pedido de transferencia: envío
    - Pedido de transferencia: recepción
