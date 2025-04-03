<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Автоматизация процесса</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            line-height: 1.6;
        }
        .step {
            margin-bottom: 20px;
            padding: 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .step.completed {
            background-color: #e6ffe6;
            border-color: #009900;
        }
        button {
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:disabled {
            background-color: #cccccc;
        }
    </style>
</head>
<body>
    <h1>Автоматизация процесса получения подарка</h1>
    <div id="steps">
        <div class="step" id="step1">
            <h3>Шаг 1: Получите код из Telegram</h3>
            <p>Откройте чат в Telegram и скопируйте код.</p>
            <button onclick="completeStep(1)">Готово</button>
        </div>
        <div class="step" id="step2">
            <h3>Шаг 2: Вставьте код в Binance</h3>
            <p>Перейдите на сайт Binance, вставьте код в соответствующее поле и нажмите "Подтвердить".</p>
            <button onclick="completeStep(2)" disabled>Готово</button>
        </div>
        <div class="step" id="step3">
            <h3>Шаг 3: Получите подарок в Red Packet</h3>
            <p>Откройте приложение Red Packet, нажмите "Получить", затем "Открыть" и закройте окно.</p>
            <button onclick="completeStep(3)" disabled>Готово</button>
        </div>
    </div>

    <script>
        let currentStep = 1;

        function completeStep(step) {
            if (step === currentStep) {
                // Отметить текущий шаг как завершенный
                document.getElementById(`step${step}`).classList.add('completed');

                // Активировать следующий шаг
                currentStep++;
                const nextStepButton = document.querySelector(`#step${currentStep} button`);
                if (nextStepButton) {
                    nextStepButton.disabled = false;
                }

                // Если все шаги завершены
                if (currentStep > 3) {
                    alert("Процесс завершен! Подарок получен.");
                }
            }
        }
    </script>
</body>
</html>
