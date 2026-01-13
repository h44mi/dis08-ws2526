Last login: Tue Jan 13 10:24:57 on ttys000
(base) h44mi@nat079012 ~ % cd /Users/h44mi/Downloads/bashcrawl-stable-2024.02.09/entrance
(base) h44mi@nat079012 entrance % cat scroll

It is pitch black in these catacombs.
You have a magickal spell that lists all items in a room.

To see in the dark, type:     ls
To move around, type:         cd <directory>

Try looking around this room.
Then move into one of the next rooms.

EXAMPLE:

$ ls 
$ cd cellar

Remember to cast ``ls`` when you get into the next room!

(base) h44mi@nat079012 entrance % ls
cellar	scroll
(base) h44mi@nat079012 entrance % cd cellar
(base) h44mi@nat079012 cellar % ls
armoury		scroll		treasure
(base) h44mi@nat079012 cellar % cat scroll

 Illusions are strong here.
 It is difficult to tell what is a doorway and what is an object.

 The magic spell you use to look can be augmented.

 From now on, cast your spell like this:
 
 ls -F
 
 Directories (the rooms of these catacombs) end with a / symbol.
 
 Encounters (programs) end with a * symbol.

 You can avoid having to type `ls -F` every time by running the
 following:

 alias ls='ls -F'

 This is known as a shell or command alias.  With this alias,
 typing simply ls by itself will run ls -F. Try it out!

(base) h44mi@nat079012 cellar % alias ls='ls -F'
(base) h44mi@nat079012 cellar % ls
armoury/	scroll		treasure*
(base) h44mi@nat079012 cellar % cd armoury 
(base) h44mi@nat079012 armoury % ls
chamber/	potion*		scroll		treasure*
(base) h44mi@nat079012 armoury % cat sctroll
cat: sctroll: No such file or directory
(base) h44mi@nat079012 armoury % cat scroll

#You can interact with items in the room (they end with a *)
#by running them as a command (a shell script).
#For example, to collect treasure:
#./treasure 
#The . (dot) means *don't move*, and the name of the 
#script makes the code run.  This is known as a 
#relative path, and the . means the current room
#(directory). 
#You may have left treasure in the previous room.
#Go back to a previous directory with two dots,
#which means *take a step back*.
#EXAMPLE:
cd ..

(base) h44mi@nat079012 armoury % cd .. 
(base) h44mi@nat079012 cellar % cd treasure 
cd: not a directory: treasure
(base) h44mi@nat079012 cellar % ./treasure
You have found an emerald **amulet**!"

To collect treasure, you must have a variable to hold your inventory.

Create a variable and add your treasure to it like this:

export I=amulet,$I

You can always check your wealth with this command:

echo $I

(base) h44mi@nat079012 cellar % export I=amulet,$I

(base) h44mi@nat079012 cellar % echo $I
amulet,
(base) h44mi@nat079012 cellar % ls
armoury/	scroll		treasure*
(base) h44mi@nat079012 cellar % cd armoury 
(base) h44mi@nat079012 armoury % ls
chamber/	potion*		scroll		treasure*
(base) h44mi@nat079012 armoury % cat scroll 

#You can interact with items in the room (they end with a *)
#by running them as a command (a shell script).
#For example, to collect treasure:
#./treasure
#The . (dot) means *don't move*, and the name of the 
#script makes the code run.  This is known as a 
#relative path, and the . means the current room
#(directory). 
#You may have left treasure in the previous room.
#Go back to a previous directory with two dots,
#which means *take a step back*.
#EXAMPLE:
#cd ..

(base) h44mi@nat079012 armoury % ./potion 
You have found a potion bottle of swirling
green liquid. Do you want to drink it?  y/n

y
The taste of a rustic green plant fills your mouth.  It
warms and strengthens you.

Create a variable for your health points (HP).  You have
15HP:

export HP=15

You can check your health at any time:

echo $HP

(base) h44mi@nat079012 armoury % export HP=15

