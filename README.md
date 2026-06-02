[![DOI](https://img.shields.io/badge/DOI-10.82901%2Fnemar.nm000199-blue)](https://doi.org/10.82901/nemar.nm000199)

# Learning from label proportions for a visual matrix speller (ERP)

Learning from label proportions for a visual matrix speller (ERP) dataset from Hübner et al 2017 [1]_.

## Dataset Overview

- **Code**: Huebner2017
- **Paradigm**: p300
- **DOI**: 10.1371/journal.pone.0175856
- **Subjects**: 13
- **Sessions per subject**: 3
- **Events**: Target=10002, NonTarget=10001
- **Trial interval**: [-0.2, 0.7] s
- **Runs per session**: 9
- **Session IDs**: session_1
- **File format**: BrainVision

## Acquisition

- **Sampling rate**: 1000.0 Hz
- **Number of channels**: 31
- **Channel types**: eeg=31, misc=6
- **Channel names**: C3, C4, CP1, CP2, CP5, CP6, Cz, EOGvu, F10, F3, F4, F7, F8, F9, FC1, FC2, FC5, FC6, Fp1, Fp2, Fz, O1, O2, P10, P3, P4, P7, P8, P9, Pz, T7, T8, x_EMGl, x_GSR, x_Optic, x_Pulse, x_Respi
- **Montage**: standard_1020
- **Hardware**: BrainAmp DC
- **Reference**: nose
- **Ground**: FCz
- **Sensor type**: passive Ag/AgCl
- **Line frequency**: 50.0 Hz
- **Impedance threshold**: 20.0 kOhm
- **Cap manufacturer**: EasyCap
- **Auxiliary channels**: EOG (1 ch, vertical), pulse, respiration

## Participants

- **Number of subjects**: 13
- **Health status**: healthy
- **Age**: mean=26.0, std=1.5
- **Gender distribution**: female=5, male=8
- **BCI experience**: mostly naive
- **Species**: human

## Experimental Protocol

- **Paradigm**: p300
- **Number of classes**: 2
- **Class labels**: Target, NonTarget
- **Trial duration**: 25.0 s
- **Study design**: Visual ERP speller copy-spelling task using a 6x7 grid with learning from label proportions (LLP) classifier. Two sequences with different target/non-target ratios: sequence 1 (3 targets/8 stimuli), sequence 2 (2 targets/18 stimuli). Unsupervised calibrationless approach.
- **Feedback type**: visual
- **Stimulus type**: character matrix
- **Stimulus modalities**: visual
- **Primary modality**: visual
- **Synchronicity**: synchronous
- **Mode**: online
- **Training/test split**: False
- **Instructions**: Copy-spelling task: subjects spelled the sentence 'FRANZY JAGT IM KOMPLETT VERWAHRLOSTEN TAXI QUER DURCH FREIBURG' three times
- **Stimulus presentation**: soa_ms=250, stimulus_duration_ms=100, grid_size=6x7, highlighting_method=salient (brightness enhancement, rotation, enlargement, trichromatic grid overlay), viewing_distance_cm=80, screen_size_inches=24

## HED Event Annotations

Schema: HED 8.4.0 | Browse: https://www.hedtags.org/hed-schema-browser

```
  Target
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Target

  NonTarget
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Non-target

```
## Paradigm-Specific Parameters

- **Detected paradigm**: p300
- **Number of targets**: 42
- **Stimulus onset asynchrony**: 250.0 ms

## Data Structure

- **Trials**: 12852
- **Trials context**: 68 highlighting events per character, 63 characters per sentence, 3 sentences = 68*63*3 = 12852 EEG epochs per subject. Each epoch is a Target (10002) or NonTarget (10001) event.

## Preprocessing

- **Data state**: raw
- **Preprocessing applied**: False

## Signal Processing

- **Classifiers**: LLP (Learning from Label Proportions), shrinkage-LDA, EM-algorithm
- **Feature extraction**: mean amplitude per time interval
- **Frequency bands**: analyzed=[0.5, 8.0] Hz

## Cross-Validation

- **Method**: 5-fold chronological cross-validation
- **Folds**: 5
- **Evaluation type**: within_subject

## Performance (Original Study)

- **Accuracy**: 84.5%
- **Auc**: 0.975
- **Online Spelling Accuracy**: 84.5
- **Post Hoc Spelling Accuracy**: 95.0
- **Accuracy After Rampup**: 90.2
- **Supervised Auc**: 0.975
- **Max Spelling Speed Chars Per Min**: 2.4

## BCI Application

- **Applications**: speller, communication
- **Environment**: laboratory
- **Online feedback**: True

## Tags

- **Pathology**: Healthy
- **Modality**: Visual
- **Type**: Research

## Documentation

- **DOI**: 10.1371/journal.pone.0175856
- **License**: CC-BY-4.0
- **Investigators**: David Hübner, Thibault Verhoeven, Konstantin Schmid, Klaus-Robert Müller, Michael Tangermann, Pieter-Jan Kindermans
- **Senior author**: Michael Tangermann
- **Contact**: david.huebner@blbt.uni-freiburg.de; michael.tangermann@blbt.uni-freiburg.de; p.kindermans@tu-berlin.de
- **Institution**: Albert-Ludwigs-University
- **Department**: Brain State Decoding Lab, Cluster of Excellence BrainLinks-BrainTools, Department of Computer Science
- **Address**: Freiburg, Germany
- **Country**: DE
- **Repository**: Zenodo
- **Data URL**: http://doi.org/10.5281/zenodo.192684
- **Publication year**: 2017
- **Funding**: BrainLinks-BrainTools Cluster of Excellence funded by the German Research Foundation (DFG), grant number EXC 1086; bwHPC initiative, grant INST 39/963-1 FUGG; European Union's Horizon 2020 research and innovation programme under the Marie Sklodowska-Curie grant agreement No 657679; Special Research Fund from Ghent University; BK21 program funded by Korean National Research Foundation grant No. 2012-005741
- **Ethics approval**: Ethics Committee of the University Medical Center Freiburg; Declaration of Helsinki
- **Keywords**: brain-computer interface, BCI, event-related potentials, ERP, P300, learning from label proportions, LLP, unsupervised learning, calibrationless, visual speller

## Abstract

Using traditional approaches, a brain-computer interface (BCI) requires the collection of calibration data for new subjects prior to online use. This work introduces learning from label proportions (LLP) to the BCI community as a new unsupervised, and easy-to-implement classification approach for ERP-based BCIs. The LLP estimates the mean target and non-target responses based on known proportions of these two classes in different groups of the data. We present a visual ERP speller to meet the requirements of LLP. For evaluation, we ran simulations on artificially created data sets and conducted an online BCI study with 13 subjects performing a copy-spelling task. Theoretical considerations show that LLP is guaranteed to minimize the loss function similar to a corresponding supervised classifier. LLP performed well in simulations and in the online application, where 84.5% of characters were spelled correctly on average without prior calibration.

## Methodology

The experiment used a modified visual ERP speller with a 6×7 grid. Two distinct stimulus sequences with different target/non-target ratios were used: sequence 1 had 3 targets in 8 stimuli, sequence 2 had 2 targets in 18 stimuli. Each trial consisted of 4 sequences of length 8 and 2 sequences of length 18, totaling 68 highlighting events per character. The LLP algorithm exploited these known proportions to reconstruct mean target and non-target ERP responses without requiring labeled data. The classifier was reset at the start of each sentence and retrained after each character. Subjects spelled a German pangram sentence three times. One subject (S2) had prior EEG experience; others were naive. Sessions lasted about 3 hours including setup. Participants were compensated 8 Euros per hour.

## References

Hübner, D., Verhoeven, T., Schmid, K., Müller, K. R., Tangermann, M., & Kindermans, P. J. (2017) Learning from label proportions in brain-computer interfaces: Online unsupervised learning with guarantees. PLOS ONE 12(4): e0175856. https://doi.org/10.1371/journal.pone.0175856

.. versionadded:: 0.4.5
Appelhoff, S., Sanderson, M., Brooks, T., Vliet, M., Quentin, R., Holdgraf, C., Chaumon, M., Mikulan, E., Tavabi, K., Hochenberger, R., Welke, D., Brunner, C., Rockhill, A., Larson, E., Gramfort, A. and Jas, M. (2019). MNE-BIDS: Organizing electrophysiological data into the BIDS format and facilitating their analysis. Journal of Open Source Software 4: (1896). https://doi.org/10.21105/joss.01896

Pernet, C. R., Appelhoff, S., Gorgolewski, K. J., Flandin, G., Phillips, C., Delorme, A., Oostenveld, R. (2019). EEG-BIDS, an extension to the brain imaging data structure for electroencephalography. Scientific Data, 6, 103. https://doi.org/10.1038/s41597-019-0104-8

---
Generated by MOABB 1.5.0 (Mother of All BCI Benchmarks)
https://github.com/NeuroTechX/moabb
