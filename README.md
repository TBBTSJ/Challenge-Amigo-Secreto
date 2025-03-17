<h1 align="center"> Challenge Amigo Secreto </h1>

<h2 alingn="center"> ¡Ingresa los nombres de tus amigos y sortealos para elegir a tu amigo secreto! </h2>

<h4> Primero, veremos la funcionalidad de este proyecto y al final, anexaremos los código utilizados. </h4>
<h5>Esta es la pantalla principal:</h5>

![image](https://github.com/user-attachments/assets/2ae8d77e-3379-4280-a3f2-797dfac2c0e9)

<h5>Ingresa los nombres de tus amigos :smile:</h5>
<h5>Cada que escribas un nombre, debes dar click en el botón "Añadir" para poder guardarlo.</h5>

![image](https://github.com/user-attachments/assets/6d3167d9-b989-4c35-ac4e-4fe884d36715)

![image](https://github.com/user-attachments/assets/cd9c4268-ebdc-40b6-acad-dcdc024307a6)

<h5>Entonces los nombres de tus amigos se irán agregando a la lista que aparece abajo: :point_down:</h5>

![image](https://github.com/user-attachments/assets/38498703-f95d-4bd9-be11-34fdb9be6666)

<h5>Nota: Si le das click al botón "Añadir" sin haber escrito el nombre de tu amigo, te aparecerá un cuadro de texto con la siguiente alerta:</h5>

![image](https://github.com/user-attachments/assets/83fb20d6-530b-43cc-99ae-bc89ed071a58)

<h5>¿Estás listo para realizar el sorteo y saber quién será tu amigo secreto?</h5>
<h4> :exclamation: :grey_question: :sparkles: </h4>
<h5>Lo que tenemos que hacer es dar click en el botón "Sortear amigo" </h5>

![image](https://github.com/user-attachments/assets/3572c1a5-4e08-4774-b72d-c73d1f62ed7c)

<h5> ¡Listo, aquí está tu amigo secreto! </h5>

![image](https://github.com/user-attachments/assets/acacdc27-5bf6-480e-8b15-d292f3a49ed9)

<h5> A continuación agrego el código. </h5>

Tenemos el codigo HTML y CSS proporcionados por Alura.
```
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100;400;700;900&family=Merriweather:ital,wght@0,300;0,400;0,700;0,900;1,300;1,400;1,700;1,900&display=swap" rel="stylesheet">
    <title>Amigo Secreto</title>
</head>

<body>
    <main class="main-content">
        <header class="header-banner">
            <h1 class="main-title">Amigo Secreto</h1>
            <img src="assets/amigo-secreto.png" alt="Imagen representativa de amigo secreto">
        </header>
        
        <section class="input-section">
            <h2 class="section-title">Digite el nombre de sus amigos</h2>
            <div class="input-wrapper">
                <input type="text" id="amigo" class="input-name" placeholder="Escribe un nombre">
                <button class="button-add" onclick="agregarAmigo()">Añadir</button>
            </div>
           
            <ul id="listaAmigos" class="name-list" aria-labelledby="listaAmigos" role="list"></ul>
            <ul id="resultado" class="result-list" aria-live="polite"></ul>

            <div class="button-container">
                <button class="button-draw" onclick="sortearAmigo()" aria-label="Sortear amigo secreto">
                    <img src="assets/play_circle_outline.png" alt="Ícono para sortear">
                    Sortear amigo
                </button>
            </div>
        </section>
    </main>

    <script src="app.js" defer></script>
</body>
</html>
```
```
:root {
    --color-primary: #4B69FD;
    --color-secondary: #FFF9EB;
    --color-tertiary: #C4C4C4;
    --color-button: #fe652b;
    --color-button-hover: #e55720;
    --color-text: #444444;
    --color-white: #FFFFFF;
}

/* Estilos generales */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    height: 100vh;
    background-color: var(--color-primary);
    display: flex;
    justify-content: center;
    align-items: center;
}

.main-content {
    display: flex;
    flex-direction: column;
    height: 100%;
    width: 100%;
}

/* Banner */
.header-banner {
    flex: 40%;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 40px 0 0;
}

/* Sección de entrada */
.input-section {
    flex: 60%;
    background-color: var(--color-secondary);
    border: 1px solid #000;
    border-radius: 64px 64px 0 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
    width: 100%;
}

/* Títulos */
.main-title {
    font-size: 48px;
    font-family: "Merriweather", serif;
    font-weight: 900;
    font-style: italic;
    color: var(--color-white);
}

.section-title {
    font-family: "Inter", serif;
    font-size: 36px;
    font-weight: 700;
    color: var(--color-primary);
    margin: 10px 0;
    text-align: center;
}

/* Contenedores de entrada y botón */
.input-wrapper {
    display: flex;
    justify-content: center;
    width: 100%;
    max-width: 600px;
    margin-top: 20px;
}

.input-name {
    width: 100%;
    padding: 10px;
    border: 2px solid #000;
    border-radius: 25px 0 0 25px;
    font-size: 16px;
}

.button-container {
    width: 300px;
    justify-content: center;
}

/* Estilos de entrada de texto */
.input-title {
    flex: 1;
    padding: 10px 15px;
    font-size: 16px;
    border: 2px solid #333;
    border-right: none;
    border-radius: 25px 0 0 25px;
    font-family: "Merriweather", serif;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
}

/* Estilos de botón */
button {
    padding: 15px 30px;
    font-family: "Inter", sans-serif;
    font-size: 16px;
    border: 2px solid #000;
    border-radius: 25px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
    cursor: pointer;
}

.button-add {
    background-color: var(--color-tertiary);
    color: var(--color-text);
    border-radius: 0 25px 25px 0;
}

.button-add:hover {
    background-color: #a1a1a1;
}

/* Listas */
ul {
    list-style-type: none;
    color: var(--color-text);
    font-family: "Inter", sans-serif;
    font-size: 18px;
    margin: 20px 0;
}

.result-list {
    margin-top: 15px;
    color: #05DF05;
    font-size: 22px;
    font-weight: bold;
    text-align: center;
}

/* Botón de sortear título */
.button-draw {
    display: flex;
    align-items: center;
    width: 100%;
    padding: 10px 40px;
    color: var(--color-white);
    background-color: var(--color-button);
    font-size: 16px;
}

.button-draw img {
    margin-right: 40px;
}

.button-draw:hover {
    background-color: var(--color-button-hover);
}
```
Lo siguiente, es crear las funciones para el ingreso de los nombres de tus amigos, la creación de la lista de los mismos y el sorteo para poder encontrar a tu amigo secreto.
```
// El principal objetivo de este desafío es fortalecer tus habilidades en lógica de programación. Aquí deberás desarrollar la lógica para resolver el problema.
//Creamos las funcionalidades
document.addEventListener("DOMContentLoaded", () => {
    const inputNombre = document.getElementById("amigo");
    const botonAgregar = document.querySelector(".button-add");
    const listaNombres = document.getElementById("listaAmigos");
    const botonSortear = document.querySelector(".button-draw");
    const resultado = document.getElementById("resultado");
    
    //Función que guardará los nombres que ingresemos
    let nombres = [];

    // Función para que se vayan agregando los nombres a la lista
    function agregarAmigo() {
        const nombre = inputNombre.value.trim();
        
        //Saltará una alerta en caso de que no haya escrito nada en el nombre
        if (nombre === "") {
            alert("Por favor, ingresa un nombre válido.");
            return;
        }

        //Cuando vayamos agregando los nombres se van a ir agregando en la lista debajo de donde ingresamos
        nombres.push(nombre);
        actualizarLista();
        inputNombre.value = "";
        inputNombre.focus();
    }

    //Botón para guardar la información
    botonAgregar.addEventListener("click", agregarAmigo);

    // Función para actualizar la lista en la página
    function actualizarLista() {
        listaNombres.innerHTML = "";
        nombres.forEach((nombre) => {
            const li = document.createElement("li");
            li.textContent = nombre;
            listaNombres.appendChild(li);
        });
    }

    // Función para realizar el sorteo
    function sortearAmigo() {
        if (nombres.length === 0) {
            alert("La lista está vacía. Agrega nombres antes de sortear.");
            return;
        }
        const indiceAleatorio = Math.floor(Math.random() * nombres.length);
        resultado.innerHTML = `<li>🎉 El amigo secreto es: ${nombres[indiceAleatorio]} 🎉</li>`;
    }

    botonSortear.addEventListener("click", sortearAmigo);
});
```

<h3 alingn="center"> ¡Listo! </h3>
