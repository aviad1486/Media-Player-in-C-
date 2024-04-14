# Media-Player-in-C-
Application:
You are required to implement 2 types of audio players (MP3 & MP4), and a small set of operations – downloading a song, playing all songs, removing all songs from your player, creating a backup of your player, and restoring its content from the backup.
•	Download: there are 3 genres of songs – Foxtrot, Techno, and Waltz. Songs are “downloaded” from a SongFactory instance, as Song*, and stored on the Player. To store the songs on the player you will implement a linked list.
•	Play: playing all songs is simulated by simply printing their genres one by one. On MP3, songs are played in a chronological order – the genre of the songs that was downloaded first (last) is printed first (last) etc. An MP4 player somehow plays songs in a reverse order, and it does not play Techno.
•	Backup: your program should initially create two instances of a player – one is used to download and play songs, and the other is used to back up your songs. Backing up your songs should be implemented as letting the backup player be a deep copy of the other player.
•	Restore: restoring the content of your player should be implemented as letting your player be a deep copy the backup player.
•	Remove: all songs on your player should be deleted.

Application flow:
1.	The main function should define Player* player and Player* backup, and wait for user input – if the user inputs 3 – both player and backup should be initialized as (pointers to) MP3s; if the user inputs 4 – both player and backup should be initialized as MP4s.
2.	Your main function should run a while loop that waits for user input. User input should be an integer in range 0-5; each choice indicates an operation you should implement.
a.	An input of 1 stands for a download. Now your program needs to wait for an additional integer and act accordingly – download a Foxtrot if you get 1, Techno if you get 2, and Waltz if you get 3.
b.	An input of 2 stands for play. You should print all the genres you have in your player, one by one. When you finish, print the number of songs in your player.
c.	An input of 3 stands for backup. You should let your backup point to a deep copy of your player (do not forget to free all existing memory in your backup).
d.	An input of 4 stands for restore. You should let your player point to a deep copy of your backup (do not forget to free all existing memory in your player).
e.	An input of 5 stands for remove. You should delete all songs in your player.
f.	If the input is 0, you should quit the while loop, free all memory used by your program and terminate.

MP3, MP4:
The requirements for your players are very specific and require your full attention. If anything is not clear, see the relevant input-output example below. You are also encouraged to ask questions at the dedicated forum on the course site.
•	An MP3 is initialized with a Walts* waltz = new Waltz(); (see code). This song must be played first upon operation play. When you remove (or restore) all songs from the player, this song should also be removed (restored). It might be restored later from the backup…
•	Although an MP4 does not play Techno, it should have them as links (in the linked list data structure). E.g., when you print the number of your songs in your player (upon operation play, any Techno you have in your player should be counted.

Implementation:
•	You are given some code. You must use this code, and must never override it! That is, you should use the SongFactory to download songs as Song*, you should store the songs on the Player as a linked list starting at Link* head, each link in the linked list must use a pointer to a song (Song* cur) and a pointer to the next link (Link* next), etc.
•	Make sure that all memory is freed before the process terminates.
•	Never explicitly call a destructor.
•	Casting usually indicates non-generic code that cannot be easily extended. Do not use it.
•	Do not duplicate code! Use the base class Player for code that both types of players share.
