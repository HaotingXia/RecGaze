# RecGaze 🧠
Learning Reciprocity Relationship for Efficient Gaze Following via Integrative Scenario Modeling

## 🔍 Overview

Gaze following (GF) aims to locate the gaze target of a person in a scene, which is essential for human–computer interaction, attention analysis, and assisted driving. However, existing methods struggle with face occlusion, complex relationships, and facial shadows. RecGaze addresses these challenges by introducing **reciprocity relationships** into GF via large language models (LLMs). It leverages two key insights: (1) multigranularity features (scene, head, eye) provide complementary gaze cues, and (2) individuals in the same scene tend to share similar gaze targets. The framework consists of three core modules: **Reciprocity Semantic Extraction (RSE)**, **Reciprocity Relationship Reasoning (RRR)**, and **Reciprocal Gaze Mining (RGM)**. Extensive experiments on GazeFollow and VideoAttentionTarget demonstrate that RecGaze achieves state-of-the-art accuracy with high computational efficiency.

## 📌 Abstract

Robustly estimating gaze targets under occlusion, complex relationships, and facial shadows remains challenging. Previous methods often rely on explicit visual matching and single-level features, which fail when visual evidence is incomplete. We observe that gaze following is governed by multi-level reciprocal relationships, where different granularities (scene, head, eye) can compensate for each other, and scene-aware gaze similarity among individuals provides additional cues. Motivated by this, we propose **RecGaze**, a novel gaze following framework that integrates reciprocity relationship reasoning via LLMs. Specifically, we design a **Reciprocity Semantic Extraction (RSE)** module to capture fine-grained visual cues, a **Reciprocity Relationship Reasoning (RRR)** module to generate hierarchical textual descriptions using LLMs, and a **Reciprocal Gaze Mining (RGM)** module to enable cross-modal interaction for accurate gaze target localization. RecGaze is evaluated on GazeFollow and VideoAttentionTarget, achieving superior performance over state-of-the-art methods while maintaining favorable computational efficiency.

## 🚀 Main Contributions

1. **Reciprocity Relationship Learning for Gaze Following**  
   We introduce discriminative reciprocity relationships into GF for the first time, revealing mutual gaze relationships by exploiting different feature associations of the same individual and similarities between different individuals. The model adaptively focuses on key gaze-related areas at multiple granularities across various scenarios.

2. **RSE and RRR for Cross-Modal Alignment**  
   The **RSE** module extracts segmented visual features using DINOv2 to capture fine-grained cues related to potential gaze targets. The **RRR** module leverages BLIP2 to generate hierarchical text descriptions at scene, head, and eye levels, building robust connections between visual features and semantic information.

3. **RGM for Precise Gaze Restoration**  
   A novel architecture is proposed where visual features and scene-aware semantic descriptions are modeled to estimate line-of-sight targets. The **RGM** module facilitates interaction between visual tokens and reciprocity tokens, enabling precise restoration of the gaze target by exploiting both multigranularity features and scene-dependent similarity.

4. **Strong Benchmark Performance and Efficiency**  
   Extensive experiments on GazeFollow and VideoAttentionTarget show that RecGaze outperforms existing state-of-the-art methods, achieving higher accuracy while maintaining favorable computational efficiency. The learnable parameter size is only 3.81M, significantly reducing deployment costs.

## 🧩 Method

RecGaze follows a reciprocity reasoning paradigm for gaze following:

1. Extract multigranularity visual features from the input image using a frozen DINOv2 encoder.
2. Generate hierarchical textual descriptions (scene, head, eye) via LLM (BLIP2) to form reciprocity tokens.
3. Mine reciprocal relationships through the RGM module, which performs token selection and cross-modal interaction.
4. Predict the gaze heatmap and in/out probability with a lightweight decoder.
5. Exploit scene-aware gaze similarity to enhance robustness in complex scenarios.

The framework consists of three core modules: **RSE**, **RRR**, and **RGM**, which collaborate to discern and exploit gaze relationships in the scene.

## 📊 Benchmarks

RecGaze is evaluated on standard gaze following benchmarks:

- **GazeFollow**
- **VideoAttentionTarget**

Additional experiments are conducted on:

- **ChildPlay** (educational scenarios)
- **GOO-real** (retail environments)

## 📝 Citation

If this work is helpful for your research, please cite RecGaze. The BibTeX entry will be provided after publication.

```bibtex
@article{recgaze,
  title   = {RecGaze: Learning Reciprocity Relationship for Efficient Gaze Following via Integrative Scenario Modeling},
  journal = {IEEE Transactions on Neural Networks and Learning Systems},
  year    = {2026},
}
```

## 🏷️ Keywords

Gaze following, reciprocity relationship, large language model, computer vision, multimodal reasoning.

## 📄 License

The license will be specified when the code is released.
