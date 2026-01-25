# ⚽ Modelo xG con Decaimiento Exponencial

Modelo de **goles esperados (xG)** basado en distancia euclidiana y decaimiento exponencial, con un **R² = 0.947**.

## 📐 Fórmula

```
xG = e^(-d/k) × a + b
```

Donde `d = √(dx² + dy²)` es la distancia euclidiana al centro de la portería (teorema de Pitágoras).

## 🧪 Pruébalo sin instalar nada

| Notebook | Descripción |
|----------|-------------|
| [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jeke-deportivas/jeke-xg-model-basic/main?urlpath=%2Fdoc%2Ftree%2Fjeke-xg-lite.ipynb) | **Lite** - Solo Inputs Jeknica Poisson |
| [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jeke-deportivas/jeke-xg-model-basic/main?urlpath=%2Fdoc%2Ftree%2Fjeke-xg-model.ipynb) | **Modelo** - Solo exponencial + rankings |
| [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jeke-deportivas/jeke-xg-model-basic/main?urlpath=%2Fdoc%2Ftree%2Fjeke-xg-model-prototype.ipynb) | **Prototipo** - Proceso completo, compara modelos |

## 📦 Requisitos

- **Python 3.13.11** (recomendado usar [pyenv](https://github.com/pyenv/pyenv))
- [pip](https://pip.pypa.io/en/stable/)

## 🚀 Instalación

```bash
git clone https://github.com/jeke-deportivas/jeke-xg-model-basic.git
cd jeke-xg-model-basic
bin/setup
source .venv/bin/activate
```

## ▶️ Uso

1. Lanza Jupyter Lab:

   ```bash
   jupyter lab
   ```

2. Abre el archivo `jeke-xg-model-prototype.ipynb`.

3. Selecciona el kernel **Python (jeke-xg)**.

4. Ejecuta las celdas en orden.
   El notebook descarga los datos de **Understat** para la liga y temporadas definidas en:

   ```python
   LEAGUE = "EPL"     # "EPL", "La_Liga", "Bundesliga", "Serie_A", "Ligue_1", "RFPL"
   SEASON = ["2024", "2025"]
   ```

## 📊 Qué hace cada notebook

### Lite (`jeke-xg-lite.ipynb`)
* Descarga tiros de una liga/temporada desde Understat
* Calcula xG con modelo exponencial
* Genera inputs Jeknica Poisson por equipo

### Modelo (`jeke-xg-model.ipynb`)
* Proceso educativo del modelo exponencial
* Rankings ofensivos y defensivos por equipo
* Análisis por jugador: xG, xA y over/under performance
* Consulta de xG por partido

### Prototipo (`jeke-xg-model-prototype.ipynb`)
* Proceso completo de investigación
* Compara tres modelos:
  | Modelo | R² |
  |--------|-----|
  | Longitudinal (solo X) | 0.888 |
  | Euclidiano (X + Y) | 0.917 |
  | **Decaimiento Exponencial** | **0.947** |

## 📝 Notas

* La librería `jeke-understat-scrapper` usa scraping, por lo que puede tardar algunos minutos en descargar toda una temporada.
* Para evitar bloqueos, el código incluye `sleep` entre requests.

## 📄 Licencia

Este código está bajo la licencia MIT.
© 2025 **Jeke Deportivas**
