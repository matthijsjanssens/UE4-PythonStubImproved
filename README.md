# UE4 Python Stub Improvements
A python script which creates an improved Unreal module stub file for better type annotation and auto-completion.

<img width="1060" alt="image" src="https://user-images.githubusercontent.com/8052061/149562408-1847bae0-fdd6-4e6f-98a6-afd9a90da1ad.png">

# Usage
## Generating the Stub File
Set script as a Python Startup script in the Unreal Editor Project Settings and enable Python Developer Mode in the Editor or Project Settings. Restart the Editor (twice if Developer Mode wasn't enabled yet) and find the improved Python Stub file in .../Your-UE4-Project/InterMediate/PythonStubImproved/unreal.py

## Adding it to Visual Studio Code
Add the following workspace setting:
```
{
    "python.defaultInterpreterPath": "C:/Program Files/Epic Games/UE_4.27/Engine/Binaries/ThirdParty/Python3/Win64/python",
    "python.analysis.stubPath": "C:/Repositories/Your-UE4-Project/Intermediate/PythonStubImproved/"
}
```

# Current State
* 3441 return type annotations have been corrected
* ```List.cast(Class, [])``` is turned into ```List[Class]()```
* ```Map.cast(KeyClass, ValueClass, {})``` is turned into ```Dict[KeyClass, ValueClass]()```
* ```Set.cast(Class, [])``` is turned into ```{Class()}```
* ```DEBUG``` constant can be set to ```True``` to highlight before and after changes by commenting out the original code (look for ```# --```).

# Todo
* Fix function argument type annotation (currently often Unknown)
* Support for multiple python versions (currently tested on 3.7.7 and relying on the typing module)
* Extend Unreal classes to expose Editor Properties directly
