--- 
title: "Actualizar el formato adoptando una nueva versión de base de ese formato para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede mantener una configuración de formato de informes electrónicos."
author: NickSelin
manager: AnnBe
ms.date: 02/06/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: cfc68c1d0810cbc296b35c09176dde2c948a50d0
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---
# <a name="upgrade-your-format-by-adopting-of-new-base-version-of-that-format-for-electronic-reporting-er"></a>Actualizar el formato adoptando una nueva versión de base de ese formato para informes electrónicos (ER)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede mantener una configuración de formato de informes electrónicos. Este procedimiento explica el modo en que se puede crear una versión personalizada de un formato en función del formato recibido de un proveedor de configuración. También explica cómo adoptar una nueva versión base de ese formato.



Para finalizar estos pasos, debe completar primero los pasos de los procedimientos "Creación y activación de un proveedor de configuraciones" y "Usar formato creado para generar documentos electrónicos para pagos”. Estos pasos se pueden llevar a cabo en la empresa GBSI.


## <a name="select-format-configuration-for-customization"></a>Seleccionar configuración del formato para personalización
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * En este ejemplo, la empresa de muestra Litware, Inc. (`http://www.litware.com`) actuará como proveedor de configuración que admite las configuraciones de formato para pagos electrónicos para un país concreto.  Empresa de muestra Proseware, Inc (`http://www.proseware.com`) actuará como consumidor de la configuración del formato que Litware, Inc. proporcionó. Proseware, Inc. usa formatos en determinadas regiones de ese país.  
2. Haga clic en Configuraciones de informes.
3. Haga clic en Mostrar filtros.
4. Aplique los siguientes filtros: especifique un valor de filtro de "BACS (UK ficticia)" en el campo "Nombre" mediante el operador de filtro "empieza por".
    * BACS (ficticio Reino Unido)  
    * La configuración de formato seleccionada BACS (ficticia del Reino Unido) es propiedad del proveedor Litware, Inc.  
5. Haga clic en Mostrar filtros.
6. En la lista, busque y seleccione el registro deseado.
    * La versión del formato con el estado de Completado se usará por Proseware, Inc. para personalización.  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a>Crear una nueva configuración para su formato personalizado de documento electrónico
Proseware, Inc. recibió la versión 1.1 de la configuración de BACS (ficticia del Reino Unido) que contiene el formato inicial para generar documentos de pago electrónico de Litware, Inc. de acuerdo a su servicio de suscripción. Proseware, Inc. desea comenzar a usar esto como estándar para su país pero se requiere alguna personalización para admitir requisitos regionales específicos. Proseware, Inc. también desea conservar la capacidad de actualizar un formato personalizado tan pronto como llegue una nueva versión (con los cambios para admitir nuevos requisitos específicos de país) de Litware, Inc. y quieren desarrollar esta actualización con el coste más bajo.  Para ello, Proseware, Inc. debe crear una configuración mediante la configuración BACS (ficticio de Reino Unido) de Litware, Inc. como base.  
1. Cierre la página.
2. seleccione Proseware, Inc. para convertirlo en un proveedor activo.
3. Haga clic en Definir como activo.
4. Haga clic en Configuraciones de informes.
5. En el árbol, expanda "Pagos (modelo simplificado)".
6. En el árbol, seleccione "Pagos (modelo simplificado\BACS (ficticio Reino Unido)".
    * Seleccione la configuración BACS (ficticio de Reino Unido) de Litware, Inc. Proseware, Inc. utilizará la versión 1.1 como base para la versión personalizada.  
7. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
    * Esto le permite crear una nueva configuración para un formato de pago personalizado.  
8. En el campo Nuevo, especifique "Derivan del nombre: BACS (ficticio Reino Unido), Litware, Inc.".
    * Seleccione la opción Derivar para confirmar el uso de BACS (ficticio Reino Unido) como la base para crear la versión personalizada.  
