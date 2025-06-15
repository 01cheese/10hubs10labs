---
title: AI Calorie Calculator
published: 2025-06-15
updated: 2025-06-15
description: "Upload a food photo and instantly get its calories using FastAPI and a HuggingFace image model — all under 300 lines of code."
image: "./assets/img/calorie_calculator.png"
tags: [Python, FastAPI, ML, HuggingFace, AI, 300lines]
category: Projects
draft: false
lang: "en"
---

# 🧠 AI Calorie Calculator

**AI Calorie Calculator** is a smart web app that identifies food from an uploaded image and returns its estimated calories and nutritional values. Built with FastAPI and HuggingFace Transformers, it uses a pre-trained image classification model trained on 101 food categories.

All core functionality is implemented in less than **300 lines of Python code**.

---

## Features

- Upload any food image (JPEG, PNG)
- AI model predicts food class (e.g., pizza, sushi, burger)
- Displays calories, protein, carbs, and fat
- Built with FastAPI and served as a web app
- Fully open source and easy to deploy

---

## How It Works

1. User uploads an image via the web interface.
2. The image is sent to the FastAPI backend.
3. A HuggingFace model (`nateraw/food`) processes the image.
4. The predicted label is matched with a JSON dataset of nutrition values.
5. Caloric and nutritional data is returned and displayed.

---

## Example Code (Backend)

```python
@app.post("/predict/")
async def predict_food(file: UploadFile = File(...)):
    image_data = await file.read()
    image = Image.open(io.BytesIO(image_data)).convert("RGB")
    inputs = processor(images=image, return_tensors="pt")
    with torch.no_grad():
        outputs = model(**inputs)
        logits = outputs.logits
        idx = logits.argmax(-1).item()
    label = labels[idx]
    nutrition = nutrition_data.get(label, {})
    return JSONResponse({
        "predicted_label": label,
        "nutrition": nutrition
    })
```

---

## Technologies Used

- FastAPI
- HuggingFace Transformers
- PIL (Python Imaging Library)
- JSON nutrition dataset
- Vanilla HTML + JS frontend

---

## How to Run Locally

```bash
git clone https://github.com/01cheese/ML-food-calories-fastAPI
cd ai-calorie-calculator
pip install -r requirements.txt
uvicorn main:app --reload
```

Then open your browser at:  
`http://127.0.0.1:8000`

---

## 🔗 GitHub

[https://github.com/your-username/ai-calorie-calculator](https://github.com/your-username/ai-calorie-calculator)

---

## YouTube

<iframe width="100%" height="468" src="https://www.youtube.com/embed/UR8eWHFC8s0?si=dm_MbHfku2-0SHCo" title="Lightning Generator" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

## 🌐 Live Demo

[https://10hubs10labs.vercel.app](https://10hubs10labs.vercel.app)

---

## Summary

This project is an ideal starter for anyone learning FastAPI, machine learning, or working with image recognition models. It shows how simple AI tools can solve real-world tasks like calorie tracking using just a few lines of code.

Made by [your-name](https://github.com/your-username)
