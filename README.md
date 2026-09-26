# GraalClang 🚀

**GraalClang** es una implementación de alto rendimiento del entorno y lenguaje de compilación **C/C++ (basado en Clang/LLVM)**, desarrollada sobre **GraalVM** utilizando el framework Truffle y la infraestructura Sulong.

Esta plataforma lleva la ejecución de código C/C++ directamente al runtime de GraalVM mediante la interpretación y compilación JIT (Just-In-Time) de Bitcode de LLVM, permitiendo ejecutar código nativo seguro con recolección de basura gestionada, optimizaciones dinámicas e interoperabilidad de cero copia con todo el ecosistema políglota.

---

## 🌟 Características Principales

* **Ejecución Segura de LLVM Bitcode:** Interpretación y compilación JIT dinámica de Bitcode producido por Clang mediante Truffle (Sulong Engine), ofreciendo aislamiento de memoria y mitigación de errores comunes de punteros.
* **Optimizaciones Dinámicas JIT:** Aplicación de *inlining* cruzado entre código C/C++ y lenguajes de alto nivel (como Java, Python o JavaScript) en tiempo de ejecución.
* **Interoperabilidad Políglota de Cero Copia:** Invocación bi-direccional directa entre funciones C/C++ y objetos gestionados en la JVM sin sobrecostes de serialización o bindings C-FFI manuales.
* **Despliegue Nativo (Native Image):** Empaquetado de aplicaciones C/C++ junto con el entorno políglota en binarios autónomos utilizando **GraalVM Native Image**.

---

## 🏗️ Arquitectura de la Plataforma

* **Clang LLVM Front-End:** Compila el código fuente C/C++ a archivos de Bitcode (`.bc`) optimizados para ser consumidos por el runtime.
* **Sulong Truffle Engine:** Motor de ejecución que traduce las instrucciones del Bitcode de LLVM a nodos de Árbol de Sintaxis Abstracta (AST) de Truffle.
* **Polyglot Interop API:** Interfaz para exponer estructuras de C (`struct`), punteros a funciones y arreglos de memoria hacia otros lenguajes de la plataforma GraalVM.

---

## 🚦 Inicio Rápido

### Prerrequisitos

* **GraalVM JDK** (versión 21 o superior) con componentes de LLVM/Sulong habilitados.
* Toolchain de **Clang/LLVM** instalado en el sistema.
* Variable de entorno `JAVA_HOME` apuntando al directorio de instalación de GraalVM.

### Instalación

```bash
# Clonar el repositorio
git clone [https://github.com/tu-usuario/graal-clang.git](https://github.com/tu-usuario/graal-clang.git)
cd graal-clang

# Construir el proyecto utilizando Gradle
./gradlew build
