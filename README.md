# 🫀 Heart Disease Report Generator with LLaMA 3.2

A comprehensive medical report generation system that combines machine learning predictions with local LLaMA 3.2 to create detailed, personalized heart disease risk assessments and medical reports.

## 🚀 Features

- **Local LLM Processing**: Uses LLaMA 3.2 locally via Ollama for privacy and cost-effectiveness
- **Heart Disease Prediction**: ML model predicts heart disease risk based on patient data
- **Medical Report Generation**: AI-generated comprehensive medical reports
- **PDF Export**: Automatic PDF report generation for medical records
- **ECG Image Support**: Optional ECG image upload and processing
- **Web Interface**: User-friendly Gradio web application
- **Privacy-First**: All processing happens locally, no data leaves your machine

## 📋 Prerequisites

- Python 3.8+
- Ollama installed ([Download here](https://ollama.ai))
- At least 8GB RAM (16GB+ recommended)
- Heart disease prediction model (included)

## 🛠️ Installation

### 1. Install Ollama and LLaMA 3.2
```bash
# Install Ollama from https://ollama.ai
ollama pull llama3.2
```

### 2. Install Python Dependencies
```bash
pip install gradio
pip install fpdf
pip import_ipynb
pip install scikit-learn
pip install pandas
pip install numpy
pip install pillow
pip install requests
```

### 3. Verify Setup
```bash
# Check if Ollama is running
ollama list

# Should show llama3.2 in the list
```

## 🏗️ Project Structure

```
final/
├── app.ipynb                 # Main Gradio application
├── llm/
│   ├── __init__.ipynb        # LLM module initialization
│   ├── llama_ollama.ipynb    # LLaMA 3.2 integration
│   └── prompt_builder.ipynb  # Medical prompt construction
├── utils/
│   ├── __init__.ipynb        # Utils module initialization
│   ├── predict.ipynb         # Heart disease prediction model
│   ├── pdf_generator.ipynb   # PDF report generation
│   └── image_handler.ipynb   # ECG image processing
├── model/                    # Trained ML models
├── static/                   # Static assets
│   └── reports/             # Generated PDF reports
└── README.md                # This file
```

## 🎯 How It Works

### 1. **Data Input**
- Patient demographic and medical data (age, sex, blood pressure, cholesterol, etc.)
- Optional ECG image upload

### 2. **Risk Prediction**
- Machine learning model analyzes patient data
- Predicts heart disease risk probability
- Uses trained Decision Tree Classifier

### 3. **Report Generation**
- LLaMA 3.2 generates comprehensive medical report
- Includes risk assessment, recommendations, and medical insights
- Personalized based on patient data and prediction results

### 4. **Output**
- Detailed medical report in text format
- Professional PDF report for medical records
- Stored ECG images (if provided)

## 🚀 Usage

### Running the Application

1. **Start the Gradio App:**
   ```bash
   jupyter lab
   # Open app.ipynb and run all cells
   ```

2. **Access the Web Interface:**
   - Open your browser to `http://127.0.0.1:7860`
   - Fill in patient data
   - Upload ECG image (optional)
   - Generate report

### Input Parameters

| Parameter | Description | Range |
|-----------|-------------|-------|
| Age | Patient age | 20-100 |
| Sex | Gender (0=Female, 1=Male) | 0-1 |
| Chest Pain Type | Type of chest pain | 0-3 |
| Resting BP | Resting blood pressure | 90-200 |
| Cholesterol | Serum cholesterol | 100-600 |
| Fasting Sugar | Fasting blood sugar > 120 | 0-1 |
| Rest ECG | Resting ECG results | 0-2 |
| Max Heart Rate | Maximum heart rate achieved | 60-202 |
| Exercise Angina | Exercise-induced angina | 0-1 |
| ST Depression | ST depression induced by exercise | 0-6.2 |
| Slope | Slope of peak exercise ST segment | 0-2 |
| Major Vessels | Number of major vessels colored by fluoroscopy | 0-4 |
| Thalassemia | Thalassemia type | 0-3 |

## 🔧 Technical Details

### Machine Learning Model
- **Algorithm**: Decision Tree Classifier
- **Features**: 13 medical parameters
- **Output**: Heart disease risk probability (0-1)
- **Accuracy**: Trained on UCI Heart Disease dataset

### LLaMA 3.2 Integration
- **Model**: llama3.2 (8B parameters)
- **Local Processing**: Via Ollama API
- **Prompt Engineering**: Specialized medical prompts
- **Output**: Structured medical reports

### PDF Generation
- **Library**: FPDF
- **Format**: Professional medical report layout
- **Content**: Patient data, predictions, AI-generated insights
- **Storage**: Local file system

## 📊 Sample Output

### Generated Report Example:
```
PATIENT MEDICAL REPORT
Patient ID: a1b2c3d4
Date: 2024-01-15

RISK ASSESSMENT:
Based on the provided data, this patient shows a 75% probability of heart disease risk.

CLINICAL FINDINGS:
- Age: 65 years
- Blood Pressure: Elevated (160/95 mmHg)
- Cholesterol: High (280 mg/dL)
- ECG: Abnormal ST segment depression

RECOMMENDATIONS:
1. Immediate lifestyle modifications
2. Regular cardiovascular monitoring
3. Consultation with cardiologist
4. Medication review if applicable

FOLLOW-UP:
Schedule follow-up appointment within 2 weeks for further evaluation.
```

## 🛡️ Privacy & Security

- **Local Processing**: All data processed locally
- **No Cloud Storage**: Reports stored on local machine
- **No API Calls**: LLaMA 3.2 runs completely offline
- **Data Protection**: No patient data transmitted externally

## 🔍 Troubleshooting

### Common Issues

**Ollama Connection Error:**
```bash
# Ensure Ollama is running
ollama serve

# Check model availability
ollama list

# Pull model if needed
ollama pull llama3.2
```

**Model Loading Error:**
- Ensure all dependencies are installed
- Check Python environment compatibility
- Verify model files are in correct location

**PDF Generation Error:**
- Install FPDF: `pip install fpdf`
- Check write permissions in static/reports directory
- Ensure sufficient disk space

### Performance Optimization

1. **Memory Usage:**
   - Close other applications when running
   - Use quantized LLaMA models for better performance
   - Consider GPU acceleration if available

2. **Response Time:**
   - LLaMA 3.2 may take 10-30 seconds for report generation
   - First run may be slower due to model loading
   - Subsequent requests will be faster

## 🤝 Contributing

This project is part of the LLM Engineering course. Contributions are welcome:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📄 License

This project is for educational purposes. The original course materials belong to their respective creators.

## 🙏 Acknowledgments

- **Original Course**: LLM Engineering by Edward Donner
- **Dataset**: UCI Heart Disease Dataset
- **LLaMA Model**: Meta AI
- **Ollama**: Local LLM framework

## 📞 Support

For issues or questions:
1. Check the troubleshooting section above
2. Review Ollama documentation: https://ollama.ai/docs
3. Open an issue in the repository

---

**⚠️ Medical Disclaimer**: This tool is for educational purposes only. It should not be used for actual medical diagnosis or treatment decisions. Always consult with qualified healthcare professionals for medical advice.
