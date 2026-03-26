# 🔐 Configuración de llaves SSH para GitHub
Guía paso a paso para generar y configurar llaves SSH en Windows y conectarse a GitHub.
## 📌 Requisitos
- Tener Git instalado ([descargar](https://git-scm.com/downloads))
- Una cuenta en [GitHub](https://github.com)

## 1️⃣ Generar la llave SSH

Abrí **Git Bash** o **CMD** y ejecutá:

```bash
ssh-keygen -t ed25519 -C "tu-email@ejemplo.com"
ssh-keygen -t ed25519 -C "joaquinramoscristeche@gmail.com"
Presionás Enter para aceptar la ubicación por defecto: C:\Users\usuario\.ssh\id_ed25519

Te pedirá una frase de contraseña (opcional): podés ponerla o dejarla vacía presionando Enter dos veces

---

## 2 Verificar que se crearon los archivos
dir C:\Users\usuario\.ssh
Debe mostrarte:
id_ed25519 (llave privada - no compartir)
id_ed25519.pub (llave pública)

---

## 3 Iniciar el agente SSH y agregar la llave
eval $(ssh-agent -s)
ssh-add C:\Users\usuario\.ssh\id_ed25519

---

## 4. Copiar la clave pública
type C:\Users\usuario\.ssh\id_ed25519.pub
#Seleccionás y copiás TODO el texto (empieza con ssh-ed25519 y termina con tu email)

---

## 5. Agregar la clave en GitHub
Entrar a GitHub.com → Settings (foto de perfil arriba a la derecha)

En el menú izquierdo: SSH and GPG keys

Click en "New SSH key"

Title: un nombre descriptivo (ej: "Mi PC")

Key: pegar la clave pública copiada

Click en "Add SSH key"

---

## 6. Probar la conexión
bash
ssh -T git@github.com
Si es la primera conexión: escribí yes y Enter

Hi TU_USUARIO! You've successfully authenticated, but GitHub does not provide shell access.






