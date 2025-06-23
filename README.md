# React Native Logs

**Professional CLI utility for React Native developers** — Start once and forget. Automatically connects to Metro bundler, handles disconnections, and provides persistent real-time log viewing with enhanced formatting.

[![npm version](https://badge.fury.io/js/react-native-logs.svg)](https://badge.fury.io/js/react-native-logs)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

![React Native Logs in action](assets/example.png)

## Why React Native Logs?

React Native development often involves juggling multiple terminal windows and losing important console output. This utility solves that by providing a dedicated, persistent log viewer that automatically connects to your Metro bundler and intelligently formats your debug output.

## Key Features

- **🚀 Set and Forget** — Start once, runs continuously with automatic reconnection
- **🔗 Seamless Integration** — Auto-discovers and connects to Metro bundler WebSocket
- **🎨 Enhanced Readability** — Color-coded log levels with clean stack trace filtering
- **💾 Persistent Logging** — Automatic log file generation with configurable retention
- **🤖 AI-Ready Output** — Clean, structured log format perfect for LLM debugging assistance
- **🔄 Zero Maintenance** — Handles Metro restarts and connection drops without intervention
- **⚙️ Developer-Friendly Configuration** — CLI arguments and environment variables support
- **⚡ Zero Dependencies** — Lightweight with minimal overhead

## Quick Start

```bash
# Install globally for immediate access
npm install -g react-native-logs
# or
yarn global add react-native-logs

# Start logging (works with any React Native project)
rn-logs
```

## Installation Options

```bash
# Global installation (recommended for development workflow)
npm install -g react-native-logs
# or
yarn global add react-native-logs

# Project-specific installation
npm install react-native-logs
# or
yarn add react-native-logs

# One-time usage without installation
npx react-native-logs
# or
yarn dlx react-native-logs
```

## Usage

### Basic Usage

```bash
# Connect to default Metro port (8081)
rn-logs

# Specify custom Metro port
rn-logs --port 8082

# Configure connection timeouts
rn-logs --timeout 10000 --reconnect 2000
```

### Advanced Configuration

```bash
# Maximum log file size management
rn-logs --max-lines 500

# Environment-based configuration
RN_LOGS_PORT=8082 RN_LOGS_TIMEOUT=15000 rn-logs

# Combined approach
rn-logs -p 8082 -t 10000 -r 2000 --max-lines 1000
```

## Configuration Reference

### CLI Arguments

| Option        | Short | Description                    | Default |
| ------------- | ----- | ------------------------------ | ------- |
| `--port`      | `-p`  | Metro bundler port             | `8081`  |
| `--timeout`   | `-t`  | Connection timeout (ms)        | `5000`  |
| `--reconnect` | `-r`  | Reconnection delay (ms)        | `3000`  |
| `--retry`     |       | Retry delay after failure (ms) | `5000`  |
| `--max-lines` | `-m`  | Log file line limit            | `100`   |
| `--help`      | `-h`  | Show help information          |         |
| `--version`   | `-v`  | Display version                |         |

### Environment Variables

| Variable            | Description             | Default |
| ------------------- | ----------------------- | ------- |
| `RN_LOGS_PORT`      | Metro bundler port      | `8081`  |
| `RN_LOGS_TIMEOUT`   | Connection timeout (ms) | `5000`  |
| `RN_LOGS_RECONNECT` | Reconnection delay (ms) | `3000`  |
| `RN_LOGS_RETRY`     | Retry delay (ms)        | `5000`  |
| `RN_LOGS_MAX_LINES` | Log file line limit     | `100`   |

## Integration Workflows

### Log Files

- **Location**: `./logs/metro.log` (relative to working directory)
- **Format**: Plain text with timestamps and log levels — perfect for LLM analysis
- **AI-Friendly**: Clean, structured format ideal for debugging with AI assistants
- **Rotation**: Automatic truncation based on `--max-lines` setting
- **Persistence**: Survives Metro restarts and connection drops

### Console Output

- **Color Coding**: Different colors for INFO, WARN, ERROR, DEBUG levels
- **Timestamps**: Local time for each log entry
- **Stack Traces**: Cleaned and filtered for relevance

## License

MIT © [noma4i](https://github.com/noma4i)
