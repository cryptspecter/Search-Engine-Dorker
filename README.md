# Advanced Search Engine Dorker Tool

An intuitive, powerful, and fully customizable web-based GUI to organize, manage, and execute search engine dorks for security research, OSINT, and bug bounty hunting.

This tool is a single, self-contained web page that runs entirely in your browser. On its first run, it fetches a default set of dorks to get you started. From that moment on, the entire collection is saved in your browser's local storage, making it your own personal, editable, and persistent dork library.

---

## Key Features

* **Your Personal Dork Library**: A default dork set is loaded from GitHub on first use and then cached in your browser. After that, it's all yours—edit, delete, and add dorks to build your custom collection.
* **Fully Persistent**: All changes, including edits, deletions, and favorites, are saved locally in your browser. Your personalized dork set will be waiting for you every time you open the tool.
* **Dynamic Inputs**: Dorks use placeholders like `$target.com$` and `$keyword$` to prompt you for input, making them highly reusable and versatile.
* **Powerful Search & Filtering**: Instantly search across all dorks or filter by collection to find the exact query you need in seconds.
* **Pop-up Blocker Proof**: The "Run Category" feature generates a list of clickable URLs, allowing you to open multiple tabs without being blocked by your browser.
* **Full Data Management**:
    * **Import/Export**: Back up your personal dork collection to a JSON file or import a completely new collection from a file.
    * **Reset to Default**: Easily revert your collection back to the original default set fetched from GitHub.
    * **Clear All**: Wipe the entire collection to start from a blank slate.
* **Zero Dependencies**: Runs entirely client-side. No server or setup is needed. Just visit the web page.
* **Clean & Responsive UI**: A modern, dark-themed interface that works smoothly on both desktop and mobile devices.

---

## How to Use

1.  **Access the Tool**: Open your browser and go to:
    [https://0bl1vyx.github.io/Search-Engine-Dorker/](https://0bl1vyx.github.io/Search-Engine-Dorker/)

2.  **Start Dorking**: On your first visit, the tool will automatically load the default dork set. You can immediately start running dorks, editing them, or adding your own. Your personalized collection is automatically saved in your browser.

---

## Customizing Your Dork Collection

You don't need to edit any code to customize your dork list. All customization is done directly through the tool's interface.

The best way to load a completely custom set of dorks is by using the **Import** feature.

1.  **Create Your JSON File**: First, create a `dorks.json` file containing your custom collections and dorks. Follow the detailed instructions in the **Master Dork File Guide** to ensure your file is structured correctly.
2.  **Clear Existing Dorks (Optional)**: If you want to start fresh, click the **Settings** icon in the tool and choose **Clear All Dorks**. This will give you a blank slate.
3.  **Import Your File**: In the **Settings** menu, click **Import from File** and select the `dorks.json` file you created. Your custom collection will instantly load and is ready to use.

---

## Disclaimer

This tool is intended for educational and ethical security research purposes only. The creator is not responsible for any misuse of this tool. Users are solely responsible for their actions and must comply with all applicable laws. Do not use this tool for any illegal activities.

---

## Contributing

Contributions, bug reports, and suggestions are welcome! Feel free to open an issue or submit a pull request if you have ideas for improvements or new features.

---

## License

This project is licensed under the MIT License.
