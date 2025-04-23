# Gologin_Profile_Manager
Create GoLogin profiles offline, GoLogin profiles locally Gologin profile tool offline, Gologin Antidetect browser offline management, Multi-account management offline
GoLogin Profile Creator
GoLogin Profile Creator is a Python-based GUI tool designed to automate the creation of browser profiles using the GoLogin API and Orbita Browser. It allows users to generate multiple profiles with customizable proxy settings, manage profiles, and launch them with specific configurations (headless or visible mode).
Features

Automated Profile Creation: Generate multiple GoLogin profiles with randomized browser fingerprints.
Proxy Support: Configure profiles with free proxies (US/UK) or custom proxies (IP:Port:User:Pass).
Headless Mode: Option to run profiles in headless or visible mode (default: headless).
Timeout Configuration: Set custom timeout duration for profile initialization.
Profile Management: View, edit, and delete profiles via a user-friendly table interface.
Orbita Browser Integration: Automatically downloads and manages the Orbita Browser executable.

Prerequisites
Before using the tool, ensure you have the following:

Python 3.8+ installed on your system.
GoLogin API Token: Obtain a token from your GoLogin account.
System Requirements:
Windows OS (the tool is designed for Windows due to Orbita Browser compatibility).
Internet connection for downloading Orbita Browser and making API calls.


Dependencies: Install required Python packages listed in requirements.txt.

Installation

Clone the Repository:
git clone https://github.com/yourusername/gologin-profile-creator.git
cd gologin-profile-creator


Install Dependencies:Create a virtual environment (optional but recommended) and install the required packages:
python -m venv venv
source venv/Scripts/activate  # On Windows
# source venv/bin/activate  # On macOS/Linux
pip install -r requirements.txt


Prepare GoLogin Token:

Create a file named token.txt in the project root directory.
Paste your GoLogin API token into token.txt.


Run the Tool:
python main.py



Usage

Launch the Application:

Run python main.py to start the GUI.
The tool will check for the Orbita Browser and download it if necessary (stored in the browsers directory).


Configure Settings:

GoLogin Token: Enter or verify your API token in the "GoLogin Token" field.
Number of Profiles: Specify how many profiles to create (1–9999).
Proxy Settings:
Select a free proxy region (US, UK, or NONE) from the dropdown.
Or enter a custom proxy in the format IP:Port:User:Pass.


Headless Mode: Check/uncheck the "Run in Headless Mode" checkbox (default: checked).
Timeout: Enter the timeout duration in seconds (default: 2).


Create Profiles:

Click the "Create Profile(s)" button to start the creation process.
The tool will generate profiles with randomized fingerprints and display progress in the log window.


Manage Profiles:

View created profiles in the table, which includes:
ID, Proxy Region, Note, Profile Name, Profile ID, Proxy Status, Proxy Info, and Chrome Version.


Double-click a profile’s ID to launch it in Orbita Browser.
Edit fields like Note, Profile Name, Proxy Info, or Chrome Version directly in the table.
Right-click a profile to delete its folder and data.
Enable/disable proxy for a profile using the checkbox in the "Proxy" column.


Profile Storage:

Profiles are stored in the profiles directory as gologin_<profile_id>.
A profiles.csv file maintains the profile data for persistence.



Example Workflow

Enter your GoLogin token in the GUI.
Set "Number of profiles to create" to 5.
Select "us" as the proxy region or input a custom proxy.
Check "Run in Headless Mode" and set timeout to 3 seconds.
Click "Create Profile(s)" to generate 5 profiles.
Double-click a profile ID to launch it in Orbita Browser (headless or visible).
Edit the "Note" field or toggle the proxy checkbox as needed.

Troubleshooting

Orbita Browser Download Fails:
Check your internet connection and ensure the URL https://orbita-browser-windows.gologin.com/orbita-browser-latest.zip is accessible.
Verify write permissions in the browsers directory.


API Token Errors:
Ensure the token in token.txt or the GUI is valid and not expired.


Profile Launch Fails:
Confirm the Chrome version in the table matches the installed Orbita Browser version.
Check if the profile folder (profiles/gologin_<profile_id>) exists.


Proxy Issues:
Verify the custom proxy format (IP:Port:User:Pass) is correct.
Test the proxy independently to ensure it’s functional.



Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a new branch (git checkout -b feature/your-feature).
Make your changes and commit (git commit -m "Add your feature").
Push to the branch (git push origin feature/your-feature).
Open a Pull Request on GitHub.

Please ensure your code follows the project’s style guidelines and includes appropriate tests.
License
This project is licensed under the MIT License. See the LICENSE file for details.
Acknowledgments

Built with PyQt5 for the GUI.
Uses the GoLogin API for profile creation.
Powered by Orbita Browser for profile execution.

Contact
For issues, suggestions, or questions, please open an issue on the GitHub repository.

Note: Replace yourusername in the repository URL with your actual GitHub username before publishing.
