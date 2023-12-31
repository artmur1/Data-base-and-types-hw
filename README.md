# Домашнее задание к занятию "`Базы данных, их типы`" - `Мурчин Артем`

### Задание 1. СУБД
Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для каждой предметной области.

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?

1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных.

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы?

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это реализовать?

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.

1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД логистов?

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

Приведите ответ в свободной форме.

### Решение 1
1.1. Реляционная СУБД

1.2. Для лендингов можно использвать реляционную СУБД. Для CRM системы лучше использовать реляционную СУБД.

1.3. Для реализации базы по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании думаю, что подойдет документо-ориентированная СУБД.

1.4. Для быстрого формирования маршрутов доствки материалов по объектам и распределению курьеров по маршрутам с доставкой документов можно использовать СУБД ключ-значение. Также эта СУБД будет быстро работать со связями. Реалиционная база тоже подойдет для реализации этой задачи.

### Задание 2. Транзакции
2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

Приведите ответ в свободной форме.

### Решение 2

Ввод номера телефона для пополнения баланса, ввод суммы пополнения

1. Начало транзакции - проверка достаточности средств на банковском расчетном счете пользователя
2. Списание средств с банковского счета пользователя
3. Перевод средств в банк телефонного оператора
4. Зачисление средств на банковский расчетный счет телефонного оператора
5. Пополнение баланса счёта телефона
6. Сообщение банку пользователя, что транзакция завершена при помощи foreign ключа. - конец транзакции.

### Задание 3. SQL vs NoSQL
3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

Приведите ответ в свободной форме.

### Решение 3
Преимущества SQL-систем по отношению к NoSQL:
1. В SQL базах используется транзакционная модель, что позволяет обеспечивать ACID.
2. SQL БД могут использовать процессы резервного копирования и восствновления для обеспечения сохранности данных и минимизации потерь в случае сбоя.
3. В SQL можно легко установить ограничение на доступ к данным для разных пользователей.
4. В SQL можно применять разные аутентификационные механизмы для обеспечения безопасности данных.
5. Язык запросов SQL позволяет быстро обрабатывать сложные запросы

### Задание 4. Кластеры
Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.

На основе какого критерия будете выбирать тип СУБД и какая модель распределённых вычислений здесь справится лучше всего и почему?

Приведите ответ в свободной форме.

### Решение 4

Буду выбирать тип СУБД на основе критерия "Производительность".
Для решения этой задачи лучше всего подходит модель распределенных вычислений “Master-Slave”. Ее суть в следующем: один узел (Master) координирует работу остальных узлов (Slave). Slave выполняет основную часть вычислений. Master отправляет задания Slave и получает результат вычислений.
Преимущества этой модели: высокая производительность, масштабируемость, простота реализации.

Под эти нужды можно использовать сетевую СУБД. Наиболее известными сетевыми СУБД являются следующие: DSM (корпорация UNIVAC), IDMS (Cullinane), DBMS (DEC).
Из big data можно выбрать Data Warehouse.
