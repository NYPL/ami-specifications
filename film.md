# Specifications for film handling, treatment, and digitization (draft)
## Film treatment, handling, and rehousing

### Film handling
* Films on cores and in archival cans must be stored flat, horizontally. 
* Films in shipping containers and on shipping reels may be stored vertically until rehoused to archival cans and cores to prevent damage prior to rehousing.
* Films should not be transported via sprockets through any equipment unless for syncing purposes through synchronizers. This should apply to all phases of film work, including winding, inspection, cleaning, scanning. Record footage count through scanning as opposed to synchronizer.

### Film cleaning
* Prior to digitization, if condition of the film allows for cleaning, films shall be cleaned with a solvent approved by NYPL, preferably Perchloroethylene. 
* Precaution must be used when cleaning films with magnetic sound. Magnetic film cleaning chemicals must be discussed with with NYPL.
* Cleaning solvents must not remove NYPL unique identifiers; otherwise, a method for reapplying identifiers to film leader must be proposed by the vendor.

### Film repair
* Repair deteriorated or broken splices and perforations as needed to achieve acceptable image capture.
* Any repair actions taken must not result in any significant loss of content or annotations beyond what is necessary to achieve capture. Annotations on leader that must be cut off to make a repair must be included in the JSON metadata. 
* Chemical treatment for deshrinking or rehumidification of shrunken, brittle and/or curling film must be approved with NYPL prior to treatment.

### Film rehousing and leader
* Cans and cores: NYPL anticipates that a majority of film objects will be rehoused to archival cores and containers prior to vendor work, but some objects may not be due to their condition. Only objects which have not been rehoused by NYPL may be rehoused.
  * If needed, non-archival containers, shipping reels, and cores must be replaced with archival containers, cores, and/or reels. must comply with the Photographic Activity Test (PAT, ISO18916) 
  *  must be approved by NYPL
* Leader: Most film objects will have 20 feet of new leader pre-attached (10 feet at head, 10 feet at tail), labeled with NYPL unique identifiers. 
  * If leader must be added to an object: add 10ft of white leader matching the object's material base to the head and tail, and label the head and tail leader with the object's NYPL unique identifier ("Primary" or "CMS" Id). 
    - Convention: **CMS# 123456** [large space] **HEAD**

## Digitization: Film Groups 1 and 2: Motion Picture Film, Silent / Sound
### Deliverables
For each original recording, the following shall be produced: 
* One preservation master file*
* One mezzanine file*
* One service copy file*
* One metadata file per media file
  * If the object has audio content (i.e. composite sound print), audio must be synchronized and embedded in all final deliverables.
  
### Capture tools
* Film must be digitized and captured as DPX, then transcoded with any synchronous Broadcast Wave files to FFV1/FLAC/Matroska using RAWcooked (https://mediaarea.net/RAWcooked).

### Preservation Master Specifications
|Attribute | Specification: 35mm | Specification: 16mm | Specification: 8mm / Super 8mm / Double 8mm |
|---| :---: | :---: | :---: |
| Video bit depth |16 bit|10 bit | 10 bit|
| Resolution | 4K optical side overscan | 2K optical side overscan | 2K optical side overscan |
| Video codec | FFv1 version 3 from DPX |FFv1 version 3 from DPX | FFv1 version 3 from DPX |
| File wrapper | Matroska (.mkv) from DPX | Matroska (.mkv) from DPX | Matroska (.mkv) from DPX |
| Frame size | 4096 x 3112| 2048 x 1556 | 2048 x 1556|
| Frame rate | (Same as original media as determined) | (Same as original media as determined) | (Same as original media as determined) |
| Pixel Aspect Ratio |  1.000| 1.000| 1.000|
|Color space| Linear RGB | Linear RGB | Linear RGB |
| Color primaries | BT.709 | BT.709 | BT.709
| Audio data encoding* | FLAC from PCM/WAV | FLAC from PCM/WAV | FLAC from PCM/WAV |
| Audio bit depth* | 24 bit|  24 bit|  24 bit|
| Audio sampling rate* |  96,000 Hz| 96,000 Hz| 96,000 Hz|
| Audio channels* | Same as source object|Same as source object|Same as source object|
|Transfer characteristics| Printing density | Printing density | Printing density |
|Notes | Transcoded to FFV1/MKV from DPX using RAWCooked | Transcoded to FFV1/MKV from DPX using RAWCooked | Transcoded to FFV1/MKV from DPX using RAWCooked

*If audio is present in recording

### Edit Master Specifications
|Attribute | Specification: (all formats) 
|---| :---: |
| Video bit depth | 10 bit|
| Resolution | 1920 x 1080 |
| Video codec | ProResHQ	|
| File wrapper | Quicktime	|
| Frame size | 1920 x 1080	|
| Frame rate | (Same as preservation master as determined)
| Broadcast Standard | NTSC |
| Scan type | Progressive	|
| Display Aspect Ratio | 16:9, pillarboxed / letter boxed as needed|	
|Color space| 4:02:02	|
| Color primaries | BT.709 | BT.709 | BT.709
| Audio data encding* | AAC|
| Audio bit depth* | 24 bit|
| Audio bit rate* | 320 kbps|
| Audio sampling rate* |  48,000 Hz|
| Audio channels* | Same as preservation master|
|Image corrections | Color corrected for dye fading, Cropped to picture - no frame-lines or sound track visible, Non-anamorphic|

*If audio is present in source object.

### Service Copy Specifications
|Attribute | Specification: (all formats) 
|---| :---: |
| Video bit depth | 8 bit|
| Resolution | 720 x 486 |
| Video codec | H264	|
| File wrapper | MPEG-4 (.mp4)|
| Frame size | 720 x 486	|
| Frame rate | (Same as preservation master as determined)
| Scan type | Progressive	|
| Broadcast Standard | NTSC |
| Display Aspect Ratio | 4:3, letterboxed as needed |
| Color space| 4:02:02	|
| Color primaries | BT.709 | BT.709 | BT.709
| Audio data encding* | PCM|
| Audio bit depth* | 24 bit|
| Audio bit rate* | 2304 kbps|
| Audio sampling rate* |  48,000 Hz|
| Audio channels* | Same as edit master|
| Image corrections | Color corrected for dye fading, Cropped to picture - no frame-lines or sound track visible, Non-anamorphic|

*If audio is present in source object.

## Digitization: Film Group 3: Audio Film
### Deliverables
For each original recording, the following shall be produced: 
* One preservation master file
* One edit master file
* One metadata file per media file
 

### Preservation master *and* Edit master specifications: Film group 3 (Audio film)
|Attribute | Specification: (all formats) 
|---| :---: |
| Audio data encding* | Free Lossless Audio Encoding (FLAC)|
| Wrapper | FLAC (.flac)	|
| Audio bit depth* | 24 bit|
| Audio sampling rate* |  96,000 Hz|
| Audio channels* | Same as source object|
| Other characteristics | If there are tones / sync marks present, they must be captured or resolved and described in metadata signal notes|
| BEXT etadata | If possible, BEXT metadata must be embedded as per specifications for audio deliverables	|



