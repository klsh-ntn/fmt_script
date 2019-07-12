# klsh_pmt

The repository contains scripts for KLSH PMT


1. В файле `judges.dat` нужно закомментить/удалить неприехавших людей,
добавить приехавших и прописать им следующие вещи: скилл (первая колонка),
0/1 — знает ли физику (вторая колонка), третья колонка — 0/1 (может ли быть главным) и далее нужно перечислить все команды через пробел, которые этот человек не может судить.
Очень важно команды заполнять именно вот так, с `\\gamma`

2. В файле `rooms.dat` нужно переименовать все столы, их должно стать 11.
Первыми идут более высокие столы. Последняя строчка должна быть пустой!!

3. Перед каждым матчем нужно заполнять файл `matches_N.dat`, где N — номер встречи. Для примера я положил matches_0.dat. Сверху идут первые столы, ниже последние.

Связываем команды 1 и 2 по рейтингу, если они раньше не играли.

Связываем команды 3 и 4 по рейтингу, если они раньше не играли.

И т.д.


4. Теперь запускаем
```bash
python2 main_gen_scripy.py N
```
где N — номер встречи. этот скрипт создаст файл с судьями для каждого стола. Скрипт рандомно выбирает судей так, чтобы 1) был физик, 2) был главный, 3) суммарный скилл был больше минимального необходимого для данного стола (они прописаны в min_skills.dat). В сгенерированном файле с судьями можно их попереставлять, как хочется. То что генерирует скрипт это некая затравка

5.  Затем запускаем три скрипта
```bash
python2 protocols_gen.py N
python2 notifications_gen.py N
python2 school_notifications_gen.py N
```

они генерят протоколы, объявление в штаб и объявление для школьников на столовую

в конце питон сам откроет texmaker, останется только нажать на кнопочку build, и всё. если нет texmaker'a, лучше поставить. иначе будет ошибка, но это не страшно. тогда нужно соответствующий теховский файл открыть чем-то вашим и скомпилить


о существовании `judges.dat` и об алгоритме первичной расстановки лучше умалчивать
