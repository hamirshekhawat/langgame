**Game Design Document: Language Tiles (Working Title)**

---

# 🎮 Game Design Section

## 1. Working Title
**Language Tiles** (placeholder): A relaxing tile-based language learning game.

## 2. Current Status
- **Status**: Design prototyping complete, first mechanics and core loops mapped.
- **Completed**: Learning loop, sentence-to-scene tile system, chapter progression structure.
- **In Progress**: UI prototyping, sentence tile design, first chapter vocabulary sets.
- **Issues**: Need to validate long-term engagement with real users.

## 3. Concept Statement
A peaceful, tile-based game where players build sentences in a foreign language to gradually assemble a beautiful, personalized world.

## 4. Genre
- Casual
- Language-learning
- Puzzle (light narrative)

## 5. Target Audience
- Casual learners of Chinese (beginner to intermediate)
- Ages 12+, educational or hobby interest
- Learners using mobile, tablet, or desktop

## 6. Unique Selling Points (USPs)
- Language learning through calm, low-pressure gameplay
- Tile-based sentence building that rewards comprehension
- Scene-building visuals that reflect vocabulary mastery
- Structured progression with sandbox rewards

## 7. Player Experience and Game POV
- **POV**: Top-down / 2D immersive view
- **Player Fantasy**: Build a tranquil world through language mastery
- **Emotions**: Calm, curiosity, pride, discovery
- **Player Role**: Learner, explorer, storyteller

## 8. Visual and Audio Style
- Soft pastel colors, flat tiles, minimalist scenes
- Ambient soundscapes (wind, birds, light music)
- Light audio feedback with each tile interaction

## 9. Game World Fiction
There is no central plot. Each chapter represents a theme in life (a park, cafe, home, market). As the player builds sentences, those locations come to life.

## 10. Monetization
- Free with optional cosmetic upgrades (scene skins, decorative tiles)
- No pay-to-win, no locked language content
- Possible premium version with extra scenes

## 11. Platform(s), Technology, and Scope
- Unity (2D)
- WebGL and Mobile (iOS/Android)
- Solo/small team project, MVP within 3–4 months
- First-playable: sentence building + 1 full chapter
- Major risks: content fatigue, drop-off after novelty

## 12. Core Loops
- Drag-and-drop sentence building (core loop)
- Successful sentence → scene tile placement → unlocks next challenge (progression loop)
- Optional: review mode → XP and collectible tiles (long-term engagement loop)

## 13. Objectives and Progression
- **Short-term**: Complete a sentence, unlock tile
- **Medium-term**: Complete chapter scenes
- **Long-term**: Unlock and decorate sandbox world

## 14. Game Systems

> _Note: This section reflects the updated terminology where “Sentence Tiles” are now “Language Tokens” and “Scene/Decorative Tiles” are “World Tiles.”_

### ✨ Separated Systems Overview
To reflect the distinction between interactive language learning and world-building, the system is now divided into two main mechanics:

- **Language Token System**: Handles all interactive grammar and sentence construction.
  - Uses draggable **Language Tokens**
  - Tokens represent vocabulary or grammar structures (subject, verb, object, connectors)
  - Players build valid sentences using tokens in the sentence strip
  - Token feedback includes highlights, sound effects, and grammar validation
  - Grammar rules applied during validation phase

- **World Tile System**: Handles visual feedback and scene construction.
  - Uses **World Tiles**
  - Tiles are unlocked upon sentence completion or through creative placement
  - World Tiles are placed in a chapter grid or sandbox world
  - Certain tile configurations trigger discovery sentences and ambient animations

### Cross-Tile Ambient Animations
Visual events (e.g., birds, trains, breezes) that move across multiple tiles triggered by chapter milestones, completed sentence clusters, or sandbox arrangements. These animations enhance immersion and reward players with a sense of living, breathing progress.

