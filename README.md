# bitsandbytes-win-prebuilt

This is an experimental build of the bitsandbytes binaries for Windows. 
It's compiled against CUDA11.6 x64 using Visual Studio 2022 under Windows 11. 
In most cases it functions desireably in both Windows 10 and 11, but no vigorious testing is conducted. So, use at your at own risk.  

To use this with the official bitsandbytes codebase, you have to make some hardcoded patch:

```
in cuda_setup/main.py:
make evaluate_cuda_setup() always return "libbitsandbytes_cuda116.dll"
in ./cextension.py:
change ct.cdll.LoadLibrary(binary_path) to ct.cdll.LoadLibrary(str(binary_path))
```

