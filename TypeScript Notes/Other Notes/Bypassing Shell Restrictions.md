---
tags:
  - ChatGPT
---
The issue occurs because PowerShell's execution policy is set to restrict running scripts unless they are digitally signed. This is a security feature of PowerShell, and it can be adjusted to allow running scripts like `tsc.ps1`.

Here’s how you can resolve this:

---

### **Option 1: Bypass Execution Policy Temporarily**
1. Use the following command to run the `tsc` command without permanently changing the execution policy:
   ```bash
   powershell -ExecutionPolicy Bypass -Command "tsc --init"
   ```

---

### **Option 2: Change Execution Policy for Your Session**
1. Temporarily set the execution policy to bypass for the current session:
   ```bash
   Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
   ```
2. Run your `tsc` command:
   ```bash
   tsc --init
   ```
3. This change will only last for the current PowerShell session.

---

### **Option 3: Update Execution Policy Globally**
If you want to permanently allow scripts to run, you can change the execution policy for the current user:
1. Open PowerShell as an Administrator.
2. Run this command to set the policy:
   ```bash
   Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
   ```
3. Confirm the change by typing `Y` when prompted.
4. Retry the `tsc --init` command.

---

### **Why This Happens**
The `tsc.ps1` script is part of the global npm installation. By default, PowerShell requires scripts to be signed for security. Adjusting the execution policy resolves this.

---

If you're still facing issues, let me know, and we can debug further!