# PARTE 6 — Full Stack Open

Testing, entorno de desarrollo y despliegue.

## Estructura

```
PARTE6/
├── src/
│   └── api/
│       └── app.js           # Servidor Express con endpoints CRUD
├── package.json
└── README.md
```

## Servidor Express

El servidor provee los siguientes endpoints:

- **GET /api/persons** — Retorna la lista completa de personas
- **POST /api/persons** — Añade una nueva persona (valida que name y number estén presentes)
- **DELETE /api/persons/:id** — Elimina una persona por su ID

### Flujo de operaciones

1. **Listar:** `GET /api/persons` retorna JSON con todos los persons
2. **Añadir:** POST con `{ name, number }`. Si falta algún campo, retorna 400 error
3. **Eliminar:** DELETE a `/api/persons/:id` filtra y remueve la persona

### Variables de entorno

- `PORT` — Puerto del servidor (default: 3001)
- `MONGODB_URI` — URI de conexión a MongoDB (opcional, para la Parte 3)

## Despliegue

La aplicación se puede desplegar en:

- **Render.com** — Configurar el servicio Node.js, establecer variable `PORT`
- **Railway** — Importar repositorio, las variables se configuran en dashboard
- **Heroku** — `git push heroku main`, setear config vars

## Scripts útiles

```bash
# Iniciar servidor
npm start

# Ejemplo de test con supertest (externo)
# const api = await request(app).get('/api/persons')
```