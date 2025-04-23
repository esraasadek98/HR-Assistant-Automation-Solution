# HR-Assistant-Automation-Solution
Project Overview
This UiPath automation project streamlines the CV screening process for HR departments using uses Google's Gemini AI API by automatically extracting candidate information from resumes, including Name, Phone, Email, Address, Job Title and Fit/Not Fit feedback based on requirements.evaluating their fit for a position, and organizing the data in a structured Excel format
<h1>Workflow Architecture</h1>
Main.xaml
├── ScrappingCVData.xaml
│   ├── PreCondition.xaml (checks for valid files)
│   ├── CVProcessingAI.xaml (Gemini API integration)
│   └── addDataToExcel.xaml (writes to output file)
└── Logs completion status
