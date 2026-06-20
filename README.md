# Plataforma Cloud para Análisis de Microemprendimientos y Predicción de Sostenibilidad Económica

Este repositorio contiene el sistema integral desarrollado para la evaluación de viabilidad financiera y predicción de riesgo de insolvencia en microemprendimientos utilizando modelos avanzados de Machine Learning.

---

##  Integrantes del Proyecto (DSSMD)
* **Escalante Cordero Diego Jhamil**
* **Fernández Flores Melvin Mijael**
* **Merida Quispe Denshel David**
* **Soliz Villca Saily Mayber**

* **Materia:** Tecnologías Emergentes I - Paralelo "A"
* **Docente:** Ing. Miguel Pacheco Arteaga
* **Institución:** Universidad Privada del Valle (UNIVALLE)
* **Gestión:** 2026

---

## 🏛️ 1. Diagrama de Arquitectura del Sistema

La plataforma está diseñada bajo un principio de desacoplamiento modular, optimizada para entornos cloud y alta disponibilidad (99.9%), garantizando una ejecución ligera en el frontend y un aislamiento completo del motor analítico.

```text
+--------------------------------------------------------+
|                  INTERFAZ DE USUARIO                   |
|       Streamlit Web UI / React Frontend Component      |
+---------------------------+----------------------------+
                            |
                            | Petición de Inferencia (JSON)
                            v
+--------------------------------------------------------+
|               CORE ENGINE / BACKEND API                |
|             (Módulo de Inferencia Python)              |
+---------------------------+----------------------------+
                            |
         +------------------+------------------+
         | Carga del Modelo                    | Registro de Logs
         v                                     v
+-----------------------+            +-----------------------+
|   MOTOR DE IA (.PKL)  |            |  MÓDULO AUDITORÍA     |
|   Random Forest Engine|            |  Persistencia (.CSV)  |
+-----------------------+            +-----------------------+
         |                                     |
         v (Predicción)                        v (Almacenamiento)
   [ALTO / MEDIO / BAJO]               [base_auditoria.csv]
