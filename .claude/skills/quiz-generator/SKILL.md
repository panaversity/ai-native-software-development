---
name: quiz-generator
description: |
  ALWAYS generate interactive quizzes using the Quiz component (20-30 comprehensive questions).
  Creates MDX files with college-level conceptual questions, EQUAL LENGTH options (±2 words max),
  and randomized correctOption indices (0-3). Quizzes prevent length-based guessing by keeping all
  options similar word count. Features globally-registered Quiz component with built-in: progress
  tracking, answer validation, instant explanations, results page, color-coded feedback, theme support.
  Follows ##_chapter_##_quiz.md naming convention. CRITICAL: All options MUST be equal length.
allowed-tools: [Read, Bash, Write, Glob]
version: 3.1.0
---

# Quiz Generator: College-Level Interactive Chapter Assessments

**Version:** 3.1.0 | **Alignment:** Constitution v2.2.0, Principle 1 (AI-First Teaching) | **CRITICAL:** Always use Quiz component, EQUAL LENGTH options (±2 words), 20-30 comprehensive questions

**Quiz Component Location:** `book-source/src/components/Quiz.tsx` (globally registered—no imports needed)
**Usage Reference:** `book-source/src/components/QUIZ_USAGE.md` (example structure + best practices)
**Example Quiz:** `book-source/src/components/references/example-quiz.md` (full working example with all patterns)

---

## Purpose

Generate high-quality, college-level MCQ quizzes (20-30 comprehensive questions) using the globally-registered Quiz component (`<Quiz />`). Each quiz measures conceptual understanding with built-in interactive features including progress tracking, answer validation, instant explanations, results scoring, and color-coded feedback. **CRITICAL: All options MUST have equal length (±2 words maximum difference) to prevent length-based guessing.** The Quiz component automatically handles theme switching and mobile responsiveness.

**Output is ALWAYS a Quiz component, NEVER static markdown quizzes.** See example-quiz.md for complete working pattern.

**Core Principles:**
- Test understanding and application, not memorization
- **PREVENT LENGTH-BASED GUESSING: All options must be equal length (±2 words)**
- Randomize correct answer distribution across options (0-3 indices)
- Provide meaningful explanations for each answer
- Comprehensive coverage of chapter material (20-30 questions for thorough assessment)

---

## When to Activate

This skill should be used when creating end-of-chapter assessments. **CRITICAL: This skill ALWAYS generates interactive quizzes using the Quiz component—NEVER static markdown quizzes.**

Activate this skill when:
- Creating end-of-chapter assessments that MUST use the Quiz component
- Need college-level conceptual questions (20-30 comprehensive questions)
- Want interactive quiz with built-in scoring, feedback, and instant explanations
- **Require EQUAL LENGTH options (±2 words max) to prevent length-based guessing**
- Require randomized correct answers with consistent distribution (correctOption indices 0-3)
- Need fully responsive, accessible quiz with light/dark theme support
- Creating MDX-compatible quiz files using `<Quiz />` component

**Trigger phrases:**
- "Create a quiz for Chapter X"
- "Generate comprehensive chapter assessment for Chapter X"
- "Build an interactive quiz with 20-30 questions"
- "Create chapter quiz with equal length options"
- "Generate college-level assessment with equal-length MCQs"

**MANDATORY REQUIREMENTS:**
1. Use Quiz component (NEVER static markdown)
2. Generate 20-30 questions (comprehensive coverage)
3. **ALL options MUST be equal length (±2 words maximum difference)**
4. Randomize correctOption indices evenly across 0-3
5. Passing score: 70%

---

## Key Concepts

### College-Level Conceptual Questions

**Shift from Recall to Understanding:**

❌ **Recall (Avoid):**
> "What is a Python list?" → Tests memorization

✅ **Conceptual (Target):**
> "Given this code with list operations, what misconception does this error reveal?" → Tests understanding

**Why College-Level?**
1. Job readiness: Professional developers need to understand WHY, not just WHAT
2. AI-era skills: With AI generating code, understanding concepts matters more than syntax recall
3. Transfer learning: Conceptual knowledge transfers; memorized facts don't
4. Better assessment: Conceptual questions predict programming competence

