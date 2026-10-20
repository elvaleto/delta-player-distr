<div align="center">

# Delta Player

**Frame generation. RTX video enhancement. Moments worth saving.**

Windows video player for high-refresh displays, HDR films and a more visual way to navigate your videos.

[![Download Windows alpha](https://img.shields.io/badge/Download-Windows%20alpha-8bd5ca?style=for-the-badge)](https://github.com/elvaleto/delta-player-distr/releases/latest) [![All releases](https://img.shields.io/badge/All-releases-30363d?style=for-the-badge)](https://github.com/elvaleto/delta-player-distr/releases)

![Windows 11 x64](https://img.shields.io/badge/Windows%2011-x64-3878c7?style=flat-square) ![NVIDIA RTX](https://img.shields.io/badge/NVIDIA-RTX-76b900?style=flat-square&logo=nvidia&logoColor=white) ![RIFE](https://img.shields.io/badge/Interpolation-RIFE%20%2F%20Micro%20Riffe-a78bfa?style=flat-square) ![Renderers](https://img.shields.io/badge/Direct3D%2012-Vulkan-64748b?style=flat-square)

</div>

| Motion that fits your display | More from your picture |
| :--- | :--- |
| **NVIDIA Video Frame Generation, RIFE and Micro Riffe**, with scene-cut detection to avoid blending across cuts. VRR-aware frame pacing. | **RTX Video Super Resolution + TrueHDR**, HDR10 / HLG, Dolby Vision metadata through HDR10 output, and dynamic tone mapping. |

<table>
<tr>
<td colspan="2" valign="top">
<strong>Playback HUD</strong><br>
See the HDR-to-display color path and tone-mapping mode. Scrub the timeline with visual previews.<br><br>
<a href="assets/hud.webp"><img src="assets/hud.webp" alt="Playback HUD: Dolby Vision color path, tone mapping, audio layout and timeline previews with chapters and marks" width="100%"></a>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<strong>Frame generation controls</strong><br>
Choose a backend, target your display refresh or a frame-rate multiplier, and tune generation resolution.<br><br>
<a href="assets/settings.webp"><img src="assets/settings.webp" alt="Interpolation settings: RIFE on NVIDIA TensorRT CiG, frame-rate targets, multiplier and generation resolution" width="100%"></a>
</td>
<td width="50%" valign="top">
<strong>Pipeline diagnostics</strong><br>
Inspect live GPU shader fusion, Dolby Vision tone mapping, ICC 3D LUT transforms, optical flow scene cuts and frame generation.<br><br>
<a href="assets/osd.webp"><img src="assets/osd.webp" alt="Render pipeline diagnostics: GPU shader fusion, Dolby Vision RPU tonemapping, ICC 3D LUT, optical flow scene detection and NVIDIA VFG" width="100%"></a>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<strong>Track routing & dual audio</strong><br>
Select primary and secondary audio tracks independently. Route sound to two devices with dedicated clocks, resamplers and formats.<br><br>
<a href="assets/tracks.webp"><img src="assets/tracks.webp" alt="Audio track selection: primary and secondary track routing, dual audio outputs, stream formats and bitrates" width="100%"></a>
</td>
<td width="50%" valign="top">
<strong>Media information</strong><br>
Search stream parameters, container tags, Dolby Vision RPU metadata, mastering luminance and hardware zero-copy D3D12VA decoding.<br><br>
<a href="assets/media-info.webp"><img src="assets/media-info.webp" alt="Media information panel: searchable stream details, Dolby Vision Profile 7 metadata, mastering display colorimetry and D3D12VA decoder" width="100%"></a>
</td>
</tr>
<tr>
<td width="50%" valign="top">
<strong>Marks</strong><br>
Save scenes with comments. Search thumbnail cards grouped by video and jump straight back.<br><br>
<a href="assets/marks.webp"><img src="assets/marks.webp" alt="Marks: scene thumbnails grouped by video, with comments, timestamps and search" width="100%"></a>
</td>
<td width="50%" valign="top">
<strong>Watch history</strong><br>
Resume from thumbnails. See saved positions, progress and dates.<br><br>
<a href="assets/history.webp"><img src="assets/history.webp" alt="Watch history: video thumbnails, saved positions, progress bars and session dates" width="100%"></a>
</td>
</tr>
</table>

**Around the film:** automatic black-bar cropping for ultrawide screens · Ambilight · two independent audio outputs · Steam Audio for headphones · GPU-drawn HUD and native searchable panels.

**Try it:** extract the **whole ZIP**, run `delta-player.exe` or the separate `delta-player-vulkan.exe`, and drop in a video. **F2** → settings; **F1** → controls. Portable data stays beside the app when `portable.ini` is present.

<details>
<summary>Compatibility</summary>

Windows 11 x64. Direct3D 12 requires Feature Level 12_1 / Shader Model 6.6; Vulkan is a separate executable. Features depend on the GPU, driver and display. Native NVIDIA VFG targets RTX 40 / 50; other interpolation methods have their own requirements. VRR depends on display and driver configuration. Dolby Vision Profile 7 FEL residual is not applied. This is an alpha distribution; AMD and older GPU coverage remains limited.

</details>
