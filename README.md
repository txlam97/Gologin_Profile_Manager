# Gologin_Profile_Manager
Create GoLogin profiles offline, GoLogin profiles locally Gologin profile tool offline, Gologin Antidetect browser offline management, Multi-account management offline

GoLogin Profile Creator
GoLogin Profile Creator is a Windows GUI tool that automates the creation and management of browser profiles using the GoLogin API and Orbita Browser. It allows users to generate multiple profiles with randomized fingerprints, configure proxies, and launch profiles in headless or visible mode. The tool is available as a standalone executable (.exe) for easy use or as source code for developers.
Features

Automated Profile Creation: Generate multiple GoLogin profiles with randomized browser fingerprints.
Proxy Support: Use free proxies (US/UK) or custom proxies (IP:Port:User:Pass).
Headless Mode: Run profiles in headless or visible mode (default: headless, enabled via checkbox).
Timeout Configuration: Set custom timeout for profile initialization (default: 2 seconds, adjustable via textbox).
Profile Management: View, edit, and delete profiles in a user-friendly table interface.
Orbita Browser Integration: Automatically downloads and manages the Orbita Browser executable.

Prerequisites
To use the .exe or source code, ensure the following:

Windows OS: The tool is designed for Windows due to Orbita Browser compatibility.
GoLogin API Token: Obtain a token from your GoLogin account.
Internet Connection: Required for downloading Orbita Browser and making API calls.
For Source Code Users:
Python 3.8+.
Dependencies listed in requirements.txt.



Installation
Option 1: Using the Executable (.exe)

Download the Latest Release:

Go to the Releases page on GitHub.
Download the latest .exe file (e.g., GoLoginProfileCreator-vX.X.X.exe).


Run the Executable:

Double-click the .exe file to launch the tool.
The tool will automatically create a browsers folder in the same directory to download Orbita Browser if needed.


Prepare GoLogin Token:

Create a file named token.txt in the same directory as the .exe.
Paste your GoLogin API token into token.txt.



Option 2: Using the Source Code

Clone the Repository:
git clone https://github.com/yourusername/gologin-profile-creator.git
cd gologin-profile-creator


Install Dependencies:Create a virtual environment (recommended) and install required packages:
python -m venv venv
source venv/Scripts/activate  # On Windows
pip install -r requirements.txt


Prepare GoLogin Token:

Create a token.txt file in the project root.
Paste your GoLogin API token into token.txt.


Run the Tool:
python main.py



Usage

Launch the Tool:

For .exe: Double-click the .exe file.
For source: Run python main.py.
The tool will download Orbita Browser to the browsers directory if not already present.


Configure Settings:

GoLogin Token: Verify or enter your API token in the "GoLogin Token" field.
Number of Profiles: Specify how many profiles to create (1–9999).
Proxy Settings:
Select a free proxy region (US, UK, or NONE) from the dropdown.
Or enter a custom proxy in the format IP:Port:User:Pass.


Headless Mode: Check/uncheck "Run in Headless Mode" (default: checked). Checked means profiles run in headless mode; unchecked means visible mode.
Timeout: Enter timeout duration in seconds (default: 2) in the "Timeout" textbox. This sets the delay between starting and stopping profiles during creation.


Create Profiles:

Click "Create Profile(s)" to generate profiles.
Progress is shown in the log window.
Profiles run in headless or visible mode based on the checkbox, with the specified timeout.


Manage Profiles:

View profiles in the table, showing:
ID, Proxy Region, Note, Profile Name, Profile ID, Proxy Status, Proxy Info, Chrome Version.


Double-click a profile’s ID to launch it in Orbita Browser.
Edit Note, Profile Name, Proxy Info, or Chrome Version in the table.
Right-click a profile to delete its folder and data.
Toggle proxy status using the "Proxy" column checkbox.


Profile Storage:

Profiles are saved in the profiles directory as gologin_<profile_id>.
Profile data is stored in profiles.csv for persistence.



Example Workflow

Place token.txt with your GoLogin token next to the .exe or in the source root.
Launch the tool (via .exe or python main.py).
Set "Number of profiles" to 5, select "us" proxy, check "Run in Headless Mode", and set "Timeout" to 3.
Click "Create Profile(s)" to generate 5 profiles.
Double-click a profile ID to launch it in Orbita Browser (headless or visible).
Edit "Note" or toggle proxy as needed.

Creating the Executable
To build your own .exe (for developers):

Install PyInstaller:pip install pyinstaller


Run:pyinstaller --onefile --windowed main.py


Find the .exe in the dist folder.
Ensure token.txt, profiles, and browsers are in the same directory as the .exe when distributing.

Troubleshooting

Orbita Browser Download Fails:
Ensure internet access and check https://orbita-browser-windows.gologin.com/orbita-browser-latest.zip.
Verify write permissions in the browsers directory.


API Token Errors:
Confirm the token in token.txt or GUI is valid and not expired.


Profile Launch Fails:
Check that the Chrome version in the table matches the Orbita Browser version.
Ensure the profile folder (profiles/gologin_<profile_id>) exists.


Proxy Issues:
Verify custom proxy format (IP:Port:User:Pass).
Test proxy functionality independently.


Headless Mode Issues:
Confirm "Run in Headless Mode" setting matches desired behavior.
Close conflicting browser instances.


Timeout Issues:
Increase timeout (e.g., to 5 seconds) if profiles fail to initialize.



Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a branch (git checkout -b feature/your-feature).
Commit changes (git commit -m "Add your feature").
Push (git push origin feature/your-feature).
Open a Pull Request.

Ensure code follows style guidelines and includes tests.
License
This project is licensed under the MIT License. See the LICENSE file.
Acknowledgments

Built with PyQt5 for the GUI.
Uses GoLogin API for profile creation.
Powered by Orbita Browser.

Contact
For issues or suggestions, open an issue on the GitHub repository.

Note: Replace yourusername with your GitHub username before publishing.

