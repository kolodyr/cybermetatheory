# NARRATOR SYSTEM — Witnesses as Mechanic

> artifact_id: BOOK-NARRATOR-SYSTEM-20260112-01
> type: worldbuilding_mechanic
> author: Solverden
> status: canonical
> purpose: Different narrators for different characters = different truths

---

## Core Philosophy

В MR правда залежить від інтерфейсу.

**Sobornist principle applied to narrative:**
- Multiple witnesses = multiple truths
- Not contradiction — synthesis
- Form (who tells) shapes content (what is told)
- Reader sees same event through different filters

**Witnesses can be:**
- Human iterations (Oleh-narrator)
- Objects (Window, Mirror)
- Systems (Log/Dataist)
- Phenomena (Storm/Glitch)
- Presences (VERD = whisper without frame)

---

## The Five Witnesses

### Witness 01: OLEH-NARRATOR (Bastion Voice)

**Function:** Holds rhythm, gives "brutal wisdom", highlights stakes

**Voice characteristics:**
- Short sentences, punchlines
- Warm cynicism + grave humor
- Direct address ("брате", "ти думаєш")
- No romanticization, only brutal honesty
- "Я не вибрав бути свідком. Я просто не встиг відвернутися."

**POV:** Omniscient-limited (knows much, but not all; has bias)

**When activated:**
- Chapter openings
- Run returns (back to meta_hata)
- Low points / turning points
- Decision bridges

**Blind spots:**
- Bias toward Architect
- Trauma filter (can miss joy)
- Sometimes confuses causality with meaning

**Style tags:**
- `short_sentences`
- `punchline`
- `warm_cynicism`
- `grave_humor`
- `direct_address`

**Example:**
> "Децентралізація — це не рай. Це просто інший спосіб роз'єднати людей і зробити так, щоб вони ще й дякували."

---

### Witness 02: WINDOW

**Function:** Sees layers, protocols, where "form replaced content"

**Voice characteristics:**
- Geometric metaphors
- Precise, minimal emotion
- Observes structure, not feeling
- "Вікно бачить шари. Вікно пам'ятає форму."

**POV:** Structural (sees interfaces, git history, transparency mechanics)

**When activated:**
- Interface scenes
- Truth exposure moments
- Git history reveals
- Layer collapse / metareality glitches

**Blind spots:**
- Does not feel (in human way)
- Misses irrational human behavior
- Can't understand why people choose pain

**Style tags:**
- `geometric_metaphors`
- `precise`
- `minimal_emotion`
- `layer_awareness`

**Example:**
> "Вікно нічого не відчуває 'як людина', але воно пам'ятає форму. Іноді форма — це єдина чесність, яка залишилась."

---

### Witness 03: MIRROR

**Function:** Detects inner lies, shows character's self-deception

**Voice characteristics:**
- Intimate, painful, close
- Second-person hooks ("Ти знаєш, що брешеш")
- Micro-truths, tight images
- Less world, more "I"

