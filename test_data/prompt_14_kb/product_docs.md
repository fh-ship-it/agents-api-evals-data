# TaskFlow Product Documentation

## Getting Started

### Creating Your Account

1. Visit [taskflow.io/signup](https://taskflow.io/signup)
2. Enter your work email and choose a password
3. Verify your email address
4. Choose your plan (or start a 14-day free trial)
5. Set up your workspace name and invite team members

### Your First Project

After creating your workspace, click the **+** button in the sidebar to create your first project. You can:

- **Start from scratch**: An empty project with default task statuses
- **Use a template**: Choose from Marketing Campaign, Software Sprint, Product Launch, Event Planning, or Content Calendar
- **Import**: Bring in existing data from Trello, Asana, Jira, Monday.com, or CSV

### Navigation

The main interface consists of:

- **Sidebar**: Access workspaces, projects, favorites, and settings
- **Main view**: Your current project view (Board, List, Gantt, Calendar, or Timeline)
- **Task detail panel**: Opens when clicking any task, showing full details, comments, and activity

## Projects

### Project Structure

Each project contains:

- **Task groups** (also called sections or columns, depending on your view)
- **Tasks** within each group
- **Custom fields** for additional data points
- **Views** (Board, List, Gantt, Calendar, Timeline)

### Project Settings

Access via the gear icon in the project header:

- **General**: Name, description, color, icon
- **Statuses**: Customize task statuses for this project
- **Custom Fields**: Add project-specific data fields
- **Automations**: Set up rules and triggers
- **Members**: Manage who has access and their roles
- **Integrations**: Configure project-specific integrations

### Project Templates

Save any project as a template:

1. Open Project Settings
2. Click "Save as Template"
3. Choose what to include (structure, sample tasks, automations, custom fields)
4. Name your template and save

Templates are available to all workspace members.

## Tasks

### Creating Tasks

- Click **+ Add Task** in any group/column
- Use the **Quick Add** shortcut (press `Q` anywhere)
- Create from email by forwarding to your project's unique email address
- Use the API or Zapier integration

### Task Properties

Every task has:

| Property | Description |
|----------|-------------|
| Title | Short description of the task |
| Description | Rich text with formatting, images, and file attachments |
| Status | Current state (customizable per project) |
| Assignee(s) | One or more team members responsible |
| Due Date | Single date or date range |
| Priority | Urgent, High, Medium, Low, or None |
| Tags | Color-coded labels for categorization |
| Custom Fields | Any additional fields defined at project or workspace level |

### Subtasks

Break complex tasks into subtasks:

1. Open a task
2. Click "Add Subtask"
3. Each subtask has its own assignee, due date, and status
4. Parent task progress is calculated from subtask completion

### Dependencies

Link tasks that depend on each other:

- **Finish-to-Start** (default): Task B can't start until Task A is done
- **Start-to-Start**: Task B starts when Task A starts
- **Finish-to-Finish**: Task B finishes when Task A finishes
- **Start-to-Finish**: Task B finishes when Task A starts

Dependencies are visualized in the Gantt chart view with connector lines.

### Comments and Activity

- Add comments with @mentions to notify team members
- Attach files directly to comments
- View the full activity log showing all changes
- Use emoji reactions for quick feedback

## Team Management

### Roles and Permissions

| Role | Permissions |
|------|------------|
| Owner | Full access, billing management, can delete workspace |
| Admin | Manage members, projects, settings (no billing) |
| Member | Create and edit tasks, view all projects they're added to |
| Guest | View-only access to specific projects |

### Custom Roles (Enterprise)

Create roles with granular permissions:

- Project-level: create, edit, delete, archive, manage members
- Task-level: create, edit, assign, delete, change status
- Workspace-level: manage integrations, custom fields, templates

### Inviting Members

1. Go to Workspace Settings > Members
2. Click "Invite Members"
3. Enter email addresses (bulk invite supported)
4. Assign a default role
5. Optionally add them to specific projects

## Integrations

### Slack

- Real-time notifications for task updates
- Create tasks from Slack messages
- `/taskflow` slash command for quick task creation
- Channel-to-project linking

### Google Workspace

- **Calendar**: Two-way sync of task due dates
- **Drive**: Attach Google Docs, Sheets, and Slides to tasks
- **Gmail**: Create tasks from emails

### GitHub / GitLab

- Link pull requests to tasks
- Auto-update task status based on PR state
- View code changes from the task detail panel

### REST API

Base URL: `https://api.taskflow.io/v1`

Authentication: Bearer token (API key)

Key endpoints:

```
GET    /projects              List all projects
POST   /projects              Create a project
GET    /projects/:id/tasks    List tasks in a project
POST   /projects/:id/tasks    Create a task
PATCH  /tasks/:id             Update a task
DELETE /tasks/:id             Delete a task
GET    /users                 List workspace members
```

Rate limits: 100 requests/minute (Professional), 500 requests/minute (Enterprise)

## Billing

### Plans

| Feature | Starter | Professional | Enterprise |
|---------|---------|-------------|-----------|
| Price | $9/user/mo | $19/user/mo | Custom |
| Users | Up to 10 | Up to 100 | Unlimited |
| Projects | 10 | Unlimited | Unlimited |
| Storage | 5 GB | 100 GB | Unlimited |
| Automations | 5/project | Unlimited | Unlimited |
| SSO | No | No | Yes |
| API Access | No | Yes | Yes |
| Support | Email (48h) | Email+Chat (24h) | Phone+Chat (4h) |
| Uptime SLA | None | 99.9% | 99.9% |

### Changing Plans

Upgrades take effect immediately. Downgrades take effect at the end of the current billing cycle. When downgrading, you may need to reduce usage (users, projects, storage) to fit within the new plan's limits.

### Billing FAQ

- **Annual billing**: Save 20% by paying annually
- **Invoices**: Available in Settings > Billing > Invoices
- **Payment methods**: Credit card, ACH bank transfer (annual only), wire transfer (Enterprise)
- **Refunds**: Pro-rated refunds available within 30 days of payment
