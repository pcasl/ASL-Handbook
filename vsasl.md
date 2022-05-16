# Velocity Selective ASL (VSASL)

In the early years of ASL development, arterial transit time (ATT) is a major problem. It introduces error in the CBF quantification and reduces the SNR of ASL images. Besides techniques to correct the ATT effects, another idea is to reduce or eleminate the ATT. Since ATT is mainly caused by the distance between labeling plane and imaging plane, Eric Wong et al. proposed one of the earliest work to label the blood inside the image slab by selecting a certain flow velocity, instead of a separate labeling location.

The idea of velocity labeling was introduced by Norris et al. in 1999 [^1]. Based on the idea from spectrum selective RF design, graidents are introduced among RFs to acheive saturation and inversion for a certain range of velocity.

In 2002, a 90x-G-180y-G-90-x labeling pulse was introduced into ASL [^2]. The gradients were designed to remove and so as to label the flow above 1cm/s in the label images. In the control images, the gradients were turned off so that the high-velocity blood was preserved. Therefore, the difference of the two images was generated to show the high velocity blood effect. In the acquistion, the same velocity cutoff was used and therefore, only low-velocity flow is imaged. By a cobination of high-velocity-label and low-velocity-image scheme, this method presents a contrast from the blood that decelerates across the cutoff velocity. 

As mentioned by the authors, the major advantage of the VSASL is the insensitivity to the ATT. However, the major disadvatages are reduced labeling efficiency (only saturation was achieved) and motion sensitivity.  

In 2003, two modifications were added to the above pulse train: a BIR4 pulse to improve the B1 robustness and lower flip angle to use hyperechos [^3]. However, the improvements of the new design was not clear. The authors claimed the motion is not problem, since most bulk motion is below 1cm/s which contains little effects from the labeling part. 

[^1]: Norris DG, Schwarzbauer C. Velocity selective radiofrequency pulse trains. J. Magn. Reson. 1999;137:231–236 doi: 10.1006/jmre.1998.1690.
[^2]: Wong E, Liu T, Sidaros K, Frank L, Buxton R. Velocity Selective Arterial Spin Labeling. In: ISMRM; 2002. p. 0621.
[^3]: Wong E, Cronin M. Velocity Selective Arterial Spin Labeling using an Adiabatic Hyperecho Pulse Train. In: ISMRM; 2003. p. 2181.