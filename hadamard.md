# Hadamard Encoding

ASL with multiple delays can fully describe the dynamic perfusion signal by quantifing arterial transit time, which results in more accurate CBF measurement. However, multi-delay measurement is time consuming. 

Guenther introduced the Hadamard encoding ASL on ISMRM 2007 [^1]. The idea is to devide a long labeling blood bolus into a few small sub-boli, and each sub-boli can have different PLDs. In the original ISMRM abstract and Wells et al.'s work [^2], a natural-order Hadamard encoding matrix with an order of 8 was used. While the Hadmard encoding matrix was mirrored and the first colume was removed to acheive 'ASL condition'. This design is detailed as following:

```python
import numpy as np
from scipy.linalg import hadamard
E = hadamard(8)*-1 # mirror the encoding matrix
E = E[:,1:] # remove the first column
print('encoding matrix: ',E)
D = np.transpose(E)
print('decoded ASL:', D@E)
```
where E is the encoding matrix, or the sequence to acquire ASL images. D is the decoding matrix to reconstruct the ASL images with designed LD and PLD. The output is 
```
encoding matrix:  
[[-1 -1 -1 -1 -1 -1 -1]
 [ 1 -1  1 -1  1 -1  1]
 [-1  1  1 -1 -1  1  1]
 [ 1  1 -1 -1  1  1 -1]
 [-1 -1 -1  1  1  1  1]
 [ 1 -1  1  1 -1  1 -1]
 [-1  1  1  1  1 -1 -1]
 [ 1  1 -1  1 -1 -1  1]]
decoded ASL:
[[8 0 0 0 0 0 0]
 [0 8 0 0 0 0 0]
 [0 0 8 0 0 0 0]
 [0 0 0 8 0 0 0]
 [0 0 0 0 8 0 0]
 [0 0 0 0 0 8 0]
 [0 0 0 0 0 0 8]]
 ```
 
 The bolus duration can be non-equal [^2] as presented by Wells et al [^2] and van Osch et al's work [^3]. 

[^1]: M. Guenther. Highly efficient accelerated acquisition of perfusion inflow series by Cycled Arterial Spin Labeling. ISMRM 2007;0380
[^2]: Wells JA, Lythgoe MF, Gadian DG, Ordidge RJ, Thomas DL. In vivo Hadamard encoded continuous arterial spin labeling (H-CASL). Magn. Reson. Med. 2010;63:1111–1118 doi: 10.1002/mrm.22266.
[^3]: van Osch MJ, Teeuwisse WM, Chen Z, Suzuki Y, Helle M, Schmid S. Advances in arterial spin labelling MRI methods for measuring perfusion and collateral flow. J. Cereb. Blood Flow Metab. 2018;38:1461–1480 doi: 10.1177/0271678X17713434
