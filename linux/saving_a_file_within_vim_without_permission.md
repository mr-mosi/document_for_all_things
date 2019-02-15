## How to save a file within vim without permission

### The solution
Here is the way through which root privileges can be acquired and the file can be saved from within the vim editor window. 
Instead of saving the file through `:w` use `:w ! sudo tee %`