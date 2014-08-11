# hubot-gocd

Report build status from ThoughtWorks' Go.

See [`src/gocd.coffee`](src/gocd.coffee) for full documentation.

## Installation

In hubot project repo, run:

`npm install hubot-gocd --save`

Then add **hubot-gocd** to your `external-scripts.json`:

```json
["hubot-gocd"]
```

##Pipelines and stages to track

The script looks for a `go-pipelines.json` at the root of your Hubot.

This is used to configure which pipelines and stages are to be tracked.
In addition, we can also specify which statuses of the stages should be reported

Example:

```json
{
  "Pipeline1": {
    "Stage": ["passed", "failed"]
  },
  "Pipeline2": {
    "Stage": ["failed"]
  }
}
```

The status of stage `Stage` of `Pipeline1` is reported both when it fail as
well as when it passes. The status of stage `Stage` of `Pipeline2` is reported
only when it fails.
