
[Uploading Agendas.Html…]()<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Agendas</title>

    <style>
        body {
            font-family: 'Times New Roman', Times, serif;
            font-style: italic; 
            font-size: 18px;
            margin: 0;
            padding: 0;
            background: linear-gradient(45deg, #00b4db, #83e377);
            animation: shimmer 2s infinite linear;
            position: relative;
        }

        @keyframes shimmer {
            0% {
                color: #333;
            }
            50% {
                color: #555;
            }
            100% {
                color: #333;
            }
        }

        .container {
            width: 80%;
            margin: 100px auto; /* Ajustado para mover las casillas más hacia abajo */
            background-color: rgba(255, 255, 255, 0.8); /* Cambiado a un color de fondo blanco con 80% de opacidad */
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            position: relative;
            overflow: hidden; /* Añadido para ocultar el desbordamiento de los elementos animados */
        }

        /* Crear el efecto de destello en los bordes */
        .container::before,
        .container::after {
            content: "";
            position: absolute;
            top: 10;
            left: 10;
            width: 100%;
            height: 100%;
            background: linear-gradient(50deg, #00b4db, #83e377, #00b4db); /* Colores del destello */
            animation: shine 2s infinite linear alternate;
            z-index: -1;
        }

        .container::after {
            background: linear-gradient(45deg, #83e377, #00b4db, #83e377); /* Cambiamos el orden de los colores */
            animation-delay: 1s; /* Retrasamos la animación en 1 segundo */
        }

        @keyframes shine {
            0% {
                transform: translateX(-150%);
            }
            100% {
                transform: translateX(150%);
            }
        }

        h1 {
            text-align: center;
            color: #333;
        }

        .form-group {
            margin-bottom: 30px; /* Aumentado el espacio entre las casillas */
        }

        label {
            display: block;
            font-weight: bold;
            color: #555;
        }

        input[type="text"],
        input[type="date"],
        input[type="tel"],
        input[type="email"],
        select,
        textarea {
            width: 100%;
            padding: 8px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }

        textarea {
            height: 100px;
        }

        button[type="submit"],
        .share-button {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 16px;
            border-radius: 4px;
            cursor: pointer;
            margin-top: 20px;
            transition: background-color 0.3s ease;
        }

        button[type="submit"]:hover,
        .share-button:hover {
            background-color: #0056b3;
        }

        .data-list {
            background-color: #f9f9f9;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            margin-top: 20px;
            overflow: auto;
            max-height: 300px;
        }

        .data-list ul {
            list-style-type: none;
            padding: 0;
        }

        .data-list li {
            margin-bottom: 10px;
            padding: 10px;
            background-color: #fff;
            border-radius: 4px;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .data-list li:hover {
            transform: translateY(-3px);
        }

        .data-list li label {
            font-weight: bold;
            color: #333;
        }

        .data-list li span {
            color: #666;
        }

        /* Estilos para la imagen */
        .container img {
            position: absolute;
            top: 10px;
            left: 10px;
            width: 150px;
            height: 150px;
            animation: shine 1s infinite alternate;
        }

        @keyframes shine {
            0% {
                opacity: 1;
            }
            100% {
                opacity: 0.5;
            }
        }
    </style>
</head>



<body>
<div class="container">
    <h1>AGENDAMIENTOS DE CITA </h1>

<p> &nbsp; </p>
<p> &nbsp; </p>

    <form id="medicalForm">
        <div class="form-group">
            <label for="name">Nombre completo:</label>

            <input type="text" id="name" required>
        </div>
        <div class="form-group">
            <label for="dob">Fecha de Nacimiento:</label>
            <input type="date" id="dob" required>
        </div>
        <div class="form-group">
            <label for="gender">Género:</label>
            <select id="gender" required>
                <option value="masculino">Masculino</option>
                <option value="femenino">Femenino</option>
                <option value="otro">Otro</option>
            </select>
        </div>
        <div class="form-group">
            <label for="phone">Número de Teléfono:</label>
            <input type="tel" id="phone" required>
        </div>
        <div class="form-group">
            <label for="emergencyContact">Número de Teléfono o Contacto de Emergencia:</label>
            <input type="tel" id="emergencyContact" required>
        </div>
        <div class="form-group">
            <label for="email">Correo Electrónico:</label>
            <input type="email" id="email" required>
        </div>
        <div class="form-group">
            <label for="address">Dirección:</label>
            <input type="text" id="address" required>
        </div>
        <div class="form-group">
            <label for="stratum">Estrato:</label>
            <input type="number" id="stratum" required min="1" max="6">
        </div>
        <div class="form-group">
            <label for="eps">EPS:</label>
            <input type="text" id="eps" required>
        </div>
        <div class="form-group">
            <label for="age">Edad:</label>
            <input type="number" id="age" required min="0">
        </div>
        <div class="form-group">
            <label for="healthCondition">Enfermedades o Limitaciones:</label>
            <textarea id="healthCondition" required></textarea>
        </div>
        <div class="form-group">
            <label for="appointmentDay">Día de la Cita:</label>
            <input type="date" id="appointmentDay" required>
        </div>
        <div class="form-group">
            <label for="symptoms">Síntomas:</label>
            <textarea id="symptoms" required></textarea>
        </div>
        <button type="submit">Agendar Cita</button>
    </form>
    <button class="share-button" id="shareButton">Compartir Datos</button>
    <div class="data-list" id="dataList"></div>

     <img src="https://i.ibb.co/rwvY804/IMG-20240504-WA0119.jpg" width="50px" height="50px">

</div>

<script>
    document.getElementById('medicalForm').addEventListener('submit', function(event) {
        event.preventDefault();
        var name = document.getElementById('name').value;
        var dob = document.getElementById('dob').value;
        var gender = document.getElementById('gender').value;
        var phone = document.getElementById('phone').value;
        var emergencyContact = document.getElementById('emergencyContact').value;
        var email = document.getElementById('email').value;
        var address = document.getElementById('address').value;
        var stratum = document.getElementById('stratum').value;
        var eps = document.getElementById('eps').value;
        var age = document.getElementById('age').value;
        var healthCondition = document.getElementById('healthCondition').value;
        var appointmentDay = document.getElementById('appointmentDay').value;
        var symptoms = document.getElementById('symptoms').value;

        var dataList = document.getElementById('dataList');
        var listItem = document.createElement('div');
        listItem.classList.add('data-item');
        listItem.innerHTML = `
                <ul>
                    <li><label>Nombre:</label> <span>${name}</span></li>
                    <li><label>Fecha de Nacimiento:</label> <span>${dob}</span></li>
                    <li><label>Género:</label> <span>${gender}</span></li>
                    <li><label>Número de Teléfono:</label> <span>${phone}</span></li>
                    <li><label>Contacto de Emergencia:</label> <span>${emergencyContact}</span></li>
                    <li><label>Correo Electrónico:</label> <span>${email}</span></li>
                    <li><label>Dirección:</label> <span>${address}</span></li>
                    <li><label>Estrato:</label> <span>${stratum}</span></li>
                    <li><label>EPS:</label> <span>${eps}</span></li>
                    <li><label>Edad:</label> <span>${age}</span></li>
                    <li><label>Enfermedades o Limitaciones:</label> <span>${healthCondition}</span></li>
                    <li><label>Día de la Cita:</label> <span>${appointmentDay}</span></li>
                    <li><label>Síntomas:</label> <span>${symptoms}</span></li>
                </ul>
            `;
        dataList.appendChild(listItem);

        // Clear form fields after submission
        document.getElementById('medicalForm').reset();
    });

    document.getElementById('shareButton').addEventListener('click', function() {
        var dataList = document.getElementById('dataList');
        var dataText = '';

        // Loop through list items and concatenate data
        var listItems = dataList.getElementsByClassName('data-item');
        for (var i = 0; i < listItems.length; i++) {
            var item = listItems[i];
            dataText += item.innerText.trim() + '\n';
        }

        // Copy data to clipboard
        navigator.clipboard.writeText(dataText);

        alert('Datos copiados al portapapeles. Puedes pegarlos en cualquier aplicación para compartir.');
    });
</script>
</body>
</html>


<!DOCTYPE html>
<html lang="en">
<head>


    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulario Médico</title>

    <body>
    <div>
        <img src="img.jpg"width="250px" height="250px">

    </div>

    </body>


    <style>

        body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background: linear-gradient(45deg, #00b4db, #83e377);
    animation: shimmer 2s infinite linear;
}

@keyframes shimmer {
    0% {
        color: #333;
    }
    50% {
        color: #555;
    }
    100% {
        color: #333;
    }
}

.container {
    width: 80%;
    margin: 50px auto;
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h1 {
    text-align: center;
    color: #333;
}


        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            font-weight: bold;
            color: #555;
        }

        input[type="text"],
        input[type="date"],
        input[type="tel"],
        input[type="email"],
        select,
        textarea {
            width: 100%;
            padding: 8px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }

        textarea {
            height: 100px;
        }

        button[type="submit"],
        .share-button {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 16px;
            border-radius: 4px;
            cursor: pointer;
            margin-top: 20px;
            transition: background-color 0.3s ease;
        }

        button[type="submit"]:hover,
        .share-button:hover {
            background-color: #0056b3;
        }

        .data-list {
            background-color: #f9f9f9;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            margin-top: 20px;
            overflow: auto;
            max-height: 300px;
        }

        .data-list ul {
            list-style-type: none;
            padding: 0;
        }

        .data-list li {
            margin-bottom: 10px;
            padding: 10px;
            background-color: #fff;
            border-radius: 4px;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .data-list li:hover {
            transform: translateY(-3px);
        }

        .data-list li label {
            font-weight: bold;
            color: #333;
        }

        .data-list li span {
            color: #666;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Formulario Médico</h1>
        <form id="medicalForm">
            <div class="form-group">
                <label for="name">Nombre:</label>
                <input type="text" id="name" required>
            </div>
            <div class="form-group">
                <label for="dob">Fecha de Nacimiento:</label>
                <input type="date" id="dob" required>
            </div>
            <div class="form-group">
                <label for="gender">Género:</label>
                <select id="gender" required>
                    <option value="masculino">Masculino</option>
                    <option value="femenino">Femenino</option>
                    <option value="otro">Otro</option>
                </select>
            </div>
            <div class="form-group">
                <label for="phone">Número de Teléfono:</label>
                <input type="tel" id="phone" required>
            </div>
            <div class="form-group">
                <label for="emergencyContact">Número de Teléfono de Contacto de Emergencia:</label>
                <input type="tel" id="emergencyContact" required>
            </div>
            <div class="form-group">
                <label for="email">Correo Electrónico:</label>
                <input type="email" id="email" required>
            </div>
            <div class="form-group">
                <label for="address">Dirección:</label>
                <input type="text" id="address" required>
            </div>
            <div class="form-group">
                <label for="stratum">Estrato:</label>
                <input type="number" id="stratum" required min="1" max="6">
            </div>
            <div class="form-group">
                <label for="eps">EPS:</label>
                <input type="text" id="eps" required>
            </div>
            <div class="form-group">
                <label for="age">Edad:</label>
                <input type="number" id="age" required min="0">
            </div>
            <div class="form-group">
                <label for="healthCondition">Enfermedades o Limitaciones:</label>
                <textarea id="healthCondition" required></textarea>
            </div>
            <div class="form-group">
                <label for="appointmentDay">Día de la Cita:</label>
                <input type="date" id="appointmentDay" required>
            </div>
            <div class="form-group">
                <label for="symptoms">Síntomas:</label>
                <textarea id="symptoms" required></textarea>
            </div>
            <button type="submit">Agendar Cita</button>
        </form>
        <button class="share-button" id="shareButton">Compartir Datos</button>
        <div class="data-list" id="dataList"></div>
    </div>

    <script>
        document.getElementById('medicalForm').addEventListener('submit', function(event) {
            event.preventDefault();
            var name = document.getElementById('name').value;
            var dob = document.getElementById('dob').value;
            var gender = document.getElementById('gender').value;
            var phone = document.getElementById('phone').value;
            var emergencyContact = document.getElementById('emergencyContact').value;
            var email = document.getElementById('email').value;
            var address = document.getElementById('address').value;
            var stratum = document.getElementById('stratum').value;
            var eps = document.getElementById('eps').value;
            var age = document.getElementById('age').value;
            var healthCondition = document.getElementById('healthCondition').value;
            var appointmentDay = document.getElementById('appointmentDay').value;
            var symptoms = document.getElementById('symptoms').value;

            var dataList = document.getElementById('dataList');
            var listItem = document.createElement('div');
            listItem.classList.add('data-item');
            listItem.innerHTML = `
                <ul>
                    <li><label>Nombre:</label> <span>${name}</span></li>
                    <li><label>Fecha de Nacimiento:</label> <span>${dob}</span></li>
                    <li><label>Género:</label> <span>${gender}</span></li>
                    <li><label>Número de Teléfono:</label> <span>${phone}</span></li>
                    <li><label>Contacto de Emergencia:</label> <span>${emergencyContact}</span></li>
                    <li><label>Correo Electrónico:</label> <span>${email}</span></li>
                    <li><label>Dirección:</label> <span>${address}</span></li>
                    <li><label>Estrato:</label> <span>${stratum}</span></li>
                    <li><label>EPS:</label> <span>${eps}</span></li>
                    <li><label>Edad:</label> <span>${age}</span></li>
                    <li><label>Enfermedades o Limitaciones:</label> <span>${healthCondition}</span></li>
                    <li><label>Día de la Cita:</label> <span>${appointmentDay}</span></li>
                    <li><label>Síntomas:</label> <span>${symptoms}</span></li>
                </ul>
            `;
            dataList.appendChild(listItem);

            // Clear form fields after submission
            document.getElementById('medicalForm').reset();
        });

        document.getElementById('shareButton').addEventListener('click', function() {
            var dataList = document.getElementById('dataList');
            var dataText = '';

            // Loop through list items and concatenate data
            var listItems = dataList.getElementsByClassName('data-item');
            for (var i = 0; i < listItems.length; i++) {
                var item = listItems[i];
                dataText += item.innerText.trim() + '\n';
            }

            // Copy data to clipboard
            navigator.clipboard.writeText(dataText);

            alert('Datos copiados al portapapeles. Puedes pegarlos en cualquier aplicación para compartir.');
        });
    </script>
</body>
</html>



Muchas Gracias por escogernos.
