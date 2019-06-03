# AMI Digital Asset Technical Specifications

This document outlines the technical specifications and requirements for digitization of analog media collections and digital packaging of deliverable files. For corresponding information about shipping, handling and reporting, please see:

![ami-handling](https://github.com/NYPL/ami-handling)

## Table Of Contents
<!-- MarkdownTOC -->

- [Specifications for Digital Assets](#specifications-for-digital-assets)
  - [FILM MEDIA](#film-media)
    - [Preservation Master file specifications: Film groups 1 and 2](#preservation-master-file-specifications-film-groups-1-and-2)
    - [Mezzanine file specifications: Film groups 1 and 2](#mezzanine-file-specifications-film-groups-1-and-2)
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
    - [Audio channel / track configurations and terminology matrix](#audio-channel--tack-configurations-and-terminology-matrix)
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


<a name="specifications-for-digital-assets"></a>
# Specifications for Digital Assets

Specifications may be modified over time to reflect changes in best practices or NYPL’s digital infrastructure, or to reflect previously unspecified media or conditions.

The following sections are broken into format groups to define the file deliverables for different media types and format variations.

<a name="film-media"></a>
## Film Media
**Deliverables**
For each original recording, the following shall be produced:
* One preservation master file*
* One mezzanine file*
* One service copy file*
* One metadata file per media file
**If the object has audio content (i.e. composite sound print), audio must be synchronized and embedded in all final deliverables.**

*_Capture tools_*
Film must be digitized and captured as DPX, then transcoded with any synchronous Broadcast Wave files to FFV1/FLAC/Matroska using RAWcooked (https://mediaarea.net/RAWcooked).

<a name="preservation-master-file-specifications-film-groups-1-and-2"></a>
#### **_Preservation master file specifications: Film groups 1 & 2: Motion picture film, silent / sound_**

| Source format | 35mm | 16mm | 8mm / Super 8mm / Double 8mm |
| ---- | ---- | ---- | ---- |
| Video bit depth | 16 bit | 10 bit | 10 bit |
| Resolution | 4K optical side overscan | 2K optical side overscan | 2K optical side overscan |
| Video codec | FFv1 version 3 from DPX | FFv1 version 3 from DPX  | FFv1 version 3 from DPX |
| File wrapper | Matroska (.mkv) from DPX | Matroska (.mkv) from DPX | Matroska (.mkv) from DPX |
| Frame size | 4096x3112 | 2048x1556 | 2048x1556 |
| Frame rate | (Same as source. If not described, please determine on viewing and describe in metadata signal) | (Same as source. If not described, please determine on viewing and describe in metadata signal) | (Same as source. If not described, please determine on viewing and describe in metadata signal) |
| Pixel aspect ratio | 1.000 | 1.000 | 1.000 |
| Audio bit depth* | 24 bit | 24 bit | 24 bit |
| Audio sampling rate* | 96,000 Hz | 96,000 Hz | 96,000 Hz |
| Audio codec/data encoding* | FLAC from PCM/WAV | FLAC from PCM/WAV | FLAC from PCM/WAV |
| Audio channels* | Same as source object | Same as source object | Same as source object |
| Color space | Linear RGB | Linear RGB | Linear RGB |
| Color primaries | BT.709 | BT.709 | BT.709 |
| Transfer characteristics | Printing Density | Printing Density | Printing Density |
| Notes | Transcoded to FFV1/MKV from DPX using RAWCooked | Transcoded to FFV1/MKV from DPX using RAWCooked | Transcoded to FFV1/MKV from DPX using RAWCooked |

<a name="mezzanine-file-specifications-film-groups-1-and-2"></a>
#### **_Mezzanine file specifications: Film group 1 & 2 (Motion picture film, silent / sound)_**

| Source format | 35mm | 16mm | 8mm / Super 8mm / Double 8mm |
| --- | ---| --- | --- |
| Bit depth | 10 bit | 10 bit | 10 bit |
| Resolution | 1920 x 1080 | 1920 x 1080 | 1920 x 1080 |
| Display aspect ratio | 16:9 pillarboxed / letter boxed as needed | 16:9 pillarboxed / letter boxed as needed | 16:9 pillarboxed / letter boxed as needed |
| Video codec | ProResHQ | ProResHQ | ProResHQ |
| File wrapper | Quicktime | Quicktime | Quicktime |
| Frame size | 1920 x 1080 | 1920 x 1080 | 1920 x 1080 |
| Frame rate | (Same as preservation master) | (Same as preservation master) | (Same as preservation master) |
| Broadcast standard | NTSC | NTSC | NTSC |
| Scan type | Progressive | Progressive | Progressive |
| Pixel aspect ration | 1.000 | 1.000 | 1.000 |
| Audio data encoding* | PCM | PCM | PCM |
| Audio bit rate* | 2304 kbps | 2304 kbps | 2304 kbps |
| Audio bit depth* | 24 bit | 24 bit | 24 bit |
| Audio sampling* rate* | 48,000 Hz | 48,000 Hz | 48,000 Hz |
| Audio channels* | same as Preservation Master* | same as Preservation Master* | same as Preservation Master* |
| Color space | 4:2:2 | 4:2:2 | 4:2:2 |
| Image corrections | Color corrected for dye fading,
Cropped to picture - no frame-lines or sound track visible, Non-anamorphic | Color corrected for dye fading,
Cropped to picture - no frame-lines or sound track visible, Non-anamorphic | Color corrected for dye fading,
Cropped to picture - no frame-lines or sound track visible, Non-anamorphic |

#### _Service copy file specifications: Film group 1 & 2 (Motion picture film, silent / sound)_

| Source format | 35mm | 16mm | 8mm / Super 8mm / Double 8mm |
| --- | ---| --- | --- |
| Bit depth | 8 bit | 8 bit | 8 bit |
| Resolution | 720 x 486 | 720 x 486 | 720 x 486 |
| Display aspect ratio | 4:3 letterboxed as needed | 4:3 letterboxed as needed | 4:3 letterboxed as needed |
| Video codec | H264 | H264 | H264 |
| File wrapper | MPEG-4 (.mp4) | MPEG-4 (.mp4) | MPEG-4 (.mp4) |
| Color space | 4:2:2 | 4:2:2 | 4:2:2 |
| Frame size | 720 x 486 | 720 x 486 | 720 x 486 |
| Frame rate | (Same as preservation master) | (Same as preservation master)  | (Same as preservation master) |
| Broadcast standard | NTSC | NTSC | NTSC |
| Scan type | Progressive | Progressive | Progressive |
| Pixel aspect ratio | 1.000 | 1.000 | 1.000 |
| Audio codec | AAC | AAC | AAC |
| Audio bit rate | 320 kbs | 320 kbs | 320 kbs |
| Audio sampling rate | 48,000 Hz | 48,000 Hz | 48,000 Hz |
| Audio channels | same as Mezzanine* | same as Mezzanine* | same as Mezzanine* |
| Image | Color corrected for dye fading | Color corrected for dye fading| Color corrected for dye fading |
| corrections | Cropped to picture - no frame-lines or sound track visible, Non-anamorphic | Cropped to picture - no frame-lines or sound track visible, Non-anamorphic | Cropped to picture - no frame-lines or sound track visible, Non-anamorphic |

### Film Group 3: Audio film

#### _Preservation master file specifications: Film group 3 (Audio film)_

| Source format | 35mm | 16mm | 8mm / Super 8mm / Double 8mm |
| --- | ---| --- | --- |
| Audio data encoding | Free Lossless Audio Encoding (FLAC) | Free Lossless Audio Encoding (FLAC) | Free Lossless Audio Encoding (FLAC) |
| Wrapper | FLAC (.flac) | FLAC (.flac) | FLAC (.flac) |
| Bit depth | 24 bit | 24 bit | 24 bit |
| Sampling rate | 96,000 Hz | 96,000 Hz | 96,000 Hz |
| Number of audio channels | (same as source) | (same as source) | (same as source) |
| Other characteristics | If there are tones / sync marks present, they must be captured or resolved and described in metadata signal notes. | If there are tones / sync marks present, they must be captured or resolved and described in metadata signal notes. | If there are tones / sync marks present, they must be captured or resolved and described in metadata signal notes. |
| BEXT metadata | If possible, BEXT metadata must be embedded as per specifications for audio deliverables | If possible, BEXT metadata must be embedded as per specifications for audio deliverables | If possible, BEXT metadata must be embedded as per specifications for audio deliverables |

#### _Edit master file specifications: Film group 3 (Audio film)_

| Source format | 35mm | 16mm | 8mm / Super 8mm / Double 8mm |
| --- | ---| --- | --- |
| Audio data encoding | Flac | Flac | Flac |
| Wrapper | Flac | Flac | Flac |
| Bit depth | equal to preservation master | equal to preservation master | equal to preservation master |
| Sampling rate | equal to preservation master | equal to preservation master | equal to preservation master |
| Number of audio channels | equal to preservation master | equal to preservation master | equal to preservation master|
| Other characteristics | If there are tones / sync marks present, they must be captured and described in metadata signal notes | If there are tones / sync marks present, they must be captured and described in metadata signal notes | If there are tones / sync marks present, they must be captured and described in metadata signal notes |
| BEXT metadata | BEXT metadata must be embedded as per specifications for audio deliverables | BEXT metadata must be embedded as per specifications for audio deliverables | BEXT metadata must be embedded as per specifications for audio deliverables |


### Film Group 4: Filmstrips
NYPL will review recommendations for digitization of filmstrips (and accompanying audio media, where applicable) before defining a specification. Requests for recommendations regarding these objects have been included in the Business Questions section.

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
* .srt sidecar filemames must match their accompanying Preservation Master filename. Example:
  * scb_123456_v01_pm.mkv
  * scb_123456_v01_pm.srt
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

<a name="audio-channel--track-configurations-and-terminology-matrix"></a>
#### Audio channel / track configurations and terminology matrix

![Audio grid](https://github.com/NYPL/ami-specifications/blob/master/ami-specificationsImages/NYPL_audioGrid_2017.jpg)

<a name="section-d-digital-asset-structure"></a>
## Section D: Digital Asset Structure

<a name="file-name-and-file-structure-specifications"></a>
### File name and file structure specifications

<a name="file-names"></a>
#### File names
* NYPL will provide the vendor with a filename “root” for each collection object, consisting of a three-letter prefix, the primary ID, a volume number (and a face number for audio items), and a two-letter suffix indicating the role of the file.  These sections are each separated by an underscore: (prefix)_(primary ID)_(item structure)_(file role)
  * Video example: myd_123456_v01_pm
  * Audio example : myh_987654_v01f01r01_pm
* The vendor is responsible for completing the filename to accommodate multiple volumes, faces, regions, etc. where applicable, as defined by the filename components listed below.

<a name="item-structure"></a>
#### Item structure
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


--
## DRAFT text


### VIDEO MEDIA

#### _Deliverables_
For each original recording, the following shall be produced:
  * One preservation master file
      * If captions are present in source, one closed captions sidecar file
  * One service copy file
  * One metadata file per media file
  * Image files as described

#### _Capture tools_
Preservation master video files must be generated by professional-grade capture devices and software, with either direct capture to FFV1/FLAC/MKV, or transcoding from V210/PCM/MOV. Specific FFmpeg transcoding recipes will be provided by NYPL to ensure consistency.

### Preservation master files, all groups
  * Characteristics intrinsic to the broadcast standard of the source material, including frame rate, pixel aspect ratio, interlacing, resolution, and recording standard (NTSC, PAL, SECAM, etc.) should be preserved.
  * Signal extraction must be optimal, and carried out using the equipment and accessories that are appropriate for the original format characteristics.
  * The most direct and clean signal path must be used at all times from source to destination. There may be no devices inserted in the signal path that are not being used. If there are multiple destination formats being used in the transfer the signal path must be routed in parallel. No daisy-chaining of devices may occur.
  * The highest quality signal format (composite, S-Video, Component, SDI, etc.) available for the source media type must be used throughout the entirety of the signal path from source through destination. Exceptions to this must be explained and requested prior to performing the transfer.
  * Luminance, black, and color levels should be adjusted to existing color bars if they are present on tape and look accurate. If color bars are not present or are clearly inaccurate, preview each tape in order to adjust levels according to the content of the tape using known references (such as blue sky, known blacks and whites, flesh tone, etc.). Luma should be adjusted to fall within broadcast range (100 IRE max) and must not exceed 110 IRE.
  * The transfer should capture all content recorded on the original object, including any bars and tone, slates, or other material coming before the start of the recorded program.
  * The recording should run until the end of the recorded content (picture and sound).  If this endpoint cannot be unambiguously determined, the recording should run until the end of the original object.
  * If present on the source tape, closed captions must be captured.

### Video preservation master sidecar files
#### Closed captions
  * If captions are present in source object, an .scc sidecar file must be created and accompany the preservation master file (closed captioning must be embedded in service copies. See service copy specifications).
      * Format: Scenarist Closed Caption File (.scc)
      * Naming Convention: division_PrimaryID_v01_pm.scc
  * Closed captions specifications may change in the future to accommodate updates to standards or NYPL infrastructure needs.

### QCTools Reports
  * Each video preservation master file should receive a corresponding QCTools report, which will be included in the PreservationMasters Bagged directory as a sidecar file.
      * Format: QCTools Report (gzipped XML) (https://www.bavc.org/preserve-media/preservation-tools)
      * Naming Convention: division_PrimaryID_v01_pm.mkv.qctools.xml.gz

**_Preservation master file specifications:_**
**_video group 1: analog and digital cassettes, analog open reel_**

| Attribute | Specification |
| ---- | ------ |
| Video codec | FFv1 version 3 |
| Data compression | Lossless, Intra-frame (GOP-1) only |
| Chroma subsampling | 4:2:2 YUV |
| Bit depth | 10-bit |
| File wrapper | Matroska (.mkv) |
| Frame rate | (Same as original media) |
| Frame size | (Same as original media) |
| Broadcast standard | (Same as original media) |
| Pixel aspect ratio | D1 NTSC (.91) or PAL (1.09) |
| Slices | 24 |
| Slicecrc | 1 |
| Audio format | FLAC |
| Audio bit depth | 24-bit |
| Audio sampling rate | 48 kHz |
| Audio channels | (Same as original media, see guidelines for silent channels) |

### Silent audio channels
  * If a channel exists and is silent, the channel should be captured and a note should be included in the JSON file that the indicates that the tape and the channels delivered on preservation master file are silent. If a channel is non-existent, then it won't be captured. For example:
  * If soundField="ch.1:mono, ch.2: none" rather than soundField= "mono", then the second channel exists, and source.audioRecording.numberOfAudioChannels = 2 (and the preservation master file delivered will contain 2 channels of audio, one of which is silent).
  * Two silent channels If detected as actual channels / i.e. recorded with "black" vs. not recorded), both channels should be captured and delivered with the preservation master, and a signalNote should be included that the tape is silent.

### Timecode
  * Two forms of legacy/source timecode should be retained: LTC Timecode, recorded on an audio channel, should be captured as an audio stream in the resulting preservation master file; VITC timecode, if present, should be captured through the use of appropriate playback devices and a carefully routed SDI signal chain.

  **_Preservation master file specifications: video group 2: DV (digital video) cassettes_**

  NYPL prefers native capture of DV content, with the understanding that errors and varying conditions may require alternative approaches to signal capture. Below are NYPL primary specifications, followed by specifications for cases where the native DV capture with .dv wrapper is problematic due to problems with a given object.

| Attribute | Specification | Notes |
| ---- | ---- | ---- |
| Video codec | (Same as source) | See note |
| File wrapper | DV (.dv) | See note |
| Other characteristics | (Same as source) | If it is necessary to capture DV or HDV tapes via SDI (i.e. as V210/MOV), due to problematic tapes, deliverables must be transcoded and rewrapped as “.mkv”. |

**_Preservation master file specifications: video group 3: optical discs_**

| Attribute | Specification |
| ---- | ------ |
| File system | ISO 9660 / UDF |
| File wrapper | ISO (.iso) |
| Other characteristics | (Same as source) |

**_Service copy file specifications: all video groups_**

| Attribute | Specification |
| ---- | ------ |
| Video codec | H.264/MPEG-4 AVC (ISO/IEC 14496-10 - MPEG4 Part 10, Advanced Video Coding) |
| Video bit rate | 3.5 Mbit/second |
| Chroma subsampling | 4:2:0 YUV |
| Bit depth | 8-bit |
| File wrapper | MP4 |
| Frame rate | (Same as preservation master) |
| Frame size | (Same as preservation master) |
| Broadcast standard | (Same as original media) |
| Pixel aspect ratio | (Same as preservation master, see below for Anamorphic video) |
| Audio codec | AAC |
| Audio bit rate | 320 kbps |
| Audio sampling rate | 48 kHz |
| Audio channels | 2 (see examples) |
| Closed captions* | CEA-608  (*if applicable) |

#### _Anamorphic video_
  * For service copies created from Anamorphic preservation masters, treat source as D1/DV NTSC or PAL Widescreen to produce a 16 x 9 service copy without padding. Pixel aspect ratio should be 1.21 (NTSC) / 1.46 (PAL).

#### _Complex audio configurations_
  * 4 audio channels on source:
      * If a source tape has 4 audio channels of identical content (i.e. 4 mics in a single room recording the same content), the 4 channels captured in the preservation master should be mixed down to 2 for the service copy.
      * If each audio channel contains different content, consult with NYPL for how to proceed.
          * 2-channel Spanish / English language audio: If one channel contains Spanish dialogue and the other channel contains English dialogue, the audio content of the preservation master and the service copy must be identical.
      * Audible content in only one channel:
          * If there is only audible content in a single channel of any number of channels in a source tape and preservation master, the channel containing audible content should be mapped for production of a 2-channel service copy to provide a better user experience.

#### _Timecode_
  * Audible LTC Timecode should be eliminated, and “normal” content should be duplicated onto the second channel.

#### _Trimming of Heads and Tails_
  * Color bars must not be trimmed.
  * Long tails of black / “snow” / unrecorded content may be trimmed after confirmation that there is no visible or audible recorded content.
  * Trimming must not result in an abrupt end of visible or audible content.

### AUDIO MEDIA

#### Deliberables
For each collection object, the following shall be produced:
  * One or more preservation master file(s)
  * One edit master file per preservation master
  * One metadata file per media file
  * For optical audio only, one CUE file per preservation master file
  * Image files as described

#### Capture tools
Preservation master and edit master files must be captured/encoded as Broadcast Wave Format (BWF), with embedded BEXT metadata (see “Embedded Metadata” section).

Files that exceed the Broadcast Wave Format 4GB file size limitation should be captured as RF64, with the same embedded metadata values. Post-capture, all Broadcast Wave and RF64 files should be transcoded to the FLAC codec and container, with embedded metadata and original modification times retained through the use of the FLAC Utility (https://xiph.org/flac/download.html) by following the command listed on the FFmprovisr website (https://amiaopensource.github.io/ffmprovisr/#flac-tool). Original capture as Wave64 (.w64) is not acceptable.

#### Preservation master
  * Technical guidelines: The production of preservation master files will comply with the technical recommendations, practices and strategies outlined by the International Association of Audiovisual Archives
  * Strategic guidelines - IASA-TC 03, version 3: The production of preservation master files will comply with the ethical recommendations, practices and strategies outlined by the International Association of Audiovisual Archives.
  * Optimal signal extraction from analog sources seeks to be complete, and includes the transfer of the “lead-in” and “play-out” portions of a recording.
  * Analog signals will be converted to a digital bitstream by means of an Analog-to-Digital converter which complies with the specifications in FADGI’s Audio Analog-to-Digital Converter Performance Specification and Test Method.
  * No signal processing will be applied to the Analog-to-Digital converter’s digital bitstream, including, but not limited to equalization, level adjustment, dither, noise reduction.

#### Signal Extraction
  * Signal extraction from analog original audio recordings will comply with the technical recommendations, practices and strategies outlined by the International Association of Audiovisual Archives.
  * Optimal signal extraction for the production of preservation master files should aim to capture the complete dynamic and frequency ranges of the original recording.
  * Signal extraction must be carried out using the equipment and accessories that are appropriate and intended for the original format characteristics.
      * Example: a full-track mono recording on an open reel audio tape must be transferred using a full-track audio head (rather than a stereo head).
      * If this is not possible, provide an explicit proposal for work, subject to NYPL approval.
  * An optimal signal extraction from the original recording will be a flat (unmodified) transfer, free of signal processing, equalization, level adjustment, noise reduction, etc. Exceptions would include:
      * de-emphasis of a recording’s stated pre-emphasis (playback equalization)
      * decoding of a recording’s stated noise-reduction encoding
      * Optimal signal extraction from original sources includes the extraction of the intended signal, along with any unintended signal (such as artifacts and anomalies in the signal associated with the inherent limitations of historic recording technologies).
      * Preservation master files may be one or two-channel (interleaved), and the configuration employed will be determined by the needs of the original recording.
      * Levels may be adjusted ONLY if there is severe distortion or digital clipping from the source, and this adjustment must be noted clearly in the metadata.
      * If a sync tone is present (i.e. Pilottone), tone must be captured or resolved.  
      * For all grooved media, preservation master files must include the “needle-drop” and “needle-lift”.

#### Special circumstances and object-file relationships
  * **Faces:** In general, one preservation master file will be generated for each physically or technically discrete recording area of the original object.
      * For example, each side of an audio cassette or disc will be recorded as a separate preservation master file, identified with a designated Face number.
  * Considerations and circumstances that impact the number of preservation masters generated for each physical object, and/or for each discrete recording area:
      * For an object which is found to have content recorded both forwards and backwards on the same Face, a second Face may be created for the reversed content to be recorded in the proper direction.
      * **Region:** For an object with regions recorded at different speeds or sampling rates, a separate preservation master must be created for each Region (filename_v01f01r01_pm).

        * File overlap:
            * Speed Changes: If multiple preservation masters are created for a single recording due to speed changes, the cut should be made at a logical break in the audible content (if at all possible), and there must be exactly 5 seconds of audible content overlapping between the tail of the first preservation master and the head of the following PM so that the regions may be recombined in the future if necessary.
            * Sampling Rate Changes: If a digital source object has been recorded at multiple sampling rates, a separate preservation master must be created for each region. _These regions do not need to overlap, but please include a note listing the timestamp on the source object where each region begins._

#### Embedded metadata
BEXT metadata must be embedded in each audio file upon capturing to WAV. See Metadata section for details.

**_Preservation master file specifications: audio group 1: analog magnetic_**

  | Attribute | Specification |
  | ---- | ----- |
  |Audio data encoding | Free Lossless Audio Codec (FLAC) |
  | File wrapper | FLAC (.flac) |
  |Bit depth | 24 |
  | Sampling rate | 96,000 Hz |
  | Number of audio channels | (same as source) |

**_Preservation master file specifications: audio group 2: digital magnetic_**

  | Attribute | Specification |
  | ---- | ----- |
  | Audio codec | Free Lossless Audio Codec |
  | File wrapper | FLAC (.flac) |
  | Bit depth | (same as source) |
  | Sampling rate | (same as source) |
  | Number of audio channels | (same as source) |

**_Preservation master file specifications: audio group 3: optical disc_**

#### CUE text files
In congress with capturing a Broadcast Wave file prior to transcoding to .flac, a CUE file must be generated. The CUE file must:
  * Follow the same naming convention as the WAV file, but instead with a ".cue" extension. Example: "myh_123456_v01f01_pm.cue"
  * Be referenced in the JSON file under the technical.cueFile field, by its complete filename
  * Be nested within the Preservation Masters directory, accompanying the Preservation Master WAV file (the Edit master must not have a .cue file):
      * PrimaryID
          * data
              * PreservationMasters
                  * division_PrimaryID_v01f01.flac
                  * division_PrimaryID_v01f01.cue
                  * division_PrimaryID_v01f02.flac
                  * division_PrimaryID_v01f02.cue
                * EditMasters
                  * division_PrimaryID_v01f01.flac
                  * division_PrimaryID_v01f02.flac

  **_Preservation master file specifications: audio group 3: optical disc_**

  | Attribute | Specification |
  | ---- | ----- |
  |Audio codec | Free Lossless Audio Codec (FLAC) |
  | File wrapper | FLAC (.flac) |
  | Bit depth | (same as source) |
  | Sampling rate | (same as source) |
  | Number of audio channels | 2 (left + right discrete) |
  | Other characteristics | CDs should be captured as a single file |

  **_Preservation master file specifications: audio group 4: grooved disc_**

  | Attribute | Specification |
  | ---- | ----- |
  | Audio data encoding | Free Lossless Audio Codec (FLAC) |
  | File wrapper | FLAC (.flac) |
  | Bit depth | 24 |
  | Sampling rate | 96,000 Hz |
  | Number of audio channels | 2 (left + right discrete) |

#### Reproduction details  
  * Playback EQ curves for all discs should be utilized.
      * If a disc’s playback curve is not known or stated on the label, the phono EQ should be set to RIAA (for microgrooves 1948-present) or a “default” curve of 400Hz turnover and -12dB @ 10kHz rolloff (for transcription discs). **All EQ curves should be noted in the metadata digitization process notes.**
  * Equipment
      * NYPL requires either the Time-Step line of phono EQs, or the KAB Souvenir Equalizer. Owl EQs are not acceptable due to the age, added noise floor, and lack of versatility needed for our collections. **Other phono EQs may be submitted for approval.**
  * All discs should be transferred with the cartridge switched to "lateral" unless otherwise indicated on the label.
  * A full complement of stylus shapes and sizes should be on-hand at the vendor transfer station, and **he best sounding size/shape stylus used for transfer should be noted in the metadata digitization process notes.**
        * Modern LP styli must **not** be used to transfer shellac, shellac-vinyl compound, or early vinyl discs.
  * Tone arm requirements:
        * Arm must be long enough to comfortably reach the outer grooves.
        * Arm should be vertically adjustable to accommodate the various thicknesses of pressings.
        * During playback, the angle of the tonearm from front to back should be perfectly parallel in relationship to the disc while it is playing.
  * While playing a face, for any speed changes or instances where the stylus has to be repositioned to continue playing, a separate preservation master must be created for each Region.
      * If the stylus skips, attempt to correct and retransfer the area before and after, add this note into the metadata along with time stamp.
        * If unable to perform these functions, set aside and return to NYPL.

**_Preservation master file specifications: audio group 5: grooved cylinder_**

  | Attribute | Specification |
  | ---- | ----- |
  | Audio data encoding | Free Lossless Audio Codec (FLAC) |
  | File wrapper | FLAC (.flac) |
  | Bit depth | 24 |
  | Sampling rate | 96,000 Hz |
  | Number of audio channels | 2 (left + right discrete) |

#### Reproduction Details
  * No playback EQ curves for cylinder preservation masters. Must be transferred “flat”, with cartridge switched to “vertical”.  
  * At the start of the preservation master file, a 1kHz tone at operating level (-16 dBFS) for 30 seconds should be added.
  * Equipment must be approved by NYPL in writing. NYPL prefers use of Archeophone, Endpoint, or Levin CPS1 cylinder reproducers. Period equipment is not acceptable for use due to age and inconsistency of these machines and the greater potential for damage to the Archival Objects.
  * An appropriate assortment of stylus sizes and shapes for cylinders should be on-hand at the vendor transfer station and **the best sounding size/shape stylus used for transfer should be noted in the phonoCartridge metadata fields.**
  * Player setup and playback practices should adhere to best practices.
  * Careful determination of the groove pitch (Threads Per Inch or TPI), speed (with correction if needed), and cylinder material (brown wax, Gold Moulded, etc.) need to be determined BEFORE transfer and noted in metadata digitization process notes.

**_Edit master file specifications: all audio groups_**

  | Attribute | Specification |
  | ---- | ----- |
  | Audio data encoding | Free Lossless Audio Codec (FLAC) |
  | File wrapper | FLAC (.flac) |
  | Bit depth | equal to preservation master |
  | Sampling rate | equal to preservation master |
  | Number of audio channels | Mono, 1; Stereo, 2 |

#### Head and Tail Edits (Trimming)
  * The “needle-drop” and “needle-lift” present in preservation master files must be edited out of the edit master files.
  * Unrecorded portions of the collection object captured in the preservation master shall be eliminated.
  * Test tones and any equipment noise at the start and/or end of audible content (such as equipment on/off “clicks” or a stylus in the groove) should be trimmed. Trimming should not result in an abrupt start and/or end of audible content.
  * Elimination of the 5-second overlap included on any Preservation Masters that have been split out into multiple files for separate regions / streams / etc.

#### Level adjustment  
  * When balance and/or overall level are insufficient a peak level adjustment of max. -2db may be implemented as necessary.
#### Channel Adjustment
  * Ensuring that "mono" is true mono

### DATA MEDIA  
#### Deliverables
For each collection object, the following shall be produced:
  * One or more preservation master file(s)
  * One metadata file per media file
  * Image files as described

#### Capture tools
Preservation masters must be captured/encoded as ISO9660 Disc Images.

#### Preservation master file specifications: data optical disc
Media in Data Group 1 are distinguished from media in Audio Group 3 and Video Group 3 as follows:
  * Data Group 1 uses an ISO 9660 file system to encode data
  * Data Group 1 discs do not contain a top-level directory title “AUDIO_TS” or “VIDEO_TS”

  | Attribute | Specification |
  | ---- | ----- |
  |File system | ISO 9660 / UDF |
  | File wrapper | ISO (.iso) |
  | Other characteristics | (Same as source) |
