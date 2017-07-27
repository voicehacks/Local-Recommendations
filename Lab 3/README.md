### Lab 3: Extend the skill logic with smart recommendations
For step-by-step instructions with some sample code for you to use, go to the [detailed instructions](https://github.com/voicehacks/Labs/tree/master/Lab%203/Detailed%20Instructions) in this lab.

When the user says "go outside", the ```GoOutIntent``` intent is called and the code in the GoOutIntent handler block is executed.
This makes an API call over the Internet to the Yahoo Weather service, which returns the weather and current time in your city.

You can enhance the ```GoOutIntent``` handler code (around line 185) to make a relevant activity suggestion to the user.
For example, add logic to decide, based on current time and weather conditions, whether to:

 * Go out to a local beach or park
 * Recommend a movie theatre or mall
 * Attend a scheduled public event happening soon
 * Staying home to watch a movie on Amazon Prime
 * etc..
