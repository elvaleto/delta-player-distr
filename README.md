<div align="center">

# Delta Player

**Frame generation. RTX video enhancement. Moments worth saving.**

Windows video player for high-refresh displays, HDR films and a more visual way to navigate your videos.

[![Download Windows alpha](https://img.shields.io/badge/Download-Windows%20alpha-8bd5ca?style=for-the-badge)](https://github.com/elvaleto/delta-player-distr/releases/latest) [![All releases](https://img.shields.io/badge/All-releases-30363d?style=for-the-badge)](https://github.com/elvaleto/delta-player-distr/releases)

![Windows 11 x64](https://img.shields.io/badge/Windows%2011-x64-3878c7?style=flat-square) ![NVIDIA RTX](https://img.shields.io/badge/NVIDIA-RTX-76b900?style=flat-square&logo=nvidia&logoColor=white) ![RIFE](https://img.shields.io/badge/Interpolation-RIFE%20%2F%20Micro%20Riffe-a78bfa?style=flat-square) ![Renderers](https://img.shields.io/badge/Direct3D%2012-Vulkan-64748b?style=flat-square)

</div>

> **0.1.2 development preview.** Screenshots show the current development build. The public download is **0.1.1 alpha (build 1122)**; the Marks and Watch history features below are coming in 0.1.2.

| Motion that fits your display | More from your picture |
| :--- | :--- |
| **NVIDIA Video Frame Generation, RIFE and Micro Riffe**, with scene-cut detection to avoid blending across cuts. VRR-aware frame pacing. | **RTX Video Super Resolution + TrueHDR**, HDR10 / HLG, Dolby Vision metadata through HDR10 output, and dynamic tone mapping. |

<table>
<tr>
<td width="50%" valign="top">
<strong>Playback HUD</strong><br>
See the HDR-to-display color path and tone-mapping mode. Scrub the timeline with visual previews.<br><br>
<a href="assets/hud.webp"><img src="assets/hud.webp" alt="Playback HUD: HDR10-to-SDR color path, dynamic tone mapping, audio layout and timeline preview" width="100%"></a>
</td>
<td width="50%" valign="top">
<strong>Frame generation controls</strong><br>
Choose a backend, target your display refresh or a frame-rate multiplier, and tune generation resolution.<br><br>
<a href="assets/settings.webp"><img src="assets/settings.webp" alt="Interpolation settings: RIFE on NVIDIA TensorRT CiG, frame-rate targets, multiplier and generation resolution" width="100%"></a>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<strong>Marks · 0.1.2 preview</strong><br>
Save scenes with comments. Search thumbnail cards grouped by video and jump straight back.<br><br>
<a href="assets/marks.webp"><img src="assets/marks.webp" alt="Marks: scene thumbnails grouped by video, with comments, timestamps and search" width="100%"></a>
</td>
<td width="50%" valign="top">
<strong>Watch history · 0.1.2 preview</strong><br>
Resume from thumbnails. See saved positions, progress and dates.<br><br>
<a href="assets/history.webp"><img src="assets/history.webp" alt="Watch history: video thumbnails, saved positions, progress bars and session dates" width="100%"></a>
</td>
</tr>
</table>

**Around the film:** automatic black-bar cropping for ultrawide screens · Ambilight · two independent audio outputs · Steam Audio for headphones · GPU-drawn HUD and native searchable panels.

**Try it:** extract the **whole ZIP**, run `delta-player.exe` or the separate `delta-player-vulkan.exe`, and drop in a video. **F2** → settings; **F1** → controls. Portable data stays beside the app when `portable.ini` is present.

<details>
<summary>Compatibility & preview notes</summary>

Windows 11 x64. Direct3D 12 requires Feature Level 12_1 / Shader Model 6.6; Vulkan is a separate executable. Features depend on the GPU, driver and display. Native NVIDIA VFG targets RTX 40 / 50; other interpolation methods have their own requirements. VRR depends on display and driver configuration. Dolby Vision Profile 7 FEL residual is not applied. This is an alpha distribution; AMD and older GPU coverage remains limited.

Screenshots supplied by the project author; the settings view shows **0.1.2, build 1192**. Click any preview to inspect it at a larger size. Images were resized where needed and encoded as WebP for faster loading; the interface and content were not retouched. Still images illustrate the UI and selected settings, not measured HDR quality or interpolation performance.

</details>
