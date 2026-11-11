# Ocarina of Time (Switch 2) CPU fast-path test

This is an experimental **Windows x64** build, not a verified FPS improvement.
Game: **The Legend of Zelda: Ocarina of Time**, Switch 2 title `0400486024DEC000`.

## Get the build

Use the prerelease Windows ZIP from the [BrodXI/Lichii releases](https://github.com/BrodXI/Lichii/releases). `windows-x86_64-pgo` has a profile previously trained on Ocarina of Time; `windows-x86_64` is the standard build. Unzip into a **new folder**, not over an existing emulator installation.

## Compare the new code with the old path

Use the **same ZIP build** for both tests. Each launch must start in a **new Command Prompt**, opened in the folder containing `lichii.exe`.

**Old callback, control:**

```bat
set "EDEN_NX2_INLINE_CNTPCT=0"
lichii.exe
```

**New inline x64 counter read:**

```bat
set "EDEN_NX2_INLINE_CNTPCT=1"
lichii.exe
```

The default is enabled. This optimization activates only with a CPU supporting invariant TSC, the emulator's **Normal** CPU clock, and **Sync Core Speed off**. Otherwise both commands intentionally run the original code.

## Record a meaningful comparison

1. Use one Ocarina of Time save point and exact location, 1080p or another fixed resolution. Keep CPU/GPU accuracy, graphics backend, VSync, game patches and resolution identical.
2. Compare an **A-B-B-A** order across four separate launches. After shaders and resources have warmed, record at least 60 seconds of standing still per run.
3. Record real FPS (mean and 1% low if available), frame time, CPU usage, GPU usage, CPU/GPU model, build commit and settings. Disable external frame generation or interpolation while measuring.
4. Keep shader caches and game files the same across runs. A launch that compiles large shader batches is not comparable.
5. Watch for visual glitches, audio problems, crashes, or unusual timer behavior. If present, use the control command and report the log.

Higher GPU usage is **not** the objective by itself. Higher real FPS or smoother frame times at the same settings is the test.

This fast path is isolated from the broader GPU-thread optimization proposed in upstream [#805](https://github.com/zortos293/Lichii/pull/805).
