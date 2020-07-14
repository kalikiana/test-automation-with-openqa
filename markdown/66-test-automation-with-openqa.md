<!-- .slide: data-state="cover-image" id="test-automation-with-openqa" data-timing="20" -->
<div class="title">
    <h1>Test Automation with openQA</h1>
    <h2>Christian Dywan</h2>
</div>

<div class="date-location">July 12, 2020, BONN</div>

<div class="image">
    <div class="qr-embedded-wrapper">
        <div class="qrcode" id="qrcode-test-automation-with-openqa" />
    </div>
    <h2><a href="https://kalikiana.github.io/test-automation-with-openqa" target="_blank"
           id="test-automation-with-openqa">kalikiana.github.io/test-automation-with-openqa</a></h2>
</div>


<!-- .slide: data-state="normal toc" id="overview" data-timing="20s" -->
## Agenda

<div class="breadcrumbs">Overview</div>

1. Architecture overview
> The heavy lifting: virtual machines and bare metal

1. The Web UI
> Managing, scheduling and reviewing test jobs via the browser

1. RESTful API
> Scheduling jobs from the command line and via RESTful API

1. Use cases
> Who uses openQA?


<!-- .slide: data-state="divider-image" id="slido" data-timing="20" -->
# sli.do #protest89

<div class="image">
    <div class="qr-embedded-wrapper">
        <div class="qrcode" id="qrcode-slido-protest89" />
    </div>
    <h2><a href="https://app.sli.do/event/sslzhahz" target="_blank"
           id="slido-protest89"></a></h2>
</div>


<!-- .slide: data-state="normal" id="what-is-openqa" data-timing="20s" -->
## What is openQA

* Schedule tests on the system level
* Use mouse and keyboard input
* Serial console and SSH input
* Review through the web interface
* Zero changes to the application under test


<!-- .slide: data-state="divider-image" id="openqa-architecture" data-timing="20s" -->
# The architecture of openQA

<img alt="openQA architecture" src="images/openqa_architecture.png"/>


<!-- .slide: data-state="normal" id="backends" data-timing="20s" -->
## Backends

* QEMU
* svirt
* IPMI
* Serial console
* SSH


<!-- .slide: data-state="divider-image" id="last-builds-leap" data-timing="20s" -->
# Reviewing builds per product

<img alt="Overview of the last builds" src="images/last-builds-leap.png"/>


<!-- .slide: data-state="divider-image" id="test-result-overview" data-timing="20s" -->
# All green, good to go

<img alt="Test result: green" src="images/test-result-overview.png"/>


<!-- .slide: data-state="divider-image" id="test-result-failed" data-timing="20s" -->
# Oh noes, something failed

<img alt="Test result: failed" src="images/test-result-failed.png"/>


<!-- .slide: data-state="divider-image" id="test-result-failed-needle" data-timing="20s" -->
# Needle mismatch - theming changes?

<img alt="Needle error" src="images/test-result-failed-needle.png"/>


<!-- .slide: data-state="divider-image" id="needle-editor-json" data-timing="20s" -->
# Needle editor

<img alt="Needle editor" src="images/needle-editor-json.png"/>


<!-- .slide: data-state="divider-image" id="kde-softfailed-result" data-timing="20s" -->
# Softfailed?

<img alt="Test result: softfailed" src="images/kde-softfailed-result.png"/>


<!-- .slide: data-state="divider-image" id="kde-softfailed-no-reboot" data-timing="20s" -->
# Known bug with reboots of the live image

<img alt="Soft failure in KDE tests" src="images/kde-softfailed-no-reboot.png"/>


<!-- .slide: data-state="divider-image" id="job-group-properties" data-timing="20s" -->
# Job group properties

<img alt="Job group settings" src="images/job-group-properties-leap.png"/>


<!-- .slide: data-state="divider-image" id="job-templates-yaml" data-timing="20s" -->
# Job templates defined in YAML

<img alt="Job template editor" src="images/job-templates-yaml-leap.png"/>


<!-- .slide: data-state="normal" id="post-jobs-cli" data-menu-title="Post jobs"  -->
## Schedule jobs via the CLI

Get job details as JSON

```
openqa-cli api jobs/1222737
```

Post a job

```
openqa-cli api --host http://openqa.example.com \
-X POST jobs \
DISTRI=sle VERSION=15-SP2 \
FLAVOR=Online ARCH=x86_64 \
TEST=create_hdd_textmode \
MACHINE=64bit BUILD=189.1
```

Post an ISO

```
openqa-cli api -X POST isos \
DISTRI=sle VERSION=15 FLAVOR=Desktop-DVD-Updates \
ARCH=x86_64 TEST=qam-all \
FOO=1 BAR=baz
```


<!-- .slide: data-state="divider" id="openqa-use-cases" data-timing="20s" -->
# openQA is not just SUSE


<!-- .slide: data-state="divider-image" id="fedora" data-timing="20s" -->
# Fedora

<img alt="Fedora" src="images/fedora.png"/>


<!-- .slide: data-state="divider-image" id="qubes-os" data-timing="20s" -->
# QUBES OS

<img alt="QUBES OS" src="images/qubes-os.png"/>


<!-- .slide: data-state="divider-image" id="wsl" data-timing="20s" -->
# Linux on Windows

<img alt="WSL" src="images/wsl.png"/>


<!-- .slide: data-state="divider-image" id="openqa-in-openqa" data-timing="20s" -->
# openQA in openQA

<img alt="openQA in openQA" src="images/openqa-in-openqa.png"/>


<!-- .slide: data-state="thanks" id="thank-you" -->
# Thank you


<!-- .slide: data-state="subchapter" id="Q-and-A" -->
# Questions?
