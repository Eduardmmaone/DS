# [Тестовое задание](https://github.com/hoittoken/Python/blob/master/Py/Projects/progect_motorica/test_task/Task_1.ipynb)

Необходимо построить **модель распознавания жестов** в парадигме обучения с учителем. 

Параметры модели оптимизированы на предложенных данных для обучения. 

Валидация модели произведена на отложенной тестовой выборке

В качестве метрики оценки качества решения выбран **Mean F-score**.
***

## Соревнование на Kaggle 
## [Motorica x SkillFactory internship test task on Kaggle](https://www.kaggle.com/competitions/motorica-x-skillfactory-internship-test-task/overview)

Значки которые мне нравятся 🔥 

![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
 ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)

   * Тестовые данные предстваляют из себя 323 наблюдения. Каждое наблюдение состоит из 100 зафиксированных с равными промежутками времени, показаниями 40 датчиков.
   * Получены данные показания по технике: Пилоту поступают команды о выполнении жестов, пилот после получения команды с некоторой естественной задержкой выполняет жесты.
   * Целевая переменная представляет из себя закодированную команду поданную пользователю на выполнение жеста в каждый момент времени.

# Что было сделано:
1. Данные преобразованны из 3d массива в 2d
    
2. Определена нижняя граница показаний датчиков (условный уровень "0")
3. Определены ключевые датчики (для каждого жеста)
4. Компенсирована задержка между командой на выполнения жеста и выполнением этого жеста (с помощью сумарной скользящей средней по ключевым датчикам)
5. На подготовленных данных протестрированы ряд классификаторов (с параметрами по умолчанию):
    
    5.1. [sklearn.ensemble.RandomForestClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html) **Public Score: 0.94148**
    
    5.2. [CatBoost.CatBoostClassifier](https://catboost.ai/en/docs/concepts/loss-functions-multiclassification) **Public Score: 0.93814**
    
    5.3. [lightgbm.LGBMClassifier](https://lightgbm.readthedocs.io/en/v3.3.2/pythonapi/lightgbm.LGBMClassifier.html) **Public Score: 0.94148**

6. Протестированы разные комбинации уставок для сработки датчиков и компенсации задержки
7. Проведено финальное моделирование с оптимальными уставками и гиперпараметрами **Public Score: 0.97407** 