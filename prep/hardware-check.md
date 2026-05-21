# Hardware Check

Can your laptop run a local LLM during the workshop? Almost certainly yes — but check these three things first.

## Minimum specs by model

| Your machine has... | You can comfortably run | Notes |
|---|---|---|
| 8 GB RAM, 5 GB free disk | **Llama 3.2 3B** (Q4_K_M, ~2 GB) | Slower but works. Expect a few seconds before responses start. |
| 16 GB RAM, 10 GB free disk | **Qwen 2.5 7B Instruct** (Q4_K_M, ~4.5 GB) — recommended | Smooth experience. This is the workshop default. |
| 16+ GB RAM + dedicated GPU or Apple Silicon M-series | **Gemma 2 9B** or larger 13B-class models | Use this if you want stronger reasoning. |

## How to check your RAM

**macOS:**
- Click the Apple menu → **About This Mac**.
- Look for **Memory** (e.g., "16 GB").

**Windows:**
- Press **Ctrl + Shift + Esc** to open Task Manager.
- Click **Performance** → **Memory**.
- Look at the top-right — total installed RAM.

## How to check free disk space

**macOS:**
- Apple menu → **About This Mac** → **More Info** → **Storage**.
- You need at least **5 GB free** for Llama 3.2 3B, or **10 GB free** for Qwen 7B / Gemma 9B.

**Windows:**
- Open **File Explorer** → **This PC**.
- Right-click your main drive (usually `C:`) → **Properties**.
- Check the **Free space** indicator.

## How to check your OS version

**macOS:** Apple menu → **About This Mac** → top of the window shows your version.
- Required: **Apple Silicon** (M1 / M2 / M3 / M4). LM Studio does **not** support Intel Macs.
- Minimum OS: **macOS 13 Ventura** (older versions may work but performance degrades).

**Windows:** Press **Win + R**, type `winver`, press Enter.
- Minimum: **Windows 10 (64-bit)**. Windows 11 recommended.

## If you're unsure

Pick **Llama 3.2 3B (Q4_K_M)**. It works on any Apple Silicon Mac or Windows laptop with 8 GB+ RAM, and you can always download a larger model after the workshop once you know what you're doing.

## If your laptop genuinely can't run anything

Pair up with someone at the workshop. The hands-on segment is more useful when discussed than when each person works in isolation.