- In **sandbox mode**, ambient animations serve as reactive elements based on tile arrangement. Example:
  - Train tiles placed adjacently → train sprite animates across
  - Group of trees → bird or wind animation
  - Lantern tiles → floating lanterns at night
- Animations are non-blocking and low-intensity
- Triggered via tags, adjacency detection, or chapter milestones
- Implemented using tweening tools like LeanTween or DOTween

### Discovery Sentence Unlocks
These are special sentences unlocked not by direct instruction but by creative **World Tile** placement in both sandbox and chapter scenes.

- Unlocked by matching patterns (e.g., "tree" + "bench" + "lamp")
- Discovery Sentences:
  - Optional and visually distinct (e.g., glow border)
  - Not required for progression
  - Encourage experimentation and reinforce learned concepts
- When a discovery sentence is unlocked:
  - The sentence appears with audio/translation
  - **Associated tokens are also unlocked** (e.g., "长椅", "公园", "坐") for reuse in review mode or sandbox construction
- Technical Implementation:
  - Each DiscoveryPattern includes `required_tiles`, `unlocks_sentence_id`, and optional `unlocks_token_ids`
  - Triggered via spatial detection algorithms or adjacency graphs

### Additional Systems
- Scene tile placement logic
- Sentence evaluation + feedback
- Progress tracking (by vocabulary, grammar category)
- Sentence tagging for grammar type (e.g., subject, verb, modifier, connector)
- Support for abstract grammar via multi-strip sentences and syntax helper tiles

## 15. Interactivity
- Drag-drop sentence tiles
- Click/tap for feedback, translations, pronunciation
- Hover: sentence replay, visual/audio tooltip
- Scene responds with soft animations (reward feedback)

## 16. Chapter Progression Map
- Chapter 1: Morning in the Park (greetings, preferences)
- Chapter 2: Afternoon at Home (objects, negation, adjectives)
- Chapter 3: Train Station (time, directions, transactions)
- Chapter 4+: Café Lane, School Life, Market Day...

## 17. Sandbox Tile Placement Logic
- After completing Chapters 1–2, player unlocks Sandbox
- Each repeated sentence practice → places aesthetic tile
- Player can arrange unlocked tiles freely

## 18. MVP Systems and Features
- Sentence tile builder
- Scene tile unlocker
- Audio + visual feedback system
- Chapter progression
- Sandbox unlock
- Review system with spaced repetition and mini-challenges

## 19. Game Objects
- **Language Tokens** (text-based sentence parts)
  - Nouns, verbs, connectors, modifiers
  - Dragged into sentence strip UI
- **World Tiles** (scene visuals)
  - Placed on grid map after sentence completion
  - Includes decorative and animated types
- **NPCs** (non-interactive or click-to-speak characters)
  - Trigger dialogue, hint grammar rules
- **Discovery Sentences** (unlockable)
  - Triggered by world tile patterns
  - Unlock new language tokens for future use

## 20. Localization
- Initial: Chinese → English learners (Pinyin-based)
- Expandable to other L1-L2 pairs (e.g., Spanish → English)

## 21. Tools
- Unity
- Google Sheets for vocabulary design
- Ink or Yarn (for dialogue trees, optional)

## 22. Technical Documentation
- Tile data stored as ScriptableObjects or JSON
- Sentence evaluation via string pattern matching
- Save data: local first, cloud optional
- Tile type metadata for grammar structure logic

## 23. Ideas and Expansions
- Add voice recognition
- Multiplayer cooperative scene building
- Seasonal themes (e.g., Mid-Autumn Festival)

## 24. Unresolved Questions
**[RESOLVED]**
- Best reinforcement system: use spaced review quests + dialogue puzzles post-Chapter 3
- Sentence-first unlocks preferred, with scene silhouette foreshadowing
- Abstract grammar supported via tile categories and multi-line sentence logic

## 25. Prototypes
- MVP in Unity: sentence tiles + scene tile appearing on success
- Testing tile placement and feedback polish

