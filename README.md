# EXFOR C4 File (C4)
The EXFOR C4 File is the [EXFOR Entry File](https://nds.iaea.org/nrdc/exfor-master/entry/) converted to C4 (Computational Format) by ForEXy [1].

**Download**
- download the zipped file of the current version from the [EXFOR C4 File](https://nds.iaea.org/nrdc/exfor-master/c4/) website, or
- download the full repository using the terminal command:
```
git clone https://github.com/iaea-nrdcnetwork/exfor-c4-file.git
```

**Contents**

The following quantities are within the scope of these libraries:

* cross section (incl. gamma production)
* angular differential cross section (incl. gamma production)
* energy differential cross section (incl. gamma production)
* double differential cross section
* fission neutron multiplicity
* fission product yield

for any projectiles and reactions not leaving two or more heavy (A>4) nuclides.

The data lines follow the C4 format defined in the X4TOC4 manual [2] in general, but with slightl modification (e.g., MF8 instead of MF18 for FPY, MF202-207, 454 and 459 instead of MF9000 for particle and nuclide productions).

The comment lines (starting from #) added before and after the data lines follow the "Full EXFOR in XC4 format"[4] designed by Viktor Zerkin except for the counters following #DATASETS and #DATA in the header part. They are always set to zero in C4Lib. (Inform me if you need to have actual numbers there!)

One file corresponds to one subentry. If there are several running variables (e.g., incident energy and angle for angular differential cross sections), the dataset is separated to "blocks" so that each part has one running variable. For example, angular distribution data at three incident energies in a subentry are stored in three blocks.

*Examples*
* `d/D4408.005-a-Ni-x-sig-excfun-mon-Takacs_2020.c4`:
Same as the 1st example of the C6Lib file.

* `1/10037.024-n-Fe56-el-adxc-angdisc-mon-Boschung_1971.c4`:
Same as the 2nd example of the C6Lib file, but it also includes the data at 5.58 MeV.

* `c/C0841.008-p-Bi209-xn-ddxl-enedisl-mon-Kalend_1983.c4`:
Same as the 3rd example of the C6Lib file, but also includes the data at 30, 45, 60 and 90 deg.

C4 files are stored in a subdirectory of the projectile/geographical area (i.e., 1/ for neutron data from USA and Canada).


## Abbreviations in C4Lib file names
### Isomeric state
An isomeric state is indicated by

* g: ground state production (G)
* m: first metastable state production (M or M1)
* n: second metastable state production (M2)
* p: ground + first metastable state production (G+M1)
* q: ground + second metastable state production (G+M2)
* r: first + second metastable state production (M1+M2)

*Example*
 "Au196n" is for 196m2Au (9.6 h) while "Au196p" is for the sum of 196gAu (6.2 d) and 196g1Au (8.1 s).


### Physical quantity
* adxc: angular differential cross section in c.m. system
* adxl: angular differential cross section in lab. system
* ddxc: double differential cross section in c.m. system
* ddxl: double differential cross section in lab. system
* edxc: energy differential cross seciton in c.m. system
* edxl: energy differential cross seciton in lab. system
* sig:  cross section
* sigc: cross section (cumulative)
* fyc:  fission product yield (cumulative)
* fyi:  fission product yield (independent)
* nud:  fission neutron multiplicity (delayed)
* nup:  fission neutron multiplicity (prompt)
* nut:  fission neutron multiplicity (total)


### Distribution (running variable)
* angdisc: c.m. angle dependence
* angdisl: lab. angle dependence
* enedisc: c.m. outgoing energy dependence
* enedisl: lab. outgoing energy dependence
* excfun:  incident energy dependence
* lvldis:  level energy dependence
* nucdis:  product nuclide dependence
* othdis:  other distribution (probably indication of processing error!)
* sponnu:  spontaneous fission neutron multiplicity


### Incident particle spectrum
* brs:  bremsstrahlung spectrum average and unfolded
* fis:  fission neutron spectrum field
* mon:  mono energetic field
* mxw:  Maxwellian field
* sdt:  slow-down time spectrometer field
* spa:  averaged over a spectrum with  <E>~0.0253 eV or narrow energy width


### Constant
* angc: c.m. angle
* angl: lab. angle
* elvl: excitation energy (of product)
* enec: c.m. outgoing energy
* enel: lab. outgoing energy
* prod: product


### Author name
A blank and "-" in author's name are replaced by "%" and "+" in the file name (e.g., "Abd%El+Kariem" for "Abd El-Kariem".)


## References
1. N.Otuka, V.Devi, O.Iwamoto, [Appl.Radiat.Isot.225(2025)111903](https://doi.org/10.1016/j.apradiso.2025.111903).
2. D.E.Cullen and A.Trkov, "Program X4TOC4 (Version 2001-3)", [Report IAEA-NDS-80 Rev.](https://doi.org/10.61092/iaea.tvbj-sa2z), International Atomic Energy Agency.
3. V.Zerkin, "Full EXFOR in C4 format: delivery to WPEC group SG-30", Working Paper [WP2008-37](https://nds.iaea.org/nrdc/nrdc_2008/working/wp2008-37.pdf), Technical Meeting of the International Network of Nuclear Reaction Data Centres IPPE, Obninsk and Moscow State University, Moscow, Russian Federation 22 - 25 September 2008].
