# Digital Twin for Precision Farming

A web-based precision farming prototype that brings together interactive farm visualization, crop analysis, weed detection, weather information, crop recommendations, agricultural market information, and AI-powered farming assistance.

## Features

- **Interactive Farm Visualization:** Explore the farm through a three-dimensional visualization.
- **Weed Detection:** Upload an image for weed detection using a YOLO model.
- **Weather Information:** View weather information provided by the Open-Meteo API.
- **Crop Recommendations:** Get recommendations based on available soil and weather information.
- **Agricultural Market Information:** Retrieve market-price information through the backend integration.
- **AI Farming Assistant:** Ask farming-related questions using the Groq API.
- **User Authentication:** Access the application through its login and registration functionality.
- **Notifications and Settings:** Access notifications, profile settings, language preferences, and appearance options.
- **Voice Assistance:** Use supported speech input and spoken responses.

## Technology Stack

| Component | Technology |
|---|---|
| Frontend | React.js, JavaScript, Vite |
| Backend | Python, FastAPI |
| Weed Detection | YOLO |
| Weather Data | Open-Meteo API |
| AI Assistant | Groq API |
| Database | SQLite |
| Version Control | Git and GitHub |

## Prerequisites

Install the following before starting:

- Python
- Node.js and npm
- Git
- Visual Studio Code (recommended)

## Getting Started

### 1. Clone the Repository

Open a terminal and run:

```bash
git clone https://github.com/bnashritha22/Digital-Twin-for-Precision-Farming.git
cd Digital-Twin-for-Precision-Farming
```

### 2. Set Up the Backend

Open a terminal at the project root and run:

```powershell
cd backend
python -m venv venv
.\venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

If PowerShell prevents virtual-environment activation, you can run the backend using the virtual environment's Python executable directly.

### 3. Configure Environment Variables

Inside the `backend` folder, create a file named `.env`.

Add your own Groq API key:

```env
GROQ_API_KEY=your_groq_api_key_here
```

Replace the placeholder with your own API key. Do not share your API key or commit the `.env` file to GitHub.

Obtain an API key through the official Groq Console: https://console.groq.com/

The `.env.example` file provides a template for the required environment variable.

### 4. Start the Backend

From the `backend` directory, run:

```powershell
python -m uvicorn main:app --host 127.0.0.1 --port 8000
```

The backend should be available at:

- API base: http://127.0.0.1:8000
- Interactive API documentation: http://127.0.0.1:8000/docs
- Status endpoint: http://127.0.0.1:8000/api/status

Keep this terminal open while using the application.

### 5. Set Up the Frontend

Open a **second terminal** at the project root and run:

```powershell
cd frontend
npm install
npm run dev
```

Open the local address displayed by Vite, usually:

http://localhost:5173

Keep both the frontend and backend terminals running while using the application.

## Troubleshooting

### Backend does not start

- Confirm that Python is installed.
- Ensure that the virtual environment is activated.
- Install the dependencies using `pip install -r requirements.txt`.
- Check whether port `8000` is already in use.

### Frontend does not start

- Confirm that Node.js and npm are installed.
- Run `npm install` inside the `frontend` folder.
- Check whether port `5173` is already in use.

### AI assistant does not respond

- Confirm that `backend/.env` contains a valid Groq API key.
- Restart the backend after changing the environment variables.
- Check the backend terminal for errors.

### Weed detection does not work

- Confirm that the model file `backend/models/best.pt` exists.
- Use an image format supported by the application.
- Check the backend terminal for model-loading or inference errors.

## Project Structure

```text
Digital-Twin-for-Precision-Farming/
├── backend/
│   ├── main.py
│   ├── requirements.txt
│   ├── models/
│   │   └── best.pt
│   ├── .env.example
│   └── ...
├── frontend/
│   ├── package.json
│   └── ...
├── .gitignore
└── README.md
```

## Security

- Never commit API keys, passwords, or other secrets.
- Keep `.env` files out of version control.
- Each developer should use their own API key.
- Do not commit personal databases or virtual-environment folders.

## Note

This project is a web-based prototype for precision farming. Physical IoT sensors, drones, and satellite-based monitoring are not included as implemented hardware integrations.

## Repository

https://github.com/bnashritha22/Digital-Twin-for-Precision-Farming
