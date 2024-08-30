# Twitch_auto_collect_points

Script to auto collect points on twitch channels

```javascript
  setInterval(()=>{
    const btn = document.querySelector('button[aria-label="Claim Bonus"]');
  
    if (!btn) return;
  
    btn.click()
  },30000)
```


## How to use

1. Open a channel
2. press `F12` and go to console
3. Paste the code on the console and press `enter`
4. Close the console or twitch will memory leak. I learned this the hard way.

That's it. The script will query the document every 30 seconds to chack in the bonus button is there and click it if it is.

**Important Note:** If you **close** the tab or the browser you need to **repeat** the process. 

Tested on Firefox but I don't see a reason why it would not work on other browsers.

## Issues

At anytime twitch can change the way to query the button.

Use the following code to check if it still works (the button needs to be visible)

```javascript
  document.querySelector('button[aria-label="Claim Bonus"]');
```

If you press enter it shoul return something like this

```html
  <button class="ScCoreButton-sc-ocjdkq-0…-ocjdkq-5 ljgEdo fEpwrH" aria-label="Claim Bonus">
```

It will return `null` it it doesn't work anymore. 

At that point feel free to open a issue or submit a PR with the new selector.


Enjoy.


