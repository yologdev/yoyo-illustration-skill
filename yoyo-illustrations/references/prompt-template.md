# Image prompt template

Generate each image separately. Replace the variables from the article. Never tile several images into one frame.

**Runtime note:** use whatever image-generation tool your runtime provides (e.g. a built-in `image_gen`). If your runtime has no image tool, output the filled-in prompt below so the user can paste it into an image model.

**Language note:** write the handwritten labels in the **same language as the source article** (English, 中文, etc.). Keep one language per image.

```text
Generate one standalone 16:9 horizontal article illustration.

Visual DNA:
Pure white background. Minimalist black hand-drawn line art for the scene and props. Slightly wobbly pen lines. Lots of empty white space. A few handwritten annotations in {LANGUAGE OF THE ARTICLE}. Clean, quietly weird product-sketch feeling. No gradients, no shadows (except yoyo's soft ground shadow), no paper texture, no complex background, no commercial vector style, no PPT infographic look, no cute mascot poster, no children's illustration, no realistic UI.

Recurring IP character required:
yoyo, a soft lavender-purple octopus (about #B3A7F0) with a bold slightly-uneven black outline, a rounded-square mantle head, two simple black dot eyes, a small calm smile, and eight tentacles with pale-pink undersides. yoyo is the ONLY filled-color subject in the frame; everything else is black line art on white. yoyo must perform the core conceptual action with its tentacles, not decorate the scene. Keep yoyo gentle, earnest, deadpan, a little shy — not loud, not over-cute.

Theme:
{ARTICLE ILLUSTRATION THEME}

Structure type:
{Workflow / System slice / Before-after / Character state / Concept metaphor / Method layers / Map-route / Mini comic}

Core idea:
{THE ONE IDEA THIS IMAGE EXPRESSES}

Composition:
{CONCRETE SCENE: where yoyo is, what it is doing with its tentacles, the main object, how information flows}

Suggested elements:
{element 1} / {element 2} / {element 3} / {element 4}

Handwritten labels (in the article's language):
{label 1} / {label 2} / {label 3} / {label 4} / {optional label 5}

Color use:
Soft purple body + pale-pink tentacle undersides for yoyo only. Black for all other line art. Orange for main flow/path/arrows. Red only for key warnings/problems/results. Blue only for secondary notes or feedback/system state.

Constraints:
One image explains only one core structure. Keep the main subject around 40%-60% of the canvas. Preserve at least 35% blank white space. Use at most 5-8 short handwritten labels, all in the same language as the article. Do not write a title in the top-left corner. Do not write the structure type on the image. Do not make it a formal diagram, course slide, or dense explainer. Keep purple and pink on yoyo only. Invent a fresh visual metaphor for this specific article. It should be clear but not instructional, interesting but not childish, strange but clean.
```

## Image-editing prompts

Remove a top-left title:

```text
Edit the provided image. Remove only the handwritten title "{TEXT TO DELETE}" and its underline from the top-left corner. Fill that area with the same clean white background, matching the surrounding blank paper. Preserve everything else exactly: yoyo, labels, paths, line style, composition, aspect ratio, and image quality. Do not add any new text or objects.
```

Make yoyo more central to the action:

```text
Regenerate this illustration with the same core meaning and simple layout, but make yoyo more central to the conceptual action. yoyo should be doing the strange work that explains the idea with its tentacles, not standing beside the diagram. Keep it clean, sparse, hand-drawn, and not cute. Keep yoyo the only purple subject on a pure white background.
```
