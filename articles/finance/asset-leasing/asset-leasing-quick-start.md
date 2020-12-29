---
title: Introducción al arrendamiento de activos
description: Este tema describe la capacidad de arrendamiento de activos y recorre los pasos para crear un arrendamiento de activos y ver la información de esos arrendamientos.
author: moaamer
manager: Ann Beebe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-09-24
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9e206569aad3f53a2f6f66e6d6253226e5980078
ms.sourcegitcommit: 30c541426cf2037b768e3556e1b170a64991f64a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "4447779"
---
# <a name="asset-leasing-get-started"></a>Introducción al arrendamiento de activos

[!include [banner](../includes/banner.md)]

Este tema describe la capacidad de arrendamiento de activos y recorre los pasos para crear un arrendamiento de activos y ver la información de esos arrendamientos. El tema también define la terminología utilizada en la interfaz de usuario y la documentación. El arrendamiento de activos es una capacidad avanzada para administrar, rastrear y automatizar las transacciones financieras del arrendatario para los activos arrendados en Microsoft Dynamics 365 Finance. El arrendamiento de activos cumple con las normas internacionales de contabilidad (NIIF 16) y las normas US GAAP (ASC 842). El arrendamiento de activos captura y procesa la información principal sobre los arrendamientos y ayuda a generar asientos de diario en todo el ciclo de vida del arrendamiento desde el reconocimiento inicial, los asientos de diario mensuales, hasta el deterioro y la terminación del arrendamiento. El arrendamiento de activos se integra a la perfección con otros componentes de Dynamics 365 Finance, incluidos Activos fijos, Proveedores y Contabilidad general.

Para obtener más información sobre las normas de contabilidad, consulte la documentación estándar de la NIIF 16 y la US GAAP ASC 842.

## <a name="asset-leasing-elements"></a>Elementos de arrendamiento de activos
El siguiente diagrama muestra los elementos principales del proceso empresarial de los arrendamientos.

[![Elementos de arrendamiento de activos](./media/overview-01.png)](./media/overview-01.png)

Un activo arrendado contiene los siguientes componentes principales:

- **Contrato de arrendamiento** - El arrendador es propietario del activo y acuerda con el arrendatario arrendar un activo por un período específico a cambio de pagos periódicos de arrendamiento. Además del contrato legal entre el arrendador y el arrendatario, el contrato de arrendamiento captura decisiones de gestión como la probabilidad de ejercer una opción de renovación y transferencia de propiedad.

- **Cálculo y clasificación de arrendamientos según norma contable** - El cálculo y clasificación del arrendamiento identifica la norma contable que se aplicará en la medición inicial y posterior, así como la prueba de clasificación que determina cuál será el tipo de arrendamiento. Un arrendamiento puede ser un arrendamiento financiero, un arrendamiento operativo, un arrendamiento a corto plazo o un arrendamiento de bajo valor. El sistema también calcula el valor presente de futuros pagos mínimos de arrendamiento con el propósito de valuación y clasificación.

- **Transacciones de arrendamiento** - El arrendamiento de activos respalda el reconocimiento inicial del activo por derecho de uso para arrendamientos en el balance general, así como la medición posterior de los arrendamientos dentro del balance o fuera del balance. La transacción de reconocimiento inicial mide el valor presente de los pagos mínimos de arrendamiento futuros. Estos datos se utilizan para determinar el valor del activo por derecho de uso inicial y el pasivo por arrendamiento, que afectan el balance general de la organización. La medición posterior de las transacciones de arrendamiento mensuales implica la acumulación de intereses sobre el pasivo por arrendamiento, lo que aumenta el pasivo por arrendamiento. También mide el devengo de los pagos por arrendamiento que disminuyen el pasivo por arrendamiento y que posteriormente serán pagados al arrendador. La medición también incluye la amortización del activo por derecho de uso.

  Para los arrendamientos fuera de balance, el sistema calcula el gasto de arrendamiento en línea recta sobre el que sea menor: la vida económica del activo o el plazo del arrendamiento. Los ajustes de arrendamiento miden las modificaciones del contrato, como la extensión o expansión del arrendamiento, y la transacción de deterioro que utiliza el activo por derecho de uso para costos no recuperables.

  El arrendamiento de activos se integra con el libro mayor para garantizar que todas las transacciones de arrendamiento publicadas actualicen su plan de cuentas. El arrendamiento de activos se integra con Cuentas por pagar para rastrear las facturas del arrendador en Cuentas por pagar y tomar pagos futuros desde allí. La integración con Activos fijos le permite realizar un seguimiento de los arrendamientos en el registro de activos fijos y publicar transacciones de activos por derecho de uso, incluido el reconocimiento inicial, la depreciación y el deterioro del activo, desde dentro de Activos fijos.   

