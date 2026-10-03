# C⁴ Project Page

Static project page for **Commit Locally, Exit Globally: Coordinating Adaptive Sampling and Early Exit in Diffusion Language Models**.

**Live site:** https://c4-dllm.github.io/

**Repository:** https://github.com/c4-dllm/c4-dllm.github.io

The page is plain HTML/CSS/JavaScript and has no build step. Its structure follows the supplied `project-page.zip` reference while the visual story and interactive decoder walkthrough are tailored to C⁴. Paper figures and the PDF are copied from the local manuscript source.

## Preview

```bash
cd /ssd2/cactus8603/c4-project-page
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Layout

```text
index.html                 # complete single-page site
static/images/overview.svg # C⁴ method overview
static/images/*.png        # paper figures
static/animations/*.gif    # animated decoding comparison
static/animations/*.mp4    # lighter, controllable playback of the original GIF
static/pdf/paper.pdf       # paper button target
.nojekyll                  # serve unchanged on GitHub Pages
```

The decoder walkthrough uses illustrative values, not live model inference. The HumanEval video preserves the supplied GIF; its playback clock is separate from the model-runtime counters inside each panel. Both animations require explicit playback. Paper figures support keyboard-accessible expansion and zoom; the mobile section menu and citation-copy fallback work without a framework.

The results story includes a 24-setting reliability matrix, component-ablation cards, a co-design comparison against composing CVEE with WINO, and a simplified three-regime step decomposition. Values are transcribed from the local manuscript; the full paper tables remain the source of record.

## Responsive behavior

- Compact section menu at widths up to 840 px; full navigation above that breakpoint.
- Two-column mobile metrics, single-column content cards, and a contained horizontal results table.
- Safe-area spacing for notched phones plus a compact landscape layout for short screens.
- Touch targets are at least 44 px where controls are custom-rendered.

Responsive QA covers 320–1920 px viewports, common phone and tablet emulations, portrait and landscape orientations, and Chromium, Firefox, and WebKit browser engines.

### Final verification — October 3, 2026

- All 24 speedup/accuracy-delta cells match the local manuscript source. All 10 local asset/link targets resolve; there are no duplicate IDs or unresolved in-page/ARIA references.
- Chromium, Firefox, and Linux WebKit passed the 11-size viewport check, mobile navigation, keyboard walkthrough, figure dialog/zoom/focus restoration, and citation-copy fallback. Chromium also passed actual clipboard copying. No JavaScript exceptions or HTTP error responses occurred in these checks.
- MP4 playback advanced successfully in Chromium and Firefox. Linux WebKit did not decode either the original MP4 or a temporary lower-profile compatibility encode, so Safari/iOS video playback remains unverified. The original GIF link remains available as a fallback. Browser-engine and viewport tests do not substitute for testing a physical iPhone/iPad.

## Before publishing

- The bundled PDF is the September 18, 2026 anonymous ICLR review draft. Replace it with the intended public author-version PDF before a non-anonymous release; do not change manuscript authorship in the page build.
- The public arXiv v2 abstract (August 13, 2026) currently says 2.6–8.6×, while the bundled revised manuscript reports 2.6–18.6× (18.66× in its table). Page results follow the bundled PDF. Keep the version note until the public record and intended manuscript are synchronized.
- Verify whether author names and public arXiv/GitHub links should remain visible during review.
- If the site must be anonymous, remove the author/affiliation row and replace public links with anonymized URLs.
- The page can be deployed directly with GitHub Pages or an anonymous repository mirror.
