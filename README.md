# JSON-Schema_classicfication_using_Groq

````markdown
# Task 2: Structured User Information Extraction using Groq Function Calling

This project demonstrates extracting structured user information from conversational chat text using **Groq API** with JSON Schema validation.

---

## 📌 Objective

- Extract structured fields (`name`, `email`, `phone`, `location`, `age`) from user messages.
- Use Groq's **function-calling** capabilities to automate information extraction.
- Validate extracted data against a predefined JSON schema.

---

## 🛠️ Dependencies

- Python 3.x
- Groq SDK (`pip install groq`)
- Optional: `jsonschema` library for validation (`pip install jsonschema`)

---

## ⚡ Setup

1. Set your **Groq API Key** in environment variables:

```python
import os
os.environ["GROQ_API_KEY"] = "<YOUR_API_KEY>"
````

2. Initialize Groq client:

```python
from groq import Groq
client = Groq(api_key=os.environ["GROQ_API_KEY"])
```

---

## 🔧 JSON Schema

```json
{
  "type": "object",
  "properties": {
    "name": {"type": "string"},
    "email": {"type": "string"},
    "phone": {"type": "string"},
    "location": {"type": "string"},
    "age": {"type": "integer"}
  },
  "required": ["name", "email", "phone", "location", "age"],
  "additionalProperties": false
}
```

* Ensures all required fields are extracted correctly.
* Prevents unexpected or extra fields in output.

---

## 🚀 Example Usage

```python
chats = [
    "Hi, I'm Rajesh Kumar. My email is rajesh.kumar@email.com. I live in Bangalore and my phone is +91 9876543210. I'm 28 years old."
]

result = extract_with_groq(chats[0])
print(result)
```

**Sample Output:**

```json
{
  "name": "Rajesh Kumar",
  "email": "rajesh.kumar@email.com",
  "phone": "+91 9876543210",
  "location": "Bangalore",
  "age": 28
}
```

---

## ✅ Validation

* Uses `jsonschema` to check the extracted data against the schema.
* Ensures accuracy and prevents missing fields or invalid types.

---

## 📝 Features

* Automated extraction using Groq function-calling.
* Handles multiple chat examples.
* Validates output automatically (optional).
* Ready for integration into chatbots, CRM, or data pipelines.

---

## ⚠️ Notes

* Make sure the Groq API Key is valid and has access to the `llama-3.1-8b-instant` model (or the model you choose).
* Validation is optional if `jsonschema` is not installed.
* Designed for demonstration purposes; production use may require error handling and sanitization.

---

## 🔗 References

* [Groq Python SDK Documentation](https://www.groq.ai/docs)
* [JSON Schema](https://json-schema.org/)

---

**Author:** Amit Kushwaha
**Date:** 2025-09-15

```

