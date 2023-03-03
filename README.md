# Проект по университетскому курсу "Обработка и интерпретация сигналов"

В качестве решаемой задачи выбрано создание алгоритма играющего в дискретную антагонистическаую [игру](https://ru.wikipedia.org/wiki/%D0%92%D0%BE%D0%B9%D0%BD%D0%B0_%D0%B2%D0%B8%D1%80%D1%83%D1%81%D0%BE%D0%B2) с полной информацией под названием "Война вирусов".
Конкретная версия правил заключается в следующем:

<b>*Игровое поле*</b>

Игровая доска представляет собой квадратное поле $n \times n$ клеток, где $n$ представляет собой натуральное число больше или равное 10 и меньшее 16.

<b>*Цель игры*</b>

Игрок побеждает в игре, если его противник остается без возможных ходов.

<b>*Процесс игры*</b>

В игре участвуют два игрока играющие Синими  и Красными "вирусами" соответственно.
Игра начинается с пустой доски.
Игроки ходят по очереди. Начинает игрок, играющий Синими "вирусами".
Каждый ход состоит из $k$ "шагов".($k$ фиксируется в начале игры и представляет собой натуральное число от 1 до 5) Каждый "шаг" является либо размножением, либо поглощением (зомбированием):

  +  "размножение"  - это выставление знака нового "вируса" своего цвета в любую "доступную" (см. ниже) пустую клетку доски;
  +   "поглощение" - это "зомбирование" одного из вирусов противника, находящегося на "доступной" (см. ниже) клетке. В этом случае "вирус" противника в клетке заменяется на специальный знак  "зомби" цвета игрока. "Зомби" остаются неизменными на доске до конца партии, т.е. они не могут быть "оживлены", "восстановлены" или удалены с доски.

Клетка является "доступной" в следующих случаях:
  + клетка является самой левой верхней клеткой поля для первого игрока или самой правой нижней для второго.
  +  если клетка непосредственно соприкасается (по вертикали, горизонтали или диагонали) с живым "вирусом" игрока
  +  если между клеткой и "вирусом" игрока, уже находящимся на доске, есть непрерывная цепочка из "зомбированных" "вирусов" противника, т.е. цепочка из соприкасающихся (по вертикали, горизонтали или диагонали) "зомби" цвета игрока.
Игрок обязан сделать все $k$ "шагов" каждый ход. Если игрок не может сделать все $k$ "шагов", то он проигрывает партию.
![Пример](/images/example.png "Пример игровой позиции")

---

## Решения, используемые для антагонистических игр с неполной информацией
- [Reinforcement Learning на примере игры в Калах](https://torlenor.org/machine%20learning/reinforcement%20learning/2020/10/23/machine_learning_reinforment_learning_kalah_part1.html#reinforcement-learning-agents)
- [Реализация reinforcement learning алгоритмов](https://stable-baselines3.readthedocs.io/en/master/)

    Stable Baselines3 (SB3) is a set of reliable implementations of reinforcement learning algorithms in PyTorch

- [Статья на Medium: "ow to Train an AI to Play Any Game"](https://towardsdatascience.com/how-to-train-an-ai-to-play-any-game-f1489f3bc5c?gi=b8f3ce057fa7)
- [Статья на Medium: "How To Build Your Own AI To Play Any Board Game"](https://medium.com/applied-data-science/how-to-train-ai-agents-to-play-multiplayer-games-using-self-play-deep-reinforcement-learning-247d0b440717)
    * [Библиотека, используемая в статье](https://github.com/davidADSP/SIMPLE)
- [Статья на Medium: "Teaching AI To Play a Platform-Fighting Game Using Genetic Neural Networks"](https://medium.com/@mikecazzinaro/teaching-ai-to-play-a-platform-fighting-game-using-neural-networks-ef9316c34f52)
    * Evolutionary Learning + Neural Network
- ["How to teach AI to play Games: Deep Reinforcement Learning"](https://towardsdatascience.com/how-to-teach-an-ai-to-play-games-deep-reinforcement-learning-28f9b920440a?gi=074b8864243e)

### Научные статьи
- [Сравнение различных RL стратегий](https://ieeexplore.ieee.org/abstract/document/8861927)
- [GP в настольных играх со скрытой информацией](https://link.springer.com/chapter/10.1007/978-3-319-31471-6_10)