---

# 📚 Glossary

**Language Token** – A draggable unit of language (e.g., word, phrase connector) used to build sentences in the sentence strip UI.

**World Tile** – A visual or animated object placed on the grid map to reflect progress or storytelling, unlocked through sentence completion.

**Discovery Sentence** – A special sentence that is revealed when specific tile configurations are placed; often unlocks additional tokens.

**Ambient Animation** – A non-blocking, visual animation triggered by the presence or arrangement of world tiles (e.g., birds flying over trees).

**Chapter** – A themed level or unit of progression that introduces new vocabulary and sentence structures.

**Sandbox Mode** – A freeform mode where unlocked tiles can be arranged creatively, often used for relaxation or reinforcement.

**Language Token Strip** – The UI area where players build and validate sentences using draggable tokens.

**Review Mode** – A practice feature that uses repetition and mini-challenges to reinforce learned sentences or grammar.

**Connector Token** – A type of language token that joins sentence parts (e.g., “but”, “and”, “because”).

**Token Metadata** – Attached grammar information used to validate whether a sentence is grammatically correct.

---

# 🧩 Implementation Details

## 📁 Database / Data Structure Design
To support sentence tiles, scene tiles, grammar structures, chapter progression, and discovery sentences, we propose the following key data tables or JSON objects:

### 1. `Sentences`
| Field               | Type      | Description                                      |
|--------------------|-----------|--------------------------------------------------|
| `id`               | String    | Unique sentence ID                               |
| `text_zh`          | String    | Sentence in Chinese                              |
| `text_pinyin`      | String    | Pinyin transcription                             |
| `text_en`          | String    | English translation                              |
| `chapter_id`       | String    | Chapter it belongs to                            |
| `grammar_tags`     | Array     | Subject, verb, connector, etc.                   |
| `audio_clip`       | FilePath  | Voice clip associated with sentence              |
| `unlocked_tile_id` | String    | World tile this sentence unlocks (if any)        |
| `is_discovery`     | Boolean   | Marks it as a discovery sentence                 |
| `unlocked_token_ids`| Array    | Tokens unlocked when this sentence is discovered |

### 2. `LanguageTokens`
| Field             | Type      | Description                                       |
|------------------|-----------|---------------------------------------------------|
| `id`             | String    | Unique token ID                                   |
| `text_zh`        | String    | Token text in Chinese                             |
| `pinyin`         | String    | Pronunciation                                     |
| `type`           | Enum      | `noun`, `verb`, `modifier`, `connector`, etc.     |
| `grammar_role`   | String    | Used for grammar validation                       |
| `icon_asset`     | FilePath  | Optional icon (e.g., part-of-speech visual)       |
| `available_in`   | Array     | Chapters or modes where token is available        |
| `is_discovery_only` | Boolean | True if token only unlocked via discovery         |

### 3. `WorldTiles`
| Field             | Type      | Description                                       |
|------------------|-----------|---------------------------------------------------|
| `id`             | String    | Unique tile ID                                    |
| `name`           | String    | Tile display name                                 |
| `type`           | Enum      | `scene`, `decorative`, `animated`                |
| `image_asset`    | FilePath  | Sprite or image used                              |
| `animation_tag`  | String    | Optional (e.g., triggers bird/train/etc.)         |
| `available_in`   | Array     | Chapters or sandbox zones where it's used         |

### 3. `Chapters`
| Field         | Type    | Description                                      |
|--------------|---------|--------------------------------------------------|
| `id`         | String  | Unique chapter ID                               |
| `title`      | String  | Chapter title                                   |
| `theme`      | String  | e.g., Park, Home, Train Station                 |
| `sentence_ids` | Array  | Sentence IDs introduced in this chapter         |
| `background` | FilePath| Background image/sound                          |

