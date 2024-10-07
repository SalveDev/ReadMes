# Glosario de Medidas de Power BI

## 1. Ingresos Cond
- **Descripción**: Evalúa el porcentaje actual y asigna un color según el rango del valor.
  
- **Criterios**:
  - **Mayor que 0.95**: Asigna el color **Verde** (`#00BC00`)
  - **Mayor que 0.90**: Asigna el color **Amarillo** (`#FBC916`)
  - **Mayor que 0**: Asigna el color **Rojo** (`#ED3434`)
  - **En otro caso**: Asigna el color **Negro** (`#000000`)

- **Formato de Salida**: Color en formato hexadecimal.

- **Ejemplo**: 
  - Para un porcentaje actual de **0.96**, el resultado será **Verde** (`#00BC00`).
  - Para un porcentaje actual de **0.91**, el resultado será **Amarillo** (`#FBC916`).
  - Para un porcentaje actual de **0.05**, el resultado será **Rojo** (`#ED3434`).
  - Para un porcentaje actual de **0.00**, el resultado será **Negro** (`#000000`).

---

## 2. CheckList Cond
- **Descripción**: Esta medida evalúa la diferencia en días entre una fecha de checklist y la fecha actual, asignando un color en función de la cantidad de días restantes.

- **Criterios**:
  - **Si está vacío**: Asigna el color **Negro**.
  - **Si los días son negativos**: Asigna el color **Negro**.
  - **Menos de 7 días**: Asigna el color **Verde**.
  - **Entre 7 y 9 días**: Asigna el color **Amarillo**.
  - **9 días o más**: Asigna el color **Rojo**.

- **Formato de Salida**: Color en formato hexadecimal.

- **Ejemplo**:
  - Si el checklist está vacío o la fecha es anterior a hoy, el resultado será **Negro**.
  - Si quedan menos de 7 días para el checklist, el resultado será **Verde**.
  - Si quedan entre 7 y 9 días, el resultado será **Amarillo**.
  - Si quedan 9 días o más, el resultado será **Rojo**.

---

## 3. RevGerZon
- **Descripción**: Esta medida evalúa la calificación más reciente de un "Gerente de Zona" y asigna un color según la antigüedad de la fecha y la calificación obtenida.

- **Criterios**:
  - **Si la calificación está vacía**: Asigna el color **Negro** (`#000000`).
  - **Si han pasado más de 30 días desde la fecha máxima**: Asigna el color **Naranja** (`#FF7F00`).
  - **Si la calificación es "VERDE"**: Asigna el color **Verde** (`#00BC00`).
  - **Si la calificación es "AMARILLO"**: Asigna el color **Amarillo** (`#FBC916`).
  - **Si la calificación es "ROJO"**: Asigna el color **Rojo** (`#ED3434`).

- **Formato de Salida**: Color en formato hexadecimal.

- **Ejemplo**:
  - Si no hay calificación disponible, el resultado será **Negro** (`#000000`).
  - Si la última fecha de revisión fue hace más de 30 días y la calificación es "ROJO", el resultado será **Rojo** (`#ED3434`).
  - Si la calificación es "VERDE" y la fecha de revisión es reciente, el resultado será **Verde** (`#00BC00`).

---
## 4. RevCoorCom
- **Descripción**: Esta medida evalúa la calificación más reciente de un "Coordinador Comercial" y asigna un color según la antigüedad de la fecha y la calificación obtenida.

- **Criterios**:
  - **Si la calificación está vacía**: Asigna el color **Negro** (`#000000`).
  - **Si han pasado más de 15 días desde la fecha máxima**: Asigna el color **Naranja** (`#FF7F00`).
  - **Si la calificación es "VERDE"**: Asigna el color **Verde** (`#00BC00`).
  - **Si la calificación es "AMARILLO"**: Asigna el color **Amarillo** (`#FBC916`).
  - **Si la calificación es "ROJO"**: Asigna el color **Rojo** (`#ED3434`).