(base) h44mi@nat079012 armoury % echo $HP 
15
(base) h44mi@nat079012 armoury % ls
chamber/	potion*		scroll		treasure*
(base) h44mi@nat079012 armoury % ./treasure
You have found a gleaming silver **sword**!  You marvel at
its craftsmanship, and you recall tales from your childhood
of the great mystic king Rannismir who bore such a sword to
protect the kingdom from the undead.

Add this item to your inventory:

export I=sword,$I

Remember, you can check your inventory:

echo $I

(base) h44mi@nat079012 armoury % export I=sword,$I

(base) h44mi@nat079012 armoury % echo $I

sword,amulet,
(base) h44mi@nat079012 armoury % ls
chamber/	potion*		scroll		treasure*
(base) h44mi@nat079012 armoury % cd chamber 
(base) h44mi@nat079012 chamber % ls
scroll		spell*		statue*		treasure*
(base) h44mi@nat079012 chamber % cat scroll 

#You seem to have reached the end of this hall. 
#Turn back and try another path.
#Remember, to back track one directory, you type:
#cd ..
#If you are drawing a map of your progress,
#you can always get the name of your working
#directory with this command:
#pwd

(base) h44mi@nat079012 chamber % cd ..
(base) h44mi@nat079012 armoury % ls
chamber/	potion*		scroll		treasure*
(base) h44mi@nat079012 armoury % cd chamber
(base) h44mi@nat079012 chamber % ls
scroll		spell*		statue*		treasure*
(base) h44mi@nat079012 chamber % ./spell 
Runes, the language of the ancient mystics that once ruled
this land, are inscribed upon the western wall.

Do you want to read them? y/n  y
You recall the lessons of Caitlyn the Green, who taught you
these ancient letters.  

The runes are instructions on how to summon a portal that
will allow you to walk through an invisible door contained
in the wall.

In Bash, a symbolic link (symlink) is a *shortcut* to
another file or directory.  Create one from this room to the
adjacent one:

ln -fs ../../../chapel/courtyard/aviary/hall portal

(base) h44mi@nat079012 chamber % ln -fs ../../../chapel/courtyard/aviary/hall portal

(base) h44mi@nat079012 chamber % ls
portal@		scroll		spell*		statue*		treasure*
(base) h44mi@nat079012 chamber % cd portal
(base) h44mi@nat079012 portal % ls
library/	monster*
(base) h44mi@nat079012 portal % ./monster
A hulking three-legged beast, with a mouth full of fangs and
a barbed tail and 8 arms, lumbers toward you.

If you have a sword, you can attack.  Otherwise, you should
run.  

Do you want to attack? y/n  y
Enter a number:  8
The monster rolled  27
You rolled  13

Your attack is deflected off the monster's leathery flesh.
You take 5 points damage. Deduct this from your HP.

let HP=HP-5

Enter a number:  let HP=HP-5
The monster rolled  66
You rolled  76
A hit! A palpable hit!  You have slain the beast.

(base) h44mi@nat079012 portal % ls
carcass*	library/	treasure*
(base) h44mi@nat079012 portal % ./carcass
You find the carcass of a foul beast.  Nothing of interest
lies within its remains.

(base) h44mi@nat079012 portal % ./treasure
You have found a **crown**!  Add it to your inventory.

(base) h44mi@nat079012 portal % export I=crown,$I

(base) h44mi@nat079012 portal % echo $I

crown,sword,amulet,
(base) h44mi@nat079012 portal % ls
carcass*	library/	treasure*
(base) h44mi@nat079012 portal % cd library
(base) h44mi@nat079012 library % ls
scroll	tome*
(base) h44mi@nat079012 library % cat scroll 
#You are in a small library.  There are
#shelves on all sides of the room, 
#containing many books and knicknacks.  
#Before you, there is a small table 
#with a very large book open on it.

(base) h44mi@nat079012 library % ./tome

You see a large tome on the table, open
to a page in the middle of the book.

Do you read it? y/n  y

The tome appears to be a book of spells.  Here is the 
first spell:


Map the entire dungeon!

You can see the layout of the entire dungeon using the
"tree" command.  You may need to install it as a separate
package, consult your operating system package manager for
details on how to do this.  If you're reading this from the
library, your relative current directory path should be:

entrance/chapel/courtyard/aviary/hall/library

If you run the following command, from the library:

