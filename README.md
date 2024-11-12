# Long-term optical imaging of the spinal cord in awake behaving mice

Design files, microCT data, and documentation related to spinal cord imaging methods developed in the Basbaum Lab by [Biafra Ahanonu](https://bahanonu.com/) and [Andrew Crowther](https://profiles.ucsf.edu/andrew.crowther).
<!-- - Preprint: Ahanonu*, Crowther*, _et al_. (2023). _Long-term optical imaging of the spinal cord in awake, behaving animals_. bioRxiv (https://www.biorxiv.org/content/10.1101/2023.05.22.541477v1.full). Abstract below. -->
- B. Ahanonu*, A. Crowther*, A. Kania, M. Rosa-Casillas, A.I. Basbaum. (2024). Long-term optical imaging of the spinal cord in awake behaving mice. _Nature Methods_. https://doi.org/10.1038/s41592-024-02476-3 (https://www.nature.com/articles/s41592-024-02476-3)
- See code for imaging processing at https://github.com/bahanonu/ciatah.

> Advances in optical imaging and fluorescent biosensors enable study of the spatiotemporal and long-term neural dynamics in the brain of awake animals. However, methodological difficulties and fibrosis limit similar advances in the spinal cord. Here, to overcome these obstacles, we combined in vivo application of fluoropolymer membranes that inhibit fibrosis, a redesigned implantable spinal imaging chamber and improved motion correction methods that together permit imaging of the spinal cord in awake behaving mice, for months to over a year. We demonstrated a robust ability to monitor axons, identified a spinal cord somatotopic map, performed months-long imaging in freely moving mice, conducted Ca2+ imaging of neural dynamics in behaving mice responding to pain-provoking stimuli and observed persistent microglial changes after nerve injury. The ability to couple in vivo imaging and behavior at the spinal cord level will drive insights not previously possible at a key location for somatosensory transmission to the brain.

![image](https://github.com/basbaumlab/spinal_cord_imaging/assets/5241605/b3abd949-ef4e-4de2-8f9a-ba58e13d1ce8)

## Contents

- [3D murine skeletal models (microCT)](#3d-murine-skeletal-models-microct)
- [Running wheel and rotary encoder](#running-wheel-and-rotary-encoder)
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
![image](https://github.com/bahanonu/ciatah/assets/5241605/fa1c9717-99ad-4b6e-bc47-0346de7ce275)

The repository includes a 3D model of an entire mouse (C57/BL6 from JAX) skeleton to help facilitate designing of surgical components and other analysis of the spinal cord and brain. This model is displayed above with spinal chamber components. Files can be found in the directory below.

- STL: `data\microCT\microCT_mouse_fullbody_scan_processed.stl`
- TIFF: `data\microCT\microCT_mouse_fullbody_scan_processed.stl`

We recommend setting coordinate origin points to bregma or lambda once the STL files are loaded in the CAD software of choice to facilitate easier placement of components in line with stereotaxic coordinates. Also, use the bregma-lambda distance to confirm that the units are correct after import, else scale the model to achieve the correct size.

## Running wheel and rotary encoder
![image](https://github.com/basbaumlab/spinal_cord_imaging/assets/5241605/3f8b98aa-7a7c-434e-9984-c1209bb30165)

The running wheel design allows delivery of sensory stimuli to animals' paws while they are awake (left panel above). We use an infrared (IR) transmitting acrylic sheet that allows use of IR lights and cameras to monitor the animal while keeping the surface visibly black. This has multiple advantages over visibly clear acrylic for animal behavior and stimulus delivery. We then laser cut the above design (e.g. using a `ULS V3.50 Laser Cutter`); the different colors for the hexagons indicate the relative order in which they will be cut (middle panel above), this allows more even heat dissipation during the run and reduces the chance the acrylic will become warped. We use a 3D printed piece to connect the rotary encoder to the running wheel (right panel above).

- Design files
  - Running wheel (Illustrator): `design_files\running_wheel\runningWheel.ai`.
    - Remember to change the weight of the lines to match what is required for the laser cutter being used.
    - Layout based on aluminum sheet used for freely moving imaging and behavior: https://www.mcmaster.com/92725T51/.
  - 3D printed rotary encoder to running wheel: `design_files\running_wheel\encoder_to_wheel_attach.stp`.
- Materials and devices
  - Infrared transmitting acrylic: https://www.eplastics.com/ACRY31430-125PM11-555X11-850.
  - Rotary encoder: https://www.amazon.com/Signswise-Incremental-Optical-Encoder-Quadrature/dp/B00Y9KDDCY.
  - Brass insert for 1/4-20 screws: https://www.mcmaster.com/92395A116/.
    - This can heat set into the 3D printed part that connects to the rotary encoder.

## Spinal chamber design files

The STEP and STL files can be used for laser cutting (after conversion, e.g. to [DXF file](https://en.wikipedia.org/wiki/AutoCAD_DXF)), 3D printing, and for planning surgeries using CAD software.

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

There are slightly different design considerations for 3D printing if non-metallic materials are needed for compatibility with microCT, MRI, or other imaging modalities. We found that biocompatible 3D printed materials can work and are compatible with microCT imaging (see above or below microCT slices and 3D reconstruction). However, these spinal chamber components often need to be thicker due to the lower strength of the materials compared to steel or other metals.

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
<div style="font-size: 0.8em;">Modular motion correction pipeline that addresses each of the issues outlined in a: features identified using deep learning followed by control point and rigid registration (large displacement motion correction method, LD-MCM), deformation correction using displacement fields followed by rigid registration, and manual or automated cross-session motion correction (CS-MCM).</div>

## Questions?

Please email any additional questions not covered in the repository to `github [at] bahanonu [dot] com` or open an issue.


## License

Copyright (C) 2020-2024 Biafra Ahanonu and Andrew Crowther.

This project is licensed under the terms of the GPLv3 license. See LICENSE file for details.


## References

Please cite the [Ahanonu*, Crowther*, 2024](https://doi.org/10.1038/s41592-024-02476-3) _Nature Methods_ paper on spinal cord imaging if you use related methods or procedures.

```bibtex
@article{Ahanonu2024-wq,
  title     = "Long-term optical imaging of the spinal cord in awake behaving
               mice",
  author    = "Ahanonu, Biafra and Crowther, Andrew and Kania, Artur and
               Rosa-Casillas, Mariela and Basbaum, Allan I",
  journal   = "Nat. Methods",
  publisher = "Springer Science and Business Media LLC",
  pages     = "1--13",
  month     =  nov,
  year      =  2024,
  language  = "en"
}

```
<!-- Please cite the [Ahanonu*, Crowther*, 2023](https://doi.org/10.1101/2023.05.22.541477) preprint on spinal cord imaging if you use related methods or procedures. -->
<!-- @article{ahanonu2023long,
  title={Long-term optical imaging of the spinal cord in awake, behaving animals},
  author={Ahanonu, Biafra and Crowther, Andrew and Kania, Artur and Casillas, Mariela Rosa and Basbaum, Allan},
  journal={bioRxiv},
  pages={2023--05},
  year={2023},
  publisher={Cold Spring Harbor Laboratory}
} -->

Please see https://bahanonu.github.io/ciatah/references/ for additional references depending on processing steps undertaken.