9. En el campo Nombre, escriba "BACS (personalizado ficticio del Reino Unido)".
    * BACS (personalizado ficticio del Reino Unido)  
10. En el campo Descripción, escriba "Formato de pago de proveedor BACS (Reino Unido ficticio personalizado)".
    * Pago de proveedor BACS (personalizado ficticio del Reino Unido)  
    * El proveedor de configuraciones activo (Proseware, Inc.) se especifica automáticamente aquí. Este proveedor podrá mantener esta configuración. Otros proveedores podrán usar esta configuración, pero no podrán mantenerla.  
11. Haga clic en Crear configuración.

## <a name="customize-your-format-for-the-electronic-document"></a>Personalizar el formato para el documento electrónico
1. Haga clic en Diseñador.
2. Haga clic en Expandir/Contraer.
3. Haga clic en Expandir/Contraer.
4. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Banco".
5. Haga clic en Agregar para abrir el cuadro desplegable.
6. En el árbol, seleccione XML\Elemento.
7. En el campo Nombre, escriba "IBAN".
    * IBAN  
8. Haga clic en Aceptar
9. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\IBAN".
10. Haga clic en Agregar para abrir el cuadro desplegable.
11. En el árbol, seleccione "Texto\Cadena".
12. Haga clic en Aceptar
13. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Cadena".
14. Escriba "60" en el campo Longitud máxima.
15. Haga clic en la ficha Asignación.
16. En el árbol , expanda "modelo".
17. En el árbol, expanda modelo\Pagos.
18. En el árbol, expanda modelo\Pagos\Acreedor.
19. En el árbol, expanda modelo\Pagos\Acreedor\Cuenta.
20. En el árbol, seleccione "modelo\Pagos\Acreedor\Cuenta\IBAN".
21. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo =  modelo.Pagos\Proveedor\Banco\IBAN\Cadena".
22. Haga clic en Enlazar.
23. Haga clic en Guardar.

## <a name="validate-the-customized-format"></a>Validar el formato personalizado
1. Haga clic en Validar.
    * Valide el diseño de formato personalizado y los cambios de asignación de datos para asegurarse de que todos los enlaces son correctos.  
2. Cierre la página.

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a>Cambie el estado de la versión actual de la configuración del formato personalizada
    * Cambie el estado de la configuración del formato diseñado de Borrador a Completado para que esté disponible para la generación de documentos de pago.  
1. Haga clic en Cambiar estado.
    * Observe cómo la versión actual de la configuración seleccionada se encuentra en el estado Borrador.  
2. Haga clic en Completar.
3. En el campo Descripción, escriba un valor.
4. Haga clic en Aceptar
5. En la lista, busque y seleccione el registro deseado.
    * Observe cómo la configuración creada se guarda como versión completada 1.1.1. Esto significa que es la versión 1 del formato BACS personalizado (personalizado ficticio del Reino Unido), que se basa en la versión 1 del formato BACS (personalizado ficticio del Reino Unido), que se basa en la versión 1 del modelo de datos de pagos (modelo simplificado).  

## <a name="test-the-customized-format-to-generate-payment-files"></a>Probar el formato personalizado para generar archivos de pago
Complete los pasos del procedimiento “Usar formato creado para generar documentos electrónicos para pagos” en una sesión paralela de Dynamics 365 for Finance and Operations. Seleccione el formato de BACS (personalizado ficticio del Reino Unido) en parámetros del método de pago electrónico. Asegúrese de que el archivo de pago creado contiene el nodo XML recién introducido que presenta código IBAN de acuerdo con los requisitos regionales.  

## <a name="update-the-existing-country-specific-configuration"></a>Actualizar la configuración específica de país existente
Litware. Inc debe actualizar la configuración de BACS (ficticio del Reino Unido) y adoptar nuevos requisitos de país para gestionar el formato de documentos electrónicos. Más adelante, esto se incluirá en una nueva versión de esta configuración que se ofrecerá para los suscriptores de servicio, incluidos Proseware, Inc.  

