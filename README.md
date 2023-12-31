# TimeAgo Tumblr plugin
I've absolutely loved using [@bychloethemes](https://bychloethemes.tumblr.com)'s  [timeAgo(); plugin](https://bychloethemes.tumblr.com/plugins/timeago) but wanted to utilize the timestamp feature without the requirement of jQuery since I no longer use jQuery in my themes. This is my attempt at a pure Javascript timestamp plugin. I have, respectfully, adapted some of Chloe's options for easy usage.

> [!NOTE]
> Basic JS/HTML knowledge isn't necessarily required but it's helpful.

## How to use
Before `</body>` Place the readable or minified version of the script in a `<script>` tag. Use Tumblr's theme assets to upload it.

```html
<script src="timeago.min.js"></script>
```
You could also paste the script with your other script snippets, but the unminified version takes up a few lines of code. If you do, just make sure the initialization follows.

### Initialization
Place the following snippet to initialize the timeAgo functionality inside a  `<script>` tag

```Javascript
const elements = document.querySelectorAll('.timeago');

timeAgo(elements, {
    time: 'letter', // should be 'letter' 'short' or 'word'
    spaces: false, // 'true' adds spaces between words and numbers
    words: false, // 'true' turns numbers to words
    prefix: '',  // adds a prefix. could be '~' or 'about' or 'posted' etc.
    suffix: '' // adds a suffix. could be 'ago' or period, etc.
});
```

### Time options
There are 3 different time options:

| Letter | Short | word |
| ------ | -----| -----
|s       | sec | second |
|m       | min | minute |
|h       | hr  | hour   |
|d       | day | day    |
|w       | wk  | week   |
|y       | yr  | year   |

### HTML
This plugin requires a UNIX time stamp, and for Tumblr that is `{Timestamp}`. We also need to give it a class name, so for example:
```html
<div class="timeago">{Timestamp}</div>
```
Make sure the class matches the initialization's `querySelectorAll`.

### Result
Now you're html document should look somehat like this:

```html
<html>
    <body>
        <div class="timeago">{Timestamp}</div>
    
        <script src="timeago.min.js"></script>
        <script>
            const elements = document.querySelectorAll('.timeago');
            
            timeAgo(elements, {
                time: 'letter', // should be 'letter' 'short' or 'word'
                spaces: false, // 'true' adds spaces between words and numbers
                words: false, // 'true' turns numbers to words
                prefix: '',  // adds a prefix. could be '~' or 'about' or 'posted' etc.
                suffix: '' // adds a suffix. could be 'ago' etc.
            });
        </script>
    </body>
</html>
```
## Credits
Most of the script was written by me, but the initialization parts are credited to [@bychloethemes](https://bychloethemes.tumblr.com) - I do not claim ownership of the initialization at all. A big thanks to Mike on Stack Overflow for helping with incorperating that.
