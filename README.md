# FLUX Modular WF

The Flux Modular WF is a ComfyUI workflow that works like a "Swiss army knife" and is based on FLUX Dev.1 model by Black Forest Labs.
![Flux Modular WF](https://www.tenofas.ai/wp-content/uploads/2025/07/workflow.png)
The workflow comes in two different edition:

1) the standard model edition that uses the BFL original model files (you can set the weight_dtype in the “Load Diffusion Model” node to fp8 which will lower the memory usage if you have less than 24Gb Vram and get Out Of Memory errors);
2) the GGUF model edition that uses the GGUF quantized files and allows you to choose the best quantization for your GPU's needs.

Press "1", "2" and "3" to quickly navigate to the main areas of the workflow.

You will need around 14 custom nodes (but probably a few of them are already installed in your ComfyUI). I tried to keep the number of custom nodes to the bare minimum, but the ComfyUI core nodes are not enough to create workflow of this complexity. I am also trying to keep only Custom Nodes that are regularly updated.

Once you installed the missing (if any) custom nodes, you will need to config the workflow as follow:

1) load an image (like the COmfyUI's standard example image ) in all three the "Load Image" nodes at the top of the frontend of the wf (Primary image, second and third image).
2) update all the "Load diffusion model", "DualCLIP LOader", "Load VAE", "Load Style Model", "Load CLIP Vision" or "Load Upscale model". Please press "3" and read carefully the red "READ CAREFULLY!" note for 1st time use in the workflow!

In the INSTRUCTIONS note you will find all the links to the model and files you need if you don't have them already.

This workflow let you use Flux model in any way it is possible:
1) Standard txt2img or img2img generation;
2) Inpaint/Outpaint (with Flux Fill)
3) Standard Kontext workflow (with up to 3 different images)
4) Multi-image Kontext workflow (from a single loaded image you will get 4 images consistent with the loaded one). Do not use the "Kontext switch" to select the number of images, that is used only for the Standard Kontext worfklow;
5) Depth or Canny;
6) Flux Redux (with up to 3 different images) - Redux works with the "Flux basic wf".

You can use different modules in the workflow:
1) Img2img module, that will allow you to generate from an image instead that from a textual prompt;
2) HiRes Fix module;
3) FaceDetailer module for improving the quality of image with faces;
4) Upscale module using the Ultimate SD Upscaler (you can select your preferred upscaler model) - this module allows you to enhance the skin detail for portrait image, just turn On the Skin enhancer in the Upscale settings;
5) Overlay settings module: will write on the image output the main settings you used to generate that image, very useful for generation tests;
6) Saveimage with metadata module, that will save the final image including all the metadata in the png file, very useful if you plan to upload the image in sites like CivitAI.

You can now also save each module's output image, for testing purposes, just enable what you want to save in the "Save WF Images".

Before starting the image generation, please remember to set the Image Comparer choosing what will be the image A and the image B!

Once you have choosen the workflow settings (image size, steps, Flux guidance, sampler/scheduler, random or fixed seed, denoise, detail daemon, LoRAs and batch size) you can press "Run" and start generating you artwork!

Post Production group is always enabled, if you do not want any post-production to be applied, just leave the default values.