En los procesos relacionados con las disposiciones de servicio reales, cada nueva versión de BACS (ficticio del Reino Unido) se puede importar por Proseware, Inc. desde Litware, Inc. configuraciones repositorias LCS En este procedimiento simularemos esto actualizando BACS (ficticio del Reino Unido) en nombre de un proveedor de servicio.

1. Cierre la página.
2. Seleccione el proveedor Litware, Inc.
3. Haga clic en Definir como activo.
4. Haga clic en Configuraciones de informes.
5. En el árbol, expanda "Pagos (modelo simplificado)".
6. En el árbol, seleccione "Pagos (modelo simplificado\BACS (ficticio Reino Unido)".
    * La versión provisional del provedor Litware, Inc. (ficticio del Reino Unido) se selecciona para incorporar cambios para admitir nuevos requisitos específicos de país.  

## <a name="localize-the-base-format-of-the-electronic-document"></a>Localizar el formato base del documento electrónico
Supongamos que hay nuevos requisitos regionales específicos del país que admite Litware:  
- Un valor para el código SWIFT del banco del acreedor en cada transacción de pago.  
- Un límite de 100 caracteres para la longitud del texto para el nombre del proveedor en un archivo de generación.  
 
Seleccione la versión de borrador de la configuración que desee para introducir los cambios necesarios.  

1. Haga clic en Diseñador.
2. Haga clic en Expandir/Contraer.
3. Haga clic en Expandir/Contraer.
4. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Banco".
5. Haga clic en Agregar para abrir el cuadro desplegable.
6. En el árbol, seleccione XML\Elemento.
7. En el campo Nombre, escriba "SWIFT'.
    * SWIFT  
8. Haga clic en Aceptar
9. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\SWIFT".
10. Haga clic en Agregar para abrir el cuadro desplegable.
11. En el árbol, seleccione "Texto\Cadena".
12. Haga clic en Aceptar
13. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Cadena".
14. Escriba "100" en el campo Longitud máxima.
15. Haga clic en la ficha Asignación.
16. En el árbol , expanda "modelo".
17. En el árbol, expanda modelo\Pagos.
18. En el árbol, expanda modelo\Pagos\Acreedor.
19. En el árbol, expanda modelo\Pagos\Acreedor\Agente.
20. En el árbol, seleccione "modelo\Pagos\Acreedor\Agente\SWIFT".
21. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo = modelo.Pagos\Proveedor\SWIFT\Cadena".
22. Haga clic en Enlazar.
23. Haga clic en Guardar.

## <a name="validate-the-localized-format"></a>Valide el formato localizado
1. Haga clic en Validar.
2. Cierre la página.

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a>Cambiar el estado de la versión actual de la configuración del formato base
Cambie el estado de la configuración del formato base actualizada de Borrador a Completado para que esté disponible para la generación de documentos de pago y actualizaciones de configuraciones de formato derivadas de él.  
1. Haga clic en Cambiar estado.
    * Observe cómo la versión actual de la configuración seleccionada se encuentra en el estado Borrador.  
2. Haga clic en Completar.
3. En el campo Descripción, escriba un valor.
4. Haga clic en Aceptar
5. En la lista, busque y seleccione el registro deseado.

## <a name="change-the-base-version-for-the-custom-format-configuration"></a>Cambiar la versión de base para la configuración de formato personalizada
Se informa a Proseware, Inc. de que hay una nueva versión 1.2 disponible de la configuración BACS (ficticio Reino Unido) para generar documentos de pago electrónico de acuerdo con los requisitos específicos de país anunciados recientemente. Proseware, Inc. desea empezar a usarla como estándar para el país.  Para ello, Proseware, Inc. tiene que cambiar la versión de la configuración base por la configuración personalizada BACS (personalizada ficticia del Reino Unido). En lugar de la versión 1.1 de BACS (ficticio Reino Unido), use la nueva versión 1.2.  

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. seleccione Proseware, Inc. para marcarlo como proveedor activo.
3. Haga clic en Definir como activo.
4. Haga clic en Configuraciones de informes.
5. En el árbol, expanda "Pagos (modelo simplificado)".
6. En el árbol, expanda "Pagos (modelo simplificado\BACS (ficticio Reino Unido)".
7. En el árbol, seleccione "Pagos (modelo simplificado\BACS (ficticio Reino Unido\BACS (personalizado ficticio del Reino Unido)".
    * Seleccione la configuración BACS (personalizada ficticia del Reino Unido), que es propiedad de Proseware, Inc.  
    * Use la versión de borrador de la configuración seleccionada para introducir los cambios necesarios.  
