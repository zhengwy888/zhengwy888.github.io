---
layout: post
title: Neural Art Video - Yangshuo
---
Inspired by [A Neural Algorthm of Artistic Style](http://arxiv.org/abs/1508.06576), I made a video style adaption from a drone aerial of Yangshuo, Guilin. Looking at my hometown through the lens of artist is a pleasant experience.
<iframe width="560" height="315" src="https://www.youtube.com/embed/g9BxlwlQWlc" frameborder="0" allowfullscreen></iframe>
(If you are in China 墙内请戳[优酷](http://v.youku.com/v_show/id_XMTM0Mjk3OTk0NA==.html))

Some of the higher layer neural network from the original paper (conv4\_1 and conv5\_1) had to be taken out to smooth out flickering in sub regions. 
The Starry Night segment is flickering, due to the uncertainty during gradient descend. I processed the video frame by frame, thus sometimes the L-BFGS optimizer can take an entire different direction of optimizing the video. Some frames' gradient exploded and had to be retrained by hand afterward.

I hope this can provide an inspiration for the next neural art. Great thanks for the [Neural Art Torch7 repo](https://github.com/kaishengtai/neuralart).

Future Directions:
Continuous Gradient Descending exploiting the similarity between video frames
Realtime processing (a dream?)


