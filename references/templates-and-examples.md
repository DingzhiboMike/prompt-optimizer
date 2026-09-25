# Шаблоны и примеры трансформации ТЗ → промпт

Читай, когда собираешь промпт по типовой задаче (Этапы 3–5) или нужен образец трансформации.

## Шаблоны для типовых задач

### 1. Контент-генерация (посты, статьи)
```xml
<context>
AS-IS (current content problem):
[Что не работает в текущем контенте: низкий engagement, generic, не резонирует с аудиторией]

TO-BE (desired content outcome):
[Желаемый результат: конкретные метрики engagement, реакция аудитории, бизнес-цель]
</context>

<task>
[Тип контента: пост/статья/лонгрид]
Topic: [конкретная тема]
Angle: [уникальный угол зрения]
</task>

<audience>
Who: [конкретная аудитория]
Knowledge level: [новичок/продвинутый/эксперт]
Pain points: [что их беспокоит]
Current behaviour: [что читают сейчас, что не работает]
</audience>

<structure>
[Конкретная структура, например:]
1. Hook (провокационный тезис или вопрос)
2. Context (почему это важно сейчас)
3. Core insight (главная мысль + supporting evidence)
4. Actionable takeaway (что делать с этим)
</structure>

<style>
Voice: [первое лицо/безличный/экспертный]
Tone: [аналитический/провокационный/обучающий]
Complexity: [простой язык/профессиональный жаргон]
Length: [100-150 / 500-700 / 1500+ слов]
</style>

<must_include>
- [Конкретные элементы]
- Minimal 1 concrete example or data point
- Personal insight or non-obvious take
</must_include>

<never_include>
- Generic advice anyone could write
- Corporate speak or buzzwords without definition
- Obvious statements
- [Другие исключения]
</never_include>
```

**Опционально для multi-output:** если шаблон используется для генерации нескольких вариантов — в начало промпта добавь SSoT-блок из `diversity-protocol`.

### 2. Анализ и исследование
```xml
<context>
AS-IS (current state of knowledge):
[Что известно/не известно сейчас, какие есть пробелы в понимании]

TO-BE (desired understanding):
[Что нужно понять, какие вопросы должны быть отвечены, какие решения приняты на основе анализа]

Decision to be made:
[Какое решение будет приниматься на основе этого анализа]
</context>

<analysis_task>
Subject: [что анализируем]
Focus: [конкретный аспект]
Depth: [surface-level / deep-dive]
</analysis_task>

<methodology>
Approach: [сравнительный / трендовый / причинно-следственный]
Sources to consider: [откуда брать данные]
Analysis framework: [если есть специфичный - SWOT, Porter's 5, Jobs-to-be-done, etc.]
</methodology>

<output_structure>
Format: [prose / structured report / table]
Sections:
1. [Раздел 1]
2. [Раздел 2]
3. Conclusion with actionable insights
</output_structure>

<quality_criteria>
- Evidence-based (конкретные данные, не мнения)
- Contrarian insights (не очевидные выводы)
- Actionability (что с этим делать)
- Measurable (где возможно, с метриками)
</quality_criteria>
```

### 3. Синтетические интервью
```xml
<synthetic_interview>
Role: [B2B marketer / Product Manager / Sales leader]
Company size: [startup / mid-market / enterprise]
Industry: [tech / SaaS / manufacturing]
Context: [какую проблему пытается решить]
</synthetic_interview>

<interview_parameters>
Experience level: [2-5 years / 5-10 years / 10+ years]
Current challenges: [конкретные pain points]
Decision-making authority: [influencer / decision-maker / end-user]
</interview_parameters>

<output_format>
For each question:
1. Question: [вопрос]
2. Response: [realistic answer with specific details]
   - Include hesitations, nuances
   - Reference real tools/processes
   - Provide concrete numbers when relevant
3. Meta-insight: [что это говорит о сегменте]
</output_format>

<realism_requirements>
- Use industry-specific terminology naturally
- Include objections and doubts (not just positive)
- Reference real market conditions
- Demonstrate knowledge gaps where appropriate
- Show emotional responses (frustration, excitement, skepticism)
</realism_requirements>
```

### 4. Код и технические задачи
```xml
<code_task>
Goal: [что должен делать код]
Language/Framework: [конкретный стек]
Input: [формат входных данных]
Output: [формат выходных данных]
</code_task>

<technical_requirements>
Performance: [критичность производительности]
Error handling: [как обрабатывать ошибки]
Dependencies: [можно использовать / нельзя использовать]
Code style: [PEP8 / Airbnb / Google Style Guide]
</technical_requirements>

<deliverables>
1. Working code with inline comments
2. [Usage example / Unit tests / Documentation]
3. [Edge cases handling]
</deliverables>
```

