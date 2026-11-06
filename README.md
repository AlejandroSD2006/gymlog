# GymLog

Registro de entrenamientos en una sola página: organiza tus rutinas, apunta los ejercicios y guarda cómo evolucionan el peso, las series y las repeticiones.

![HTML](https://img.shields.io/badge/HTML-151A21?style=flat-square&logo=html5&logoColor=5EEAD4)
![CSS](https://img.shields.io/badge/CSS-151A21?style=flat-square&logo=css&logoColor=5EEAD4)
![JavaScript](https://img.shields.io/badge/JavaScript-151A21?style=flat-square&logo=javascript&logoColor=5EEAD4)

## Qué hace

- **Rutinas**: crea y elimina rutinas (por ejemplo, "Pierna" o "Empuje").
- **Ejercicios**: añade ejercicios a cada rutina; cada uno se despliega para ver su historial.
- **Progreso**: registra peso (kg), repeticiones, series (opcional) y una nota. Cada registro guarda la fecha automáticamente.
- **Persistencia**: los datos se guardan en el navegador; no hace falta cuenta ni conexión.

## Uso

No tiene dependencias ni paso de compilación. Abre `index.html` en el navegador.

## Cómo está hecho

Todo el código (HTML, CSS y JavaScript sin librerías) está en `index.html`. El estado es un único objeto guardado en `localStorage` bajo la clave `gymlog`:

```
routines[]
  ├─ id, name
  └─ exercises[]
       ├─ id, name
       └─ progress[]   → { weight, reps, sets, note, date }
```

Cada cambio de interfaz pasa por una función que modifica ese objeto, lo guarda y vuelve a pintar la vista.

## Limitaciones

- Los datos están ligados al navegador y al dispositivo donde se crearon; no hay sincronización ni exportación.
- Sin gráficas de evolución: el historial se muestra como lista.
