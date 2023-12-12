# DLSS2FSR (formerly FidelityFx Super Resolution 2.0 for Era Engine)
Drop-in DLSS replacement with FSR 2.0 for Era Engine.

## Compilation

### Requirements
* Visual Studio 2022
* latest Vulkan SDK (1.3.216.0)
* DX12
* DX11

### Instructions
* Clone this repo with all of its submodules.
* Compile the FSR 2.0 submodule in external/FidelityFX-FSR2 as instructed in [official documentation](https://github.com/GPUOpen-Effects/FidelityFX-FSR2#quick-start-checklist). Note: I used the GenerateSolutionsDLL.bat but I am sure static libraries will work fine too.
* Open the CyberFSR.sln with Visual Studio 2022.
* Hit Compile in VS2022, if you compiled the FSR2 in Debug mode, compile CyberFSR in Debug mode, and if you compiled the FSR2 DLLs in Release mode, do the same in CyberFSR. This will result in a DLL in either `[root]/x64/Debug/CyberFSR.dll` or `[root]/x64/Release/nvngx.dll`.
* Copy the compiled `ffx_fsr2_api_dx12_x64.dll` and `ffx_fsr2_api_x64.dll` from the FidelityFX Directory to your Cyberpunk 2077 executable directory.
* Rename the compiled DLL from two steps ago to `nvngx.dll` if it is `CyberFSR.dll`.
* Copy `nvngx.dll` to your Cyberpunk 2077 executable directory.
* Run the `EnableSignatureOverride.reg` to allow Cyberpunks DLSS implementation to load unsigned DLSS versions
* Run the game and set the quality in the DLSS settings
* Play the game with FSR 2.0
