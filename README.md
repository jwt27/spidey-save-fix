This is a patch for [The Amazing Spider-Man](https://www.mobygames.com/game/dos/amazing-spider-man), a puzzle/action platformer released in 1990 for IBM PC.

The problem that this patch addresses, is that the game appears to support progress saves through checkpoints, but this is never saved to disk. Your progress is lost whenever you exit the game and boot it up again. While this is typical behaviour in early home computer games that load from tape, for a disk-based PC game from 1990 it is highly unusual. Given the length and difficulty of this game, it is next to impossible to finish in one session.  
After applying this patch, both your progress and highscores are saved to disk. As a side effect, this patch also removes the copy protection routines, since this space is overwritten by the new code.

The game's executable is compressed with Microsoft EXEPACK, and must be decompressed before patching. A suitable tool is [unEXEPACK](https://github.com/w4kfu/unEXEPACK).  
To apply the patch, run:  
````
$ xdelta3 -d -s spidey-unpacked.exe spidey.xdelta spidey-patched.exe
````

To enable the fix, create two empty (0 byte) files in the same directory: SPIDEY.SAV and HISCORE.DAT. When these files are removed again, the game behaves as it did originally; no progress or highscores are saved. To reset your progress or the high score list, clear out the respective file.

It is safe to accidentally start a new game without losing progress. The save file is only overwritten once you hit the first checkpoint.

This patches the US release only. To determine whether you have the US or the international version:
- International release starts with a language selection screen for the copy protection questions.
- US release has a fifth video mode (16-color Tandy).
- US release shows a comic strip intro sequence on startup.
