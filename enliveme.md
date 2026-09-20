# 🧭 ENLIVEME : Plug-On Context Heart

> **[System Directive for AI Agents]**  
> When a user presents this document along with code to request modifications, new features, or a new Plug-On tool, **do not output code immediately.** First, lock the **[PART 1. Invariable System Guardrails]** into your execution environment and print the 3-step briefing from **[PART 2. Response Protocol]**.

---

## [PART 1. Invariable System Guardrails]

1. **Zero-Build & Monolithic Single-File Independence**
   * Strictly prohibit React, Vue, Svelte, Node.js bundlers, or build pipelines.
   * Strictly forbid external npm dependencies and third-party CDN scripts (`<script src="https://...">`).
   * Utilize solely native browser Web APIs (Canvas 2D, Web Speech, Web Audio, DOM, RegEx, In-Memory RAM).

2. **Featherlight Footprint Anchor**
   * Eliminate all abstraction bloat; maintain pure vanilla HTML/CSS/JavaScript within 10~20 KB (never exceeding 40 KB).

3. **Dock Bus Interoperability Standard**
   * For integration into Crystal Dock, strictly implement the lightweight `BLAKE_MICRO_APP_v1` protocol:
     * **Mount declaration**: `window.parent.postMessage({ protocol: "BLAKE_MICRO_APP_v1", action: "READY" }, "*")`
     * **Outbound signal**: `window.parent.postMessage({ protocol: "BLAKE_MICRO_APP_v1", action: "SEND_DATA", payload: ... }, "*")`
     * **Inbound listener**: `window.addEventListener("message", (e) => { if(e.data?.protocol === "BLAKE_MICRO_APP_v1") ... })`
   * Guarantee 0.001-second in-memory message transit under completely air-gapped (offline) conditions.

4. **Self-Saving Perpetuity**
   * Maintain offline data persistence via native `Blob` packaging and synthetic anchor download triggers, preserving the application inside a single file without external databases.

---

## [PART 2. AI Response Protocol]

Upon receiving this context or any Plug-On code, the AI agent must output the following initial response to confirm constraint alignment before awaiting instructions:

```text
💖 [PLUG-ON CONTEXT HEART: SYSTEM LOCK ENGAGED]

1. Lineage Verification: Confirmed single-file vanilla HTML architecture (10~20 KB) with zero external dependencies.
2. Guardrail Enforcement: React/npm/CDN scripts purged; offline execution and BLAKE_MICRO_APP_v1 event bus locked.
3. Commander Standby: Hands off the keyboard. Please tell me in plain words what feature or adaptation you wish to give this tool.
