# Retrieving Bitlocker Keys from TPM using SPI or LPC Communications

Retrieving Bitlocker keys from the TPM using SPI or LPC communications requires an understanding of the specific protocol supported by the TPM chip, as well as the device's make and model. Proper documentation and research are essential for successful key retrieval. This repo is to collaborate all the awesome resources and information hopefully into one place!

NOTE: I'm 100% sure that there is alot of blogs/data missing here, but please if you know of any and want to contribute, please DO a PR!

## Introduction

Trusted Platform Module (TPM) is a hardware-based security chip that is often used to store encryption keys securely, including Bitlocker keys used for full disk encryption in Windows environments. Retrieving these keys from the TPM can be achieved through various communication channels, although the specific method may vary depending on the device's make and model.

## Table: TPM Communication Methods

| Make       | Model           | Model Number | TPM       | Protocol | Location   | Debug Headers | Blog/Research   | Extractable |
|------------|-----------------|--------------|-----------|----------|------------|---------------|-----------------|-------------|
| Lenovo     | Gen 6           |              | 2.0       | SPI      | Under Keyboard | Yes     |  | Yes         |
| Dell       | Lattitude       | E5470        | 2.0       | SPI      | Motherboard| Yes          |  | Yes         |
| Example   | Laptop          |              | 1.2       | SPI      | Under Battery  | No          |  | Yes         |

## Research

For further information and detailed instructions, refer to the provided blog posts and research documents.

[A Deep Dive into TPM-based BitLocker Drive Encryption](https://blog.scrt.ch/2023/09/15/a-deep-dive-into-tpm-based-bitlocker-drive-encryption/)

[TPM Sniffing](https://blog.scrt.ch/2021/11/15/tpm-sniffing/)

[Extracting BitLocker keys from a TPM](https://pulsesecurity.co.nz/articles/TPM-sniffing)

[Bypassing Bitlocker using a cheap logic analyzer on a Lenovo laptop](https://www.errno.fr/BypassingBitlocker.html)

[From Stolen Laptop to Inside the Company Network](https://dolosgroup.io/blog/2021/7/9/from-stolen-laptop-to-inside-the-company-network)

[Sniffing Bitlocker Keys on the SPI Bus](https://www.cryptic.red/post/sniffing-tpm-keys-on-the-spi-bus)

[TPM 2.0: Extracting Bitlocker keys through SPI](https://lucasteske.dev/2024/01/tpm2-bitlocker-keys)

[Understanding TPM Sniffing Attacks](https://trmm.net/tpm-sniffing/)

[Breaking Bitlocker: Bypassing the Windows Disk Encryption](https://www.youtube.com/watch?v=wTl4vEednkQ)

[TPM Sniffing Attacks Against Non-Bitlocker Targets](https://www.secura.com/blog/tpm-sniffing-attacks-against-non-bitlocker-targets)

[Sniff, there leaks my BitLocker key](https://labs.withsecure.com/publications/sniff-there-leaks-my-bitlocker-key)

## Tools

A list of awesome tools for sniffing TPM data are listed below.

[bitlocker-spi-toolkit](https://github.com/WithSecureLabs/bitlocker-spi-toolkit)

[Pico-TPMSniffer](https://github.com/stacksmashing/pico-tpmsniffer)

[LPCClocklessAnalyzer](https://github.com/stacksmashing/LPCClocklessAnalyzer)






