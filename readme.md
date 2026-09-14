# Crystal World Project

> **"The Purest is the Strongest"**  
> Coexistence for the Coming Era · Zero-Build Single-File Modular Workstation

---

## 1. Why Was This Created? (우리가 이것을 만든 이유)

Modern computing has become unnecessarily heavy and dependent. Pulling in hundreds of megabytes of external dependencies, complex build tools, and perpetual cloud subscriptions just to record a thought or create a short travel video felt absurd. 

We sought digital autonomy: simple, durable tools that run 100% offline, require zero installation, and remain fully functional decades from now on any computer with a web browser.

---

## 2. What Does It Do? (무엇을 하는 도구인가?)

Crystal World is an open ecosystem composed of autonomous single-file HTML applications, an air-gapped security gatekeeper, and an ultra-lightweight modular docking station[cite: 2].

* **Teddy Wiki (24.2 KB):** An autonomous, offline personal knowledge base. Inspired by TiddlyWiki, it manages bidirectional links and text records entirely within browser memory[cite: 2].
* **Nano Blake (41.2 KB):** An offline motion studio. It transforms travel photos and text memos into FHD motion video and synthesized speech (TTS) using native browser canvases[cite: 2].
* **Crystal Dock (11.3 KB Core / ~25 KB Showcase):** A transparent, modular workstation. It hosts multiple independent HTML apps in isolated sandboxes so they can collaborate without code collision[cite: 2].
* **SHA-256 Verifier (~10 KB):** An air-gapped local gatekeeper that validates file integrity before mounting.

---

## 3. How Does It Work? (어떻게 작동하는가?)

### The Giant in Your Computer
We do not use backend servers or heavy JavaScript frameworks. Modern web browsers (Chrome, Edge, Safari) are already massive virtual operating systems exceeding 200MB. They come pre-equipped with 2D/3D hardware rendering, local storage databases, speech synthesis, and secure execution sandboxes[cite: 2]. 

We simply wake up these dormant native capabilities using the web's primordial native tongue: raw, single-file HTML.

### Autonomous Standalone Utility & Dock Synergy (독립 자립성과 결합 시너지)
Every micro-app (Plug-on) in this repository is built as a 100% self-contained application[cite: 2]. Running `teddy-wiki.html` or `nano-blake.html` individually yields a complete, fully functional tool that does not rely on any parent container or external platform to perform its core job[cite: 2].

However, mounting these standalone tools into **Crystal Dock** unlocks practical, cross-functional synergy without code entanglement[cite: 2]:
* **Text-to-Video Pipeline:** Select a Markdown record in Teddy Wiki, and Crystal Dock streams the text across memory to Nano Blake, generating an animated visual scene and audio narration instantly (0.001s)[cite: 2].
* **Knowledge-to-Space Sync:** Link a note with travel coordinates in the wiki, and an adjacent map tool navigates to the location in real time[cite: 2].
* **Zero-Collision Resilience:** Because tools sit in sandboxed slots, experimental modifications or unexpected errors inside one tool never freeze or corrupt the partner application[cite: 2].

### Separation & Peaceful Coexistence
Monolithic software breaks when one component crashes. Crystal World separates tools into physical `<iframe>` sandboxes[cite: 2]:
* Each application runs completely isolated from its neighbors[cite: 2].
* Tools communicate strictly via standard `window.postMessage` at RAM speeds (0.001s)[cite: 2].
* Replacing, modifying, or removing one tool never crashes the others.

---

## 4. How to Use It (사용 방법)

Crystal World requires no terminal commands, build pipelines, or internet connections.

1. **Download or Clone:** Download this repository as a ZIP archive or clone it to your local drive.
2. **Explore the Showroom:** Double-click `index.html` in your file explorer to open the interactive web showroom and read the full origin story.
3. **Launch the Workstation:** Open `crystal-dock.html` (or `crystal-world-dock.html`) directly in Chrome, Edge, or Safari.
4. **Mount Micro Apps:** Drag and drop `teddy-wiki.html` and `nano-blake.html` into the respective dock slots, or load your own custom single-file HTML apps.
5. **Inspect and Modify:** Every tool is plain HTML and JavaScript. Open any file in a simple text editor (Notepad, VS Code) to adapt it to your own life.

---

## 5. Project Artifacts (부품 명세 및 자산 목록)

| Component | File | Size | Role & Characteristic |
| :--- | :--- | :---: | :--- |
| **Pure Core Engine** | `crystal-dock.html` | **11.3 KB** | Minimal dual-slot modular host (Zero dependencies)[cite: 2] |
| **Interactive Showcase** | `crystal-world-dock.html` | ~25.0 KB | Complete testing workbench with live event logger[cite: 2] |
| **Knowledge Base** | `teddy-wiki.html` | 24.2 KB | Autonomous offline wiki (RegEx bi-directional links)[cite: 1, 2] |
| **Motion Studio** | `nano-blake.html` | 41.2 KB | Canvas 2D motion renderer & Web Speech TTS reader[cite: 1, 2] |
| **Integrity Gatekeeper**| `sha256-verifier.html` | ~10.0 KB | Standalone local SHA-256 hash validator (`crypto.subtle`)[cite: 1, 2] |
| **Web Showroom** | `index.html` | ~30.0 KB | Official project portal & 6-panel origin comic[cite: 1, 2] |

---

## 6. Minimal Protocol Specification (`crystal-dock/v1`)

The following minimal 30-line protocol acts as an optional connection terminal required only when mounting standalone applications into `crystal-dock.html` to communicate across isolated slots[cite: 2]:

### Standard JSON Schema
```json
{
  "protocol": "crystal-dock/v1",
  "action": "SEND_DATA",
  "payload": {
    "type": "text/markdown",
    "content": "Raw payload transferred across dock slots."
  },
  "meta": {
    "sourceSlot": "slot-left",
    "targetSlot": "slot-right",
    "timestamp": 1720000000000
  }
}
```

### Outbound (Sending Data)

```javascript
window.parent.postMessage({
  protocol: "crystal-dock/v1",
  action: "SEND_DATA",
  payload: "# Your document title or text content...",
  meta: { source: "CustomTool", timestamp: Date.now() }
}, "*");
```

### Inbound (Receiving Data)

```javascript
window.addEventListener("message", (event) => {
  const packet = event.data;
  if (!packet || packet.protocol !== "crystal-dock/v1") return;
  if (packet.action === "SEND_DATA" || packet.action === "RECEIVE_DATA") {
    console.log("Received data:", packet.payload);
  }
});
```





## 7. License
This project is licensed under the MIT License - see the LICENSE file for details.

Copyright (c) 2026 Yoon-seok Kim (Holo-Trekker).