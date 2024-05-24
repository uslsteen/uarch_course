# Задание 1

- Реализуйте схемы GAg и GAp. Сравните точность предсказания с бимодальным предиктором при одинаковых (близких) размерах предсказателей.

## Отчет

- Исходный код реализованных схем предсказания [GAg](https://github.com/uslsteen/ChampSim/blob/uslsteen/branch-prediction/branch/GAg/GAg.cc) и [GAp](https://github.com/uslsteen/ChampSim/tree/uslsteen/branch-prediction/branch/GAp)



- Рассмотрим графики зависимости MPKI (branch mispredictions per KILOinstructions) и IPC (instructions per cycle) от бенчмарков для различных схем предсказания переходов.

![img](https://github.com/uslsteen/uarch_course/blob/main/task_1/pics/MPKI.png) ![img](https://github.com/uslsteen/uarch_course/blob/main/task_1/pics/IPC.png)


- Рассмотрим графики зависимости GMEAN MPKI (branch mispredictions per KILOinstructions) и GMEAN IPC (instructions per cycle) от бенчмарков  для различных схем предсказания переходов.

![img](https://github.com/uslsteen/uarch_course/blob/main/task_1/pics/GMEAN_MPKI.png) ![img](https://github.com/uslsteen/uarch_course/blob/main/task_1/pics/GMEAN_IPC.png)
