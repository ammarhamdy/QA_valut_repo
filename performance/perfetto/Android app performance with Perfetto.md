
https://ui.perfetto.dev/
https://perfetto.dev/docs/getting-started/system-tracing

---

# What Perfetto Is

`Perfetto` is Google’s **official performance tracing tool** for Android.  
It is the successor of `Systrace` and is used internally by Google, `OEMs`, and game studios.

`Perfetto` helps you profile:
✔ Frame rate (FPS, jank)
✔ UI Thread / `RenderThread` stalls  
✔ Input latency  
✔ Layout & measure time  
✔ CPU usage per process/thread  
✔ Memory usage, allocations  
✔ GPU rendering  
✔ System-level I/O, network, Binder calls  
✔ Battery / power

---

# The Two Main Ways to Use `Perfetto`

## Option A — `Perfetto` UI (web):
[https://ui.perfetto.dev](https://ui.perfetto.dev)
This is where you **view and analyze** the results.

## Option B — `Perfetto` Command-line tools
You can capture traces using:
- `perfetto` binary
- `adb shell perfetto` (preinstalled on Android)
- Android Studio → Profilers (uses `Perfetto` internally)

---

# How to Record a Perfetto Trace (APK, no source code)

## The Fastest way: Android Studio
1. Connect your device → `Android Studio`
2. Open:  
    **View → Tool Windows → Profiler**
3. Click **"Start new performance recording"**
4. Select capture types:
    - CPU
    - Memory
    - GPU
    - Jank / Frame timing
    - Network
5. Press **Record** → interact with the app → **Stop**
This automatically generates a **`Perfetto` trace**.

## Use Built-in `Perfetto` on the Device (`adb` shell)

```
adb shell perfetto -o /data/misc/perfetto-traces/trace.pb -t 20s \
    sched freq idle am wm gfx view binder_driver
```
This records:
- CPU scheduler
- UI / RenderThread
- GPU / graphics
- Window Manager

Trace location:
```sh
adb pull /data/misc/perfetto-traces/trace.pb trace.pb
```
Open it in **`ui.perfetto.dev`**.

---

# Example
 

```sh
adb start-server
curl -LO get.perfetto.dev/tracebox
chmod +x ./tracebox
./tracebox websocket_bridge
```

Run this to restart DNS service if you need.
```sh
sudo systemctl restart systemd-resolved
```

Start the recording: ![[Pasted image 20251210134527.png]]

