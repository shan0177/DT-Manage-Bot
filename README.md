<div align="center">
  <img src="https://i.imgur.com/U4130A9.png" alt="Bot Logo Banner" width="800"/>
  <h1>🤖 Telegram Channel Manager & Gatekeeper Bot 🤖</h1>
  <p>
    A powerful, all-in-one Python bot for automating Telegram channel access, managing members, and providing a full suite of admin tools through a secure web dashboard.
  </p>
  
  <p>
    <img alt="Python Version" src="https://img.shields.io/badge/python-3.11+-blue.svg?style=for-the-badge&logo=python&logoColor=white">
    <img alt="License" src="https://img.shields.io/badge/license-MIT-green.svg?style=for-the-badge">
  </p>
</div>

<p align="center">
  <em>A demonstration of a user getting an invite and the admin viewing stats on the web dashboard.</em><br>
  <img src="https://i.imgur.com/g8e1g8O.gif" alt="Bot Demo GIF" width="700"/>
</p>

---

## 🌟 About The Project

Tired of manually approving users, dealing with spammers, and watching your private invite links get shared publicly? This bot is the definitive solution, designed to be a comprehensive gatekeeper and administrative assistant for your Telegram communities.

The core principle is **secure, automated access**. Instead of giving users a direct invite, the bot requires them to pass through a verification step using a shortlink. This single feature prevents unauthorized access, stops link sharing, and gives you full control over who joins your channels.

But it doesn't stop there. For administrators, this bot is a complete control panel. You get a massive suite of commands and a **password-protected web dashboard** to:
* 📊 View deep, real-time statistics on user activity.
* 🗂️ Browse all of the bot's files and data directly from your web browser.
* 📢 Broadcast messages to your entire user base.
* 🗓️ Schedule daily content to keep your community engaged.
* 🛡️ Automate member removal based on custom timers, with exceptions for VIPs.

Built with a robust architecture using Python, `python-telegram-bot`, and MongoDB for persistent data backup, this bot is the ultimate tool for serious community managers.

---

## ✨ Key Features

<table width="100%">
  <tr>
    <td width="50%" valign="top">
      <h3>👤 For Your Users</h3>
      <ul>
        <li>✅ **Simple & Interactive:** An easy-to-use <code>/start</code> menu with buttons.</li>
        <li>🔗 **Secure Single-Use Links:** Generates unique, temporary invite links that can't be shared.</li>
        <li>🌐 **All-Access Pass:** A <code>/genall</code> feature to get links for all channels at once.</li>
        <li>🛡️ **Spam Protection:** Built-in cooldowns to prevent abuse.</li>
        <li>❓ **Help & Support:** Clear instructions with <code>/help</code> and a <code>/report</code> command for users.</li>
      </ul>
    </td>
    <td width="50%" valign="top">
      <h3>🛠️ For Administrators</h3>
      <ul>
        <li>👑 **Full Control:** A massive set of Telegram commands for every aspect of management.</li>
        <li>💻 **Web Dashboard:** A secure, password-protected web panel for stats and file Browse.</li>
        <li>📢 **Broadcasting:** Send messages to every user who has ever started the bot.</li>
        <li>🗓️ **Content Scheduling:** Automate daily posts with the powerful scheduler.</li>
        <li>⚙️ **Automated Moderation:** Automatically remove inactive members after a configurable time.</li>
      </ul>
    </td>
  </tr>
</table>

<details>
  <summary><strong>👑 Click to see the Full List of Admin Commands</strong></summary>
  
  #### 👥 Community & Member Management
  - `/add_channel`: Add a new channel for the bot to manage.
  - `/remove_channel`: Remove a managed channel.
  - `/remove`: Kick all non-admin members on a channel's manual list.
  - `/rem`: Permanently ban a specific user from a channel.
  - `/add_exception`: Grant a user temporary immunity from auto-removal.
  - `/list_ids`, `/add_id`, `/del_id`: Manage the manual user lists for a channel.
  
  #### 📢 Content & Broadcasting
  - `/broadcast`: Reply to a message to send it to all users (copy or forward).
  - `/setschedule`: Schedule a daily message broadcast at a specific time (IST).
  - `/view_schedules`: View all active scheduled messages.
  - `/remove_schedule`: Delete a scheduled message.

  #### ⚙️ Bot & Data Control
  - `/astart`: Get a full, detailed list of all available admin commands.
  - `/stats`: Get a quick statistical overview directly in Telegram.
  - `/refresh`: Force the bot to reload all data from local files & MongoDB.
  - `/pull_json`: Download bot configuration files (`schedules`, `manual_lists`, etc.).
  - `/add_json`: Upload/replace a configuration file by replying to it.
  - `/pull_log`: Get the bot's live `bot.log` file.
  - `/clearlogs`: Clear and restart the bot's local log file.

  #### 🔗 Invite & Feature Toggles
  - `/invite`, `/ir`: Create and revoke powerful custom invite links.
  - `/revokeall`: Instantly revoke all temporary links created by the bot.
  - `/allow`, `/disable`: Turn the main invite generation feature on or off for users.
  - `/allowgenall`, `/disablegenall`: Toggle the "Get All Links" feature.

