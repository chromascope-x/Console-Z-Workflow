### Console Z - Z-Image Workflow v2.0
> *The Ultimate Z-Image Upscale & Restoration Workflow for ComfyUI*

![Console Z Cover](assets/cover-image.png)

## Overview
Console Z is a high-performance, streamlined ComfyUI workflow designed for quick image upscaling and restoration. It combines the speed of **Z-Image Turbo** with the state-of-the-art **SeedVR2** and **Ultimate SD Upscale** technologies.

![Console Z UI Overview](assets/console-z-workflow-v2-0-demo_ui.png)

## Key Features

- **Turbocharged Core**: Integrated with `Patch Sage Attention KJ` and `Torch Compile Settings` (FP16 Accumulation) to maximize inference speed on supported hardware.

- **LoRA Ready**: Seamlessly integrated LoRA support. Simply connect your preferred LoRA models to the dedicated loader stack to instantly enhance style or character consistency without disrupting the core workflow.

- **Dual Upscale Methods**:
  - **Method 1 (Latent)**: Fast latent upscaling for rapid prototyping.
  - **Method 2 (Pixel)**: High-quality pixel upscaling with automatic resolution calculation.

- **SeedVR2 Integration**: Implements `SeedVR2 Video Upscaler` (v2.5) for advanced detail restoration and artifact reduction.

- **Smart Control**:  
  - **Auto-Resolution**: Automatically detects image orientation and calculates optimal upscale factors.
  - **Modular Bypassing**: Easily toggle Ultimate SD Upscale, SeedVR2, or Sharpening modules using `Fast Groups Bypasser`.

- **Cinematic Finish**: Includes `LTXV Film Grain` and `Lucy Sharpen` for that final professional polish.

## Requirements
Ensure you have the following Custom Node packs installed via ComfyUI Manager:

- ComfyUI-SeedVR2_VideoUpscaler
- ComfyUI-KJNodes
- rgthree-comfy
- ComfyUI_UltimateSDUpscale
- ComfyUI-LTXVideo
- Was Node Suite
- ComfyUI_JPS-Nodes
- ComfyUI-Easy-Use
- ComfyUI_FearnworksNodes

## Usage Guide

### Load Models & LoRAs
Select your Checkpoint in the **Load Models** group. Connect your LoRAs in the **LoRA Stack** group to apply custom styles.

### Select Input Mode
- **Text-to-Image**: Enter your prompt and leave the Load Image node bypassed or unused.
- **Image-to-Image**: Load your image in the **Load Image (i2i)** group and ensure the switch is set to use the image input.

### Configure Sampler Upscaling
- **Use Sampler 2 Upscale?**: Choose whether to enable the second pass upscaling.
- **Sampler 2 Upscale Method**: Selects between 1: Latent Upscale (Faster) and 2: Pixel Upscale (Quality).

### Choose Additional Upscaling (as needed)
- **Ultimate SD Upscale**: Enable for adding texture to flat areas.
- **SeedVR2**: Enable for fixing artifacts and restoration.
- **Control**: Use the Fast Bypasser buttons to toggle these modules on/off instantly.
- **⚠️ Important**: It is recommended to choose **EITHER** Ultimate SD Upscale **OR** SeedVR2, not both simultaneously. If you must chain them, significantly reduce the upscale factor (e.g., 1.2x or 1.5x) to prevent OOM errors and excessive image dimensions.

### Adjust Final Look
Tweak intensity in the **LTXV Film Grain** node or adjust iterations in the **Lucy Sharpen** node for your desired output. Use the Fast Bypasser buttons to toggle these modules on/off instantly.

## Notes
- **VRAM Usage**: SeedVR2 can be VRAM intensive. If you encounter OOM errors, enable `Tiled VAE` in the SeedVR2 settings.
