### animated lolcat combined with figlet

<p align="center">
   <img src="https://github.com/vzvz4/jfiglol/blob/master/img/g.gif"/>
</p>

## Usage
- use file named "jfiglol", copy "jfiglol" to /usr/bin/ directory if you want  

```bash
$ ./jfiglol "Your input here"
# don't forget double quotes if your text contains spaces

$ ./jfiglol "Some text" -a 
# if you want to animate your input
```
### Command pattern:

jfiglol \[mode\] \[printer\] \[options\]

You can download figlet fonts here http://www.figlet.org/examples.html aslo there is few in "fonts" folder.
```
with specific font
$ ./jfiglol --font "/path/to/font.flf" "Your text Here" -r

print file
$ ./jfiglol --file "path/to/file" -r

just your input
$ ./jfiglol --plain "Your input here" -r
```
 - Examples:

 animated output with 3d.flf font and rainbow colors print mode
 ```
$ ./jfiglol --font "/path/to/font.flf" "You text Here" --rainbow --animated
```
<img src="https://github.com/vzvz4/jfiglol/blob/master/img/rainbow.gif"/>

animated output with 3d.flf font and gradient colors print mode
 ```
$ ./jfiglol --font "/path/to/font.flf" "You text Here" --gradient --animated  
```
<img src="https://github.com/vzvz4/jfiglol/blob/master/img/gradient.gif"/>

animated output with 3d.flf font and mono colors print mode
 ```
$ ./jfiglol --font "/path/to/font.flf" "You text Here" --mono --animated 
```
<img src="https://github.com/vzvz4/jfiglol/blob/master/img/mono.gif"/>

 - Also you can use --verbose (-v), --random (-r) and --debug (-d) options
```
$ ./jfiglol --font "./fonts/3d.flf" "You text Here" --mono -d -v -r
```
<img src="https://github.com/vzvz4/jfiglol/blob/master/img/help.png"/>

<h1> GraalVM native-image </h1>

- Produce a native image of the application:

1. from project root run commands below to compile all java classes  

```bash
$ javac com/owpk/*.java
# or "javac -d "specific/out/folder" com/owpk/*.java"
# if you want to compile file to specific folder
```

2. produce native image, you should use "reflect-config.json" file which is in project root

```bash
$ native-image --no-server --no-fallback --static \
-H:ReflectionConfigurationFiles="reflect-config.json" com.owpk.Jfiglol
```
3. you should see "com.owpk.jfiglol" binary file in current directory, rename it how you want and copy to
   /usr/local/bin directory if you like.
