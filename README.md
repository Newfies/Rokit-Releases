# config.json

## Webhooks

| Param Name      | Type   | Description                                                                                                       |
|-----------------|--------|-------------------------------------------------------------------------------------------------------------------|
| `Main`          | URL    | The default/main webhook that valid usernames will be sent to.                                                    |
| `Alt`           | URL    | The alt webhook that valid usernames will be sent to.                                                             |
| `Message_Plain` | object | The message sent to the webhook in plain text.                                                                    |
| `Message_Embed` | object | The message sent to the webhook as an embed (use Discohook to generate).                                          |
| `Webhook_Queue` | int    | The delay before a new username is sent to the webhook. Valid usernames are stored in a queue waiting their turn. |

## Output

| Param Name          | Type | Description                                    |
|---------------------|------|------------------------------------------------|
| `Valid_Usernames`   | path | The file valid usernames will be written to.   |
| `Invalid_Usernames` | path | The file invalid usernames will be written to. |
| `Logs`              | path | The directory where logs will be written.      |


## API

| Param Name        | Type | Description                                                    |
|-------------------|------|----------------------------------------------------------------|
| `Request_Timeout` | int  | The time in seconds before a request times out and is skipped. |


## Logging & Output Options

| Param Name                | Type    | Description                                                                                                           |
|---------------------------|---------|-----------------------------------------------------------------------------------------------------------------------|
| `Write_Valid_Usernames`   | boolean | Whether valid usernames are written to the text file.                                                                 |
| `Write_Invalid_Usernames` | boolean | Whether invalid usernames are written to the text file.                                                               |
| `Write_Logs`              | boolean | Whether logs are written to the text file.                                                                            |
| `Output_Terminal_Logs`    | boolean | Whether the current logs are displayed in the terminal.                                                               |
| `Use_Webhook_Embed`       | boolean | Whether messages are sent as embeds (if `false`, plain text is used).                                                 |
| `Use_Webhook_Queue`       | boolean | **\[RECOMMENDED]** Whether a webhook queue is used to avoid rate limits (if `false`, usernames are sent immediately). |
| `Use_One_Log`             | boolean | If `true`, all logs are stored in `logs.txt`; if `false`, logs are split by timestamp (`logs_MM.DD.YYYY_HHMM.txt`).   |

# Command Line Arguments

For command line arguments visit the page at **[https://newfies.github.io/Rokit-Releases/commandlinearguments.html](https://newfies.github.io/Rokit-Releases/commandlinearguments.html)**

> [!NOTE]
> I had to put the table on its own page because GitHubs markdown kept messing with the table, making it unreadable.

```
  --h, --help                                   show this help message and exit
  --file FILE                                   File containing usernames to check [Default Off]
  --l NUMBER                                    Generate NUMBER character usernames [Default No Min/Max]
  --format FORMAT                               Generate usernmes following a specific format, read the README to learn the formatting.
  --wordgen                                     Generate words from english-words package [Default Off]
  --barcodes                                    Generate barcode style usernames [Default Off]
  --num or --numbers                            Allow numbers in username [Default False]
  --und or --underscores                        Allow underscore in username [Default False]
  --let or --letters                            Allow letters in username [Default False]
  --proxy PROXY                                 Use proxies from a file (http://ip:port) [Default: Off]
  --range RANGE                                 check RANGE amount of usernames [Default 100]
  --skip NUMBER                                 Skip NUMBER lines in input file [Default 0]
  --wh WEBHOOK or --webhook WEBHOOK             Send valid usernames to a specific webhook url [Default None]
  --alt                                         Send valid usernames to the config.json alt webhook url [Default Off]
  --delay DELAY                                 Set a DELAY between each checked username
```