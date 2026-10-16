# Test_IccP — IccP_Test (printer engine) black-box test data

Golden compare suite for `apps/IccP_Test`:

- `Printer.icc` — output printer profile (CI/Linux: resolved as
  `<TestDir>/<PrinterName>.icc` via `AV_IccP_SetIccPath`; the test passes
  the printer name `Printer`)
- `sRGB2.tif`  — input image
- `Target.tif` — golden output for `sRGB2.tif` → Printer.icc (Perceptual,
  sRGB input, pure-color K, GBU33_low filter)

Run (from this directory, CWD matters):

```
IccP_Test.exe Printer sRGB2.tif out.tif
```

`out.tif` is generated and ignored by git; CI diffs it against `Target.tif`.
