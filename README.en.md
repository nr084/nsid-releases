# nSID for Windows 11 x64

[Русский](README.md) · [Downloads](https://github.com/nr084/nsid-releases/releases) · [License](LICENSE.en.md)

> [!WARNING]
> **Changing the machine SID and other system identifiers can cause data loss and leave Windows unable to boot.** You may lose access to accounts, profiles, encrypted files, and stored credentials. Applications and remote sign-in may stop working. Before running the operation, make a full backup, verify that you can restore it, and test on a separate clone first.
>
> **nSID is provided AS IS, without warranties** to the extent permitted by applicable law. The copyright holder is not liable for damage arising from use of the software to the extent permitted by law. Mandatory user rights remain in effect. See the [license](LICENSE.en.md) for details.

nSID is a free, closed-source Windows utility for working with computer identifiers. The graphical version displays the current machine SID and subsystem settings. The command-line version reads the SID and writes diagnostic reports.

**Version 1.0 status.** Final Windows 11 x64 tests of the published archive are pending. For now, use this build only on test clones.

The Windows 10 22H2 x86 and Windows 11 ARM64 builds have not been tested for startup or migration. Use them only on test clones.

nSID is being developed for migrating Windows clones in workgroups. See the release page for the operations verified for each version and any limitations.

Before migration, fully decrypt the system volume and affected data volumes. Suspending BitLocker is insufficient.

Keep a full image off the computer and verify that it restores on a clone. If Windows fails to boot after migration, use WinRE or your backup provider's bootable media to restore the image created before running nSID. The archive includes recovery instructions. [Windows Recovery Environment](https://support.microsoft.com/en-us/windows/experience/backup-recovery/windows-recovery-environment)

### Saved Windows credentials

If you rely on Credential Manager entries, follow these steps separately as the owner of each affected profile. Verify restoration on a separate clone first.

1. Before changing the SID, search Windows for Credential Manager. Select Windows Credentials → Back up Credentials. Save the `.crd` file in a protected location and set an archive password in the Windows wizard.
2. After restarting, sign in to the same profile. If you need to recover missing entries, choose Restore Credentials, select that profile's archive, and enter its password. The wizard may replace credentials added or changed after the backup.
3. Verify access in the application or network resource that uses the saved credential.

The wizard may ask you to press Ctrl+Alt+Delete to switch to the Windows secure desktop. The archive covers Windows entries supported by the wizard. Website sign-ins are handled by your browser.

Keep a copy off the computer being migrated. If a profile belongs to a disabled account, coordinate protected-data checks with its owner before migration. Verification for that profile remains pending until the owner can sign in.

Windows manages protected file and protocol associations. If Windows asks you to choose an app after migration or opens a file in a different app, set your preferred app under Settings → Apps → Default apps.

Migration involves signing users out and restarting Windows. Save work in all sessions before starting. If you use RDP, choose Sign out in Windows to end the session. Closing the RDP window leaves it open. After the restart, review the result report before returning the computer to service. You may need to sign in to websites again.

The interface is available in Russian and English. In Settings, choose the light theme, the dark theme, or the Windows default. The archive includes command-line instructions and license terms in both languages.

© nr084
