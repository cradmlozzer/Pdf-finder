# Цифровой прорыв. Трек от Главгосэкспертизы по работе с pdf файлами

С помощью расстояния Левенштейна находит похожие слова в файлах и сохраняет результат в новый файл с подсвеченными участками.

### Подготовка к использованию

```python
cd Digital-breakthrough

```
Используем  и активируем виртуальное окружение с помощью _pip_

```python
python -m venv venv
venv/Scripts/activate.bat #for windows
```
Устанавливаем зависимости
```python
pip install -r requirements.txt
```

### Описание программы и основные параметры

```python
python main.py -h
```

* _phrase_ 

Ключевая фраза, по которой будет идти поиск. Порядок слов в целом не важен. Главное написать основные вариации запрашиваемого
* _indir_ 

Папка, из которой будут вытягиваться pdf-файлы
* _mask_thres_ 

Трешхолд для постобработки маски. Исключает последовательности короче, чем заданное число. По умолчанию нуль, те учитывает слова, стоящие обособленно
* _rate_ 

Один из главных пороговых параметров, влияние которого легко увидеть на длиных словах. Вычисляется как отношение расстояния Левенштейна к длине исходного слова. Если показатель ниже, слово учитывается

```
row_rate = levenstain(word_1,word_2)/lenght_row_word
```

*  _is_make_csv_

Булевый параметр - делать ли отчет по файлу в виде таблицы

```python
python main.py "process include folder" --indir data --mask_thres 0 --rate 0.2 --is_make_csv True
```

### Пример использования

```python
python main.py "archive tar process"
```
Пример оформеления в файле
![example_pdf](https://github.com/cradmlozzer/Digital-breakthrough/assets/108126763/43dc29c1-4d2d-462d-9e5e-6ccac54b4dea)

Пример оформление в таблице
![example_table](https://github.com/cradmlozzer/Digital-breakthrough/assets/108126763/90fa1597-a725-46f9-b137-f47eb6929956)