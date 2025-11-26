# 300 - Starting a new project

If you have Manim projects in many different directories and you do not want to setup a local project environment for each of them, you could also install Manim as a ```uv```-managed tool.

See [uv’s documentation for more information](https://docs.astral.sh/uv/concepts/tools/) on their tool mechanism.

To install Manim as a global uv tool, simply run

```
uv tool install manim
```

after which the ```manim``` executable will be available on your global system path, without the need to activate any virtual environment or prefixing your commands with ```uv run```.

Note that when using this approach, setting up your code editor to properly resolve ```import manim``` requires additional work, as the global tool environment is not automatically detected: the base path of all tool environments can be determined by running

```
uv tool dir
```

which should now contain a directory ```manim``` in which the appropriate virtual environment is located. Set the Python interpreter of your IDE to this environment to make imports properly resolve themselves.

Start by creating a new folder:

```
manim init project my-project --default
```

The ```my-project``` folder is the root folder for your project. It contains all the files that Manim needs to function, as well as any output that your project produces.
