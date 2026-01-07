# MCP Toolkit (Docker) + Claude Desktop  
### DuckDuckGo MCP + Obsidian MCP (End-to-End Guide)

This repository documents how to use the **latest MCP Toolkit via Docker**, add **DuckDuckGo** and **Obsidian MCP tools**, and connect them to **Claude Desktop**.

This follows the **actual working flow using the Docker UI**, not config files or CLI hacks.

---

## Overview

This setup enables Claude to act as a real execution agent:

- MCP Toolkit runs inside Docker
- Tools are added via Docker UI
- Obsidian is authenticated using an API key
- Claude Desktop connects as a client
- Claude automatically invokes tools based on your prompt

### Example Prompt

> Find the top 10 Kerala restaurants in Bangalore using DuckDuckGo and create a note in my Obsidian vault.

Claude will:
- Search using DuckDuckGo MCP
- Reason over the results
- Create a Markdown note using Obsidian MCP

---



## Prerequisites

- Docker Desktop (latest)
- MCP Toolkit Docker Extension
- Claude Desktop (with MCP support enabled)
- Obsidian installed
- Obsidian **Local REST API** plugin enabled
- Obsidian API Key

---

## Step 1: Enable MCP Toolkit in Docker

1. Open **Docker Desktop**
2. Go to **Extensions**
3. Install and enable **MCP Toolkit**
4. Open the MCP Toolkit extension

This starts the MCP runtime inside Docker.

---

## Step 2: Add MCP Tools (DuckDuckGo + Obsidian)

Inside **MCP Toolkit (Docker UI)**:

1. Open the **Tools** tab
2. Click **Add Tool**
3. Add **DuckDuckGo MCP**
4. Add **Obsidian MCP**

At this stage, Obsidian is added but not authenticated.

---

## Step 3: Configure Obsidian MCP (API Key)

### In Obsidian

1. Open **Settings → Community Plugins**
2. Enable **Local REST API**
3. Copy the generated **API Key**

### In Docker MCP Toolkit

1. Open **Obsidian MCP tool settings**
2. Paste the Obsidian API Key
3. Save the configuration

This allows MCP to read and write notes in your vault.

---

## Step 4: Connect MCP Toolkit to Claude Desktop

1. Open **MCP Toolkit**
2. Go to the **Client** tab
3. Select **Claude Desktop**
4. Click **Connect**

Docker MCP Toolkit is now connected to Claude.

---

## Step 5: Verify Tools in Claude

1. Open **Claude Desktop**
2. Go to **Settings → Tools / MCP**
3. Confirm the following tools are visible:
   - DuckDuckGo
   - Obsidian

If they appear, the connection is successful.

---

## Step 6: Run a Full Workflow Prompt

In Claude Desktop, run:


Claude will automatically:
- Invoke DuckDuckGo MCP for search
- Process and summarize results
- Invoke Obsidian MCP
- Create a Markdown note in your vault

No manual tool selection is required.

---

## Step 7: Verify in Obsidian

Open your Obsidian vault.

You should see a newly created note containing:
- Restaurant names
- Locations
- Short descriptions

The file is created directly by MCP via Docker.

---

## Screenshots

Add screenshots in this order for clarity:

1. Docker Extensions → MCP Toolkit enabled  
<img width="885" height="703" alt="Screenshot 2026-01-07 at 11 28 08 PM" src="https://github.com/user-attachments/assets/e0839f69-c677-4f7c-8704-9baa090cc925" />


2. MCP Toolkit → Tools tab (DuckDuckGo + Obsidian added)  
<img width="845" height="367" alt="Screenshot 2026-01-07 at 11 22 30 PM" src="https://github.com/user-attachments/assets/b17ce0cd-2be9-42bc-a074-dec392fdf569" />


3. Claude Desktop → Available MCP tools visible  
<img width="319" height="167" alt="Screenshot 2026-01-07 at 11 23 25 PM" src="https://github.com/user-attachments/assets/de3f72b4-2137-4900-9d32-d4cf4fa724c4" />

4. Claude Desktop → Prompt and Response
<img width="785" height="840" alt="Screenshot 2026-01-07 at 10 38 25 PM" src="https://github.com/user-attachments/assets/2bc46cae-9bda-497e-ad31-1af5766b3b66" />

5. Obsidian vault → Note created by MCP  
<img width="944" height="1048" alt="Screenshot 2026-01-07 at 10 50 41 PM" src="https://github.com/user-attachments/assets/63f78df0-18f1-47ae-b20f-675007f5b7f9" />


---

## Why This Setup Is Powerful

- Docker isolates the MCP runtime
- Tools are explicitly managed
- Claude acts as the decision layer
- Obsidian remains local-first
- No brittle plugins or automations

This turns Claude into a **real execution agent**, not just a chat UI.

---


## Notes

- Obsidian API key is mandatory
- Tools must be added before connecting Claude
- MCP Toolkit Docker extension must remain running

---

## License

MIT

