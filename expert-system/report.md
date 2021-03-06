## Отчет по лабораторной работе №3
### по курсу "Искусственый интеллект"
### Экспертные системы

#### Студенты: 
[Гончар Дмитрий](https://github.com/DimasGon) (8О-304Б)  
[Корнев Игорь](https://github.com/IgorK381538) (8О-304Б)  
[Сомова Мария](https://github.com/marysom) (8О-304Б)    
[Тектониди Екатерина](https://github.com/iCat7) (8О-304Б)  
[Кривенко Дмитрий](https://github.com/kdg1511) (8О-306Б)   


### Тема работы

Каждый день сотни людей покупают ноутбуки. Кому-то для игр, кому-то для работа и тд. Некоторым не обойтись без ноутбука. Но как выбрать нужный ноутбук и не потратить деньги зря? Для ответа на этот вопрос Вы можете воспользоваться нашей программой для выбора ПРАВИЛЬНОГО ноутбука. 
Данная экспертная система расчитывает оптимальный ноутбук, который удовлетворяет запросам пользователя, а именно:
 - для чего этот ноутбук
 - задачи какой сложности он будет выполнять
 - сколько ноутбук должен работать автономно
 - некоторые фичи, которые должны присутствовать
 - мобильность ноутбука
 - игровая матрица ноутбука
ЭС будет задавать следующий вопрос, а базируясь на вашем предыдущем ответе.

### Концептуализация предметной области

В ходе работы над концептуализацией предметной области нами были выделены следующие категории ноутбуков:
 - Игровой;
 - Для работы;
 - Универсальный (подойдет как для работы, так и для игр);
 - Профессиональный (подойдет для тех, кто серьезно занимается 3D-моделированием или видеомонтажом);
 - Ноутбук начального уровня (подойдет для нетребовательных пользователей, идеален для интернета, учёбы, соцсетей, кино);  
 
Затем мы определили какими чертами обладает каждая категория ноутбуков, чтобы понимать, какие вопросы необходмо будет задавать.  

Графическая иллюстрация (рекомендуем открыть в новой вкладке): 
![base](https://github.com/MAILabs-Edu-AI/lab-expert-system-notebook/blob/master/base.png)  

 Предметная область была разделена между членами команды следующим образом: 
  - Игорь Корнев занимался классификацией ноутбуков, разбиением их на категории, описанием общей схемы предметной области;
  - Дмитрий Гончар занимался составлением вопросов для ЭС, внес в базу знаний множество ноутбуков, относящихся к категории "универсальные";
  - Мария Сомова занималась составлением вопросов для ЭС, описанием общей схемы предметной области, внела в базу знаний множество ноутбуков, относящихся к категрии "профессиональные";
  - Дмитрий Кривенко занимался внесением в базу знаний множеств ноутбуков, относящихся к категориям "для работы" и "ноутбук начального уровня"
  - Екатерина Тектониди занималась внесением в базу знаний множества ноутбуков, относящихся к категории "игровой".  

### Принцип реализации системы

 - Мы использовали систему SWI Prolog в связи с тем, что эта система уже знакома из курса "Логическое программирование" и обладает хорошим отладчиком.
 - Графическая иллюстрация архитектуры системы (рекомендуем открыть в новой вкладке).
 
 ![sx](https://github.com/MAILabs-Edu-AI/lab-expert-system-notebook/blob/master/sxema.png)


- Полный код программы [main.pl](https://github.com/MAILabs-Edu-AI/lab-expert-system-notebook/blob/master/main.pl)
### Механизм вывода

Для вывода вопросов используется следующий фрагмент кода:
```answers([], _).
answers([First|Rest], Index) :-
write(Index), write(' '), answer(First), nl,
NextIndex is Index + 1,
answers(Rest, NextIndex).
```
Первым аргументом answers получает список из идентификаторов вопросов. К примеру, это может быть список   
[for_work, professional, games, work_games, internet_movies_education, dont_know, brag].   
Второй аргумент – номер для ввода после вопроса для идентификации выбора пользователя.   
Как производится вывод: проходя по списку идентификаторов программа выводит номер вопроса   
(write(Index)), пробел (write(' ')), а затем сам вопрос (answer(First)).   
Здесь First – голова списка. Для каждого члена списка, который передается в answers прописаны answer(…):
```answer(for_work) :-
write('Only for work').
answer(professional) :-
write('3D-modelling, video production').
answer(games) :-
write('Only for games').
```
Весь остальной вывод реализован аналогичным образом.


### Протокол работы системы

![1](https://pp.userapi.com/c840026/v840026525/696c2/BWIFgWwfOk4.jpg)

![2](https://pp.userapi.com/c840026/v840026525/696d4/0WnkE5OOUPI.jpg)

![3](https://pp.userapi.com/c840026/v840026525/696fa/k7wwNez7SKY.jpg)

## Выводы

В наше время всё стремится к тому, что человек пытается автоматизировать как можно больше работы и сэкономить как можно больше денег. Отсюда вопрос: как можно автоматизировать работу тем самым сэкономив деньги? Ответ прост – написать программную оболочку, которая заменит сотрудника! Это мы и сделали в нашей работе. Мы предлагаем экспертную систему, которая представляет возможность онлайн консультирования клиента. Эта система поможет покупателю выбрать ноутбук, а предпринимателю – сэкономить деньги.   
При выполнении работы наша команда узнала много аспектов ЭС. Мы освежили в памяти недавно использованные навыки по написанию пролог-программ, а также приобрели новые навыки логического программирования, разработка ЭС оказалась очень увлекательным делом. Однако не обошлось и без трудностей - у нас было много споров о том, какие воросы должна задавать ЭС, в каком порядке, как хранить данные о ноутбуках, как должно быть устроено тело ЭС.  Очень важно было сделать именно экспертную систему, а не программу, осуществляющую поиск данных в табличке. Нашу ЭС можно отнести к ЭС с динамической базой знаний, так как система реагирует на каждый вопрос, решая какой вопрос будет следующим. Таким образом, каждый следующий вопрос основан на предыдущем ответе.
Данная лабораторная работа очень полезна, так как она учит работать в команде и думать, а не просто следовать алгоритму.
