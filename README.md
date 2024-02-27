# Long-term optical imaging of the spinal cord in awake, behaving animals: design files and microCT data

Design files, microCT data, and documentation related to spinal cord imaging methods developed in the Basbaum Lab by [Biafra Ahanonu](https://bahanonu.com/) and [Andrew Crowther](https://profiles.ucsf.edu/andrew.crowther).
- Preprint: Ahanonu and Crowther, _et al_. (2023). _Long-term optical imaging of the spinal cord in awake, behaving animals_. bioRxiv (https://www.biorxiv.org/content/10.1101/2023.05.22.541477v1.full). Abstract below.
- See code for imaging processing at https://github.com/bahanonu/ciatah.

> Advances in optical imaging approaches and fluorescent biosensors have enabled an understanding of the spatiotemporal and long-term neural dynamics in the brain of awake animals. However, methodological difficulties and the persistence of post-laminectomy fibrosis have greatly limited similar advances in the spinal cord. To overcome these technical obstacles, we combined in vivo application of fluoropolymer membranes that inhibit fibrosis; a redesigned, cost-effective implantable spinal imaging chamber; and improved motion correction methods that together permit imaging of the spinal cord in awake, behaving mice, for months to over a year. We also demonstrated a robust ability to monitor axons, identify a spinal cord somatotopic map, perform months-long freely moving imaging, conduct Ca2+ imaging of neural dynamics in behaving animals responding to pain-provoking stimuli, and observe persistent microglial changes after nerve injury. The ability to couple neural activity and behavior at the spinal cord level will drive insights not previously possible at a key location for somatosensory transmission to the brain.

![image](https://github.com/basbaumlab/spinal_cord_imaging/assets/5241605/b3abd949-ef4e-4de2-8f9a-ba58e13d1ce8)

## Contents

- [3D murine skeletal models (microCT)](#3d-murine-skeletal-models-microct)
- [Spinal chamber design files](#spinal-chamber-design-files)
- [3D printing](#3d-printing)
- [CAD software](#cad-software)
- [Motion correction methods](#motion-correction-methods)
- [Questions](#questions)
- [License](#license)
- [References](#references)

Contact: __Biafra Ahanonu, PhD (github [at] bahanonu [dot] com)__ and __Andrew Crowther, PhD (andrew.crowther [at] ucsf [dot] edu)__.

Made in USA.<br>
<img src="https://user-images.githubusercontent.com/5241605/71493809-322a5400-27ff-11ea-9b2d-52ff20b5f332.png" align="center" title="USA" alt="USA" width="auto" height="50">

## 3D murine skeletal models (microCT)
![2023_02_27_test03-3](https://github.com/bahanonu/ciatah/assets/5241605/fa1c9717-99ad-4b6e-bc47-0346de7ce275)

The repository includes a 3D model of an entire mouse (C57/BL6 from JAX) skeleton to help facilitate designing of surgical components and other analysis of the spinal cord and brain. This model is displayed above with spinal chamber components. Files can be found in the directory below. 

- STL: `data\microCT\microCT_mouse_fullbody_scan_processed.stl`
- TIFF: `data\microCT\microCT_mouse_fullbody_scan_processed.stl`

We recommend setting coordinate origin points to bregma or lambda once the STL files are loaded in the CAD model of choice to facilitate easier placement of components in line with stereotaxic coordinates.

## Spinal chamber design files

The STEP and STL files can be used for laser cutting (after conversion, e.g. to DXF file), 3D printing, and for planning surgeries using CAD software.

### Side bars and stabilizing plate
![image](https://github.com/basbaumlab/spinal_cord_imaging/assets/5241605/a1c272cb-647a-485c-bfa3-e9be856ba39b)

The repository contains design files for the side bars and stabilizing plate. The stabilizing plate has several different designs depending on user needs in terms of optical access or footprint if other devices will be placed on the stabilizing plate. The stabilizing plate files can be found at:
```
design_files\stabilizing_plate
```

The side bars files can be found below. Note that `sidebar_design01_3dprinter` files are for 3D printing, see below for additional details.
```
design_files\side_bar
```

### Cover
![image](https://github.com/basbaumlab/spinal_cord_imaging/assets/5241605/03497db5-7921-4b6c-8964-6fb1c34c340b)

The cover allows users to protect the spinal imaging window in a manner that is quick to remove. It uses circular neodymium magnets (https://www.mcmaster.com/5862K141/) to snap onto the ferromagnetic mild steel used for the stabilizing plate. It is concave to provide space in case devices are placed at the imaging site or if the final window is not flush with the stabilizing plate.  The cover files are located at:

```
design_files\cover
```

### Laser cutting
Laser cutting is a cost-effective method for making many of the components for the spinal chamber. Users can work with most companies that offer laser cutting services. For the paper, we mainly worked with Laser Alliance LLC (https://laseralliance.com/). See below for materials that can be used or requested when laser cutting.

- Stabilizing plate: 0.75-mm (~1/32'') thick mild steel
- Thin side bars (preferred): https://www.mcmaster.com/8983K111/
- Thick side bars: https://www.mcmaster.com/8983K113/

## 3D printing
![image](https://github.com/basbaumlab/spinal_cord_imaging/assets/5241605/ad7e1cc7-d92a-4736-9400-a56065f26dc8)

There are slightly different design considerations for 3D printing if need non-metallic materials for compatibility with microCT, MRI, or other modalities. We found biocompatible 3D printed materials can work and are compatible with microCT imaging (see above or below microCT slices and 3D reconstruction). However, these spinal chamber components often need to be thicker due to the lower strength of the materials compared to steel.

- `Surgical Guide` - https://dental.formlabs.com/store/materials/surgical-guide-resin/
- `BioMed Clear` - https://formlabs.com/store/materials/biomed-clear-resin/


### Metal 3D printing
Metal 3D printing is an alternative to laser cutting and grinding or 3D printing as above. See below for a list of several companies that offer metal 3D printing services. We have found the spinal chamber components can be printed with titanium, stainless steel, or other metals depending on needs.

- https://i.materialise.com/en/3d-printing-materials
- https://www.protolabs.com/services/3d-printing/direct-metal-laser-sintering/
- https://www.shapeways.com/3d-print-material-technology/slm
- https://www.xometry.com/capabilities/3d-printing-service/metal/

## CAD software

For loading the STL and STEP files, there are a variety of CAD programs, some are listed below. These can also be used to make assemblies of the mouse skeleton and spinal chamber components along with any other 3D models needed to design new experiments.

- PTC Creo (https://www.ptc.com/en/products/creo)
- AutoDesk Fusion 360 (https://www.autodesk.com/products/fusion-360/overview)
- FreeCAD (https://www.freecad.org/)
- SOLIDWORKS (https://www.solidworks.com/product/solidworks-3d-cad)

## Motion correction methods

The spinal cord can have rapid and substantial (hundreds of micrometers) movement during the course of imaging. We created a workflow consisting of new and existing techniques then validated it on spinal cord data. The CIAtah repository contains these methods for motion correction of spinal imaging data using feature identification (e.g. with DeepLabCut), control point registration, and other methods. See code and documentation at:
- https://bahanonu.github.io/ciatah

![image](https://github.com/basbaumlab/spinal_cord_imaging/assets/5241605/3d33431a-a530-4b34-8533-0cd3fd81d1ae)
<div style="font-size: 0.8em;">Imaging a large spinal cord field is subject to several types of motion artifacts.</div><br><br>

![image](https://github.com/basbaumlab/spinal_cord_imaging/assets/5241605/c1ab9d49-dd8e-4df5-a5da-696ae014cf63)
<div style="font-size: 0.8em;">Modular motion correction pipeline that addresses each of the issues outlined in a: features identified using deep learning followed by control point and rigid registration (large displacement motion correction method, LD-MCM), deformation correction using displacement fields followed by rigid registration, and manual or automated cross-session motion correction (CS-MCM).</div><br><br>


## Questions?

Please email any additional questions not covered in the repository to `github [at] bahanonu [dot] com` or open an issue.


## License

Copyright (C) 2020-2024 Biafra Ahanonu and Andrew Crowther.

This project is licensed under the terms of the GPLv3 license. See LICENSE file for details.


## References

Please cite the [Ahanonu*, Crowther*, 2023](https://doi.org/10.1101/2023.05.22.541477) preprint on spinal cord imaging if you use related methods or procedures.

```bibtex
@article{ahanonu2023long,
  title={Long-term optical imaging of the spinal cord in awake, behaving animals},
  author={Ahanonu, Biafra and Crowther, Andrew and Kania, Artur and Casillas, Mariela Rosa and Basbaum, Allan},
  journal={bioRxiv},
  pages={2023--05},
  year={2023},
  publisher={Cold Spring Harbor Laboratory}
}
```

Please see https://bahanonu.github.io/ciatah/references/ for additional references depending on processing steps undertaken.