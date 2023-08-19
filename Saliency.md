### Vector Saliency

Saliency is a value between 0 and 1 that indicates how important a vector or a field inside a vector is. The most important ones have a value, the least important, a saliency of 0.

<mark style="background: #ABF7F7A6;">The saliency value for a vector is computed as the average of individual saliencies calculated for each of the components.</mark>

### Individual Saliencies

Individual saliencies for each value are computed relative to the window of attention. The highest value in the window will generally have a saliency value of 1, as well as the lowest one. An average value will have a saliency value of 0.

The highest volume in the current window yields a saliency of 1. The lowest has a saliency of 0.

The longest duration and the shortest one have saliencies of 1 (either long = salient or staccato = salient), and the average duration will have a saliency of 0.

Similarly for pitch - highest and lowest notes have saliency of 1, and average pitch has saliency of 0.

Derivatives follow the saliency rules as the components they come from.

### Pre-Saliency

Based on the average of these saliencies, each note gets a _pre-saliency_ value, which is used to compute the periodicity of the input. This can lead the computer to expect salient notes at specific times if it has been seeing them periodically. Hence, if falling on a periodically salient time, even a silence could appear important.

### Saliency Maps

We have thus constructed many saliency maps. One can pay attention to notes salient in volume, or in pitch, or in duration, or in their derivatives. The pattern matcher also computes a periodicity saliency map, which gives a value of 1 to notes expected to be salient, and a 0 to the non-salient ones. Together with the pre-saliency values, this final addition constitutes the saliency part of the code.
![[Pasted image 20230723110018.png]]