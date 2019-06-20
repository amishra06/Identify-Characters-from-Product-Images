# Identify Characters from Product Images(CrowdANALYTIX)
## Problem Statement
Identify the “characters” from each image from a list of  42 possible characters:

Angry Birds, Baloo, Bart simpson, Ben, Bulbasaur, Charizard, Charlie brown, Charmender, Chicken_little, Cinderella, Darth_vader, Disney_princes, Donald_duck, Godzilla, Goku, Goofy, Han-solo, Harry_potter, Hellokitty, Itachi, John_Cena, Jojosiwa, Kakashi, Marilyn_monroe, Mickey_mouse, Minions, Naruto, Pikachu, Pokemon, Popeye, Power_rangers, R2-D2, Roman_reigns, Scoopy Doo, SpongeBob, SquarePants, Squirtle, Teenage_mutant_ninja_turtles, Tom and Jerry, Toy_story_characters, Vampirina, Vegeta, Winnie the poo


## Data
Data set consists of product images like t-shirts, bags, keychains, mobile covers, etc. with characters graphics. The master data set has been split into training and test data sets for the contest tasks. Participants will use the data sets provided to develop and test their models for prediction.

## My Approach

### 1. Balanced the unbalanced training data
I found that one class has around 408 images whereas the one with lowest number of images is just 78. All other classes have training images between these two numbers. So I worked on balancing the training set. For that purpose I augment the existing images and saved them in same class folders to increase the number of training images.

### 2. Split the data into training and validation set
To work with fastai's data block api we need to create validation set also. For that reason I created validation folder (Valid) in same location where training data folder (CAX_Characters_Train) exists. I am randomly shuffled the train set files and moved 20 percent files to validation folder maintaining the same path structure as training data

### 3. Training the model
  * Created databunch using fastai data block api.
  * Created the CNN learner with transfer learning using resnet50.
  * Trained data with discriminative learning rate
  * First trained with size of 128 and then for size of 256
  
  ## Result
  * Public Leaderboard - 0.86406  
  * Private leaderboard - 
