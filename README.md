# rethinkux_assignment
Assignment for Rethink UX

Initialize git repository and your project inside that directory.
-- done

Write code in the project.
-- done

Create a Readme file that contains :
-- in progress

How to set up the project on our systems?
-- The project is hosted on github pages at https://arkeyve.github.io/rethinkux_assignment/. There would be no need to setup, however, if required, we would just need to unzip the repo files.

How to run the project?
-- Go to https://arkeyve.github.io/rethinkux_assignment/, or uzip and execute index.html on any modern browser.

How you’re representing objects in your system? Tell us about the data structure
-- I've designed the assignment as requested, with minimal styles and a clean approach. There are no data structures as such. (a combination of stacks and queues was initially attempted for undo/redo operations, but the current approach seemed better to me)

How the undo-redo functionality is working? Discuss the approach here.
-- I had initially planned on maintaining two arrays. The undo stack and redo queues would have worked together for those operations. However, rather than maintaining multiple data structures, it made more sense to me to keep a single history array, and a pointer to the current state in history.
   The functions work as follows:
      - A history array is initialized with no elements along with a pointer (p) initialized as -1.
      - Whenever a change is made to the state of the canvas, an image is saved in the history array with the state after the change, and p is incremented.
      - If undo is requested, we subtract p by 1, clear the canvas, and draw the pth state from the history array.
      - If redo is requested, we add 1 to p, clear the canvas, and draw the pth state from the history array.

Websites that helped you complete this assignment if any.
-- w3school and mozilla for canvas reference

Problems you faced if any.
-- Well, first, I found this tonight, thanks to gmail's aggressive spam filter.
   As for the assignment, I could not figure out how to draw intermediate rectangles and lines while the mouse is being dragged. I tried two approaches:
      - on drag, clear the canvas and keep painting the state before the rectangle started, and the current state of the rectangle. This probably failed due to some issue in the asynchronous execution.
      - Only draw the final state on canvas, but show a temporary fixed size floating div to indicate the rectangle being drawn, and to give the illusion that it's being drawn directly on canvas.

Create a zip file and submit it on the submission page. Note: Do not forget to include ‘.git’ folder into the zip file. It’ll help us analyzing your commit messages if any.
Note: Max zip size allowed is 100 MB