tree -F ..

You should see this:

..
├── library/
│   ├── scroll
│   └── tome*
└── carcass*

The "tree" command takes many of the same options as the
"ls" command, including colors and viewing hidden files.  Go
back to the entrance and try it out!

Do you want to read another spell? y/n  y

View the world in color!

If you have a modern, color terminal, you can view the
output of the ls command in color!  This will still be a
valid command if you don't have a color terminal, you just
won't see colors.  Try this:

alias ls='ls -F --color=auto'

Now when you run the "ls" command by itself, rooms
(directories), scrolls (text files), and encounters
(executable files) should each have different colors.
Depending on the $LS_COLORS variable, many other files will
have different colors too!  

You can read more about colors by consulting the 
"dircolors" manual.  To read more, type this spell:

man dircolors

In the manual, you can type 'q' (without quotes) to
exit the manual page.

Do you want to read another spell? y/n  n
(base) h44mi@nat079012 library % ls
scroll	tome*
(base) h44mi@nat079012 library % cd ../../../..

(base) h44mi@nat079012 cellar % cd ..
(base) h44mi@nat079012 entrance % pwd
/Users/h44mi/Downloads/bashcrawl-stable-2024.02.09/entrance
(base) h44mi@nat079012 entrance % tree -F
zsh: command not found: tree
(base) h44mi@nat079012 entrance % brew install tree
zsh: command not found: brew
(base) h44mi@nat079012 entrance % ls
cellar/	chapel/	scrap	scroll	vault/
(base) h44mi@nat079012 entrance % cat scroll 

It is pitch black in these catacombs.
You have a magickal spell that lists all items in a room.

To see in the dark, type:     ls
To move around, type:         cd <directory>

Try looking around this room.
Then move into one of the next rooms.

EXAMPLE:

$ ls 
$ cd cellar

Remember to cast ``ls`` when you get into the next room!

(base) h44mi@nat079012 entrance % cd cellar
(base) h44mi@nat079012 cellar % ls
armoury/	scroll		treasure*
(base) h44mi@nat079012 cellar % cd armoury
(base) h44mi@nat079012 armoury % ls
chamber/	potion*		scroll		treasure*
(base) h44mi@nat079012 armoury % cd chamber
(base) h44mi@nat079012 chamber % ls
portal@		scroll		spell*		statue*		treasure*
(base) h44mi@nat079012 chamber % cat scroll 

#You seem to have reached the end of this hall. 
#Turn back and try another path.
#Remember, to back track one directory, you type:
#cd ..
#If you are drawing a map of your progress,
#you can always get the name of your working
#directory with this command: 
#pwd

(base) h44mi@nat079012 chamber % cd portal
(base) h44mi@nat079012 portal % ls
carcass*	library/	treasure*
(base) h44mi@nat079012 portal % cd library
(base) h44mi@nat079012 library % ls
scroll	tome*
(base) h44mi@nat079012 library % cd ..
(base) h44mi@nat079012 portal % cd .. 
(base) h44mi@nat079012 chamber % ./spell 
The invoked portal is still there, wide open as it has been
since its first appearance.

You can go through it just like any other door :

cd portal

(base) h44mi@nat079012 chamber % ./ statue
zsh: permission denied: ./
(base) h44mi@nat079012 chamber % ./statue
A rugged statue stands in the corner of the room.

Do you approach it? y/n  y
The statue springs to life, rumbling:

WHO DARES INTRUDE UPON THE CHAMBER OF SPIRITS?

It thrusts a fist at you, hitting you for 5 damage.

Do you have a sword? y/n  y
You strike the statue and it breaks to pieces!

However, you have taken damage.
Deduct 5 from your HP variable:

let "HP=HP-5"

(base) h44mi@nat079012 chamber % let "HP=HP-5"

(base) h44mi@nat079012 chamber % ls
pieces*		portal@		scroll		spell*		treasure*
(base) h44mi@nat079012 chamber % ./pieces
You sift through the pieces of a shattered statue.

You find nothing of interest in the statue's remains.

(base) h44mi@nat079012 chamber % ./treasure

