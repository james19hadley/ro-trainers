# TU Darmstadt RO Interactive Trainers Hub

Комплекс интерактивных веб-тренажёров для подготовки к экзамену по курсу **Rechnerorganisation (RO)** в **TU Darmstadt**.

Каждый тренажёр представляет собой полностью автономный **Single-File HTML** (с инлайновым CSS, SVG-графикой и чистым JavaScript), не требующий сервера, установки или внешних зависимостей.

---

## 📋 Список тренажёров

| № | Файл | Экзаменационная задача | Темы и механика | Вес в баллах |
|---|---|---|---|---|
| **1** | [`machine_code_trainer.html`](./machine_code_trainer.html) | **Aufgabe 2:** RISC-V Maschinencode | Декодер форматов R, I, S, B, U, J; сборка Immediate; hex $\leftrightarrow$ bin $\leftrightarrow$ ASM | **8–12 P** |
| **2** | [`calling_conventions_trainer.html`](./calling_conventions_trainer.html) | **Aufgabe 3:** Calling Conventions & Stack | Caller/Callee-saved регистры, генерация прологов/эпилогов, стек-фреймы | **10–14 P** |
| **3** | [`cache_trainer.html`](./cache_trainer.html) | **Aufgabe 4 / 8:** Cache-Speicher | Direct Mapped, Set Associative, Tag/Index/Offset, 3C-Misses, AMAT | **8–12 P** |
| **4** | [`single_cycle_trainer.html`](./single_cycle_trainer.html) | **Aufgabe 5:** Eintakt-Prozessor | Векторная схема однотактника, 25+ инструкций, проводка, сигналы управления | **6–8 P** |
| **5** | [`multicycle_trainer.html`](./multicycle_trainer.html) | **Aufgabe 6:** Mehrtakt-Prozessor | Векторный граф FSM Мура, пошаговый симулятор, задания WiSe26/SoSe25, критический путь $T_C$ и $f_{max}$ | **8–10 P** |
| **6** | [`pipeline_trainer.html`](./pipeline_trainer.html) | **Aufgabe 7:** Pipeline Hazards | 5-ступенчатый конвейер, RAW-конфликты, Forwarding Unit, Load-Use Stalls, Branch Flush | **12–15 P** |
| **0** | [`index.html`](./index.html) | **Главный портал (Hub)** | Единая витрина всех 6 тренажёров с фильтрацией, поиском и запуском в 1 клик | **Итого: ~65+ P** |

---

## 🚀 Как выложить на GitHub Pages (в 3 команды)

В директории `ro-trainers-hub`:

```bash
cd /home/ging/stud/RO/ro-trainers-hub

# 1. Инициализировать git
git init
git add .
git commit -m "Deploy TU Darmstadt RO Interactive Trainers Suite"

# 2. Создать репозиторий на GitHub через gh CLI (публичный)
gh repo create ro-trainers --public --source=. --remote=origin --push

# 3. Включить GitHub Pages для ветки main
gh api -X POST /repos/:owner/ro-trainers/pages -f build_type=workflow || gh repo edit --enable-pages --pages-branch main
```

После этого страница со всеми тренажёрами сразу станет доступна по ссылке вида:  
`https://<username>.github.io/ro-trainers/`