**Cognitive Level Target:**
- 75%+ questions at Apply level or higher
- Focus on debugging, prediction, analysis (not recall)

---

### Quiz Component Architecture

**Built-in Features (No Manual Implementation Needed):**
- ✅ Progress bar showing completion percentage
- ✅ Question navigation (Back/Next buttons + dot navigation for jumping)
- ✅ Answer counter (X/Y answered)
- ✅ Validation: Can't submit until all questions answered
- ✅ Results page with score, statistics, and review option
- ✅ Color-coded feedback (green = correct, red = incorrect)
- ✅ Instant explanations shown after submission
- ✅ Question review with all answers and explanations visible
- ✅ Retake button to try again
- ✅ Light/Dark theme auto-switching
- ✅ Fully responsive (mobile, tablet, desktop)

**Why 20-30 Questions (Comprehensive Assessment)?**
- Comprehensive coverage of all chapter material (not just highlights)
- Quiz component handles navigation well with dot interface + Back/Next
- Progressive disclosure: one question per screen (not overwhelming)
- Mobile-friendly: progressive scrolling through one question at a time
- Thorough assessment ensures mastery before moving forward
- Matches college-level standards: comprehensive, not quick-check

---

### Answer Randomization with Quiz Component

**Requirements:**
- Correct answers distributed across 0-3 indices (not a/b/c/d)
- For 8 questions: ~2 per index (25% each)
- No obvious patterns
- Maximum 2 consecutive same answers

**Quiz Component Format:**
```javascript
{
  question: "Your question?",
  options: ["Option A", "Option B", "Option C", "Option D"],
  correctOption: 2,  // Index 0-3, NOT 1-4!
  explanation: "Why this is correct..."
}
```

