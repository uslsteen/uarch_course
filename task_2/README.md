# Задание 2

- Реализуйте политику замещения для L2 кэша в Champsim и сравнтить ее с LRU наборе benchmark-ов из 1-ого задания. В качестве политики замещения можно взять любую кроме тех, что в Champsim уже есть.

## Отчет

1. Исходный код реализованных схем политик замещения [MRU](https://github.com/uslsteen/ChampSim/blob/uslsteen/cache-policy/replacement/mru/mru.cc) и [LFU](https://github.com/uslsteen/ChampSim/bl=ob/uslsteen/cache-policy/replacement/lfu/lfu.cc)

2. Симулятор Champsim был запущен на одном и том же наборе бенчмарков с тремя разными политиками замещения кэшей. Вкратце:

    - ```LRU``` - стратегия замещения наименее недавно использованного элемента. Стратегия лучше всего работает для программ с высокой временной и пространственной локальностью по данным, поскольку в кэше сохраняются именно недавно использованные элементы.

    - ```LFU``` -  стратегия замещения наименее часто используемого элемента. Хорошо подходит для программ, в которых к определенным данным требуется более частый доступ. Для работы алгоритма необходимо поддержать счетчики числа использования.

    - ```MRU``` - стратегия замещения наиболее недавно использованного элемента. Стратегия эффективна лишь в том случае, если вам зачем-то необходимо хранить кучу старых, мусорных данных.

Исходя из алгоритмов работы, можно однозначно сказать, что у ```MRU``` будут почти всегда худшие показатели.

3. Рассмотрим графики зависимости HIT RATE и IPC от бенчмарков для различных политик замещения кэшей.

![img](https://github.com/uslsteen/uarch_course/blob/main/task_2/pics/HIT_RATE.png) ![img](https://github.com/uslsteen/uarch_course/blob/main/task_2/pics/IPC.png)

- **HIT RATE**: На ряде бенчамарков ```LRU``` стратегия значительно лучше ```LFU``` и ```MRU```. Лишь на одном тесте ```LFU``` cлегка лучше ```LRU```. Интересно, что для бенчмарка ```623.xalancbmk_s-165B.champsimtrace``` у LRU значение HIT RATE стремится к нулю $(hits = 254, misses = 380336 \Rightarrow \frac{254}{254 + 380336})$.
- **IPC**: Примечательно, что несмотря на значения по HIT RATE в пользу LRU, разрыв по IPC менее разгромный. На значительном числе тестов LFU либо не хуже, либо даже лучше LRU политики. Более того, на одном бенчмарке даже MRU превосходит LRU.

4. Рассмотрим графики зависимости GMEAN MPKI и GMEAN IPC от бенчмарков для различных политик замещения кэшей.

![img](https://github.com/uslsteen/uarch_course/blob/main/task_2/pics/GMEAN_HIT_RATE.png) ![img](https://github.com/uslsteen/uarch_course/blob/main/task_2/pics/GMEAN_IPC.png)

Геометрически усреднив значения по всем бенчмаркам, убеждаемся, что ```LRU``` - самая выигрышная политика по IPC. Однако в виду бенчмарка ```623.xalancbmk_s-165B.champsimtrace``` усредненное значение HIT RATE ```LFU``` оказалось заметно выше.
