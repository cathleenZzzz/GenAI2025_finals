# GenAI2025 Finals Documentation

(Final Project for Golan Levin's Generative AI Class)

Below is the tinkering I did for the final project for Golan Levin's Generative AI class.

---

## 1. Trained a GAN on Images of Micro Fragments Found in a Carpet

The GAN (trained from a dataset of images contained [here](https://cathleenzzzz.github.io/stuckincarpet/)) will probably end up being the most fun for me and the most interesting thing for others.

I used the Colab notebook by Derrick Schultz ([link](https://github.com/brownvc/R3GAN/)).  
There is really minimal technical effort by me, just some debugging and GPT generating the script for the latent loops.

Here is the folder with the debugged Python scripts: [Google Drive folder](https://drive.google.com/drive/folders/1F69HsQV__R6fduAYwGv-eEUZp5KsDkvV?usp=sharing).

From the trained models, I generated some looping videos that are sorted by t-SNE and displayed [here](https://cathleenzzzz.github.io/stuckincarpet_moving/).

Here are some example vids:

- [Loop 1](https://github.com/cathleenZzzz/GenAI2025_finals/raw/main/LoopingVideos/loop3.mp4)
- [Loop 2](https://github.com/cathleenZzzz/GenAI2025_finals/raw/main/LoopingVideos/loop9.mp4)
- [Loop 3](https://github.com/cathleenZzzz/GenAI2025_finals/raw/main/LoopingVideos/loop10.mp4)
- [Loop 4](https://github.com/cathleenZzzz/GenAI2025_finals/raw/main/LoopingVideos/loop11.mp4)
- [Loop 5](https://github.com/cathleenZzzz/GenAI2025_finals/raw/main/LoopingVideos/loop12.mp4)
- [Loop 6](https://github.com/cathleenZzzz/GenAI2025_finals/raw/main/LoopingVideos/loop13.mp4)

---

## 2. ControlNet Tinkering in ComfyUI

While the GAN was training, I had this really bad idea (which, honestly, wasn't appropriate for this class) — finding characters in branch shapes.  
But being completely inexperienced in anything related to that, I lost patience with figuring out the logistics of edge map → skeleton extraction.

In fairness to the capacity of AI, if I had the time (and really just patience) to label the images with polygons indicating where the trees are and train a model that way, it might have worked.

The edge graphs and skeletons are kind of pretty, but in the end, I was mostly just doing random image processing in Python.

So at this point, I decided to use these sort-of-branch skeletons to make depth maps and normal maps.  
I passed these as ControlNet conditions into ComfyUI to generate skin-like images textured according to the maps. I also tried different base models for the generation.

To be honest, the results weren't that interesting to me — it didn't really scream "skin." Maybe the prompting was lacking too.

---

### Images are displayed in this order:

`Original Image` → `Edge Map` → `Skeleton` → `Normal + Depth Maps` → `"Skin" Generation`

**Original Image:**

![Original Image](https://raw.githubusercontent.com/cathleenZzzz/GenAI2025_finals/main/TreeSkinImages/original.png)

**Edge Detection:**

![Edge Detection](https://raw.githubusercontent.com/cathleenZzzz/GenAI2025_finals/main/TreeSkinImages/edge.png)

**Skeleton Extraction:**

![Skeleton](https://raw.githubusercontent.com/cathleenZzzz/GenAI2025_finals/main/TreeSkinImages/skeleton.png)

**Depth Map:**

![Depth Map](https://raw.githubusercontent.com/cathleenZzzz/GenAI2025_finals/main/TreeSkinImages/depth.png)

**Normal Map:**

![Normal Map](https://raw.githubusercontent.com/cathleenZzzz/GenAI2025_finals/main/TreeSkinImages/normal.png)

**"Skin" Generation Result:**

![Skin Generation](https://raw.githubusercontent.com/cathleenZzzz/GenAI2025_finals/main/TreeSkinImages/generated.jpg)

Most of the skeletons look the same, and generation took a long time, so I didn't produce very many outputs.  
You can expect them to look relatively similar. There was a lot of vibe coding — and honestly, I'm not sure if the result was worth it.
