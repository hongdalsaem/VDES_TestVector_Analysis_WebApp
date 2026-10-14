# VDES Link 19 Mobile Web Analyzer

Responsive browser-only I/Q waveform viewer, Welch PSD, RRC matched-filter constellation, automatic integer symbol-phase search, 16-QAM blind decision EVM/SNR proxy, touch pan/zoom, axis controls, and PNG export.

## Quick start

Run `python -m http.server 8000` in this folder, then visit `http://localhost:8000` on your PC. The **Load bundled Link 19 vectors** button loads the included 32,768-sample test vectors. You can also select I/Q TXT files independently on PC or mobile.

## Publish to GitHub Pages

Create a GitHub repository (public for free GitHub Pages use), commit **index.html** and the TXT files (optional; omit vectors if they are proprietary), then enable **Settings → Pages → Deploy from a branch → main / (root)**. Open `https://YOUR_USER.github.io/YOUR_REPO/` on a smartphone. Plotly is loaded from a public CDN, requiring internet access when the page is loaded. Uploaded files are processed in-browser; no analysis backend receives them. If bundled vectors are published to a public repository, they become publicly accessible.

## Notes

Default Fs 1,228,800 Hz and SPS 16 are provisional, not verified from manufacturer metadata. RRC rolloff/span are assumed; current timing recovery is integer-phase search, not fractional timing recovery. EVM/SNR proxy is blind decision-directed, not calibrated RF SNR. DSP results may differ slightly from scipy due to FFT/Welch implementation and edge handling. `Normalize constellation gain/phase` applies a decision-directed fit for visual inspection. The `Ideal 16-QAM reference` crosses appear in normalized mode.
