# FALLING BLOCKS

![Gameplay Image](images/gameplay.jpg)

**Description:** This is a clone of the well-known game of falling puzzle blocks. It is written in C and relies on the ncurses library. It runs the whole game in the terminal when the user runs the executable and then resumes business-as-usual when the game is over. **'a', 's', 'd'** keys to move left, down, and right. **'f'** key to rotate the tetromino. **'p'** to pause the game. Press **'CTRL+C'** to exit, except during the game over screen when you'll be prompted to quit with **'q'**. I wrote this to see if I could and this is the unoptimized prototype. After writing it, I got side-tracked by life and abandoned the project, but I was recently encouraged to put it up again. It never got past the "naïve prototype" stage and it shows in a lot of the code. I plan on re-writing this in Rust, rather than C, in the very near future.

**Options:** `-easy`, `-medium`, and `-hard` set the size of the speed decrements for each new level (so harder means the blocks fall faster sooner). `-ascii` and `-solid` set the symbols used for the tetromino blocks (solid gives a more arcade-like appearance). By default no color is used. An example might be `./blocks -easy -ascii` or `./blocks -solid -hard`. Some players might find it easier to "line up" the tiles using the `-ascii` setting instead of the `-solid` setting.

**State of the Project:** pre-0.0.1. Like a car with just an engine, wheels, loud muffler, one headlight, and a frame. It can be played from start to finish for as long as you like. It can take awhile to ramp up to high difficulty, and the nature of the input system makes it very difficult once it gets there, but it's totally good for an hour or two of fun.

**Installation/Dependencies:** If you want to use this you'll need to build it yourself by following these steps:
1. Make sure you have `gcc` installed, along with basic build tools. On Debian-based systems like Ubuntu this is usually in a package called `build-essential`. You'll also need `libncurses5-dev` (the version I had when writing it) or later, which you can also find in your distribution repositories. On Arch all you should need is `base-devel`. Consult your distribution's repositories for more information if you're on another distro.
2. Clone this repository or download it. 
3. From the main project directory, enter: `gcc -O2 src/falling_blocks.c -o blocks -l ncurses`
4. You should now have an executable file named `blocks` and you can run the game with: `./blocks [OPTIONS]`

**Disclaimer:** I am not a professional programmer, although I did enjoy making this a lot. Compile and run at your own risk. It is heavily unoptimized and the style is not yet presentable. With the exception of ncurses' internal behavior, everything happens on the stack. This was a quick prototype where I didn't want to spend much time on memory allocation. Almost everything happens "in-place" and it has a very small memory footprint. The functions which govern the rotation of tetrominos and actual display logic are *extremely naïve* and although the game runs great you can tell that it's using much more CPU than it should for such a simple game. I haven't messed with this very much since writing it in early 2020 and I have a million ideas on how to improve this code-base, and I'll be re-implementing all of this in Rust in the near future, which is a language I've taken an interest in. In the meantime, anyone who wants to mess with it is 100% welcome to do so; I have left comments in some of the most pertinent parts of the code where performance is an issue. If I do anything further with the C version of the project before moving on to the Rust version it will be to refactor those parts (because I'll admit they're ridiculous). I had a lot of fun writing this and sharing is caring, so have at it. I have learned a lot since writing this and I am in a position to get back to it soon.

**References:** Some resources were helpful while making this program so far:
- *C Programming, a Modern Approach (2nd Edition)* by K.N. King. I surely am not doing this fine book justice by mentioning it in the same breath as my naïve and unoptimized prototype, but it really is a wonderful book and was extremely helpful.
- Wikipedia has a good page on tetrominos.
- The ncurses documentation

