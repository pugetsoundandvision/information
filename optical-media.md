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



![EAC window example](/resources/EAC.jpg)

## DVDs

### Background

![Isobuster window example](/resources/isobuster.jpg)