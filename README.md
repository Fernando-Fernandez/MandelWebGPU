# MandelWebGPU

A collection of Mandelbrot set experiments exploring how far browser GPUs can be pushed, starting from
WebGL fragment shaders and moving toward WebGPU compute-oriented approaches. Each HTML file in the root
is a self-contained prototype you can open in a browser (preferably via `http://localhost` to avoid file
URL restrictions).

## Experiments

| File | Description |
| ---- | ----------- |
| `mandelGPU.html` | Baseline WebGL renderer with rectangle zoom, smooth coloring toggle (`s`), and adaptive iteration counts. |
| `mandelGPUFP64.html` | WebGL shader that emulates FP64 operations for deeper zoom stability. |
| `mandelEmulated64.html` | JavaScript/CPU emulated double-precision path for benchmarking and visual comparisons. |

Open `index.html` for a simple landing page that links to each experiment.

## Requirements

- A modern Chromium-based browser (Chrome, Edge, etc.). Firefox Nightly works for the WebGL demos; WebGPU
  flags are still experimental.
- Optional: enable WebGPU behind flags (`chrome://flags` → enable "Unsafe WebGPU") to test upcoming WGSL
  kernels when they are added.

## Running locally

```bash
cd MandelWebGPU
python3 -m http.server 8080
```

Then navigate to `http://localhost:8080/` and pick an experiment from the landing page.

## Next steps

- Port the current fragment shader math to WGSL compute pipelines.
- Compare performance between native GPU double-precision (where available) and emulated techniques.
- Add UI overlays for iteration count, zoom depth, and WebGPU adapter information once compute demos land.
