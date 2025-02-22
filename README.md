<div align="center">
    <h1 align="center">Self-host Moshi with BentoML</h1>
</div>

This is a BentoML example project, showing you how to serve and deploy [Moshi](https://github.com/kyutai-labs/moshi) with BentoML.

See [here](https://github.com/bentoml/BentoML?tab=readme-ov-file#%EF%B8%8F-what-you-can-build-with-bentoml) for a full list of BentoML example projects.

## Prerequisites

If you want to test the Service locally, we recommend you use a Nvidia GPU with at least 24Gb VRAM.

## Instructions

```bash
# installing uv with curl -LsSf https://astral.sh/uv/install.sh | sh
git clone https://github.com/bentoml/BentoMoshi.git && cd BentoMoshi

# option 1: bentoml serve [RECOMMENDED]
uvx --with-editable . bentoml serve . --debug

# option 2: script
uvx --from . server
```

To use the client, specify the `URL` on BentoCloud:

```bash
# option 1: uvx [RECOMMENDED]
URL=<bentocloud-endpoint> uv run --with-editable . bentomoshi/client.py

# option 2: using python
URL=<bentocloud-endpoint> python bentomoshi/client.py
```

> [!NOTE]
>
> If you are hosting this on your own server, make sure to include the port the model is served into the URL, for example:
>
> ```bash
> URL=http://localhost:3000 uvx --from . client
> ```
