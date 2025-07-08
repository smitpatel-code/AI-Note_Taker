# AI-Note_Taker
My Research Assistant: Chrome Extension & Spring Boot Backend
This repository showcases "My Research Assistant", a project comprising a Chrome Extension and a Spring Boot backend service.

The Chrome Extension is designed to streamline research by providing quick summaries and suggesting related topics for selected text on any webpage. It offers a convenient right-click context menu to trigger these actions.

The Spring Boot Backend (research-assistant) acts as the brain behind the operation. It receives requests from the Chrome Extension, processes them, and then interacts with the Google Gemini API to generate intelligent responses (summaries, suggestions, etc.) before sending them back to the extension.

Project Structure
RESEARCH_ASSISTANT_EXT/: Contains all the source code for the Chrome Extension (e.g., manifest.json, popup.html, background.js, etc.).

research-assistant/: Contains the Spring Boot application (backend service), including its pom.xml (or build.gradle) and source code.

Getting Started: Trying Out the Project
To experience the full functionality of "My Research Assistant," you'll need to run both the backend service locally and install the Chrome extension.

1. Obtain a Free Google Gemini API Key
The backend service uses the Google Gemini API to perform its AI-powered tasks. You can obtain a free API key for personal use and testing from Google AI Studio.

Go to Google AI Studio:
Open your web browser and navigate to: https://aistudio.google.com/

Log in with Your Google Account:
If prompted, sign in with your personal Google account.

Create Your API Key:

On the left-hand navigation pane, look for and click on "Get API key".

Click the "Create API key in new project" button (or "Create API key" if it gives you that option directly).

Your new API key (a long alphanumeric string) will be generated and displayed. Copy this key immediately and keep it secure. You will need it for the next step.

2. Running the Backend Service (Research Assistant)
This Spring Boot application powers the AI capabilities of the Chrome Extension.



Steps:

Download the Project Source Code:
You can get the entire project by either cloning the repository or downloading a ZIP archive:

Option A: Clone the Repository (Recommended if you have Git):

Bash

git clone https://github.com/smitpatel-code/AI_Note_Taker.git
cd RESEARCH_ASSISTANT_EXT # Navigate into the backend project folder


Option B: Download as a ZIP:

Go to this GitHub repository page in your browser.

Click the green "<> Code" button (or "Code" button).

Select "Download ZIP".

Unzip the downloaded file This will create a folder Navigate into it.

Open Project in Your IDE:
Open the research-assistant project folder (the one containing pom.xml or build.gradle) in your preferred Java IDE (e.g., IntelliJ IDEA, Eclipse, VS Code). The IDE should automatically recognize it as a Spring Boot project and resolve dependencies.

Configure Your Gemini API Key:
The application reads the Gemini API key from an environment variable for security.

Set the Environment Variable:
Set the API key you obtained in Step 1 as an environment variable named GEMINI_KEY.

For macOS/Linux (Terminal):

Bash

export GEMINI_KEY="YOUR_ACTUAL_GEMINI_API_KEY"
# Then run your application from the same terminal session
For Windows (Command Prompt):

DOS

set GEMINI_KEY="YOUR_ACTUAL_GEMINI_API_KEY"
rem Then run your application from the same command prompt
For Windows (PowerShell):

PowerShell

$env:GEMINI_KEY="YOUR_ACTUAL_GEMINI_API_KEY"
# Then run your application from the same PowerShell window
Within your IDE (Recommended for IDE users):
In your IDE's run configuration settings for the ResearchAssistantApplication (or your main Spring Boot class), look for a section to add "Environment variables." Add GEMINI_KEY with your API key as its value.

Run the Spring Boot Application:
Once the API key is configured, you can start the backend:

From your IDE (Recommended):

Locate the main application class, typically ResearchAssistantApplication.java (e.g., in src/main/java/com/research/assistant).

Right-click on this file or the main method within it, and select "Run 'ResearchAssistantApplication.main()'" or similar.

From the Terminal/Command Line:

Ensure your terminal is in the research-assistant project root directory.

If using Maven:

Bash

mvn spring-boot:run

Verify Backend is Running:
Check your IDE console or terminal output. You should see messages indicating that the Spring Boot application has started and the Tomcat server is running, usually on port 8080:

Tomcat started on port(s): 8080 (http) with context path ''
The backend is now operational and awaiting requests.

3. Installing and Running the Chrome Extension
This is the client-side component that interacts with the backend.

Locate the Extension Folder:
The Chrome extension's files are located within the downloaded project structure.
Navigate to the chrome-extension folder inside the main project directory you downloaded (e.g., [YourRepositoryName]-main/chrome-extension/ or [YourRepositoryName]/chrome-extension/ if you cloned). This folder contains your manifest.json file. Remember the path to this folder!

Open Chrome Extensions Page:
Open your Google Chrome browser. In the address bar, type chrome://extensions and press Enter.

Enable Developer Mode:
On the Chrome Extensions page, look for a toggle switch labeled "Developer mode" in the top-right corner. Make sure it is turned ON.

Load the Unpacked Extension:
After enabling Developer mode, a button labeled "Load unpacked" will appear (usually on the left or top left). Click this button.

Select the Extension Folder:
A file browser window will open. Navigate to and select the chrome-extension folder you located in Step 1 (the one containing your manifest.json file).

Extension Installed!
The extension should now appear in your list of Chrome extensions. You might see its icon in your browser's toolbar (you may need to click the puzzle piece icon to pin it for easy access).

4. Using the Extension with the Local Backend
With both the research-assistant backend running locally and the Chrome Extension installed:



Technologies Used
Chrome Extension: HTML, CSS, JavaScript

Backend: Java, Spring Boot

AI Integration: Google Gemini API

HTTP Client: Spring WebClient
