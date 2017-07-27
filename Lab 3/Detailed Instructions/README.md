## Extend the skill logic with smart recommendations

When the user says "go outside", the ```GoOutIntent``` intent is called and the code in the GoOutIntent handler block is executed.
This makes an API call over the Internet to the Yahoo Weather service, which returns the weather and current time in your city.

You can enhance the ```GoOutIntent``` handler code (around line 185) to make a relevant activity suggestion to the user.
For example, add logic to decide, based on current time and weather conditions:

* If it is before 6 am in current time, recommend staying in bed. 
* If it’s after 10 pm, recommend going to bed
* If it’s around breakfast, lunch or dinner recommend a restaurant accordingly
* If it’s raining or wet outside, stay home and watch a movie on Amazon Prime Video
* Spend some time here working on a robust algorithm 

#### Follow these steps

1. Test ‘go outside’ skill in simulator first. You should get a standard response giving you the time and weather conditions in your city. 
1. Go to your lambda function
1. Scroll through your code to one of the last handlers, called ```GoOutIntent```
1. Now, paste this code into your GoOutIntent:
```
            var AMPM = localTime.substring(6,8);
            console.log(AMPM);
            var hour = parseInt(localTime.substring(6,8));
            if(AMPM == "PM") { hour = hour + 12; }
            
            var suggestion = 'Read a book.';
            
            console.log(suggestion);
            
            if(hour < 7 ) {suggestion = 'Sleep.'; }
            if(hour >= 7 && hour < 12) {suggestion = 'Ask me for a breakfast recommendation.'; }
            if(hour >= 12 && hour < 14) {suggestion = 'Ask me for a lunch recommendation.'; }
            if(hour >= 17 && hour < 20) {suggestion = 'Ask me for a dinner recommendation.'; }
            
            if(hour >= 22) {suggestion = 'Go to bed.'; }
            
            if(hour >= 20 && hour < 22) {
                if(['Rain', 'Shower', 'Thunderstorms'].indexOf(currentCondition) > -1) {
                    suggestion = 'Stay home and watch a movie on Amazon Prime since it is wet outside.';   
                } else {
                    suggestion = 'Check out what is playing at the Cineplex movie theater on 123 Main St.';
                }
                
            }
            
            if (['Sunny'].indexOf(currentCondition) > -1 -1 && currentTemp > 75 && hour < 11) {suggestion = 'Plan a day at the beach, as it is sunny and warm today.'}
            
            console.log(suggestion);
            this.emit(':tell', 'It is ' + localTime
            + ' and the weather in ' + data.city
            + ' is '
            + currentTemp + ' and ' + currentCondition
            + '. I suggest you ' + suggestion);
```            
1. What we have just done is create some logic that matches possible outcomes to a custom response for our users. 
1. Now click Save, then click Test. Our test should pass.
1. Go to the developer portal.
1. Type 'go outside' into the Enter Utterance field found in the Service Simulator and press enter
1. Alexa should give us a customized recommendation according to your code. 




