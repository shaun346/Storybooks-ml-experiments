# Storybooks-ml-experiments
This is a basic machine learning project to identify 3 books based on the training and testing data provided to it.

I created a dataset of 90 pictures consisting of 3 story books, 30 pictures each. I shot those pictures in different angles, lightings, orientations and with obstructions. The goal of the machine learning model is to identify these books with maximum accuracy.

When i originally trained the model for the first time, the results were a little confusing. According to my results, my loss was decreasing uniformly at an optimal rate but my validation accuracy wasnt increasing accordingly and just kept bouncing from 50 to 22 to ending at 33.33% (graph is attached for it).
Upon further analysis and research i realized this was a classic scenario of overfitting: my model was practically "memorizing" the data instead of understanding it. This was causing it to randomly guess as opposed to knowing. That explained the 33.33% (3 books).

I did 2 things to fix that:-

1. I increased the dropout rate to 50% from 25%. This basically caused half the neurons to shut down during every single pass, forcing the model to learn multiple ways to recognize the book.
2. I added regularization. What this meant was that if my network tried to make any single connection too strong(weight), then the optimizer will shrink that weight back down. This is a classic fix in case of overfitting.

After that i built a new model with the above changes, and that fixed my model by a lot(graph attached). My validation accuracy, although still fluctuating a lot, had a considerable increase from first Epoch (22.22%) to the final one (50%).

After that, I decided to test my model a little and see how increasing the learning rate drastically effects my model.
I created an identical model with the difference being that i increased the learning rate from 0.001 to 0.05, making it 50 times larger.

This heavily damaged the model(graph attached). It caused both my loss and my accuracy to flatline. This was because the learning rate was so huge that it was practically leaping to and fro around the ideal function. 

The only few things i am curious about is why my accuracy still maxed out at 50%, But i think that would increase drastically with improved dataset with more pictures and better organised training and testing data.

This really helped me understand why more training data isnt always optimal for the network if it just memorizes the data instead of understanding it. Also this helped me understand how learning rate effects the model.



