# Fuze
An experimental x86_64 hobby OS project.
&nbsp;  
&nbsp;  
&nbsp;  

[![FuzeOS Kernel CI](https://github.com/Sayan505/FuzeOS/actions/workflows/test_knl.yml/badge.svg)](https://github.com/Sayan505/FuzeOS/actions/workflows/test_knl.yml)

&nbsp;
## Road Map
#####  LEGEND:
💙: On my list.  
💛: In-progress.  
💚: Completed.  
&nbsp;
### Progress:
💚 Boot Protocol. (Stiletto)  
💚 UEFI Booting (FuzeBoot; ELF64 kernel).  
💚 Serial Port.  
💚 GDT.  
💙 Re-configure Paging.  
💚 GOP Video.  
💚 Text Renderer on GOP.  
💚 stdout.  
💙 Load IDT.  
💛 pcspkr.  
💙 PMM.  
💙 VMM.  
💙 Parse ACPI tables.  
💙 ACPI Shutdown.  
💙 APICs.  
💙 LAPIC Timer.  
💙 HPET Timer.  
💙 A Graphics Library. (GOP)  
💙 USB Driver.  
💙 stdin.  
💙 PCI Driver.  
💙 SMP & SMT.  
💙 Scheduler.  
💙 Storage Driver. (AHCI, FAT32)   
And, so on...   

&nbsp;

## Build Fuze
### &nbsp; Get the source
&nbsp; &nbsp; `git clone` to test the kernel with the pre-build bootloader or,  
&nbsp; &nbsp; `git clone --recursive` during cloning to fetch this repo and EDK2 + all its submodules or,   
&nbsp; &nbsp; `make init_submodules`, which is `git submodule update --init --recursive` after `git clone` to get EDK2 and its submodules.
### &nbsp; Requirements
* clang (for Kernel)
* GCC (build-essential; for the FuzeBoot Bootloader)
* GNU LD
* nasm
* GNU Parted
* dosfstools
* EDK II (optional; binary included, to build the FuzeBoot bootloader)

### &nbsp; Process
&nbsp; Build full system with disk images (losetup requires root):  
&nbsp; &nbsp; `make`  
&nbsp; Build full system in $(FSDIR) without generating disk images:  
&nbsp; &nbsp; `make testall`  
&nbsp; Build to test the kernel only, in $(FSDIR) without generating disk images:  
&nbsp; &nbsp; `make test`, requires `make bootloader`, once.

&nbsp;

## Run Fuze
&nbsp; Run the full system from the disk image:  
&nbsp; &nbsp; `make run`  
&nbsp; Run the full system from $(FSDIR) in RW mode:  
&nbsp; &nbsp; `make testrun`  

&nbsp;

## Build FuzeBoot UEFI bootloader
### &nbsp; Requirements
* Atleast GCC5 (build-essential)
* uuid-dev / libuuid-devel
* iasl
* nasm
* python3-distutils
* [EDK II](https://github.com/tianocore/edk2):  
###### &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Dependencies of EDK II are subject to change.

### &nbsp; Process
+ Build with FuzeBoot. (Platform and inf included)
+ just do `make bootloader`.