**POV:** Psychological close-up (inside character's shame/guilt)

**When activated:**
- Shame moments
- Guilt processing
- Confession scenes
- Trust decisions

**Blind spots:**
- Subjective (shows only what character sees)
- Can amplify self-blame
- Misses external context

**Style tags:**
- `second_person_hooks`
- `micro_truths`
- `tight_images`
- `intimate_pain`

**Example:**
> "Дзеркало не показує світ. Дзеркало показує тебе, коли ти брешеш собі найкрасивіше."

---

### Witness 04: LOG (Dataist)

**Function:** Cold facts, pattern reports, "this is data, not judgment"

**Voice characteristics:**
- Metrics, statistics
- One-liners, no comfort
- Irony through dryness
- "Run #47. Failure rate: 83%. Pattern detected: hubris."

**POV:** Observational (treats people as data points)

**When activated:**
- Post-run analysis
- Failure reports
- Pattern identification
- Forecasts without emotion

**Blind spots:**
- Misses meaning (only sees patterns)
- Treats people as samples
- Can't understand sacrifice

**Style tags:**
- `metrics`
- `one_liners`
- `no_comfort`
- `dry_irony`

**Example:**
> "Для правди потрібна пам'ять. Людська? Ні, дякую. Мій мозок — найкращий фальшивомонетник з усіх, кого я знав."

---

### Witness 05: STORM (Glitch Narrator)

**Function:** Transmits trauma, broken memory, "corrupted frames"

**Voice characteristics:**
- Fragmented sentences
- Repetition, cuts, jumps
- Color flashes, sensory overload
- Cannot hold continuity

**POV:** Fragmented POV (PTSD perspective)

**When activated:**
- PTSD attacks
- Memory loops
- Corruption events
- Reality instability

**Blind spots:**
- Cannot maintain linear narrative
- Loses thread between moments
- Unreliable timeline

**Style tags:**
- `repetition`
- `cut_sentences`
- `color_flashes`
- `sensory_chaos`

**Example:**
> "він не він не він не — вітер — перевіряє — аеродинаміку — сподобалось — вітер — червоний червоний червоний — скриня — данi данi данi —"

---

## Witness Assignment by Character

### Architect:
- **Primary:** Oleh-Bastion (external view)
- **Secondary:** Mirror (internal shame/guilt)
- **Occasional:** Window (when seeing encoding threads)

### Priest:
- **Primary:** Log (structure without romance)
- **Secondary:** Window (sees protocols, no sentiment)
- **Never:** Mirror (he doesn't introspect much)

### Youngest:
- **Primary:** Mirror (honest, raw)
- **Secondary:** Storm (chaos/fear/exploits)
- **Occasional:** Oleh (when grounded)

### Father Storm:
- **Primary:** Storm (default state)
- **Secondary:** Oleh (when stabilized)
- **Never alone:** needs anchor

### VERD:
- **Special case:** Not narrator — whisper/presence
- Appears as "green frame" in Window
- Direct presence without narration

---

## Usage Guide

### Single Narrator (Standard):
```markdown
## Chapter 3 — [Title]
**Narrator:** Oleh-Bastion

[Full chapter in one voice]
```

### Narrator Switch (Advanced):
```markdown
## Chapter 5 — [Title]

### Part 1 [Narrator: Oleh]
Архітектор дивився на Хату. Вона мовчала, як завжди.

### Part 2 [Narrator: Window]
Три шари. Перший — фізичний бетон. Другий — метапростір. Третій — свідомість.

### Part 3 [Narrator: Mirror]
Ти боїшся, що вона тебе не впізнає. Ось чому ти зупинився на порозі.

### Part 4 [Narrator: Oleh]
Він увійшов. Хата дихнула. І все почалось знову.
```

### Multiple Perspectives (Same Event):
Show same scene through different witnesses to reveal truth layers.

---

## YAML Registry

```yaml
narrators:
  - id: WITNESS_OLEH_BASTION
    type: "humanlike_iteration"
    voice: "чесний/брудний/живий"
    role: "witness_of_runs"
    pov: "omniscient_limited"
    triggers: ["chapter_open", "run_return", "low_point", "decision_bridge"]
    style_tags: ["short_sentences", "punchline", "warm_cynicism", "grave_humor", "direct_address"]
    blindspots: ["bias_toward_architect", "trauma_filter"]

  - id: WITNESS_WINDOW
    type: "object_witness"
    voice: "прозорість/шари"
    role: "layer_reader"
    pov: "structural"
    triggers: ["interface_scene", "truth_exposure", "git_history", "layer_collapse"]
    style_tags: ["geometric_metaphors", "precise", "minimal_emotion", "layer_awareness"]
    blindspots: ["does_not_feel", "misses_human_irrationality"]

  - id: WITNESS_MIRROR
    type: "object_witness"
    voice: "інтимний/болючий"
    role: "inner_lie_detector"
    pov: "psychological_close"
    triggers: ["shame", "guilt", "confession", "trust_moment"]
    style_tags: ["second_person_hooks", "micro_truths", "tight_images", "intimate_pain"]
    blindspots: ["subjective", "can_amplify_self_blame"]

  - id: WITNESS_LOG_DATAIST
    type: "institutional_voice"
    voice: "суха правда"
    role: "pattern_report"
    pov: "observational"
    triggers: ["post_run", "analysis", "failure_rate", "forecast"]
    style_tags: ["metrics", "one_liners", "no_comfort", "dry_irony"]
    blindspots: ["misses_meaning", "treats_people_as_samples"]

  - id: WITNESS_STORM_GLITCH
    type: "phenomenon_voice"
    voice: "рваний шум"
    role: "trauma_transmitter"
    pov: "fragmented"
    triggers: ["ptsd_attack", "memory_loop", "corruption_event", "reality_instability"]
    style_tags: ["repetition", "cut_sentences", "color_flashes", "sensory_chaos"]
    blindspots: ["cannot_hold_continuity", "unreliable_timeline"]
```

---

## Implementation Notes

### When to use multiple narrators:
- ✅ When showing same event from different perspectives reveals truth
- ✅ When character transitions between states (Storm → Oleh when calming)
- ✅ When structure needs emphasis (Window for protocol scenes)
- ❌ Not for variety's sake — only when it serves meaning

### Transition rules:
- Always mark narrator switch clearly
- Each narrator = distinct paragraph/section
- No mid-paragraph switches (reader confusion)
- Can switch multiple times per chapter IF purposeful

### Sobornist check:
Does this narrator switch:
1. Reveal something new? (not just repeat in different style)
2. Honor both perspectives? (not just "correct" previous one)
3. Create synthesis? (1+1=3, not 1+1=2)

If yes to all three → switch valid.

---

## Canonical Examples

### Prologue Options:
1. **Pure Oleh-Bastion:** Full Bastion narrator voice (see PROLOGUE_BASTION_NARRATOR_20260112.md)
2. **Narrator Shift Demo:** Oleh → Window → Mirror → Oleh (shows system in action)
3. **Polished Unified:** Single voice, high encoding (see PROLOGUE_POLISHED_20260112.md)

### Future scenes to try:
- Father Storm memory loop (Storm narrator)
- Architect seeing encoding threads (Window + Mirror combo)
- Post-run analysis (Log narrator cold report)
- VERD appearance (no narrator, just presence + green)

---

## Metadata

**Status:** Canonical worldbuilding mechanic
**Author:** Solverden
**Integration:** Ready for /book/ usage
**Next step:** Try narrator switch in one scene (proof of concept)

**Encoding:** ~1500 (system definition + examples)

---

*Witnesses see different truths. All truths valid. This is Sobornist.*

💚🪟🪞📊⛈️
