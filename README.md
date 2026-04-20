# ScripT-Rex
An easy-to-use DevTool utility for re-initializing the Chrome Dinosaur game by bypassing loadTimeData restrictions.
## Instructions
1. Go to chrome://dino or a conventional network error page in the Chrome browser
2. Open devtools
   * Press ctrl+shift+i

     OR

Go to the 3 dots drop-down menu

<img src="Content/Assets/Example1.png" alt="First Example" width="200" height="150">
Go to "More Options" and select "Developer Tools"

<img src="Content/Assets/Example2.png" alt="First Example" width="400" height="300">
3. Go to the console tab in devtools and paste in the following code:

```
// 1. Remove the "disabled" flag
delete loadTimeData.data_[ "disabledEasterEgg" ];

// 2. Bypass the disabled check
Runner.prototype.isDisabled = () => false;

// 3. Clear any existing instances
Runner.instance_ = null;

// 4. Hide the "disabled by owner" snackbar message
const snackbar = document.querySelector(".snackbar");
if (snackbar) snackbar.hidden = true;

// 5. Start the game
new Runner(".interstitial-wrapper");
