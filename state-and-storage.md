# State and Storage Model

## Current state model

LearnFIL currently relies on browser localStorage to manage learning state.

localStorage is used to store:

1. Completed lessons  
2. Module progress  
3. Lesson execution state  
4. Validation results  
5. UI preferences and navigation context  

This allows the application to run entirely client side, work offline, and avoid any centralized backend dependencies.

At present, localStorage is the active and implemented storage mechanism.

---

## Why localStorage today

localStorage is used in the current phase because it:

1. Keeps learning friction low  
2. Avoids identity and authentication complexity  
3. Makes progress immediately usable without setup  
4. Enables fast iteration on curriculum and UX  

This choice prioritizes accessibility and ease of experimentation while the platform evolves.

---

## Known limitations of the current approach

localStorage is:

1. Device specific  
2. Browser specific  
3. Not verifiable  
4. Easy to reset or modify  
5. Not portable across environments  

These limitations are acknowledged and are the primary motivation for introducing a verifiable storage layer.

---

## Direction: Filecoin onchain cloud

LearnFIL is intentionally evolving toward using Filecoin onchain cloud as the canonical storage layer for learning progress.

The goal is for meaningful learning events to be:

1. Content addressed  
2. Persisted in a decentralized manner  
3. Verifiable over time  
4. Portable across devices and communities  

Filecoin will anchor learning checkpoints and curriculum state as immutable records.

---

## Planned role of Filecoin

Filecoin is planned to be used for:

### Learning checkpoints
Each completed lesson or module will produce a checkpoint containing:

1. Lesson or module identifier  
2. Timestamp  
3. Validation hash  
4. Optional metadata  

These checkpoints will be stored as content addressed data and referenced by a CID.

### Curriculum snapshots
Curriculum versions will be snapshotted so that:

1. Progress can reference a specific curriculum state  
2. Changes to lessons are transparent  
3. Certificates and attestations can be audited  

---

## Relationship between localStorage and Filecoin

In the target architecture:

Filecoin will define canonical learning state.  
localStorage will act as a cache and execution layer.

localStorage will store:

1. In progress session state  
2. Temporary execution data  
3. Cached references to Filecoin CIDs  

If localStorage is cleared, progress can be reconstructed from Filecoin anchored checkpoints once integration is complete.

---

## Current implementation status

1. localStorage based progress tracking is fully implemented  
2. Filecoin onchain cloud integration is in progress  
3. Checkpoint schemas and storage flows are being designed  
4. Migration paths from local-only state to anchored state are planned  

---

## Design intent

LearnFIL is moving from local-first to verifiable-first.

Local state enables fast learning.  
Filecoin enables durable, portable, and auditable learning records.