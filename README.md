#  Taller 01 Fork – Sistemas Operativos

**Autor:** Elier Ibarra  
**Materia:** Sistemas Operativos  
**Docente:** John Corredor  
**Universidad:** Pontificia Universidad Javeriana  
**Fecha:** 28/10/2025

---

### 📘 Descripción General
Este repositorio contiene un ejercicio en **C** sobre **creación de procesos** y **comunicación entre procesos** usando **`fork()`** y **pipes** (`dup2` para redirección).  
El proyecto está **documentado, funcional y listo para compilar** con `gcc`.

---

## 📁 Archivos Incluidos

| Archivo        | Descripción                                                                 |
|----------------|------------------------------------------------------------------------------|
| `main.c`       | Proceso **padre**: crea pipes y `fork()`, coordina hijos y muestra resultados. |
| `suma1.c`      | Proceso (hijo/nieto) que **suma** números del archivo 00 y escribe por pipe. |
| `suma2.c`      | Proceso (hijo 2) que **suma** números del archivo 01 y escribe por pipe.      |
| `sumatotal.c`  | Proceso que **combina**/verifica la suma total y la envía al padre.          |
| `leer.c`       | Utilidades de **lectura/parseo** de archivos de texto.                       |
| `leer.h`       | Cabecera para las funciones de lectura.                                      |

---

## 🛠️ Instrucciones de Compilación

> Puedes compilar **rápido con `gcc`** (como en el ejemplo de la foto) o usar un `Makefile`.
> Aquí te dejo la forma directa con gcc para cada ejecutable:

```bash
# Binario principal (padre que orquesta)
gcc -Wall -O2 -std=c11 -pthread main.c leer.c -o taller_procesos

# Ejecutables auxiliares (si requieren utilidades de lectura, enlaza leer.c):
gcc -Wall -O2 -std=c11 -pthread suma1.c leer.c -o suma1
gcc -Wall -O2 -std=c11 -pthread suma2.c leer.c -o suma2
gcc -Wall -O2 -std=c11 -pthread sumatotal.c leer.c -o sumatotal