**How to Randomize:**
1. Write questions first (don't worry about position)
2. After ALL questions written, shuffle correctOption values
3. Verify distribution is roughly equal
4. Ensure no 3+ consecutive same answers

📖 **Reference:** [answer-distribution.md](./references/answer-distribution.md) for verification methods

---

### Explanation Quality (Critical)

**Quiz component shows explanations immediately after submission.** This enables deeper learning than traditional quizzes:

**Good Explanations (60-150 words):**
1. **Explain WHY correct** (2-3 sentences)
2. **Address why distractors wrong** (1-2 sentences each)
3. **Add context/examples** (connections, real-world usage)

**Example:**
```javascript
explanation: "Lists are mutable (changeable) in Python, so append() modifies the original list.
This is different from strings, which are immutable—you can't change them after creation.
The add() method doesn't exist in Python (that's Java), insert() requires a position,
and push() is JavaScript. Understanding mutability is crucial for debugging variable scope issues."
```

---

## Quiz Architecture

### Fixed Constraints (Non-Negotiable)

```yaml
question_count: 20-30  # Comprehensive assessment (20-30 questions)
options_per_question: 4  # Always exactly 4 options
option_length: EQUAL  # ±2 words maximum difference (CRITICAL to prevent length guessing)
question_format: multiple_choice  # Only MCQ
correct_answer_distribution: random_equal  # indices 0-3 equally distributed
passing_score: 70  # 70% (14/20 or 21/30)
file_naming: ##_chapter_##_quiz.md  # e.g., 05_chapter_02_quiz.md
output_format: Markdown with Quiz component  # <Quiz {...} /> (globally registered)
component_globally_registered: true  # No imports needed
```

**CRITICAL ANTI-PATTERNS:**
- ❌ **LENGTH-BASED GUESSING: Options with different lengths** (e.g., 5 words vs 20 words)
  - Students can guess by selecting longest/shortest option
  - ALL options MUST be ±2 words maximum difference
  - MANUALLY VERIFY word count for every option
- ❌ Using array indices 1-4 (use 0-3!)
- ❌ Questions that test recall instead of understanding
- ❌ Explanations without addressing why distractors are wrong
- ❌ No randomization of correctOption values
- ❌ Fewer than 20 or more than 30 questions
- ❌ File naming like `##_quiz.md` (use `##_chapter_##_quiz.md`)

---

### File Structure (Quiz Component Format)

```markdown
---
sidebar_position: X  # e.g., 05 (lesson count + 1)
title: "Chapter X: [Topic] Quiz"
---

# Chapter X: [Topic] Quiz

Brief introduction (1-2 sentences describing what students will assess).

<Quiz
  title="Chapter X: [Topic] Assessment"
  questions={[
    {
      question: "Question 1 text here? (Conceptual, not recall)",
      options: [
        "Option A (8-12 words, equal length)",
        "Option B (8-12 words, equal length)",
        "Option C (8-12 words, equal length) ← CORRECT",
        "Option D (8-12 words, equal length)"
      ],
      correctOption: 2,  // Index 0-3 (NOT 1-4!)
      explanation: "Why correct (2-3 sentences). Why each distractor is wrong (1-2 sentences each).
        Additional context or real-world connection (1-2 sentences). Total: 80-150 words."
    },
    {
      question: "Question 2 text?",
      options: [
        "Option A (equal length: 10 words)",
        "Option B (equal length: 11 words)",
        "Option C (equal length: 10 words)",
        "Option D (equal length: 9 words) ← CORRECT"
      ],
      correctOption: 3,
      explanation: "Comprehensive explanation here..."
    },
    // ... 18-28 more questions (total: 20-30 questions)
  ]}
  passingScore={72}
/>
```

**Key Requirements (CRITICAL):**
- ✅ Exactly 4 options per question (no more, no less)
- ✅ **ALL options MUST be equal length (±2 words maximum) - MANUALLY COUNT WORDS**
- ✅ `correctOption` uses 0-3 index (NOT 1-4!)
- ✅ Explanations address why correct AND why each distractor is wrong
- ✅ No imports needed for `<Quiz />` (globally registered component)
- ✅ 20-30 questions total (comprehensive assessment)
- ✅ `passingScore={72}` (approximately 72% = 14/20 or 21/30)

**Word Count Verification Example:**
```
Option A: "Lists are mutable objects in Python" = 6 words ❌ Too short
Option A: "Lists are mutable objects in Python that can be changed" = 10 words ✅ Good
Option B: "Tuples are immutable sequences that cannot be modified" = 8 words ✅ Good (8-10 range)
Option C: "Dictionaries store key-value pairs for efficient lookups" = 7 words ❌ Too short (5-7 words off)
Option C: "Dictionaries store key-value pairs and enable efficient lookups" = 9 words ✅ Good (8-10 range)
```

📖 **Reference:** [file-naming.md](./references/file-naming.md) for naming conventions | [example-quiz.md](./references/example-quiz.md) for complete working example

---

## The Generation Process (Overview)

```
Chapter Content → Analyze → Select Topics → Generate Questions →
Design Distractors → Randomize Answers → Write Explanations →
Format Quiz Component → Validate → ##_chapter_##_quiz.mdx
```

### 7-Stage Process Summary

1. **Analyze Chapter Structure:** Identify core concepts and learning objectives
2. **Select 5-10 Key Topics:** Choose highest-impact concepts (not comprehensive coverage)
3. **Generate Conceptual Questions:** Write understanding-focused questions (no recall)
4. **Design Meaningful Distractors:** Create distractors testing specific misconceptions
5. **Randomize Correct Answers:** Shuffle correctOption indices (0-3); verify equal distribution
6. **Write Comprehensive Explanations:** 60-150 words explaining why correct AND why each distractor is wrong
7. **Format Quiz Component:** Use `<Quiz {...} />` with all 5-10 questions in questions array

📖 **Reference:** [generation-process.md](./references/generation-process.md) for detailed stage-by-stage workflow

---

## Quality Standards

### Content Quality
- ✅ 20-30 questions (comprehensive assessment)
- ✅ College-level conceptual (75%+ Apply or higher)
- ✅ Realistic scenarios (debugging, prediction, analysis)
- ✅ No obvious recall questions ("What is...?")

### Option Length Quality (CRITICAL - PREVENTS GUESSING)
- ✅ **ALL options MUST be equal length (±2 words maximum difference)**
- ✅ **MANUALLY COUNT WORDS for every option in every question**
- ✅ If option is 10 words, others must be 8-12 words
- ✅ Longest option ≠ always correct (verify distribution)
- ✅ No option noticeably longer or shorter than others
- ✅ Test by reading quiz: no option visually stands out by length

### Answer Randomization Quality (CRITICAL)
- ✅ Correct answers evenly distributed (indices 0-3: ~25% each for 20-30 Q)
- ✅ No 3+ consecutive same correctOption values
- ✅ No patterns (not 0,1,2,3,0,1,2,3...)
- ✅ All index values (0,1,2,3) represented equally

### Explanation Quality
- ✅ 80-150 words each (comprehensive, not rushed)
- ✅ Explain WHY correct (2-3 sentences)
- ✅ Address why EACH distractor is wrong (1 sentence each)
- ✅ Additional context (examples, connections, misconceptions)

### Component Format Quality
- ✅ Proper JSX syntax in MDX file
- ✅ Exactly 4 options per question (no more, no less)
- ✅ correctOption uses 0-3 indices (NOT 1-4!)
- ✅ File named: `##_chapter_##_quiz.mdx`
- ✅ No imports needed (Quiz globally registered)
- ✅ passingScore property set to 70

📖 **Reference:** [quality-checklist.md](./references/quality-checklist.md) for complete validation criteria

---

## Common Pitfalls (Top 6)

1. **LENGTH-BASED GUESSING (CRITICAL):** Options with wildly different lengths
   - ❌ Option A: 5 words | Option B: 15 words | Option C: 8 words | Option D: 6 words
   - ❌ Students guess longest option and score 95% by guessing
   - ✅ Option A: 10 words | Option B: 9 words | Option C: 11 words | Option D: 10 words (±2 words)
   - Fix: **MANUALLY COUNT WORDS for every option. Make all ±2 words maximum difference.**

2. **Index Confusion (CRITICAL):** Using correctOption: 1-4 instead of 0-3
   - ❌ `correctOption: 4` → References non-existent 5th option
   - ✅ `correctOption: 3` → Correct (last option, 4th item)
   - Fix: Always use 0-3 indices

3. **Testing Recall:** "What is X?" questions → Memorization
   - ❌ "What is a Python list?"
   - ✅ "Which operation modifies a list in-place?"
   - Fix: Focus on Apply/Analyze/Evaluate levels

4. **Weak Distractors:** Options that are obviously wrong
   - ❌ "Which is correct?" with options including "banana" or "xyz"
   - ✅ "Which is correct?" where all options are plausible misconceptions
   - Fix: Every distractor should test a specific misconception

5. **Missing Explanation Details:** Not addressing why distractors are wrong
   - ❌ "Lists are mutable." (only explains correct answer)
   - ✅ "Lists are mutable; strings aren't. The append() method exists, but add() doesn't (that's Java)..." (explains all options)
   - Fix: Address each distractor explicitly

6. **Answer Patterns:** Obvious distribution patterns in correctOption
   - ❌ correctOption sequence: 0,1,2,3,0,1,2,3... (repeating pattern)
   - ✅ correctOption sequence: 2,0,1,3,1,0,2,1... (random distribution)
   - Fix: Shuffle after writing; verify no patterns

📖 **Reference:** [pitfalls-and-solutions.md](./references/pitfalls-and-solutions.md) for all common mistakes

---

## File Naming Convention

### Pattern: `##_chapter_##_quiz.md`

Where:
- First `##` = sidebar_position (lesson count + 1)
- Second `##` = chapter number (zero-padded)
- Extension: `.md` (Quiz component is globally registered, no imports needed)

**Examples:**
- Chapter 2 (4 lessons): `05_chapter_02_quiz.md`
- Chapter 5 (6 lessons): `07_chapter_05_quiz.md`
- Chapter 14 (5 lessons): `06_chapter_14_quiz.md`

**Why this naming:**
- Matches lesson naming convention
- Clear chapter identification
- `.md` extension (Quiz component handles JSX rendering)
- Natural sorting places quiz at chapter end

📖 **Reference:** [file-naming.md](./references/file-naming.md) for complete guidance

---

## Integration with Book Workflow

### Related Skills
- **learning-objectives:** Align questions to chapter objectives
- **assessment-builder:** General assessment principles
- **technical-clarity:** Ensure question language is accessible
- **content-evaluation-framework:** Validate quiz quality

### Related Infrastructure
- **Constitution:** Aligns with Principle 1 (AI-First Teaching) and Principle 5 (Progressive Complexity)
- **Chapter Index:** `specs/book/chapter-index.md`

---

## Handoff Criteria

The quiz is ready for human review when:

**Content Complete:**
- [ ] 20-30 questions generated (comprehensive chapter coverage)
- [ ] ALL major topics covered (proportional across all lessons)
- [ ] 75%+ at Apply level or higher (conceptual, not recall)
- [ ] Each question tests distinct concept from chapter material
- [ ] No "What is...?" recall questions
- [ ] Realistic scenarios (debugging, analysis, prediction)

**Option Length Verified (CRITICAL - Prevents Length-Based Guessing):**
- [ ] **MANUALLY COUNTED WORDS for ALL options in ALL questions**
- [ ] ALL options within ±2 words of each other per question
- [ ] If option is 10 words, all others are 8-12 words (max variance ±2)
- [ ] No option visually stands out as significantly longer/shorter
- [ ] Longest option ≠ always correct (spot-checked distribution)

**Answer Randomization Verified:**
- [ ] correctOption uses 0-3 indices only (NOT 1-4)
- [ ] Correct answers evenly distributed (~25% each index for 20-30 Q)
- [ ] No 3+ consecutive same correctOption values
- [ ] No obvious patterns (0,1,2,3,0,1,2,3... is bad)
- [ ] All 4 indices (0,1,2,3) represented in distribution

**Explanation Quality Verified:**
- [ ] All explanations 80-150 words (comprehensive, not rushed)
- [ ] Each explanation explains WHY correct (2-3 sentences)
- [ ] Each explanation addresses WHY EACH distractor is wrong (1 sentence each)
- [ ] Additional context/examples provided (real-world connection)
- [ ] Distractors test specific misconceptions (not joke answers)

**Quiz Component Format Valid:**
- [ ] Valid JSX syntax in markdown file (proper braces, quotes)
- [ ] Exactly 4 options per question (no more, no less)
- [ ] correctOption values use 0-3 indices (spot-checked accuracy)
- [ ] Questions array contains all 20-30 questions
- [ ] passingScore property set to 72
- [ ] Quiz component used with correct props: title, questions, passingScore
- [ ] No imports needed - `<Quiz />` is globally registered
- [ ] File named: `##_chapter_##_quiz.md` (correct numbering)
- [ ] File uses `.md` extension
- [ ] YAML frontmatter correct: sidebar_position, title
- [ ] Saved to correct chapter directory

**Human Review Checklist:**
- [ ] Spot-check 5-10 questions for: option length equality, misconception testing, conceptual rigor
- [ ] Verify word counts are truly equal (±2 max) - can't be visual estimate
- [ ] Confirm technical accuracy of all explanations against chapter content
- [ ] Test Quiz component rendering in Docusaurus (actual interactive test)
- [ ] Verify navigation works (Back/Next, dots, submit, results)
- [ ] Check color-coded feedback displays correctly (green/red)
- [ ] Approve for deployment

📖 **Reference:** [quality-checklist.md](./references/quality-checklist.md) for complete validation

---

## Bundled Resources

This skill includes detailed reference documentation:

- **[generation-process.md](./references/generation-process.md)** - Complete 7-stage workflow for Quiz component generation with examples
- **[answer-distribution.md](./references/answer-distribution.md)** - Randomization strategies and verification methods for correctOption indices
- **[file-naming.md](./references/file-naming.md)** - Naming conventions with examples
- **[pitfalls-and-solutions.md](./references/pitfalls-and-solutions.md)** - Common mistakes and fixes for Quiz component quizzes
- **[quality-checklist.md](./references/quality-checklist.md)** - Complete validation checklist for Quiz component format

Use `Read` tool to access references as needed during quiz generation.

---

**Quiz Generator v3.1.0 ALWAYS creates interactive assessments using the globally-registered Quiz component with EQUAL LENGTH OPTIONS. NEVER creates static markdown quizzes. Comprehensive 20-30 question quizzes measure conceptual understanding with instant feedback and prevent length-based guessing. Built-in features include progress tracking, answer validation, color-coded results, explanations, retake buttons, and full theme support—no manual implementation needed. Every quiz MUST use <Quiz /> component with 20-30 questions, equal-length options (±2 words max), randomized correctOption indices (0-3), and 70% passing score.**
