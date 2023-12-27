# lpm
Lua Package Manager (for ComputerCraft/OpenComputers)

## install
to install you can either use the pastebin method (might not work) or the file method.<br>

To use the pastebin method download pastbin code : \<AWAITING\><br>
To use the file method<br>

<ol>
  <li>create a file named anything you want</li>
  <li>edit the file</li>
</ol>

3. add
```lua
local lpm = http.get("https://raw.githubusercontent.com/AlphaTechNinja/lpm/main/lpm.lua")
local dest = fs.open("lpm.lua","w")
dest.write(lpm.readAll())
lpm.close()
dest.close()
```
  <br>
4. then run the file and your done (make sure to run lpm afterwards to setup)<br>

## use
to use lpm make sure it's installed and setup<br>

after that you can run "lpm install" to install the lpm API (requiring lpm itself with provide a very basic API)<br>

## how to make a lpm package
first run "lpm install lpm-packer"<br>

then create a new directory named after your package and inside place two files named metadata.etd (btw etd stands for Encoded Table Data) and source.lua.<br>

If you need multiple files create a new directory in the package's directory named "src" and move your "source.lua" file into it then add your files (also supports nested directorys).<br>

To package your package run "lpm run lpm-packer \<PATH TO PACKAGE\> [optional: --silent]" (your package will be the orginal name but with a ".pkg" extension)<br>

now after you have packaged it you can either export it (CraftOS-PC or other emulators only) by going into your app data and finding the emulators files and pulling it from there or uploading to pastebin and retriving it later<br>

<b>HEY!</b><br>

before you go off packaging it without the "metadata.etd" modified to work listen up.<br>

i have made a example in the root directory called "example-package" with a correctly modified version of the file please examine it and read my comments<br>

then modify the file so that looks like the example one but with the settings you want (MAKE SURE TO CHANGE THE ONES I MARKED WITH "*" NEXT TO IT)<br>

## how to upload packages
To upload a package (make sure you have it packaged) create a fork of this repo and go into "packages" and upload your file there then create a pull request and i will review it, and if i like it i will add it <br>

## package upload rules
Obviously your package must not contain malware or spyware of any sort (it's ok to fetch info if the user agrees).<br>

Your package must serve a use (it can not be a useless library)
You have the choice to apply a lisense to it or not.<br>

You agree that I am allowed to modify your package (i won't make big changes i might fix a bug or two (: )
Your code needs to be somewhat neat (please).<br>

## using external sources
I will make a package for lpm for accessing external packages (like from other repos) but currently there is NO support for external packages.<br>

For an alternitive you could change the github repo it fetchs from in the "lpm.lua" file (IF YOU HAVE NO EXPIERENCE USING LUA DO NOT TOUCH THIS FILE instead wait for the package to come out).<br>

## commands
here are all current and will be added commands:<br>

<ul>
  <li>
 lpm install [--silent] [--replace] [--debug ?]:: installs a package from the lpm repo
  </li>
  <li>
    lpm run [--sandbox]:: runs a installed package
  </li>
  <li>
    lpm remove :: removes an installed package
  </li>
  <li>
    ? lpm extern {link} {name} :: same as "lpm install" but from a external source
  </li>
</ul>

## notes
Sorry for OpenComputers users as there is no way to export packages on a public server unless your hosting it.<br>

Sadly i don't know how to perform github actions from the OpenComputer/OpenComputers system, sorry for my lack of the github API knowledge<br>
