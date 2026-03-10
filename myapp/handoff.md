{
  "agents": [
    {
      "name": "CodeAnalyzer",
      "type": "static_analysis",
      "description": "Analyzes code for issues and detects missing tests.",
      "triggers": ["git_commit", "code_comment"],
      "handoff_to": ["TestGenerator"]
    },
    {
      "name": "TestGenerator",
      "type": "unit_test_generator",
      "description": "Generates unit tests for code based on analysis.",
      "triggers": ["handoff_from_CodeAnalyzer"],
      "output": "suggested_unit_tests"
    },
    {
      "name": "DocWriter",
      "type": "documentation",
      "description": "Generates code documentation when requested.",
      "triggers": ["code_comment", "manual_request"]
    }
  ],
  "workflow": [
    {
      "event": "git_commit",
      "start_agent": "CodeAnalyzer"
    },
    {
      "event": "handoff",
      "from_agent": "CodeAnalyzer",
      "to_agent": "TestGenerator"
    }
  ]
}

How this works

CodeAnalyzer starts on a Git commit or code comment.

If it detects missing tests, it triggers a handoff to TestGenerator.

TestGenerator generates unit test suggestions and outputs them.

Other agents like DocWriter can run independently based on comments or manual requests.