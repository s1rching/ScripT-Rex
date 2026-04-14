# ScripT-Rex
An easy-to-use DevTool utility for re-initializing the Chrome Dinosaur game by bypassing loadTimeData restrictions.
## Instructions
1. Go to chrome://dino in the Chrome browser
2. Open devtools
   * Press ctrl+shift+i

     OR


<figure>
  <img src="Content/Assets/Example1.png" alt="First Example" width="200" height="150">
  <figcaption>Go to the 3 dots drop-down menu</figcaption>
</figure>
<figure>
  <img src="Content/Assets/Example2.png" alt="First Example" width="400" height="300">
  <figcaption>Go to "More Options" and select "Developer Tools"</figcaption>
</figure>
3. Go to the console tab in dev tools and paste in the following code:

```delete loadTimeData.data_["disabledEasterEgg"];
Runner.prototype.isDisabled = () => false;
Runner.instance_ = null; 
new Runner(".interstitial-wrapper");

