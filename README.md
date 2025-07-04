# TPM SNIFFING

Retrieving Bitlocker keys from a dTPM using SPI, I2C or LPC communications requires an understanding of the specific protocol supported by a dTPM chip, as well as the device's make and model. Proper documentation and research are essential for successful key retrieval. This repo is to collaborate all the awesome resources and information hopefully into one place!

NOTE: I'm 100% sure that there is alot of blogs/data missing here, but please if you know of any and want to contribute, please DO a PR!

## Introduction

Trusted Platform Module (TPM) is a hardware-based security chip that is often used to store encryption keys securely, including Bitlocker keys used for full disk encryption in Windows environments. Retrieving these keys from a dTPM can be achieved through various communication channels, although the specific method may vary depending on the device's make and model.

## Table: TPM Communication Methods

| Make      | Model         | Model Number        | TPM     | Chipset          | Protocol | Location                        | Debug Headers                          | Blog/Research                                                                       | Extractable |
|-----------|---------------|---------------------|---------|------------------|----------|---------------------------------|----------------------------------------|-------------------------------------------------------------------------------------|-------------|
| Lenovo    | Thinkpad      | L440                | 1.2     | P24JPVSP         | LPC      | Under Keyboard                  | Yes                                    | [Blog](https://blog.scrt.ch/2021/11/15/tpm-sniffing/)                               | Yes         |
| Lenovo    | X1 Carbon     | Gen 11              | 2.0     | ST33TPHF2XSPI    | SPI      | Under Motherboard               | Test Pads                              | [@NoobieDog](https://x.com/NoobieDog/status/1755166872985571662?s=20)               | Yes         |
| Lenovo    | T460          | BT462 NM-A581 rev.2 | 1.2     | SLB9670VQ1.2     | SPI      | Under Motherboard               | Extractable via BIOS Chip              | [@zaphoxx](https://twitter.com/zaphoxx/status/1763669704177078560)                  | Yes         |
| Lenovo    | Thinkpad      | X380 Yoga           | 1.2/2.0 | P68HAHB5         | SPI      | Under Motherboard               | Test Pads                              | [Github](https://github.com/Theophile-Wemaere/TPM-sniffing)                         | Yes         |
| Lenovo    | Thinkpad      | T470                | 2.0     | ST33HTPH2E32AHA6 | SPI      | Motherboard (QFN package)       | Extractable via BIOS Chip (U49) SOIC8  | [@lowercase_drm](https://x.com/lowercase_drm/status/1912783481546883149)            | Yes         |
| Dell      | Lattitude     | E7450               | 1.2     | AT97SC3205       | SPI      | Under Motherboard               | No                                     | [@SecurityJon](https://twitter.com/SecurityJon/status/1445020885472235524)          | Yes         |
| Dell      | Lattitude     | E5470               | 2.0     | NPCT650JAOYX     | SPI      | Motherboard                     | Yes                                    | [Blog](https://labs.withsecure.com/publications/sniff-there-leaks-my-bitlocker-key) | Yes         |
| Dell      | Lattitude     | E5450               | 1.2     | AT97SC3205       | SPI      | Motherboard                     | Yes                                    | [Blog](https://luemmelsec.github.io/Go-away-BitLocker-you-are-drunk/)               | Yes         |
| Microsoft | Surface Pro 3 |                     | 2.0     | SLB9665TT2.0     | LPC      | Under Battery                   | No                                     | [Blog](https://pulsesecurity.co.nz/articles/TPM-sniffing)                           | Yes         |
| Asus      | TPM-M R2.0    |                     | 2.0     | SLB9665TT2.0     | LPC      | -                               | Yes                                    | [Video](https://www.youtube.com/watch?v=-Fj3SeZww3M)                                | Yes         |
| HP        | Elite         | 640 g9              | 2.0     | SLB9670          | SPI      | -                               | Yes                                    | -                                                                                   | Yes         |
| HP        | Elite         | 830 G7              | 2.0     | SLB9670VQ        | SPI      | Under Motherboard (QFN package) | Extractable via 25Q256JVEN chip WSON8  | [@lowercase_drm](https://x.com/lowercase_drm/status/1917155760192291171)            | Yes         |
| HP        | Elite         | 1040 G3             | 2.0     | SLB9670VQ        | SPI      | Under Motherboard (QFN package) | Extractable via BIOS Chip (U23) SOIC8  | [@lowercase_drm](https://x.com/lowercase_drm/status/1912783481546883149)            | Yes         |
| HP        | Elite         | 1040 G10            | 2.0     | NPCT760HABYX     | SPI      | Under Motherboard               | Extractable via 25Q256JVEN (chip U367) | [@lowercase_drm](https://x.com/lowercase_drm/status/1935300711224361382)            | Yes         |

## Research

For further information and detailed instructions, refer to the provided blog posts and research documents.

[Privilege escalation through TPM Sniffing when BitLocker PIN is enabled](https://blog.scrt.ch/2024/10/28/privilege-escalation-through-tpm-sniffing-when-bitlocker-pin-is-enabled/)

[Stealing the Bitlocker key from a TPM](https://astralvx.com/stealing-the-bitlocker-key-from-a-tpm/)

[TPM Hate Him! TPM Attacks](https://hacky.solutions/blog/2024/02/tpm-attack)

[Microsoft bitLocker bypasses are practical](https://blog.compass-security.com/2024/02/microsoft-bitlocker-bypasses-are-practical/)

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

[Bitlocker Attacks](https://github.com/Wack0/bitlocker-attacks)

[BitCracker: BitLocker meets GPUs](https://arxiv.org/abs/1901.01337)

[TPM Fail](https://tpm.fail/)

[TPM Vulnerabilties](https://www.bleepingcomputer.com/news/security/new-tpm-20-flaws-could-let-hackers-steal-cryptographic-keys/)

[AMD TPM Exploit](https://www.tomshardware.com/news/amd-tpm-hacked-faultpm)

[Sniffing Bitlocker Keys 2024](https://en4rab.github.io/posts/Sniffing-Bitlocker-Keys/)

## Tools

A list of awesome tools for sniffing TPM data are listed below.

[bitlocker-spi-toolkit](https://github.com/WithSecureLabs/bitlocker-spi-toolkit)

[Pico-TPMSniffer](https://github.com/stacksmashing/pico-tpmsniffer)

[LPCClocklessAnalyzer](https://github.com/stacksmashing/LPCClocklessAnalyzer)

[PICO TPM SNIFFER - SPI](https://github.com/zaphoxx/pico-tpmsniffer-spi)

[libsigrokdecoder_spi-tpm](https://github.com/ghecko/libsigrokdecoder_spi-tpm)

[IceStick LPC TPM Snigger](https://github.com/SySS-Research/icestick-lpc-tpm-sniffer)

[SPITKey](https://github.com/en4rab/SPITkey)


## Trainings

[Hands-on-security Bitlocker/TPM Hardware training Course](https://hands-on-security.com/#trainings)

## Mitigations 

The only mitigation for this attack is to enable BitLocker with a PIN OR security key which is adds "Preboot Authentication”. The sniffable key isnt released until after the correct pin is entered. Enterprises rarely use the PIN or security key because it’s inconvenient for users, they need to enter the unlock PIN then their normal user password. 

[Preboot Authentication](https://learn.microsoft.com/en-us/windows/security/operating-system-security/data-protection/bitlocker/countermeasures#preboot-authentication)



