{
  "agents": [
    {
      "name": "BitbucketCommitWatcher",
      "type": "commit_listener",
      "description": "Runs in the background whenever a new commit is made to the local Bitbucket repository.",
      "triggers": ["bitbucket_commit"],
      "handoff_to": ["CodeAnalyzer"]
    },
    {
      "name": "CodeAnalyzer",
      "type": "static_analysis",
      "description": "Analyzes the code of new commits for issues or improvements.",
      "triggers": ["handoff_from_BitbucketCommitWatcher"],
      "handoff_to": ["TestGenerator"]
    },
    {
      "name": "TestGenerator",
      "type": "unit_test_generator",
      "description": "Generates unit tests automatically for new commit changes.",
      "triggers": ["handoff_from_CodeAnalyzer"],
      "output": "suggested_unit_tests"
    },
    {
      "name": "DocWriter",
      "type": "documentation",
      "description": "Generates documentation based on the new commit code.",
      "triggers": ["handoff_from_CodeAnalyzer"]
    }
  ],
  "workflow": [
    {
      "event": "bitbucket_commit",
      "start_agent": "BitbucketCommitWatcher"
    },
    {
      "event": "handoff",
      "from_agent": "BitbucketCommitWatcher",
      "to_agent": "CodeAnalyzer"
    },
    {
      "event": "handoff",
      "from_agent": "CodeAnalyzer",
      "to_agent": ["TestGenerator", "DocWriter"]
    }
  ]
}