- **Formato de Salida**: Color en formato hexadecimal.

- **Ejemplo**:
  - Si no hay calificación disponible, el resultado será **Negro** (`#000000`).
  - Si la última fecha de revisión fue hace más de 15 días y la calificación es "ROJO", el resultado será **Rojo** (`#ED3434`).
  - Si la calificación es "VERDE" y la fecha de revisión es reciente, el resultado será **Verde** (`#00BC00`).

---
## 5. DescuentosFormato
- **Descripción**: Esta medida evalúa la participación de los descuentos sobre las ventas y asigna un color si la participación supera el umbral establecido.

- **Criterios**:
  - **Si la participación de descuentos (`PartcDscto`) es mayor o igual a 0.06**: Asigna el color **Rojo**.

- **Formato de Salida**: Color en formato hexadecimal.

- **Ejemplo**:
  - Si la participación de descuentos es **0.07**, el resultado será **Rojo**.
  - Si la participación de descuentos es **0.05**, no se asignará ningún color.

---
## 6. LM Cond
- **Descripción**: Esta medida evalúa el valor del lento movimiento sobre el total de inventario y asigna un color según el rango del valor.

- **Criterios**:
  - **Si el valor lento movimiento (`LM VS INV`) es mayor o igual a 0.05**: Asigna el color **Rojo**.
  - **Si el valor lento movimiento es mayor o igual a 0.03**: Asigna el color **Amarillo**.
  - **Si el valor lento movimiento es mayor que 0**: Asigna el color **Verde**.
  - **En otro caso**: Asigna el color **Negro**.

- **Formato de Salida**: Color en formato hexadecimal.

- **Ejemplo**:
  - Si el valor de `LM VS INV` es **0.06**, el resultado será **Rojo**.
  - Si el valor es **0.04**, el resultado será **Amarillo**.
  - Si el valor es **0.02**, el resultado será **Verde**.
  - Si el valor es **0.00**, el resultado será **Negro**.

---
## 7. COLORCC
- **Descripción**: Esta medida evalúa el estado de los artículos en existencia y exhibición, asignando un color según condiciones específicas.

### Criterios de COLORCC:
- **Si `#ED3434` está presente en los resultados de `ExSinExh` o `ExhSinEx`**: Asigna el color **Rojo**.
- **Si `#FBC916` está presente en los resultados de `ExSinExh` o `ExhSinEx`**: Asigna el color **Amarillo**.
- **Si el valor de **ComCot** es mayor que 0**: Asigna el color **Verde**.
- **En otro caso**: Asigna el color **Negro**.

### Ejemplo de COLORCC:
- Si `ExhSinEx` o `ExSinEx` contiene `#ED3434`, el resultado será **Rojo**.
- Si `ExhSinEx` o `ExSinEx` contiene `#FBC916`, el resultado será **Amarillo**.
- Si **ComCot** es mayor que 0, el resultado será **Verde**.
- Si ninguna de las condiciones se cumple, el resultado será **Negro**.

### Dependencias:
#### 7.1. **ExhSinEx**
- **Descripción**: Cuenta la cantidad de artículos exhibidos que tienen un estado específico basado en **DIFDCOND**.

- **Criterios**:
  - **Contar artículos exhibidos que son `#ED3434` y no existen**: Asigna el color **Rojo**.
  - **Contar artículos exhibidos que son `#FBC916` y no existen**: Asigna el color **Amarillo**.
  - **Si no hay coincidencias**: Asigna el color **Verde**.

- **Formato de Salida**: Color en formato hexadecimal.

- **Ejemplo**:
  - Si hay artículos exhibidos que son `#ED3434`, el resultado será **Rojo**.
  - Si hay artículos exhibidos que son `#FBC916`, el resultado será **Amarillo**.
  - Si no hay artículos en ninguno de los estados, el resultado será **Verde**.