You have found a stash of **diamonds**!  They are old and worn
with age,  but they still gleam in the magickal light
emanating from your eyes.

Prefix this item to your inventory:

export I=diamonds,$I

Remember, you can check your inventory:

echo $I

(base) h44mi@nat079012 chamber % export I=diamonds,$I

(base) h44mi@nat079012 chamber % echo $I

diamonds,crown,sword,amulet,
(base) h44mi@nat079012 chamber % ls
pieces*		portal@		scroll		spell*		treasure*
(base) h44mi@nat079012 chamber % cd portal
(base) h44mi@nat079012 portal % ls
carcass*	library/	treasure*
(base) h44mi@nat079012 portal % ./treasure
This treasure has already been taken.
(base) h44mi@nat079012 portal % cd library
(base) h44mi@nat079012 library % ls
scroll	tome*
(base) h44mi@nat079012 library % ./tome

You see a large tome on the table, open
to a page in the middle of the book.

Do you read it? y/n  y

The tome appears to be a book of spells.  Here is the 
first spell:


Keep track of where you've been!

Instead of using "cd <room>" and "cd .." to 
navigate the catacombs, you can keep track of the
rooms you've been in by using "pushd" and "popd". 
"pushd", as the name implies, pushes the directory you
pass as the argument onto the room (directory) stack.
Use it like so:

pushd <room>

The angle brackets mean you specify the room (directory),
you don't type the angle brackets.  To see your current
stack, type the following command:

dirs

This will print out the list of directories on the stack. 
The data structure is a known as a stack, because you only
add or remove elements from the top of the stack, it is also
known as a LIFO (Last In, First Out) data structure.  To
remove the top room (directory) from the stack, and change
directory to the new directory on the top of the stack, use 
"popd", like so:

popd

This will remove the top element of the stack ("pop" it off the
stack), and change directory to the next top of the stack.

Here's an example.  You're in a room (directory) called 
~/bashcrawl/entrance/field/, with the following
other rooms:

cemetary/ jail/ oubliette/

To change directory to the cemetary, and place it on the directory
stack, use this:

pushd cemetary

Now, the directory stack (output of the "dirs" command),
shows this:

~/bashcrawl/entrance/field/cemetary ~/bashcrawl/entrance/field

...and your current directory (present working directory,
held in the $PWD variable) is the cemetary.  To go back to
the field, run "popd".  The directory stack will return to
~/bashcrawl/entrance/field, and your current directory will
be that directory.  You can mix and match "pushd" with "cd",
and only the directories you add with "pushd" will be on the
stack.  This is useful for returning to another directory,
after exploring the rest of the dungeon.

Good luck!

Do you want to read another spell? y/n  n
(base) h44mi@nat079012 library % ls
scroll	tome*
(base) h44mi@nat079012 library % ./tome

You see a large tome on the table, open
to a page in the middle of the book.

Do you read it? y/n  n
(base) h44mi@nat079012 library % cd ..
(base) h44mi@nat079012 portal % ö
zsh: command not found: ö
(base) h44mi@nat079012 portal % pwd
/Users/h44mi/Downloads/bashcrawl-stable-2024.02.09/entrance/cellar/armoury/chamber/portal
(base) h44mi@nat079012 portal % ls
carcass*	library/	treasure*
(base) h44mi@nat079012 portal % ./carcass
You find the carcass of a foul beast.  Nothing of interest
lies within its remains.

(base) h44mi@nat079012 portal % cd ..
(base) h44mi@nat079012 chamber % ls
pieces*		portal@		scroll		spell*		treasure*
(base) h44mi@nat079012 chamber % cat scroll 

#You seem to have reached the end of this hall. 
#Turn back and try another path.
#Remember, to back track one directory, you type:
#cd ..
#If you are drawing a map of your progress,
#you can always get the name of your working
#directory with this command:
#pwd

(base) h44mi@nat079012 chamber % cd ..
(base) h44mi@nat079012 armoury % ls
chamber/	potion*		scroll		treasure*
(base) h44mi@nat079012 armoury % cat scroll 

