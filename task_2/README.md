# Задание 2

- Реализуйте политику замещения для L2 кэша в Champsim и сравнтить ее с LRU наборе benchmark-ов из 1-ого задания. В качестве политики замещения можно взять любую кроме тех, что в Champsim уже есть.

## Отчет

- Исходный код реализованных схем политик замещения [MRU](https://github.com/uslsteen/ChampSim/blob/uslsteen/cache-policy/replacement/mru/mru.cc) и [LFU](https://github.com/uslsteen/ChampSim/blob/uslsteen/cache-policy/replacement/lfu/lfu.cc)


- Рассмотрим графики зависимости HIT RATE и IPC от бенчмарков для различных политик замещения кэшей.

![img](https://github.com/uslsteen/uarch_course/blob/main/task_2/pics/HIT_RATE.png) ![img](https://github.com/uslsteen/uarch_course/blob/main/task_2/pics/IPC.png)


- Рассмотрим графики зависимости GMEAN MPKI и GMEAN IPC от бенчмарков для различных политик замещения кэшей.

![img](https://github.com/uslsteen/uarch_course/blob/main/task_2/pics/GMEAN_HIT_RATE.png) ![img](https://github.com/uslsteen/uarch_course/blob/main/task_2/pics/GMEAN_IPC.png)
