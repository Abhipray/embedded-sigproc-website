+++ 
date = "2020-08-31"
title = "876 days journey to becoming a Master of Electrical Engineering"
markup = "mmark"
+++

Last month I gave my last exam towards an MS in Electrical Engineering at Stanford. For two and a half years now, I took at least one course every quarter. Every course taught me something new. Most gave me the opportunity to work on a project. Here is a brief summary of topics I studied and more interestingly, what I did with each topic. 

## 1. Statistical signal processing (Tsachy Wiessman)

I learned about random signals and systems, a new layer of abstraction for me (on top of the familiar deterministic signals and systems theory). Here, I mostly worked on problem sets on topics like Kalman filtering, Wiener filtering, random processes etc. No projects. 

## 2. Digital signal processing (Jose Krause Perin)

I took DSP as a summer course so it was accelerated. Through work experience, I had scratched the surface on several DSP topics and concepts such as FIR/IIR filtering, interpolation, downsampling etc. With this course, I got really satisfying explanations for why and how digital signals are manipulated. We had fun problem sets involving MATLAB implementations, for example implementing the adaptive noise cancellation algorithm of Apple airpods.

**With the knowledge I gained from these first two courses, I wrote a [blog post]({{< ref "/posts/pdm_pcm_conversion" >}}) explaining how Pulse Density Modulation (PDM) works.**

## 3. Linear dynamical systems (Reza Nasiri)

I wanted a more general understanding of how dynamical systems worked because I encountered them frequently in the literature. **It turned out that the familiar linear systems I was studying in my undergraduate EE classes were a special case of LDS systems. I wrote a blog post about this [here]({{< ref "/posts/linearity" >}}). The course also gave me a crash course in linear algebra leading to a [blog post]({{< ref "/posts/linearity" >}}) on the meaning of linearity.**


## 4. Information theory (Tsachy Weissman)