</details>

---

## 💻 The Admin Web Dashboard

This bot includes a powerful, built-in web dashboard, giving you unparalleled insight and control.

* **Secure Access:** The entire admin area is protected by a password you set.
* **Live Statistics:** View a beautiful, animated dashboard with overall bot stats and detailed per-channel activity.
* **Full File Access:** Includes a complete file explorer to browse and view any file in the bot's directory (`.py` code, `.json` data, `.html` templates, etc.) with full syntax highlighting.

<div align="center">
  <p><em>Main Dashboard View</em></p>
  <img src="https://i.imgur.com/lJ7wYV5.png" alt="Admin Dashboard Screenshot" width="700"/>
  <br><br>
  <p><em>Interactive File Explorer</em></p>
  <img src="https://i.imgur.com/yD8vP3Q.png" alt="File Explorer Screenshot" width="700"/>
</div>

---

## 🚀 Getting Started

Follow these steps to get your bot up and running.

### 1. Prerequisites
* Python 3.10 or higher
* A Telegram Bot Token from [@BotFather](https://t.me/BotFather)
* A free MongoDB Atlas account for database hosting

### 2. Installation
1.  **Clone the Repository:**
    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2.  **Install Dependencies:**
    This will install all the required Python libraries.
    ```bash
    pip install -r requirements.txt
    ```

3.  **Configure Your Bot:**
    * Create a file named `.env` in the project's root directory.
    * Copy the variables from the configuration table below and fill in your own values.

4.  **Run the Bot:**
    You're all set! Start the bot with this command.
    ```bash
    python main.py
    ```

---

<details>
  <summary><strong>⚙️ Click to see the Full `.env` Configuration Guide</strong></summary>
  
  | Variable                        | Description                                                                                             | Required? | Default Value |
  | ------------------------------- | ------------------------------------------------------------------------------------------------------- | :-------: | :-----------: |
  | `BOT_TOKEN`                     | The API token for your bot from Telegram's @BotFather.                                                    |    ✅     |      N/A      |
  | `BOT_USERNAME`                  | Your bot's username without the '@'.                                                                      |    ✅     |      N/A      |
  | `ADMIN_CHAT_ID`                 | Your numeric Telegram ID. For multiple admins, separate with a comma.                                     |    ✅     |      N/A      |
  | `MONGO_URI`                     | The full connection string for your MongoDB Atlas cluster.                                                |    ✅     |      N/A      |
  | `MONGO_DB_NAME`                 | The name of the database to use within your MongoDB cluster.                                              |    ✅     |      N/A      |
  | `WEB_ADMIN_PASSWORD`            | The password you will use to log in to the web admin dashboard.                                           |    ✅     |      N/A      |
  | `SECRET_KEY`                    | A long, random string used to secure web sessions.                                                        |    ✅     |      N/A      |
  | `LOGS_CHANNEL`                  | The numeric ID of the private channel where the bot sends general logs, reports, and errors.              |    ✅     |      N/A      |
  | `DATABASE_CHANNEL_ID`           | (Optional) ID of a channel for more detailed logs (joins, kicks, etc.).                                   |    ❌     |     None      |
  | `URL`                           | (Optional) The public URL of your bot, used for keep-alive pings on platforms like Koyeb.                 |    ❌     |     None      |
  | `PORT`                          | (Optional) The port for the web server.                                                                   |    ❌     |     `8000`    |
  | `SHORTLINK_API_KEY`             | (Optional) API key for your shortlink service. If blank, links won't be shortened.                        |    ❌     |     None      |
  | `AUTO_REMOVAL_DURATION_SECONDS` | (Optional) How long a member stays before being auto-removed (in seconds).                                |    ❌     |    `86400`    |
  | `USER_COOLDOWN_SECONDS`         | (Optional) Cooldown time for non-admin users to prevent spam.                                             |    ❌     |      `5`      |
  | `REMOVAL_DELAY`                 | (Optional) Delay in seconds between kick actions to avoid API limits.                                     |    ❌     |     `1.0`     |
  | `MAX_RETRIES`                   | (Optional) Max number of retries for failed Telegram API calls.                                           |    ❌     |      `3`      |
</details>

---

### 📜 License

This project is distributed under the MIT License. See `LICENSE` for more information.
