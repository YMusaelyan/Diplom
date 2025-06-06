# Димпломная работа
Тема: Применение нейронных дифференциальных уравнений для анализа динамических систем\
Выполнил: Мусаелян Ярослав Александрович\
Группа: М8О-407Б-21\
Научный руководитель: д. ф-м н., профессор, профессор каф. 806\ 
Ревизников Дмитрий Леонидович

## Содержание репозитория
Данный репозиторий содержит файл в формате IPYNB (Interactive Python Notebook). В данном файле содержится практическая часть диплома.

## Метод решения
В ходе работы была разработана модель на основе нейронных дифференциальных уравнений для восстановления и прогнозирования динамики временного ряда. Данная модель была обучена и протестирована на синтетических временных рядах. В качестве даанных рядов были взяты синусоидальный, коссинусоидальный сигнлы и апериодическая функция - аналитическое решение звена 1 порядка. Также был реализован подбор гиперпараметров.

## Стек технологий

Языки программирования: Python
Фреймфорк: Pythorch
Библиотеки Python: NumPy, Matplotlib, Seaborn
Стандартные модули: math,os


## Описание основных блоков кода
ode_solve - функция, которая решает ОДУ методом Эйлера.\
ODEAdjoint - класс, для реализации сопряженного уравнения.\
NeuralODE - модуль, интегрирующий ОДУ в PyTorch, позволяющий использовать ее как часть нейросети.\
ODEF - вычисляет градиенты для работы сопряженного метод.\
NNODEF - конкретная реализация функции ODEF с использованием нейросети.\
RNNEncoder - RNN энкодер, принимает входные данные и на выходе выдает латентный вектор.\
NeuralODEDecoder - декодер, основанный на нейронных дифферинциальных уравнениях, принимает латентный вектор и преобрзует в выходные данные.\
ODEVAE - итоговая модель, основанная на вариационном автоэнкодере.

## Схема итоговой модели ODEVAE
![image](https://github.com/user-attachments/assets/af4a9f52-a959-49e2-8fc5-a4382d16d7ca)\
На вход подаются изначальные данные - временной ряд. RNNEncoder принимает входные данные и на выходе выдает латентный вектор. NeuralODEDecoder, основанный на нейронных дифферинциальных уравнениях, принимает латентный вектор и преобрзует в выходные данные.

## Пример результатов работы
### Восстановление и предсказание синусоидального сигнала
![image](https://github.com/user-attachments/assets/439a07f5-c7a7-4b87-b73f-f5cff6904b70)\
![image](https://github.com/user-attachments/assets/f0e9cf52-9264-4efb-b817-0d0fb48b6dfd)

### Восстановление и предсказание апериодической функции: аналитического решения звена 1 порядка
![image](https://github.com/user-attachments/assets/10de6e08-0a2d-4c1c-b8a0-1c14841b91bd)\
![image](https://github.com/user-attachments/assets/1baf3d9a-b753-4093-ba40-2e2e891a7030)