I had recently read the [Dover book](https://www.amazon.com/Introduction-Information-Theory-Symbols-Mathematics/dp/0486240614) on Information Theory and Claude Shannon's biography, "A Mind At Play". Both of these combined to get me pumped up for this class on the theory of 1s and 0s. We went over different aspects of a fascinating theory for how to abstractly represent and transmit information. It defined the notion of entropy, H as a measure of information in the units of bits. There are two major pieces-- source encoding and communication channel encoding. In source coding or compression, we want to eliminate redundancies to represent the message in as few number of bits as possible. In channel encoding, we typically want to introduce redundancies in order to make sure the receiver can decode correctly. Entropy gives limits on maximum possible compression rate as well as maximum possible rate of transmission through a channel.

**For the project, my teammate Sakshi and I worked on finding good tactile representations for image signals.  I discovered a unique way of generating error correction codes called Gray codes and wrote a blog post on it. Tsachy had all the teams present their projects at an elementary school across from Stanford. [Here]({{< ref "/posts/tactile_vision" >}}) are more details on our project.**


## 5. Adaptive signal processing (Bernard Widrow)

Dr. Widrow invented the least mean square (LMS) learning algorithm for adapting linear filters and was a pioneer of adaptive signal processing and neural networks. He was 89 years old when he taught the course so he was full of great stories. It was very cool to hear about how neural networks that are all the rage today had some humble beginnings in adaptive filtering. 

**For my project, I implemented a linear prediction based algorithm to remove stationary noise in speech signals. The project and its implementation can be found [here](https://github.com/Abhipray/speech_denoising).**


## 6. Machine learning (Andrew Ng)

I took Andrew Ng's online Machine learning class in 2011 (which happened to be the very first Coursera course) so was excited when given the opportunity to take it in person. I had a different perspective this time around and absorbed a lot more.

**For my project, I worked with two other students, Stephane and Jake to try out an idea that came up with Dr. Widrow-- a relative LMS algorithm for updating the weights of an artificial neuron. The paper for this is [here](__LMS_CS229_paper.pdf). The poster is [here](CS229_Poster.pdf)**


## 7. Deep generative models (Aditya Grover & Stefano Ermon)

With the recent successes of GANs in generating images, I wanted a foundational understanding for how they are able to achieve such realistic images. The course covered several generative models for data. The course notes are succinct and online [here](https://deepgenerativemodels.github.io/notes/index.html) if you are interested. 

**For the project, my two teammates and I worked on audio bandwidth extension. Here is the [paper](CS236_AudioSuperResolution_2019_Nov.pdf).**

## 8. Deep learning (Andrew Ng)

I had taken some deep learning modules from Coursera before my Master's degree but wanted to take this for the extra in-person lectures that discussed the latest and greatest. 

**For the project, I worked on building an RNN based voice activity detector with the intention of using it on our Neosensory Buzz. Here are the [paper](CS230_Project_Report.pdf) and [poster](CS230_Poster.pdf).**

## 9. Perceptual audio coding (Marina Bosi)

Through my work at Neosensory, I had read a lot about audio codecs especially their compression schemes so I was excited to take this course. This course was a deep dive into various parts of modern codecs like mp3 and aac. Over the course, we built piece by piece a fully functional codec -- quantization, frequency mapping, leveraging perceptual masking, etc. 

**For the final project, my teammates Jatin, Arda and I implemented three new features-- block switching, spectral band replication and gain shape quantization. I worked on the vector quantization piece that implements the same scheme (Pyramid Vector Quantization) used by [Opus](https://www.opus-codec.org/static/presentations/opus_celt_aes135.pdf). Our final project code is on [GitHub](https://github.com/Abhipray/audio-codec). The slide deck is [here](Music_422_Project.pdf) and paper is [here](Music_422_Project_Report.pdf).**


## 10. Computational models of the neocortex (Tom Dean)

Tom Dean teaches this class by bringing in the latest and greatest developments in neuro-inspired AI. We covered a broad range of topics trying to lead up to an agent that can collaborate with humans using natural language. We reviewed our current understanding of how certain parts of the brain interact with each other to achieve a goal. For example, the basal ganglia is a subcortical part that works with the cortex in decision making. There are hypotheses that explain how this system works like the actor-critic model described in this [paper](https://arxiv.org/abs/1912.07660#:~:text=We%20present%20a%20computational%20and,mechanisms%20underlying%20human%20decision%2Dmaking.&text=We%20argue%20that%20by%20operating,complex%20human%20plans%20and%20decisions).

**For my final project, I did a literature survey and critical commentary on models inspired by Hebbian learning, "neurons that fire together wire together". I discovered some really cool models here, especially ones that lead to the formation of "cell assemblies", sets of tightly connected neurons that perform a task. The over-arching theme here was to find ways of mitigating catastrophic interference-- when a network learns task A, then task B, it forgets task A. Here is the [paper](CS376C_Hebbian_report.pdf).**

## 11. TinyML (Zain Asgar & Pete Warden)

The class centered around machine learning inference on embedded systems (the "edge"). We read research papers on model optimization and did assignments to implement an inference engine. 

**With Pete's mentorship, I did a final project to recognize gestures performed on the Neosensory Buzz using its onboard microphone. It used a recurrent neural network to make real-time predictions on whether there was a "double tap", "finger snap" etc. Here is a [video demo]( 
https://www.youtube.com/watch?v=eto0syTwN0U)**

## 12. Summer research (Bernard Widrow)

For two summers and any spare time I find, I have been helping Dr. Widrow write a book with a working title "Cybernetics 2.0". Just like the original Cybernetics book authored by Norbert Wiener, this book dives deep into how feedback can be used to model adaptivity and learning in living systems. It starts with Dr. Widrow's bio-inspired model for a neuron described in the paper "Hebbian-LMS". We extend the model and apply it to various homeostatic regulatory systems such as blood pressure regulation. 

**I have written simulations that have helped refine the model. Some code is available on [GitHub](https://github.com/Abhipray/hebbian_lms).**

I am also owning the editing of the book. The book includes some amazing personal stories from Dr. Widrow (who is a nonagenarian) such as encounters with Norbert Wiener, Dr. Feynman etc. If you are excited about this and want to get involved, please reach out to me. 

## 13. Convex Optimization

Convex optimization problems are searches through vector space to find the vector that satisfies some constraints and minimizes a convex objective function. A convex objective function is one that has only a single minimum (eg. $x^2$). The course armed me with tricks and techniques for noticing convex optimization problems. They are everywhere. For example, the [SpaceX rocket re-landing](https://www.youtube.com/watch?v=kURkC7R3wXY) uses a convex optimization problem solver.

## 14. How Insanely Great Products Get Built?

This was a seminar course bringing in folks from the industry to talk about their experiences. This year had a great selection of speakers which included people like Jon Rubinstein, Ted Hoff, Diane Greene, etc. It was fun getting some insider perspective on the teams that have built some revolutionary products like the iPod and the microprocessor.


## Conclusion

I have without doubt already forgotten a lot of what I learned but it's comforting to know that I can rely on my notes whenever I need to. Re-learning a concept a second time is a lot faster. 

If you are an engineer considering taking graduate-level courses, I can't recommend it enough! It was a tremendously challenging but rewarding journey. If you have any questions about my experiences, feel free to reach out to me. 