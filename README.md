# AI Project Estimator - Backend 🚀

This is the backend for the **AI Project Estimator** system, a highly intelligent API that analyzes software projects to estimate development effort, time, and cost. It utilizes a Multi-Agent system powered by **Google Gemini** and **OpenAI**, alongside a local **Machine Learning Model** (Random Forest Regressor) for value-based cost estimation.

## 🛠️ Tech Stack

- **Framework**: FastAPI (Python 3.10+)
- **Generative AI**: Google Gemini API, OpenAI API
- **Machine Learning**: Scikit-Learn (Multi-output Regression)
- **Database**: MongoDB Atlas (Motor/PyMongo)
- **Server**: Uvicorn

## 📂 Architecture

The backend is built around an **Agentic AI** design pattern:
- `orchestrator.py`: Manages the flow of data between different agents.
- `estimation_agent.py`: Uses the `.pkl` ML model and Gemini to calculate costs.
- `metrics_agent.py`: Analyzes code complexity and structure.
- `risk_agent.py` & `report_agent.py`: Evaluate technical risks and compile the final Markdown report.

## 🚀 Local Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Manohar-2905/SoftwareCost_esstimator_backend.git
   cd SoftwareCost_esstimator_backend
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Environment Variables:**
   Rename `.env.example` to `.env` and fill in your keys:
   ```env
   GEMINI_API_KEY=your_google_gemini_api_key
   OPENAI_API_KEY=your_openai_api_key
   MONGODB_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret
   ```

5. **Run the server:**
   ```bash
   uvicorn main:app --reload --port 8000
   ```
   The API will be available at `http://localhost:8000`. You can access the Swagger documentation at `http://localhost:8000/docs`.

## 🌍 Deployment
This backend is optimized to be deployed easily on platforms like **Render.com** or **Railway**. Ensure you configure your environment variables in your hosting provider's dashboard and set your build command to `pip install -r requirements.txt` and start command to `uvicorn main:app --host 0.0.0.0 --port $PORT`.
