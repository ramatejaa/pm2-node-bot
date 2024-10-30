# Steps to Set Up and Connect a BOT with "pm2" for Automatic Startup

### 1. Install the "pm2" Package Globally
   - Open the terminal in Visual Studio Code (or any terminal).
   - Install `pm2` globally using npm:

     ```bash
     npm install -g pm2
     ```

### 2. Find the Global `node_modules` Folder Location
   - To locate the global `node_modules` directory, run the following command in the terminal:

     ```bash
     npm root -g
     ```

   - You should see a path like this in the output:
     ```
     C:\Users\YourUsername\AppData\Roaming\npm
     ```

### 3. Add the Global npm Folder to the System PATH
   - This allows you to run `pm2` from anywhere in the terminal. Follow these steps:
     1. Search for **Environment Variables** in Windows search and open it.
     2. In the **System Properties** window, click **Environment Variables**.
     3. In the **System variables** section, select **Path** and click **Edit**.
     4. Click **New** and paste the npm path you found earlier (e.g., `C:\Users\YourUsername\AppData\Roaming\npm`).
     5. Click **OK** to save the changes.

### 4. Set Execution Policy for PowerShell
   - Open PowerShell as Administrator:
     - Right-click on PowerShell and select **Run as administrator**.
   - In PowerShell, run the following command to allow scripts to execute:

     ```powershell
     Set-ExecutionPolicy RemoteSigned
     ```

   - Confirm by typing `Y` and pressing Enter.

### 5. Verify the pm2 Installation
   - After adding the npm path and setting the execution policy, verify the `pm2` installation by checking its version. In the terminal, type:

     ```bash
     pm2 --version
     ```

   - If the installation was successful, this should display the version of `pm2`.

### Advantages of Using "pm2" for Bot Management
1. **Automatic Startup on Reboot**:
   - Use `pm2 startup` to configure the bot to start automatically after the computer reboots.
   - Save the current PM2 process list with `pm2 save` to ensure they are resurrected on reboot.

2. **Process Management**:
   - Use `pm2 list` to check the status of your bot and other processes managed by PM2.
   - View logs for troubleshooting with `pm2 logs myBot`.

