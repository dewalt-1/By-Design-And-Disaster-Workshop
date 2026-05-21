# LM Studio Setup Guide

This guide walks you through installing **LM Studio**, downloading a language model, configuring it for your hardware, and confirming it runs entirely on your machine — no internet required after setup.

Total time: **15–25 minutes**, depending on download speeds. **Please do this before the workshop**, otherwise the venue Wi-Fi may slow everyone down.

If you get stuck, see [Common problems](#common-problems) at the bottom, or message Ben.

---

## What you'll do

1. Install LM Studio (a free desktop app for running LLMs locally)
2. Set the folder where your models will live
3. Get a model — either from Ben's USB stick at the workshop, or by downloading one yourself
4. Configure LM Studio for your specific hardware (Mac and Windows differ)
5. Send a first message and verify it works **offline**

---

## Step 1 — Install LM Studio

Download the installer for your OS from:

**[https://lmstudio.ai](https://lmstudio.ai)**

LM Studio is free, runs on macOS (Apple Silicon and Intel), Windows, and Linux, and does not require an account.

The installer is about 500 MB. Open it and follow the standard install prompts.

---

## Step 2 — Set your models directory

Models are big files (2–10 GB each). You want them in a folder you can find, not buried in the app bundle.

In LM Studio:

1. Click the **gear icon** (Settings) in the lower-left of the window.
2. Look for **Models Directory** (sometimes called "Local models folder").
3. Set the path to a folder you'll remember. Suggested:
   - **macOS:** `~/Desktop/Local_Research_Library`
   - **Windows:** `C:\Users\YOUR_NAME\Desktop\Local_Research_Library`

Create that folder first if it doesn't exist. LM Studio will now load and save all models from there.

---

## Step 3 — Get a model

You have two paths:

### Path A — USB stick at the workshop (primary)

Ben will bring USB sticks with pre-downloaded `.gguf` model files. At the start of the workshop:

1. Copy the contents of the USB into your `Local_Research_Library` folder.
2. In LM Studio, the models will appear under **"My Models"** automatically (you may need to click **Re-scan** or restart the app).

This is the recommended path — no dependency on venue Wi-Fi.

### Path B — Download in-app (fallback / before the workshop)

If you want to be set up before you arrive, or you can't make it to Ben for the USB:

1. In LM Studio, go to the **Discover** tab (magnifying-glass icon).
2. Search for the model name from the table below.
3. Pick the **Q4_K_M** quantization (it's the recommended size/quality balance).
4. Click **Download**. The file will save into your models directory.

---

## Recommended models

Pick **one text model** based on your hardware. If you'll work with photos, also pick **one vision model**.

| Model | Size | Quant | Why pick this | Search term in LM Studio |
|---|---|---|---|---|
| **Qwen 2.5 7B Instruct** ⭐ | ~4.5 GB | Q4_K_M | **Recommended.** Strong multilingual support — directly relevant to the workshop's Global South / multilingual discussion. Excellent reasoning for its size. | `qwen2.5-7b-instruct` |
| Llama 3.2 3B Instruct | ~2 GB | Q4_K_M | Lighter fallback for older or low-RAM laptops (8 GB RAM). Faster, but less capable for nuanced text. | `llama-3.2-3b-instruct` |
| Gemma 2 9B Instruct | ~5.5 GB | Q4_K_M | Stronger reasoning if you have 16 GB+ RAM and want a more capable model. Slower than Qwen 7B. | `gemma-2-9b-it` |
| Moondream2 | ~2 GB | Q4_K_M | **Vision model — optional, lightweight.** Required only if you'll use [`../prompts/photo-first-read.md`](../prompts/photo-first-read.md). Designed for "look at image, answer briefly" — a good fit for the short labelled output the photo prompt asks for. Runs comfortably on 8 GB-RAM laptops. | `moondream2` |
| Qwen2-VL 7B Instruct | ~5 GB | Q4_K_M | **Vision model — heavier alternative.** Stronger than Moondream on dense scenes, multilingual signage, and longer descriptions. Pick this only if Moondream feels too terse and you have the RAM. | `qwen2-vl-7b-instruct` |

If unsure, **download Qwen 2.5 7B Instruct (Q4_K_M)**. Add **Moondream2** alongside it only if you plan to work with site photos during the hands-on segment — LM Studio shows an image-attach button in the chat composer when a vision-capable model is loaded; if you don't see it, double-check that the loaded model is the vision build, not a text-only one.

> **What is a quant?** Quantization compresses the model's numerical weights to make it smaller and faster, with a small accuracy cost. `Q4_K_M` is "4-bit, K-quant, medium" — the most common sweet spot. Higher (Q5, Q6, Q8) means bigger and more accurate; lower (Q3, Q2) means smaller and rougher.

---

## Step 4 — Configure for your hardware

Load the model: click on it under **My Models** and hit **Load**. Before the first load, you'll see options. Settings differ by OS.

### macOS (Apple Silicon: M1 / M2 / M3 / M4)

- In the load dialog, ensure the **MLX** backend is selected. If MLX isn't available for your model, **Metal** is the fallback — also fine.
- Unified Memory means GPU offload is automatic. **Leave the defaults** for layers / offload.
- Set **Context Length** to **4096** initially. (You can raise it later if needed.)

### macOS (Intel)

- Older Intel Macs will run, but slowly. Use **Llama 3.2 3B** and expect tokens to trickle.
- Backend: **Metal** (or CPU if Metal isn't offered).

### Windows (NVIDIA or AMD GPU)

- In the load dialog, find the **GPU Offload** slider.
- **Start at 10 layers.** Click Load. Watch the **RAM** and **VRAM** indicators at the top of LM Studio.
- If everything loads fine, **unload the model**, increase the slider by 10 layers, and reload.
- Repeat until **RAM/VRAM usage reaches ~80%**. Stop there. Going higher risks crashes.
- Set **Context Length** to **4096**.

### Windows (integrated graphics only / no dedicated GPU)

- Set **GPU Offload to 0** — the CPU will handle everything.
- Use **Llama 3.2 3B**, not the larger models.
- Set **Context Length** to **2048** to save RAM.

### Troubleshooting lag during inference

If the model loads but responses are slow or your machine gets hot:

- Drop **Context Length** to **2048**.
- Windows: lower the GPU Offload by 5–10 layers.
- Close other RAM-heavy apps (browsers with many tabs are the biggest culprit).

---

## Step 5 — Verify it works (first inference)

Now we'll confirm two things: that it generates text, **and** that it works without an internet connection.

1. Open the **Chat** tab in LM Studio.
2. Confirm your model is loaded (you'll see its name at the top).
3. Clear any default **system prompt** in the right-hand panel.
4. Paste this system prompt (from [`prompts/reflective-assistant.md`](../prompts/reflective-assistant.md)):

   > You are a critical design research companion. Do not generate creative ideas. Do not paraphrase or summarize what I share. Ask me questions that help me clarify my tacit knowledge.

5. Send a first message:

   > I'm a design researcher working on urban mobility in a postcolonial context. I keep wanting to write that infrastructure "excludes" certain users, but I'm not sure that's the right word. Help me get clearer.

   You should see a response in a few seconds.

6. **The offline test:** disconnect your Wi-Fi (turn it off in your OS). Send another message:

   > That's helpful. What would you ask me next?

   If you get a response, the model is genuinely running on your hardware. Welcome to local LLMs.

---

## Common problems

**"Model won't load" / "Out of memory"**
- You're out of RAM. Try a smaller model (Llama 3.2 3B), drop Context Length to 2048, and close other apps.
- Windows: lower the GPU Offload slider.

**"Output is very slow" (less than ~5 words per second)**
- Drop Context Length to 2048.
- Windows: lower GPU Offload by 5–10 layers — paradoxically, offloading *less* sometimes helps when VRAM is the bottleneck.
- Close browser tabs and other apps.

**"I copied the .gguf from USB but I don't see it in LM Studio"**
- Confirm the file is directly inside the models folder you set in Step 2, or in a subfolder (LM Studio scans subdirectories).
- In Settings → Models Directory, click **Re-scan** or restart LM Studio.

**"LM Studio says the model needs more RAM than I have"**
- That's an honest message. Pick a smaller model (Llama 3.2 3B) or a lower quant (Q3_K_M instead of Q4_K_M).

**"I see the model load but Chat is greyed out"**
- The model may still be loading into RAM (first load is slow — 30–60 seconds is normal). Wait a minute.

---

## After the workshop

- Try the prompts in [`prompts/`](../prompts/) with your own field notes or drafts.
- Adopt the folder pattern in [`templates/`](../templates/) for transparent documentation of your LLM use — this matters for citation and academic integrity (see [`references/reading-list.md`](../references/reading-list.md) for institutional guidelines).
- Experiment with different models. The LM Studio Discover tab has thousands. Look for "Instruct" models in the 3B–13B range to start.
