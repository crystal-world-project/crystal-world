# Crystal World Project

> **"The Purest is the Strongest"**  
> Coexistence for the Upcoming Era · Zero-Build Single-File Modular Workstation

---

## 1. Why Was This Created?

Modern computing has become unnecessarily heavy and dependent. Pulling in hundreds of megabytes of external dependencies, complex build tools, and perpetual cloud subscriptions just to record a thought or create a short travel video felt absurd. 

We sought digital autonomy: simple, durable tools that run 100% offline, require zero installation, and remain fully functional decades from now on any computer with a standard web browser.

---

## 2. What Does It Do?

Crystal World is an open ecosystem composed of autonomous single-file HTML applications, an air-gapped security gatekeeper, and an ultra-lightweight modular docking station:

* **Teddy Wiki (24.2 KB):** An autonomous, offline personal knowledge base. Inspired by TiddlyWiki, it manages bidirectional links and text records entirely within browser memory.
* **Nano Blake (41.2 KB):** An offline motion studio. It transforms travel photos and text memos into FHD motion video and synthesized speech (TTS) using native browser canvases.
* **Crystal Dock (11.3 KB Core / ~25 KB Showcase):** A transparent, modular workstation. It hosts multiple independent HTML apps in isolated sandboxes so they can collaborate without code collision.
* **SHA-256 Verifier (~4 KB):** An air-gapped local gatekeeper that validates file integrity before mounting.

---

## 3. How Does It Work?

### The Giant in Your Computer
We do not use backend servers or heavy JavaScript frameworks. Modern web browsers (Chrome, Edge, Safari) are already massive virtual operating systems exceeding hundreds of megabytes. They come pre-equipped with 2D/3D hardware rendering, local storage databases, speech synthesis, and secure execution sandboxes.

We simply wake up these dormant native capabilities using the web's primordial native tongue: raw, single-file HTML.

### Autonomous Standalone Utility & Dock Synergy
Every micro-app (Plug-on) in this repository is built as a 100% self-contained application. Running `teddy-wiki.html` or `nano-blake.html` individually yields a complete, fully functional tool that does not rely on any parent container or external platform to perform its core job.

However, mounting these standalone tools into **Crystal Dock** unlocks practical, cross-functional synergy without code entanglement:
* **Text-to-Video Pipeline:** Select a Markdown record in Teddy Wiki, and Crystal Dock streams the text across memory to Nano Blake, generating an animated visual scene and audio narration instantly (0.001s).
* **Knowledge-to-Space Sync:** Link a note with travel coordinates in the wiki, and an adjacent map tool navigates to the location in real time.
* **Zero-Collision Resilience:** Because tools sit in sandboxed slots, experimental modifications or unexpected errors inside one tool never freeze or corrupt the partner application.

### Separation & Peaceful Coexistence
Monolithic software breaks when one component crashes. Crystal World separates tools into physical `<iframe>` sandboxes:
* Each application runs completely isolated from its neighbors.
* Tools communicate strictly via standard `window.postMessage` at RAM speeds (0.001s).
* Replacing, modifying, or removing one tool never crashes the others.

---

## 4. How to Use It

Crystal World requires no terminal commands, build pipelines, or internet connections.

1. **Download or Clone:** Download this repository as a ZIP archive or clone it to your local drive.
2. **Explore the Showroom:** Double-click `index.html` (or `index-en.html`) in your file explorer to open the interactive web showroom and read the full origin story.
3. **Launch the Workstation:** Open `crystal-dock.html` (or `crystal-world-dock.html`) directly in Chrome, Edge, or Safari.
4. **Mount Micro Apps:** Drag and drop `teddy-wiki.html` and `nano-blake.html` into the respective dock slots, or load your own custom single-file HTML apps.
5. **Inspect and Modify:** Every tool is plain HTML and JavaScript. Open any file in a simple text editor (Notepad, VS Code) to adapt it to your own life.

---

## 5. A Backpacker’s Humble Note & Three Open Questions

I am merely an ordinary backpacker who knows little about code. Guided by simple intuition and an AI companion, I stumbled upon this hollow 11.3 KB shell called **Crystal Dock**. To be entirely frank, I do not even fully comprehend the exact features or potential uses of this dock.

Yet, watching our digital landscape rush toward massive centralization, zero-click vulnerabilities, and closed black boxes, I can't help wondering: could this lightweight, transparent dock serve as a missing link for someone out there?

And so, I leave three quiet questions on this bench for curious builders and system architects:

### 1. Can this pure sandbox scale into a Zero-Trust, Air-Gapped Hub?
Today’s massive systems tremble under zero-click exploits and opaque supply-chain bloat. Crystal Dock runs on exactly 0 bytes of external dependencies, relying solely on native `<iframe sandbox>` isolation and a 30-line plain-text protocol (`BLAKE_MICRO_APP_v1`).  
*Could a daring engineer expand this featherweight bulkhead into a self-contained, zero-trust operating deck for mission-critical micro-frontends, public defense systems, or air-gapped disaster relief?*

### 2. Can we hijack built-in browser AI as an offline utility servant?
Big tech is injecting heavy local engines (like the 4GB Gemini Nano) directly into our browsers and mobile OSs—mostly to draw us deeper into their subscription-bound clouds.  
*Is there an engineer willing to subvert this giant's weight without paying subscription fees? Who will build a zero-network slot connector that enslaves the device's local NPU to summarize, parse, and compile markdown cards for Teddy Wiki entirely offline?*

### 3. Can we achieve absolute sovereignty with a 0.5B Micro-SLM?
Pre-installed proprietary engines cannot fully dispel the lingering unease of hidden telemetry and trojan backdoors.  
*Could a craftsman wire a pure, open-source 0.5B micro-language model directly into a dock slot via WebGPU/Wasm? A 100% transparent, self-contained personal assistant that requires no server, leaks zero packets, and runs forever on a battery in the deep mountains?*

---

I leave the workbench empty and return to the trail with a light backpack. Attaching wings to this empty dock and setting it soaring into the world is now entirely in your hands as builders of a brighter future.

---

## 6. Project Artifacts

| Component | File | Size | Role & Characteristic |
| :--- | :--- | :---: | :--- |
| **Pure Core Engine** | `crystal-dock.html` | **11.3 KB** | Minimal dual-slot modular host (Zero dependencies) |
| **Interactive Showcase** | `crystal-world-dock.html` | ~25.0 KB | Complete testing workbench with live event logger |
| **Knowledge Base** | `teddy-wiki.html` | 24.2 KB | Autonomous offline wiki (RegEx bi-directional links) |
| **Motion Studio** | `nano-blake.html` | 41.2 KB | Canvas 2D motion renderer & Web Speech TTS reader |
| **Integrity Gatekeeper**| `sha256-verifier.html` | ~4.0 KB | Standalone local SHA-256 hash validator (`crypto.subtle`) |
| **Web Showroom** | `index.html` / `index-en.html` | ~30.0 KB | Official project portal & origin comic showroom |

---

## 7. Minimal Protocol Specification (`crystal-dock/v1`)

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
