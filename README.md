# NGT/EY Hackathon 2025

## Om Hackaton'et
[Kort introduktion til hackathon'et og samarbejdet mellem NGT og EY. Beskriv overordnet format med 3 cases og 3 teams]

## Format
[Beskriv den praktiske struktur for hackathon'et - varighed, lokation, overordnet tidsplan]

### Projekt Struktur
```
hackaton2025/
├── config/             # Konfigurationsfiler - definer egen config.yaml per team/case
├── data/              
│   ├── raw/           # Rå data
│   └── processed/     # Behandlet data
├── docs/              # Dokumentation
├── models/            # Gemte modeller
├── notebooks/         # Jupyter notebooks
├── src/               # Kildekode
│   ├── models/        # Model implementeringer
│   ├── preprocessing/ # Data preprocessing
│   ├── utils/         # Hjælpefunktioner
│   └── visualization/ # Visualiseringsværktøjer
└── tests/             # Unit tests
```


## Cases
[Beskrivelse af de tre cases og deres specifikke tekniske krav/fokusområder]

## Tekniske Krav

### Tilgængelige Modeller
https://app.requesty.ai/ er en router til mere end 100 forskellige sprog modeller. Heriblandt til GPT-4, Claude Sonnet 3.5, DeepSeek, Qwen2.5, llama mm.

Opret en bruger på hjemmeside for at se de mange forskellige modeller og hvordan de integreres ind i koden. Eksempel kan ses nedenunder.

Der skal IKKE oprettes API-nøgler. Dette er gjort, og i skal blot kontakte Nicki Lentz eller Caroline Ostenfeldt for at få dem udleveret.

### Brug af Modellerne
```python
import openai

ROUTER_API_KEY = "your-api-key"

# Initialize the client
client = openai.OpenAI(
    api_key=ROUTER_API_KEY,
    base_url="https://router.requesty.ai/v1"
)

try:
    # Make your API call
    response = client.chat.completions.create(
        model="deepinfra/Qwen/Qwen2.5-72B-Instruct",
        messages=[
            {
                "role": "system",
                "content": "You are a helpful assistant."
            },
            {
                "role": "user",
                "content": "Hello! How can you help me today?"
            }
        ]
    )

    # Print the assistant's response
    print("Assistant:", response.choices[0].message.content)

except openai.APIError as e:
    print(f"OpenAI API error: {e}")
except Exception as e:
    print(f"Unexpected error: {e}")
```

## Setup Guide

### 1. Klargøring af Udviklingsmiljø
```bash
# Clone repository
git clone https://github.com/[organization]/hackaton2025.git
cd hackaton2025

# Opret virtual environment
python -m venv venv
source venv/bin/activate  # På Windows: venv\Scripts\activate

# Installer dependencies baseret på jeres case behov
pip install -r requirements.txt  # Opret denne fil baseret på jeres case
```

## Eksperter & Mentorer
[Information om tilgængelige eksperter og mentorer fra både NGT og EY]

## Evaluering & Præsentation
[Beskriv hvordan løsningerne skal præsenteres og evalueres]

## Kontakt
[Kontaktinformation til relevante kontaktpersoner fra både NGT og EY]

## Next Steps
[Information om hvad der sker efter hackathon'et, opfølgning, implementering etc.]