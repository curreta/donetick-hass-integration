
# Donetick Home Assistant Integration (Fork)

> **This is a proof-of-concept fork.** It adds per-chore sensor entities that expose task metadata (ID, assignee, due date, priority, etc.) as state attributes. This makes it possible to build custom dashboard cards that call the `donetick.*` services directly — enabling richer chore management UIs beyond what the built-in todo platform supports. See the `examples/` directory for sample dashboard cards and scripts.

---



A Home Assistant integration for Donetick that provides support for managing todo lists and controlling "things" as Home Assistant entities.

> [!WARNING]  
> This version of the integration requires Donetick server version **0.1.53** or greater.

## Features

### 📋 Todo Lists
- **Multiple Todo Lists**: "All Tasks" view and individual assignee-specific lists
- **Task Management**: Create, update, delete, and complete tasks
- **Task attributes**: Task descriptions, due dates can be managed in Home Assistant


### 🔧 Things Integration  
- **Sync things**: Control Donetick "things" as Home Assistant entities
- **Multiple Entity Types**: 
  - **Switch**: Boolean things (true/false)
  - **Number**: Numeric things with increment/decrement
  - **Text**: Text input things

### 🔧 Services
- `donetick.create_task` - Create new tasks
- `donetick.update_task` - Update existing tasks  
- `donetick.delete_task` - Delete tasks
- `donetick.complete_task` - Mark tasks complete with user attribution

## Installation

### Via HACS
1. Open HACS in Home Assistant
2. Navigate to Integrations  
3. Click "⋮" → "Custom repositories"
4. Add repository: `https://github.com/donetick/donetick-hass-integration/`
5. Category: Integration
6. Search for "Donetick" and install
7. Restart Home Assistant

## Configuration

Configure via **Settings** → **Devices & Services** → **Add Integration** → **Donetick**

**Required:**
- **Server URL**: 
  - Cloud: `https://api.donetick.com`
  - Self-hosted: `http://your-host:2021` (or your port)
- **API Token**: Generate from Donetick user settings

**Optional:**
- **Show Due In**: Days ahead to display upcoming tasks (default: 7)
- **Create Unified List**: Enable "All Tasks" todo list (default: true)  
- **Create Assignee Lists**: Individual todo lists per user (default: false) 
