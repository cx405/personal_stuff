Since I haven't figured yet how to make github actually track the pages that I need, I am going to use this method: both as exercise and for practical use. Its impossible to edit the gist so I am going to use this instead.

# bugs/isses with nixos
-- -- -- --
Open: YES  
Problem: KDE Phonon can't connect to phonon-gstreamer backend  
Probable reason: Incorrect search paths in gstreamer-phonon package  
Severity: HIGH  
Link: https://github.com/NixOS/nixpkgs/issues/27050  
Notes: I still have no idea how to fix this. This makes KDE desktop useless, for desktop user.  


Open: YES  
Problem: the standard tools on nixos very probably contain a bug, that can lead to corruption of user profile.  
Probable reason: bug in standard tools  
Severity: MEDIUM/unknown  
Link: https://github.com/NixOS/nixpkgs/issues/36989  
Notes:  standard nix toolchain has corrupted symlinks within "/nix/var/nix/profiles/per-user/<my_user_name_here>/" 