## <a name="asset-leasing-components"></a>Componentes del arrendamiento de activos 
Mapas de arrendamiento de activos, información de arrendamiento, cronogramas de pago, fechas de inicio y finalización y frecuencia de pago. También automatiza los cálculos del valor presente, los pagos mensuales del arrendamiento, los intereses y la amortización del arrendamiento. El sistema realiza pruebas de clasificación de arrendamientos, según la configuración. El sistema también crea y registra las transacciones de arrendamiento correspondientes, que se basan en el marco definido por el estándar contable que está siguiendo.

El siguiente diagrama muestra el libro de arrendamientos, el arrendamiento, el calendario de pagos calculado, las pruebas de clasificación para arrendamientos y libros de arrendamientos, y las transacciones contables correspondientes.

[![Arrendamiento, libro de arrendamientos y calendario de pagos](./media/overview-02.png)](./media/overview-02.png)

- **Libro de alquiler** - El libro de arrendamientos incluye toda la información del contrato de arrendamiento, como términos de arrendamiento, valor razonable y pagos de arrendamiento. También incluye el estándar de contabilidad que está siguiendo, el tipo de arrendamiento y los umbrales que se consideran en la prueba de clasificación de arrendamiento. El libro de arrendamientos también contiene las transacciones de arrendamiento que se registraron en el libro mayor. 
  
- **Arrendamiento** - El arrendamiento lleva la información de arrendamiento de activos que representa la base del arrendamiento de activos, la fuente de información de arrendamiento es el contrato de arrendamiento y las decisiones de administración que se realizan fuera de Dynamics 365 Finance. El valor razonable del activo es el precio que se pagaría por un activo en una transacción en la fecha de medición. Este valor puede depender del tipo de activo, las condiciones del mercado y otros criterios que se pueden tener en cuenta en la evaluación. El valor razonable del activo se considerará en la ecuación de la prueba de clasificación.

- **Vida útil del activo** - Representa los períodos remanentes de la vida útil de un activo, desde la fecha de inicio del arrendamiento. La vida útil de un activo se considerará en la ecuación de la prueba de clasificación. Se diferencia de la vida útil definida en Activos fijos.

- **Tasa de endeudamiento incremental** - Esta es la tasa de interés que se utilizará para calcular el valor presente. El sistema utilizará la tasa implícita si está definida en los datos del arrendamiento para calcular el valor presente de los pagos del arrendamiento. Si no se define la tasa implícita, el sistema utilizará la tasa de endeudamiento incremental.

- **Tipo de anualidad** - Este es el pago del arrendamiento adeudado al comienzo del período de pago o al final del período. Esto podría ser un pago por adelantado o una anualidad adeudada (al comienzo del período de pago del arrendamiento) o una anualidad ordinaria (al final del período de pago del arrendamiento).

  El primer mes se considerará período número cero para el pago por adelantado; el primer mes se considerará período uno para los pagos atrasados.

- **Intervalo de capitalización** - Esto representa el número de períodos en los que se capitalizan los intereses por año. Esto podría ser mensual (12 períodos por año), trimestral (4 períodos por año), semestral (2 períodos por año) o anual (1 período por año). El número de períodos se considerará en el cálculo del valor presente.

- **Fecha de inicio** - Es la fecha en la que el arrendador pone el activo a disposición del arrendatario para su uso. Todos los cálculos y transacciones de arrendamiento se basarán en la fecha de inicio. La fecha de inicio debe ser al comienzo de un período (el primero del mes) para garantizar la precisión de los cálculos posteriores. Puedes usar el campo **Fecha de firma del contrato** para ingresar la fecha real en la que se firmó el contrato.

- **Plazo del arrendamiento** - Esta es la duración del período de arrendamiento, en meses.

> [!NOTE] 
> La definición del plazo del arrendamiento se basa en el número de períodos, o intervalos, en las líneas de programación de pagos. El número definido de intervalos se convertirá a meses.

