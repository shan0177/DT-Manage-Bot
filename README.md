<div align="center">
  <h1>🤖 Telegram Channel Manager & Gatekeeper Bot 🤖</h1>
  <p>
    A powerful, all-in-one Python bot for automating Telegram channel access, managing members, and providing a full suite of admin tools through a secure web dashboard.
  </p>

  <p>
    <img alt="Python Version" src="https://img.shields.io/badge/python-3.11+-blue.svg?style=for-the-badge&logo=python&logoColor=white">
    <img alt="License" src="https://img.shields.io/badge/license-MIT-green.svg?style=for-the-badge">
  </p>
</div>

---

### 📚 Table of Contents
1. [About The Project](#-about-the-project)
2. [How It Works](#-how-it-works-the-user-journey)
3. [Key Features](#-key-features)
4. [The Admin Web Dashboard](#-the-admin-web-dashboard)
5. [Technology Stack](#-technology-stack)
6. [Getting Started](#-getting-started)
7. [Configuration Guide](#️-configuration-env-guide)

---

<details>
  <summary><h3>🌟 About The Project</h3></summary>

Tired of manually approving users, dealing with spammers, and watching your private invite links get shared publicly? This bot is the definitive solution, designed to be a comprehensive gatekeeper and administrative assistant for your Telegram communities.

The core principle is **secure, automated access**. Instead of giving users a direct invite, the bot requires them to pass through a verification step using a shortlink. This single feature prevents unauthorized access, stops link sharing, and gives you full control over who joins your channels.

But it doesn't stop there. For administrators, this bot is a complete control panel. You get a massive suite of commands and a **password-protected web dashboard** to:
* 📊 View deep, real-time statistics on user activity.
* 🗂️ Browse all of the bot's files and data directly from your web browser.
* 📢 Broadcast messages to your entire user base.
* 🗓️ Schedule daily content to keep your community engaged.
* 🛡️ Automate member removal based on custom timers, with exceptions for VIPs.

Built with a robust architecture using Python, `python-telegram-bot`, and MongoDB for persistent data backup, this bot is the ultimate tool for serious community managers.

</details>

<details>
  <summary><h3>👣 How It Works: The User Journey</h3></summary>

The bot creates a seamless and secure funnel for new users wanting to join your channels.

| Step | Action | Description |
| :--: | --- | --- |
| **1** | **User Starts Bot** | The user finds your bot and sends the `/start` command. |
| **2** | **Channel Selection** | The bot replies with an interactive menu of all your managed channels. |
| **3** | **Receives Shortlink** | Upon selecting a channel, the user is given a unique, protected shortlink. |
| **4** | **Verification** | The user must open the link and complete the required task (e.g., view an ad, solve a captcha). |
| **5** | **Redeems Key** | After verification, they receive a long, random key which they paste back into the bot chat. |
| **6** | **Gets Invite Link** | The bot verifies the key and finally provides the personal, single-use Telegram invite link. |
| **7** | **Timer Starts** | The moment the user joins the channel, the bot's internal auto-removal timer starts for them. |

</details>

<details>
  <summary><h3>✨ Key Features & Admin Commands</h3></summary>

<table width="100%">
  <tr>
    <td width="50%" valign="top">
      <h4>👤 For Your Users</h4>
      <ul>
        <li>✅ **Simple & Interactive:** An easy-to-use <code>/start</code> menu with buttons.</li>
        <li>🔗 **Secure Single-Use Links:** Generates unique, temporary invite links that can't be shared.</li>
        <li>🌐 **All-Access Pass:** A <code>/genall</code> feature to get links for all channels at once.</li>
        <li>🛡️ **Spam Protection:** Built-in cooldowns to prevent abuse.</li>
        <li>❓ **Help & Support:** Clear instructions with <code>/help</code> and a <code>/report</code> command for users.</li>
      </ul>
    </td>
    <td width="50%" valign="top">
      <h4>🛠️ For Administrators</h4>
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
  <summary><h4>👑 Click to see the Full List of Admin Commands</h4></summary>

  <h5>👥 Community & Member Management</h5>
  <ul>
    <li><code>/add_channel</code>: Add a new channel for the bot to manage.</li>
    <li><code>/remove_channel</code>: Remove a managed channel.</li>
    <li><code>/remove</code>: Kick all non-admin members on a channel's manual list.</li>
    <li><code>/rem</code>: Permanently ban a specific user from a channel.</li>
    <li><code>/add_exception</code>: Grant a user temporary immunity from auto-removal.</li>
    <li><code>/list_ids</code>, <code>/add_id</code>, <code>/del_id</code>: Manage the manual user lists for a channel.</li>
  </ul>

  <h5>📢 Content & Broadcasting</h5>
  <ul>
    <li><code>/broadcast</code>: Reply to a message to send it to all users (copy or forward).</li>
    <li><code>/setschedule</code>: Schedule a daily message broadcast at a specific time (IST).</li>
    <li><code>/view_schedules</code>: View all active scheduled messages.</li>
    <li><code>/remove_schedule</code>: Delete a scheduled message.</li>
  </ul>

  <h5>⚙️ Bot & Data Control</h5>
  <ul>
    <li><code>/astart</code>: Get a full, detailed list of all available admin commands.</li>
    <li><code>/stats</code>: Get a quick statistical overview directly in Telegram.</li>
    <li><code>/refresh</code>: Force the bot to reload all data from local files & MongoDB.</li>
    <li><code>/pull_json</code>: Download bot configuration files (<code>schedules</code>, <code>manual_lists</code>, etc.).</li>
    <li><code>/add_json</code>: Upload/replace a configuration file by replying to it.</li>
    <li><code>/pull_log</code>: Get the bot's live <code>bot.log</code> file.</li>
    <li><code>/clearlogs</code>: Clear and restart the bot's local log file.</li>
  </ul>

  <h5>🔗 Invite & Feature Toggles</h5>
  <ul>
    <li><code>/invite</code>, <code>/ir</code>: Create and revoke powerful custom invite links.</li>
    <li><code>/revokeall</code>: Instantly revoke all temporary links created by the bot.</li>
    <li><code>/allow</code>, <code>/disable</code>: Turn the main invite generation feature on or off for users.</li>
    <li><code>/allowgenall</code>, <code>/disablegenall</code>: Toggle the "Get All Links" feature.</li>
  </ul>

</details>
</details>

<details>
  <summary><h3>💻 The Admin Web Dashboard</h3></summary>

This bot includes a powerful, built-in web dashboard, giving you unparalleled insight and control.

* **Secure Access:** The entire admin area is protected by a password you set.
* **Live Statistics:** View a beautiful, animated dashboard with overall bot stats and detailed per-channel activity.
* **Full File Access:** Includes a complete file explorer to browse and view any file in the bot's directory (`.py` code, `.json` data, `.html` templates, etc.) with full syntax highlighting.

<div align="center">

<table>
  <tr>
    <td align="center">
      <p><em>Main Dashboard View (Overall Stats)</em></p>
      <img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEheoWbqtU5e3mGk65ysx6HvEbhYlltCxx8Jh4SFU9DAW-IKLCSxWvePzNLVpj04L8OYSV7jHs7vEd4E0d31Tax77119Myu4U83pp5BLkU6hZfbEbeP74AJ-cEuebpM1Ur9TT_nf_Vk6j2eKKXp1cTlCnRQQ7-85goTabZe5OY55yV2nROGqc1l1evD9EMM/s1920/Screenshot%202025-08-04%20225735.png" alt="Admin Dashboard Screenshot 1" width="300"/>
    </td>
    <td align="center">
      <p><em>Main Dashboard View (Channel Stats)</em></p>
      <img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgzTUlLjqcytPow8fnghQXmGhfZ_UdxxuQaLZ1Wi3tfYKnvnIJdHvnJmRVQDAx4n2SntKu7jolkatoaRvsrEFUueYbWZd5GEt4w4psXbWtJLbNJjmpyCvJkwbBGtJK5tzvxWgqopv-kqMUy_gqrBFGtsPXCBYOl8h03_BYafasI3how40k3rZBG_3RD0pA/s1920/Screenshot%202025-08-04%20225757.png" alt="Admin Dashboard Screenshot 2" width="300"/>
    </td>
    <td align="center">
      <p><em>Interactive File Explorer</em></p>
      <img src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh5X4e0_5inzFKP8AWmA2J_0yykEWFP1YojpLG1ewU5ifv3cfTvnAn8FadaNWnweo5Om3ZGz8NExtvfRvBaTJmyRE0XrLTINfeoGcBWq3HsbkF9Ung3sSKuKizKJJiwkwUSpghkBZm7neqMSqhcfDGGis1J6kW19_Da9Y03S6z0WbEFkmbEPRkmrmTTwoI/s1920/Screenshot%202025-08-04%20225819.png" alt="File Explorer Screenshot" width="300"/>
    </td>
  </tr>
</table>

</div>

</details>

<details>
  <summary><h3>🛠️ Technology Stack</h3></summary>

This bot is built with a modern, asynchronous stack for high performance.

* **Python 3.10+**: The core programming language.
* **python-telegram-bot**: One of the most powerful and popular libraries for interacting with the Telegram Bot API.
* **Quart**: An asynchronous web framework with a Flask-like API, used to serve the admin dashboard.
* **MongoDB**: A NoSQL database used as a persistent, cloud-based backup for all configuration files.
* **Motor**: The official asynchronous driver for using MongoDB with `asyncio`.
* **AIOFiles**: Used for asynchronous reading and writing of local JSON files.

</details>

<details>
  <summary><h3>🚀 Getting Started & Configuration</h3></summary>

### Prerequisites
* You must have Python 3.10 or newer installed.
* You will need a Telegram Bot Token from [@BotFather](https://t.me/BotFather).
* You will need a free MongoDB Atlas account for the database backup feature.

### Installation
1.  **Get the Code:**
    Clone this project to your local machine or server.
    ````bash
    git clone <repository_url>
    cd <repository_directory>
    ````

2.  **Install the Requirements:**
    This will install all the Python libraries the bot needs to run.
    ````bash
    pip install -r requirements.txt
    ````

3.  **Configure Your Bot:**
    * Create a new file named `.env` in the main folder.
    * Copy the variables from the configuration guide below and fill in your own secret keys and settings.

4.  **Launch the Bot:**
    You're all set! Start the bot with this command.
    ````bash
    python main.py
    ````
<br>

<details>
  <summary><h4>⚙️ Click to see the Full `.env` Configuration Guide</h4></summary>

  | Variable                        | Description                                                                                             | Required? | Default Value |
  | ------------------------------- | ------------------------------------------------------------------------------------------------------- | :-------: | :-----------: |
  | `API_ID`                        | (Optional) Your personal Telegram API ID from my.telegram.org.                                          |    ❌     |     None      |
  | `API_HASH`                      | (Optional) Your personal Telegram API Hash from my.telegram.org.                                        |    ❌     |     None      |
  | `BOT_TOKEN`                     | **(Required)** The API token for your bot from Telegram's @BotFather.                                     |    ✅     |      N/A      |
  | `BOT_USERNAME`                  | **(Required)** Your bot's username without the '@'.                                                       |    ✅     |      N/A      |
  | `ADMIN_CHAT_ID`                 | **(Required)** Your numeric Telegram ID. For multiple admins, separate with a comma.                      |    ✅     |      N/A      |
  | `MONGO_URI`                     | **(Required)** The full connection string for your MongoDB Atlas cluster.                                 |    ✅     |      N/A      |
  | `MONGO_DB_NAME`                 | **(Required)** The name of the database to use within your MongoDB cluster.                               |    ✅     |      N/A      |
  | `WEB_ADMIN_PASSWORD`            | **(Required)** The password you will use to log in to the web admin dashboard.                            |    ✅     |      N/A      |
  | `SECRET_KEY`                    | **(Required)** A long, random string used to secure web sessions.                                         |    ✅     |      N/A      |
  | `LOGS_CHANNEL`                  | **(Required)** The numeric ID of the private channel where the bot sends general logs, reports, and errors.              |    ✅     |      N/A      |
  | `DATABASE_CHANNEL_ID`           | (Optional) ID of a channel for more detailed logs (joins, kicks, etc.).                                   |    ❌     |     None      |
  | `URL`                           | (Optional) The public URL of your bot, used for keep-alive pings on platforms like Koyeb.                 |    ❌     |     None      |
  | `PORT`                          | (Optional) The port for the web server.                                                                   |    ❌     |     `8000`    |
  | `SHORTLINK_API_KEY`             | (Optional) API key for your shortlink service. If blank, links won't be shortened.                        |    ❌     |     None      |
  | `AUTO_REMOVAL_DURATION_SECONDS` | (Optional) How long a member stays before being auto-removed (in seconds).                                |    ❌     |    `86400`    |
  | `USER_COOLDOWN_SECONDS`         | (Optional) Cooldown time for non-admin users to prevent spam.                                             |    ❌     |      `5`      |
  | `REMOVAL_DELAY`                 | (Optional) Delay in seconds between kick actions to avoid API limits.                                     |    ❌     |     `1.0`     |
  | `MAX_RETRIES`                   | (Optional) Max number of retries for failed Telegram API calls.                                           |    ❌     |      `3`      |
</details>
</details>
