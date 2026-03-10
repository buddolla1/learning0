{
  "agents": [
    {
      "name": "BackgroundWatcher",
      "type": "file_watcher",
      "description": "Runs in the background on file changes",
      "triggers": ["file_save", "git_commit"],
      "output": "analysis_results"
    }
  ]
}Place this file in your project root. Copilot Agents will pick it up automatically (if using VS Code Copilot with agents enabled).

Your agent can now run automatically on triggers like file saves or commits, without manual intervention.