# Tips for Components


Once you code the components, many concepts of the course come together.
In addition, running components in Python requires a lot of technical details to be correct as well, and the complexity may initially be high. Therefore, some tips and comments that may help and motivate you.


# Inherent Difficulties

**Good Component Structures:** Working in teams gets easier when the system is decomposed into separate components, but arriving at a good component structure in itself can be difficult. And then there is the problem of ensuring that the components interaction with each other consistently. Part of this is difficult simply because it is a complex task, and there is not a clear, simple and necessarily straightforward way to arrive at a good component decomposition. The other part is to coordinate code in a team of developers. Therefore, having a good overall system understanding from deployment diagrams and interactions is so valuable.

**APIs between components:** Defining APIs that also specify a sequence of actions is, unfortunately, not mainstream. There are a lot of standards to specify call signatures (which data to send and what to expect in return), but not an equally standard and popular way to specify their sequence. In this course, instead of learning an API language that does specify also behavior, we use the interactions as a specification of the expected behavior.

**Complexity of concurrency:** Working with more complex interactions, ones that go back and forth, invole alternatives and more than two communication partners are notoriously complex, but in some cases absolutely necessary. Therefore it may be quite natural that you struggle a bit, simply because you are trying to solve a complex problem. Just don't do one mistake: Don't blame the tools for the problem when its the problem that's hard. (You can blame the tools if they don't do what they should, though.) For example, it's tempting to think that you could "code" a solution easier without state machines. For some problems this might be true, but for some it isn't.

**Going back to diagrams:** Once you are coding, you need to have a picture of the overall system in your mind, for example in the form of a deployment diagram, interactions between components and state machines for the coordination of local behavior. If that picture is not consistent, creating code code can be frustrating and impossible even. In that case, go back to the diagrams and improve your understanding of the system!



# Tips

**Move away from notebooks:** Only use notebooks for small code parts. Notebooks are not always the best solution with concurrency, threads, STMPY and MQTT. Instead, run code in *.py projects from the command line.

**Work alone:** Work alone for a while — coding in team is hard or impossible once code gets complex. You need silence and focus to get your head around all the elements that need to connect to each other.

**Work in pairs:** Try to work in pairs. One student (A) can create some code that focuses on a single component or function in a component. Then you look at the code together as a pair. Let the other student (B) explore the code and explain to (A) what the code probably does, or ask questions and be a critical friend to find problems or improvements if necessary.

**Be persistent:** Nearly all new code fails in early versions, since there are so many things to consider.

**Isolate problems:** Make a lot of small programs to test functions you are not yet familiar with. Don't expect you can code many new things into a large piece of code and all will work. It will just get hard (or impossible) to debug.

**Re-Read:** Have again a look at the STMPY documentation. It should be complete. If you miss something, tell me. Also, dare to have a look at the source code yourself. It might be easier than you think. Also, have a look again at the activity on components, which introduces many of the concepts in the text. 