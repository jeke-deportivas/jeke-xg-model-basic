# ⚽ Power Curve xG - Experimento en Jupyter

Este repositorio contiene un **notebook Jupyter** que reproduce el experimento de [Jeke Deportivas en YouTube](https://youtu.be/0gqfQWc6teQ) sobre la **curva de potencia para modelar goles esperados (xG)** en fútbol, utilizando datos de [Understat](https://understat.com).

## 📦 Requisitos

- Python 3.10 o superior
- [pip](https://pip.pypa.io/en/stable/)
- Jupyter Notebook o Jupyter Lab

## 🚀 Instalación

Clona el repo y crea un entorno virtual:

```bash
git clone https://github.com/jeke-deportivas/jeke-xg-model-basic.git
cd jeke-xg-model-basic
python3 -m venv venv
source venv/bin/activate
````

Instala dependencias (jupyter notebook):

```bash
pip install jupyter
```

## ▶️ Uso

1. Lanza Jupyter Lab o Notebook:

   ```bash
   jupyter lab
   ```

   o

   ```bash
   jupyter notebook
   ```

2. Abre el archivo `jeke-xg-model-prototype.ipynb`.

3. Ejecuta las celdas en orden.
   El notebook descarga los datos de **Understat** para la liga y temporada definidas en:

   ```python
   LEAGUE = "EPL"     # "EPL", "La_Liga", "Bundesliga", "Serie_A", "Ligue_1", "RFPL"
   SEASON = "2024"
   ```

   y luego entrena la **Power Curve** para estimar probabilidades de gol en función de la distancia.

## 📊 Qué hace este notebook

* Descarga todos los partidos de una liga/temporada desde Understat.
* Extrae tiros y calcula distancia → probabilidad de gol.
* Ajusta una curva de potencia $p(\text{gol}) = a \cdot d^b$.
* Evalúa el modelo con métrica R².
* Muestra resultados por equipo, temporada y condición local/visitante.

## 📝 Notas

* La librería `understatapi` usa scraping, por lo que puede tardar algunos minutos en descargar toda una temporada.
* Para evitar bloqueos, el código incluye `sleep` entre requests.
* Los resultados son **experimentales** y están pensados como base para exploración y aprendizaje.


## 📄 Licencia

Este código está bajo la licencia MIT.  
© 2025 **Jeke Deportivas**