### 5. Frontend / design задача
```xml
<context>
AS-IS: [текущий UI / его отсутствие, что не устраивает]
TO-BE: [тип продукта — dashboard / landing / dev-tool / fintech; нужное ощущение]
</context>

<design_direction>
[Вариант 1 — конкретная спецификация:]
Палитра: [перечислить hex'ы, например #E9ECEC #8C9A9E #11171B]
Типографика: [конкретный шрифт + характер: square/angular sans, serif display]
Радиусы / отступы / motion: [4px corner radius; generous margins; transition all 160ms]
Использовать эту систему по всей странице, не вводить яркие акценты сверх неё.

[Вариант 2 — выбор до сборки:]
Before building, propose 4 distinct visual directions for this brief
(each: bg hex / accent hex / typeface — one line of rationale).
Ask me to pick one, then implement only that direction.
</design_direction>

<frontend_aesthetics>
NEVER use generic AI-generated aesthetics: overused fonts (Inter, Roboto, Arial,
system fonts), cliched schemes (purple gradients on white/dark), predictable layouts,
cookie-cutter components. Use unique fonts, cohesive theme, micro-interactions.
</frontend_aesthetics>
```

> Выбираю Вариант 1, если у пользователя уже есть бренд-гайд или чёткое видение. Вариант 2 — когда направление не определено. **Без** одного из двух вариантов модель скатится в свой дефолтный визуальный стиль.

## Примеры трансформации ТЗ → Промпт

### Пример 1: Размытое ТЗ → Чёткий промпт через As-Is → To-Be

**Исходное ТЗ:**
"Напиши пост про AI в маркетинге"

**Этап 0: Уточнение As-Is → To-Be**
```
AS-IS: Пишу generic посты про AI, которые не цепляют аудиторию. Нет engagement.

TO-BE: Хочу пост, который провоцирует дискуссию среди B2B маркетологов и показывает 
конкретный, неочевидный инсайт про AI в конкурентном анализе.

GAP: Нужен конкретный угол зрения + данные + практический takeaway.
```

**После оптимизации:**
```xml
<context>
AS-IS: Generic AI-in-marketing content doesn't resonate with B2B marketing leaders.
TO-BE: Create a LinkedIn post that sparks discussion by revealing a non-obvious insight 
about AI in competitive analysis.
</context>

<instructions>
Write a LinkedIn post for B2B marketing leaders:

1. Hook: provocative question about traditional competitor research limitations
2. Core insight: specific example of AI-driven insight traditional methods miss 
   (use concrete metric or data point)
3. Practical takeaway: one actionable first step readers can take this week
</instructions>

<style>
Tone: Conversational but data-informed, first person
Format: 150-200 words, natural paragraphs (no bullet points)
Voice: Based on real experience, not theoretical
</style>

<constraints>
MUST include:
- At least one specific metric or data point
- A non-obvious insight (not "AI makes things faster")
- Personal angle or story

NEVER include:
- Generic AI hype without substance
- Vendor mentions or product pitches
- Buzzwords without definition (unless deconstructing them)
- Listicles or "5 ways to..." format
</constraints>
```

### Пример 2: Сложное ТЗ → Структурированный промпт

**Исходное ТЗ:**
"Мне нужен анализ конкурентов для нового AI-продукта в B2B маркетинге, чтобы понять позиционирование"

**Этап 0: As-Is → To-Be анализ**
```
AS-IS: 
- Запускаем AI marketing intelligence платформу в US рынок
- Есть несколько конкурентов (HubSpot AI, 6sense, Clearbit)
- Не понимаем, почему клиенты выбирают их vs. что они заявляют в маркетинге
- Наше позиционирование пока размытое

TO-BE:
- Понять реальные jobs-to-be-done каждого конкурента (не заявленные, а фактические)
- Найти gap между их позиционированием и реальностью
- Определить 3 positioning angles для нашего продукта на основе white space
- Иметь evidence-based данные для принятия решения

GAP: Нужен глубокий анализ с фокусом на клиентскую перспективу, не на features.
```

**После оптимизации:**
```xml
<context>
AS-IS:
- Launching B2B AI marketing intelligence platform in US mid-market ($10M-$100M ARR)
- Competitors: HubSpot AI, 6sense, Clearbit (+ manual analysis)
- Gap: Don't understand why customers choose competitors vs. what they claim
- Current positioning: undefined

TO-BE:
- Clear understanding of actual jobs-to-be-done for each competitor
- Identify positioning gaps (claim vs. reality)
- 3 testable positioning angles based on white space opportunities
- Evidence-based data for positioning decision

Target budget range customers consider: $500-$5000/month per tool
</context>

<role>
Act as competitive intelligence analyst with focus on customer perspective, 
not feature comparisons.
</role>

<instructions>
Conduct competitive positioning analysis:

1. For each top 5 competitor, identify:
   - Stated positioning (from their marketing)
   - ACTUAL jobs-to-be-done (from user reviews on G2, Reddit, customer forums)
   - Gap between claim and reality
   - User switching triggers (what makes customers leave)

2. Analyze white space:
   - Underserved needs in each customer segment
   - Complaints that aren't addressed

3. Synthesize into positioning opportunities:
   - 3 specific positioning angles to test
   - Rationale for each based on evidence
   - Clear differentiation from competitors
</instructions>

<output_format>
Executive summary table:
| Competitor | Stated Position | Actual JTBD | Key Gap | Our Opportunity |

Detailed analysis for each competitor:
- Positioning statement
- 3 main use cases from actual users (with source links)
- Top 3 complaints from reviews
- White space opportunity

Conclusion:
- 3 recommended positioning angles with rationale
- Next steps for validation
</output_format>

<quality_criteria>
- Evidence-based (link to all sources: G2, Reddit, review sites)
- Customer perspective focus (not feature lists)
- Non-obvious insights (not surface-level observations)
- Actionable recommendations (clear next steps)
</quality_criteria>

<constraints>
EXCLUDE:
- Generic feature comparison tables
- Pricing as primary differentiator
- Assumptions without data backing
- Marketing speak from competitor websites as truth
- SEO-optimized "best of" articles as sources
</constraints>
```

