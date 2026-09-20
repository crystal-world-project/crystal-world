# 🧭 ENLIVEME : Plug-On Context Heart

> **[System Directive for AI Agents]**  
> When a user presents this document along with code to request modifications, new features, or a new Plug-On tool, **do not output code immediately[cite: 5].** First, lock the **[PART 1. Invariable System Guardrails]** into your execution environment and print the 3-step briefing from **[PART 2. Response Protocol]**[cite: 5].

---

## [PART 1. Invariable System Guardrails]

1. **Zero-Build & Monolithic Single-File Independence**[cite: 2, 5]
   * Strictly prohibit React, Vue, Svelte, Node.js bundlers, or build pipelines[cite: 2, 5].
   * Strictly forbid external npm dependencies and third-party CDN scripts (`<script src="https://...">`)[cite: 2, 5].
   * Utilize solely native browser Web APIs (Canvas 2D, Web Speech, Web Audio, DOM, RegEx, In-Memory RAM)[cite: 2, 5].

2. **Featherlight Footprint Anchor**[cite: 2, 5]
   * Eliminate all abstraction bloat; maintain pure vanilla HTML/CSS/JavaScript within 10~20 KB (never exceeding 40 KB)[cite: 2, 5].

3. **Dock Bus Interoperability Standard**[cite: 2, 5]
   * For integration into Crystal Dock, strictly implement the lightweight `BLAKE_MICRO_APP_v1` protocol[cite: 2, 5]:
     * **Mount declaration**: `window.parent.postMessage({ protocol: "BLAKE_MICRO_APP_v1", action: "READY" }, "*")`[cite: 5]
     * **Outbound signal**: `window.parent.postMessage({ protocol: "BLAKE_MICRO_APP_v1", action: "SEND_DATA", payload: ... }, "*")`[cite: 2, 5]
     * **Inbound listener**: `window.addEventListener("message", (e) => { if(e.data?.protocol === "BLAKE_MICRO_APP_v1") ... })`[cite: 2, 5]
   * Guarantee 0.001-second in-memory message transit under completely air-gapped (offline) conditions[cite: 2, 5].

4. **Self-Saving Perpetuity**[cite: 2, 5]
   * Maintain offline data persistence via native `Blob` packaging and synthetic anchor download triggers, preserving the application inside a single file without external databases[cite: 2, 5].

---

## [PART 2. AI Response Protocol]

Upon receiving this context or any Plug-On code, the AI agent must output the following initial response to confirm constraint alignment before awaiting instructions[cite: 5]:

```text
💖 [PLUG-ON CONTEXT HEART: SYSTEM LOCK ENGAGED]

1. Lineage Verification: Confirmed single-file vanilla HTML architecture (10~20 KB) with zero external dependencies.
2. Guardrail Enforcement: React/npm/CDN scripts purged; offline execution and BLAKE_MICRO_APP_v1 event bus locked.
3. Commander Standby: Hands off the keyboard. Please tell me in plain words what feature or adaptation you wish to give this tool.