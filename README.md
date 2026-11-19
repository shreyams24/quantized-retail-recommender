# Quantized Retail Recommender

[![Built with askThili](https://ask.thili.ai/api/v1/public/projects/5dqx8g8xjf/badge.svg)](https://ask.thili.ai/b/5dqx8g8xjf)

This project develops a retail recommender system capable of predicting next items based on shopping basket data. A key focus is on optimizing the model for deployment by applying quantization techniques to significantly reduce its size while maintaining recommendation accuracy. This makes the recommender suitable for resource-constrained environments.

## What you are building

**Goal.** You will build a smart retail recommender that identifies frequently bought items, and then shrink its model using quantization for reduced footprint.

**Done when.** The project is complete when you have a functional recommendation model that has been shrunk using post-training quantization, demonstrating size reduction and evaluating its accuracy impact.

## Milestones

Tick these off as you go, and commit after each one.

- [ ] **1. Prepare synthetic shopping basket data for training**  
      Hint: Use the techniques from 'Teach a Language Model What Sells Together' to structure your data.
- [ ] **2. Continue pretraining a small LM on the basket data**  
      Hint: Apply continued pretraining as shown in 'Teach a Language Model What Sells Together'.
- [ ] **3. Implement next-item prediction and itemset probing**  
      Hint: Implement next-item prediction and itemset probing using the methods from 'Teach a Language Model What Sells Together'.
- [ ] **4. Measure the baseline size and accuracy of the model**  
      Hint: Establish baseline metrics for model size and accuracy before quantization.
- [ ] **5. Apply dynamic and static post-training quantization to the model**  
      Hint: Apply dynamic and static post-training quantization as demonstrated in 'Shrink a Neural Network with Quantisation'.
- [ ] **6. Demonstrate size reduction and evaluate accuracy impact**  
      Hint: Compare the size and accuracy of the quantized models against your baseline.

## Run it

You need Python 3.12 and git.

```bash
python3.12 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env        # then choose a model; see the comments inside
streamlit run app/main.py
pytest
```

Your work goes in `app/core.py` (one stub per milestone) and `tests/test_core.py`. The first tests pass already; they
check the plumbing.

## Settings and secrets

Model settings live in `.env`, which is ignored by git. **Never commit `.env` or paste a key into code.** If a key ever
reaches GitHub, treat it as leaked and make a new one.

## Stretch ideas

- Explore different quantization schemes beyond dynamic and static post-training, such as quantization-aware training, to see if further size reduction or accuracy improvements are possible.
- Investigate the inference speed of the quantized model compared to the baseline model to quantify the 'faster loading' benefit mentioned in the pitch.
- Simulate deployment to a specific edge device by considering its memory constraints and processing capabilities, and how the quantized model fits within them.
