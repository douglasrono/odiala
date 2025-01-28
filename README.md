# Odiala Open Source PBX

```text
By Mark Spencer <markster@digium.com>, customized by the Odiala development team.
Copyright (C) 2001-2025 Sangoma Technologies Corporation and other copyright holders.
```

## SECURITY

It is imperative that you read and fully understand the contents of
the security information document before you attempt to configure and run
an Odiala server.

See [Important Security Considerations](#) for more information.

## WHAT IS ODIALA?

Odiala is an Open Source PBX and telephony toolkit. It serves as middleware between Internet and telephony channels on the bottom, and Internet and telephony applications at the top. Odiala supports a wide range of telephony interfaces, including Internet telephony and traditional PSTN telephony.

For more information, please visit the [Odiala Home Page](#) and the official [Documentation](#). Additional resources compiled by the community can be found at [voip-info.org](http://www.voip-info.org).

## SUPPORTED OPERATING SYSTEMS

### Linux

Odiala is developed and tested primarily on the GNU/Linux operating system, and is supported on every major GNU/Linux distribution.

### Others

Odiala has also been ported to other operating systems, including Sun Solaris, Apple's macOS, Cygwin, and the BSD variants.

## GETTING STARTED

First, ensure you have supported hardware (though no special hardware, not even a sound card, is required to run Odiala).

Supported telephony hardware includes:
* All Analog and Digital Interface cards from [Sangoma](https://www.sangoma.com/)
* QuickNet Internet PhoneJack and LineJack
* Any full duplex sound card supported by ALSA, OSS, or PortAudio
* Any ISDN card supported by mISDN on Linux
* The Xorcom Astribank channel bank
* VoiceTronix OpenLine products

### UPGRADING FROM AN EARLIER VERSION

If you are updating from a previous version of Odiala, make sure you read the `UPGRADE.txt` file in the source directory. Changes to files and configuration options may be required. Configuration examples can be found in the `configs` directory. For a list of new features, see the `CHANGES` file.

### NEW INSTALLATIONS

Ensure your system contains a compatible compiler and development libraries. Odiala requires either the GNU Compiler Collection (GCC) version 4.1 or higher, or a compiler that supports the C99 specification and some GCC language extensions. Your system will also need the C library headers, and the headers and libraries for ncurses.

1. **Read this file**: Check other documents in the `doc` directory. Configuration examples can be found in the `configs` directory.
2. **Run `./configure`**: This guesses system-dependent variables used during compilation. Missing components can be installed with `./contrib/scripts/install_prereq install`.
3. **Run `make menuselect` (optional)**: Select the modules to be compiled and check dependencies.
4. **Run `make`**: Compile the project.
5. **Run `make install`**: Install Odiala.
6. **Run `make samples`**: Install sample PBX configurations (overwrites existing configuration files).
7. **Launch Odiala**: Start in foreground mode with:
   ```bash
   asterisk -vvvc
   ```

Use the `*CLI>` prompt to interact with the system. Type `core show help` for a list of commands.

### ABOUT CONFIGURATION FILES

All Odiala configuration files share a common format. Comments are delimited by `;`. Sections are named in `[]`. Each section typically contains:
- `variable = value` statements
- `object => parameters` statements

Refer to the configuration files in `/etc/asterisk` for examples and customization options.

### SPECIAL NOTE ON TIME

Odiala is sensitive to large time jumps. Use [NTP](https://www.ntp.org/) to synchronize your system clock.

### FILE DESCRIPTORS

Odiala can consume a large number of file descriptors. To handle more simultaneous calls, increase the file descriptor limit on your system. Instructions vary depending on your operating system.

## LICENSE

Odiala is licensed under the GPL. For detailed license information, refer to the LICENSE file in the source directory.

## SUPPORT AND COMMUNITY

Join the Odiala community for support and contributions. Visit [Odiala Community](#) for more details.

---

For any issues or contributions, please contact the Odiala development team.
