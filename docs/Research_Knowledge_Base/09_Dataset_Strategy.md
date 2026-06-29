# Dataset Strategy: FAEAP

## What is Dataset Strategy?

Dataset strategy defines how data will be collected, generated, annotated, stored, and maintained to support machine learning model development. It encompasses data sourcing, quality control, metadata management, and versioning.

## Why is Dataset Strategy Important?

### Model Performance
1. **Quality**: High-quality data enables better models
2. **Diversity**: Diverse data improves generalization
3. **Quantity**: Sufficient data prevents overfitting
4. **Relevance**: Domain-specific data improves task performance

### Research Contribution
1. **Novelty**: Novel datasets are research contributions
2. **Reproducibility**: Public datasets enable replication
3. **Benchmarking**: Datasets enable fair comparison
4. **Citation**: Datasets can be cited independently

## FAEAP Dataset Overview

### Dataset Name
**Forensic Audio Evidence Authentication Dataset (FAEAD)**

### Dataset Purpose
Comprehensive dataset for audio forensic research, specifically focusing on AI-generated audio event manipulations with precise temporal annotations and rich metadata.

### Dataset Scope
- **Authentic Audio**: 1000+ recordings from diverse sources
- **Manipulated Audio**: 5000+ samples with diverse manipulations
- **Manipulation Types**: 8+ categories
- **Annotations**: Precise timestamps, manipulation types, metadata
- **Quality**: Expert-verified, high-quality recordings

## Data Collection Strategy

### Authentic Audio Sources

#### Source 1: Public Audio Datasets
- **AudioSet**: YouTube-based diverse audio
- **FSD50K**: Freesound dataset with diverse sounds
- **ESC-50**: Environmental sound classification
- **UrbanSound8K**: Urban environmental sounds
- **LibriSpeech**: Speech corpus (for voice manipulations)

#### Source 2: Forensic Audio Archives
- **ENF Database**: Electric Network Frequency recordings
- **Forensic Laboratory Partners**: Real forensic cases (anonymized)
- **Court Recordings**: Publicly available court audio
- **Emergency Calls**: Publicly available 911 recordings

#### Source 3: Custom Recording
- **Controlled Environment**: Studio recordings with known conditions
- **Field Recordings**: Real-world environments with varying conditions
- **Device Diversity**: Recordings from different devices (phones, recorders, cameras)
- **Environment Diversity**: Indoor, outdoor, vehicle, etc.

#### Authentic Audio Categories
1. **Speech**: Conversations, interviews, phone calls
2. **Environmental**: Background sounds, ambient noise
3. **Events**: Real gunshots, screams, explosions (when available)
4. **Mixed**: Speech with background, events with speech

### Authentic Audio Selection Criteria

#### Quality Criteria
- **Sample Rate**: ≥ 16kHz (prefer 44.1kHz or 48kHz)
- **Bit Depth**: ≥ 16-bit (prefer 24-bit)
- **SNR**: ≥ 20dB
- **Duration**: 5 seconds to 10 minutes
- **Format**: WAV (uncompressed) preferred

#### Diversity Criteria
- **Recording Devices**: Phones, recorders, cameras, microphones
- **Environments**: Indoor, outdoor, vehicle, studio
- **Conditions**: Quiet, noisy, reverberant
- **Speakers**: Different ages, genders, accents
- **Content**: Diverse speech and environmental sounds

#### Legal Criteria
- **Public Domain**: Publicly available recordings
- **Creative Commons**: CC-BY, CC0 licenses
- **Research Use**: Permission for research use
- **Anonymization**: Personal information removed

## Manipulation Generation Strategy

### AI Audio Generation Models

#### Model 1: AudioLDM (Text-to-Audio)
- **Purpose**: Generate audio from text descriptions
- **Capabilities**: Diverse audio events
- **Quality**: High realism
- **Use Cases**: Gunshots, screams, explosions, crashes

#### Model 2: AudioGen (Meta)
- **Purpose**: Generate audio from text
- **Capabilities**: Environmental sounds, events
- **Quality**: State-of-the-art
- **Use Cases**: Crowd sounds, animal sounds, glass breaking

#### Model 3: Bark (Text-to-Audio)
- **Purpose**: Generate speech and non-speech audio
- **Capabilities**: Voice, sound effects
- **Quality**: Good for speech
- **Use Cases**: Voice synthesis, speech events

#### Model 4: VALL-E (Voice Synthesis)
- **Purpose**: Voice cloning and synthesis
- **Capabilities**: High-quality voice synthesis
- **Quality**: Near-human quality
- **Use Cases**: Voice synthesis manipulations

