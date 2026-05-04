## Build and Run Playwright MCP Server locally
To build/run Playwright MCP Server in your local machine follow the below steps

### Step 1 : Clone Repository

```bash
git clone https://github.com/executeautomation/mcp-playwright.git
```

## Step 2: Install Dependencies
```bash
npm install
```

## Step 3: Build Code
```bash
npm run build
npm link
```

## Step 4: Configuring Playwright MCP in Claude Desktop 

Modify your `claude-desktop-config.json` file as shown below to work with local playwright mcp server

```json
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": [
        "--directory",
        "/your-playwright-mcp-server-clone-directory",
        "run",
        "@modelcontextprotocol/playwright-mcp-server"
      ]
    }
  }
}
```

## Step 5: Setting Environment Variables

To configure the browser executable path and user data directory path using environment variables, set the following variables in your environment:

```bash
export BROWSER_EXECUTABLE_PATH="/path/to/your/browser"
export BROWSER_USER_DATA_DIR="/path/to/your/user/data/dir"
```

## Step 6: Using a Configuration File

Alternatively, you can use a configuration file to set the browser executable path and user data directory path. Create a `config.json` file in your project directory with the following content:

```json
{
  "browserExecutablePath": "/path/to/your/browser",
  "userDataDir": "/path/to/your/user/data/dir"
}
```

Then, modify your `claude-desktop-config.json` file to include the path to the configuration file:

```json
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": [
        "--directory",
        "/your-playwright-mcp-server-clone-directory",
        "run",
        "@modelcontextprotocol/playwright-mcp-server",
        "--config",
        "/path/to/your/config.json"
      ]
    }
  }
}
```

## Reward
If your setup is all correct, you should see Playwright MCP Server pointing your local machine source code

![Playwright MCP Server](./img/mcp-server.png)
