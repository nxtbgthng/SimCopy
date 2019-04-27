# SimCopy

This is a small command line utility (*written in Swift!*) that's been written out of a need to synchronize HomeKit configurations between iOS simulators.

If you run the HomeKit Simulator (available from `Xcode -> Open Developer Tool -> More Developer Tools…` ) on the same machine as the iOS Simulator, you can actually add simulated HomeKit devices to the simulator and test your app there! 🎉

*But there's a catch*: Each simulator is a new device, and needs a new connection to the simulated HomeKit devices. However: A HomeKit device can only be added once and then it needs to reset. So the solution is to copy the HomeKit configuration (that's `homed` and `KeyChain`) to all the other simulators once you have configured it for one. I couldn't find anything that does this, so I wrote a little tool.

**Note: This is only as sophisticated as I needed it, and can be improved on versatility, robustness and error handling. Feel free to fork send a Pull Request if you want to extend it**

Here's how to use it:

- Have a working Xcode toolchain (If you made it this far, you probably have…)
- Make the `simcopy` file executable

```
Use this tool to copy the HomeKit Configurations between iOS simulators.

  simcopy help
    Prints this help.

  simcopy copyhome <sourceUDID> <targetUDID>
    Copies the HomeKit configuration and KeyChain from one simulator to the other.

  simcopy spreadhome <devicename>
    Copies the HomeKit configuration from the simulator with the specified name to all simulators with the same runtime (OS version).
```

Have "fun" ;-)
