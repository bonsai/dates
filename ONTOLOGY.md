# DATE Ontology

> **Agentは助ける。決めるのは、自分。**

## 1. Ontology の目的

DATE Ontology は、デートを「成功させるための行動」ではなく、

**人が誰かと関わり、考え、行動し、経験し、自分自身を変化させていく過程**

として記述するための概念モデルである。

## 2. World

```text
PERSON
  │
  ├── RELATIONSHIP
  │       │
  │       ├── CHAT
  │       ├── DATE
  │       └── EXPERIENCE
  │
  └── SELF

PLACE
EVENT
TIME
PLAN
AGENT
OBSERVATION
DECISION
OUTCOME
REFLECTION
CHANGE
```

## 3. Core Entities

### PERSON — 人

世界の主体。Agentではなく、**Personが主人公**。

```yaml
Person:
  id:
  name:
  preferences:
  interests:
  experiences:
  observations:
```

### SELF — 自分

自分はどう考えているか、何を望むか、何を経験し、どう変化したかを表す。

### RELATIONSHIP — 関係

PersonとPersonの間に存在する状態。ただし他者の内面を直接知ることはできない。

Relationship は観察可能な情報から作る**仮説**として扱う。

```yaml
Relationship:
  person_a:
  person_b:
  observations:
  shared_experiences:
  communication_history:
  intimacy_hypothesis:
  confidence:
```

### CHAT — 会話

人と人の関係を変化させる行為。

```text
PERSON → CHAT → OBSERVATION → RELATIONSHIP CHANGE
```

**Chatだけでも親密度は変化する。**

### DATE — デート

複数のPersonが、ある時間・場所・目的を共有する経験。

```yaml
Date:
  participants:
  time:
  places:
  activities:
  purpose:
  plan:
  outcome:
```

Dateの目的は必ずしも恋愛ではない。会話、食事、音楽、アート、散歩、学習、遊び、沈黙なども含む。

### ODEKAKE — おでかけ

**移動と体験の単位。**

```text
PLACE A → MOVE → PLACE B → EXPERIENCE
```

ODEKAKEは「親密度」そのものではない。

```text
ODEKAKE → 移動・共有体験 → 可能な変化 → RELATIONSHIP / SELF
```

### PLACE — 場所

```yaml
Place:
  id:
  name:
  location:
  type:
```

park / cafe / bar / museum / livehouse / theatre / library / bathhouse / street など。

### EVENT — イベント

```yaml
Event:
  id:
  title:
  time:
  place:
  category:
  price:
  source:
```

### PLAN — 計画

未来に対する仮説。Planは命令ではなく、**選択肢**である。

```yaml
Plan:
  participants:
  destinations:
  schedule:
  activities:
  alternatives:
  reasons:
```

### AGENT — エージェント

人間の判断を補助する存在。

```text
OBSERVE
ANALYZE
IMAGINE
SUGGEST
PLAN
REFLECT
```

ただし `DECIDE` はしない。

## 4. Observation

Agentが扱えるのは基本的に Observation。

```yaml
Observation:
  subject:
  fact:
  source:
  timestamp:
  confidence:
```

事実・解釈・可能性・選択を混同しない。

```text
FACT
 ↓
INTERPRETATION
 ↓
POSSIBILITY
 ↓
CHOICE
```

## 5. Intimacy

親密度は**目的・状態変化の一つ**だが、単一スコアでは表現しない。

```yaml
Intimacy:
  dimensions:
    conversation:
    trust:
    shared_experience:
    openness:
    continuity:
    comfort:
  evidence:
  confidence:
```

Signals の例：会話が続いた、質問が返ってきた、共通の話題が増えた、一緒に体験した、次の予定が生まれた。

## 6. Decision

最重要オブジェクト。

```yaml
Decision:
  person:
  situation:
  options:
  selected:
  reason:
```

Agentは選択肢を提示できる。しかし最終判断はPersonが行う。

## 7. Experience

実際に起きたこと。Planとは別物。

```yaml
Experience:
  participants:
  time:
  place:
  activities:
  events:
  emotions:
  outcome:
```

**予定外もデータである。**

## 8. Reflection

経験を次の判断へ変換する。

```yaml
Reflection:
  experience:
  what_happened:
  what_i_thought:
  what_i_learned:
  next_action:
```

```text
DECISION → ACTION → EXPERIENCE → REFLECTION → LEARNING → NEXT DECISION
```

## 9. Change

最終的に重要なのは「デート成功」ではなく**変化**。

```yaml
Change:
  subject:
  before:
  after:
  evidence:
```

## 10. Agent Loop

```text
       PERSON
          ↓
       OBSERVE
          ↓
       ANALYZE
          ↓
       IMAGINE
          ↓
       OPTIONS
          ↓
       DECISION
          ↓
         ACT
          ↓
      EXPERIENCE
          ↓
      REFLECTION
          ↓
        CHANGE
          ↓
    NEXT DECISION
          ↺
```

Agentはこのループを支援する。**ループの主体はPerson。**

## 11. Date Ontology Graph

```text
PERSON
 │
 ├──── CHAT ────→ OBSERVATION
 │                  │
 │                  ↓
 │             RELATIONSHIP
 │                  │
 │                  ↓
 │              INTIMACY
 │
 ├──── DATE ─────→ EXPERIENCE
 │                  │
 │                  ↓
 │              REFLECTION
 │                  │
 │                  ↓
 │                CHANGE
 │
 └──── ODEKAKE ──→ PLACE
                     │
                     ↓
                   EVENT
                     │
                     ↓
                    PLAN
                     │
                     ↓
                  DECISION
```

## 12. 最上位の原則

DATE Ontology は、**「どうすれば相手を攻略できるか」**をモデル化しない。

モデル化するのは、**「どうすれば自分で考え、選び、経験し、そこから成長できるか」**である。

```text
AIに人生を決めてもらう
          ✕

AIに助けてもらいながら
自分で人生を判断できるようになる
          ○
```

> **目的地を最適化するシステムではない。**
>
> **人が変化していく世界を記述するOntologyである。**
