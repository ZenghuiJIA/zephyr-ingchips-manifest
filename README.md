# INGCHIPS Zephyr west manifest

This manifest creates a minimal ING9168/ING9188 workspace from the existing
INGCHIPS Zephyr fork and SDK repositories.

```powershell
west init -m git@github.com:ZenghuiJIA/zephyr-ingchips-manifest.git zephyrproject
cd zephyrproject
west update
west build -b ing9168_mini/ing9168 zephyr/samples/hello_world
```

The SDK is checked out at `modules/hal/ingchips`. Its revision is pinned so
that builds do not change when the SDK default branch advances.

The Zephyr project uses `ZenghuiJIA/zephyr` branch
`dev_ingchips_mainline`. The manifest imports only CMSIS from that branch and
does not fetch Nordic or other vendor HAL repositories.