#You can interact with items in the room (they end with a *)
#by running them as a command (a shell script).
#For example, to collect treasure:
#./treasure
#The . (dot) means *don't move*, and the name of the 
#script makes the code run.  This is known as a 
#relative path, and the . means the current room
#(directory). 
#You may have left treasure in the previous room.
#Go back to a previous directory with two dots,
#which means *take a step back*.
#EXAMPLE:
#cd ..

(base) h44mi@nat079012 armoury % ./tresure
zsh: no such file or directory: ./tresure
(base) h44mi@nat079012 armoury % ./treasure
This treasure has already been taken.
(base) h44mi@nat079012 armoury % ./potion 
You have found a potion bottle of swirling
green liquid. Do you want to drink it?  y/n

y
The taste of a rustic green plant fills your mouth.  It
warms and strengthens you.

Create a variable for your health points (HP).  You have
15HP:

export HP=15

You can check your health at any time:

echo $HP

(base) h44mi@nat079012 armoury % export HP=15

(base) h44mi@nat079012 armoury % echo $HP

15
(base) h44mi@nat079012 armoury % cd ../..
(base) h44mi@nat079012 entrance % pwd
/Users/h44mi/Downloads/bashcrawl-stable-2024.02.09/entrance
(base) h44mi@nat079012 entrance % ls
cellar/	chapel/	scrap	scroll	vault/
(base) h44mi@nat079012 entrance % cat scroll 

It is pitch black in these catacombs.
You have a magickal spell that lists all items in a room.

To see in the dark, type:     ls
To move around, type:         cd <directory>

Try looking around this room.
Then move into one of the next rooms.

EXAMPLE:

$ ls 
$ cd cellar

Remember to cast ``ls`` when you get into the next room!

(base) h44mi@nat079012 entrance % cd chapel
(base) h44mi@nat079012 chapel % ls
altar*		courtyard/	scroll
(base) h44mi@nat079012 chapel % ./altar
In the corner is a decaying old altar of some forgotten god.
There is a small trinket on the ground.  It looks religious
in nature.

Do you want to put the trinket back on the altar? y/n  
y
You place the trinket upon the altar.  You feel a gentle
breeze pass through the room.

(base) h44mi@nat079012 chapel % ls
altar*		courtyard/	scroll
(base) h44mi@nat079012 chapel % cd courtyard
(base) h44mi@nat079012 courtyard % ls
aviary/		fountain*	rags*		scroll
(base) h44mi@nat079012 courtyard % ./fountain 
Do you want to approach the fountain? y/n  y
The waters sparkle in the light of your gaze.  You feel
drawn to it.

But you suddenly feel strength to turn away.  You hear a
sigh from the altar in the chapel.

(base) h44mi@nat079012 courtyard % ls
aviary/		fountain*	rags*		scroll
(base) h44mi@nat079012 courtyard % ./ rags
zsh: permission denied: ./
(base) h44mi@nat079012 courtyard % ./rags
There's a pile of old **rags**.  They are old and worn with
age, and probably fell off of some poor adventurer.

Do you want to take the rags? y/n  y
As you take the rags from the floor, you find a salted fish,
probably from the rations of the former owner of these rags.
Prefix these items to your inventory:

export I=rags,fish,$I

Remember, you can check your inventory

echo $I

(base) h44mi@nat079012 courtyard % export I=rags,fish,$I

(base) h44mi@nat079012 courtyard % echo $I

rags,fish,diamonds,crown,sword,amulet,
(base) h44mi@nat079012 courtyard % ls
aviary/		fountain*	rags*		scroll
(base) h44mi@nat079012 courtyard % cat scroll 

There is a great fountain in the center of this courtyard.
The waters are bright and clear in the magickal light
emanating from your eyes.

There were once plants growing here, but they are all 
dead and gnarled now.

If you stand still here, you can hear the soft rippling
of water, and even the occasional splash.

Perhaps there are fish that yet live in the fountain?

(base) h44mi@nat079012 courtyard % ls
aviary/		fountain*	rags*		scroll
(base) h44mi@nat079012 courtyard % cd aviary
(base) h44mi@nat079012 aviary % ls
crystal*	hall/		penguin*	scroll
(base) h44mi@nat079012 aviary % ./crystal 
A white crystal, forged by the Queen of Winter, on the
frosty ground.

