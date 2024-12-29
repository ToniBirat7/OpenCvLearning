### Project Idea 

## Video Player Using AI (AI to Use Desktop)

As models like `Llama` can access the file system from the computer. We can use it to find the path for our files in our computer. 

On the other side we will have a model which will be trained or can be trained on the Screen Shot or Video that shows how to open the file (e.g. opening a video file from drive C). We will train the model with large amount of data. 

After the model has been trained, we will run the model (the model will start capturing the frames from the screen just like OBS Studio does). From each frame it will calculate the initial position of the cursor, then the vector (Direction, Magnitude) required to reach to the destination folder or file. 

Once the magnitude and direction has been calculated we will use the OS API to interact the cursor and move the cursor based on the position of the cursor on each frame that will be processed by our model. 

The cursor should follow a sequential path i.e. more clicks. 

**Example**

I gave the prompt to my model to open a video named NewYear.mp4. Then initially `Llama` or any other model will find me the path to the video. Once the path is found, our model which will be trained on the Pictures or Video of locating and opening the file will start to capture our window just like (OBS does). Then for each frame it will calculate the position of cursor and the position it needs to reach to open the first folder (e.g. My Computer). Then the cursor will click and open the `My Computer` folder. Then again it will capture the frame and the process repeats till we reach the destination file and open it. 

### Expansion of Idea

This is the base idea that can be expanded later on to create a model which takes prompt (Build a simple portfolio website). GPT will give the code, trained model will extract the data from the response. Then follow the above process to open VsCode paste it and run the server and interact it with the mouse on the Website (Like Scrolling, Clicks) no need of UI tester.  