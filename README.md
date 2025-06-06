# 📚 Mis Recursos App

Aplicación web para llevar un registro de series, películas y libros vistos o por ver. Los usuarios pueden añadir, editar y eliminar recursos, así como filtrarlos por estado, formato y plataforma.

## 🧩 Tecnologías utilizadas

- **MongoDB** (Base de datos)

## 📁 Estructura de la base de datos (MongoDB)

La base de datos se llama: `mis_recursos_app`

## 🧪 Comandos de creación y prueba en MongoDB
### 🧠 CREAR - base de datos y colecciones
```json
use mis_recursos_app
```
---

### 📌 insertar un recurso : Rogue One
```json
db.recursos.insertOne({
  nombre: "Rogue One",
  genero: "Ciencia Ficción",
  plataforma: "Disney+",
  estado: "Terminado",
  formato: "Película",
  fecha_terminacion: "2024-12-05",
  valoracion: 4,
  resena: "Una gran historia que conecta perfectamente con el Episodio IV."
})
```
---

### 📚 LEER – Ver todos los recursos
```json
db.recursos.find().pretty()
```
---

### 💡 ACTUALIZAR – Modificar datos de un recurso

```json
db.recursos.updateOne(
  { nombre: "Rogue One" },
  {
    $set: {
      estado: "En progreso",
      valoracion: 3,
      resena: "Aún no la termino, pero me gusta."
    }
  }
)
```
---

### ❌ ELIMINAR – Borrar un recurso

```json
db.recursos.deleteOne({ nombre: "Rogue One" })
```
---

## 🔍 FILTRAR y BUSCAR
### Por estado:
```json
db.recursos.find({ "estado": "Pendiente" })
db.recursos.find({ "estado": "En progreso" })
db.recursos.find({ "estado": "Terminado" })
```

### Por formato:
```json
db.recursos.find({ "formato": "Serie" })
db.recursos.find({ "formato": "Película" })
db.recursos.find({ "formato": "Libro" })
```

### Por plataforma:
```json
db.recursos.find({ plataforma: "Netflix" })
db.recursos.find({ plataforma: "Amazon" })
db.recursos.find({ plataforma: "Kindle" })
```

###  Búsqueda por nombre (coincidencia parcial):
```json
db.recursos.find({ nombre: { $regex: "titanic", $options: "i" } })
```

###  Búsqueda exacta
```json
db.recursos.find({ nombre: "Rogue One" }).pretty()
```
---

### 📊 BONUS – Contar documentos
```json
db.recursos.countDocuments()  // Total
db.recursos.countDocuments({ estado: "Pendiente" })  // Solo los pendientes
```
---

## ✅ Funcionalidades del proyecto

	•	Crear nuevos recursos con valoración y reseña
	•	Leer recursos existentes
	•	Editar detalles de un recurso
	•	Eliminar recursos que ya no se deseen conservar
	•	Filtrar por estado, formato o plataforma
	•	Buscar recursos por nombre con texto parcial
	•	Validar datos como:  valoracion entre 1 y 5
	•	fecha_terminacion válida (formato YYYY-MM-DD)
---

## ✍ Autor

💀 **CARLOS DANIEL ARAUZ SANJUAN**  💀
Proyecto académico para el modulo de bases de datos con MongoDB.
