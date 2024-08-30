Для создания приложения "Игральная кость" на React, начнем с инициализации нового проекта и разработки всех необходимых компонентов.

1. Создание нового проекта React
Используем create-react-app для инициализации проекта. В терминале выполните:

npx create-react-app dice-app
cd dice-app
2. Установка необходимых файлов
Создадим файл Dice.js в папке src/components для компонента кубика:

// src/components/Dice.js
import React, { useState } from 'react';
import './Dice.css';

const diceImages = [
  'dice1.png', 'dice2.png', 'dice3.png',
  'dice4.png', 'dice5.png', 'dice6.png'
];

const Dice = () => {
  const [currentDice, setCurrentDice] = useState(0);

  const rollDice = () => {
    const newRoll = Math.floor(Math.random() * 6);
    setCurrentDice(newRoll);
  };

  return (
    <div className="dice-container">
      <img src={`/images/${diceImages[currentDice]}`} alt={`Dice showing ${currentDice + 1}`} className="dice-image" />
      <button className="roll-button" onClick={rollDice}>Бросить кубик</button>
    </div>
  );
};

export default Dice;
3. Создание CSS для компонента
Создаем файл Dice.css в папке src/components для стилизации:

/* src/components/Dice.css */
.dice-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 20px;
}

.dice-image {
  width: 100px;
  height: 100px;
  margin: 20px;
}

.roll-button {
  padding: 10px 20px;
  font-size: 18px;
  cursor: pointer;
}
4. Редактирование основного файла приложения
Отредактируем App.js, чтобы интегрировать компонент Dice:

// src/App.js
import React from 'react';
import Dice from './components/Dice';
import './App.css';

function App() {
  return (
    <div className="App">
      <h1>Игральная кость</h1>
      <Dice />
    </div>
  );
}

export default App;
Добавьте в public папку /images с изображениями кубика dice1.png, dice2.png, ..., dice6.png.

5. Добавление стилей для главного приложения
Отредактируйте файл App.css:

/* src/App.css */
.App {
  text-align: center;
  margin-top: 50px;
}

h1 {
  font-size: 2rem;
  margin-bottom: 20px;
}
6. Запуск приложения
Сохраните все файлы и запустите приложение:

npm start
