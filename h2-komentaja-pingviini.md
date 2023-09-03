# H2 Komentaja Pingviini

## x) Lue ja tiivistä
(note opettajalle; en kääntänyt suomeksi, sillä hakeminen englanniksi helpompaa.)
## Moving and Looking around

- $ pwd (Prints the working directory
- $ ls (List files in working directory
- $ cd ... (Change directory to "...")

## File Manipulation

- $ nano FOO.TXT (text editor)
- $ mkdir NEWFOLDER (Create a new directory ie. folder)
- $ mv OLDNAME NEWNAME (Move or rename directory or file If NEWNAME does not exist, oldname is renamed to newname.)
- $ mv SOMEFILE NEWDIR/ (If both parameters are files, NEWNAME is overwritten, if target is a directory, OLDNAME is moved there)
- $ cp -r ORIGINAL COPY (Copy ORIGINAL to COPY. "-r" means recursive, ORIGINAL is copied with contets if it is a directory.)
- $ rmdir EMPTYDIR (Remove an empty directory)
- $ rm JUNK (Remove file named junk)
- $ rm -r FOLDEROFJUNK (Remove FOLDEROFJUNK/ and its contents.)

## Help

- $ man ls (Show manual page of a command)
- $ ls --help (Manual page is shown in 'less') 
- $ wget -h (Many commands have a short builtin help)

## Administrative commands

Operations requiring high privileges are run with 'sudo'. These commands gain ulimited privileges.
- $ sudo apt-get update (Update list of available packages(Important: Run apt-get update before giving other apt comamnds.))
- $ apt-cache search dungeon adventure (Search for software with keywords, no sudo needed)
- $ sudo apt-get -y install nethack-console (Package name is the part before dash '-' It is needed when installing.)
- $ dpkg --listfiles nethack-console (Many programs are shown in the applications menu. For most command line applications, you have to find out the right command.)
- /usr/lib/games/nethack
- $ nethack (Usually the command is the file in one of the bin/ or game/ directiories.)
- $ sudo apt-get purge nethack (Removes the game and it's system wide settings to avoid addiction (referring to teacher.)) 
