# GitHub User Activity CLI

Sample solution for the [GitHub User Activity challenge](https://roadmap.sh/projects/github-user-activity) from [roadmap.sh](https://roadmap.sh/).

A simple command-line interface (CLI) application that fetches and displays recent activity of any GitHub user. Built with Node.js and powered by the GitHub API.

## Features

- 🔍 Fetch recent activity for any GitHub user
- 📊 Display various event types (commits, issues, stars, forks, etc.)
- ⚡ Real-time data from GitHub API
- ✔️ Error handling for invalid usernames
- 🎯 Clean and readable output format
- 📦 No external dependencies required

## Installation

1. Clone or download this repository
2. Make sure you have Node.js installed (v14 or higher)
3. Navigate to the project directory

```bash
cd github-user-activity
```

## Usage

Run the application using Node.js with a GitHub username as an argument:

```bash
node main.js <github-username>
```

### Examples

```bash
# View activity for a specific user
node main.js kamranahmedse

# View activity for another user
node main.js torvalds

# View activity for yourself
node main.js your-github-username
```

## Supported Event Types

The CLI displays the following GitHub activity events:

| Event Type | Description | Display Format |
|-----------|-------------|-----------------|
| `PushEvent` | Commits pushed to a repository | Pushed X commit(s) to repository |
| `IssuesEvent` | Issue opened, closed, or modified | Opened/Closed an issue in repository |
| `WatchEvent` | Repository starred | Starred repository |
| `ForkEvent` | Repository forked | Forked repository |
| `CreateEvent` | Branch or repository created | Created branch/repository |
| Other Events | Various other GitHub activities | Activity in repository |

## Output Example

```
- Pushed 3 commits to kamranahmedse/developer-roadmap
- Opened a new issue in kamranahmedse/developer-roadmap
- Starred kamranahmedse/developer-roadmap
- Forked awesome-project
- Created branch in personal-repo
```

## Project Structure

```
github-user-activity/
├── main.js                 # Main entry point with CLI logic
└── README.md               # Project documentation
```

## How It Works

1. **Accepts Username**: The script takes a GitHub username as a command-line argument
2. **Fetches Data**: Uses the GitHub API endpoint `https://api.github.com/users/{username}/events` to retrieve recent activity
3. **Processes Events**: Parses different event types and formats them for display
4. **Displays Results**: Outputs the formatted activity to the terminal

## Error Handling

The application gracefully handles various error scenarios:

- **No Username Provided**: Shows an error message asking for a GitHub username
- **User Not Found**: Displays "User not found" if the username doesn't exist on GitHub
- **API Errors**: Shows appropriate error messages for network or API failures

## Requirements Met

✅ Accepts GitHub username as a command-line argument  
✅ Fetches recent activity using the GitHub API  
✅ Displays activity in a readable format  
✅ Handles errors gracefully  
✅ No external libraries or frameworks used  
✅ Pure Node.js implementation  

## GitHub API Reference

This project uses the GitHub Events API endpoint:
- [GitHub Events API Documentation](https://docs.github.com/en/rest/activity/events?apiVersion=2022-11-28)
- Endpoint: `https://api.github.com/users/{username}/events`
- Rate Limit: 60 requests per hour for unauthenticated requests

## Learning Outcomes

This project helps you practice:
- Working with REST APIs
- Handling asynchronous operations (async/await)
- Parsing JSON data
- Building CLI applications
- Error handling and validation
- Command-line argument processing

## Advanced Features (Optional Enhancements)

You can enhance this project by adding:
- Filter activity by event type
- Display more detailed information about events
- Cache results to reduce API calls
- Add pagination for older events
- Export activity data to different formats (JSON, CSV)
- Add command-line options and flags (e.g., `--limit 10`, `--type push`)

---