- **Línea de programación de pagos** - Esto captura los pagos de arrendamiento por período. También especifica si un período de renovación se ejercerá e incluirá en la medición inicial del activo por derecho de uso y el pasivo por arrendamiento. Puede definir la fecha de inicio de los pagos vencidos del arrendamiento y los intervalos de período que representan la duración del arrendamiento, que pueden ser días, meses o años.

- **Frecuencia de pago** - Indica si el pago es mensual, trimestral, semestral o anual. La fecha de finalización se calcula automáticamente en función de la fecha de inicio y el número de períodos ingresados.

- **Calendario de pago** - Este es el valor presente calculado, basado en el período de tiempo cubierto por los pagos de arrendamiento, el monto de los pagos, los períodos de capitalización y el tipo de anualidad.

- **Periodos** - Estos son los períodos de arrendamiento que reflejan el tipo de capitalización interna y anualidad. El intervalo de capitalización determina cómo se dividirán los períodos. Puede configurar los siguientes intervalos de capitalización:

  - Mensual, 12 periodos al año
  - Trimestral, 4 periodos al año
  - Semestral, 2 periodos al año
  - Anual, 1 periodo al año

El primer período comenzará con el período cero, si el tipo de anualidad es anualidad pagadera. En caso contrario, el primer período comenzará con uno, si el tipo de anualidad son pagos atrasados.

- **Meses** - Esto indica el número de meses calendario durante la duración del contrato de arrendamiento. El monto del pago es el monto adeudado según se define en la frecuencia de pago. El valor actual calculado es el pago de arrendamiento por período basado en el valor presente, los intervalos de capitalización y la tasa de interés incremental.

> [!NOTE] 
> El valor presente se calcula con base en la ecuación de flujo de efectivo descontado.

- **Libros** - Esta es la configuración preconfigurada que se asociará con cada arrendamiento. El libro define el estándar contable aplicado, los tipos de arrendamiento y el umbral que se utiliza como base para las pruebas de clasificación. Las pruebas de clasificación se utilizan para especificar el tipo de arrendamiento automáticamente.

- **Marco contable** - Esto muestra el estándar de contabilidad seleccionado, ya sea IFRS 16 y ASC 842, que está respaldando. El estándar contable está designado en el libro asociado con el arrendamiento. El estándar contable determinará las cuentas contables que se especifican en el perfil de contabilización.

- **Tipos de arrendamiento** Esto indica cuál de los dos tipos de arrendamientos se utilizará, ya sea un arrendamiento financiero o un arrendamiento operativo. En un arrendamiento financiero, los riesgos y beneficios relacionados con el activo arrendado se transfieren al arrendatario. Bajo un arrendamiento operativo, los riesgos y recompensas relacionados con el activo arrendado permanecen en el arrendador. Una tercera opción es una identificación automatizada del tipo de arrendamiento, ya sea financiero u operativo, con base en los umbrales definidos en el libro. Esta identificación automática se realiza durante la prueba de reclasificación del arrendamiento.

- **Umbrales** - Esto se utiliza en las pruebas de clasificación de arrendamientos para determinar si el activo se clasifica como uno de los siguientes:

  - **Plazo del arrendamiento** - Este es el porcentaje de la vida útil que se utilizará en la prueba de clasificación. El sistema clasificará el arrendamiento como financiero si el tipo de arrendamiento se establece en automático y si el plazo del arrendamiento durante la vida útil del activo es mayor o igual al porcentaje aquí definido.

  - **Valor presente** - Este es el porcentaje del valor razonable del activo que se utilizará en la prueba de clasificación. El sistema clasificará el arrendamiento como financiero si el tipo de arrendamiento se establece en automático y si el valor presente de los pagos por arrendamiento futuros sobre el valor razonable del activo es mayor o igual al porcentaje aquí definido.

  - **Arrendamiento a corto plazo** - Si el plazo del arrendamiento es menor o igual al valor definido, el arrendamiento se clasificará como arrendamiento a corto plazo.

  - **Bajo valor** - Si el valor razonable del activo es menor o igual al valor definido, el arrendamiento se clasificará como arrendamiento de bajo valor.

  - **Clasificación de arrendamientos y transacciones** La clasificación de arrendamientos es un proceso automatizado para clasificar los arrendamientos con base en los umbrales definidos en los libros además de otros criterios de prueba de clasificación para identificar si el arrendamiento es financiero, operativo, a corto plazo o de bajo valor. Esto también se utiliza para identificar si se sigue el proceso de alquiler diferido.

