# P-H3-Image Workflows

**English** | [日本語](README.ja.md)

Community-created prompts and (planned) ComfyUI workflows for [P-H3-Image](https://huggingface.co/PrunaAI/P-H3-Image), focused on character consistency using reference images **without training a character LoRA**.

The initial experiments use **one three-view character reference sheet** (front, side, and back views) as `Picture 1` to generate new scenes, outfits, camera angles, and poses. The goal is to explore how much of the original character's facial features, hairstyle, and illustration style can be retained across different compositions.

> **Status:** This repository currently contains prompt examples only. ComfyUI workflows may be added later. This is an independent experiment, not an official PrunaAI repository.

## Contents

| Resource | Description | Status |
| --- | --- | --- |
| [Three-view character prompts](prompts/three-view-character-prompts.md) | Three English prompts for generating a new scene from a character reference sheet | Available |
| ComfyUI workflows | Reusable workflow JSON files and configuration notes | Planned |

### Prompt scenarios

1. **School uniform / classroom:** A student writing at a desk, viewed from a three-quarter side angle. A hand-drawn 2D TV anime look is requested.
2. **Sweater / looking back:** A character in a knit sweater, shown from behind while looking over her shoulder, in a cowboy shot. Focuses on more detailed fabric and anime illustration rendering.
3. **Bikini / beach:** A full-body seated beach scene with an upward gaze. This is a **proposed revised prompt**, not yet verified with a final generation in this experiment.

See the [full, copyable prompts](prompts/three-view-character-prompts.md) for the exact wording.

## How to use

1. Prepare a three-view character sheet. The current examples use a single image containing front, side, and rear views of the character's head.
2. Open a P-H3-Image generation or editing workflow that accepts image references.
3. Load the character sheet as **Picture 1**.
4. Copy one prompt from [the prompt collection](prompts/three-view-character-prompts.md), adjust the scene or outfit if desired, and generate.
5. Evaluate character identity, pose, composition, and art style separately; compare results across seeds when assessing consistency.

**Note:** These prompts deliberately ask P-H3-Image to treat `Picture 1` as a **character design and style reference**, rather than preserving the original three-view layout. Results depend on the model, reference image, seed, and generation settings. A three-view sheet is not guaranteed to behave like a trained LoRA.

## Findings so far

- A single three-view sheet can be used to create a **new, single-character composition**, rather than merely extending the original turnaround sheet.
- The tested classroom and sweater examples retained recognizable facial and hairstyle features, even when outfit and scene changed.
- **Art style is not fully locked by the reference.** Classroom backgrounds tended toward realistic lighting and materials despite 2D anime style instructions.
- Aggressive requests for flat colors and simplified backgrounds produced a more stylized image but also simplified the character's face and clothing.
- Describing **fine linework, layered shading, knit texture, and soft highlights** improved sweater detail in the observed sample.

These are qualitative observations from a small number of manual tests, **not controlled benchmarks or guarantees**. The beach prompt's revised output has not yet been evaluated.

## Future additions

- ComfyUI workflow JSON files
- Reference-image and prompt variations
- Reproducible settings and side-by-side examples, where available

## References

- [P-H3-Image — official model page](https://huggingface.co/PrunaAI/P-H3-Image)
- [P-H3-Image-Comfy — official ComfyUI model files and examples](https://huggingface.co/PrunaAI/P-H3-Image-Comfy)
- [ComfyUI](https://github.com/Comfy-Org/ComfyUI)

This repository is an independent community project and is not affiliated with or endorsed by PrunaAI.
