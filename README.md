# Gologin_Profile_Manager
Create GoLogin profiles offline, GoLogin profiles locally Gologin profile tool offline, Gologin Antidetect browser offline management, Multi-account management offline
Usage

Launch the Application:
Run This Tool to start the GUI.
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



Ensure "Run in Headless Mode" is checked for headless operation, or uncheck for visible mode.



Set "Timeout" to 3 seconds.



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

