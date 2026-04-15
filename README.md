# Лабораторная работа №13 — CI/CD для Python-проекта

## Структура проекта

```
cicd_project/
├── main.py                      ← Основной код
├── test_main.py                 ← Тесты
└── .github/
    └── workflows/
        └── ci.yml               ← GitHub Actions (CI/CD)
```

---

## Часть 1. Локальный запуск тестов

### Установи pytest
```bash
pip install pytest
```

### Запусти тесты
```bash
pytest
```

Результат — все тесты должны пройти (4 passed):
```
test_main.py ....   [100%]
4 passed in 0.XXs
```

---

## Часть 2. Настройка CI/CD на GitHub

1. Зайди на https://github.com и создай новый репозиторий
2. Загрузи все файлы проекта (включая папку `.github`)
3. После загрузки GitHub автоматически запустит тесты

Посмотреть результат: вкладка **Actions** в репозитории

✅ Зелёная галочка — тесты прошли  
❌ Красный крест — есть ошибка

---

## Самостоятельные задания

### Задание 1 — Намеренно вызвать ошибку
Измени в `main.py` функцию `add`:
```python
def add(a, b):
    return a - b   # Ошибка!
```
Загрузи на GitHub → CI покажет красный крест ❌

### Задание 2 — Исправить ошибку
Верни правильный код:
```python
def add(a, b):
    return a + b
```
Загрузи снова → CI покажет зелёную галочку ✅

### Задание 3 — Добавить новый тест
В `test_main.py` добавь:
```python
def test_add_zero():
    assert add(0, 0) == 0
```

---

## Загрузка на GitHub (команды Git)

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/ТвойАккаунт/ТвойРепозиторий.git
git push -u origin main
```
