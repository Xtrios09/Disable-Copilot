---

# 🪟 Disable Windows Copilot & Bing Integration

This project provides a simple **Windows Registry (.reg)** script that disables **Windows Copilot**, **Edge sidebar (HubsSidebar)**, and **Bing search suggestions** in Windows Search.

It’s ideal for users or IT administrators who prefer a cleaner, distraction-free Windows environment without Microsoft Copilot or Bing-powered suggestions.

---

## 📋 Features

* 🚫 **Disable Windows Copilot**

  * Prevents Windows Copilot from running for both **current user** and **all users (system-wide)**.
* 🧭 **Disable Microsoft Edge Sidebar**

  * Removes the Edge sidebar ("Hubs Sidebar") which includes Copilot integration.
* 🔍 **Disable Bing Search Suggestions**

  * Removes Bing-powered results from the Windows search box.

---

## 🧠 How It Works

This script modifies specific Windows Registry keys under both:

* `HKEY_CURRENT_USER` (affecting the logged-in user)
* `HKEY_LOCAL_MACHINE` (affecting all users on the system)

### Registry Changes

```reg
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows\WindowsCopilot]
"TurnOffWindowsCopilot"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsCopilot]
"TurnOffWindowsCopilot"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge]
"HubsSidebarEnabled"=dword:00000000

[HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows\Explorer]
"DisableSearchBoxSuggestions"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\Explorer]
"DisableSearchBoxSuggestions"=dword:00000001
```

---

## ⚙️ Usage

1. Download the `.reg` file from this repository.
2. Double-click the file to apply the changes.
3. When prompted by Windows, click **Yes** to confirm adding the keys to the registry.
4. Restart your PC (or log out and back in) for the changes to take effect.

---

## 🔄 Reverting Changes

If you want to **re-enable Copilot** or **restore Bing search suggestions**, you can:

* Manually delete the registry keys above, or
* Set all DWORD values back to `0` instead of `1`.

---

## ⚠️ Disclaimer

> **Use at your own risk.**
> Modifying the Windows Registry can impact system behavior. Always create a **System Restore Point** or **Registry Backup** before applying any changes.

---

## 🧑‍💻 Author

📦 GitHub: [@Xtrios09](https://github.com/Xtrios09)

---
