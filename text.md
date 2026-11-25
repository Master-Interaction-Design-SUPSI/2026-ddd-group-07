---
title: How far can you drive on the electricity of 1,000 AI prompts?
authors: Jennifer Ji, Victoria Mezo
---

**Generative AI** (text) feels weightless, yet every answer is computed on physical chips (**GPUs**) that draw electricity from the grid. Our sub-topic is the electricity of **AI inference**: the energy needed to use a model once it has been trained. It connects to the Materialities of AI [[Crawford, 2021. Atlas of AI|https://yalebooks.yale.edu/9780300264630/atlas-of-ai|type=bibliography]] through its most direct material input, **electricity**, and the hardware and data centres behind it.

*How far could an electric [[car]] drive on the GPU electricity that different AI models need to answer the same 1,000 prompts?*

We used the [Hugging Face AI Energy Score](https://huggingface.co/spaces/AIEnergyScore/Leaderboard): 62 open text-generation models (reasoning off), each tested with the same 1,000 prompts on the same hardware and measured in kWh of GPU electricity. We converted each value into kilometres using the consumption of an electric car, 20.7 kWh per 100 km [[Weiss et al., 2024. Energy Consumption of Electric Vehicles in Europe|https://doi.org/10.3390/su16177529|type=bibliography]], and placed the distances on the real road from Mendrisio to Lugano along the lake (18.4 km, route computed with OSRM on [OpenStreetMap](https://www.openstreetmap.org) data).

**Findings.** For the same task, the most demanding model (Command R+) used 2,609 times more electricity than the lightest (distilgpt2): 16.55 km, stopping 1.85 km before Lugano, versus 6.3 m, just over one car length. 51 of the 62 models never leave the first 400 m. **Model size** explains much of this gap: the AI Energy Score groups models into class A (up to 20 billion parameters), B (up to 66 billion) and C (more than 66 billion) [[Hugging Face, 2025. AI Energy Score documentation|https://huggingface.github.io/AIEnergyScore/|type=bibliography]], and almost all models that drive far are class C. Size is not the only factor: some large models use much less. The same request can cost very different amounts of electricity depending on which model answers it.

**Limits.** These are calculated equivalents, not real trips, and only GPU electricity is counted, not cooling or the rest of the data centre, so real consumption is higher. All values, the ranking of the 62 models and our method are in our [AI Energy Score Dataset - EV](https://docs.google.com/spreadsheets/d/1gV1MIYA_KC-2h9cvhMLrzJ1bjpzuPDZQu6nHo7eDj9E/edit?gid=920061101#gid=920061101).
