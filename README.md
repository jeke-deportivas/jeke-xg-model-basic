# ⚽ Power Curve xG - Experimento en Jupyter
Este repositorio contiene un **notebook Jupyter** que reproduce el experimento de [Jeke Deportivas en YouTube](https://youtu.be/0gqfQWc6teQ) sobre la **curva de potencia para modelar goles esperados (xG)** en fútbol, utilizando datos de [Understat](https://understat.com).

## 🧪 Pruébalo sin instalar nada
👉 [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jeke-deportivas/jeke-xg-model-basic/main?urlpath=%2Fdoc%2Ftree%2Fjeke-xg-model-prototype.ipynb) <<<

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

   y luego entrena la **Power Curve** para estimar probabilidades de gol en función de la distancia.

## 📊 Qué hace este notebook

* Descarga todos los partidos de una liga/temporadas desde Understat.
* Extrae tiros y calcula distancia → probabilidad de gol.
* Ajusta una curva de potencia \$p(\text{gol}) = a \cdot d^b\$.
* Evalúa el modelo con métrica R².
* Muestra resultados por equipo, temporada y condición local/visitante.

## 📝 Notas

* La librería `understatapi` usa scraping, por lo que puede tardar algunos minutos en descargar toda una temporada.
* Para evitar bloqueos, el código incluye `sleep` entre requests.
* Los resultados son **experimentales** y están pensados como base para exploración y aprendizaje.

## 📄 Licencia

Este código está bajo la licencia MIT.
© 2025 **Jeke Deportivas**
