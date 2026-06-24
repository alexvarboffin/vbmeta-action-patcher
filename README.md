## Patch your VBMeta Image
This github action will let you patch your vbmeta. Prebuilt files for patching aren't mine, all the credits should be given to him; [lbxzr](https://github.com/libxzr)'s [vbmeta-disable-verification](https://github.com/libxzr/vbmeta-disable-verification).

## Guide
* Fork this repository.
* Replace `vbmeta.img` with your stock or from android (google) source.
* Go to `Action` tab, then Run the workflows.
* Go to `Release` section of the repository, download the new vbmeta image, and flash it.

## Notes
* It is equivalent to: `fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img`.
* **Architecture** selects which patcher binary to run on the GitHub runner, not your phone's CPU. GitHub Actions uses `x86_64` Linux — pick **x86_64** for the fastest run (recommended). Other architectures work via QEMU emulation.
* If patching failed with `cannot execute binary file: Exec format error`, you chose a binary that does not match the runner; use **x86_64**.
