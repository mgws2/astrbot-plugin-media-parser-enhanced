# AstrBot Media Parser — RC2

A modified distribution of [drdon1234/astrbot_plugin_media_parser](https://github.com/drdon1234/astrbot_plugin_media_parser),
based on public commit c16a938128014403057f1deeeaedecbd1fc15707.
Original author credits and AGPL-3.0 are retained. See NOTICE and CREDITS.md.

## Functionality and scope

The public snapshot routes supported media links, including Douyin and Bilibili,
through AstrBot message handling and the shared downloader. Other upstream
parsers remain in place. This release restores the two required parser/signing
modules and replaces only Bilibili AV-to-BV conversion with a MIT-derived
implementation. Valid integer conversions preserve the original interface;
negative and >=2**51 identifiers are rejected explicitly.

This package contains the public implementation. Production-only parser fixes,
preview templates, private long-video integrations, Worker/R2, NapCat and the
browser sidecar are excluded. No QQ-M1 changes are included.
There is no browser-sidecar call path or sidecar enable switch in this snapshot:
ordinary Douyin parsing uses the upstream public/web paths. Sidecar exclusion
therefore requires no network permission relaxation.

## Installation

Use a separate compatible AstrBot installation. Extract this archive, rename
its plugin folder to astrbot_plugin_media_parser, and place it under
AstrBot's data/plugins/. Install requirements.txt into the host's own
environment using trusted distribution sources, then use AstrBot's normal
plugin loading and configuration interface. Do not overwrite a running deployment.
FFmpeg is needed for upstream media processing paths that invoke it; provide it
separately where those paths are used. It is not bundled or runtime-tested here.

Configure through _conf_schema.json in AstrBot's plugin UI. Keep secrets in
private runtime configuration; never commit cookies or login/session files.
Authentication-assisted Bilibili features require user-owned authorization.
No credentials, runtime data or services are included.

## Validation and limitations

Dependency pins reuse the previously reviewed local Python 3.11.9 environment.
Upstream metadata declares AstrBot >=4,<5; this is inherited, not certification
of every host in that range. Offline tests use real Python dependencies and
explicit AstrBot host doubles. Actual host startup, QQ delivery and current
Douyin/Bilibili availability have not been verified for this candidate.
No platform requests, browser startup or production connections are used in
the candidate checks. Bilibili HTTP 412 may still occur; no permanent fix is claimed.
The inherited non-JSON error diagnostic includes up to 200 response characters;
review and redact diagnostic output before sharing it. Production diagnostic
patches are not included in this public-source candidate.
The ZIP is for review before publication; no deployment or GitHub publication
has occurred. Consult the accompanying release report for exact test results.

Use only with appropriate content access and redistribution authorization.
Platform terms and upstream APIs may change independently of this snapshot.
