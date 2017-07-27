If it is before 6 am in current time, recommend staying in bed. 
If it’s after 10 pm, recommend going to bed
If it’s around breakfast, lunch or dinner recommend a restaurant accordingly
If it’s raining or wet outside, stay home and watch a movie on Amazon Prime Video
Spend some time here working on a robust algorithm 


Test ‘go outside’ skill in simulator first
Go to lambda function
One of the last handlers, called GoOutIntent
3:50 look at code
Save, then test
Go to developer portal
Type you outside and press enter
Should give a recommendation according to your code




Paste this code:
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
                    suggestion = 'Stay home and watch a movie on Amazon Prime since it is wet outside.'   
                } else {
                    suggestion = 'Check out what is playing at the Cineplex movie theater on 123 Main St.'
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
