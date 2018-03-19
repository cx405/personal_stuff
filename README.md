Since I haven't figured yet how to make github actually track the pages that I need, I am going to use this method: both as exercise and for practical use. Its impossible to edit the gist so I am going to use this instead.

# bugs/issues with nixos
-- -- -- --
Relevant: YES  
Problem: nixos can't directly run the opengl applications, which results in black screen or weird resolution followed by black screen (at least on my machine). Freeorion works flawlessly though.  
Probable reason: GL library binding  
Severity: HIGH  
Link: https://github.com/NixOS/nixpkgs/issues/9415  
Notes: basically, a blocker to all opengl games. Breaks nixos as desktop system.  


Relevant: YES(17.09), NO (17.09 with workaround), NO (18.03+, no workaround needed)  
Problem: KDE Phonon can't connect to phonon-gstreamer or phonon-vlc backends  
Actual reason: Incorrect search paths in gstreamer-phonon package  
Severity: HIGH(breaks multimedia subsystem of KDE desktop)  
Link: https://github.com/NixOS/nixpkgs/issues/27050  
Notes: This happens because the phonon backends have hard-coded search paths, which fail on nixos. This makes KDE useless for desktop user. Currently the problem is NOT patched in 17.09.  


Relevant: YES  
Problem: the standard tools on nixos very probably contain a bug, that can lead to corruption of user profile.  
Probable reason: bug in standard tools  
Severity: MEDIUM/unknown  
Link: https://github.com/NixOS/nixpkgs/issues/36989  
Notes:  standard nix toolchain has corrupted symlinks within "/nix/var/nix/profiles/per-user/<my_user_name_here>/" 