#### 7.2. **ExSinExh**
- **Descripción**: Cuenta la cantidad de artículos no exhibidos que tienen un estado específico basado en **DIFDCOND**.

- **Criterios**:
  - **Contar artículos no exhibidos que son `#ED3434` y existen**: Asigna el color **Rojo**.
  - **Contar artículos no exhibidos que son `#FBC916` y existen**: Asigna el color **Amarillo**.
  - **Si no hay coincidencias**: Asigna el color **Verde**.

- **Formato de Salida**: Color en formato hexadecimal.

- **Ejemplo**:
  - Si hay artículos no exhibidos que son `#ED3434`, el resultado será **Rojo**.
  - Si hay artículos no exhibidos que son `#FBC916`, el resultado será **Amarillo**.
  - Si no hay artículos en ninguno de los estados, el resultado será **Verde**.

#### 7.3. **ComCot**
- **Descripción**: Calcula la suma de artículos en existencia sin exhibición y artículos exhibidos sin existencia, excluyendo ciertas líneas.

- **Criterios**:
  - **Sumar `Articulos en Existencia sin Exhibicion` y `Articulos Exhibidos sin Existencia`** donde `LINEA` no sea **"LECHADAS"** o **"LAVADEROS"**.

- **Formato de Salida**: Número entero.

- **Ejemplo**:
  - Si hay 10 artículos en existencia sin exhibición y 5 exhibidos sin existencia, el resultado será **15**.

#### 7.4. **DIFDCOND**
- **Descripción**: Evalúa la diferencia de días desde la última entrada o salida de los artículos y asigna un color basado en la cantidad de días.

- **Criterios**:
  - **Si los días son mayores que 8**: Asigna el color **Rojo**.
  - **Si los días son mayores que 5**: Asigna el color **Amarillo**.
  - **Si los días son mayores o iguales a 0**: Asigna el color **Verde**.

- **Formato de Salida**: Color en formato hexadecimal.

- **Ejemplo**:
  - Si la diferencia de días es 9, el resultado será **Rojo**.
  - Si la diferencia de días es 6, el resultado será **Amarillo**.
  - Si la diferencia de días es 0, el resultado será **Verde**.

#### 7.5. **DIFD**
- **Descripción**: Calcula la diferencia de días entre la fecha de la última entrada o salida de los artículos, dependiendo de su estado de exhibición y existencia.

- **Criterios**:
  - **Si el artículo no está exhibido y existe**: Calcula la diferencia desde **UltimaEntrada**.
  - **Si el artículo está exhibido y no existe**: Calcula la diferencia desde **UltSalida**.

- **Formato de Salida**: Número entero.

- **Ejemplo**:
  - Si la última entrada fue hace 10 días, el resultado será 10.
  - Si la última salida fue hace 3 días y el artículo está exhibido, el resultado será 3.

---
## 8. **Rotacion Cond**
- **Descripción**: Evalúa la rotación de inventario y asigna un color según las condiciones especificadas.

### Criterios de **Rotacion Cond**:
- **Si la rotación es mayor o igual a 5**: Asigna el color **Rojo**.
- **Si la rotación es mayor o igual a 3**: Asigna el color **Amarillo**.
- **Si la rotación es mayor que 0**: Asigna el color **Verde**.
- **En otro caso**: Asigna el color **Negro**.

### Ejemplo de **Rotacion Cond**:
- Si la **Rotacion** es 6, el resultado será **Rojo**.
- Si la **Rotacion** es 4, el resultado será **Amarillo**.
- Si la **Rotacion** es 2, el resultado será **Verde**.
- Si la **Rotacion** es 0, el resultado será **Negro**.

### Dependencias:
#### 8.1. **Rotacion**
- **Descripción**: Calcula la rotación de inventario dividiendo el **Valor Inv** entre la **Venta $**.

- **Criterios**: 
  - **Rotacion** = **Valor Inv** / **Venta $**.

