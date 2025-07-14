# [korg.nanokontrol2 nºport]
GOP abstraction form korg nanokontrol2 controller for plug and play use on Pure Data

![Nanokontrol2 in Pure Data](gui.jpg)


 # 🎛️ Korg Nanokontrol 2 Abstraction for Pure Data

A Pure Data abstraction that replicates the interface of the **Korg Nanokontrol 2** MIDI controller using **Graph-On-Parent (GOP)** functionality. It allows intuitive, zero-patching control of elements in the parent patch, with instant visual feedback.

## 🚀 Features

- Plug-and-play control directly within the parent patch via GOP.
- Visual feedback in real-time.
- Sends and receives MIDI messages to/from the parent patch.
- Built-in **savestate system** for multiple independent instances.
- Single argument (`port number`) that matches your Pure Data MIDI settings.

## 🎚️ Usage

1. Open Pure Data and configure your desired MIDI port number in `Media > MIDI settings`.
2. Create an instance of the abstraction using the port number:
3. Send and receive data to/from parent patch. To receive data from the controller, just use its send outlet and filter with [route nºparam] to get the control value. To send data to the controller, use the receive inlet to send [param_set nºparam value( or [param_label nºparam name_param( messages to the controller. This is more explained in details on the help patch. 
   ```pd
   [korg.nanokontrol2 1]
## NOTE: It has only one creation argument: number port and it should match the number choose in midi setting dialog.
## NOTE: Else library is necessary to use it.
## NOTE: Unnasigned buttons the "Loop", "Backward", and "Forward" buttons are currently unassigned. When pressed, they flash yellow to indicate their availability for future functionality.
## NOTE: using multiple instances of [korg.nanokontrol2] is possible but without open the help patch. 
## NOTE: Is neceessary to use the abs in conjunction with its respetive patch of the Korg Editor which is provided as well.
## NOTE: Ii is recommended that controller is in CC generic mode, you can ensure it by pressing CYCLE + SET MARKET when connecting the device. 
