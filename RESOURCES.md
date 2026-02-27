


# 1. Proxmox anti-detection (5min)
git clone https://github.com/zhaodice/proxmox-ve-anti-detection
cd proxmox-ve-anti-detection
wget patches/001-anti-detection.patch  # Apply to pve-qemu

# 2. Kernel RDTSC patch (copy from gist above)
cd /usr/src/linux && patch -p1 < rdtsc-spoof.patch

# 3. Test with Pafish
wget https://github.com/a0rtega/pafish/releases/latest/download/pafish.exe
wine pafish.exe  # Should show 45/47 passes
Real hacker validation: These repos bypass EAC/Vanguard/nProtect—exact Ghost Mode. zhaodice's Proxmox patch = your Type-1 hypervisor base.

Your hw fingerprint still needed for SMBIOS/disk spoofing. Drop dmidecode -t system && lsblk -o SERIAL,MODEL → instant custom config.