You can prefix this item to your inventory:

I=crystal,$I

Remember, you can check your inventory:

echo $I

(base) h44mi@nat079012 aviary % I=crystal,$I

(base) h44mi@nat079012 aviary % echo $I

crystal,rags,fish,diamonds,crown,sword,amulet,
(base) h44mi@nat079012 aviary % ls
crystal*	hall/		penguin*	scroll
(base) h44mi@nat079012 aviary % ./penguin 
One of the birds finally notices your presence.  It turns
its head sideways, seemingly beckoning for you to come
closer.

Do you get closer? y/n  y
You take a step forward, and the bird rushes toward you, its
mouth open wide.  

Do you happen to have a fish? y/n  y

You toss the fish at the penguin,  which catches the fish
mid-air and gobbles it down.

Don't forget to remove the fish from your inventory.  Try
the following command:

export I=$(sed "s/fish//; s/,,/,/" <<< $I)

(base) h44mi@nat079012 aviary % export I=$(sed "s/fish//; s/,,/,/" <<< $I)

(base) h44mi@nat079012 aviary % echo $I

crystal,rags,diamonds,crown,sword,amulet,
(base) h44mi@nat079012 aviary % ls
crystal*	hall/		penguin*	scroll
(base) h44mi@nat079012 aviary % cat scroll 

You enter a room that has been magickally frost-bitten.

Snow and frost covers the ground, an icy pond leading perhaps
to an underground lake or to the outside, is in the far corner.

A few small black and white birds waddle around the room,
taking no notice of you.

Tip:
You can make your shell autocomplete the names of files and
directories by pressing the Tab key after typing the first
few letters.

When you move to the next room, try typing

cd h

and then press TAB.

(base) h44mi@nat079012 aviary % cd crystal 
cd: not a directory: crystal
(base) h44mi@nat079012 aviary % ls
crystal*	hall/		penguin*	scroll
(base) h44mi@nat079012 aviary % cd hall 
(base) h44mi@nat079012 hall % ls
carcass*	library/	treasure*
(base) h44mi@nat079012 hall % ./treasure 
This treasure has already been taken.
(base) h44mi@nat079012 hall % ./ carcass
zsh: permission denied: ./
(base) h44mi@nat079012 hall % ./carcass
You find the carcass of a foul beast.  Nothing of interest
lies within its remains.

(base) h44mi@nat079012 hall % cd library 
(base) h44mi@nat079012 library % ls
scroll	tome*
(base) h44mi@nat079012 library % ./tome

You see a large tome on the table, open
to a page in the middle of the book.

Do you read it? y/n  n 
(base) h44mi@nat079012 library % cat scroll 
#You are in a small library.  There are
#shelves on all sides of the room, 
#containing many books and knicknacks.  
#Before you, there is a small table 
#with a very large book open on it.

