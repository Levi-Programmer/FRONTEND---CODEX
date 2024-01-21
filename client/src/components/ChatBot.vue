<template>
    <div id="chat-container">
        <div id="chat-box">
            <div id="chat-logs"></div>
        </div>
        <input id="chat-input" type="text" placeholder="Escribe aquí..." />
        <button id="send-btn">Enviar</button>
    </div>
</template>



<script>

document.addEventListener("DOMContentLoaded", function() {
    var step = 0;
    var userName, userDocumentType, userDocumentNumber;

//bloque codigo, que da mensaje predeterminado de bienvenida//

    addBotMessage("¡Hola!, Bienvenido a H O R I Z O N, la aerolínea del futuro ¿Cual es tu nombre completo?");

    document.getElementById("send-btn").addEventListener("click", function() {
        var userInput = document.getElementById("chat-input").value;
        document.getElementById("chat-input").value = "";

        if (userInput.trim() === "") return; 

        if (step === 0) {
            userName = userInput;
            addBotMessage("Encantado, " + userName + ". ¿Cuál es tu tipo de documento?");
            showDocumentTypes();
            step++;
        } else if (step === 2) {
            userDocumentNumber = userInput;
            addBotMessage("Gracias, " + userName + ". Tu tipo de documento es " + userDocumentType + " y el número es: " + userDocumentNumber + ".");
        }
    });

    function showDocumentTypes() {
        var documentTypes = ["Cedula de ciudadanía", "Pasaporte", "Carné de Extranjería", "Otro"];
        var chatLogs = document.getElementById("chat-logs");
        var list = document.createElement("ul");

        documentTypes.forEach(function(type) {
            var listItem = document.createElement("li");
            var button = document.createElement("button");
            button.textContent = type;
            button.onclick = function() {
                userDocumentType = type;
                addBotMessage("¡Genial! Has seleccionado: " + type + ". Por favor, ingresa tu número de documento, para darte mejor asesoramiento en esta experiencia.");
                step = 2; 
            };
            listItem.appendChild(button);
            list.appendChild(listItem);
        });

        chatLogs.appendChild(list);
    }

    function addBotMessage(message) {
        var para = document.createElement("P");
        para.innerHTML = "Agente Horizon: " + message;
        document.getElementById("chat-logs").appendChild(para);
    }
});

</script>


<style scoped>

#chat-container {
    width: 400px;
    margin: auto;
    background-color: #f5f5f5;
    border: 1px solid #ddd;
    padding: 10px;
}
/*podemos crear un mismo bloq adicionando un */
#chat-box {
    height: 300px;
    overflow-y: auto;
    border: 1px solid #cccccc;
    padding: 10px;
    background-color: #fff;
}

#chat-logs {
    font-family: Arial, sans-serif;
    font-size: 14px;
}

#chat-input {
    width: calc(100% - 110px);
    padding: 10px;
}

#send-btn {
    width: 100px;
    padding: 10px;
}

</style>