<h1 align="center">Desafío - AMIGO SECRETO</h1>

![Visualización del desafío "Amigo Secreto"](https://github.com/user-attachments/assets/0cf6b184-2523-4ae7-ab14-b673e34cee98)

<h2>Descripción</h2>
<p>Un proyecto de parte de Alura haciendo un juego demostrando el desarrollo en programación principalmente en Javascript.</p>

<h3>Partes del proyectos</h3>

. Archivo "index.html": Se uso una estructura simple para tener claro donde se trabajara al usar clases e id.  

. Archivo "style.html": El diseño es prolijo manteniendo un orden entre los botones sin roce y un espacio considerable entre la lista de nombre que se van agregando.

. Archivo "app.js": Las divisiones creando funciones y documentación concreta de lo que esta preparado cada parte del "index.html".

<h3>Desarrollo del Juego "Amigo Secreto"</h3>

Utilizando los fundamentos básicos de la programación, siguiendo un enfoque estructurado y ordenado. Se explica cómo se implementó la lógica del juego:

### 1. Estructura del Código

El código comenzo con un **array** que almacena los nombres de los amigos ingresados por el usuario. Este array es el corazón del juego, ya que guarda la información necesaria para realizar el sorteo.

```javascript
let amigos = []; // Array para almacenar los nombres
```

### 2. Funciones y Condicionales

Las funciones como división del código en tareas específicas y reutilizables. Un ejemplo, la función "agregarAmigo()" valida si el campo de texto está vacío antes de agregar un nombre al array.

```javascript
function agregarAmigo() {
    const input = document.getElementById('amigo');
    const nombre = input.value.trim();

  if (nombre === "") {
        alert("Por favor, ingresa un nombre válido.");
        return;
    }

    amigos.push(nombre);
    input.value = "";

    actualizarLista();
}
```

### 3. Bucles y Actualización de la Interfaz
Para mostrar los nombres en pantalla, se utiliza un bucle que recorre el array y actualiza la lista visible en la página.

```javascript
function actualizarLista() {
    const listaAmigos = document.getElementById('listaAmigos');
    listaAmigos.innerHTML = "";

    amigos.forEach(amigo => {
        const li = document.createElement('li');
        li.textContent = amigo;
        listaAmigos.appendChild(li);
    });
}
```

### 4. Funcionalidad de los Botones

El juego incluye dos botones principales:

- Sortear Amigo: Selecciona un nombre aleatorio del array y lo muestra en pantalla.

```javascript
function sortearAmigo() {
    if (amigos.length === 0) {
        alert("No hay nombres en la lista para sortear.");
        return;
    }

    const indiceAleatorio = Math.floor(Math.random() * amigos.length);
    const amigoSecreto = amigos[indiceAleatorio];

    const resultado = document.getElementById('resultado');
    resultado.innerHTML = `<li>El amigo secreto es: ${amigoSecreto}</li>`;
}
```

- Nuevo Juego: Reinicia el juego, limpiando la lista de nombres y el resultado del sorteo.

```javascript
function nuevoJuego() {
    amigos = [];
    document.getElementById('listaAmigos').innerHTML = "";
    document.getElementById('resultado').innerHTML = "";
    alert("¡Nuevo juego iniciado! Puedes agregar nuevos nombres.");
}
```

### 5. Conclusión
Este proyecto demuestra la implementación de las bases de la programación (variables, funciones, condicionales, bucles) para crear una aplicación interactiva y funcional, un ejemplo perfecto para entender cómo la lógica de programación se traduce en una experiencia de usuario tangible.

