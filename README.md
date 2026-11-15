# android_vendor_lineage

Fork of `LineageOS/android_vendor_lineage` with the changes of the **LG G
Pad X 8.0 (V521)** port to **LineageOS 15.1** (Android 8.1).

| Branch | What it is |
| --- | --- |
| `lineage-15.1` | the upstream LineageOS 15.1 branch, unchanged |
| `lineage-15.1-v521` | the branch the V521 port builds from |

## What is different on `lineage-15.1-v521`

| Commit | Subject |
| --- | --- |
| `56e571d` | v521: allow building with an insecure adb |

`ro.adb.secure=1` makes the adb daemon ask for the authorisation of every
host that connects to it.  While the device is being brought up that means
that every adb command has to be confirmed on the screen of the tablet,
which is not workable over a remote shell.

`WITH_ADB_INSECURE=true` skips the property, the same way `lineage-16.0`
does it.  The flag is set in the device tree of the V521, and the default
is unchanged for every other device.

## The port

The full description of the port is in the device tree:
<https://github.com/MicahOttah/android_device_lge_v521>
