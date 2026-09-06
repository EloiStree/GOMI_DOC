# 📕 File Extension

In GOMI, you mainly interact with file formats.    

The UI in GOMI is there to help you understand or have fun with the code, but it should not be mandatory.    
The aim is to be able to `git` your configuration.    

But also to remotely help people with disabilities or people who don't like computers.   
You can give them a link to a big file on GitHub and change the configuration remotely when they need.   

**Try if you can:**    
> One file equals one topic to append to the app.    
  
All files are merged into one big file, split by `FILE>>>|file_name.file_extension`.   
They are grouped by `file_extension` and by `file_name`.   

The developer can then hook into that to import based on the `file_extension` format, and use `file_name` when needed.   
   
`.gate_out_udp`, for example, is used to specify who we send the text/byte/integer to.   
`.ab_input_to_command` allows us to listen for input and link it to a basic command.   
`.text_to_command` allows us to link a macro name to a command to interpret.   

If you want to add one to the app, you need to keep the **one file, one topic** idea to make it more readable and keep the documentation simple.   

You can find all the file format documentation I am using by default in the app in this folder.    
This does not cover community-added `.file_extension` formats.   
  
-------------------




