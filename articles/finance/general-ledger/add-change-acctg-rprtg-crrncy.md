---
title: Cambiar la divisa contable o de notificación
description: Este tema explica cómo cambiar la divisa contable o de notificación, o agregar una divisa de notificación a la configuración de un libro mayor.
author: kweekley
ms.date: 05/05/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0435deb009173684c7faaf5340e8095c019ec71c
ms.sourcegitcommit: 2cd82983357b32f70f4e4a0c15d4d1f69e08bd54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085483"
---
# <a name="change-the-accounting-or-reporting-currency"></a>Cambiar la divisa contable o de notificación

[!include [banner](../includes/banner.md)]

Este tema explica cómo cambiar la divisa contable o de notificación, o agregar una divisa de notificación a la configuración de un libro mayor.

## <a name="symptom"></a>Síntoma

Puede que desee cambiar la divisa contable o de notificación, o agregar una divisa de notificación a la configuración del libro mayor. Esto suele ocurrir en los siguientes escenarios:

- Se especificó una divisa contable o de notificación errónea al configurar una entidad jurídica. Ahora desea cambiar esa divisa.
- Se especificó una divisa de notificación al configurar una entidad jurídica, pero la organización ahora quiere eliminar la divisa de notificación.
- La organización está actualizando o migrando a Microsoft Dynamics 365 Finance y desea cambiar la divisa contable o de notificación.

Una organización que no usó anteriormente la capacidad de doble divisa quiere comenzar a usarla. Este problema suele ocurrir en los siguientes escenarios.

- No se especificó ninguna divisa de notificación al configurar una entidad jurídica. (Una divisa de notificación es opcional). Ahora desea agregar una divisa de notificación.

## <a name="resolution"></a>Resolución

La consideración más importante es si se han registrado transacciones (reales o presupuestarias) en la entidad jurídica para la configuración del libro mayor. **No puede cambiar la divisa contable o de notificación, ni agregar una divisa de notificación, si se han registrado transacciones (reales o presupuestarias) en la entidad jurídica**. Siga los pasos de una de las siguientes secciones, dependiendo de si se han registrado transacciones.

### <a name="no-transactions-have-been-posted"></a>No se han registrado transacciones

1. En la entidad jurídica para la que está actualizando las divisas, vaya a **Libro mayor \> Configuración del libro mayor \> Libro mayor**.
2. En la página **Libro mayor**, seleccione **Editar**.
3. En la ficha desplegable **Divisa**, seleccione la divisa contable y la divisa de notificación que se utilizarán para la entidad jurídica.
4. Seleccione **Guardar**.

Si los campos para la divisa contable y la divisa de notificación no están disponibles en la página **Libro mayor**, significa que una o más transacciones (reales o presupuestadas) se han registrado en la entidad jurídica. Por lo tanto, las divisas no se pueden cambiar. En este caso, siga los pasos de la siguiente sección.

### <a name="transactions-have-been-posted"></a>Se han registrado transacciones

**Si se han registrado transacciones en la entidad jurídica, la única forma de cambiar o agregar divisas contables y de notificación es crear una nueva entidad jurídica con las divisas correctas**. Para facilitar este proceso, la administración de datos del sistema le permite copiar registros de configuración y registros maestros de la entidad jurídica actual a una nueva entidad jurídica.

Los cambios en las divisas contables y de notificación se aplican globalmente. Afectan no solo al libro mayor, sino también a todos los sublibros auxiliares (Clientes, Proveedores, Inventario, Proyecto, etc.), a todas las soluciones de proveedores de software independientes (ISV) y a cualquier extensión que haya realizado para almacenar importes.

El proceso de encontrar y convertir cada importe a una divisa diferente está sujeto a errores. Por lo tanto, el equipo de ingeniería no deberá aprobar los scripts que cambien o agreguen divisas contables y de notificación. Además, aunque una herramienta que solía estar disponible para Microsoft Dynamics AX 2012 le hubiera permitido cambiar o agregar divisas contables y de notificación, dicha herramienta quedó en desuso para AX 2012 R3 y Finance.

Siga estos pasos para copiar la configuración y los datos maestros de la entidad jurídica actual a una nueva entidad jurídica.

1. Vaya a **Espacios de trabajo \> Administración de datos**.
2. Seleccione **Plantillas** en el grupo **Importación/exportación**.
3. Asegúrese de que haya plantillas disponibles. Si no hay plantillas disponibles, seleccione **Cargar plantillas predeterminadas** y espere a que se generen las plantillas.
4. Vuelva al espacio de trabajo **Administración de datos**.
5. Seleccione **Copiar a entidad jurídica**.
6. Escriba un nombre y una descripción para el grupo.
7. En el campo **Entidad jurídica de origen**, seleccione la entidad jurídica desde la que copiar los datos.
8. En la ficha desplegable **Entidades jurídicas de destino**, seleccione **Crear entidades jurídicas** para crear una nueva entidad jurídica a la que pueda copiar los datos de la entidad jurídica de origen. Elija **Seleccionar existente** para copiar datos a una entidad jurídica existente.
9. Opcional: establezca el campo **Copiar secuencias numéricas** en **Sí**. (Se recomienda este paso al copiar los datos).
10. En el área **Entidades seleccionadas**, elija **Agregar plantilla**.
11. Seleccione las plantillas a utilizar. Entre las plantillas sugeridas para una nueva entidad jurídica se encuentran **025 - Libro mayor** y **Finanzas**. Le recomendamos que revise todas las demás plantillas disponibles para determinar si alguna de ellas puede aplicarse a sus necesidades.
12. Seleccione **Copiar en entidad jurídica** para iniciar un proceso por lotes que creará las entidades seleccionadas y las copiará en la entidad jurídica de destino.
13. Una vez completado el proceso, pero antes de registrar cualquier transacción, vaya al libro mayor y actualice las divisas contable y de notificación, como se describió anteriormente en este tema.

Si creó una nueva entidad jurídica para poder cambiar la divisa contable o de notificación, verifique que los saldos iniciales se conviertan de las divisas de la entidad jurídica anterior a las nuevas divisas.

Para ver un vídeo que muestra los pasos anteriores, consulte [Copiar a entidad jurídica](https://community.dynamics.com/365/b/techtalks/posts/copy-into-legal-entity-october-24-2017).
