# Learning Buddy — Avatar Build Roadmap

## Phase 1: 2D Avatar Images (current)
**Goal:** A library of square, upper-body character portraits the app can display.

### Characters (6)
| Folder | Character |
|---|---|
| `aarav/` | Cheerful 10-yr-old Indian boy, short black hair, warm brown skin |
| `meera/` | Bright 10-yr-old Indian girl, long black braid, light brown skin, gold studs |
| `kabir/` | Curious 11-yr-old boy, curly dark hair, deep brown skin, round glasses |
| `zoya/` | Lively 10-yr-old girl, short wavy dark-brown bob, fair skin, freckles |
| `leo/` | Friendly cartoon lion cub, fluffy golden mane, amber eyes, upright |
| `pip/` | Cuddly cartoon panda cub, big shiny eyes, upright |

### Outfits (8)
`school`, `hero`, `astronaut`, `scientist`, `doctor`, `sports`, `traditional`, `explorer`

### Emotions (6)
`happy`, `excited`, `thinking`, `surprised`, `proud`, `sleepy`

### File naming convention
`<character>/<outfit>-<emotion>.png`
Examples: `aarav/hero-excited.png`, `kabir/doctor-thinking.png`, `pip/astronaut-sleepy.png`

### Sets
- **Recommended start:** 78 images per build cycle
  - All 8 outfits × happy face = 48
  - Hero outfit × 5 other emotions = 30
- **Full set:** 288 images (6 × 8 × 6)

### Image spec
- Square, ≥1024×1024, PNG/JPG
- Upper body (head, shoulders, chest), centred, facing forward
- Plain soft pastel background
- No text, logos, or branded characters

---

## Phase 2: 3D Model Migration (future)
**Goal:** Replace static 2D images with an animated, interactive 3D avatar while keeping the same visual identity.

### Approach options
1. **Retarget from 2D reference** — Use the approved 2D images as concept art to model a 3D character in Blender/Maya.
2. **AI 2D→3D lift** — Tools like Rodin, Tripo, or Meshy can lift a character image to a rough 3D mesh; refine manually.
3. **Ready-made avatar platform** — Ready Player Me, VRoid, or MetaHuman create rigged 3D avatars from a photo/reference.

### Recommended path
- Start with **Ready Player Me** or **VRoid** for a rigged, app-ready avatar (supports Unity/Unreal/WebGL).
- Use the Phase 1 images as the visual reference to match hair, skin, and clothing.
- Export as `.glb`/`.gltf` for web, or `.fbx` for game engines.

### Deliverables
- One rigged 3D model per character
- Blend shapes / emotion presets matching the 6 emotions
- Outfit swap system (8 costume variants)

---

## Phase 3: Voice Integration (future)
**Goal:** Give each avatar a voice so it can speak to children during lessons.

### Components
1. **Text-to-Speech (TTS)** — Generate speech from lesson text.
   - Options: ElevenLabs (expressive, child-friendly voices), Google Cloud TTS, Azure TTS.
   - Pick a distinct voice per character (age-appropriate, warm, clear).
2. **Lip-sync** — Drive the 3D model's mouth from the audio.
   - Options: Rhubarb Lip Sync (open source), LiveLink Face, or engine-native lip-sync.
3. **Optional: Speech-to-Text (STT)** — Let the child talk back to the avatar.
   - Options: Whisper, Google Speech-to-Text.

### Workflow
- Lesson script → TTS → audio file
- Audio + 3D model → lip-sync animation
- Play animation + audio together in the app

### Deliverables
- One voice profile per character
- Lip-sync pipeline integrated into the app
- (Optional) Voice input for two-way conversation

---

## Build Order Summary
1. ✅ **2D image library** — app shows whatever exists; fast to iterate.
2. ⬜ **3D models** — migrate each character, matching the 2D look.
3. ⬜ **Voice + lip-sync** — bring the avatars to life.
