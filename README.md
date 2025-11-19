# 🧪 Restful Booker API Testing — Postman + Newman

Este proyecto contiene una suite completa de pruebas API automatizadas usando **Postman**, **Variables**, **Environments**, **Colecciones** y **Newman CLI**.

El objetivo es simular un flujo real de QA Automation para una API pública (Restful Booker).

---

## 🚀 Tecnologías utilizadas

- **Postman**  
- **Newman (CLI)**  
- **Node.js** (para ejecutar Newman)  
- **Restful Booker API** (pública)

---


## 📁 Estructura del repositorio

postman-restfulbooker-automation/

│

├── collections/

│ └── RestfulBooker.postman_collection.json

│

├── environments/

│ └── RestfulBooker-Prod.postman_environment.json

│

├── docs/

│ └── Postman_Project_Fases.pdf ← Documentación del proyecto

│

└── README.md


---


## 🏗 Descripción del proyecto

Este proyecto realiza pruebas automatizadas sobre la API pública **Restful Booker**, cubriendo:

- Autenticación (token dinámico)
- Crear reservas (POST)
- Obtener reservas (GET)
- Actualizar reservas (PUT)
- Eliminar reservas (DELETE)
- Validaciones automáticas con scripts de test
- Variables globales, de entorno e internas
- Ejecución por consola con **Newman**
- Generación de reportes HTML

---


## 🌐 API Base

https://restful-booker.herokuapp.com


---


## 🔧 Configuración inicial

### 📌 1. Clonar repositorio

git clone https://github.com/TU_USUARIO/postman-restfulbooker-automation.git
cd postman-restfulbooker-automation


### 🧩 2. Importar colección y environment
En Postman:

Import → Collection:
collections/RestfulBooker.postman_collection.json

Import → Environment:
environments/RestfulBooker-Prod.postman_environment.json


### 🔑 3. Variables de entorno configuradas
Variable	Descripción
baseUrl	URL base de la API
bookingId	ID dinámico de la reserva creada
token	Token generado para acciones protegidas


---


## 🧪 Suites de prueba incluidas
✔ Smoke Suite
- Create Token
- Get Booking

✔ Regression Suite
- Create Token
- Create Booking
- Get Booking
- Update Booking
- Delete Booking

---


## 📝 Scripts de Test incluidos

### Guardar token:

let json = pm.response.json();
pm.environment.set("token", json.token);
Guardar bookingId:

let json = pm.response.json();
pm.environment.set("bookingId", json.bookingid);
Validar respuestas:

pm.test("Status code 200", () => {
    pm.response.to.have.status(200);
});


---


## 🖥 Ejecutar pruebas con Newman
1. Instalar Newman:
npm install -g newman

2. Ejecutar colección:
newman run collections/RestfulBooker.postman_collection.json -e environments/RestfulBooker-Prod.postman_environment.json

## 📊 Reporte HTML (recomendado)
1. Instalar reporter:
npm install -g newman-reporter-htmlextra

2. Ejecutar:
newman run collections/RestfulBooker.postman_collection.json \
  -e environments/RestfulBooker-Prod.postman_environment.json \
  -r htmlextra
  
3. El reporte se guardará en:
  newman/
    └── RestfulBooker API Tests-report.html

---

  
## 📚 Documentación del proyecto
Disponible en:

📄 docs/Postman_Project_Fases.pdf

Contiene todas las Fases, paso a paso, incluyendo:

- Workspace
- Environments
- Variables
- Colecciones
- CRUD
- Suites
- Newman CLI
- Reportes


---


##👩‍💻 Autor
SophxDev - Software Developer & QA Automation.
🔗 LinkedIn: https://www.linkedin.com/in/jaquelineespino/


---
