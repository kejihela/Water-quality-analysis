# Water-quality-analysis
To analyze a dataset collected from CEFAS and, using neural networks, detect when threshold levels of certain substances are reached / exceeded.
We'll be using data from the UK's Centre for Environment, Fisheries, and Aquaculture (CEFAS). CEFAS keeps track of water quality by dispatching vessels (much like the Endeavour on the right) to collect samples and examine the environment. A variety of compounds are monitored, including phytoplankton, with which we will be working today.
Here's a quick and easy explanation of what phytoplankton is and why it's important. Essentially, it is a naturally occurring species of micro algae that is a vital part of its ecosystem, providing food for marine life among other things (in its natural volume and concentration). If phytoplankton becomes out of control, it can cause a dangerous algal bloom, which can affect fish, animals, and birds.

![image](https://user-images.githubusercontent.com/72225471/171477881-19742691-75e1-45cc-9cb1-7303b0dc56e9.png)

![image](https://user-images.githubusercontent.com/72225471/171478478-cbba0020-f8fc-4544-8963-f374a5bb9be8.png)
![image](https://user-images.githubusercontent.com/72225471/171478628-a89ccc70-1166-45e7-89e9-cabbdac4266d.png)

Figure 1: Microscopic phytoplantkon.
Figure 2: Harmful algal bloom on satellite images.

![image](https://user-images.githubusercontent.com/72225471/171479132-7253e3aa-f88a-4542-b7c0-6f13e5ae1a37.png)

**Data Cleaning**
The following columns are the ones we're most interested in, as we already know from the data description:
• Pseudo-nitzschia spp. cells L-1 (ASP)
• Alexandrium spp. cells L-1 (PSP)
• Prorocentrum lima cells L-1 (DSP)
• Dinophysiaceae cells L-1 (DSP)
There are some cells with numbers, some with text, some empty, and many with the code "ND" - which we know means "not detected" from the explanation.

**Data labelling**
At the end of the day, we want to train a machine learning model (a classifier) that can tell us whether every observed data value exceeds the phytoplankton threshold.

**Deep Learning**
I'll define and train a neural network in this section. If you've gone through the backpropagation course, you'll have a better understanding of some of the "ingredients" of neural nets that we'll need to define and modify in this section. Keras will be used to train our neural network. Keras is a Python library that offers a more convenient set of methods and implementations for developing deep learning models than other frameworks like (core) TensorFlow. Other libraries, such as PyTorch, provide a middle level of abstraction, but we'll stick with Keras for now.