#### 8.2. **Valor Inv**
- **Descripción**: Suma el valor del inventario.

- **Criterios**: 
  - **Valor Inv** = SUM('CUBO MP'[ValorInv]).

#### 8.3. **Venta $**
- **Descripción**: Suma el total de ventas.

- **Criterios**: 
  - **Venta $** = SUM('CUBO MP'[TotalVenta]).

---
## 9. **MetaCond**
- **Descripción**: Evalúa el indicador de meta y asigna un color basado en las condiciones específicas.

### Criterios de **MetaCond**:
- **Si el indicador meta es mayor que 1.10**: Asigna el color **Rojo**.
- **Si el indicador meta es mayor que 0.90**: Asigna el color **Verde**.
- **Si el indicador meta es mayor que 0.85**: Asigna el color **Amarillo**.
- **Si el indicador meta es menor o igual a 0.85**: Asigna el color **Rojo**.

### Ejemplo de **MetaCond**:
- Si el **Indicador Meta** es 1.15, el resultado será **Rojo**.
- Si el **Indicador Meta** es 0.95, el resultado será **Verde**.
- Si el **Indicador Meta** es 0.87, el resultado será **Amarillo**.
- Si el **Indicador Meta** es 0.80, el resultado será **Rojo**.

### Dependencias:
#### 9.1. **Indicador Meta**
- **Descripción**: Calcula el indicador de meta dividiendo los `MTS EXIST` entre la `Meta`.

- **Criterios**: 
  - **Indicador Meta** = `MTS EXIST` / `Meta`.

#### 9.2. **MTS EXIST**
- **Descripción**: Calcula la existencia total de revestimientos en pisos y paredes.

- **Criterios**:
  - **MTS EXIST** = 
    ```DAX
    VAR ExistPisos = CALCULATE(
                        SUM('CUBO MP'[EXISTENCIA]),
                        FILTER(
                            ART,
                            ART[CATEGORIA] = "REVESTIMIENTOS" && ART[LINEA] = "PISOS"
                        ))
    VAR ExistParedes = CALCULATE(
                        SUM('CUBO MP'[EXISTENCIA]),
                        FILTER(
                            ART,
                            ART[CATEGORIA] = "REVESTIMIENTOS" && ART[LINEA] = "PAREDES"
                        ))

    RETURN
    ExistParedes + ExistPisos
    ```

#### 9.3. **Meta**
- **Descripción**: Calcula la suma de las metas para pisos y paredes.

- **Criterios**:
  - **Meta** = 
    ```DAX
    VAR PISOS = SUMX(
                    FILTER(
                        'MTS REV',
                        'MTS REV'[Atributo.1] = "Meta" && 'MTS REV'[Atributo.2] = "PISOS"), 
                    'MTS REV'[Valor])
    VAR PAREDES = SUMX(
                    FILTER(
                        'MTS REV',
                        'MTS REV'[Atributo.1] = "Meta" && 'MTS REV'[Atributo.2] = "PAREDES"), 
                    'MTS REV'[Valor])
    RETURN
    PISOS + PAREDES
    ```

---
## 10. **Mts Cond**
- **Descripción**: Evalúa la disponibilidad de metros y asigna un color basado en las condiciones específicas.

### Criterios de **Mts Cond**:
- **Si la disponibilidad de metros es mayor o igual a 0.15**: Asigna el color **Rojo**.
- **Si la disponibilidad de metros es mayor o igual a 0.1**: Asigna el color **Amarillo**.
- **Si la disponibilidad de metros es mayor que 0**: Asigna el color **Verde**.
- **Si la disponibilidad de metros es menor que 0**: Asigna el color **Naranja**.
- **En otro caso**: Asigna el color **Negro**.

