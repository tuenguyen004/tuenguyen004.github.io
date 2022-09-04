<!-- 

Reminders for myself on how to prototype, preview, and publish

For full details on Hugo, refer to:
https://youngkin.github.io/post/createafreeblogsite/

Customizing light themes, refer to:
https://congx.dev/posts/custom-light-terminal-theme/

To build local webstie for prototyping, create two COMMAND PROMPT (cmd) WINDOWS: one at root 
directory of the website, and the other at root/themes/hugo-theme-terminal. 
Let's call the former terminal A and the latter terminal B

First, type command "sudo npm --version" (to make sure npm is accesible by cmd) and 
then "npm run dev" in terminal B [why not sure, maybe to rebuild website assets 
into html?]

Second, type command "hugo server" in terminal A and nagivate to http://localhost:1313/ to preview the website being edited

To stop both terminals, use Ctrl+C 

To rebuild and upload onto Github, delete the "/docs" folder and run "hugo" in terminal A to rebuild all html assets. Then run git add, git commit, and git push origin master 

OTHER NOTES/REMINDERS:
* To adjust website width, refer to theme\hugo-theme-terminal\assets\css\main.css and look for .container{padding}

-->
