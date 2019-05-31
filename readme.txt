RMmodel.hoc
The set of .mod files and the hoc file included here implement the models
described for ventral cochlear nucleus neurons in the series of papers by
Rothman and Manis (2003a,b,c; hereafter refered to as R&M). The equations for
each channel type are implemented in separate .mod files. Please note that the
models for IA, IHT and ILT are based on actual measurements in isolate
well-voltage clamped guinea pig VCN neurons, as described in R&M, 2003b. The
models for INa and Ih are based on average kinetic measurements of those
conductances in other cell types (see R&M, 2003c), and are included as a matter
of convenience and completeness.

The files named "klt_kinetics.hoc", "kht_kinetics.hoc", "ia_kinetics.hoc", "na
kinetics.mod" and "ih_kinetics.hoc" use only one (plus a passive conductance)
channel to show the voltage dependence of the kinetics, the effect of the
conductance on a current-clamp pulse in an otherwise passive cell, and the
voltage clamp behavior over a range of voltages. These are mainly to confirm the
behavior of the models.

The file RMmodel.hoc reproduces traces in Figures 2, 3 and 4 of Rothman and
Manis, 2003c. While the results are very close to the original models (which, in
the paper, were run in ACSL, not NEURON, although the general behavior was
verified in NEURON), in a few cases they are not identical. In particular, in
Figure 2D, the "type I-II" model fires 2 action potentials in response to +100
pA depolarizations, however the NEURON model only fires one action potential
followed by a subthreshold wavelet. Increasing the depolarization to +102 pA
is sufficient to reproduce the result in the paper (you can verify this by
selecting the model from the "Full IV Model Selection" button, entering 102 into
the "IV max  (pA)" box, 3 into the "# IV steps" box, and then hitting the "Run"
button) . Such differences may arise from the different integration methods
(unlikely here), or from small differences in the initial conditions for the
models in the different simulation environments.

To enable some generality to these models, an "IV" mode is included. To use this
, select the model, and set the IV max current and the number of steps. The
model cell will then be presented with -imax to +imax current steps. You can use
this to explore, for example, the range over which the intermediate cell classes
(type II-I and type I-II fire 1, 2, 3 or a train of action potentials, depending
on the size of the low threshold conductance.

Also included is a "type II-o" model, which is not in the original papers
reached from the Full IV Model Selection" menu. This is modified, hybrid Type II
model, with a very large low threshold potassium conductance, coupled with the
Milgore (see NeuronDB) implementation of the Ih meausrements of Bal and Oertel,
2000 (hcno.mod). The model is designed to approximate a posterior ventral
cochlear nucleus Octopus neuron. For comparison with published studies, it will
be necessary to change the temperature in NEURON from 22 to 33 deg. C (Tools ->
Distributed Mechanisms -> Celsius).

Any questions regarding these implementations should be directed to:
pmanis@med.unc.edu

2 April 2004
Paul B Manis, Ph.D.

