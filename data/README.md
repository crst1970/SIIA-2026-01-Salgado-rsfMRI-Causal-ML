# Datos

Este proyecto usa datos publicos de ABIDE I preprocesados mediante ABIDE PCP,
derivada C-PAC, variante `filt_noglobal`.

## Origen

- Dataset: Autism Brain Imaging Data Exchange I (ABIDE I).
- Preprocesamiento: ABIDE Preprocessed Connectomes Project (ABIDE PCP).
- Derivada usada: C-PAC.
- Variante usada: `filt_noglobal`.
- Sitio de referencia: https://fcon_1000.projects.nitrc.org/indi/abide/

El uso de los datos debe respetar las condiciones de acceso, uso y citacion
indicadas por ABIDE/INDI. Los NIfTI completos no se redistribuyen en este
repositorio por tamano y por buenas practicas de gestion de datos.

## Archivo incluido

En Git solo se conserva:

```text
data/ABIDE_pcp/Phenotypic_V1_0b_preprocessed1.csv
```

Este archivo fenotipico se usa para cruzar `SUB_ID`, `FILE_ID`, `DX_GROUP` y
`SITE_ID`.

## Estructura esperada

La corrida completa espera que los datos esten fuera del repositorio, en una
ruta indicada por la variable de entorno `ABIDE_DATA_ROOT`:

```text
ABIDE_DATA_ROOT/
`-- ABIDE_pcp/
    |-- Phenotypic_V1_0b_preprocessed1.csv
    `-- cpac/
        `-- filt_noglobal/
            `-- *_func_preproc.nii.gz
```

Ejemplo en PowerShell:

```powershell
$env:ABIDE_DATA_ROOT = "D:\ruta\a\datos"
```

La carpeta `data/ABIDE_pcp/cpac/` puede contener una muestra local para pruebas,
pero no representa por si sola la cohorte de 723 sujetos usada en la corrida
principal.
