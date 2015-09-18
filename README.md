# slack-cleaner

Bulk delete messages on Slack.

## Install

```bash
pip install slack-cleaner
```

## Usage

```bash
# Delete all messages from a channel
slack-cleaner --token=<TOKEN> --message --channel general

# Delete all messages from certain user
slack-cleaner --token=<TOKEN> --message --channel gossip --user johndoe

# Delete all messages from bots (especially flooding CI updates)
slack-cleaner --token=<TOKEN> --message --channel auto-build --bot

# Delete all messages older than 2015/09/19
slack-cleaner --token=<TOKEN> --message --channel general --before 20150919

# Always have a look at help message
slack-cleaner --help
```

## Tips

After the task, a backup file `slack-cleaner.<timestamp>.log` will be created
in current directory.

If any API problem occurred, try `--rate=<delay-in-seconds>` to reduce the API
call rate (which by default is unlimited).

If you see the following warning from `urllib3`, consider to install missing
packages: `pip install --upgrade requests[security]` or just upgrade your
Python to 2.7.9.

```
InsecurePlatformWarning: A true SSLContext object is not available. 
          This prevents urllib3 from configuring SSL appropriately and may cause certain SSL connections to fail. 
          For more information, see https://urllib3.readthedocs.org/en/latest/security.html#insecureplatformwarning.
```

## Credits

**To all the struggling :cry: startup founders who can only afford free plan.**
