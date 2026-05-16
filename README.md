## Prerequisites

- Python 3.11+
- Java 21 + Maven
- Node 18+ + Angular CLI (`npm install -g @angular/cli`)
- A **Google Gemini API key** — get one free at https://aistudio.google.com/

## Setup & Run

### 1. Python AI Service

```bash
cd incident-analyzer-ai-repo
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

pip install -r requirements.txt

# Create .env from the example and add your key
copy .env.example .env
# Edit .env and set GEMINI_API_KEY=your_key_here

uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

Service docs: http://localhost:8000/docs

### 2. Spring Boot API Gateway

```bash
cd incident-analyzer-service-repo

# Set env variable (Windows PowerShell)
$env:GEMINI_API_KEY = "your_key_here"

mvn spring-boot:run
```

Swagger UI: http://localhost:8080/swagger-ui.html

### 3. Angular UI

```bash
cd incident-analyzer-ui-repo
npm install
ng serve
```

UI: http://localhost:4200
