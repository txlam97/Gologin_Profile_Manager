# GoLogin Profile Creator

GoLogin Profile Creator is a Windows GUI tool that automates the creation and management of browser profiles using the GoLogin API and Orbita Browser. It allows users to generate multiple profiles with randomized fingerprints, configure proxies, and launch profiles in headless or visible mode. The tool is available as a standalone executable (.exe) for easy use or as source code for developers.

## Features

- **Automated Profile Creation**: Generate multiple GoLogin profiles with randomized browser fingerprints.
- **Proxy Support**: Use free proxies (US/UK) or custom proxies (IP:Port:User:Pass).
- **Headless Mode**: Run profiles in headless or visible mode (default: headless, enabled via checkbox).
- **Timeout Configuration**: Set custom timeout for profile initialization (default: 2 seconds, adjustable via textbox).
- **Profile Management**: View, edit, and delete profiles in a user-friendly table interface.
- **Orbita Browser Integration**: Automatically downloads and manages the Orbita Browser executable.

## Prerequisites

To use the .exe or source code, ensure the following:

- **Windows OS**: The tool is designed for Windows due to Orbita Browser compatibility.
- **GoLogin API Token**: Obtain a token from your [GoLogin account](https://app.gologin.com/).
- **Internet Connection**: Required for downloading Orbita Browser and making API calls.
- **For Source Code Users**:
  - Python 3.8+.
  - Dependencies listed in `requirements.txt`.

## Installation

### Option 1: Using the Executable (.exe)

1. **Download the Latest Release**:
   - Visit the [Releases](https://github.com/yourusername/gologin-profile-creator/releases) page on GitHub.
   - Download the latest `.exe` file (e.g., `GoLoginProfileCreator-vX.X.X.exe`).

2. **Run the Executable**:
   - Double-click the `.exe` file to launch the tool.
   - The tool will create a `browsers` folder in the same directory to download Orbita Browser if needed.

3. **Prepare GoLogin Token**:
   - Create a file named `token.txt` in the same directory as the `.exe`.
   - Paste your GoLogin API token into `token.txt`.

### Option 2: Using the Source Code

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/gologin-profile-creator.git
   cd gologin-profile-creator
   ```

2. **Install Dependencies**:
   Create a virtual environment (recommended) and install required packages:
   ```bash
   python -m venv venv
   source venv/Scripts/activate  # On Windows
   pip install -r requirements.txt
   ```

3. **Prepare GoLogin Token**:
   - Create a `token.txt` file in the project root.
   - Paste your GoLogin API token into `token.txt`.

4. **Run the Tool**:
   ```bash
   python main.py
   ```

## Usage

1. **Launch the Tool**:
   - For .exe: Double-click the `.exe` file.
   - For source: Run `python main.py`.
   - The tool will download Orbita Browser to the `browsers` directory if not present.

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

## Creating the Executable

To build your own .exe (for developers):

1. Install `PyInstaller`:
   ```bash
   pip install pyinstaller
   ```

2. Run:
   ```bash
   pyinstaller --onefile --windowed main.py
   ```

3. Find the .exe in the `dist` folder.
4. Ensure `token.txt`, `profiles`, and `browsers` are in the same directory as the .exe when distributing.

## Troubleshooting

- **Orbita Browser Download Fails**:
  - Ensure internet access and check `https://orbita-browser-windows.gologin.com/orbita-browser-latest.zip`.
  - Verify write permissions in the `browsers` directory.
- **API Token Errors**:
  - Confirm the token in `token.txt` or GUI is valid and not expired.
- **Profile Launch Fails**:
  - Check that the Chrome version in the table matches the Orbita Browser version.
  - Ensure the profile folder (`profiles/gologin_<profile_id>`) exists.
- **Proxy Issues**:
  - Verify custom proxy format (`IP:Port:User:Pass`).
  - Test proxy functionality independently.
- **Headless Mode Issues**:
  - Confirm "Run in Headless Mode" setting matches desired behavior.
  - Close conflicting browser instances.
- **Timeout Issues**:
  - Increase timeout (e.g., to 5 seconds) if profiles fail to initialize.

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a branch (`git checkout -b feature/your-feature`).
3. Commit changes (`git commit -m "Add your feature"`).
4. Push (`git push origin feature/your-feature`).
5. Open a Pull Request.

Ensure code follows style guidelines and includes tests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file.

## Acknowledgments

- Built with [PyQt5](https://www.riverbankcomputing.com/software/pyqt/).
- Uses [GoLogin API](https://gologin.com/).
- Powered by [Orbita Browser](https://gologin.com/orbita-browser).

## Contact

For issues or suggestions, open an issue on the [GitHub repository](https://github.com/yourusername/gologin-profile-creator/issues).

---
*Note*: Replace `yourusername` with your GitHub username before publishing.