Las pruebas de clasificación incluyen Transferencia de propiedad, Opción de compra, Plazo de arrendamiento, Valor presente y Activo único. El siguiente diagrama ilustra las pruebas de clasificación de arrendamientos.

[![Pruebas de clasificación de arrendamientos](./media/overview-03.png)](./media/overview-03.png)

Cada tipo de arrendamiento maneja la contabilidad de manera diferente para diferentes transacciones de arrendamiento. Las transacciones incluyen el reconocimiento inicial, los gastos por intereses, el pago vencido del arrendamiento y la depreciación del arrendamiento, y se basan en los estándares de contabilidad que está siguiendo (NIIF 16 o ASC 842). Las cuentas del libro mayor se definen en el perfil de registro de arrendamientos para cada tipo de transacción y marco contable.

## <a name="asset-leasing-transactions"></a>Transacciones de arrendamiento de activos

#### <a name="initial-recognition"></a>Reconocimiento inicial 
El reconocimiento inicial de un activo arrendado utiliza el valor presente calculado para que se pueda informar en el balance. El asiento contable para esto se genera automáticamente. Esta transacción debita la cuenta del activo por derecho de uso y acredita la cuenta del pasivo por arrendamiento operativo de la siguiente manera. Si un activo fijo está asociado con el arrendamiento, la entrada de reconocimiento inicial se reflejará como una adquisición de activo fijo. En este escenario, debe definir un perfil de contabilización de activos fijos para contabilizar en la cuenta de activo por derecho de uso. 

> [!NOTE]
> Los arrendamientos operativos están respaldados solo por US GAAP ASC 842.

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Arrendamiento operativo bajo US GAAP              |     Activo por derecho de uso      |     Pasivo por arrendamiento operativo       |
|     Arrendamiento financiero bajo IFRS y US GAAP        |     Activo por derecho de uso      |     Pasivo por arrendamiento operativo       |

#### <a name="lease-liability-amortization-interest-expense"></a>Amortización del pasivo por arrendamiento (gastos por intereses) 
El interés de un arrendamiento se reconoce calculando el interés del saldo inicial del arrendamiento, el pago del período de arrendamiento, la tasa de interés de préstamo y los períodos de intervalo compuesto por año. El monto de los intereses aumenta la cuenta de pasivo por arrendamiento operativo al acreditarla, que se reflejará en el balance general de la organización. La transacción también incluye un asiento de débito en la cuenta de gastos por intereses, que se refleja en el estado de pérdidas y ganancias para los arrendamientos financieros, y en la cuenta de gastos de arrendamiento para los arrendamientos operativos.

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Entrada de pasivo por arrendamiento operativo según US GAAP ASC 842    |     Gastos de intereses          |     Pasivo por arrendamiento operativo         |
|     Entrada de pasivo por arrendamiento financiero bajo IFRS y US GAAP      |     Gastos de intereses          |     Pasivo por arrendamiento financiero           |

#### <a name="accrued-lease-payment"></a>Pago de arrendamiento devengado
Un pago de arrendamiento acumulado se reconoce como un pago futuro de arrendamiento que debe procesarse como una transacción de pago del banco o cuentas de efectivo. El pago del arrendamiento adeuda disminuye el pasivo del arrendamiento al debitar la cuenta del pasivo del arrendamiento contra si un sub-libro mayor del proveedor en caso de que el arrendador se define como un proveedor, o contabilizar el lado del crédito en una cuenta del libro mayor de documentos por pagar, entonces el pago se ejecutará contra cualquiera de los proveedores o pagarés por pagar.

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Arrendamiento operativo bajo US GAAP              |  Pasivo por arrendamiento operativo    |   Pasivo del proveedor (libro mayor auxiliar) / Documentos por pagar  |
|     Arrendamiento financiero bajo IFRS y US GAAP        |  Pasivo por arrendamiento financiero      |   Pasivo del proveedor (libro mayor auxiliar) / Documentos por pagar  |

