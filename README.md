# Pochta2022
RussiaChampionship
В репозитории представлены основные артефакты решения - модуль программы Логином (бесплатная общедоступная версия, LoginomCommunity вер.6.5.1) "Почта России обработка данных.lgp", в котором выполнялись все операции по предобработке данных, а также три исполняемых программных модуля, на основе которых выполнялась подготовка решения.
В модуле catboost_model файл Прогноз 74.ipynb- первоначальная подготовка, с общим результатом 74.1%, по всем доступным полям датасета.
После того, как выяснилось, что в трейне и тесте неравномерное распределение по параметру 'oper_type + oper_attr', данный параметр был исключен из обработки моделью, однако, первоначальный результат (оптимальный по наиболее многочисленным значениям поля типа и атрибутам: 1004_-1, 2_6, 2_1) использовался в последующей подготовке ансамблевого решения.
Затем использовался модуль xgboost kaggle.ipynb (при неравномерном распределении по категориальным типам xgboost эффективнее catboost), позволивший получить наиболее сбалансированный результат, при движении параметра настройки scale_pos_weight (снижая и увеличивая количество точек в выборке).
На окончательной стадии подготовки решения использовался модуль xgboost kaggle финализация.ipynb для снижения числа решений по типам и атрибутам, не равным трем приведенным выше.
Комплексная сабмиссии собиралась, исходя из задачи - как можно меньшее количества выбранных единиц при сохранении по-возможности высокого показателя по метрике ЛБ.
Через несколько промежуточных комбинаций полученных тремя моделями решений, наиболее оптимальным признан результат 80.7002 по метрике публичного ЛБ с количеством единиц в 284413 . Финальная сабмиссия приведена в архиве Почта России.rar. 
