# MQsim_cxl
 2025_final_project
# CXL-flash Design Tools
### Prerequisites
1. The tracing tool runs on a Linux machine. We recommend using a machine with Ubuntu 20.04.5 LTS with Linux Kernel 5.17.4 installed.
2. Our simulator is designed to be independent of the hardware setup. However, it is developed using [Visual Studio 2022 IDE](https://visualstudio.microsoft.com/downloads/) on Windows, and it was only tested on a Windows 11 environment. 

Source code: 
1. [Trace Generator](https://github.com/Sh1mwww/trace_generator.git): a memory tracing tool utilized in this work.
2. [MQSim CXL] (included in this repository): a trace-driven simulator utilized in this work. 
3. [Trace Translator](https://github.com/Sh1mwww/trace_translation.git): an example code to translate \*.vout or \*.pout files to \*.trace files.

Trace files:
1. [Memory Traces for the CXL-flash Simulator](https://doi.org/10.5281/zenodo.7916219): memory trace files (\*.trace) used in our research paper.

# MQSim CXL: A Simulator for CXL-flash

MQSim CXL is a trace-driven CXL-flash device simulator built on top of MQSim-E[7], a version of MQSim[8]. 
The following documentation provides detailed information about the useage of MQSim CXL. 

## Usage in Windows

1. Open the MQSim.sln solution file in MS Visual Studio 2022 or later.
2. Set the Solution Configuration to Release (it is set to Debug by default).
3. Compile the solution.
4. Run the generated executable file (e.g., MQSim.exe) either in command line mode or by clicking the MS Visual Studio run button. 

To run with the run button, 1) under Debug of the top panel, 2) select MQSim Debug Properties, 3) under Configuration Properties, 4) select Debugging, 5) in Command Arguments, enter "-i ssdconfig.xml -w workload.xml" 5) Click OK

Command line execution:

```
$ .\MQSim.exe -i ssdconfig.xml -w workload.xml 
```
## MQSim CXL Specific Execution Configurations 

This simulator is built on top of MQSim-E. However, not all the MQSim-E-native configurations apply to this simulator; hence, we suggest users to utilize the ssdconfig.xml and workload.xml files included in this repository. We recommend only making modifications to parameters specified below and leave rest as they are.