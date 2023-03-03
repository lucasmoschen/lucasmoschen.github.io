---
title: "Neural Networks and Deep Learning"
excerpt: "Studies and homeworks of the Neural Networks subject in Applied Math Course."
read_time: true
gallery:
  - url: /assets/images/chart-neural-network.png
    image_path: /assets/images/chart-neural-network.png
    alt: "chart 1"
  - url: /assets/images/chart2-neural-network.png
    image_path: /assets/images/chart2-neural-network.png
    alt: "chart 2"
---

Abstract
--- 

In this course, we studied Notions of Artificial Intelligence, Machine Learning, Linear Algebra and
Probability. Type of Neural Networks, such as Perceptron, FeedForward,
Recurrent Neural Network (RNN), Long / Short Term Memory (LSTM), Transformers,
Auto Encoders, Convolution Neural Networks, Generative Adversarial Network.
Frameworks for development and applications.

[Course material](https://github.com/rsouza/NeuralNetworks_Course)

We and my partner [Lucas Domingues](https://github.com/lucasresck) finished
with a work about Deep generative models for data creation (Deep fakes),
exploring its first use in porn celebrities and how it became famous after
[Barack Obama's
video](https://www.buzzfeed.com/craigsilverman/obama-jordan-peele-deepfake-video-debunk-buzzfeed)
made in FaceApp.

After that, its usage only increased, with applications from entertainment
videos and audios to
[politics](https://www.technologyreview.com/2020/02/19/868173/an-indian-politician-is-using-deepfakes-to-try-and-win-voters/).

{% include gallery caption="Here we show how it grew along the years." %}

Technical Background 
---

- **Encoder-Decoder Networks:** Four neural networks are used alone or combined to create this kind of media: Two networks with narrower layers towards the center so that there is a encode in the latent space.
- **Convolucional Neural Networks:** Learn filters that move through the entrance forming a map of abstract features.
- **Generative Adversarial Networks:** A dispute between a neural network that generates fakes and a neural network that discriminates fakes from real ones.
- **Recurrent Neural Networks:** Handles sequential variables. After processing $$x^{(i-1)}$$ the network remembers the internal state and can use $$x^{(i)}$$.
 
Nowadays, the CycleGan is a great tool used to deal with audio input. 
