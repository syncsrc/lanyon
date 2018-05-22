---
layout: post
title: Micro-Renovator, a microcode updater
tags: videos
---

With more microcode patches expected in response to another Spectre variant, the difficult process of acquiring and applying firmware updates is starting again. While microcode updates for these vulnerabilities can be delivered through either updates to UEFI firmware or Operating System packages, not all vendors have proven to be timely and thorough in distributing these updates.

Operating systems like Windows that do not permit users to manually apply microcode updates provided by CPU vendors are particularly impacted. Because these microcode patches need to be applied early in the boot flow for the kernel to detect and enable the new capabilities they provide, existing drivers aren't always sufficient to ensure the new protections are enabled. As a result, millions of users were without a way to apply security updates to their systems while waiting for either Microsoft or their motherboard vendor to issue an update containing the new microcode (a new UEFI firmware was released for one of my systems in **May**).

Fortunately, there's an alternative to waiting for vendors to release updates. Micro-Renovator replaces the bootloader on an EFI partition with an application that applies a microcode update before launching the OS bootloader. This gives end-users the ability to load a microcode patch directly from the the processor vendor in a manner that enables the operating system to detect and enable Spectre mitigations.

[MicroRenovator on Github](https://github.com/syncsrc/MicroRenovator)
