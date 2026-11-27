# Guía de contribución

## Reglas

1. Todo trabajo parte de un issue.
2. Nadie hace push directo a `main`; todo entra por Pull Request.
3. Todo PR requiere la aprobación de un revisor antes del merge.

## Flujo

`issue → rama → commits → Pull Request → revisión → merge`

1. Asignate un issue del sprint y movelo a **In progress**.
2. Creá la rama partiendo de `main` con el formato de la sección **Ramas**. Si usás *Development → Create a branch* del issue, renombrala para respetar el prefijo.
3. Traela a local:
   ```bash
   git fetch
   git checkout tipo/numero-issue-descripcion-corta
   ```
4. Trabajá con commits chicos y subí los cambios:
   ```bash
   git push
   ```
5. Abrí el PR hacia `main` con `Closes #numero` y un revisor asignado. La tarjeta pasa a **In review**.
6. Si piden cambios, subilos a la misma rama (el PR se actualiza solo).
7. Con la aprobación, el autor hace **Squash and merge** y **Delete branch**. La tarjeta pasa a **Done** automáticamente.

## Ramas

- Una rama por issue; no se reutilizan.
- Formato: `tipo/numero-issue-descripcion-corta` (minúsculas, sin tildes, con guiones).
- El prefijo de la rama coincide con el tipo del commit.

| Tipo | Uso | Ejemplo |
|---|---|---|
| `feat/` | Funcionalidad nueva | `feat/12-animacion-saludo` |
| `fix/` | Corrección de error | `fix/18-voz-se-corta` |
| `docs/` | Solo documentación | `docs/20-guia-instalacion` |
| `refactor/` | Mejora interna sin cambiar comportamiento | `refactor/25-ordenar-componentes` |
| `test/` | Solo pruebas | `test/21-prueba-saludo-inicial` |
| `chore/` | Configuración, dependencias, herramientas | `chore/9-gitignore` |

## Commits

- Formato: `tipo: qué hace` (español, presente, sin punto final).
- Sin tildes en el mensaje (igual que en las ramas).
- Describen el cambio, no la acción de quien lo hizo.

| Tipo | Uso | Ejemplo |
|---|---|---|
| `feat` | Funcionalidad nueva | `feat: agrega parpadeo al personaje` |
| `fix` | Corrección de error | `fix: corrige corte de voz al responder` |
| `docs` | Documentación | `docs: explica como instalar el proyecto` |
| `refactor` | Refactor sin cambio de comportamiento | `refactor: separa la animacion en componentes` |
| `test` | Pruebas | `test: prueba el saludo inicial` |
| `chore` | Configuración, dependencias | `chore: actualiza dependencias` |

## Pull Requests

- Título con el mismo formato que un commit (reemplaza los mensajes al hacer squash).
- Descripción: qué cambia y cómo probarlo.
- Vínculo al issue con `Closes #numero`.
- Revisor distinto del autor. Usá **Draft** si querés feedback antes de que esté listo.
- Merge: *Squash and merge* + *Delete branch*.

## Issues

- Título: verbo + resultado (ej. `Corregir el corte de voz al responder`).
- Debe incluir: qué hacer, criterio de terminado, responsable y etiqueta.
- Etiquetas: `bug`, `docs`, `frontend`, `animacion`, `investigacion`, `bloqueado`, `buena-primera-tarea`.
- Un error encontrado durante otra tarea va en un issue nuevo con `bug`, no en la rama actual.
- Los issues de investigación no usan rama: se cierran a mano con la conclusión escrita en el issue.

## Documentación

- Si un PR cambia el funcionamiento de algo, actualiza `/docs` en el mismo PR.
- Las decisiones importantes se registran en `/docs/decisiones`, un archivo por decisión (contexto, decisión, motivo).
