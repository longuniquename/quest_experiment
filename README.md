Quest experiment
================
```json
{
  "states": {
    "s1": {
      "title": "Selection state",
      "contents": "Choose your drink",
      "functions": [
        {
          "title": "Tea choice",
          "contents": "Tea",
          "actions": [
            {
              "fn": "set",
              "args": {
                "v2": 1
              }
            },
            {
              "fn": "go",
              "args": "s2"
            }
          ]
        },
        {
          "title": "Coffee choice",
          "contents": "Coffee",
          "actions": [
            {
              "fn": "set",
              "args": {
                "v2": 2
              }
            },
            {
              "fn": "go",
              "args": "s2"
            }
          ]
        },
        {
          "title": "Adult choice",
          "contents": "I'm adult",
          "if": {
            "equals": ["$v1", false]
          },
          "actions": [
            {
              "fn": "set",
              "args": {
                "v1": true
              }
            },
            {
              "fn": "go",
              "args": "s1"
            }
          ]
        },
        {
          "title": "Beer choice",
          "contents": "Beer",
          "if": {
            "equals": ["$v1", true]
          },
          "actions": [
            {
              "fn": "set",
              "args": {
                "v2": 3
              }
            },
            {
              "fn": "go",
              "args": "s2"
            }
          ]
        }
      ]
    },
    "s2": {
      "title": "Drinking state",
      "contents": {
        "fn": "concat",
        "args": [
          "Your drink is: ",
          {
            "fn": "switch",
            "args": {
              "1": "tea",
              "2": "coffee",
              "3": "beer"
            }
          }
        ]
      }
    }
  },
  "variables": {
    "v1": {
      "title": "Is adult",
      "default": false
    },
    "v2": {
      "title": "Drink"
    }
  }
}
```
