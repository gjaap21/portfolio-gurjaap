---
title: P6
layout: doc
---
# P6
## Reports
### Report 1
The participant was able to easily navigate the dictionary and find the word “kai”. They also intuitively understood that the thumbs up and thumbs down were for liking/disliking a translation. As for creating a post, they were able to easily figure out where this could be done, and the overall process went smoothly. However, one thing to note is that they were slightly confused by the image URL and audio URL sections. Of course, we don’t have ways of storing actual image/audio data in this project, but they commented that it would make more sense to have a file upload and an in-built audio recording button for those sections. They also thought it would be a good idea to mark those sections as “optional” since they aren’t required.
Creating an event went very smoothly. They easily understood what each of the sections was for and were able to quickly create an event. The flow for navigating to the account screen and editing the description was also fairly clear, so no issues with either of those.
Creating a flashcard group was a little more messy. They initially created a group in the Flashcards tab. However, there was no way to add words to a flashcard group from within the group, and no instructions to point them in the right direction, so this left them confused. Once I pointed them to the dictionary to add words, there weren’t any more interaction flow issues. Using the flashcards was also pretty clear.
In the Word of the Day game, the participant didn’t fully understand how to play at first. It would have been helpful to include an instructions panel on how the game works for users that aren’t very familiar with it. They really enjoyed the game once they understood it though, and liked that they were able to learn more about the word after playing.
### Report 2
During the usability study, the participant moved smoothly through several tasks, especially those involving basic functions such as adding a word to the dictionary and finding the meaning of “kai.” These initial tasks were straightforward, and the interface was intuitive enough that the participant didn’t encounter any difficulties. Similarly, they quickly figured out how to upvote a word by clicking on a post and clearly understood the meaning of upvoting. This suggests the voting system was clear and accessible.
One area where the participant had positive feedback was the event creation interface, particularly the time feature, which they found user-friendly. The participant paused for a second when trying to update their account description, initially unclear of where to change it but then found the settings button and made the change.
When it came to the flashcard task, the participant made an interesting comment about the term “flashcarding,” which was a good point since our team was so used to this word but most people wouldn’t be. The participant also created a flashcard group without issue but encountered a bug when trying to add words to the flashcards. They were redirected to a blank page, which disrupted the flow and got stuck for a little bit.
Furthermore, when the participant attempted to create a food flashcard they didn’t filter by tag, which could have simplified the process. They also expressed a desire for audio features on the flashcard page to enhance learning. Finally, while the participant enjoyed the Word of the Day game, they overlooked the “Learn More” page at the end, which may indicate that the button wasn’t as prominent as it should be.
Overall, the study highlighted both the strengths of the user interface, such as its ease of use for basic tasks and event creation, as well as areas for improvement, particularly around navigation, bug fixes, and clarity in labeling.
### Report 3
After briefing the participant about the LinguaLink app and the purpose of the user study, I provided her with the link to the app and instructed her to find the entry for the word “Kai” and rate its translations. She completed the task with ease and upvoted one of the translations, noting that she liked that the post had an image to accurately illustrate the word's meaning.
We then moved on to the second task, adding a word to the dictionary. Upon opening the Add Word page, she promptly filled out the fields. Once she clicked the Add word button, however, she struggled to figure out how to proceed next. My guess is that this is due to the fact that the Add Word page doesn’t redirect to any other page once a word is added. She paused for a while and then decided to go back to the home page and open the dictionary to find her word.
The next task was to create an event. That part was relatively straightforward for her and she commented that the app was quite easy to use. Similarly to adding words, however, I noticed that she didn’t seem to know what to do after creating the event as the form was still on the screen when she clicked the create button.
We proceeded to the flashcarding task. One thing she was confused about during the task was that her flashcard group didn’t show up directly in the flashcard group list upon creation. She nevertheless proceeded and found the rest of the task straightforward.
For the last task of the session, she played the word of the day game. She read the instructions on the screen and then started to play the game. After correctly guessing the word on her sixth attempt, she expressed that that was her favorite feature on the app. She was visibly enthusiastic as she played the game and attempted to guess the word from the clues on each attempt.
Overall, the participant mentioned that the platform was quite easy to use. She said that she loved that words had images and that she greatly enjoyed the word of the day game. She suggested that it would be great if the Word of the Day could have more words to play with per day.
## Flaws or Opportunities for Improvement
- **Adding words to a flashcard group within the group itself**  
  - **Level:** Conceptual  
  - **Severity:** Critical  
  - Users could not determine how to add posts to a flashcard group from within the flashcard page. This led to confusion on how to proceed when creating a group. There was friction between the user’s view of how the flow should be and our actual implementation.  
  - **Solution:** We could add a way to add posts to a flashcard group from within the group’s page. Alternatively, we could provide some instruction on the group’s page directing users where to go to add posts, though this solution interrupts the flow.