(base) h44mi@nat079012 library % cd entrance
cd: no such file or directory: entrance
(base) h44mi@nat079012 library % cd <entrance>
zsh: parse error near `\n'
(base) h44mi@nat079012 library % cd ../../../../..

(base) h44mi@nat079012 entrance % ls
cellar/	chapel/	scrap	scroll	vault/
(base) h44mi@nat079012 entrance % cd vault
(base) h44mi@nat079012 vault % ls
glass*		scroll		stronghold/
(base) h44mi@nat079012 vault % cat scroll 

#You have entered an asymmetric room with shards of glass
#arranged along the floor in haphazard patterns.
#As you move past them, they each appear to turn slightly,
#as if watching you go.
#On the wall is a picture of two goblets:
#one glows brightly,
#the other shines darkly

(base) h44mi@nat079012 vault % ls
glass*		scroll		stronghold/
(base) h44mi@nat079012 vault % ./ glass
zsh: permission denied: ./
(base) h44mi@nat079012 vault % ./glass
Do you have an ice crystal? y/n  y
You place the ice crystal among the shards of glass.  The
sword in your hands becomes cold.  You feel the power of
1000 blizzards coursing through it.

Don't forget to remove the crystal from your inventory.  Try
the following command:

export I=$(sed 's/crystal,//' <<< $I)
(base) h44mi@nat079012 vault % export I=$(sed 's/crystal,//' <<< $I)

(base) h44mi@nat079012 vault % ls
glass*		scroll		stronghold/
(base) h44mi@nat079012 vault % cd stronghold 
(base) h44mi@nat079012 stronghold % ls
goblet*		nursery/	orb1		scroll
(base) h44mi@nat079012 stronghold % cat scroll 

#There is a fine gold goblet at the center of a
#runic triangle on the floor.
#You try to take the goblet, but your hand
#passes through it as if it were illusory.
#You notice a glowing orb, labeled orb1, in one
#corner of the triangle. The other points of the 
#triangle are labeled orb2 and orb3, but the orbs 
#have long since been stolen by tomb raiders.
#Perhaps adding more orbs would free the goblet's 
#material form. 
#You remember a spell your magick teacher,
#Caitlin the Green, taught you long ago:
#a spell to copy and name objects...

(base) h44mi@nat079012 stronghold % cp orb1
usage: cp [-R [-H | -L | -P]] [-fi | -n] [-aclpSsvXx] source_file target_file
       cp [-R [-H | -L | -P]] [-fi | -n] [-aclpSsvXx] source_file ... target_directory
(base) h44mi@nat079012 stronghold % cp orb1 orb2
(base) h44mi@nat079012 stronghold % cp orb1 orb3 
(base) h44mi@nat079012 stronghold % ls
goblet*		orb1		orb3
nursery/	orb2		scroll
(base) h44mi@nat079012 stronghold % ./goblet 
You have freed the goblet's material form.  Add 'goblet' to
your inventory.

(base) h44mi@nat079012 stronghold % export I=goblet,$I

(base) h44mi@nat079012 stronghold % echo $I
goblet,rags,diamonds,crown,sword,amulet,
(base) h44mi@nat079012 stronghold % ls
goblet*		orb1		orb3
nursery/	orb2		scroll
(base) h44mi@nat079012 stronghold % cd nursery 
(base) h44mi@nat079012 nursery % ls
lab/	scroll	spell*
(base) h44mi@nat079012 nursery % cat scrolk 
cat: scrolk: No such file or directory
(base) h44mi@nat079012 nursery % cat scroll 

#Once a thriving nursery filled with vibrant plants,
#this is now the Nursery of the Still Dead (it says so,
#in writing on the wall).

(base) h44mi@nat079012 nursery % ./spell
A page from a druid's tome of incantations lies on the
ground.  It reveals to you how to summon a healing potion:

#To find a file on your system, use the find command.  For
#example, to search this room: 

find . -name "potion"

#Once you've found a potion, copy it to this directory and
#run this spell script again.

There are no potions in this room.  But try searching
starting at the entrance.

Hint: use pwd to determine how many rooms (folders) are
between you and the entrance.

(base) h44mi@nat079012 nursery % find . -name "potion"

(base) h44mi@nat079012 nursery % pwd
/Users/h44mi/Downloads/bashcrawl-stable-2024.02.09/entrance/vault/stronghold/nursery
(base) h44mi@nat079012 nursery % find ../../.. -name "potion"
../../../cellar/armoury/potion
(base) h44mi@nat079012 nursery % cp ../../../cellar/armoury/potion .

(base) h44mi@nat079012 nursery % ls
lab/	potion*	scroll	spell*
(base) h44mi@nat079012 nursery % ./spell 
You have summoned a potion from afar.  You drink it quickly
and feel a surge of strength.

Add 5 HP to your score.

(base) h44mi@nat079012 nursery % ls
lab/	potion*	scroll	spell*
(base) h44mi@nat079012 nursery % cd lab 
(base) h44mi@nat079012 lab % ls
ghost*	scroll
(base) h44mi@nat079012 lab % ./ghost
The room shakes, a gust of wind blasts you from nowhere.
You sense that a presence has entered the room.  The pain
you suddenly feel assures you that you are under attack by a
ghostly entity!

If you have a sword, you can attack.  Otherwise, you should
run.  

Do you want to attack? y/n  y
Enter a number:  15
The monster rolled  17
You rolled  14
+2 bonus from a mysterious wintry patron!
Your sword swings harmlessly through the air.  You take 5
points damage. Deduct this from your HP variable:  

let HP=HP-5

Enter a number:  let HP=HP-5
The monster rolled  14
You rolled  41
+2 bonus from a mysterious wintry patron!
A hit! A palpable hit!  You have slain the spirit of the
evil wizard.

(base) h44mi@nat079012 lab % 
(base) h44mi@nat079012 lab % ls
ghost*		platinum*	scroll		treasure*
(base) h44mi@nat079012 lab % cat scroll 

#An abandoned laboratory of a wizard long dead. 
#A lone magickal torch ignites as you enter, shedding
#light on the workshop, and casts haunting shadows
#on every surface.
#The flames lick the walls, burning off the moss that had
#gathered there. The burning moss sizzles in the silence
#of the catacombs, like angelic wailing or singing.

(base) h44mi@nat079012 lab % ./treasure
You have found an *emerald*!  Add it to your inventory.

(base) h44mi@nat079012 lab % export I=emerald,$I  

(base) h44mi@nat079012 lab % echo $I 
emerald,goblet,rags,diamonds,crown,sword,amulet,
(base) h44mi@nat079012 lab % ls
ghost*		platinum*	scroll		treasure*
(base) h44mi@nat079012 lab % ./platinum 
You have found a sack full of *platinum* coins!  Add it to
your inventory.

(base) h44mi@nat079012 lab % export I=emerald,$I  

(base) h44mi@nat079012 lab % echo $I
emerald,emerald,goblet,rags,diamonds,crown,sword,amulet,
(base) h44mi@nat079012 lab % export I=platinum,$I  

(base) h44mi@nat079012 lab % echo $I 
platinum,emerald,emerald,goblet,rags,diamonds,crown,sword,amulet,
(base) h44mi@nat079012 lab % ls
ghost*		platinum*	scroll		treasure*
(base) h44mi@nat079012 lab % cat scroll 

#An abandoned laboratory of a wizard long dead. 
#A lone magickal torch ignites as you enter, shedding
#light on the workshop, and casts haunting shadows
#on every surface.
#The flames lick the walls, burning off the moss that had
#gathered there. The burning moss sizzles in the silence
#of the catacombs, like angelic wailing or singing.

(base) h44mi@nat079012 lab % ./ghost
The room shakes, a gust of wind blasts you from nowhere.
You sense that a presence has entered the room.  The pain
you suddenly feel assures you that you are under attack by a
ghostly entity!

If you have a sword, you can attack.  Otherwise, you should
run.  

Do you want to attack? y/n  y
Enter a number:  20
The monster rolled  28
You rolled  27
+2 bonus from a mysterious wintry patron!
A hit! A palpable hit!  You have slain the spirit of the
evil wizard.

(base) h44mi@nat079012 lab % ls -F
ghost*		platinum*	scroll		treasure*
(base) h44mi@nat079012 lab % cd ..
(base) h44mi@nat079012 nursery % ls
lab/	potion*	scroll	spell*
(base) h44mi@nat079012 nursery % cd .. 
(base) h44mi@nat079012 stronghold % ls
goblet*		orb1		orb3
nursery/	orb2		scroll
(base) h44mi@nat079012 stronghold % cd .. 
(base) h44mi@nat079012 vault % ls
glass*		scroll		stronghold/
(base) h44mi@nat079012 vault % cd stronghold
(base) h44mi@nat079012 stronghold % cat scroll 

#There is a fine gold goblet at the center of a
#runic triangle on the floor.
#You try to take the goblet, but your hand
#passes through it as if it were illusory.
#You notice a glowing orb, labeled orb1, in one
#corner of the triangle. The other points of the 
#triangle are labeled orb2 and orb3, but the orbs 
#have long since been stolen by tomb raiders.
#Perhaps adding more orbs would free the goblet's 
#material form. 
#You remember a spell your magick teacher,
#Caitlin the Green, taught you long ago:
#a spell to copy and name objects...


Script started, output file is bashcrawl.log
(base) h44mi@nat079012 stronghold % history -1000 >> bashcrawl.log

