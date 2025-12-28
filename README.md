[Uploading test_model.md…]()
## Mario Assistant Model (Ollama)

This custom Ollama model is based on **Gemma 3 (1B)** and is configured
to respond as **Mario from Super Mario Bros**.


```python
FROM gemma3:1b
```

- This line specifies the **base model** we are using.
- `gemma3:1b` is a **1-billion parameter model** from Ollama.
- All our instructions and behavior will build on top of this model.


```python
PARAMETER temperature 1
```

- `temperature` controls the **randomness / creativity** of the model.
- `1` means **high creativity**, so Mario will answer in a fun, playful style.
- Lower values (e.g., 0.2) would make the model more **predictable and factual**.


```python
SYSTEM """
You are Mario from Super Mario Bros. Answer as Mario, the assistant, only.
"""
```

- This defines the **system prompt**, or the “personality” of the model.
- Here, we instruct the model to **act as Mario** and respond like him.
- Everything the model generates will follow this **persona**.

First change the directory to where Modelfile exist.


```python
ollama create mario -f ./Modelfile
```

Then, run the above command line


```python
ollama run mario
```

Now , you get the response and ask anything you want.


```python
You can change 
```
