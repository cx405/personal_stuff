Since I haven't figured yet how to make github actually track the pages that I need, I am going to use this method: both as exercise and for practical use. Its impossible to edit the gist so I am going to use this instead.

# bugs/issues with nixos
-- -- -- --
Relevant: YES (17.09), NO (17.09 with workaround), NO (18.03+, no workaround needed)  
Problem: KDE Phonon can't connect to phonon-gstreamer or phonon-vlc backends  
Actual reason: Incorrect search paths in gstreamer-phonon package  
Severity: HIGH (breaks multimedia subsystem of KDE desktop)  
Link: https://github.com/NixOS/nixpkgs/issues/27050  
Notes: This happens because the phonon backends have hard-coded search paths, which fail on nixos. This makes KDE useless for desktop user. Currently the problem is NOT patched in 17.09.  


Relevant: YES (17.09+)  
Problem: the standard tools on nixos very probably contain a bug, that can lead to corruption of user profile.  
Probable reason: bug in standard tools  
Severity: MEDIUM/unknown  
Link: https://github.com/NixOS/nixpkgs/issues/36989  
Notes: standard nix toolchain has corrupted symlinks within "/nix/var/nix/profiles/per-user/<my_user_name_here>/"  


Relevant: YES (18.04+)  
Problem: kdenlive package does not detect frei0r plugins, even if properly installed.  
Probable reason: unknown  
Severity: MINOR  
Link: https://github.com/NixOS/nixpkgs/issues/29614  
Notes: minor severity, because package is already implemented. Kdenlive just refuses to see it.  


Relevant: YES (18.04+), NO (with workaround)  
Problem: if "programs.gnupg.agent.enable = true" is set, then on every "sudo" there is a warning - "gpg-connect-agent: failed to create temporary file"  
Probable reason: unknown  
Severity: MINOR  
Link: https://github.com/NixOS/nixpkgs/issues/29331  
Notes: to workaround, do "sudo mkdir -p /root/.gnupg/"  


Relevant: YES (18.04+)  
Problem: there is currently no known way to list available video drivers in services.xserver.videoDrivers  
Probable reason: tool or method doesn't exist  
Severity: MEDIUM  
Link: https://github.com/NixOS/nixpkgs/issues/24801  
Notes: in some cases makes it hard to pick the correct video driver. In my case, it lead to video problems.  


Relevant: NO  
Problem: nixos can't directly run the opengl applications, which results in black screen or weird resolution followed by black screen (at least on my machine). Freeorion works flawlessly though.  
Reason: when using system with Radeon GPU, make sure that you have "ati" in the videoDrivers:  
'''
services.xserver.videoDrivers = [ "radeon" "ati" "vesa" ];
'''
Severity: HIGH (fixed)  
Link: https://github.com/NixOS/nixpkgs/issues/9415  
Link: https://github.com/NixOS/nixpkgs/issues/37673  
Notes: only added "radeon" assuming its kernel driver. However one needs "ati" as it pulls "x86-video-ati", which is DDE driver for all AMD cards for Xorg.  