### 5. `AmbientAnimations`
| Field             | Type     | Description                                            |
|------------------|----------|--------------------------------------------------------|
| `id`             | String   | Unique animation ID                                    |
| `trigger_tags`   | Array    | Tags that trigger animation (e.g., 3x trees)          |
| `tile_path`      | Array    | Path tiles over which animation plays                 |
| `animation_asset`| FilePath | Sprite or animation to play                           |
| `context`        | Enum     | `chapter` or `sandbox`                                |

These data structures support scalability, modularity, and player progression across both linear (chapter) and open-ended (sandbox) gameplay.

---

# 📋 Progress & Production Tracker

## 🔧 Milestones
### Milestone 1: Core Language Token Builder
_(Updated naming from 'Sentence Tile Builder')_
- [ ] Set up Unity project (2D, WebGL-ready)
- [ ] Implement tile prefab (text + optional icon + metadata)
- [ ] Drag-and-drop UI logic for sentence strip
- [ ] Submit button logic and sentence validation
- [ ] Add feedback (highlight correct/wrong tiles, chime SFX)
- [ ] Load tile sets dynamically from JSON or ScriptableObject
- [ ] Drag-and-drop logic
- [ ] Sentence validation
- [ ] Feedback UI and audio

### Milestone 2: World Tile Unlock System
_(Updated naming from 'Scene Tile Unlock System')_
- [ ] Create simple tilemap or grid-based background
- [ ] Implement auto-placement logic for scene tiles
- [ ] Link successful sentence → unlock specific scene tile
- [ ] Add soft animations (fade-in, slight bounce)
- [ ] Trigger audio narration on tile unlock
- [ ] Sentence → scene mapping
- [ ] Visual animation feedback

### Milestone 3: Chapter 1 Integration
- [ ] Design sentence list and vocabulary tags
- [ ] Link each sentence to its reward tile
- [ ] Implement chapter-level progression tracker
- [ ] Add NPC trigger logic (simple sprite + dialogue bubble)
- [ ] Localized Pinyin + English translations
- [ ] NPC prompts and tile rewards
- [ ] Scene tile tracking and replay

### Milestone 4: Review System
- [ ] Implement spaced repetition review list
- [ ] Build “review challenge” screen
- [ ] Enable re-using sentence tiles from prior chapters
- [ ] Award XP or new decorative tiles for repeated success
- [ ] XP and collectible tile rewards

### Milestone 5: Sandbox Mode
- [ ] Unlock sandbox after Chapter 2 completion
- [ ] Implement grid placement for freeform tile arranging
- [ ] Save/load sandbox tile arrangements
- [ ] Add optional decoration tiles (plants, lights)
- [ ] Decoration tile management

### Milestone 6: Advanced Grammar Support
- [ ] Add connector tile logic (`because`, `although`, etc.)
- [ ] Implement multi-strip sentence layout
- [ ] Support tile metadata and basic grammar rules
- [ ] Validate placement by structure, not just order
- [ ] Connector tile validation

### Milestone 7: Testing & Polish
- [ ] UI polish: animations, fonts, hover states
- [ ] Sound polish: ambient, SFX, narration replay
- [ ] Bug fixing and edge-case testing
- [ ] Export WebGL build for feedback
- [ ] Add basic save/load system (local)
- [ ] Bug fixing and user testing

---

## 🔧 Resource Stack
### Language & Content
- [Tatoeba](https://tatoeba.org/), CC-CEDICT, Chinese Grammar Wiki
- Google Sheets + native speaker review

### Art & UI Assets
- [Kenney.nl](https://kenney.nl/assets), OpenGameArt, Itch.io, Humaaans
- Fiverr (optional commissions)

### Audio Assets
- OpenAI TTS, Freesound.org, Audacity

### Development Tools
- Unity 2D URP
- TextMeshPro, LeanTween
- ScriptableObjects, JSON data format
- Ink/Yarn (optional dialogues)

### Testing
- Google Forms, Discord testers, PlaytestCloud (free tier)

---

