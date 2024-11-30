# PR-to-Discord
Sends Pull Request notification message to Discord.
</br></br>
![image](https://github.com/user-attachments/assets/2c86513e-f4b9-49e2-9818-54501e8ed463)

## Inputs
- `discord_webhook_url` (required): webhook URL of a Discord channel.
- `pull_request`: Pull request JSON string. Default is ${{ toJson(github.event.pull_request) }}.

## Example

아래 PR.yml 파일은 각 repository .github/workflows 아래 두면 된다.

```yaml
name: PR to Discord

on:
  pull_request_target:
    types: [opened, reopened]

jobs:
  PR:
    runs-on: ubuntu-latest
    steps:
      - uses: Team-Retrip/PR-to-Discord@main
        with:
          discord_webhook_url: ${{ secrets.DISCORD_WEBHOOK_URL }}
```