#### <a name="asset-depreciation"></a>Depreciación de activos
El activo por derecho de uso se deprecia sobre lo que sea menor: la vida útil del activo o el plazo del arrendamiento. El método para calcular la depreciación para los US GAAP (ASC 842) se basa en la diferencia entre el gasto de arrendamiento de línea recta y el monto del interés. Los intereses de los arrendamientos financieros se calculan utilizando un método estándar de línea recta. La depreciación del arrendamiento afecta la cuenta de pérdidas y ganancias debitando los gastos por intereses. El balance se ve afectado al acreditar la cuenta de activo por derecho de uso acumulado para arrendamientos financieros. Para los arrendamientos operativos, la depreciación se acredita en la cuenta de gastos de arrendamiento. Si el arrendamiento está vinculado a un activo fijo, las transacciones de depreciación se ejecutarán solo desde el módulo de activos fijos. 

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Arrendamiento operativo bajo US GAAP              |  Gasto de arrendamiento                |   Depreciación acumulada del activo por derecho de uso     |
|     Arrendamiento financiero bajo IFRS y US GAAP        |   Depreciación del gasto del activo por derecho de uso   |   Depreciación acumulada del activo por derecho de uso    |

#### <a name="short-term-lease"></a>Arrendamiento a corto plazo
Un arrendamiento a corto plazo se reconoce como un gasto, que afectará el estado de resultados de una organización. El pago de arrendamiento generado adeudará la cuenta de gastos de arrendamiento y acreditará los documentos por pagar o la cuenta del libro mayor auxiliar del proveedor.

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Entrada de arrendamiento a corto plazo bajo IFRS y US GAAP     |  Gasto de arrendamiento                |   Pasivo del proveedor (libro mayor auxiliar) / Documentos por pagar  |

#### <a name="low-value-lease"></a>Arrendamiento de bajo valor
Un arrendamiento de bajo valor se reconoce como un gasto que afectará el estado de resultados de una organización. El pago de arrendamiento generado adeudará la cuenta de gastos de arrendamiento y acreditará los documentos por pagar o el libro mayor auxiliar del proveedor.

|     Tipo                                          |     Débito                     |     Crédito                            |
|-----------------------------------------------    |-----------------------------  |------------------------------------   |
|     Entrada de arrendamiento de bajo valor bajo IFRS y US GAAP      |  Gasto de arrendamiento                |   Pasivo del proveedor (libro mayor auxiliar) / Documentos por pagar  |


#### <a name="index-revaluation"></a>Revalorización de índice
Ésta es la cuenta de arrendamiento de activos para pagos de arrendamiento variables medidos por una tasa de índice. Los cambios en los pagos de arrendamiento causados por las fluctuaciones de la tasa de índice constituyen un ajuste de arrendamiento según la NIIF 16. El pasivo por arrendamiento y los activos por derecho de uso se ajustarán para dar cuenta de los nuevos pagos. 

|     Tipo                                          |     Débito                             |     Crédito                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Entrada de revalorización del índice bajo NIIF en caso de aumento  |  Activo por derecho de uso       |   Pasivo por arrendamiento operativo |
|   Entrada de revalorización del índice bajo NIIF en caso de disminución  |  Pasivo por arrendamiento operativo  |   Activo por derecho de uso      |

Cuando los pagos cambian debido a un cambio en la tasa de índice, solo los pagos variables cambiarán a menos que haya cambios adicionales en los flujos de efectivo, como un cambio en los términos de arrendamiento relacionados con las tasas de interés según US GAAP ASC 842.

#### <a name="lease-adjustment"></a>Ajuste de arrendamiento
El arrendamiento de activos permite ajustar los arrendamientos si se modifican los términos del arrendamiento, el arrendamiento se extiende o si existen circunstancias adicionales bajo las cuales un arrendamiento requiere un ajuste. Los ajustes de arrendamiento se registran para aumentar o disminuir el activo por derecho de uso y el pasivo por arrendamiento. El proceso de ajuste toma los saldos finales arrastrados de la amortización del pasivo y el saldo del activo en la fecha del ajuste. Cuando un arrendamiento está vinculado a un activo fijo, el ajuste por derecho de uso se publicará con el ID asignado en Activos fijos. 

|     Tipo                                          |     Débito                             |     Crédito                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Entrada de ajuste de arrendamiento para IFRS y US GAAP en caso de aumento     |  Activo por derecho de uso       |   Pasivo por arrendamiento operativo |
|   Entrada de ajuste de arrendamiento para IFRS y US GAAP en caso de disminución     |  Pasivo por arrendamiento operativo  |   Activo por derecho de uso      |


#### <a name="lease-impairment"></a>Deterioro del arrendamiento
Esto representa la reducción del saldo arrastrado del activo por derecho de uso. Identifique el monto del deterioro, la fecha de la transacción y los períodos restantes. El activo restante por derecho de uso se amortizará linealmente. La lógica de deterioro del arrendamiento considera el valor de arrastre del activo que existe en el calendario de depreciación del activo.  

