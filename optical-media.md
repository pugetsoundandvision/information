# Optical A/V Media Workflows and Recommendations

## Introduction

Due to the nature of their respective standards, media items that are on optical discs require distinct preservation workflows from other types of digital content. The following information presents workflows and tool examples that facilitate the preferred preservation deliverables of UW Libraries for these formats. 

## CDDAs (Audio CDs)


### Background

Audio CDs (known as CD-DA for Compact Disc Digital Audio) contain a raw stream of audio data with an index and thus can't be 'imaged' in the same way as other digital media. Also - due to compromises made between error correction and storage space, when migrating audio CDs it is important to use specialty software that is capable of multiple passes. (As an example - according to [this paper](https://www.weareavp.com/wp-content/uploads/2014/04/OpticalMediaPreservation.pdf) by AVP, consumer players average about a 5% error rate, so a single pass would risk only capturing 95% of the audio content per disc).

The following workflow will provide recommendations for suitable software, as well as brief notes on other CD-DA specific considerations.

#### CD Drive Offsets

Different CD drives start their playback with slightly different offsets of samples. This means, that if it is desired to verify the integrity of a transfer by using checksums to compare against other transfers of the same disc (such as through a database like [Accuraterip](http://www.accuraterip.com/)) this offset must be established and the transfer software must be calibrated accordingly.

If using Exact Audio Copy, the drive model information will appear in the upper left corner of the window:

![EAC drive model number example](resources/drive-number.jpg)

This model number can then be used to search in the [Accuraterip list of drive offsets](http://www.accuraterip.com/driveoffsets.htm).


#### CD Pre-emphasis

Some CDs were created using frequency emphasis that must be accounted for and reversed on playback for correct sound. (This is analogous to the [RIAA curve](https://en.wikipedia.org/wiki/RIAA_equalization) used on LPs and their need to be played back with a phono amp). CD Players that are standards compliant will be able to detect emphasis, however this will not automatically occur during any migration. This is relatively rare, and occurs mostly on older CDs from the 1980s. Nonetheless, it should be considered when planning any migrations that might contain affected materials. Should an example of a CD containing pre-emphasis be desired, [_Can't Slow Down_](https://alliance-primo.hosted.exlibrisgroup.com/permalink/f/kjtuig/CP71148760790001451) by Lionel Ritchie is available in the UW Libraries Collection.

To accurately preserve both the contents of the optical disk, as well as the intended presentation experience of the CD, if a CD contains pre-emphasis two versions of the content should be created. A 'flat' version of the CD should be migrated, with the appropriate flags indicating pre-emphasis contained in the associated CUE sheet. Any CDs reproduced from this combination will play correctly with de-emphasis applied. In addition to this, a digital listening copy should be created that has had a de-emphasis filter applied. For methods to do this, see [Appendix A](#appendix-a).


![EAC window example](/resources/EAC.jpg)

## DVDs

### Background

![Isobuster window example](/resources/isobuster.jpg)

### Appendix A
There are several methods to apply a de-emphasis filter. If the CD is still available, ripping it via the Apple iTunes software will automatically create a de-emphasized version. If de-emphasis needs to be applied to an already existing file, the following are two options.

__FFmpeg__

The media manipulation tool [FFmpeg](https://www.ffmpeg.org/) contains an EQ filter that can reverse emphasis with the following command: `ffmpeg -i input_file.wav -af aemphasis=type=cd deemphasized_file.wav`

Command from [ffmprovisr](https://amiaopensource.github.io/ffmprovisr/#cd_eq).

A de-emphasis curve can be added to the popular tool [Audaciy](https://www.audacityteam.org/), which can then be applied to a target file.

The following text should be added to the Audacity configuration file EQCurves.xml

```
<curve name="RedBookPre">
<point f="700.000135021151" d="0.000000000000"/>
<point f="1000.101652520304" d="-0.500512741089"/>
<point f="1950.142416511543" d="-1.398496627808"/>
<point f="3000.068564380608" d="-2.502575836182"/>
<point f="5000.000948851137" d="-5.004147338867"/>
<point f="10000.005928346302" d="-7.520062176514"/>
<point f="20000.322508988818" d="-9.504367828369"/>
</curve>
```
The file can then be edited in audacity and the new curve applied via the 'Equalization' effect.

Curve was created using the information in [this paper](https://web.archive.org/web/20170704181101/https://audioxpress.com/assets/upload/files/galo3025.pdf) by a user in the [Audacity Forums](https://web.archive.org/web/20200402221556/https://forum.audacityteam.org/viewtopic.php?t=9141).