- **Make "Learn More" on Word of the Day Page Bigger**  
  - **Level:** Physical  
  - **Severity:** Minor  
  - During user testing, when the user finished the Word of the Day game, she didn’t click on the “Learn more about this word” button. I suspect she didn’t notice it due to the button being small.  
  - **Solution:** Add an instruction about the button and increase its size to make it more noticeable.
- **Fix Flashcard Bug**  
  - **Level:** Conceptual  
  - **Severity:** Major  
  - Users encountered an unexpected error message after creating a flashcard group and trying to add a word. This error was caused by the lack of the necessary code to handle this specific case, disrupting the user experience.  
  - **Solution:** Implement the required logic to properly handle adding words to flashcard groups, ensuring smooth interaction without errors.
- **Instructions for Word of the Day game**  
  - **Level:** Linguistic  
  - **Severity:** Moderate  
  - There were no instructions for the Word of the Day game, leaving some users unsure of how to play.  
  - **Solution:** Add clear instructions on the screen, or consider a simple example video, though the latter may be unnecessary.
- **No page redirection upon word or event creation**  
  - **Level:** Conceptual  
  - **Severity:** Minor  
  - After adding a new word or creating a new event, the user wasn’t redirected to the relevant page, leaving them unsure if the action succeeded.  
  - **Solution:** Automatically redirect the user to the newly created word or event to reduce friction.
---
## Design Revisions
- **Removed the quizzing page**  
  We decided to get rid of the quizzing page in the interest of time. Our other features were more core to the functionality of the app, and quizzing was not an essential feature. This decision to scope down was necessary to focus on more impactful features.
- **Changed how flashcard groups are created**  
  We decided to create and add to flashcard groups from posts rather than from a separate posts page. This was done to make it clear to users which word they are adding and to streamline the process of creating sets.
- **Enhanced dictionary browsing**  
  Initially, we designed the dictionary feature to allow users to browse entries alphabetically. During implementation, we realized that enabling users to browse entries by category would make it easier for learners to find related words. This change supports a more intuitive user experience.
- **Displayed total upvotes and downvotes**  
  We decided to show total upvotes and downvotes on posts, rather than just showing the difference between upvotes and downvotes. This provides users with a clearer understanding of how frequently an item is being voted on and the overall validation of the word or post.
- **Updated Wordling functionality**  
  Initially, Wordling only stored the possible words and the current word. During implementation, we decided to also store previous words. This change ensures that if we run out of new words, we can reuse previous ones. Additionally, we added a document that stores the word along with the date it was used to better handle data sharing between multiple users.
---
### New Changes in Response to User Testing
- **Added user roles to the event page**  
  On the eventing page, we added a user role feature to distinguish between events created by teachers and learners. This helps users quickly understand who is hosting the event and sets clearer expectations.
- **Updated flashcard page icons and messaging**  
  On the flashcarding page, we changed the icons and added messaging to clarify the purpose of various buttons. This helps users better understand the functionality and improves the overall usability of the page.
- **Auto-redirect after word or event creation**  
  On the Add Word and Create Event pages, the user is now automatically redirected to the newly created word or event. This change reduces friction that users experienced when they added a new word or event and wanted to view it immediately.
- **Flashcard group list auto-refresh**  
  The flashcard group list now automatically refreshes when a new flashcard group is created. During user testing, one participant got confused because the list of groups didn’t update after creating a new group. This update ensures the list is always current and reduces confusion.
- **Added instructions to the Word of the Day page**  
  On the Word of the Day page, we added instructions on how to play the game. This helps users who may not be familiar with the game and reduces initial confusion.
- **Moved "Update description" to the profile page**  
  We moved the "Update description" option from the settings page to the profile page, as some users had trouble finding this option. Users expect to edit their description directly from the profile page, so this change aligns with their mental model.
- **Improved visibility of "Learn more about this word" button**  
  Some users didn’t notice the "Learn more about this word" option on the Word of the Day page after completing the game. To fix this, we added an instruction to guide users towards the button and made it bigger to improve visibility and encourage interaction.