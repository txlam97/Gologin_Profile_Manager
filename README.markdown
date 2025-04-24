# GoLogin Profile Manager

GoLogin Profile Manager is a Windows GUI tool that automates the creation and management of browser profiles using the GoLogin API and Orbita Browser. It allows users to generate multiple profiles with randomized fingerprints, configure proxies, and launch profiles in headless or visible mode. The tool is available as a standalone executable (.exe) for easy use or as source code for developers.

## Features

- **Automated Profile Creation**: Generate multiple GoLogin profiles with randomized browser fingerprints.
- **Proxy Support**: Use free proxies (US/UK) or custom proxies (IP:Port:User:Pass).
- **Headless Mode**: Run profiles in headless or visible mode (default: headless, enabled via checkbox).
- **Timeout Configuration**: Set custom timeout for profile initialization (default: 2 seconds, adjustable via textbox).
- **Profile Management**: View, edit, and delete profiles in a user-friendly table interface.
- **Orbita Browser Integration**: Automatically downloads and manages the Orbita Browser executable.

## Usage
1. **Download the Latest Release**:
   - Visit the [[Releases]([https://github.com/txlam97/gologin-profile-manager/releases](https://github.com/txlam97/Gologin_Profile_Manager/releases/tag/1.0.0.1))](https://github.com/txlam97/Gologin_Profile_Manager/releases/tag/1.0.0.1) page on GitHub.
   - Download the GoLoginProfileCreator.zip then extract them   

2. **Run the Executable**:
   - Double-click the `.exe` file to launch the tool.
   - The tool will create a `browsers` folder in the same directory to download Orbita Browser if needed.
   
3. **Prepare GoLogin Token**:
   - Go to gologin.com, register any account to get API key.
   - Paste your GoLogin API token into textbox (or paste value API into a file named `token.txt` in the same directory as the `.exe`)

2. **Configure Settings**:
   - **GoLogin Token**: Verify or enter your API token in the "GoLogin Token" field.
   - **Number of Profiles**: Specify how many profiles to create (1–9999).
   - **Proxy Settings**:
     - Select a free proxy region (US, UK, or NONE) from the dropdown.
     - Or enter a custom proxy in the format `IP:Port:User:Pass`.
   - **Headless Mode**: Check/uncheck "Run in Headless Mode" (default: checked). Checked means profiles run in headless mode; unchecked means visible mode.
   - **Timeout**: Enter timeout duration in seconds (default: 2) in the "Timeout" textbox. This sets the delay between starting and stopping profiles during creation.

3. **Create Profiles**:
   - Click "Create Profile(s)" to generate profiles.
   - Progress is shown in the log window.
   - Profiles run in headless or visible mode based on the checkbox, with the specified timeout.

4. **Manage Profiles**:
   - View profiles in the table, showing:
     - ID, Proxy Region, Note, Profile Name, Profile ID, Proxy Status, Proxy Info, Chrome Version.
   - **Double-click** a profile’s ID to launch it in Orbita Browser.
   - **Edit** Note, Profile Name, Proxy Info, or Chrome Version in the table.
   - **Right-click** a profile to delete its folder and data.
   - Toggle proxy status using the "Proxy" column checkbox.

5. **Profile Storage**:
   - Profiles are saved in the `profiles` directory as `gologin_<profile_id>`.
   - Profile data is stored in `profiles.csv` for persistence.

## Example Workflow

1. Place `token.txt` with your GoLogin token next to the .exe or in the source root.
2. Launch the tool (via .exe or `python main.py`).
3. Set "Number of profiles" to 5, select "us" proxy, check "Run in Headless Mode", and set "Timeout" to 3.
4. Click "Create Profile(s)" to generate 5 profiles.
5. Double-click a profile ID to launch it in Orbita Browser (headless or visible).
6. Edit "Note" or toggle proxy as needed.

