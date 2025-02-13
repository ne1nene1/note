# note
simple script to write note with template

## installation
make file executable
```shell
chmod +x ./note
```
add to your path
```shell
mv memo /path/to/your/bin
```
or add alias to your shell config
```shell
alias memo="/path/to/this/script"
```

by default `note` will use `~/notes` as a directory for where it will place the
note in. you can change this behavior by editing the script directly or defining
$NOTES_DIR environment variable in your shell
```shell
export NOTES_DIR="/path/to/keep/your/notes"
```
if the path specified doesn't exist, it will create one for you

you also can change note's file extension and default template to be used
inside the script directly too. 

## template
templating in this script is just the script call `echo` comomand to the note
repeatly line by line. 

to use a template, you need to create one first. I have already made a preset
template inside the script. you can create your own if you know some bash
scripting. after you create a template, you need to fill in your 
template name to the fzf choices (find the line with this pattern
`templates=$( echo "note source plan empty" | tr " " "\n")`, add your template
name inside `echo` command)

you can define default template that note will be using inside the script by
editing the line `default_template="TEMPLATE"` (replace template with the template
that the script known)

by defining the variable `default_template`, the script will automatically use that
template you defined and won't summon fzf to prompt you for a template
you can renable fzf template prompt by commenting the line that has `default_template="TEMPLATE"`

## usage
create note with timestamp as its file name
```bash
note
```
create note with TITLE as its file name
```bash
note "TITLE"
```
create note that use TEMPLATE as its template
```bash
note -t "TEMPLATE"
```
you can also gave its a name too
```bash
note -t "TEMPLATE" "TITLE"
```
## author
@ne1nene (Soulmine) [github](https://github.com/ne1nene1/)
