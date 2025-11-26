# 400 - Animating a circle

1. Open a text editor, such as Notepad. Open the file ```main.py``` in the ```my-project``` folder. It should look something like this:

```
from manim import *
class DefaultTemplate(Scene):
    def construct(self):
        circle = Circle()  # create a circle
        circle.set_fill(PINK, opacity=0.5)  # set color and transparency

        square = Square()  # create a square
        square.flip(RIGHT)  # flip horizontally
        square.rotate(-3 * TAU / 8)  # rotate a certain amount

        self.play(Create(square))  # animate the creation of the square
        self.play(Transform(square, circle))  # interpolate the square into the circle
        self.play(FadeOut(square))  # fade out animation
```

2. Open the command line, navigate into your project folder ```my-project```, and execute the following command:

```
cd my-project
manim -pql main.py DefaultTemplate
```

Accept the ```Default``` when prompted.

You will get an output like:

```
Manim Community v0.19.0

[11/26/25 12:32:01] INFO     Animation 0 : Partial movie file written in                                                                                                           scene_file_writer.py:588
                             '/workspaces/manim/my-project/media/videos/main/480p15/partial_movie_files/DefaultTemplate/2289379569_3901458704_223132457.mp4'                                               
                    INFO     Animation 1 : Partial movie file written in                                                                                                           scene_file_writer.py:588
                             '/workspaces/manim/my-project/media/videos/main/480p15/partial_movie_files/DefaultTemplate/921762691_3900508965_557880437.mp4'                                                
                    INFO     Animation 2 : Partial movie file written in                                                                                                           scene_file_writer.py:588
                             '/workspaces/manim/my-project/media/videos/main/480p15/partial_movie_files/DefaultTemplate/921762691_2956010123_557880437.mp4'                                                
                    INFO     Combining to Movie file.                                                                                                                              scene_file_writer.py:739
                    INFO                                                                                                                                                           scene_file_writer.py:886
                             File ready at '/workspaces/manim/my-project/media/videos/main/480p15/DefaultTemplate.mp4'                                                                                     
                                                                                                                                                                                                           
                    INFO     Rendered DefaultTemplate                                                                                                                                          scene.py:255
                             Played 3 animations                                                                                                                                                           
Error: no "view" mailcap rules found for type "video/mp4"
[11/26/25 12:32:04] INFO     Previewed File at: '/workspaces/manim/my-project/media/videos/main/480p15/DefaultTemplate.mp4' 
```

Manim will output rendering information, then create an MP4 file. Your default movie player will play the MP4 file, displaying the following animation.

If you see an animation of a pink circle being drawn, congratulations! You just wrote your first Manim scene from scratch.

If you get an error message instead, you do not see a video, or if the video output does not look like the preceding animation, it is likely that Manim has not been installed correctly. Please refer to our [FAQ section](https://docs.manim.community/en/stable/faq/index.html) for help with the most common issues.

## Explanation

Let’s go over the script you just executed line by line to see how Manim was able to draw the circle.

The first line imports all of the contents of the library:

```
from manim import *
```

This is the recommended way of using Manim, as a single script often uses multiple names from the Manim namespace. In your script, you imported and used Scene, Circle, PINK and Create.

Now let’s look at the next two lines:

```
class DefaultTemplate(Scene):
    def construct(self):
        [...]
```

Most of the time, the code for scripting an animation is entirely contained within the ```construct()``` method of a ```Scene``` class. Inside ```construct()```, you can create objects, display them on screen, and animate them.

The next two lines create a circle and set its color and opacity:

```
circle = Circle()  # create a circle
circle.set_fill(PINK, opacity=0.5)  # set the color and transparency
```

Finally, one of the last lines uses the animation ```Create``` to display the circle on your screen:

```
self.play(Create(circle))  # show the circle on screen
```

**Tip**

All animations must reside within the ```construct()``` method of a class derived from ```Scene```. Other code, such as auxiliary or mathematical functions, may reside outside the class.
