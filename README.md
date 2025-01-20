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

Der er to måder at sætte udviklingsmiljøet op på:

#### Anbefalet: Brug af uv (hurtigere og mere effektiv)
```bash
# Installer uv (kun hvis ikke installeret på forhånd)
# med pip (både windows og macOS / Linux)
pip install uv 

# Uden pip
# På windows:
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/0.5.21/install.ps1 | iex"

# På macOS / Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Opret og aktiver virtuelt miljø
uv venv
# På Windows:
.venv\Scripts\activate
# På Linux/Mac:
source .venv/bin/activate
```

#### Alternativ: Traditionel venv
```bash
# Opret virtual environment
python -m venv venv

# Aktiver miljøet
# På Windows:
venv\Scripts\activate
# På Linux/Mac:
source venv/bin/activate
```

### 2. Team Branches
For at sikre at hvert team arbejder i deres egen branch, skal I følge disse trin:

```bash
# 1. Klon main branch
git clone https://github.com/kd-ngt/hackaton2025
cd hackaton2025

# 2. Skift til jeres team branch
# For Team A:
git checkout teamA

# For Team B:
git checkout teamB

# For Team C:
git checkout teamC
```

Bemærk:
- Sørg for at være i den rigtige team branch før I begynder at kode
- Commit og push jeres ændringer regelmæssigt til jeres team branch
- Undgå at pushe direkte til main branch

## Eksperter & Mentorer
[Information om tilgængelige eksperter og mentorer fra både NGT og EY]

## Evaluering & Præsentation
[Beskriv hvordan løsningerne skal præsenteres og evalueres]

## Kontakt
#### NGT
- Nicki Lentz
  - Email: nilen@regionsjaelland.dk
  - Tlf: +45 21 22 04 48

- Caroline Ostenfeldt
  - Email: coste@regionsjaelland.dk
  - Tlf: +45 20 59 92 91

#### EY
- Philip Theut Stehr-Nielsen
  - Email: philip.theut@dk.ey.com
  - Tlf: +45 25 29 37 23


## Next Steps
[Information om hvad der sker efter hackathon'et, opfølgning, implementering etc.]