8. Haga clic en Reorganizar.
    * Seleccione la nueva versión 1.2 de la configuración base que se aplicará como nueva base para actualizar la configuración.  
9. Haga clic en Aceptar
    * Tenga en cuenta que se han detectado algunos conflictos entre la combinación de la versión personalizada y una nueva versión base que representa algunos cambios de formato que no se pueden combinar automáticamente.  

## <a name="resolve-rebase-conflicts"></a>Resolver conflictos de reorganización
1. Haga clic en Diseñador.
    * Observe que los cambios al límite de la longitud del texto del nombre del proveedor no se podrían resolver automáticamente. Por tanto, esto se presenta en una lista de conflictos. Para cada conflicto del tipo Actualización, están disponibles las siguientes opciones: - Aplicar valor de base anterior (botón de la parte superior de la cuadrícula) para incorporar el valor de la versión base anterior (0 en nuestro caso).  - Aplicar un valor de base (botón encima de la cuadrícula) para incorporar el nuevo valor de la versión base (100 en nuestro caso).  - Mantenga su propio el valor (personalizado) (60 en nuestro caso).  Haga clic en Aplicar valor de base para aplicar un límite específico por país de 100 caracteres para la longitud del texto del nombre del proveedor.  
    * Tenga en cuenta que Proseware, Inc y Litware, Inc tienen versiones personalizadas y locales de este formato con los códigos IBAN y SWIFT con componentes relacionados que se combinan automáticamente en el formato de gestión.  
2. Haga clic en Aplicar valor de base.
    * Haga clic en Aplicar valor de base para aplicar el límite específico por país de 100 caracteres para nombres de proveedor.  
3. Haga clic en Guardar.
    * Al guardar el formato se eliminarán conflictos resueltos de la lista de conflictos.  
4. Cierre la página.

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a>Cambiar el estado de la nueva versión de la configuración del formato personalizada
1. Haga clic en Cambiar estado.
    * Cambie el estado de la configuración de formato personalizada y actualizada de Borrador a Completado. Esto hará que la configuración del formato esté disponible para generar documentos de pago. Observe cómo la versión actual de la configuración seleccionada se encuentra en el estado Borrador.  
2. Haga clic en Completar.
3. En el campo Descripción, escriba un valor.
4. Haga clic en Aceptar
    * Tenga en cuenta que la configuración creada se guarda como la versión 1.2.2 completada: versión 2 del formato BACS base (personalizado ficticia del Reino Unido), que se basa en la versión 2 del formato BACS base (ficticio Reino Unido), que se basa en la versión 1 del modelo de datos de pagos (modelo simplificado).  

## <a name="test-the-customized-format-for-payment-files-generation"></a>Probar el formato personalizado para generación de archivos de pago
Complete los pasos del procedimiento "Usar formato creado para generar documentos electrónicos para pagos" en una sesión paralela de Dynamics 365 for Finance and Operations. Seleccione el formato "BACS (personalizado ficticio del Reino Unido)" en parámetros del método de pago electrónico. Asegúrese de que el archivo de pago creado contiene el nodo XML recién introducido por Proseware, Inc. que presenta código de cuenta IBAN de acuerdo con los requisitos regionales. El archivo también debe contener el nodo XML recientemente introducido por Litware, Inc. que muestra el código bancario SWIFT de acuerdo con los requisitos de país.  


