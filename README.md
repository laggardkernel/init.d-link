# Init.d Link (Magisk)

### Intro

The module solves the situation when /system/etc/init.d doesn't exist, some app, let's say Kernel Auditor Beta, doesn't recognize the \*.d folder provided by MagiskSU and tries to create the init.d folder by itself. So we'd better symlink one from an available \*.d — post-fs-data.d, service.d or su.d.

- The module symlink a *.d folder as init.d,
- or simply create one systemlessly.
- Init.d scripts will be run by an existing superuser — MagiskSU, phh's superuser or SuperSU — or the kernel,
- but **NOT** by the module itself, in case of collision with the func of kernel.

### Symlink Priority:

1. /magisk/.core/service.d (Magisk v12)
2. /magisk/.core/post-fs-data.d (Magisk v11)
3. /magisk/phh/su.d
4. /su/su.d
5. /magisk/.core/post-fs-data.d (Magisk v12)
6. /magisk/.core/service.d (Magisk v11)

The last resort will be the creation of a systemless init.d folder.

**NOTE**: init.d will be symlinked only if available *.d foler exists.

### Support

- [\[Module\] \[Magisk\] init.d link | require Magisk 12.0+](https://forum.xda-developers.com/apps/magisk/magisk-init-d-link-t3579550) post at XDA

### Credit

- [Magisk - Root & Universal Systemless Interface \[Android 5.0+\]](https://forum.xda-developers.com/apps/magisk/official-magisk-v7-universal-systemless-t3473445) by [topjohnwu@XDA](https://forum.xda-developers.com/member.php?u=4470081)
- [init.d-link (Magisk)](https://github.com/laggardkernel/init.d-link) on GitHub by [laggardkernel](https://github.com/laggardkernel)
