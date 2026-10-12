# PERSONAL.EXE: Agenda secreta de personal

**Privada. Local. Sin internet. Cifrada con contraseña (AES-256).**

Una agenda de registro de personal que vive **solo en tu computadora**. No se conecta a internet, no usa servidores y no envía nada a nadie: lo que escribes se queda en tu PC y se guarda **cifrado**. Sin tu contraseña, los datos no se pueden leer.

**Contenido:** [Requisitos](#requisitos) | [Abrir el programa](#abrir-el-programa) | [Primer uso](#primer-uso) | [Uso diario](#uso-diario) | [Backups](#backups-cifrados) | [Seguridad](#seguridad) | [Tus datos](#dónde-quedan-tus-datos) | [Problemas](#problemas-frecuentes)

## Resumen rápido

1. Extrae `PERSONAL-win64.zip` en una carpeta fija, por ejemplo `C:\AgendaSecreta`.
2. Abre `PERSONAL.exe`.
3. La primera vez, crea tu contraseña maestra.
4. Registra personal y haz backups con regularidad.

---

## Requisitos

- Windows 10 u 11 de 64 bits.
- Unos 400 MB libres en disco.
- Nada más: **no hay que instalar nada**.

---

## Abrir el programa

### Paso 1: Extrae el ZIP

1. Clic derecho sobre `PERSONAL-win64.zip`.
2. Elige **Extraer todo...**
3. Escoge una ubicación fija y privada, por ejemplo `C:\AgendaSecreta`. Evita la carpeta *Descargas*: es la que más se limpia por accidente.
4. Pulsa **Extraer** y espera a que termine (son muchos archivos).

> **Advertencia:** nunca abras el `.exe` desde dentro del ZIP. Extráelo siempre primero.

### Paso 2: Abre el programa

1. Entra en `C:\AgendaSecreta\PERSONAL-win32-x64`.
2. Haz doble clic en **`PERSONAL.exe`** (el que tiene el icono del programa).
3. La primera vez puede tardar unos segundos en abrir.

### Paso 3: Si aparece "Windows protegió su PC"

Es normal la primera vez: el programa está hecho a medida y no tiene firma digital comercial.

1. Pulsa **Más información**.
2. Pulsa **Ejecutar de todas formas**.

> **Consejo:** si tu antivirus lo bloquea, agrega la carpeta `C:\AgendaSecreta` a las excepciones.

### Paso 4: Crea accesos rápidos (una sola vez)

> **Importante:** no saques `PERSONAL.exe` solo de su carpeta, porque necesita los archivos que lo acompañan. Usa accesos directos.

| Dónde | Cómo |
|---|---|
| **Escritorio** | Clic derecho en `PERSONAL.exe`, luego *(en Windows 11: **Mostrar más opciones**)*, **Enviar a** y **Escritorio (crear acceso directo)** |
| **Barra de tareas** | Con el programa abierto, clic derecho en su icono de la barra y **Anclar a la barra de tareas** |
| **Menú Inicio** | Clic derecho en `PERSONAL.exe` y **Anclar a Inicio** |

---

## Primer uso

### Paso 5: Crea tu contraseña maestra (solo la primera vez)

1. Al abrir por primera vez aparece **Crear bóveda**.
2. Escribe una contraseña de **8 caracteres o más** (mejor una frase de 12 o más) dos veces y pulsa **Crear y entrar**.
3. Anótala en un lugar físico seguro.

> **Muy importante:** no existe recuperación de contraseña. Si la olvidas, tus datos no se pueden recuperar, ni por ti ni por nadie.

Si venías de la versión anterior (sin contraseña), tus registros se cifran automáticamente al crear la bóveda y la copia sin cifrar se elimina.

---

## Uso diario

### Paso 6: Trabajar con la agenda

1. Abre `PERSONAL.exe`, escribe tu contraseña y pulsa **Entrar**. Tras un intento fallido hay una espera que aumenta con cada error.
2. Completa el **Formulario de Alta** (los campos con `*` son obligatorios) y pulsa **Guardar registro**. Cada cambio se guarda y se cifra al instante.
3. En la **Base de Datos**, haz clic en una persona para ver su ficha. Desde ahí puedes **Editar** o **Eliminar**. El buscador filtra por DNI, nombre o apellido.
4. Al terminar, pulsa **Bloquear ahora**. Si olvidas hacerlo, la agenda se bloquea sola tras **5 minutos** sin actividad y borra los datos de la pantalla.
5. Para cambiar la contraseña usa **Cambiar contraseña**: pide la actual y la nueva, y los datos se vuelven a cifrar.

---

## Backups cifrados

> **Nota:** es lo más importante. Si pierdes el equipo o los datos, el backup es tu única salvaguarda.

### Paso 7: Exportar e importar

1. Pulsa **Exportar Backup**: se descarga un archivo `.json` con la fecha en el nombre. Está **cifrado**: sin la contraseña es ilegible.
2. Haz un respaldo después de cada sesión importante y, como mínimo, **una vez por semana**. Guárdalo en un USB o en otra carpeta.
3. Para restaurar o pasar tus datos a otra PC, abre el programa (crea una bóveda nueva si es la primera vez) y pulsa **Importar Backup**. Si el backup se cifró con otra contraseña, el programa te la pide.
4. Un backup siempre se abre con **la contraseña que tenías al exportarlo**. Si luego cambias de contraseña, conserva la antigua para los backups viejos.
5. Si tienes backups de la versión anterior (sin cifrar), aún se pueden importar. Después de importarlos, **bórralos**: son texto plano.

---

## Seguridad

### Lo que sí hace

- Cifra todos los registros y los backups con **AES-256-GCM**, con una llave derivada de tu contraseña (**PBKDF2-SHA256**, 600 000 iteraciones y sal aleatoria propia).
- Detecta si alguien altera los datos cifrados: el programa se niega a abrirlos.
- Funciona 100 % sin internet; no hay telemetría ni servidores.
- Bloqueo automático por inactividad y botón de bloqueo manual.
- La contraseña nunca se guarda: solo existe en memoria mientras la agenda está abierta.

### Lo que no hace

- No te protege de virus, *keyloggers* u otro malware instalado en tu PC, ni de alguien que mire la pantalla mientras está abierta.
- Su fuerza depende de tu contraseña: una corta o predecible se puede adivinar por fuerza bruta si alguien copia tus datos. **Usa una frase larga y única.**
- No oculta que el archivo existe ni su tamaño aproximado.

### Buenas prácticas

1. Contraseña de Windows y bloqueo con <kbd>Windows</kbd> + <kbd>L</kbd> al alejarte.
2. Cifrado de disco (BitLocker o *Cifrado de dispositivo*) como segunda capa.
3. No guardes la contraseña en el mismo USB que los backups.
4. Los registros contienen datos personales de terceros (DNI, teléfono, dirección): manéjalos con cuidado.

---

## Dónde quedan tus datos

```text
%APPDATA%\PERSONAL.EXE
```

Para abrir esa carpeta presiona <kbd>Windows</kbd> + <kbd>R</kbd>, escribe la ruta de arriba y pulsa <kbd>Enter</kbd>.

- Los datos están cifrados: aunque alguien copie la carpeta, no puede leerlos sin tu contraseña.
- Mover o reemplazar la carpeta del programa **no** borra tus datos.
- Borrar la carpeta `%APPDATA%\PERSONAL.EXE` **sí** los borra. Haz un backup antes.

---

## Problemas frecuentes

| Problema | Solución |
|---|---|
| **No abre** | Comprueba que extrajiste el ZIP completo y que abres `PERSONAL.exe` desde su carpeta, no desde el ZIP. |
| **Pantalla en blanco** | Espera unos segundos; si sigue igual, cierra y vuelve a abrir. |
| **Contraseña incorrecta** | Revisa mayúsculas y teclado. Tras varios fallos hay que esperar unos segundos entre intentos. |
| **Olvidé mi contraseña** | No se puede recuperar. Solo te queda restaurar un backup si recuerdas la contraseña con la que se exportó, o empezar de cero borrando `%APPDATA%\PERSONAL.EXE`. |
| **No veo mis registros** | Entra con el mismo usuario de Windows de siempre, o restaura un backup con **Importar Backup**. |
| **Quiero cambiar de PC** | **Exportar Backup** en la PC vieja, copia la carpeta del programa a la nueva, ábrela, crea la bóveda e **Importar Backup**. |
| **Quiero desinstalarlo** | Borra la carpeta `C:\AgendaSecreta`. Si también quieres borrar los datos, borra `%APPDATA%\PERSONAL.EXE`. |
