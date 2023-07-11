# Цифровой прорыв. Трек от Главгосэкспертизы по работе с pdf файлами

С помощью расстояния Левенштейна находит похожие слова в файлах и сохраняет результат в новый файл с подсвеченными участками.

### Подготовка к использованию

```python
cd Digital-breakthrough

```
Используем  и активируем виртуальное окружение с помощью _pip_

```python
python -m venv venv
venv/Scripts/activate.bat
```

### Описания программы

```python
python main.py -h
```

Основные параметры
-_phrase_
Ключевая фраза, по которой будет идти поиск. Порядок слов в целом не важен. Главное написать основные вариации запрашиваемого.
-_indir_
Папка, из которой будут вытягиваться pdf-файлы
-_mask_thres_
Трешхолд для постобработки маски. Исключает последовательности короче, чем заданное число. По умалчанию нуль, те учитывает слова, стоящие обособленно
-_rate_
Один из главных пороговых параметров, влияние которого легко увидеть на длиных словах. Вычисляется как отношение расстояния Левенштейна к длине исходного слова. Если показатель ниже, слово учитывается
$$
row_rate = \frac{levenstain(word_1,word_2)}{lenght_row_word}
$$
-_is_make_csv_
Булевый параметр - делать ли отчет по файлу в виде таблицы

### Пример использования

```python
python main.py "archive tar process"
```