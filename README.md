# Bender

A bot framework that uses Slack's [RTM API](https://api.slack.com/rtm).

**Note:** this is still under active development.

## Notes

**NOTE:** the original is [here](https://github.com/seancron/bender/).

### Setup

Environment variable:

    $ export SLACK_API_TOKEN="k3yb04rd_c4+"

Python 2.7.

Get requirements:

    pip install -r requirements.txt

Sample code:

    from bender import SlackBot
    from bender.plugins import demo
    # Put code in demo or restructure it
    @message_received.connect
    def some_message(sender, **kwargs):
        event = kwargs['event']
        if 'keyboard cat' in event.text:
            sender.slack_client.send_message('https://youtu.be/J---aiyznGQ', event.channel)
    if __name__ == '__main__':
        bot = SlackBot()
        bot.run()

### Misc Notes

Slackbot:

    curl --data "Hello from Slackbot" $'https://my.slack.com/services/hooks/slackbot?token=TOKEN&channel=%23random'
