# Project 1
For this project, my high-level approach was to first connect to a socket, encode and send a json message, receive the message and decode, and make a guess based on the marks received. The guess was formulated by going through the solutions and picking the first plausible word.  

## Challenges
The main challenge I faced was learning the socket library, manipulating json, and how to tackle the gray letters. I had never seen the socket library before. I also had never seen the json library before. The gray letters were a challenge since the same letter could be both gray and yellow, and if I added it to the non-valid letters, the solution would never be found. 

## Guessing Strategy
My strategy was to comb through the solutions and return the first valid word. A valid word had the green letters in the correct spot, yellow letters in a different spot than the original guess (but still somewhere in the word), and contained none of the gray letters, even those from previous guesses. I chose this strategy since this is how I normally play Wordle. I think this strategy is effective as in my testing, most words were guessed within 6 tries.

## Testing
To test my code, I tried a variety of calls to ./client. I tested -p, -s, and leaving out hostname and username. To check that my strategy was effective, I ran ./client 50 times with an average of 5.98 guesses. At most, the client attempted 10 guesses. Adding '-s' did not impact performance, which was to be as expected. In all trials, there was no issues with the socket connecting.