# AMI Digital Asset Technical Specifications

This document outlines the technical specifications and requirements for digitization of analog media collections and digital packaging of deliverable files. For corresponding information about shipping, handling and reporting, please see:

![ami-handling](https://github.com/NYPL/ami-handling)

## Table Of Contents
<!-- MarkdownTOC -->

- [Section A: Audio](#section-a-audio)
  - [General information: audio](#general-information-audio)
  - [Preservation Master file specifications: audio](#preservation-master-file-specifications-audio)
    - [General audio guidelines](#general-audio-guidelines)
    - [Specific NYPL Requirements](#specific-nypl-requirements)
    - [Signal extraction](#signal-extraction)
    - [Audio group 1: analog audio](#audio-group-1-analog-audio)
    - [Audio group 2: digital audio](#audio-group-2-digital-audio)
    - [Audio group 3: optical](#audio-group-3-optical)
  - [Edit Master file specifications: audio](#edit-master-file-specifications-audio)
    - [Edit Master Alterations](#edit-master-alterations)
    - [All audio groups](#all-audio-groups)
- [Section B: Video](#section-b-video)
  - [General information: video](#general-information-video)
  - [Preservation Master file specifications: video](#preservation-master-file-specifications-video)
    - [General guidelines](#general-guidelines)
    - [Video group 1](#video-group-1)
    - [Video group 2](#video-group-2)
    - [Video group 3](#video-group-3)
  - [Service Copy file specifications: video](#service-copy-file-specifications-video)
    - [Optical Video Service Copies](#optical-video-service-copies)
    - [Standard Definition video](#SD-video)
    - [High Definition video](#HD-video)
- [Section C: Metadata](#section-c-metadata)
  - [Metadata specifications](#metadata-specifications)
    - [Metadata file specifications](#metadata-file-specifications)
    - [Metadata content](#metadata-content)
    - [JSON "Notes" Fields](#json-notes-fields)
    - [Metadata errors](#metadata-errors)
    - [Audio channel / tack configurations and terminology matrix](#audio-channel--tack-configurations-and-terminology-matrix)
- [Section D: Digital Asset Structure](#section-d-digital-asset-structure)
  - [File name and file structure specifications](#file-name-and-file-structure-specifications)
    - [File names](#file-names)
    - [Item structure](#item-structure)
    - [File role](#file-role)
    - [Item component chart](#item-component-chart)
  - [Digital asset delivery](#digital-asset-delivery)
  - [Digital asset packaging](#digital-asset-packaging)
    - [Primary root directories](#primary-root-directories)
    - [Sample root directory structure that contains all possible bags:](#sample-root-directory-structure-that-contains-all-possible-bags)
    - [Bagit requirements](#bagit-requirements)
- [Section E. Directory Structure Examples](#section-e-directory-structure-examples)

<!-- /MarkdownTOC -->



<a name="section-a-audio"></a>
## Section A: Audio

<a name="general-information-audio"></a>
### General information: audio
* Specifications may be modified over time to reflect changes in best practices or NYPL’s digital infrastructure, or to reflect previously unspecified media or conditions.
* Formats are broken into Groups which help define the file deliverables (mainly the preservation masters) See the full list.
* For each original audio recording, the vendor shall produce:
  * one (or more) preservation master file(s)
  * one (or more) edit master file(s)

<a name="preservation-master-file-specifications-audio"></a>
### Preservation Master file specifications: audio
<a name="general-audio-guidelines"></a>
#### General audio guidelines
* **Preservation Master:** The preservation master (PM) is the highest level derivative of the original recording, and is created in an effort to produce an authentic sonic facsimile of the original recording.  Therefore, the preservation master recording will represent an unedited, unaltered, direct, and complete capture of the signal from the output of the playback device.

* **Technical guidelines - IASA-TC 04, 2nd edition:** The production of preservation master files will comply with the technical recommendations, practices and strategies outlined in the International Association of Audiovisual Archives’, Guidelines on the Production and Preservation of Digital Audio Objects, IASA-TC 04, 2nd edition.

* **Strategic guidelines - IASA-TC 03, version 3:** The production of preservation master files will comply with the ethical recommendations, practices and strategies outlined in the International Association of Audiovisual Archives’, The Safeguarding of the Audio Heritage: Ethics, Principles and Preservation Strategy, IASA-TC 03, version 3.

* The Contractor shall notify NYPL whenever these guidelines cannot be met, and described the proposed process. Work cannot commence without NYPL approval of proposed processed.

<a name="specific-nypl-requirements"></a>
#### Specific NYPL Requirements
##### Object-file relationships and special circumstances
* **Faces:** In general, one preservation master file will be generated for each physically or technically discrete recording area of the original object.
  * For example, each side of an audio cassette will be recorded as a separate preservation master file, identified with a designated Face number.

* Considerations and circumstances that impact the number of preservation masters generated for each physical object, and/or for each discrete recording area:
  * For an object which is found to have content recorded both forwards and backwards on the same Face, a second Face may be created for the reversed content to be recorded in the proper direction.
  * **Region:** For an object with two regions recorded at different speeds, a separate PM must be created for each Region (filename_v01f01r01_pm).
  * **Part:** When a recording must be divided into parts due to file size limitations (4GB WAV limit), a separate Preservation Master file must be created for each Part.
  * There may be rare circumstances in which just the Edit Master from a PM will exceed the 4GB WAV limit (i.e. when mixing mono to stereo). In this case, the Edit Master must be split into multiple Parts, but the PM should not be split or captured as multiple parts - it must remain a single file. A note must be added to the metadata deliverables describing this circumstance.
  * **File overlap:** If multiple PMs are created for a single recording due to either speed changes or size limitations (Regions or Parts), the cut should be made at a logical break in the audible content (if at all possible), and there must be exactly 5 seconds of audible content overlapping between the tail of the first PM and the head of the following PM so that the regions/parts may be recombined in the future if necessary.

<a name="signal-extraction"></a>
#### Signal extraction
* IASA-TC 04: Signal extraction from analog original audio recordings will comply with the technical recommendations, practices and strategies outlined in the International Association of Audiovisual Archives’, Guidelines on the Production and Preservation of Digital Audio Objects, IASA-TC 04, 2nd edition, Chapter 5 (Signal Extraction from Original Carriers).
* Optimal signal extraction for the production of Preservation Master files should aim to capture the complete dynamic and frequency ranges of the original recording.
* Signal extraction must be carried out using the equipment and accessories that are appropriate and intended for the original format characteristics.
  * Example: a full-track mono recording on an open reel audio tape must be transferred using a full-track audio head (rather than a stereo head).
  * If this is not possible, the Contractor must provide an explicit proposal for work, subject to NYPL approval.
* An optimal signal extraction from the original recording will be a flat (unmodified) transfer, free of signal processing, equalization, level adjustment, noise reduction, etc.  Exceptions would include:
  * de-emphasis of a recording’s stated pre-emphasis (playback equalization)
  * decoding of a recording’s stated noise-reduction encoding
* Optimal signal extraction from original sources includes the extraction of the intended signal, along with any unintended signal (such as artifacts and anomalies in the signal associated with the inherent limitations of historic recording technologies).
* Preservation master files may be one or two-channel (interleaved), and the configuration employed will be determined by the needs of the original recording.
* Levels may be adjusted ONLY if there is severe distortion or digital clipping from the source, and this adjustment must be noted clearly in the metadata.

<a name="audio-group-1-analog-audio"></a>
#### Audio group 1: analog audio
##### Format types: analog open reel, analog cassette, wire
##### File specifications
* Format: Broadcast Wave (BWF)
* Audio data encoding: PCM
* Sampling rate: 96,000 Hz
* Number of audio channels: Same as source

##### Additional details
* Optimal signal extraction from analog sources seeks to be complete, and includes the transfer of the “lead-in” and “play-out” portions of a recording.
* Analog signals will be converted to a digital bitstream by means of an Analog-to-Digital converter which complies with the specifications in FADGI’s Audio Analog-to-Digital Converter Performance Specification and Test Method.
* No signal processing will be applied to the Analog-to-Digital converter’s digital bitstream; this would include equalization, level adjustment, dither, noise reduction, etc.

<a name="audio-group-2-digital-audio"></a>
#### Audio group 2: digital audio
##### Format types: digital audio tapes, etc.
##### File specifications
* Format: Broadcast Wave (BWF)
* Audio data encoding: PCM
* Bit depth: Same as source
* Sampling rate: Same as source
* Number of audio channels: Same as source
##### Additional details
* **Example:** a DAT recorded at 48/16 should be captured as a 48/16 Broadcast WAV file.

<a name="audio-group-3-optical"></a>
#### Audio group 3: optical audio
##### Format types: optical discs
##### File specifications: [deprecate in 2017]
* CDs should be captured as a single Broadcast WAV file that matches the bit depth and sampling rate of the original object.

##### File specifications [implement 2017]
* Format: WAV/CUE
* CDs should be captured as a single Broadcast WAV file that matches the bit depth and sampling rate of the original object.
* In addition, the vendor will create a corresponding CUE file for the Preservation Master WAV file. The CUE file must:
    * Follow the same naming convention as the WAV file, but instead with a ".cue" extension.
    * Be nested within the Preservation Masters directory, accompanying the Preservation Master WAV file (the Edit master must not have a .cue file).
    * Be referenced in the JSON file under the technical.cueFile filed, by its complete filename.
      * Example: "myh_123456_v01_pm.cue"

=======
* In addition, the vendor will create a corresponding CUE file for the Preservation Master WAV file. The CUE file must:
  * Follow the same naming convention as the WAV file, but instead with a ".cue" extension. Example: "myh_123456_v01_pm.cue"
  * Be nested within the Preservation Masters directory, accompanying the Preservation Master WAV file (the Edit master must not have a .cue file).
  * Be referenced in the JSON file under the technical.cueFile filed, by its complete filename.

##### Additional details
* If CD-ROMs or hybrid CDs (multimedia+audio) are discovered during the Contractor’s review of physical objects, the Contractor should contact NYPL to discuss adjustments to the migration strategy.
* Edit Masters for all audio CDs should adhere to the specifications below, with content delivered as a single Broadcast Wave file that matches the bit depth and sampling rate of the original object.

<a name="edit-master-file-specifications-audio"></a>
### Edit Master file specifications: audio
<a name="edit-master-alterations"></a>
#### Edit Master Alterations
The Edit Master serves as a production master – the recording from which all Service Copies for the Preservation Master will be derived.  It is a version of the Preservation Master which has been edited and/or processed to enhance the continuity and intelligibility of its content.

The Edit Master will be altered from the Preservation Master in the following ways, as necessary:
##### Head and tail edits (trimming)
* Unrecorded portions of the Archive Original object which may have been captured in the production of the Preservation Master shall be eliminated.
* Test tones and any equipment noise at the start and/or end of audible content (such as equipment on/off “clicks” or a stylus in the groove) should be trimmed.
** Trimming should not result in an abrupt start and/or end of audible content.
** When using automated processes or automation software for creation of Edit Masters, sample files must be approved by NYPL to determine acceptable results.
* Elimination of the 5-second overlap included on any Preservation Masters that have been split out into multiple files for separate regions / streams / etc.
##### Level Adjustment
When balance and/or overall level are insufficient a peak level adjustment of max. -2db may be implemented as necessary.
##### Channel adjustment
* Ensuring that "mono" is true mono
* Conversion of one-channel audio to two-channel audio (i.e. mono to dual-mono).

<a name="all-audio-groups"></a>
#### All audio groups
##### Format types: All audio groups and format types follow the same specifications for edit masters.
##### File specifications
* Format: Broadcast Wave (BWF)
* Audio data encoding: PCM
* Bit depth:  equal to the Preservation Master
* Sampling rate: equal to the Preservation Master
* Number of audio channels: 2 (dual-mono or stereo)

##### Preservation Master - Edit Master relationships and special circumstances
* In general, one Edit Master will be created for each Preservation Master file.

**Multi-track:**
* Tapes with more than 2 streams of audio are considered multi-track. For multi-track recordings, Edit masters should not be created (except in the very rare occurrence that each track is being considered a separate Face, rather than a separate Stream - see Item Structure for more detail).

**File size limitation:**
* Some Edit Masters may be larger than their Preservation Masters. Due to the 4GB file size limit for WAV, the resulting change in file size may require creation of multiple Edit Masters for a single Preservation Master. See Specific NYPL Requirements for Preservation Masters above.

<a name="section-b-video"></a>
## Section B: Video

<a name="general-information-video"></a>
### General information: video
* Specifications may be modified over time to reflect changes in best practices or NYPL’s digital infrastructure, or to reflect previously unspecified media or conditions.
* Formats are broken into Groups which help define the file deliverables (mainly the preservation masters). See the full list.
* For each original video recording, the following shall be produced:
  * one Preservation Master file
  * one Service Copy file
  * one QCTools report accompanying Preservation Master file

<a name="preservation-master-file-specifications-video"></a>
### Preservation Master file specifications: video
<a name="general-guidelines"></a>
#### General guidelines
* Characteristics intrinsic to the broadcast standard of the source material, including frame rate, pixel aspect ratio, interlacing, resolution, and recording standard (NTSC, PAL, SECAM, etc.) should be preserved.

* Signal extraction must be optimal, and carried out using the equipment and accessories that are appropriate for the original format characteristics.
* Luma, chroma and black levels may be adjusted as required on playback equipment or time base corrector to best represent source material.
* Where applicable, luma should be adjusted to fall within broadcast range (100 IRE max) and must be no higher than 110 IRE.
* The transfer should capture all content recorded on the original item, including any bars and tone, slates, or other material coming before the start of the recorded program.
* The recording should run until the end of the recorded content (picture and sound).  If this endpoint cannot be unambiguously determined, the recording should run until the end of the original object.

##### Closed captions
If present on the source tape, closed captions must be captured.
* For Preservation Masters, an .srt sidecar file must be created and accompany the Preservation Master file.
* For Service Copies, closed captioning must be embedded in CEA-608 format.

<a name="video-group-1"></a>
#### Video group 1
##### Format types: analog and digital cassettes, analog open reel
##### File specifications: 10-bit [deprecate in 2017]

|Attribute | Specification |
| --- | ----|
| Video codec |10-bit uncompressed YUV (v210)|
| Data compression | none (1:1, uncompressed)|
| Chroma subsampling | 4:2:2 YUV |
| Bit depth | 10-bit |
| File wrapper | QuickTime (.mov) |
| Frame rate | (same as original media)|
| Frame size | (same as original media) |
| Broadcast standard | (same as original media) |
| Pixel Aspect Ratio | D1 NTSC (.91) or PAL (1.09)|
| Audio format | PCM |
| Audio bit depth | 24-bit|
| Audio sampling rate | 48 kHz|
| Audio channels | (same as original media, see guidelines for silent channels)|

##### File specifications: FFv1 [implement in 2017]

|Attribute | Specification |
| --- | ----|
| Video codec |FFv1 version 3|
| Data compression | Lossless, Intra-frame (GOP-1) only|
| Chroma subsampling | 4:2:2 YUV |
| Bit depth | 10-bit |
| File wrapper | Matroska (.mkv) |
| Frame rate | (same as original media)|
| Frame size | (same as original media) |
| Broadcast standard | (same as original media) |
| Pixel Aspect Ratio | D1 NTSC (.91) or PAL (1.09)|
| Slices | 24 |
| Slicecrc | 1 |
| Audio format | PCM |
| Audio bit depth | 24-bit|
| Audio sampling rate | 48 kHz|
| Audio channels | (same as original media, see guidelines for silent channels)|

##### Additional Guidelines
* Silent channels
  * If a channel exists and is silent, the channel should be captured and a note should be included in the JSON file that  indicates that the tape and the channels delivered on PM file are silent. If a channel is non-existent, then it won't be captured. For example:
  * If soundField="ch.1:mono, ch.2: none" rather than soundField= "mono", then the second channel exists, and source.audioRecording.numberOfAudioChannels = 2 (and the PM file delivered will contain 2 channels of audio, one of which is silent).
  * Two silent channels
If detected as actual channels (i.e. recorded with "black" vs. not recorded), both channels should be captured and delivered with the PM, and a signalNote should be included that the tape is silent.

* Timecode
  * Timecode (LTC and VITC) should be captured in the configuration as recorded on the media.

<a name="video-group-2"></a>
#### Video group 2
##### Format types:  DV (digital video) cassettes

##### File specifications: 8-bit [deprecate in 2017]

|Attribute | Specification |
| --- | ----|
| Video codec |(same as source)|
| File wrapper | QuickTime (.mov)|
| Other characteristics | (same as source) |


##### File specifications: FFv1 [implement in 2017]

|Attribute | Specification |
| --- | ----|
| Video codec |(same as source)|
| File wrapper | Matroska (.mkv)|
| Other characteristics | (same as source) |

##### Examples
* DV/MiniDV objects should be captured with the DV codec
* DVCPRO objects with the DVCPRO codec, etc.  

<a name="video-group-3"></a>
#### Video group 3
##### Format types: optical discs
##### File specifications
* DVDs should be captured as ISO 9660/UDF disk image files to capture all data contained on the disc.

<a name="service-copy-file-specifications-video"></a>
### Service Copy file specifications: video
**Note:** As of 2016, NYPL uses Amazon Web Services (AWS) to deliver service copy files to patrons. Files are delivered to AWS via the Amazon Elastic Transcoder, by which the files pass through an additional level of transcoding. These specifications account for these automated post-digitization processes.

<a name="optical-video-service-copies"></a>
#### Optical Video Service Copies
* One service copy must be created for each main program within an optical video object. Note: "program" refers to what can be easily identified as a discrete full-length work; this differs from a Video Title Set, or Video_TS file, for which there can be multiple title sets for a full-length program depending on a program's length.
  * Examples: For a DVD-R that contains three different television programs, one Preservation Master (ISO) and three Service Copies (MP4) would be generated; For a Blu-Ray disc of "Gone With The Wind" that contains bonus features, one Preservation Master (ISO) and one Service Copy (MP4 of only the feature film) would be generated.
  * If the content structure of a disc is not easily discerable by the vendor, the vendor must contact NYPL for information about how best to proceed. 

<a name="SD-video"></a>
#### Standard Definition video
##### File specifications

|Attribute | Specification |
| --- | ----|
| Video codec | H.264/MPEG-4 AVC (ISO/IEC 14496-10 - MPEG4 Part 10, Advanced Video Coding) |
| Video bit rate | 3.5 Mbps|
| Chroma subsampling | 4:2:0 YUV |
| Bit depth | 8-bit |
| File wrapper | MP4 |
| Frame rate | (same as Preservation Master)|
| Frame size | (same as Preservation Master) |
| Broadcast standard | (same as original media)|
| Pixel Aspect Ratio | (same as Preservation Master, **see below for Anamorphic video**)|
| Audio Codec | AAC |
| Audio Bit Rate | 192 kbps|
| Audio sampling rate | 48 kHz|
| Audio channels | 2 (see examples)|

<a name="HD-video"></a>
#### High Definition video
##### File specifications

|Attribute | Specification |
| --- | ----|
| Video codec | H.264/MPEG-4 AVC (ISO/IEC 14496-10 - MPEG4 Part 10, Advanced Video Coding) |
| Video bit rate | 8 Mbps|
| Chroma subsampling | 4:2:0 YUV |
| Bit depth | 8-bit |
| File wrapper | MP4 |
| Frame rate | (same as Preservation Master)|
| Frame size | (same as Preservation Master) |
| Broadcast standard | (same as original media)|
| Pixel Aspect Ratio | (same as Preservation Master, **see below for Anamorphic video**)|
| Audio Codec | AAC |
| Audio Bit Rate | 192 kbps|
| Audio sampling rate | 48 kHz|
| Audio channels | 2 (see examples)|

##### Anamorphic video
* For Service Copies created from Anamorphic Preservation Masters, treat source as D1/DV NTSC or PAL Widescreen to produce a 16 x 9 Service Copy without padding. Pixel Aspect Ratio should be 1.21 (NTSC) / 1.46 (PAL).

##### Audio channels
* 4 identical channels of audio on source:
  * If a source tape has 4 channels of audio that are all the same (i.e. 4 mics in a single room recording the same content), the 4 channels captured in the PM should be mixed down to 2 for the Service Copy. If content is wildly different on each channel, the vendor should consult with NYPL for how to proceed.
* Audible content in only one channel:
  * If there is only audible content in a single channel of any number of channels in a source tape & Preservation Master, the channel containing audible content should be mapped for production of a 2-channel Service Copy to provide a better user experience.

##### Timecode
* LTC Timecode should be eliminated; audible “normal” content should be duplicated onto the second channel.
##### Trimming of heads and tails
* Color bars must not be trimmed.
* Long tails of black / unrecorded content may be trimmed after confirmation that there is no visible or audible recorded content.
* Trimming should not result in an abrupt end of visible or audible content.

<a name="section-c-metadata"></a>
## Section C: Metadata
<a name="metadata-specifications"></a>
### Metadata specifications
**Note:** Specifications may be modified to reflect found media, newly discovered issues, changes in best practices, or NYPL goals.

<a name="metadata-file-specifications"></a>
#### Metadata file specifications
* File format: JSON
* Metadata schema: the NYPL AMI metadata schema must be used.
  * The schema, validator, and samples can be found at:
github.com/nypl/ami-metadata.
** The schema evolves as issues arise. The Contractor should notify NYPL when issues are discovered in order to implement updates in a timely manner; NYPL will discuss modifications with the Contractor prior to implementation.
* Metadata must be packaged as a single JSON file for each media file.
* Metadata must validate against the digitized.json JSON Schema.
* Metadata files must be named with the same root as the media file to which they pertain, but must not include the extension of the media file.
  * Correct: [filename].json
  * Incorrect: [filename].mov.json

<a name="metadata-content"></a>
#### Metadata content
* The required contents of the metadata files are defined by the JSON metadata schema provided by NYPL, described in the previous section. According to that schema, vendors must produce metadata for each deliverable that includes designated categories.
  * Bibliographic:** about the physical media item (provided by NYPL).
  * **Source:** about the technical characteristics of the physical media item.
* **Technical:** about the files created from digitization.
* **Digitization process:** about the equipment used to playback the physical media item.
  * **Digitizer:** metadata about the vendor and operator that digitized the physical media item.

* Metadata must use the only the fields and values defined in the NYPL Vendor Metadata Specification.
* Additional metadata details:
  * If there is a question about a field, or if the provided vocabulary does not accurately describe an object or process, or if a list of terms is insufficient, contact NYPL for guidance on how to proceed. NYPL may approve and release new terms to the schema depending on priority.
  * Fields listed as "Required" for a given format category must be given a value.
* If that information is not known, the value must be “unknown”.
  * Fields listed as “Optional”, may contain a value. If there is no value, they must not be included in the metadata file. (Do not include empty optional fields.)
  * Fields listed as “Not Applicable” to a given format or media type must not be included in the metadata file. (Do not include “Not applicable fields.)

<a name="json-notes-fields"></a>
#### JSON "Notes" Fields

Please refer to the following usage guide for the various "notes" fields included in the schema:
- **bibliographic.accessNotes:** NYPL added - no additional input required
- **bibliographic.contentNotes:** any additional content notes (“title program ends mid-tape, followed by another program”; "contains explicit content")
- **technical.signalNotes:** audiovisual signal characteristics noticed during capture ("tracking errors; audio buzz")
- **source.notes.physicalConditionDigitizationNotes:** description of pre-existing damage or decay not already noted in PreShip notes (“broken leader”; "bad splices")
- **source.notes.physicalConditionPreShipNotes:** NYPL added - no additional input required
- **digitizationProcess.notes.processNotes:** rehousing, adding leader, baking, cleaning

<a name="metadata-errors"></a>
#### Metadata errors
* If misidentified/miscataloged the technical characteristics or format of an asset have been provided (i.e. NYPL-generated metadata lists an asset as an audio cassette and it is actually a video recording), please submit corrected JSON. Make any changes to source object metadata elements that would be appropriate, and note the correction in the JSON files "digitization.notes.processNotes". Example text:
  * "NYPL-provided metadata incorrectly listed [insert field name here] as [insert wrong content here]; JSON reflects correct [field name]"

<a name="audio-channel--tack-configurations-and-terminology-matrix"></a>
#### Audio channel / tack configurations and terminology matrix

![Audio grid](https://github.com/NYPL/ami-specifications/blob/master/ami-specificationsImages/NYPL_audioGrid_2017.jpg)

<a name="section-d-digital-asset-structure"></a>
## Section D: Digital Asset Structure

<a name="file-name-and-file-structure-specifications"></a>
### File name and file structure specifications

<a name="file-names"></a>
#### File names
* NYPL will provide the Contractor with a filename root for each original item, consisting of a three-letter prefix, the primary ID, a volume number (and a face number for audio items), and a two-letter suffix indicating the role of the file.  These sections are each separated by an underscore. For example:
  * (prefix)_(primary ID)_(item structure)_(file role).(ext)
  * Video: myd_mgzic1234_v01_pm
  * Audio: myh_lt10a2345_v01f01_pm
* The Contractor is responsible for creating file names in order to represent additional face, region, stream, or part elements and file roles.

<a name="item-structure"></a>
#### Item structure
* A file name must use the following components to represent the portion of a physical media item represented by the file.
* A file name must use the following components to represent the portion of a physical media item represented by the file (see “component” chart).
* **Example:** The file representing the second take of the second part of the third stream of the second region of the second face of an item marked as volume 1 is named as myd_259382_v01f02r02s03p02t02_pm.wav.

<a name="file-role"></a>
####  File role
* A file name must record its intended use using one of the following codes.
  * pm: Preservation Master, created for every physical media item
  * em: Edit Master, created for audio files
  * sc: Service Copy, created for video files

<a name="item-component-chart"></a>
#### Item component chart

|Component | Formats | Note|
| --- | ----| ----|
| Volume: v## | <ul><li>A Volume is one video or audio object in a set of objects, when that set has been assigned a single primary identifier (i.e. NYPL classmark)</li></ul> | Audio and video|
| Face: f## | <ul><li>A Face is a stream or track, or a group of streams or tracks which play synchronously, within an audio object. Every audio object has at least one Face.</li></ul> | Audio only|
| Region: r## | <ul><li>A Region is a subdivision of a Face.</li><li>Regions are most often defined by a required change in playback characteristics (speed, EQ, track configuration, etc) of an object's Face.</li><li>This is rarely used for video objects.</li></ul> | Audio and video|
| Stream: s## | <ul><li>The Stream element is used to describe multi-track and multi-channel audio objects only.</li><li>Streams are one-channel or interleaved two-channel audio streams which comprise a multi-channel or multi-track audio object.</li></ul> | Audio only|
| Part: p## | <ul><li>The part element is used when digitization of a single face of an audio or video object requires interruption because the size of the resulting file would exceed technical limits if captured all at once.</li><li>The part element may also be used when a single tape contains sections of content that are each given different unique identifiers (each section would be a distinct Part).</li></ul> | Audio and video|
| Take: t## | <ul><li>A Take is an alternate preservation capture of an entire object face, produced with alternate playback characteristics in order to compare quality or results (stylus, EQ, speed, etc.). Rare occurrence.</li></ul> | Audio only|

<a name="digital-asset-delivery"></a>
### Digital asset delivery
* Digital assets shall be delivered on hard drives.
* Hard drives must be labeled with a unique ID. The physical label and the “volume label” that appears when the drive is mounted must be the same.
* Hard drives must not contain deliverables for more than one Statement of Work.
* All external storage devices must meet NYPL Special Collections Portable Digital Storage Device Specification.
* For the most current and comprehensive specifications, including examples and tools developed by NYPL, see the following repositories under the ![NYPL GitHub Space](https://github.com/NYPL).
  * See ![Digital Preservation policies](https://github.com/NYPL/digpres-policies)
  * See [External Storage Requirements](https://github.com/NYPL/digpres-policies/blob/master/external_storage.md)
  * It is the Contractor’s responsibility to refer to the web page for most recent specifications.

<a name="digital-asset-packaging"></a>
### Digital asset packaging
<a name="primary-root-directories"></a>
#### Primary root directories
* Deliverables must be separated by media type and stored in directories "Audio" and "Video"
* Audio and Video directories must be stored in the root directory of the hard drive, and must ONLY contain completed bags.
  * Examples: If a drive contains both audio and video bags, both directories must be present; if a drive only contains video bags, they must be within a "Video" directory (no empty directories).

<a name="sample-root-directory-structure-that-contains-all-possible-bags"></a>
#### Sample root directory structure that contains all possible bags:

**HDD_uniqueID**
* Audio
  * PrimaryID
* Video
  * PrimaryID

<a name="bagit-requirements"></a>
#### Bagit requirements
* All files produced by digitization must be delivered in valid Bags. See the BagIt File Packaging Format (V0.97) at https://tools.ietf.org/html/draft-kunze-bagit-13.
* The bag name must be the Primary ID of the physical object represented by the files in the bag. (Do not use the filename root.)
* The bag must contain an md5 manifest that lists every file in the data directory and their md5 checksums.
* The bag must contain all of the media and metadata files from one, and only one, inventoried asset.
  * If an inventoried asset contains more than one physical object, please contact NYPL for instructions.
* Video bags must contain sub-directories named PreservationMasters and ServiceCopies within the data directory.*
* Audio bags must contain sub-directories named  PreservationMasters and EditMasters within the data directory.*
* All media files in a PreservationMasters directory must be represented by files in the ServiceCopies or EditMasters directory, with the exception of quality control reports.
* Each media file in the bag must have a corresponding JSON metadata file.
* For video files with closed captioning, a sidecar file (filename.srt) must accompany the preservation master file inside the PreservationMasters folder.
* The bag must not include any system files such as .DS_Store and thumbs.db.
* The bag and the files within it must not be compressed with zip, tar, etc.
* **Please note:** It is important that the sub-directories be named as they are written here, in plural (PreservationMasters / ServiceCopies / EditMasters) rather than singular form (PreservationMaster / ServiceCopy / EditMaster), regardless of the number of media files in the sub-directory.
* Bagit recommendations
  * The bag should be created with a tool using BagIt Library 4.4 or higher.
  * The bag may include tagmanifest files. Some bagging software produces these files automatically. It is not required to produce or delete these files.

<a name="section-e-directory-structure-examples"></a>
## Section E. Directory Structure Examples
The following are several examples of directory structures as expected by NYPL.

![Sample Audio Directory Structure: Groups 1 & 2 ](https://github.com/NYPL/ami-specifications/blob/master/ami-specificationsImages/SampleAudioDirectoryStructure_gp1-2.jpg)

![Sample Audio Directory Structure: Group 3](https://github.com/NYPL/ami-specifications/blob/master/ami-specificationsImages/SampleAudioDirectoryStructure_gp3.jpg)

![Sample Video Directory Structure: Group 1](https://github.com/NYPL/ami-specifications/blob/master/ami-specificationsImages/SampleVideoDirectoryStructure_gp1.jpg)

![Sample Video Directory Structure: with Closed Captioning](https://github.com/NYPL/ami-specifications/blob/master/ami-specificationsImages/SampleVideoDirectoryStructure_video_CC.jpg)

![Sample Video Directory Structure: with Image Directory](https://github.com/NYPL/ami-specifications/blob/master/ami-specificationsImages/SampleVideoDirectoryStructure_video_imageDir.jpg)