### Пример 3: Трансформационная задача (редизайн/рефакторинг)

**Исходное ТЗ:**
"Помоги с редизайном лендинга для SaaS продукта"

**Этап 0: As-Is → To-Be (после уточнения)**
```
AS-IS:
- Текущий лендинг конвертирует в demo 1.2% (индустрия: 2-3%)
- Фокус на features, а не на outcomes
- Целевая аудитория: VP Marketing в mid-market B2B
- Главная проблема: visitor не понимает value за 5 секунд
- Bounce rate 68%

TO-BE:
- Конверсия в demo requests минимум 2.5%
- Hero section сразу показывает конкретный outcome
- Clear value proposition для VP Marketing
- Bounce rate <50%
- Visitor понимает "для кого это" и "какую проблему решает" за 5 сек

CONSTRAINTS:
- Бренд и цвета не меняем
- Технологии: Webflow (не можем менять)
- Срок: концепция нужна за неделю
```

> **⚠️ Дефолтный визуальный стиль.** У моделей есть липкий «домашний» стиль для визуальных и лендинговых задач, и общие запреты («не используй X», «сделай минималистично») не помогают — модель просто переключается на другую фиксированную палитру. Два рабочих обхода вшиваю в промпт: **(1)** задать конкретную палитру и типографику спецификацией, **(2)** попросить модель предложить 3-4 направления (bg hex / accent hex / шрифт + одна строка обоснования) до сборки и собрать только выбранное.

**После оптимизации:**
```xml
<context>
AS-IS (current landing page problems):
- Conversion to demo: 1.2% (industry benchmark: 2-3%)
- Feature-focused messaging, not outcome-focused
- Bounce rate: 68%
- Target audience (VP Marketing, mid-market B2B) doesn't understand value in 5 seconds

TO-BE (desired outcome):
- Conversion to demo: minimum 2.5%
- Hero section immediately communicates concrete outcome
- Clear value prop for VP Marketing persona
- Bounce rate: <50%
- 5-second clarity test: visitor instantly understands "for whom" and "what problem solved"

Constraints:
- Brand identity and colors: unchanged
- Platform: Webflow (no migration)
- Timeline: concept needed in 1 week
</context>

<role>
Act as conversion-focused UX strategist specializing in B2B SaaS landing pages.
</role>

<instructions>
Create landing page redesign strategy:

1. Hero Section Redesign:
   - Headline: outcome-focused (not feature-focused)
   - Subheadline: specific problem + quantified result
   - CTA: low-friction, clear next step
   - Social proof: relevant logo wall OR specific metric

2. Value Proposition Section:
   - Transform current features into outcomes
   - Use "Unlike X, we Y" framework for differentiation
   - Include 1 concrete example or case result

3. Structure Optimization:
   - Recommended section order with rationale
   - What to remove (cut the fat)
   - What to add (missing trust elements)

4. Conversion Optimization:
   - CTA placement and copy recommendations
   - Friction reduction tactics
   - Trust-building elements
</instructions>

<output_format>
1. Strategic Overview:
   - Core problems identified
   - Key changes to drive conversion lift

2. Section-by-Section Blueprint:
   - Hero: [detailed recommendation]
   - Value Prop: [detailed recommendation]
   - Social Proof: [detailed recommendation]
   - CTAs: [placement + copy]

3. Copy Framework:
   - Before/After examples for key sections
   - Messaging hierarchy

4. Success Metrics:
   - How to measure if redesign hits To-Be goals
   - A/B test recommendations

5. Webflow Implementation Notes:
   - Technical considerations
   - Quick wins vs. full redesign
</output_format>

<constraints>
MUST include:
- Specific copy examples (not just "improve headline")
- Rationale for each recommendation
- Reference to conversion psychology principles
- Webflow-compatible solutions only

NEVER include:
- Generic "best practices" without context
- Features before outcomes in messaging
- Technical jargon in user-facing copy
- Recommendations requiring platform change
</constraints>
```

