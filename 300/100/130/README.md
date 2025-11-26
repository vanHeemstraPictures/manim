# 130 - Install Manim

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

**Troubleshooting**

To solve the [pangocairo problem](https://github.com/3b1b/manim/issues/1635) using these commands:
```
sudo apt-get install libcairo2-dev
sudo apt-get install libpango1.0-dev
sudo apt-get install libavformat-dev
sudo apt-get install libavdevice-dev
```

If it gives an error then one more command needs to be run:
```
pip install -I moderngl==5.5.4
```