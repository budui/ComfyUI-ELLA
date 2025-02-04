# ComfyUI-ELLA

<div align="center">
<img src="./assets/ELLA-Diffusion.jpg" width="30%" > <br/>
<a href='https://ella-diffusion.github.io/'><img src='https://img.shields.io/badge/Project-Page-green'></a>
<a href='https://arxiv.org/abs/2403.05135'><img src='https://img.shields.io/badge/arXiv-2403.05135-b31b1b.svg'></a>
</div>


[ComfyUI](https://github.com/comfyanonymous/ComfyUI)  implementation for [ELLA](https://github.com/TencentQQGYLab/ELLA).

## :star2: Changelog

- **[2024.4.19]** Documenting nodes
- **[2024.4.19]** Initial repo

## :books: Example workflows

The [examples directory](./examples/) has workflow examples. You can directly load these images as workflow into ComfyUI for use.

![workflow_example](./examples/workflow_example.png)

:tada: It works with controlnet! And [EMMA](https://github.com/TencentQQGYLab/ELLA/issues/15) is working in progress.

![controlnet_workflow_example](./examples/controlnet_workflow_example.png)

## :green_book: Install

Download or git clone this repository inside ComfyUI/custom_nodes/ directory. `ComfyUI-ELLA` requires the latest version of ComfyUI. If something doesn't work be sure to upgrade.

```bash
cd ComfyUI/custom_nodes
git clone https://github.com/TencentQQGYLab/ComfyUI-ELLA
```

Next install dependencies.

```bash
cd ComfyUI-ELLA
pip install -r requirements.txt
```

## :orange_book: Models

These models must be placed in the corresponding directories under models.

Remember you can also use any custom location setting an `ella` & `ella_encoder` entry in the `extra_model_paths.yaml` file.

- `ComfyUI/models/ella`, create it if not present.
  - Place [ELLA Models](https://huggingface.co/QQGYLab/ELLA) here
- `ComfyUI/models/ella_encoder`, create it if not present.
  - Place [t5 model](https://huggingface.co/google/flan-t5-xl) here, it should be a folder of transfomers structure with config.json

In summary, you should have the following model directory structure:

```bash
ComfyUI/models/ella/
└── ella-sd1.5-tsc-t5xl.safetensors

# It may be a little different because I only include the text_encoder part here
ComfyUI/models/ella_encoder/
└── models--google--flan-t5-xl
    ├── config.json
    ├── model.safetensors
    ├── special_tokens_map.json
    ├── spiece.model
    ├── tokenizer_config.json
    └── tokenizer.json
```


## :book: Nodes reference

[Nodes reference](./NODES.md)

## :memo: TODO

- [ ] Support prompt weighting

## :yum: Thanks

- ComfyUI: https://github.com/comfyanonymous/ComfyUI
- Diffusers (borrowed timestep modules): https://github.com/huggingface/diffusers

## :wink: Citation

```
@misc{hu2024ella,
      title={ELLA: Equip Diffusion Models with LLM for Enhanced Semantic Alignment}, 
      author={Xiwei Hu and Rui Wang and Yixiao Fang and Bin Fu and Pei Cheng and Gang Yu},
      year={2024},
      eprint={2403.05135},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```