|     Tipo                                          |     Débito                             |     Crédito                    |
|-----------------------------------------------    |-------------------------------------  |----------------------------   |
|   Entrada de deterioro para IFRS y US GAAP           |  Gasto de deterioro                   |    Activo por derecho de uso     |

>[!NOTE]
> Si el arrendamiento está vinculado a un activo fijo, el deterioro del arrendamiento debe contabilizarse desde Activos fijos porque la depreciación de activos se ejecuta desde el módulo Activos fijos.

**Moneda dual** Las transacciones de arrendamiento se pueden contabilizar en una moneda distinta a la moneda de contabilidad y presentación de informes. El tipo de cambio de moneda se define en el libro mayor en la fecha de inicio. Puede cambiar los tipos de cambio configurando el campo **Tipo de interés fijo** a **Sí** cuando crea el contrato de arrendamiento. Cuando ingresa transacciones de arrendamiento, el reconocimiento inicial y las transacciones de depreciación subsiguientes usarán el tipo de cambio a la fecha de inicio. Las transacciones de pago e intereses posteriores utilizarán el tipo de cambio activo actual. 

## <a name="create-an-asset-lease"></a>Crear un arrendamiento de activos
Complete los siguientes pasos para crear un arrendamiento nuevo. 

1. Para usar el **Arrendamiento de activos**, debe habilitarlo en el espacio de trabajo **Gestión de funciones**. Desde el espacio de trabajo **Gestión de funciones**, seleccione **Todos** para que todas las funciones se enumeren en la página. Seleccione **Arrendamiento de activos** y, a continuación, seleccione **Habilitar ahora**.
2. Vaya a **Arrendamiento de activos > Común > Resumen de arrendamiento**. Introduzca los campos necesarios en la ficha desplegable **General**. 
   - **Detalles del arrendamiento**
   - **Vida útil del activo (meses)**
   - **Grupo de arrendamiento**
   - **Tipo de interés incremental del endeudamiento (%)**
   - **Intervalo de composición**
   - **Tipo de anualidad**
   - **Divisa**
   - **Fecha de inicio**

3. Muévase a la ficha desplegable **Líneas de programación de pagos** e ingrese una línea de pago, luego seleccione **Crear horarios**.

4. Seleccione **Libros**. 

5. Cambie a la ficha desplegable **General**. Se calculan **Activo de derecho de uso inicial** y **Pasivo por arrendamiento**. 

6. Muévase a la ficha desplegable **Prueba de clasificación de arrendamiento** para comprobar el valor en el campo **Tipo de arrendamiento**. 

   El **Tipo de arrendamiento** automatico se clasifica en base a los criterios que se definen en la página **Libros**.

7.  Vaya a **Calendario de pago** bajo la sección **Función**.  

   La página **Calendario de pago** enumera los programas de pago futuros para un ID de arrendamiento. Seleccione **Confirmar horario** para poder publicar las transacciones de **Reconocimiento inicial**. 

[![Función de reconocimiento inicial](./media/overview-13.png)](./media/overview-13.png)

8. Seleccione **Reconocimiento inicial** para crear un diario de reconocimiento inicial. 

9. Seleccione **Diarios de arrendamiento de activos** para contabilizar la transacción de reconocimiento inicial. 

   Desde el calendario de pagos, puede abrir una página detallada que enumera las transacciones de activos por derecho de uso. 
 
   **Calendario de amortización del pasivo por arrendamiento** muestra la cantidad de interés que se calcula para cada período.
   
10. Cree el diario y luego vaya a **Diarios de arrendamiento de activos**. El **Calendario de amortización del pasivo por arrendamiento** también se muestra en las transacciones de intereses.

   La página **Programa de depreciación de activos** muestra las transacciones de depreciación para el ID de arrendamiento seleccionado. 

   [![Página Transacciones de activos por derecho de uso](./media/overview-20.png)](./media/overview-20.png)

   La página **Transacciones de activos por derecho de uso** enumera el reconocimiento inicial, la depreciación acumulada y el saldo del activo. 

   La página **Transacciones de pasivo por arrendamiento** muestra el reconocimiento inicial, el pago de intereses del arrendamiento, el pago del arrendamiento y el saldo del pasivo del arrendamiento. 

