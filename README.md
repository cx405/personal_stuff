Since I haven't figured yet how to make github actually track the pages that I need, I am going to use this method: both as exercise and for practical use. Its impossible to edit the gist so I am going to use this instead.

# bugs/issues with nixos
-- -- -- --
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

