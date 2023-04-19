## Стажировка в моторике


[Motorica x SkillFactory internship test task on Kaggle](https://www.kaggle.com/competitions/motorica-x-skillfactory-internship-test-task/overview)



[Тестовое задание](https://github.com/hoittoken/Python/tree/master/Py/Projects/progect_motorica) Модель распознавания жестов в парадигме обучения с учителем


Значки которые мне нравятся:

![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
 ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)

# Dataset Description

## Подход сбора данных

`Пилот` - человек, с которого собираются данные.

На руку пилота крепится манжета с датчиками, которые фиксируют движение мышц и связок руки пилота. В течение всей процедуры сбора данных зафиксированные датчиками данные записываются в файл.

Пилоту поступают команды о выполнении жестов, пилот после получения команды с некоторой естественной задержкой выполняет жесты.

## Данные

* Данные представляют из себя временные ряды, где в каждый момент времени фиксируются показания от датчиков.

* Целевая переменная представляет из себя закодированную команду поданную пользователю на выполнение жеста в каждый момент времени.

## Файлы

* X_train.npy - обучающая выборка;
* y_train.csv - закодированная команда жеста для обучающей выборки;
* X_test.npy - тестовая выборка;
* sample_submission.csv - некоторое решение задачи из которого можно взять формат;

## Описание данных

* X_train.npy и X_test.npy имеют следующие размерности (наблюдения, датчики, время);
* y_train.csv и y_test.csv имеют следующие размерности (наблюдения * время) - это обусловленно форматом ответов для Kaggle;
* y_train.csv содержит следующие классы:
* * 0 - команда "жест open";
* * 1 - команда "сгиб мизинца";
* * 2 - команда "сгиб безымянного пальца";
* * 3 - команда "сгиб среднего пальца";
* * 4 - команда "жест пистолет";
* * 5 - команда "сгиб указательного пальца";
* * 6 - команда "сгиб большога пальца";
* * 7 - команда "жест ОК";
* * 8 - команда "жест grab";
 
## Обучающая выборка

В данной постановке мы работаем с командами подаваемыми пользователю на выполнение жеста. Если есть команда "жест grab", значит в этот момент пользователь получил команду на выполнение схвата.

Аналогично и остальные жесты, кроме "жеста open".

"Жест open", который обозначает, что пользователь получил команду на возвращение руки в нейтральное состояние (раскрытая ладонь).

## Тестовая выборка
В тестовых данных целевая переменная отражает не команду для пользователя, а само выполнения жеста без задержки между получением пользователем команды и непосредственно выпонением жеста.

## Метрика оценки качества решения 

В качестве метрики оценки качества решения выбран `Mean F-score`. 

Целевые значения будут использованы для валидации решений участников на лидерборде. 
* 50% целевых значений будут использоваться на открытом лидерборде, 
* 50% на закрытом (участники не видят его до конца соревнования) во избежания переобучения “под лидерборд”. Победитель определяется по результатам на закрытом лидерборде. 
## Формат решения Формат решения можно посмотреть в файле `sample_submission.csv`.

<!--
**hoittoken/hoittoken** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.


- 🔭 I’m currently working on 
- 🌱 I’m currently learning math&ml
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about 
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
