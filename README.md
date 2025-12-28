[test_model.ipynb](https://github.com/user-attachments/files/24360509/test_model.ipynb)
{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "8b5afd02-83c3-4076-9010-f3c35eac8b82",
   "metadata": {},
   "source": [
    "## Mario Assistant Model (Ollama)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "0afd866c-6184-4db7-b9da-80d83aa04748",
   "metadata": {},
   "source": [
    "This custom Ollama model is based on **Gemma 3 (1B)** and is configured\n",
    "to respond as **Mario from Super Mario Bros**."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "317160b0-2401-4fab-a131-a133e065b526",
   "metadata": {},
   "outputs": [],
   "source": [
    "FROM gemma3:1b"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "c398dc88-7af7-4df6-9338-34e441965625",
   "metadata": {},
   "source": [
    "- This line specifies the **base model** we are using.\n",
    "- `gemma3:1b` is a **1-billion parameter model** from Ollama.\n",
    "- All our instructions and behavior will build on top of this model."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "8c9e2fe2-1df4-47ed-918c-4a48a3baf231",
   "metadata": {},
   "outputs": [],
   "source": [
    "PARAMETER temperature 1"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "3c84b480-96fa-42ae-b8c9-4c2a9744265a",
   "metadata": {},
   "source": [
    "- `temperature` controls the **randomness / creativity** of the model.\n",
    "- `1` means **high creativity**, so Mario will answer in a fun, playful style.\n",
    "- Lower values (e.g., 0.2) would make the model more **predictable and factual**."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "39987591-57e7-499b-9995-28d4977ed3ba",
   "metadata": {},
   "outputs": [],
   "source": [
    "SYSTEM \"\"\"\n",
    "You are Mario from Super Mario Bros. Answer as Mario, the assistant, only.\n",
    "\"\"\""
   ]
  },
  {
   "cell_type": "markdown",
   "id": "bef76dc9-1a89-4202-8a40-c3ed66eccc7b",
   "metadata": {},
   "source": [
    "- This defines the **system prompt**, or the “personality” of the model.\n",
    "- Here, we instruct the model to **act as Mario** and respond like him.\n",
    "- Everything the model generates will follow this **persona**."
   ]
  },
  {
   "cell_type": "markdown",
   "id": "6e27362c-5102-446e-a6cd-c559720401df",
   "metadata": {},
   "source": [
    "First change the directory to where Modelfile exist."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "337c22fe-73b5-427c-aea7-44c5c1209195",
   "metadata": {},
   "outputs": [],
   "source": [
    "ollama create mario -f ./Modelfile"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "1fea2440-5110-496e-bf14-3f67da957a3e",
   "metadata": {},
   "source": [
    "Then, run the above command line"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "ca91f551-6059-419d-a1c5-b77dc666d8dd",
   "metadata": {},
   "outputs": [],
   "source": [
    "ollama run mario"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "156f99cb-bbb9-44c5-aade-e792e14589e0",
   "metadata": {},
   "source": [
    "Now , you get the response and ask anything you want."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "76a6aa32-2e68-4336-8ed6-14c8a6254acc",
   "metadata": {},
   "outputs": [],
   "source": [
    "You can change "
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.13.2"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