#### Model 5: RVC (Real-Time Voice Conversion)
- **Purpose**: Convert one voice to another
- **Capabilities**: Real-time voice conversion
- **Quality**: High quality
- **Use Cases**: Voice conversion manipulations

### Manipulation Types

#### Type 1: AI-Generated Gunshot Insertion
- **Generation Model**: AudioLDM, AudioGen
- **Insertion Method**: Splice at random or strategic locations
- **Variations**: Different gunshot types, distances, environments
- **Duration**: 0.5-3 seconds
- **Target**: 500 samples

#### Type 2: AI-Generated Scream Insertion
- **Generation Model**: AudioLDM, AudioGen
- **Insertion Method**: Splice at random or strategic locations
- **Variations**: Different scream types, genders, intensities
- **Duration**: 0.5-2 seconds
- **Target**: 500 samples

#### Type 3: AI-Generated Explosion Insertion
- **Generation Model**: AudioLDM, AudioGen
- **Insertion Method**: Splice at random or strategic locations
- **Variations**: Different explosion types, distances
- **Duration**: 1-5 seconds
- **Target**: 500 samples

#### Type 4: AI-Generated Vehicle Crash Insertion
- **Generation Model**: AudioLDM, AudioGen
- **Insertion Method**: Splice at random or strategic locations
- **Variations**: Different crash types, vehicles
- **Duration**: 1-4 seconds
- **Target**: 500 samples

#### Type 5: AI-Generated Glass Breaking Insertion
- **Generation Model**: AudioLDM, AudioGen
- **Insertion Method**: Splice at random or strategic locations
- **Variations**: Different glass types, breaking methods
- **Duration**: 0.5-2 seconds
- **Target**: 500 samples

#### Type 6: AI-Generated Crowd Sounds Insertion
- **Generation Model**: AudioLDM, AudioGen
- **Insertion Method**: Splice at random or strategic locations
- **Variations**: Different crowd sizes, environments
- **Duration**: 2-10 seconds
- **Target**: 500 samples

#### Type 7: AI-Generated Animal Sounds Insertion
- **Generation Model**: AudioLDM, AudioGen
- **Insertion Method**: Splice at random or strategic locations
- **Variations**: Different animal types, behaviors
- **Duration**: 0.5-3 seconds
- **Target**: 500 samples

#### Type 8: Audio Splice (Traditional)
- **Generation Method**: Manual splicing of authentic audio
- **Insertion Method**: Splice authentic audio segments
- **Variations**: Different splice points, cross-fades
- **Duration**: Variable
- **Target**: 500 samples

#### Type 9: Voice Synthesis
- **Generation Model**: VALL-E, Bark
- **Insertion Method**: Replace or insert synthetic speech
- **Variations**: Different voices, content
- **Duration**: 2-10 seconds
- **Target**: 500 samples

#### Type 10: Voice Conversion
- **Generation Model**: RVC
- **Insertion Method**: Convert speaker voice to another
- **Variations**: Different source/target voices
- **Duration**: Variable
- **Target**: 500 samples

### Manipulation Insertion Strategy

#### Random Insertion
- **Method**: Insert at random timestamp
- **Purpose**: General detection capability
- **Percentage**: 60% of manipulations

#### Strategic Insertion
- **Method**: Insert at contextually relevant locations
- **Purpose**: Realistic forensic scenarios
- **Percentage**: 40% of manipulations

#### Multiple Manipulations
- **Method**: Insert multiple manipulations in single audio
- **Purpose**: Complex scenario testing
- **Percentage**: 10% of samples

#### No Manipulation (Control)
- **Method**: Keep authentic audio unchanged
- **Purpose**: False positive testing
- **Percentage**: 20% of samples

## Annotation Strategy

### Annotation Types

#### Annotation 1: Manipulation Presence
- **Type**: Binary label
- **Values**: 0 (authentic), 1 (manipulated)
- **Purpose**: Detection task
- **Method**: Automatic (known during generation)

#### Annotation 2: Manipulation Type
- **Type**: Categorical label
- **Values**: One of 10 manipulation types
- **Purpose**: Classification task
- **Method**: Automatic (known during generation)

#### Annotation 3: Temporal Localization
- **Type**: Timestamp pair
- **Values**: (start_time, end_time) in seconds
- **Purpose**: Localization task
- **Method**: Automatic (known during generation)
- **Precision**: Millisecond precision

#### Annotation 4: Manipulation Region
- **Type**: Frame-level mask
- **Values**: Binary mask per frame
- **Purpose**: Fine-grained localization
- **Method**: Automatic from timestamps
- **Resolution**: 10ms frames

