---
layout: post
title: Deep Neural Network's Discrimination Against Color
---
<p>Maybe I mislead you with the title. Machine learning only knows how to distinguish pictures from features that they were trained on. And this is a good example to show that limitation. </p>
<p>I attended a meetup for deep learning a while back. And it was very cool to see the demo for image classifier where an image can be classified with the objects in it, using a trained 'neural network'. For people who are not familiar with machine learning, you can consider 'neural network' to be exactly what it sounds like: a bunch of neurons connected to each other, passing signals along, except this is all written in software. Training the neural network means feeding some dataset to the network, let it do its calculation, compare the results to the expected output and update the network so hopefully nextime, the error can be reduced. </p>
<p>For a quick start I decided to use an existing Amazon AWS instance and an established tool, Caffe [1]. There is a publicly available state-of-the-art model from ILSVRC 2012, which was trained to classify images into 1000 different classes. To say state-of-the-art, it means it can achieve 'top-5 accuracy 80.4% on the validation set' [2]. In plain English, it means it was able to predict a top 5 list which includes the correct answer 80% of the time.</p>
<p>I started with their example, it was classified, and indeed correctly, a tabby cat. The prediction confidence was slightly less than 0.4.</p>
<p><img src="/content/images/2015cats/cat.png"  ></p>
<p>But there is a greyscaled version of the same picture sitting in the example folder. What happens if I feed it to the classifier? </p>
<p><img src="/content/images/2015cats/cat_grey.png"  ></p>
<p>Out comes a great confidence, 0.7. But to my disappointment, it thinks this is a <strong>hamster</strong>. For a human it's very easy to tell this is a definitely a cat. What is wrong with this fansy classifier? </p>
<p>I did a quick search online for hamster images, then the reason was very clear. Given the ILSVC 2012 training set was from online pictures, most of the hamsters in the top search results have black and white fur color. The computer didn't encounter any black and white 'tabby cat' picture, thus the mistake. </p>
<p><img src="/content/images/2015cats/hamster.png"></p>
<p>[<a href="https://www.google.com/search?q=hamster&amp;safe=off&amp;source=lnms&amp;tbm=isch&amp;sa=X&amp;ei=YOA1VcC4Mc64oQSw7YGgAg&amp;ved=0CAcQ_AUoAQ&amp;biw=1298&amp;bih=695">google</a>]</p>
<p>A flamingo was categorized correctly when showned with color. But when turned into greyscale, the computer told me it's a <strong>spoonbill</strong>. What is that?</p>
<p><img src="/content/images/2015cats/flamingo_grey.png"  ></p>
<p>It's almost a black and white version of flamingo. Wow, time to learn some more biology to catch up with the computers!</p>
<p><img src="/content/images/2015cats/spoonbill.png"></p>
<p>[<a href="https://www.google.com/search?safe=off&amp;biw=1298&amp;bih=695&amp;tbm=isch&amp;sa=1&amp;q=spoonbill&amp;oq=spoonbill&amp;gs_l=img.3..0l10.39246.41070.0.41312.9.9.0.0.0.0.150.718.2j4.6.0.msedr...0...1c.1.64.img..3.6.715.TY1gP4Y_YGU#imgrc=_">google</a>]</p>
<p></p>
<p>[1]https://github.com/BVLC/caffe</p>
<p>[2]https://github.com/BVLC/caffe/tree/master/models/bvlc_reference_caffenet</p>