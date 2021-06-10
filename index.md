I'm a data scientist using both Python and R. I'm passionate about using data to help drive better decision making.

In June of 2021, I graduated from the University of Chicago's Masters of Science in Analytics program. For our capstone project, my team and I worked with Conservation Labs' proprietary sound data to classify water fixture usage in multi-family homes. The project won best in show for our session.

Conservation Labs currently has a dual microphone sensor that is placed inside mutli-family residences on pipes such as the water main and hot water intake. The sensors produce second by second amplitude readings of water flow through a short-time Fourier transform. We placed several sensors in our own apartments and recorded water events as we used fixtures throughout the course of several months. With over 4 GBs of sound data across 7 unique fixtures (sink, toilet, etc.), we created an algorithm to detect when events started and stopped.

![plot](./Event_Frequencies.JPG?raw=true)

After events were identified, we performed model-specific feature engineering and tested 3 models to classify fixture usage. The first was a semi-supervised clustering approach with Gaussian Mixture Models to probabilistically cluster events based on the expectation-maximization algorithm. The benefit of this approach is that most likely labels can be propagated throughout clusters for similar events. This reduces the amount of labelled data needed. The second utilized gradient boosted trees in the form of XGBoost to classify events based on the average value of each frequency bin during the duration of the event. Both of these techniques produced models that were quick to train and 92% accurate in a holdout set of roughly 700 events.

![plot](./Spectrogram_Creation.JPG?raw=true)

The final model used a convolutional neural net to classify events that were transformed into spectrogram images. By converting the events into scaled and normalized greyscale images, they can be fed directly into a CNN as an array of floating values that will preserve the granularity of the entire event. The CNN model architecture consisted of:

- 2 convolutional layers for gross and granular features
- 1 max pooling layer for dimension reduction
- 2 dropout layers to reduce overfitting
- 1 flatten and 1 dense layer to compule the image into a single array and output predictions

Overall 20 million parameters were trained in this model, and it produced 97% accuracy in the same holdout set.

With this level of accuracy, Conservation Labs can incorporate the classifications into their existing product to build stronger customer engagement leading to higher customer retention, and most importantly, a more informed and conservation-focused user base working to be smarter about use of one of our most scarce resources.

Other projects done throughout the program can be found [here](https://github.com/tjwillz31/UChicagoMSCA).

In my spare time, I enjoy combining my data science passion with my football fandom to attempt to answer interesting questions from both a real life football and fantasy football perspective. 

My work in the 2021 NFL Big Data Bowl to create target and catch expectation models for secondary defenders based on tracking data can be found [here](https://github.com/tjwillz31/NFL). 

Analysis that I've done for articles written on [PlayerProfiler](https://playerprofiler.com) can be found [here](https://github.com/tjwillz31/Fantasy_Football).

Feel free to get in touch!

- email: taylorjwilliams31@gmail.com
- github: https://github.com/tjwillz31
- twitter: @tjwillz31
