## About

Modern Siemens MRI scanners can embed physiological recordings into DICOM files. Recent versions of dcm2niix (since v1.0.20260603) attempt to convert these to [BIDS TSV format](https://bids-specification.readthedocs.io/en/stable/modality-specific-files/physiological-recordings.html). This validation repository includes sample images from a Siemens 3T Vida running XA60.

## Running

Run `batch.sh`. It converts `In/` → `Out/` and diffs against `Ref/`. Requires dcm2niix v1.0.20260603 or later.

## Notes

This repository includes a Python script (`viewtsv`) to visualize TSV data (requires `numpy` and `matplotlib`):

```bash
python viewtsv ./Ref/func-bold_task-rest_acq-dualecho_run-1_dicom_8_recording-respiratory_physio.tsv.gz
python viewtsv ./Ref/func-bold_task-rest_acq-dualecho_run-1_dicom_8_recording-cardiac_physio.tsv.gz
```

![tsv graph](physio.png)

When you set up sequences, make sure you have selected to log physiological signals and are saving these logs as DICOM files.

![setup physio logging](log.png)
![make sure logs are saved as DICOM](log2dicom.png)
