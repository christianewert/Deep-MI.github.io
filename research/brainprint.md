---
title: BrainPrint
layout: default
group: research
---

# BrainPrint - Neuroanatomical Shape Analysis

Our BrainPrint tools provide shape descriptors of neuroanatomical structures and require a FreeSurfer or
[FastSurfer](/research/fastsurfer/) segmentation as a pre-processing step.
BrainPrint is based on "ShapeDNA" a spectral shape descriptor that is well suited for the analysis of non-rigid
bendable shapes like biological structures.

## Spectral Shape Analysis

In spectral shape analysis we employ the spectrum of the Laplace-Beltrami operator as a shape descriptor for the analysis of
shape differences. The main advantage is that this descriptor is isometry invariant. Isometry invariance means that distances
measured along the surface stay the same. So a hand with different finger positions or a person in different body postures
will be (near) isometric, as not much streching is involved. The distance from the nose to the foot is fixed for different
body postures, if measured along the surface (as opposed to measuring it in the embedding space).
Thus we are able to identify similar deformable objects even if they cannot be aligned/compared with a rigid transformation!

<img src="/static/img/research/brainprint/01_eigenmode.png" class="responsive" alt="Eigenmode" style="
	display: block;
	margin-left: auto;
	margin-right: auto;
  width: auto;
  max-width: 600px;
  height: auto;
">
<div  style="text-align: justify; width:600px; margin:0 auto;"> Fig 1. First non-constant eigenmode for similar shapes. Red and blue dots at the tips denote
the extrema, the green curves are some level sets. The Reeb graph (gray curve) approximates the medial axis.
</div>

<img src="/static/img/research/brainprint/02_registration.png" class="responsive" alt="Registration" style="
	display: block;
	margin-left: auto;
	margin-right: auto;
  width: auto;
  max-width: 600px;
  height: auto;
">
<div  style="text-align: justify; width:600px; margin:0 auto;">
Fig 2. Registration of segments across near isometric shapes. Same color indicates registered
parts across poses of the same model.
</div>

## BrainPrint

We have extended this work to analyze brain shape changes (with respect to symmetry, heritability, computer-aided diagnosis
of neurodegenerative disease, etc). The code for the <em> BrainPrint</em> tools is available on [github](https://github.com/Deep-MI/BrainPrint).

<img src="/static/img/research/brainprint/03_brainprint.png" class="responsive" alt="BrainPrint" style="
	display: block;
	margin-left: auto;
	margin-right: auto;
  width: auto;
  max-width: 600px;
  height: auto;
">
<div  style="text-align: justify; width:600px; margin:0 auto;"> Fig 3. Overview of the computation of the BrainPrint. First, MRI scans are processed with
FreeSurfer to obtain segmentations of cortical and subcortical structures. Second, a mesh is created for each brain structure.
Third, the <em>ShapeDNA</em> is computed for all meshes, constituting the <em>BrainPrint</em>.
</div>

<img src="/static/img/research/brainprint/04_asymmetry.png" class="responsive" alt="Asymmetry" style="
	display: block;
	margin-left: auto;
	margin-right: auto;
  width: auto;
  max-width: 600px;
  height: auto;
">
<div  style="text-align: justify; width:600px; margin:0 auto;">
Fig 4. Based on a brain segmentation, we create meshes from lateralized structures, e.g. the
hippocampus. The computation of the shape descriptor <em>ShapeDNA</em> yields the characteristic spectrum of the shape, which forms the
<em>BrainPrint</em>. The Mahalanobis distance between the spectra of both hemispheres results in the shape asymmetry.
</div>

<!--- More details needed, also links to github code and short doc on how to use -->

## Selected Publications and Links

<!--- include after these exist in publication list
 - [BrainPrint: A Discriminative Characterization of Brain Morphology. C.Wachinger, ..., M.Reuter. NeuroImage 109:232-248, 2015.](/publications/#reuter_2015)
 - [Laplace-Beltrami spectra as "Shape-DNA" of surfaces and solids. M. Reuter, F.-E. Wolter and N. Peinecke. Computer-Aided Design 38(4):342-366, 2006.](/publications/#reuter_2006)
-->

 - BrainPrint: A Discriminative Characterization of Brain Morphology. C.Wachinger, ..., M.Reuter. NeuroImage 109:232-248, 2015. [doi:10.1016/j.neuroimage.2015.01.032](http://dx.doi.org/10.1016/j.neuroimage.2015.01.032)
 - Laplace-Beltrami spectra as "Shape-DNA" of surfaces and solids. M. Reuter, F.-E. Wolter and N. Peinecke. Computer-Aided Design 38(4):342-366, 2006. [doi:10.1016/j.cad.2005.10.011](http://dx.doi.org/10.1016/j.cad.2005.10.011)