### Ejemplo de **Mts Cond**:
- Si la **Mts Disp** es 0.16, el resultado será **Rojo**.
- Si la **Mts Disp** es 0.12, el resultado será **Amarillo**.
- Si la **Mts Disp** es 0.05, el resultado será **Verde**.
- Si la **Mts Disp** es -0.02, el resultado será **Naranja**.

### Dependencias:
#### 10.1. **Mts Disp**
- **Descripción**: Calcula la disponibilidad de metros dividiendo la `Meta Disponible` entre la `Meta`.

- **Criterios**: 
  - **Mts Disp** = `Meta Disponible` / `Meta`.

#### 10.2. **Meta Disponible**
- **Descripción**: Calcula la meta disponible restando `MTS EXIST` de la `Meta`.

- **Criterios**:
  - **Meta Disponible** = `Meta` - `MTS EXIST`.

---
## 11. **Cartera**
- **Descripción**: Cuenta la cantidad de razones sociales distintas en la tabla `CARTERA`.

### Ejemplo de **Cartera**:
- Si la tabla `CARTERA` contiene las razones sociales "Empresa A", "Empresa B" y "Empresa A" (repetido), el resultado será **2**.

---
## 12. **TransitosCond**
- **Descripción**: Evalúa la cantidad de días desde la fecha más antigua en la tabla `TRANSITOS` y asigna un color basado en el número de días transcurridos.

### Criterios de **TransitosCond**:
- **Si la diferencia de días es mayor a 2**: Asigna el color **Rojo**.

### Ejemplo de **TransitosCond**:
- Si la fecha más antigua en `TRANSITOS` es hace 3 días, el resultado será **Rojo**.
- Si la fecha más antigua es hoy o hace 1 o 2 días, el resultado no asignará color (dependiendo de si se añaden más condiciones).

---
## 13. **PersonalCount**
- **Descripción**: Evalúa el estado del personal activo en relación con los cargos y la plantilla autorizada, asignando un color basado en diversas condiciones.

### Criterios de **PersonalCount**:
- **Si el número de gerentes (`isGer`) es 0**: Asigna el color **Rojo**.
- **Si hay alertas de puestos (`"Fuera de rango"`)**: Asigna el color **Rojo**.
- **Si el porcentaje de personal (`"% Personal"`) es mayor que 1**: Asigna el color **Rojo**.
- **Si el porcentaje de personal es exactamente 1**: Asigna el color **Verde**.
- **Si el porcentaje de personal es menor que 1**: Asigna el color **Naranja**.
- **Si el porcentaje de personal es menor o igual a 0.8**: Asigna el color **Rojo**.

### Ejemplo de **PersonalCount**:
- Si no hay gerentes y `isGer = 0`, el resultado será **Rojo**.
- Si hay alertas en `"Fuera de rango"`, el resultado será **Rojo**.
- Si el porcentaje de personal es 0.9, el resultado será **Naranja**.
- Si el porcentaje de personal es 1, el resultado será **Verde**.

### Dependencias:
#### 13.1. **Fuera de rango**
- **Descripción**: Suma las alertas de puestos.
- **Fórmula**: `"SUM('PLANTILLA AUTORIZADA'[Alerta de Puesto])"`

#### 13.2. **Alerta de Puesto**
- **Descripción**: Indica si hay un desbalance entre las personas autorizadas y los activos.

#### 13.3. **% Personal**
- **Descripción**: Calcula el porcentaje de personal activo en relación con la plantilla autorizada.
- **Fórmula**: `"% Personal = [Personal Activo] / [Plantilla Autorizada]"`

#### 13.4. **Personal Activo**
- **Descripción**: Cuenta el número de personal activo.
- **Fórmula**: `"COUNT('PERSONAL ACTIVO'[Id cargo])"`

#### 13.5. **Plantilla Autorizada**
- **Descripción**: Suma el número de personas autorizadas en la plantilla.
- **Fórmula**: `"SUM('PLANTILLA AUTORIZADA'[PersonasAutorizadas])"`
