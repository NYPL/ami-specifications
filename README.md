# AMI Digital Asset Technical Specifications

This document outlines the technical specifications and requirements for digitization of analog media collections and digital packaging of deliverable files. For corresponding information about metadata; shipping, handling and reporting; and project administration, please see:

![ami-handling](https://github.com/NYPL/ami-handling)
![ami-metadata](https://github.com/NYPL/ami-metadata)

## Table Of Contents
<!-- MarkdownTOC -->

- [Specifications for Digital Assets](#specifications-for-digital-assets)
  - [Film Media](#film-media)
  - [Video Media](#video-media)
  - [Audio Media](#audio-media)

<!-- /MarkdownTOC -->


<a name="specifications-for-digital-assets"></a>
# Specifications for Digital Assets

Specifications may be modified over time to reflect changes in best practices or NYPL’s digital infrastructure, or to reflect previously unspecified media or conditions.

The following sections are broken into format groups to define the file deliverables for different media types and format variations.

<a name="film-media"></a>
## Film Media

#### _Deliverables_
For each original recording, the following shall be produced:
* One preservation master file*
* One mezzanine file*
* One service copy file*
* One metadata file per media file
**If the object has audio content (i.e. composite sound print), audio must be synchronized and embedded in all final deliverables.**

**_Capture tools_**

Film must be digitized and captured as DPX, then transcoded with any synchronous Broadcast Wave files to FFV1/FLAC/Matroska using RAWcooked (https://mediaarea.net/RAWcooked).

### Film Groups 1 and 2: Motion picture film, silent / sound
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
| Image corrections | Color corrected for dye fading, cropped to picture - no frame-lines or sound track visible, Non-anamorphic | Color corrected for dye fading, cropped to picture - no frame-lines or sound track visible, Non-anamorphic | Color corrected for dye fading, cropped to picture - no frame-lines or sound track visible, Non-anamorphic |

#### **_Service copy file specifications: Film group 1 & 2 (Motion picture film, silent / sound)_**

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
| Image corrections| Color corrected for dye fading, cropped to picture - no frame-lines or sound track visible, Non-anamorphic | Color corrected for dye fading, cropped to picture - no frame-lines or sound track visible, Non-anamorphic | Color corrected for dye fading, cropped to picture - no frame-lines or sound track visible, Non-anamorphic |

### Film Group 3: Audio film

#### **_Preservation master file specifications: Film group 3 (Audio film)_**

| Source format | 35mm | 16mm | 8mm / Super 8mm / Double 8mm |
| --- | ---| --- | --- |
| Audio data encoding | Free Lossless Audio Encoding (FLAC) | Free Lossless Audio Encoding (FLAC) | Free Lossless Audio Encoding (FLAC) |
| Wrapper | FLAC (.flac) | FLAC (.flac) | FLAC (.flac) |
| Bit depth | 24 bit | 24 bit | 24 bit |
| Sampling rate | 96,000 Hz | 96,000 Hz | 96,000 Hz |
| Number of audio channels | (same as source) | (same as source) | (same as source) |
| Other characteristics | If there are tones / sync marks present, they must be captured or resolved and described in metadata signal notes. | If there are tones / sync marks present, they must be captured or resolved and described in metadata signal notes. | If there are tones / sync marks present, they must be captured or resolved and described in metadata signal notes. |
| BEXT metadata | If possible, BEXT metadata must be embedded as per specifications for audio deliverables | If possible, BEXT metadata must be embedded as per specifications for audio deliverables | If possible, BEXT metadata must be embedded as per specifications for audio deliverables |

#### **_Edit master file specifications: Film group 3 (Audio film)_**

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

<a name="video-media"></a>
## Video media

### _Deliverables_
For each original recording, the following shall be produced:
  * One preservation master file
      * If captions are present in source, one closed captions sidecar file
  * One service copy file
  * One metadata file per media file
  * Image files as described

**_Capture tools_**
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
