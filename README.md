# SatQuery AI – AI-Powered Satellite Imagery Analysis

SatQuery AI is an AI-powered remote-sensing application that helps users analyze satellite imagery using simple natural-language questions. It uses satellite data from **Bhoonidhi, an ISRO/NRSC data platform**, to support the analysis of geographical areas and identify features such as water bodies, vegetation, built-up areas, and changes between satellite images.

The application combines image processing, remote-sensing techniques, and AI-based analysis to convert satellite imagery into understandable results, visual overlays, and downloadable reports.

## Key Features

- **Satellite Image Analysis:** Upload and analyze satellite images for geographical insights.
- **Bhoonidhi Data:** Uses satellite imagery obtained from ISRO's Bhoonidhi data platform.
- **AI-Based Question Answering:** Ask questions about satellite images in natural language.
- **Land Cover Classification:** Identify and visualize water, vegetation, built-up areas, and bare land.
- **Change Detection:** Compare two satellite images to identify changes in geographical features.
- **Optical and SAR Analysis:** Analyze optical and Synthetic Aperture Radar (SAR) imagery.
- **Visual Results:** Display classified regions, image overlays, and highlighted areas.
- **Analysis Reports:** Generate downloadable reports containing findings, measurements, and analysis details.
- **Interactive Interface:** Explore satellite imagery and analysis results through a web-based interface.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core application and image processing |
| FastAPI | Backend API |
| HTML, CSS, JavaScript | Frontend interface |
| NumPy | Numerical and image-array processing |
| Pillow | Image processing |
| Rasterio | Geospatial raster data handling |
| SQLite | Storing application data and query history |
| Groq API | AI-powered question answering and image interpretation |
| ISRO Bhoonidhi | Satellite data source |

## Project Workflow

1. Obtain satellite imagery from the ISRO Bhoonidhi platform.
2. Upload the satellite image or images into SatQuery AI.
3. Enter a natural-language question about the selected geographical area.
4. The application processes the image using remote-sensing and image-processing techniques.
5. AI assists in interpreting the results and generating an understandable explanation.
6. View highlighted regions, visual overlays, and analysis results.
7. Generate and download an analysis report.

## Project Structure

```text
SatQuery-AI/
│
├── web/
│   └── index.html
│
├── agent.py
├── bhoonidhi.py
├── config.py
├── db.py
├── detect.py
├── fetch_tiles.py
├── package_data.py
├── run.py
├── server.py
├── tools.py
├── test_satquery.py
│
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/palakvaria24-ctrl/SatQuery-AI.git
```

```bash
cd SatQuery-AI
```

### 2. Create a Virtual Environment (Recommended)

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file in the project folder using `.env.example` as a template.

Add your Groq API key:

```env
GROQ_API_KEY=your_groq_api_key
```

Add your Bhoonidhi account credentials if required:

```env
BHOONIDHI_USER=your_bhoonidhi_username
BHOONIDHI_PASS=your_bhoonidhi_password
```

**Important:** Never upload your actual API keys or account credentials to GitHub.

### 5. Run the Application

```bash
python run.py
```

Open the application in your browser:

```text
http://localhost:8077
```

## Bhoonidhi Data Access

Bhoonidhi is an ISRO/NRSC platform for accessing satellite data products.

The project includes a Python client (`bhoonidhi.py`) for interacting with the Bhoonidhi API. It supports authentication, searching available satellite data collections, searching products by geographical area and date, and downloading available products.

Example:

```bash
python bhoonidhi.py collections
```

Search for satellite products:

```bash
python bhoonidhi.py search --collection Sentinel-1A_SAR-IW_GRD --bbox 93.90 26.90 94.30 27.10 --start 2024-10-01 --end 2024-10-31
```

## Testing

Run the project's test suite:

```bash
python test_satquery.py
```

The tests help verify image-processing operations, water detection, change detection, area calculations, database operations, and image compatibility.

## Applications

- Flood and water-body monitoring
- Agricultural and land-cover analysis
- Geographical change detection
- Satellite image interpretation
- Remote-sensing research
- Disaster-management support

## Limitations

- Analysis accuracy depends on the quality and resolution of the input satellite imagery.
- AI-generated explanations should be interpreted alongside the measured image-analysis results.
- Some analyses require compatible satellite images and appropriate geographical information.
- Access to Bhoonidhi data products may require valid account credentials.
- The application is a project-level analysis tool and does not replace official disaster-management or ground-survey assessments.

## Project Purpose

SatQuery AI was developed to make satellite imagery analysis more accessible by combining ISRO Bhoonidhi satellite data, image-processing techniques, and AI-powered natural-language interaction.

The project demonstrates how remote sensing and artificial intelligence can work together to support geographical analysis and decision-making.

---

**Developed as a project for satellite imagery analysis and AI-assisted remote sensing.**
