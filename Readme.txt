Steps to excecute:
	1.Pull the repo from github https://github.com/Prasanna616/Python.git
	2.open python file and run.(requried curser library)
	3.You can add additional typing lines in text file.

--What is Curser?
The curses library supplies a terminal-independent screen-painting and keyboard-handling facility for text-based terminals; such terminals include VT100s, the Linux console, and 
the simulated terminal provided by various programs.

--install curses on windows
pip install windows-curses


--A common problem when debugging a curses application is to get your terminal messed up when the application dies without restoring the terminal to its previous state. In Python 
  this commonly happens when your code is buggy and raises an uncaught exception. Keys are no longer echoed to the screen when you type them, for example, which makes using the shell
  difficult.
  In Python you can avoid these complications and make debugging much easier by importing the curses.wrapper() function and using it like this:
 	
	from curses import wrapper

	def main(stdscr):
    		# Clear screen
    		stdscr.clear()

    		# This raises ZeroDivisionError when i == 10.
    	for i in range(0, 11):
        	v = i-10
        	stdscr.addstr(i, 0, '10 divided by {} is {}'.format(v, 10/v))

    	stdscr.refresh()
    	stdscr.getkey()

	wrapper(main)

--The wrapper() function takes a callable object and does the initializations described above, also initializing colors if color support is present. wrapper() then runs your provided 
  callable. Once the callable returns, wrapper() will restore the original state of the terminal. The callable is called inside a try…except that catches exceptions, restores the state 
  of the terminal, and then re-raises the exception. Therefore your terminal won’t be left in a funny state on exception and you’ll be able to read the exception’s message and traceback.


--The init_pair routine changes the definition of a color-pair. It takes three arguments: the number of the color-pair to be changed, the foreground color number, and the background color
  number. For portable applications:
  The value of the first argument must be between 1 and COLOR_PAIRS-1, except that if default colors are used (see use_default_colors) the upper limit is adjusted to allow for extra pairs 
  which use a default color in foreground and/or background.

--Often, when dealing with iterators, we also get need to keep a count of iterations. Python eases the programmers’ task by providing a built-in function enumerate() for this task.
  Enumerate() method adds a counter to an iterable and returns it in a form of enumerating object. This enumerated object can then be used directly for loops or converted into a list
  of tuples using the list() method.
  Syntax: enumerate(iterable, start=0)
  Ex:	l1 = ["eat", "sleep", "repeat"]
	s1 = "geek"

	obj1 = enumerate(l1)
	obj2 = enumerate(s1)

	print(" Return Type:", type(obj1))
	print(list(enumerate(l1))
	# changing start index to 2 from 0	
	print(list(enumerate(s1))

  output:
	Return type: 
	[(0, 'eat'), (1, 'sleep'), (2, 'repeat')]
	[(2, 'g'), (3, 'e'), (4, 'e'), (5, 'k')]

