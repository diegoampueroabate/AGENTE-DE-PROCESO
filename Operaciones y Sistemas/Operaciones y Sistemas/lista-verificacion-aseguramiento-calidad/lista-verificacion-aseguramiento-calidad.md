---
name: lista-verificacion-aseguramiento-calidad
description: "Crea listas de verificación de control de calidad estandarizadas para productos, servicios o procesos para garantizar consistencia."
allowed-tools: Read Write Glob
metadata:
  author: Imperio Digital
  version: "1.0"
---

# Lista de Verificación de Aseguramiento de Calidad

## Cuándo Usar Este Skill

Usa este skill cuando necesites:
- Establecer estándares de calidad
- Crear listas de verificación antes de lanzamiento
- Reducir defectos y devoluciones
- Entrenar al equipo en calidad

---

## Principio Fundamental

LA CALIDAD NO ES LUJO — ES CONSISTENCIA. UN CHECKLIST DE CALIDAD GARANTIZA CONSISTENCIA INCLUSO CUANDO EL EQUIPO ESTÁ OCUPADO.

---

## Fase 1: Definir Estándares

¿Qué significa "hecho"?

### Criterios de Aceptación

Para cada producto/servicio, define:
- Qué debe estar presente
- Qué debe funcionar
- Qué debe estar libre de defectos

---

## Fase 2: Crear Checklist

Documenta cada verificación.

### Plantilla de Checklist

```
## Checklist de QA: [Producto/Servicio]

### Funcionalidad
- [ ] [Característica] funciona según lo especificado
- [ ] [Característica] no causa errores

### Apariencia
- [ ] [Aspecto] cumple con estándar
- [ ] Sin typos o errores

### Completitud
- [ ] Todos los elementos requeridos presentes
- [ ] Documentación incluida

### Propósito
[ ] Verificación final por QA
```

---

## Fase 3: Implementar

Integra checklist en proceso.

### Punto de Control de QA

- **Cuándo:** Antes de cualquier entrega o lanzamiento
- **Quién:** Persona diferente a quien creó
- **Cómo:** Completar checklist físicamente
- **Qué si falla:** Regresar a desarrollo, no liberar

---

## Anti-Patrones

- **Checklist demasiado largo** — se vuelve tedioso
- **Estándares poco claros** — "mira bien" es subjetivo
- **QA como enseña de aduana** — equipo evita hacerlo bien
- **Sin consecuencias por falla** — checklist se convierte en teatro

---

## Recuperación

- **Los errores pasan QA:** Especifica mejor, entrena más
- **Checklist nunca se completa:** Acórtalo, hazlo más específico
- **Equipo evade QA:** Hazlo mandatorio, muestra impacto de defectos
