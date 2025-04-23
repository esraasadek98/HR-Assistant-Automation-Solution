# HR-Assistant-Automation-Solution
Project Overview
This UiPath automation project streamlines the CV screening process for HR departments using uses Google's Gemini AI API by automatically extracting candidate information from resumes, including Name, Phone, Email, Address, Job Title and Fit/Not Fit feedback based on requirements.evaluating their fit for a position, and organizing the data in a structured Excel format
<h2>Workflow Architecture</h2>

<ul>Main.xaml</ul>
<li>ScrappingCVData.xaml</li>
 <li>PreCondition.xaml (checks for valid files)</li>
<li>CVProcessingAI.xaml (Gemini API integration)</li>
<li>addDataToExcel.xaml (writes to output file)</li>
<li>Logs completion status </li>

Key Features
Automated CV Processing: Handles PDF, JPG, PNG file formats

AI-Powered Extraction: Uses Gemini API to parse unstructured CV data

Candidate Evaluation: Assesses fit based on job requirements

Structured Output: Generates standardized Excel reports

Error Handling: Robust retry logic and exception management
Detailed Workflow Description
1. Main Orchestrator (Main.xaml)
Initiates the CV processing workflow

Configures retry parameters (2 attempts, 5-second intervals)

Defines input/output paths

Logs process completion

2. CV Processing Core (ScrappingCVData.xaml)
Pre-Condition Check:

Verifies input folder contains valid files

Throws exception if no files found

File Processing:

Iterates through all files in input folder

Handles different file types:

PDFs: Uses native text extraction with OCR fallback

Images: Uses OCR for text extraction

Skips unsupported formats

Data Collection:

Builds DataTable structure for output

Maintains candidate data across files

3. AI Processing (CVProcessingAI.xaml)
Gemini API Integration:

Constructs prompt with CV text and job requirements

Requests structured data extraction:

Contact information

Professional details

Fitness evaluation (Fit/Not Fit)

Processes JSON response

Cleans and validates output

Error Handling:

Manages API timeouts

Handles malformed responses

Preserves data integrity

4. Data Output (addDataToExcel.xaml)
Receives parsed candidate data

Maps JSON fields to DataTable columns

Appends records to output Excel file

Maintains consistent formatting
Technical Requirements
UiPath Studio

Google Gemini API key

Microsoft Excel
<h3>Setup Instructions</h3>
Clone this repository

Open project in UiPath Studio

Configure paths in Main.xaml:

Input folder for CVs

Output Excel file path

Add your Gemini API key in CVProcessingAI.xaml

Update job requirements in requirements.txt

Run Main.xaml