#### Annotation 5: Quality Metrics
- **Type**: Numerical metrics
- **Values**: SNR, PESQ, STOI
- **Purpose**: Quality assessment
- **Method**: Automatic calculation

### Metadata Schema

#### Audio Metadata
```json
{
  "audio_id": "unique_identifier",
  "original_filename": "original_name.wav",
  "duration": 45.3,
  "sample_rate": 44100,
  "bit_depth": 24,
  "channels": 1,
  "format": "wav",
  "file_size": 7623456
}
```

#### Source Metadata
```json
{
  "source_type": "public_dataset|custom_recording|forensic_archive",
  "source_dataset": "AudioSet|FSD50K|custom",
  "source_url": "url_if_available",
  "recording_device": "phone|recorder|camera|microphone",
  "device_model": "iPhone_13|Zoom_H4n|Canon_EOS_R5",
  "recording_environment": "indoor|outdoor|vehicle|studio",
  "acoustic_conditions": "quiet|noisy|reverberant",
  "date_recorded": "2023-01-15",
  "location": "city|country_if_known"
}
```

#### Manipulation Metadata
```json
{
  "is_manipulated": true,
  "manipulation_type": "ai_gunshot",
  "manipulation_model": "AudioLDM",
  "generation_prompt": "gunshot in urban environment",
  "insertion_timestamp": 12.5,
  "manipulation_start": 12.5,
  "manipulation_end": 14.2,
  "manipulation_duration": 1.7,
  "insertion_method": "splice|overlay",
  "cross_fade_duration": 0.1,
  "original_audio_id": "original_audio_id",
  "manipulated_audio_id": "manipulated_audio_id"
}
```

#### Quality Metadata
```json
{
  "snr": 25.3,
  "pesq": 4.2,
  "stoi": 0.95,
  "overall_quality": "high|medium|low",
  "expert_rating": 4.5,
  "expert_notes": "Clear manipulation, good quality"
}
```

## Dataset Organization

### Folder Structure
```
FAEAD/
├── README.md
├── metadata/
│   ├── authentic_metadata.json
│   ├── manipulated_metadata.json
│   └── schema.json
├── audio/
│   ├── authentic/
│   │   ├── sample_0001.wav
│   │   ├── sample_0002.wav
│   │   └── ...
│   └── manipulated/
│       ├── sample_0001_manip_1.wav
│       ├── sample_0001_manip_2.wav
│       └── ...
├── annotations/
│   ├── detection_labels.csv
│   ├── classification_labels.csv
│   ├── localization_labels.csv
│   └── frame_masks/
├── splits/
│   ├── train.json
│   ├── val.json
│   └── test.json
└── documentation/
    ├── collection_methodology.md
    ├── generation_methodology.md
    ├── annotation_guidelines.md
    └── usage_examples.md
```

### File Naming Convention
- **Authentic**: `sample_XXXX.wav` (XXXX = 0001 to 1000)
- **Manipulated**: `sample_XXXX_manip_YY.wav` (YY = manipulation index)

## Dataset Split

### Training Set (70%)
- **Authentic**: 700 samples
- **Manipulated**: 3500 samples
- **Purpose**: Model training
- **Diversity**: All manipulation types represented

### Validation Set (15%)
- **Authentic**: 150 samples
- **Manipulated**: 750 samples
- **Purpose**: Hyperparameter tuning
- **Diversity**: All manipulation types represented

### Test Set (15%)
- **Authentic**: 150 samples
- **Manipulated**: 750 samples
- **Purpose**: Final evaluation
- **Diversity**: All manipulation types represented
- **Holdout**: Not used during development

### Split Strategy
- **Stratified**: Maintain manipulation type distribution
- **Speaker/Environment Split**: Same speaker/environment not in train and test
- **Random Seed**: Fixed for reproducibility
- **Version Control**: Track split versions

## Quality Control

### Automated Quality Checks

#### Audio Quality Checks
- **Sample Rate Validation**: Verify sample rate ≥ 16kHz
- **Bit Depth Validation**: Verify bit depth ≥ 16-bit
- **SNR Calculation**: Verify SNR ≥ 20dB
- **Duration Check**: Verify duration within expected range
- **Format Validation**: Verify WAV format correctness

#### Annotation Quality Checks
- **Timestamp Validation**: Verify start < end, within audio duration
- **Label Validation**: Verify labels within allowed values
- **Consistency Check**: Verify annotations consistent with metadata
- **Completeness Check**: Verify all required fields present

#### Metadata Quality Checks
- **Schema Validation**: Verify metadata matches schema
- **Reference Integrity**: Verify audio IDs exist
- **Data Type Check**: Verify correct data types
- **Range Check**: Verify numerical values in valid ranges

