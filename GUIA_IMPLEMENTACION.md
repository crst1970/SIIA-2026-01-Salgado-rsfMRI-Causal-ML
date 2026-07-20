# Guia de implementacion


**Machine Learning Causal en Resonancia Magnetica Funcional**

## 1. Estructura del repositorio

```text
.
|-- script/                        # Pipeline principal y modulos auxiliares
|-- pipeline_versiones9/           # Analisis Control-vs-TEA y figuras
|-- notebooks/                     # Notebooks usados en la ejecucion del estudio
|-- data/                          # Fenotipico liviano e instrucciones de datos
|-- tests/                         # Pruebas rapidas
|-- requirements.txt
|-- README.md
`-- GUIA_IMPLEMENTACION.md
```

## 2. Datos requeridos

La corrida principal usa datos rs-fMRI preprocesados de ABIDE I, variante:

```text
ABIDE PCP / C-PAC / filt_noglobal / *_func_preproc.nii.gz
```

Por tamano, los NIfTI no se incluyen en GitHub. Se debe descargar ABIDE PCP y
definir la variable de entorno `ABIDE_DATA_ROOT` apuntando a la carpeta donde se
encuentra `ABIDE_pcp`.

Estructura esperada:

```text
ABIDE_DATA_ROOT/
`-- ABIDE_pcp/
    |-- Phenotypic_V1_0b_preprocessed1.csv
    `-- cpac/
        `-- filt_noglobal/
            `-- *_func_preproc.nii.gz
```

En `data/ABIDE_pcp/` se conserva el archivo fenotipico usado para cruzar
identificadores, diagnostico y sitio. La carpeta no contiene la cohorte NIfTI
completa.

## 3. Instalacion

Desde la raiz del repositorio:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

## 4. Ejecucion principal

Puede seguirse la ejecucion desde los notebooks:

1. `notebooks/pipeline_v8.ipynb`: corrida principal con 100 ROIs.
2. `notebooks/pipeline_versiones9.ipynb`: analisis Control-vs-TEA, figuras y tablas.
3. `notebooks/pipeline_versiones10.ipynb`: analisis complementario 7x7 por redes.
