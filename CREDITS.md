# Credits and licensing

Original project: [drdon1234/astrbot_plugin_media_parser](https://github.com/drdon1234/astrbot_plugin_media_parser),
public commit c16a938128014403057f1deeeaedecbd1fc15707.
The upstream author, registration and AGPL-3.0 root LICENSE are preserved.
This is a modified distribution, not a claim of original authorship.

The Bilibili module is restored from that public snapshot. Only av2bv is
replaced, with the MIT reference and adaptation details in NOTICE.
WBI retains the public AGPL implementation; algorithm documentation is not
redistributed. See the accompanying audit for the bounded code provenance decision.

Douyin signing is restored byte-for-byte from the same public snapshot,
including its Apache-2.0 file header and F2 credit. The explicit file-wide
license is retained. Earlier SM3 donor authorship could not be independently
established; no new ownership guarantee is made. NOTICE records the evidence.

Runtime libraries are not vendored: aiohttp (Apache-2.0 AND MIT),
cryptography (Apache-2.0 OR BSD-3-Clause), qrcode (BSD-3-Clause),
Pillow (MIT-CMU). AstrBot is supplied separately by the user.
Retain applicable license and attribution notices and satisfy AGPL corresponding
source obligations when distributing modified code or offering it over a network.

Private integrations, production overlays, preview templates, unknown assets
and the browser sidecar are excluded.