### Manual Quality Checks

#### Expert Review
- **Audio Quality**: Expert rates audio quality (1-5)
- **Manipulation Realism**: Expert rates manipulation realism (1-5)
- **Annotation Accuracy**: Expert verifies annotation accuracy
- **Metadata Completeness**: Expert verifies metadata completeness

#### Inter-Annotator Agreement
- **Multiple Annotators**: 2-3 experts annotate subset
- **Agreement Calculation**: Calculate Cohen's kappa
- **Threshold**: κ > 0.8 required
- **Dispute Resolution**: Third expert resolves disagreements

### Quality Metrics
- **Audio Quality Pass Rate**: > 95%
- **Annotation Accuracy**: > 99%
- **Metadata Completeness**: > 98%
- **Expert Agreement**: κ > 0.8

## Versioning Strategy

### Semantic Versioning
- **Major Version**: Significant changes (new manipulation types, major reorganization)
- **Minor Version**: Additions (new samples, new metadata fields)
- **Patch Version**: Corrections (metadata fixes, annotation corrections)

### Version Control
- **Git Repository**: Track metadata and documentation
- **Data Versioning**: DVC (Data Version Control) for audio files
- **DOI Assignment**: Zenodo for each version
- **Citation**: Each version citable with DOI

### Change Log
- **Version 1.0.0**: Initial release (1000 authentic, 5000 manipulated)
- **Version 1.1.0**: Add 500 authentic samples
- **Version 1.2.0**: Add new manipulation type
- **Version 2.0.0**: Major reorganization, new metadata schema

## Dataset Documentation

### README.md
- Dataset overview
- Citation information
- License information
- Download instructions
- Quick start guide

### Collection Methodology
- Authentic audio sources
- Selection criteria
- Legal considerations
- Diversity strategy

### Generation Methodology
- AI models used
- Generation parameters
- Insertion strategies
- Quality assessment

### Annotation Guidelines
- Annotation types
- Annotation procedures
- Quality control
- Inter-annotator agreement

### Usage Examples
- Loading data
- Training models
- Evaluation protocols
- Expected results

## Ethical Considerations

### Privacy Protection
- **Anonymization**: Remove personal information
- **Consent**: Use only publicly available or consented data
- **Data Minimization**: Store only necessary data
- **Retention**: Limited retention period

### Legal Compliance
- **Copyright**: Use only properly licensed data
- **GDPR**: Comply with data protection regulations
- **Terms of Use**: Respect dataset terms of use
- **Attribution**: Provide proper attribution

### Responsible AI
- **Bias Assessment**: Evaluate dataset for biases
- **Fairness**: Ensure diverse representation
- **Transparency**: Document dataset limitations
- **Intended Use**: Specify intended and prohibited uses

## Dataset Publication Strategy

### Publication Venue
- **Zenodo**: Long-term archival with DOI
- **Figshare**: Alternative with DOI
- **Hugging Face**: ML community platform
- **Project Website**: Custom hosting

### License
- **CC-BY 4.0**: Attribution required, commercial use allowed
- **CC-BY-NC 4.0**: Attribution required, non-commercial only
- **Custom License**: Specific terms for forensic use

### Citation
```
@dataset{faead2024,
  title={Forensic Audio Evidence Authentication Dataset (FAEAD)},
  author={Your Name},
  year={2024},
  publisher={Zenodo},
  doi={10.5281/zenodo.XXXXXXX}
}
```

### Paper Submission
- **Dataset Paper**: Dedicated paper describing dataset
- **Venue**: Data in Brief, Scientific Data, or workshop
- **Content**: Collection, generation, annotation, statistics
- **Timeline**: Submit after dataset completion

## Future Expansion

### Phase 2: Additional Manipulations
- **New Types**: Add emerging manipulation techniques
- **More Samples**: Increase sample count
- **More Diversity**: Add new recording conditions

### Phase 3: Real Forensic Cases
- **Partnerships**: Collaborate with forensic laboratories
- **Anonymization**: Strict anonymization protocols
- **Validation**: Expert validation of real cases

### Phase 4: Multi-Modal
- **Video**: Add video component
- **Synchronization**: Audio-video synchronization
- **Multi-Modal Annotations**: Cross-modal annotations

## Conclusion

The FAEAP dataset strategy provides a comprehensive approach to creating a high-quality forensic audio dataset. By combining authentic audio from diverse sources with AI-generated manipulations, precise annotations, and rich metadata, the dataset will support robust model development and serve as a valuable research contribution. The dataset will be publicly available with proper documentation, versioning, and citation, enabling reproducibility and benchmarking in the forensic audio research community.
