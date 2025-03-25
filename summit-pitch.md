# Summit pitch

Questions: who shall be the person that pitches?

## Title
*The title of your talk/discussion topic. This will appear in the Language Summit schedule on the conference website.*

Fearless Concurrency in Python


## Key discussion item

> *What is the "thing" you want to discuss in front of mostly Python core developers? What decision to be made? What are your questions, and proposed solutions? This should fit in 10 minutes, to allow for 20 minutes of discussion. Therefore this should be very focused. This field will only be read by Language Summit co-chairs to determine the talk acceptance. You can include a rough outline, useful links, sample discussions, etc.*


We want to discuss a dynamically checked ownership model for Python objects and a "fearless" concurrency model that it enables.
The ownership model is based on "regions" and "deep immutability" and allows existing Python data structures to be used in multi-threaded programs.

The presentation will be based on collaboration with the Faster CPython team at Microsoft and
prototyping work done on a fork of the CPython interpreter.
The initial design is documented in a research paper that is conditionally accepted to appear at the ACM PLDI'25 conference.
[Note that the paper is not yet public, but will be available by the time of the Language Summit.]

The aim of the presentation is to get feedback on the ideas, and to discuss the implications of the model for Python.
We also want to discuss with the core developers the possibility of getting this into CPython itself.
We will also describe how the model can be implemented in CPython, and what changes would be needed to the language and runtime to support it.


## The public pitch
*This will be shown in the Language Summit schedule on the conference website and published ahead of the event. Write one or two short paragraphs to pitch this topic to the attendees. This is your chance to encourage people to discuss the topic with you!*

With the move to free-threaded Python, the challenges of concurrency are coming to Python developers.
The race conditions that are common in concurrent programming are hard to debug, and require different tooling than what is commonly used in Python.
We believe there is an opportunity to build a new concurrency model for Python based on "regions" and "deep immutability".
The goal is to provide a model that is easy to use and flexible, so existing Python programs can be easily ported to multi-threading.
The model allows for safe sharing of data between threads (in free-threaded Python) and sub-interpreters.

Free-threaded Python enables the use of multiple threads with a single interpreter, but underlying sequential assumptions of the code on top of the interpreter
are not valid anymore. This adds new classes of potential bugs to Python programs.
By building fearless concurrency into Python, those sequential assumptions can be enforced at the language level, while
still permitting true multi-threading.

The presentation is based on the ideas presented in a research paper in the ACM PLDI'25 conference: (link to be once available).