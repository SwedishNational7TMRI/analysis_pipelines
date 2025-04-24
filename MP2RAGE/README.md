# T1-mapping with MP2RAGE and DREAM

## Converting DICOM to Nifti

### MP2RAGE
With the MP2RAGE dicoms inside a folder called `DICOM`, convert to nifti and put in folder called `nifti` using

```sh
dcm2niix -p n -o ./nifti DICOM
```

If magnitude, real and imaginary data was reconstructed, there should be three images in the `nifti` folder

- `<prefix>.nii`
- `<prefix>_imaginary.nii`
- `<prefix>_real.nii`

We will only use the `_imaginary.nii` and `_real.nii` images for MP2RAGE processing.

### DREAM
With the MP2RAGE dicoms inside a folder called `DICOM`, convert to nifti and put in folder called `nifti` using

```sh
dcm2niix -p n -o ./nifti DICOM
```

This will produce 4 images

- `<prefix>_e1.nii`: FID image. Use this as an anatomical reference when co-registering DREAM and MP2RAGE
- `<prefix>_e1_ph.nii`: B1 phase image
- `<prefix>_e1a.nii`: B1-map, use this for B1-correction of MP2RAGE. In units of percentage of nominal B1.
- `<prefix>_e2.nii`: STEAM image

