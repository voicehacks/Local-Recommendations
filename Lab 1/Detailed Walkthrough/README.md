## Detailed Steps for Lab 1
Follow these instructions to complete the work demonstrated in today's first lab. 

#### Steps

1. Change the skill name and invocation name to match your town.  For instance, name it "Boston Guide" and change the Invocation Name to "boston guide".
1. Click on Interaction Model to open the skill builder tool. 
1. Click save on the top left, then click build model.
1. In aws.amazon.com, open lambda console, find "Local Recommendations" and click on the name.
1. Review the first section of the code that is customized for Gloucester. It's found within the data variable. There are static data blocks called ```languageStrings```, and a ```data {}``` object containing details and lists.
Carefully modify these green strings within the quotes to define the city, state, zip, restaurants, and attractions custom to your particular town.
  Be sure to maintain quotes around all strings.  Single or double quotes around strings are both valid (```"``` or ```'```).   Ensure all objects ```{key:value}``` and lists ```[item1, item2]``` are properly nested and terminated, as in the starting      code sample. Update each line item in the data variable as needed to be representative of your city of choice.
1. The weather API shouldn’t require an update. We just updated the info in our data object, which will now be used by our API call.
1. Go back to developer.amazon, click 'test' in the box on the left, then scroll your page to the service simulator section.
1. Type the word dinner in the Enter Utterance box.
1. Below the Lambda Response box on the the right, click 'Listen'.
1. Type ‘yes’ for more details from your skill.
1. Type 'go outside' to ensure we're getting the current weather in our newly-changed city.  
1. If it works well, please [publish your skill](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/publishing-an-alexa-skill)  for the world to enjoy.
