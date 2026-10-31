# LaunchkeyMK4_CustomEncoderSensitivity
This repository contains a modified MIDI Remote Script for the Novation Launchkey MK4 (25 / 37 / 49 / 61). It fixes the default sluggish "slow-turning" behavior of the encoders in DAW mode, allowing for fast, 1-turn sweeps from 0% to 100%—essential for live performance, dub-style mixing, and quick parameter adjustments.

Out of the box, the encoders on the Launchkey MK4 are locked to a relatively slow, high-resolution response in DAW mode. While great for high precision fine-tuning, this makes it difficult to "flick" a parameter from 0% to 100% in a single smooth motion—a common requirement for live performance and dub-style mixing.
This custom script injects a mapping_sensitivity multiplier directly into the Ableton Live 12 API, allowing you to fine-tune the encoder response to your exact preference without losing any of the controller 'smart' script functions (e.g., display feedback, pads, step sequencer, etc.)

Also available for the Launch Control XL 3: [LaunchControlXL3_CustomEncoderSensitivity](https://github.com/metafysikz/LaunchControlXL3_CustomEncoderSensitivity)

**How it Works**

This repository provides a raw elements.py file. By replacing the compiled component in a copy of the default script, you can override the hard-coded "Linear Binary Offset" math that Ableton uses to interpret the Launchkey MK4's relative encoders. All other files are the untouched originals from the default Launchkey_MK4 script.

**Compatibility**
- Tested on Ableton Live 12.3.2 (Windows).
- Launchkey 25 / 37 / 49 / 61 MK4 only. The Launchkey **Mini** MK4 uses its own script and is not affected by this one.

**Installation Instructions**
1. Locate the MIDI Remote Scripts folder of your Ableton Live 12 installation:

e.g.: Windows: C:\ProgramData\Ableton\Live 12 Suite\Resources\MIDI Remote Scripts

e.g.: Mac: /Applications/Ableton Live 12 Suite.app/Contents/App-Resources/MIDI Remote Scripts/

2. Create a new folder called 'Launchkey_MK4_CustomSensitivity' in that folder.
3. Download this repo (green 'Code' button > 'Download ZIP') and unpack the files into the 'Launchkey_MK4_CustomSensitivity' folder.

**Important:** the files (elements.py, \_\_init\_\_.pyc, etc.) must sit directly inside 'Launchkey_MK4_CustomSensitivity', not in a subfolder. Unpacking the ZIP often creates an extra folder like 'LaunchkeyMK4_CustomEncoderSensitivity-main'; if so, move the files out of it. Otherwise Ableton will not show the script in the Control Surface list.

4. Open the '**elements.py**' file with a notepad or any other simple editor, and look for the 'mapping_sensitivity' parameter (below the 'ENCODER SENSITIVITY FIX' comment). Change this setting to your desired preference. The current setting (2.0) feels optimal for me.
5. Open Ableton and go to Preferences > Link/Tempo/MIDI and switch Control Surface 'Launchkey MK4' to 'Launchkey MK4 CustomSensitivity' (Ableton shows the folder name with spaces instead of underscores), leaving all the other MIDI settings of the MIDI controller as is.
6. Updating Settings: If you change the sensitivity later, restart Ableton. If the change doesn't seem to apply, close Ableton and delete the \_\_pycache\_\_ folder inside your script folder. This forces Ableton to recompile your changes on the next launch.

**After an Ableton update**

The .pyc files are taken from Live 12.3.2. If the script stops working after a Live update, copy the .pyc files from the updated original 'Launchkey_MK4' folder into your 'Launchkey_MK4_CustomSensitivity' folder (overwrite, but do **not** copy elements.pyc), and keep this repo's elements.py.

Hope you enjoy :)
