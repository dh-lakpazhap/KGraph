# ✅ ЧЕК-ЛИСТ ПРОЕКТА

---

# 🧠 1. Интеллект системы (ДХ)

## 🎯 Роль: Agent + Prompts + UX logic

### [ ] Agent логика

* [ ] Реализовать `agents.py`
* [ ] Определить flow:

  * анализ запроса
  * проверка недостающих данных
  * вызов search / graph / LLM
  * объединение результатов

---

### [ ] LLM промпты (`prompts.py`)

* [ ] Extraction prompt (сущности + claims)
* [ ] Hypothesis prompt (связи между источниками)
* [ ] Discovery prompt (поиск пробелов)
* [ ] System prompt (поведение агента)

---

### [ ] Контроль диалога

* [ ] уточняющие вопросы пользователю
* [ ] логика “что спросить дальше”
* [ ] обработка неполных запросов

---

### [ ] UX / Figma → логика

* [ ] описать пользовательские сценарии (CJM)
* [ ] определить структуру ответа (граф + текст + гипотезы)

---

## 📦 Результат от тебя:

```python
agent.chat(query) -> structured response
```

---

# 🟩 2. NLP + Embeddings + Retrieval (Поля)

## 🎯 Роль: понимание текста

### [ ] Data pipeline

* [ ] PDF → text
* [ ] chunking (смысловые блоки)

---

### [ ] NLP extraction

* [ ] entities
* [ ] relations
* [ ] claims

---

### [ ] Embeddings

* [ ] модель (OpenAI / BGE)
* [ ] индексация chunks

---

### [ ] Vector DB

* [ ] Qdrant / FAISS setup
* [ ] сохранение embeddings

---

### [ ] Search API

```python
semantic_search(query) -> docs
```

---

## 📦 Результат:

* работающий semantic search
* база документов + embeddings

---

# 🟦 3. Knowledge Graph (Люба)

## 🎯 Роль: структура знаний

### [ ] Graph schema

* [ ] Material
* [ ] Process
* [ ] Property
* [ ] Experiment

---

### [ ] Neo4j setup

* [ ] запуск базы
* [ ] создание узлов и связей

---

### [ ] Cypher pipeline

* [ ] запись данных из NLP

---

### [ ] Graph API

```python
get_subgraph(material) -> graph
```

---

### [ ] (опционально)

* [ ] дедупликация сущностей

---

## 📦 Результат:

* рабочий knowledge graph
* API для извлечения подграфов

---

# 🟨 4. Backend + Frontend (Кирилл)

## 🎯 Роль: интерфейс и интеграция

---

### [ ] Backend (FastAPI)

* [ ] `/chat`
* [ ] `/upload`
* [ ] подключение agent.chat()

---

### [ ] Интеграция модулей

* [ ] semantic_search
* [ ] get_subgraph
* [ ] agent response

---

### [ ] Frontend

* [ ] чат интерфейс
* [ ] загрузка файлов
* [ ] отображение графа
* [ ] вывод гипотез

---

## 📦 Результат:

* работающий web demo

---


# 🚀 Итоговая архитектура

```text
Frontend
   ↓
Backend (FastAPI)
   ↓
Agent 
   ↓
 ┌──────────────┬──────────────┐
 ↓              ↓              ↓
Search        Graph        LLM
(Qdrant)     (Neo4j)     (GPT)
```



