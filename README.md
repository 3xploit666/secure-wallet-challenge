# SecureWallet Challenge

![SecureWallet](secure_wallet_hero.png)

> Dos niveles. Misma app. Dificultad completamente diferente.

Un entorno de practica para ejercitar tus habilidades de ingenieria inversa en iOS frente a protecciones modernas (RASP).

---

## Level 1 — Profesional

> **Objetivo:** Lograr que la aplicacion muestre la pantalla "Authorized".

La aplicacion detectara si tu dispositivo esta jailbreakeado, siendo depurado, hookeado con Frida o corriendo en simulador. Si detecta cualquiera de estas amenazas, se autodestruira.

### Defensas
- Talsec RASP Engine (v6.14.0)
- Stripped Symbols
- Swift ABI con Protocol Witness Tables
- Terminacion agresiva ante deteccion

### Habilidades Requeridas
- Reconocimiento forense de frameworks y strings
- Ingenieria inversa estatica (Ghidra / Binary Ninja / IDA Pro)
- Comprension de Swift internals
- Binary patching ARM64

### Descarga

> **[SecureWallet.ipa](https://github.com/3xploit666/secure-wallet-challenge/raw/main/SecureWallet.ipa)**

---

## Level 2 — Hardcore

> **Objetivo:** Extraer el **flag** oculto en el binario.

SecureWallet v2 es un rediseno arquitectonico completo. Todo lo que funcionaba en el Level 1 aqui **no sirve**.

### Lo Que Sabemos
- Hookear una sola funcion **no funciona**. La app tiene mecanismos independientes que validan la integridad.
- La app detecta instrumentacion dinamica y **termina el proceso en milisegundos** usando metodos que no puedes interceptar facilmente.
- No hay logs, no hay prints, no hay pistas en la UI. **Zero info leaks.**
- El monitoreo es **continuo**. Adjuntar herramientas despues del arranque tambien falla.
- Los strings sensibles no existen como texto plano en el binario.
- `get-task-allow: false` — sin debugger en dispositivos no-jailbroken.

### Habilidades Requeridas
Todo lo del Level 1, mas:
- Analisis estatico avanzado (decompilacion y trazado de flujo sin ejecutar la app)
- Criptanalisis basico (identificacion de esquemas de cifrado en el binario)
- Cross-reference tracing
- Python/scripting para descifrado offline

### Descarga

> **[SecureWallet_v2.ipa](https://github.com/3xploit666/secure-wallet-challenge/raw/main/SecureWallet_v2.ipa)**

---

## Tech Specs

| Spec | Level 1 | Level 2 |
|------|---------|---------|
| **Language** | Swift 5 | Swift 5, `swiftc -O` |
| **Architecture** | ARM64 | ARM64 |
| **Symbols** | Stripped | Stripped (`strip -rSTx`) |
| **RASP** | Talsec v6.14.0 | Talsec v6.14.0 |
| **Target** | iOS 14.0+ | iOS 14.0+ |
| **Entitlements** | `get-task-allow: true` | `get-task-allow: false` |

## Instalacion

1. **TrollStore** (Recomendado)
2. **Sideloadly** / **AltStore**
3. **Filza** con AppSync Unified

## Write-up

El analisis tecnico completo esta disponible en el blog:
[SecureWallet Challenge: Del One-Liner al Hardcore](https://www.3xploitdev.com/blog/secure-wallet-challenge)

---

*Desarrollado por 3xploit666*
*Solo para fines educativos y de investigacion en seguridad defensiva.*
