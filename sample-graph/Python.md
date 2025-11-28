- [Python](https://www.python.org/)
  id:: 629ccb26-9513-49ea-946c-5b33f145c698
	- Pros/Cons
	  collapsed:: true
		- Pros
			- Python is a general purpose language that is used in many areas:
			  collapsed:: true
				- Data sciences
				- ((63f8fe5a-e718-4363-aba5-549a93eec7a7)) and Machine Learning
				- Web application
				- Server automation
				- web programming, scientific programming, game programming as a scripting language, automation scripting instead of Bash scripts,
		- Cons
			- Node JS basically can replace Python in almost any scenario and out perform it. Python is almost never well suited for a new project because it's slow. It enjoys some popularity because it's easy to learn and can be used almost everywhere, but unfortunately while it can be used for anything, it's almost never the best language for any one thing (this is one guy's opinion though)
			- [Python is bad](https://news.ycombinator.com/item?id=32578743)
		- ((6524165b-df01-4604-b087-36948ddba94f))
	- # Documentation
		- Cheatsheet
		  collapsed:: true
			- ((6541f026-6d71-46d4-a23e-d4197d68b21d))
			- Code snippets
			  id:: 67403b92-7779-44d2-aa1b-b401acaffdb8
			- T-strings
				- [Python’s new t-strings | Hacker News](https://news.ycombinator.com/item?id=43748512)
			- If you want to skip giving a value for a particular argument then use `None`
			- Infinite while loop
			  collapsed:: true
				- ```python
				  import time
				  
				  while True:
				  print("Looping...")
				  time.sleep(3)  # Pause for 3 seconds
				  ```
			- How to do a `sleep` timer asynchronously
			  collapsed:: true
				- ```python
				  import asyncio
				  
				  async def show_page(page):
				  while True:
				  page.refresh()
				  page.display()
				  await asyncio.sleep(3)  # Wait while allowing event processing
				  ```
			- `if` statements require a colon e.g. `if current_page == 0:`
			- To import from a parent directory the syntax is `from ../display_page import DisplayPage`
			  collapsed:: true
				- If you're instead importing from another file in the same level directory (sibling) then it'd be just `from display_page import DisplayPage`
			- To make some dictionary of values available as a module to another file
			  collapsed:: true
				- File 1
				  collapsed:: true
					- ```python
					  def get_service_values():
					  service values = {
					  "DOMAIN": "TEST1",
					  "DOMAIN2": "TEST2
					  }
					  
					  return service_values
					  ```
				- File 2
				  collapsed:: true
					- ```python
					  from file_1 import get_service_values
					  
					  service_values = get_service_values()
					  
					  f"Show: {service_values['DOMAIN']} now"
					  ```
			- `main.py` is used as the entrypoint file by convention
			- Using virtual environments for each Python project
			  collapsed:: true
				- `python -m venv <env-name>`
					- `python -m venv .venv` is the convention
						- It creates a hidden directory rather than visible (`.venv/`)
						- It's recognised by most Python tools
						- It's the convention recommended by Python docs, VSCode, other IDEs
				- `source <env-name>/bin/activate` to start the virtual environment
					- e.g. `.venv/bin/activate`
				- `deactivate` to exit the virtual environment
			- `__init__.py` empty files
			  collapsed:: true
			  AKA initialisation files
				- These serve as a marker to indicate that the directory should be treated as a module. This allows them to be imported into other Python files (e.g. `main.py`) using `from <path.to.file> import <name>` syntax
				- This should be included in every subdirectory, even if you're deeply nesting your files?
			- HTTP module vs Flask
			  collapsed:: true
				- Python http Module: Best for simple, lightweight tasks and basic HTTP server/client functionality.
				- Flask: Best for building web applications with more advanced features and a rich ecosystem of extensions.
			- Imports
			  collapsed:: true
				- Imports
				  collapsed:: true
					- Note: executing `python src/main.py` interprets imports differently than `python -m src/main.py`
					- Assuming `python src/main.py`, can now import using this syntax:
						- Example directory structure
							- `projectroot/`
								- `src/`
									- `server/`
										- `stream_server.py`
										- `audio_streamer.py`
								- `pyproject.toml`
								- `config.py`
								- `main.py`
						- Imports examples
							- In `src/main.py`
								- ```python
								  from config import *
								  from server.stream_server import *
								  ```
							- In `src/server/stream_server.py`
								- ```python
								  from config import *
								  from server.audio_streamer.py import AudioStreamer
								  ```
					-
				- To import a sibling Python file add the prefix `.`
					- e.g. `from .audio_streamer import AudioStreamer` assuming `audio_streamer.py` is a file in the same directory
				- To import one from a sibling directory instead use `..`
					- e.g. `from ..quic.packet import QuicErrorCode` assuming that the directory you're currently in is a sibling directory to `quic`, and `packet.py` is thus at the same depth
			- VSCode select the correct Python interpreter
			  collapsed:: true
				- `CTRL + SHIFT + P` for Command Palette
				- `Python: Select Interpreter`
			- VSCode - how to quickly view referenced files/modules
			  collapsed:: true
				- Go to Definition:
					- Hold Ctrl and click on the import name (e.g., click on HandshakeCompleted)
					- Or place your cursor on the name and press F12
					- Or right-click and select "Go to Definition"
				- Peek Definition:
					- Press Alt + F12 while your cursor is on the import name
					- This opens an inline view without leaving your current file
				- Go to Type Definition:
					- Press Ctrl + Shift + Click on the import name
					- Or use the keyboard shortcut Ctrl + F12
				- Find All References:
					- Press Shift + Alt + F12 to see all places where the symbol is used
			- `config.py` next to `main.py` is one convention for where to store global variables
			  collapsed:: true
				- `BASE_DIR = os.path.dirname(os.path.abspath(__file__))` can be useful
					- Requires `import os`
					- An alternative way to get the BASE_DIR path whilst within a file nested 3 layers deep: `BASE_DIR = Path(__file__).resolve().parent.parent.parent`
						- Requires `from pathlib import Path`
			- Writing the paths of directories
			  collapsed:: true
				- The `/` operator is being used with pathlib-style path concatenation, which is a cleaner alternative to `os.path.join()`
				- Using `pathlib`
					- ```python
					  from pathlib import Path
					  BASE_DIR = Path(__file__).parent
					  AUDIO_FILE = BASE_DIR / "assets" / "audio" / "test.wav"
					  ```
				- Using `os.path`
					- ```python
					  AUDIO_FILE = os.path.join(BASE_DIR, "assets", "audio", "test.wav")
					  ```
				- The `pathlib` version is generally recommended as it's more modern and provides better cross-platform compatibility. It also offers additional path manipulation methods and properties that can be useful for file operations.
			- Python
			- Obtaining the project absolute path methods
			  collapsed:: true
				- NOTE: This has niche utility - instead see "can now import using this syntax" info
				- Examples all assume project base directory is `/`, whilst code is in `src` and config file is in `src/config.py`
				- ```python
				  import os
				  
				  os.path.abspath(__file__)
				  ```
					- - Will tell you the absolute path of the file you're executing
				- ```python
				  import os
				  
				  os.path.dirname(os.path.abspath(__file__))
				  ```
					- This will obtain the path of the directory **the file is in**
					- e.g. `python src/config.py` and `cd src && python config.py` will obtain the same result (e.g. `~/Docs/Project1/src`
					- This is useful if you only want to obtain the base directory of your **variable file**, not of the whole project
				- ```python
				  from pathlib import Path
				  Path(__file__)
				  ```
					- Will tell you the absolute path of the file you're executing
				- ```python
				  from pathlib import Path
				  Path(__file__).resolve().parent
				  ```
					- Would be `src` in this example
				- ```python
				  from pathlib import Path
				  Path(__file__).resolve().parent.parent
				  ```
					- Would be `/` in this example
					- Correct, albeit seems hacky solution
					- To then print an arbitrary filepath:
						- ```python
						  AUDIO_FILE_PATH = "assets/sample-15s.mp3"  
						  BASE_DIR = Path(__file__).resolve().parent.parent
						  
						  print(BASE_DIR / AUDIO_FILE_PATH)
						  ```
						- Or
						  ```python
						  certfile=BASE_DIR / "assets/cert.pem"
						  ```
						- Normally would be `+` operator but `Path` object uses overloading on `/` so that you can use it
				- ```python
				  import os
				  import sys
				  sys.path.append(os.path.dirname(os.path.abspath(__file__)))
				  ```
				- ```python
				  import os
				  import sys
				  sys.path.insert(0, os.path.dirname(os.path.abspath(__file__)))
				  ```
				- ```python
				  BASE_DIR = Path(__file__).resolve().parent.parent
				  sys.path.append(str(BASE_DIR))  # Equivalent to `export PYTHONPATH=$PYTHONPATH:$(pwd)
				  ```
			- ((67cc4979-cb32-41f7-9f5f-4f5c3a6a900b)) and ((654b7053-547c-48ff-9b31-9b6b9dcc5b8f))
			  collapsed:: true
				- [pyproject.toml](https://packaging.python.org/en/latest/guides/writing-pyproject-toml/)
				  id:: 67cc4979-cb32-41f7-9f5f-4f5c3a6a900b
					- Example
						- ```toml
						  [project]
						  name = "example"
						  version = "1.0.0"
						  dependencies = [
						      "numpy",
						      "requests",
						      "jwcrypto",
						      "redis",
						      "setuptools"
						  ]
						  ```
				- `requirements.txt`
				  id:: 654b7053-547c-48ff-9b31-9b6b9dcc5b8f
				  collapsed:: true
					- Allows using `pip install -r requirements.txt` to easily install specific versions of packages
					- Very helpful for maintaining a codebase, especially collaboratively and/or using containerisation
					- Example
						- ```txt
						  flasgger==0.9.7.1
						  Flask==3.0.0
						  pytest==7.4.3
						  ```
				- `pyproject.toml` and `requirements.txt` use together
				  collapsed:: true
					- `pyproject.toml` and `requirements.txt` example on work machine is used in `WebTransport-py` Engineering Desktop repo. Already copied to notes
					- How to use
						- Use a Python virtual environment to install packages into
						- Use `pyproject.toml` to store the exact match version of the top-level dependencies you need
						- Use `pip freeze` to store the exact match version of all dependencies used, including child dependencies
							- James mentioned there's a bug with `pip freeze` in current version, instead have to use this: `python3 -m pip list --format freeze > requirements.txt`
					- Example files
					  collapsed:: true
						- `pyproject.toml`
							- Meta
								- Is meant to mostly replace `requirements.txt` and separate config files for each pip package
								- Can be placed at base of project, whilst code can sit in directories like `src/` and `test/`
							- Examples
								- ```toml
								  [project]
								  ...
								  dependencies = [
								  "requests==2.31.0",
								  "pandas==2.0.3",
								  "pyyaml==6.0.1",
								  "python-dotenv==1.0.0",
								  "sqlalchemy==2.0.19",
								  ]
								  
								  [project.optional-dependencies]
								  dev = [
								  "pytest==7.4.0",
								  "black==23.7.0",
								  "isort==5.12.0",
								  "flake8==6.1.0",
								  "mypy==1.4.1",
								  ]
								  
								  test = [
								  "pytest==7.4.0",
								  "pytest-cov==4.1.0",
								  "pytest-mock==3.11.1",
								  ]
								  ```
								- ```toml
								  [project]
								  name = "app"
								  version = "1.0.0"
								  license = "Proprietary"
								  dependencies = [
								  "pytest = '^6.2.4'",
								  "pyright = '^1.1.171'"
								  ]
								  
								  [tool.ruff]
								  line-length = 88
								  indent-width = 4
								  exclude = [
								  ".pip",
								  ".venv",
								  "__pycache__"
								  ]
								  
								  [tool.ruff.lint]
								  fixable = ["ALL"]
								  select = ["TID252"] # Ban relative imports
								  
								  [tool.ruff.lint.flake8-tidy-imports]
								  ban-relative-imports = "all"
								  
								  [tool.ruff.lint.pydocstyle]
								  convention = "google"
								  
								  [tool.ruff.lint.pycodestyle]
								  max-doc-length = 72
								  
								  [tool.ruff.format]
								  line-ending = "lf"
								  quote-style = "double"
								  indent-style = "space"
								  docstring-code-format = true
								  
								  [tool.pyright]
								  pythonVersion = "3.9"
								  pythonPlatform = "Linux"
								  include = ["src", "tests"]
								  exclude = ["**/*.pyc", "**/__pycache__"]
								  reportMissingImports = "error"
								  reportMissingTypeStubs = false
								  
								  [tool.pyright.ini_options]
								  pythonpath = ["src"]
								  testpaths = ["tests"]
								  asyncio_default_fixture_loop_scope = "function"
								  ```
						- `requirements.txt`
							- ```
							  aioquic==1.2.2
							  flask==3.2.3
							  numpy==6.5.3
							  scipy==7.4.2
							  ```
			- [pipx](https://github.com/pypa/pipx) 
			  collapsed:: true
			  is used to install Python CLI applications globally while still isolating them in virtual environments. pipx will manage upgrades and uninstalls when used to install Poetry.
				- ```shell
				  sudo apt install pipx
				  pipx ensurepath
				  sudo pipx ensurepath --global
				  ```
					- `pipx ensurepath` = This command ensures that the directory where pipx installs executables is included in your system’s PATH environment variable.
					- `sudo pipx ensurepath --global` = To allow pipx actions in global scope. Optional to allow pipx actions with --global argument
				- Built on venv. venv is part of Python's standard library in v3.2+
				- Recommended to install Poetry via pipx
				- Usage
					- `pipx install fanficfare`
					-
				- [Comparison with other tools](https://pipx.pypa.io/stable/comparisons/)
				- Troubleshooting
					- [[2025-05-24 Saturday]] Had to `pipx uninstall x` for each package then `pip install x` again to get `pipx upgrade-all` to work
						- ```
						  $ pipx upgrade-all
						  /home/boss/.local/pipx/venvs/key-mon/bin/python: No module named pip
						  '/home/boss/.local/pipx/venvs/key-mon/bin/python -m pip --no-input install --upgrade key-mon -q' failed
						  /home/boss/.local/pipx/venvs/yt-dlp/bin/python: No module named pip
						  '/home/boss/.local/pipx/venvs/yt-dlp/bin/python -m pip --no-input install --upgrade yt-dlp -q' failed
						  /home/boss/.local/pipx/venvs/ansible/bin/python: No module named pip
						  '/home/boss/.local/pipx/venvs/ansible/bin/python -m pip --no-input install --upgrade ansible -q' failed
						  The following package(s) failed to upgrade: key-mon,yt-dlp,ansible
						  ```
			- [Poetry](https://python-poetry.org/)
			  collapsed:: true
				- Install via `pipx install poetry`
				- A tool for dependency management and packaging in Python. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you. Poetry offers a lockfile to ensure repeatable installs, and can build your project for distribution.
			- [Pyright](https://github.com/microsoft/pyright) - static type checker
			- Python has no parallelism, it can only run one process at a time
			  collapsed:: true
				- It can do concurrency, which is basically context switching
					- Using threads
					- `asyncio` module
						- Asynchronous programming, introduced with Python's asyncio module, enables the execution of tasks that can be paused and resumed without blocking the execution of other tasks. This is particularly useful for I/O-bound tasks where the program can continue executing other tasks while waiting for I/O operations to complete. For example, the following code demonstrates the use of asyncio to download images concurrently:
						- ```python
						  import asyncio
						  
						  async def download_image(url):
						  # Download image code here
						  pass
						  
						  async def main():
						  tasks = [download_image(url) for url in urls]
						  await asyncio.gather(*tasks)
						  
						  asyncio.run(main())
						  ```
				- Each of these methods has its own advantages and is suited to different types of tasks. Threading is best for I/O-bound tasks, multiprocessing is best for CPU-bound tasks, and asynchronous programming is best for tasks that involve waiting for I/O operations to complete.
					- Threading: Allows the execution of multiple threads within a single process, useful for I/O-bound tasks.
					- Multiprocessing: Allows the execution of separate processes, each with its own memory and resources, best for CPU-bound tasks.
					- Asynchronous Programming: Enables the execution of tasks that can be paused and resumed without blocking the execution of other tasks, useful for I/O-bound tasks.
		- My Notes
			- Main guard
			  collapsed:: true
			  AKA entry point guard
				- Syntax
					- ```python
					  def main():
					    	pass
					  # at bottom of script
					  if __name__ == "__main__":
					      main()
					  ```
				- Python’s standard way to define the **entry point** of a script.
				- The `if __name__ == "__main__":` guard ensures the script only runs when executed directly (not when imported as a module).
				- What it does
					- Every Python file (module) has a built-in variable named `__name__`.
					- When a file is **run directly** (for example, `python script.py`),
					- Python sets `__name__` to `"__main__"`.
					- When a file is **imported** from another module,
					- Python sets `__name__` to the module’s name (for example, `"my_module"`).
					- So this conditional means:
					- ```
					  if this file is being run directly, not imported:
					      run main()
					  ```
				- Why it's used
					- It lets the same file act both as:
						- a **standalone script**, when executed directly, and
						- a **module**, that can be imported elsewhere without automatically running its main logic.
			- Directory structure and imports
			  id:: 68e66df0-0f54-44b1-90b6-44769a958927
			  collapsed:: true
				- Imports
				  collapsed:: true
					- Relative
						- Relative imports (like `from .. import device_monitor`) require both directories to be packages (i.e., contain `__init__.py` files) and the test must be run as part of the package, not as a standalone script.
					- Absolute
						- Example
							- ```
							  device-monitoring/
							  │
							  ├── device_monitor.py
							  └── tests/
							      └── test1.py
							  ```
							- Inside `test1.py` add:
							  ```python
							  import device_monitor
							  ```
				- Example
					- ```
					  my_project/
					  ├── pyproject.toml
					  ├── requirements.txt
					  ├── README.md
					  ├── src/
					  │   └── my_project/
					  │       ├── __init__.py
					  │       ├── main.py
					  │       └── utils.py
					  ├── tests/
					  │   ├── conftest.py
					  │   └── test_device_monitor.py
					  ```
						- Imports
							- Inside `test_unit_device_monitor.py`
								- ```python
								  from device_monitor import some_function
								  ```
						- Executing
							- `python -m my_project.device_monitor`
							- `pytest`
								- If you’re using the `src` layout, pytest automatically adds `src/` to `sys.path` if you run from the root.
								- `python3 -m pytest $(realpath $(dirname ${0}))`
									- or `python3 -m pytest`
									- or `python3 -m pytest path/to/test`
						- `pyproject.toml`
							- ```
							  [tool.pytest.ini_options]
							  pythonpath = ["src"]
							  tests = ["tests"]
							  addopts = "-v" # verbose output
							  ```
				- ### What  `__init__.py`  does
					- 🧠 1. It marks a directory as a  **Python package**
						- When Python imports something, it only treats directories **with an `__init__.py`** file as *packages*.
						- Modern Python (3.3+) introduced **namespace packages**, which don’t *require* it — but you should still include one for clarity and compatibility.
					- 2. It can run  **initialization code**
						- `__init__.py` is executed **the first time the package is imported**.
						- You can put setup logic inside it:
							- ```python
							  # src/__init__.py
							  print("Initializing src package")
							  
							  # or define package-wide variables
							  VERSION = "0.1.0"
							  ```
					- 3. It controls  **what gets imported**  with  `from package import *`
						- If you define `__all__`, you can specify which submodules or names are public:
							- ```python
							  # src/__init__.py
							  __all__ = ["device_monitor"]
							  ```
							- Now:
							  ```python
							  from src import *
							  ```
								- only imports `device_monitor`.
					- 4. It enables  **relative imports**  within the package
						- Example structure:
							- ```
							  src/
							  ├── __init__.py
							  ├── device_monitor.py
							  └── utils.py
							  ```
							- Inside `device_monitor.py`:
								- ```python
								  from .utils import helper_function
								  ```
							- That leading `.` (a *relative import*) only works if the directory is a proper package — i.e., has an `__init__.py`.
			- f-strings
			  collapsed:: true
				- https://fstrings.wtf/
					- Try this again, think I mispasted some
					- ```python
					  print(f"{...}") 
					  # Ellipsis
					  ```
						- The three dots are a special object in Python that stringifies as Ellipsis.
					- ```python
					  print(f"{...=}")
					  # ...=Ellipsis
					  ```
						- adding a trailing equals sign lets you print out the expression and what it evaluates to.
					- ```python
					  print(f"{... = }")
					  # ... = Ellipsis
					  ```
						- Whitespace is preserved
					- ```python
					  print(f"{[1,2,3]}")
					  # [1, 2, 3]
					  ```
						- Whitespace is only preserved for the expression, not for the repr of the output. Since lists stringify with whitespace, it looks a bit different.
					- ```python
					  print(f"{{1,2,3}}")
					  # {1,2,3}
					  ```
						- Well isn't that surprising? That's because here we did not actually use a set, instead '{{' and '}}' escape the curly brace.
					- ```python
					  print(f"{1,2,3}")
					  # (1, 2, 3)
					  ```
						- Because the grammar allows an expression here, an implicit tuple expression is assumed and we actually printed the debug repr of a tuple of three items instead.
					- ```python
					  print(f"{ {1,2,3} }")
					  # {1, 2, 3}
					  ```
						- Prints a set
					- ```python
					  print(f"{255:x}")
					  # ff
					  ```
						- The x modifier formats the number as hexadecimal. Note that it does not use the 0x prefix.
					- ```python
					  print(f"{255:c}")
					  # ÿ
					  ```
						- This one converts it into a unicode character which happens to be the character 'ÿ'.
					- id:: 68c98927-b679-47dc-b189-9fcf8c1fefef
					  ```python
					  print(f"{255:#x}")
					  # 0xff
					  ```
						- Alternative formats
						- For integers it will just add the leading 0x to the hexadecimal representation. Similar things are also possible for other formats like octal or binary
					- ```python
					  print(f"{255#x}") # removed `:`
					  # Fails with SyntaxError
					  ```
						- This is in fact a syntax error because the '#' is the beginning of a comment and so 'x}' are part of the comment and our string was never closed!
				- Python, JavaScript, C# allow for lots of string interpolation
				- C++ does not allow for any(?)
				- Related: template literals? or I forget the name, some new Python feature handles some of the functionality from f-strings
				  collapsed:: true
				-
			- Decorators
			  collapsed:: true
				- Class decorators
					- ((68cd70a2-aa4d-4ea8-840b-00fffdcb81ae))
					- `@singleton`
					  collapsed:: true
						- ```python
						  def singleton(cls):
						      instances = {}
						      def get_instance(*args, **kwargs):
						          if cls not in instances:
						              instances[cls] = cls(*args, **kwargs)
						          return instances[cls]
						      return get_instance
						  
						  @singleton
						  class MySingleton:
						      pass
						  
						  a = MySingleton()
						  b = MySingleton()
						  assert a is b   # Both are the same instance
						  ```
					- `@dataclass`
					  collapsed:: true
						- The `@dataclass` decorator in Python is used to **automatically generate boilerplate code** for classes that are mainly used to store data, like your `Point` class
						- Example
							- ```python
							  from dataclasses import dataclass
							  
							  @dataclass
							  class Point:
							      x: int
							      y: int
							  ```
						- What it automatically creates
							- **`__init__`** – a constructor to initialize the fields:
								- Without `@dataclass`, you would write:
								- ```python
								  class Point:
								      def __init__(self, x: int, y: int):
								          self.x = x
								          self.y = y
								  ```
							- **`__repr__`** – a readable string representation of the object:
								- ```python
								  ```
								- Without `@dataclass`, you’d have to write a `__repr__` method manually.
							- **`__eq__`** – comparison between objects:
								- ```python
								  p1 = Point(1, 2)
								  p2 = Point(1, 2)
								  print(p1 == p2)  # True
								  ```
								- Without `@dataclass`, two instances with the same values would not be equal by default.
						- Optional features:
							- `frozen=True` → makes the object **immutable** (like a tuple)
							- `order=True` → generates comparison methods like `<`, `>`, `<=`, `>=` based on the fields
							- `default` or `default_factory` → allows default values for fields
							- Example
								- ```python
								  @dataclass(frozen=True)
								  class Point:
								      x: int
								      y: int
								  ```
									- Now `p.x = 5` would raise an error because the instance is immutable.
				- Method decorators
				  id:: 68d3e6d3-181a-4772-8e2c-46cfe50cc047
					- Meta
						- How to stack multiple different ones to a method
						  collapsed:: true
							- ontop of eachother e.g.
							  ```python
							  @property
							  @abstractmethod
							  def battery_temp(self) -> float:
							    pass
							  ```
					- `@staticmethod`
					- `@classmethod`
					  collapsed:: true
						- ```python
						  @classmethod
						  def connection_state(cls) -> DeviceConnectionState:
						    # Use cls to create or return instance-related data
						    instance = cls()  # you can create an instance here
						    # ... initialize or set up ...
						    return DeviceConnectionState.OFFLINE
						  ```
							- The first parameter `cls` refers to the class itself.
								- In contrast `self` is the first parameter on instance methods as it refers to the class instance itself
							- This allows the method to create a new instance using `cls()` or access class-level attributes.
							- More flexible and preferred for factory methods because it works well with inheritance.
					- `@property`
					  id:: 68d10df3-9cc9-489c-a4a6-f6dbfa72548d
					  collapsed:: true
						- **Purpose**: Turns a method into a property, so it can be accessed like an attribute rather than a function call.[](https://www.geeksforgeeks.org/python/python-property-decorator-property/)
						- **Behavior**: When a method is decorated with `@property`, it can be accessed using attribute syntax (e.g., `obj.attr`), and the method acts as a *getter* for that attribute
						- ```python
						  class Example:
						      @property
						      def value(self):
						          return self._value
						  ```
							- Now, `Example.value` will call the `value()` method to get the underlying `_value` field
					- `@<property_name>.setter`
					  id:: 68d10df3-b57b-4fd8-b8c5-f1d2c1b315bd
					  collapsed:: true
						- **Purpose**: Defines a *setter* for another method/property, allowing assignment to `property-name` using `obj.property-name = ...`.[](https://stackoverflow.com/questions/17330160/how-does-the-property-decorator-work-in-python)
						- **Usage**: This decorator must follow a method with `@property` and use the same name. The setter method receives the value being assigned and can include validation or other logic before setting the underlying attribute.[](https://realpython.com/python-property/)
						- ```python
						  class Example:
						      @property
						      def connection_state(self):
						          return self._state
						  
						      @connection_state.setter
						      def connection_state(self, value):
						          self._state = value
						  ```
						- Now, getting and setting `example.connection_state` invokes custom logic while using simple attribute syntax
					- `@abstractmethod`
					- `@<other_function_name>` - custom decorator
					  collapsed:: true
						- ```python
						  def log_decorator(func):
						      def wrapper(*args, **kwargs):
						          print(f"Calling {func.__name__}")
						          return func(*args, **kwargs)
						      return wrapper
						  
						  class Example:
						      @log_decorator
						      def do(self):  # When called, logs then runs
						          print("Doing work")
						  ```
			- Return type hints
			  collapsed:: true
				- Return type hints in Python are a way to indicate the expected type of the value that a function or method will return. They improve code readability, help with static analysis, and assist tools like IDEs and type checkers (e.g., mypy) in catching errors before runtime
				- Template
					- ```python
					  def function_name(params) -> return_type:
					      # function body
					  ```
				- Example
					- ```python
					  def add(x: int, y: int) -> int:
					      return x + y
					  ```
						- **Return Type Hint**: `-> int` shows this method is expected to return a value of the type `int`
					- Multiple types using `Union` (`|`)
						- ```python
						  def find_user(user_id: int) -> str | None:
						      # returns username or None if not found
						  ```
					- Tuples
						- ```python
						  def get_name_and_age() -> tuple[str, int]:
						      return "Alice", 30
						  ```
			- Scoping
			  collapsed:: true
				- How to change global variables from within functions
					- Example
						- ```python
						  MAX_TEMP = 40.0
						  
						  def func1():
						      global MAX_TEMP
						      MAX_TEMP = 20.0
						  
						  def main():
						      func1()
						      print(MAX_TEMP)
						  
						  if __name__ == "__main__":
						      main()
						  ```
			- Printing objects
			  collapsed:: true
				- Examples
					- ```python
					  print(devices)
					  # {'emulator1': <__main__.AndroidDevice object at 0x7f5432423>}
					  ```
						- This means the first key is `'emulator1'` (a string)
						- The value is an instance of the class called `AndroidDevice`
							- It's a class defined in `__main__`
							- `0x7f5432423` is the memory address where the object lives.
					- Custom function for printing most data types as JSON
						- ```python
						  import json
						  
						  def to_serializable(obj):
						      """Convert objects into something JSON can serialize."""
						      if isinstance(obj, dict):
						          return {k: to_serializable(v) for k, v in obj.items()}
						      elif isinstance(obj, (list, tuple, set)):
						          return [to_serializable(v) for v in obj]
						      elif hasattr(obj, "__dict__"):  # custom object
						          return {k: to_serializable(v) for k, v in vars(obj).items()}
						      else:
						          return obj
						  
						  print(json.dumps(to_serializable(sample_variable), indent=4))
						  ```
				- ```python
				  from pprint import pprint
				  
				  pprint(dir(var_name))
				  ```
				- Related:
					- `dir(var_name)` → shows attributes/methods available on the **data type** of the variable e.g. on a dictionary object
					- `print(type(var_name))` to get the basic data type for the variable
			- Supports ((63fe5474-f771-4530-8f8a-58b55c71204e))
			  collapsed:: true
				- https://docs.python.org/3/library/functools.html#module-functools
				-
			- ### Methods
			  collapsed:: true
				- String
				  collapsed:: true
					- Slicing
					  collapsed:: true
					  #+BEGIN_IMPORTANT
					  This works on lists, tuples, strings, and other sequence types.
					  #+END_IMPORTANT
						- ```
						  sequence[start:stop:step]
						  ```
						- Where:
							- `start` → index to start (inclusive)
							- `stop` → index to end (exclusive)
							- `step` → how many items to skip each time
						- Example
							- ```python
							  nums = [0, 1, 2, 3, 4, 5]
							  print(nums[1:-1:2])  # slice
							  # [1, 3]
							  ```
							- `[1:-1:2]` means:
								- Start at index 1
								- Go up to (but not including) the last index
								- Take every 2nd element
					- `split()`
						- Example
							- ```python
							  lines = ['emulator-5554\tdevice', 'emulator-5556\tdevice']
							  for line in lines:
							      print(line.split('\t')[0])
							  # emulator-5554
							  # emulator-5556
							  ```
					- ((68e52b7a-1ac7-49c1-a5ac-c650bf8e866b))
				- Array
				  collapsed:: true
					- ((68e52b7a-1413-462b-8d71-64c9eed8fbfd))
				- Usecases
				  collapsed:: true
					- Text manipulation
						- Example
							- `lines = result.stdout.strip().splitlines()[1:]`
								- `result.stdout`: Refers to a string, usually standard output captured from running a command.[](https://www.geeksforgeeks.org/python/difference-between-strip-and-split-in-python/)
								- id:: 68e52b7a-1ac7-49c1-a5ac-c650bf8e866b
								  
								  `.strip()`: Removes whitespace (like spaces, tabs, newlines) from the start and end of the string.[](https://www.geeksforgeeks.org/python/difference-between-strip-and-split-in-python/)
								- id:: 68e52b7a-1413-462b-8d71-64c9eed8fbfd
								  
								  `.splitlines()`: Splits the entire string into a list, where each element is a line (split at line break characters like `\n`, `\r`, or both).[](https://www.programiz.com/python-programming/methods/string/splitlines)
								- `[1:]`: Takes all elements from the list except the first one (skips the first line).[](https://www.geeksforgeeks.org/python/python-string-splitlines-method/)
						- Example
							- ```python
							  import re # regex
							  
							  devices = re.split(r'[\n\t]+', devices.stdout)[1:-2:2]
							  ```
			- `continue` keyword
			  collapsed:: true
				- When inside a loop it stops executing the remaining statements for that iteration.
				- It does **not** exit the loop entirely (unlike `break`)
				- Example
					- ```python
					  for i in range(5):
					      if i == 3:
					          continue  # Skip the rest when i == 3
					      print(i)
					  ```
					- Output
					  ```
					  0
					  1
					  2
					  4
					  ```
			- ### Object-Oriented Programming
			  collapsed:: true
				- Python -> TypeScript equivalents
				  collapsed:: true
					- ```python
					  class AndroidDevice(IDevice):
					    def __init__(self, device: ADBDevice):
					      self.__device: ADBDevice = device
					      self.__connection_state = DeviceConnectionState.OFFLINE
					  ```
					- ```typescript
					  class AndroidDevice extends IDevice {
					    private _device: ADBDevice;
					    private _connectionState: DeviceConnectionState;
					  
					    constructor(device: ADBDevice) {
					      super(); // Call base class constructor if needed
					      this._device = device;
					      this._connectionState = DeviceConnectionState.OFFLINE;
					    }
					  }
					  ```
						- `extends` keyword replaces `:` for inheritance.
						- Use `private` to declare private fields (no double underscore convention).
						- Constructor calls `super()` if the parent class has a constructor (required in TypeScript).
						- Fields and types are declared explicitly (e.g., `_device: ADBDevice`).
						- Enum types such as `DeviceConnectionState` are used the same way
				- Making fields "private"
				  collapsed:: true
					- private fields (attributes) are not truly private as in some other languages like Java or C++. Instead, Python uses naming conventions, and ((68d3ebda-bcbc-4a37-afc5-bfc1a3d8afd7)) uses a mechanism called name mangling to provide limited privacy
					- Single underscore prefix `_`
						- This is a convention indicating the attribute is intended for internal use (protected-like), but it **does not prevent access**
						- Example
						  ```python
						  class MyClass:
						      def __init__(self):
						          self._internal_var = 42
						  ```
					- Double underscore prefix `__`
					  id:: 68d3ebda-bcbc-4a37-afc5-bfc1a3d8afd7
						- This triggers **name mangling**: Python changes the attribute name internally to `_ClassName__attrname` to make accidental external access harder.
						- Example
						  ```python
						  class MyClass:
						      def __init__(self):
						          self.__private_var = 42
						  
						  obj = MyClass()
						  print(obj.__private_var)  # AttributeError
						  print(obj._MyClass__private_var) # 42 (can still access, but discouraged)
						  
						  ```
					- ### Property Decorators for Controlled Access
						- To safely expose or control read/write access, use property decorators for getters and setters:
						- Example
						  ```python
						  class MyClass:
						      def __init__(self):
						          self.__private_var = 42
						  
						      @property
						      def private_var(self):
						          return self.__private_var
						  
						      @private_var.setter
						      def private_var(self, value):
						          self.__private_var = value
						  ```
							- Uses ((68d3e6d3-181a-4772-8e2c-46cfe50cc047)) for ((68d10df3-b57b-4fd8-b8c5-f1d2c1b315bd)) + ((68d10df3-9cc9-489c-a4a6-f6dbfa72548d))
					- Related: [[JavaScript]] : ((68d3eb85-cbd4-4105-b72d-07d2c0202607))
				- Basic class which when instantiated will automatically run it's only method
				  collapsed:: true
					- ```python
					  class AutoRunner:
					      def __init__(self):
					          self.run()
					  
					      def run(self):
					          print("Method was automatically run on instantiation!")
					  
					  a = AutoRunner()
					  # Output: Method was automatically run on instantiation!
					  ```
				-
			- Editable install
			  collapsed:: true
			  AKA development mode
				- Basically installs your local project inside your venv, which allows you to easily run it as a module
				- Troubleshooting
					- Offline or corporate network / PyPI mirror
					  collapsed:: true
						- If the isolated build environment can’t reach PyPI (or uses an internal index missing setuptools),
						- you’ll see “no matching distribution found”.
						- **Fix:** Try adding the `--no-build-isolation` flag:
						- ```bash
						  pip install -e . --no-build-isolation
						  ```
						- This reuses your current environment’s setuptools instead of trying to download a new one.
				- [](https://stackoverflow.com/posts/35064498/timeline)
					- As the man page says it:
					- ```
					  -e,--editable <path/url>
					     Install a project in editable mode (i.e.  setuptools "develop mode") from a local project path or a VCS url.
					  ```
					- So you would use this when trying to install a package locally, most often in the case when you are developing it on your system. It will just link the package to the original location, basically meaning any changes to the original package would reflect directly in your environment.
					- Some nuggets around the same [here](http://pip-python3.readthedocs.org/en/latest/reference/pip_install.html#vcs-support) and [here](https://stackoverflow.com/a/20043907/1860929).
					- An example run can be:
					- ```
					  pip install -e .
					  ```
					- or
					- ```
					  pip install -e ~/ultimate-utils/ultimate-utils-proj-src/
					  ```
					- note the second is the full path to where the `setup.py` would be at.
				- [Development Mode a.k.a. “Editable Installs” - setuptools 80.9.0 documentation](https://setuptools.pypa.io/en/latest/userguide/development_mode.html)
				- [What Is an Editable Install? – Python Developer Tooling Handbook](https://pydevtools.com/handbook/explanation/what-is-an-editable-install/)
			- Exceptions
			  collapsed:: true
				- All standard (built-in) exceptions are defined in the **Python standard library**, mainly in the module `builtins`.
					- ```python
					  import builtins
					  print(dir(builtins))
					  ```
					- Output:
					  ```
					  ArithmeticError, AssertionError, AttributeError,
					  ImportError, IndexError, KeyError,
					  TypeError, ValueError, RuntimeError, ...
					  ```
				- How exception classes work
					- Every exception in Python is a **class** that inherits from the built-in `BaseException`.
					- The hierarchy looks like this (simplified):
						- ```
						  BaseException
						   ├── Exception
						   │    ├── ArithmeticError
						   │    ├── LookupError
						   │    ├── ValueError
						   │    ├── RuntimeError
						   │    └── ...
						   └── SystemExit, KeyboardInterrupt, GeneratorExit
						  ```
					- When you raise an error, you’re actually creating an **instance** of one of these classes:
						- ```python
						  raise ValueError("Bad input!")
						  ```
				- How to define your own (custom) errors
					- You can subclass `Exception` (or another subclass) to create your own:
						- ```python
						  class MyCustomError(Exception):
						      """Custom error for my application."""
						      pass
						  ```
					- Then use it like this:
						- ```python
						  def risky_function():
						      raise MyCustomError("Something went wrong!")
						  
						  try:
						      risky_function()
						  except MyCustomError as e:
						      print("Caught:", e)
						  ```
							- Output: `Caught: Something went wrong!`
					- You can also add attributes and logic:
						- ```python
						  class NetworkError(Exception):
						      def __init__(self, code, message):
						          self.code = code
						          super().__init__(f"[{code}] {message}")
						  
						  try:
						      raise NetworkError(404, "Not Found")
						  except NetworkError as err:
						      print(err.code, err)
						  
						  ```
			- Ternary operators and similar
			  collapsed:: true
				- Syntax
					- ```python
					  <value_if_true> if <condition> else <value_if_false>
					  ```
				- Example
					- ```python
					  print('true') if my_variable else print('false')
					  print('true') if my_variable else None
					  ```
				- This syntax is Python’s equivalent of the C / JavaScript ternary operator:
					- ```javascript
					  myvariable ? 'true' : 'false'
					  ```
				- Short-circuiting one-liner (when you don't need `else`)
					- ```python
					  myvariable = True
					  myvariable and print("It is true")  # prints
					  myvariable = False
					  myvariable and print("It is true")  # prints nothing
					  ```
			- `pip.Dockerfile`
			  collapsed:: true
				- The needed dependency needs to be listed in both the `requirements.txt` AND the `pyproject.toml`
				- It'll update both those files in the `out/` dir with the other dependencies required
			- Logging
			  collapsed:: true
				- More professional than print statements, logs to a file though my example lacks timestamps
				- Example
					- v3 - also uses a stream handler so it logs to terminal and not just a file
						- ```python
						  import os
						  import logging
						  import sys
						  
						  
						  def configure_logger():
						      """Create and configure a logger instance."""
						      dev_env = os.getenv("DEV_ENV")
						  
						      logger = logging.getLogger("app")  # shared logger name across modules
						      logger.setLevel(logging.INFO)
						  
						      if not logger.handlers:  # Prevent adding duplicate handlers
						          # Common formatter for all handlers
						          formatter = logging.Formatter(
						              "%(asctime)s [%(levelname)s] %(name)s: %(message)s",
						              datefmt="%Y-%m-%d %H:%M:%S",
						          )
						  
						          if dev_env:
						              # 1️⃣ File handler (writes to app.log)
						              file_handler = logging.FileHandler("app.log")
						              file_handler.setFormatter(formatter)
						              logger.addHandler(file_handler)
						  
						              # 2️⃣ Stream handler (writes to stdout / terminal)
						              stream_handler = logging.StreamHandler(sys.stdout)
						              stream_handler.setFormatter(formatter)
						              logger.addHandler(stream_handler)
						          else:
						              # In production (no DEV_ENV), disable logging
						              null_handler = logging.NullHandler()
						              logger.addHandler(null_handler)
						  
						      return logger
						  
						  
						  # Create a configured logger at import time
						  logger = configure_logger()
						  ```
					- v2 - uses a `configure_logger` function to setup
						- ```python
						  import os
						  import logging
						  
						  def configure_logger():
						      """Configure and return a logger based on DEV_ENV setting."""
						      dev_env = os.getenv("DEV_ENV")
						  
						      if dev_env:
						          # Configure logging only if DEV_ENV is set
						          logging.basicConfig(
						              filename="app.log",
						              level=logging.INFO,
						              format="%(asctime)s [%(levelname)s] %(name)s: %(message)s"
						          )
						          logger = logging.getLogger(__name__)
						      else:
						          # Return a no-op logger (logs are silently ignored)
						          logger = logging.getLogger("null")
						          logger.addHandler(logging.NullHandler())
						  
						      return logger
						  
						  # --- usage ---
						  logger = configure_logger()
						  
						  logger.info("Connecting...")
						  logger.info("Disconnecting...")
						  ```
							- In other files `from mylogger import logger`
					- v1 - uses env statements everywhere
						- ```python
						  import os
						  import logging
						  
						  DEV_ENV = os.getenv('DEV_ENV')
						  
						  if DEV_ENV:
						    logger = logging.getLogger(__name__)
						    logging.basicConfig(filename='app.log', level=logging.INFO)
						  
						  DEV_ENV and logger.info('Hello, world!')
						  DEV_ENV and logger.info('Goodbye, world!')
						  ```
			- Multiple assignment or unpacking
			  collapsed:: true
				- You can assign multiple variables to an array in one line
					- `raw_serial, raw_connection_state = device_notification.split()`
				- Python lets you unpack elements from a collection (like a list, tuple, or the result of a string `.split()`) and assign them simultaneously to multiple variables in one statement, like:
					- Example
					  ```python
					  a, b = [1, 2]
					  x, y = (10, 20)
					  raw_serial, raw_connection_state = device_notification.split()
					  ```
				- You can unpack different data types, not just arrays.
					- Iterables such as tuples, lists, strings, dictionaries, sets,
				- It's often used with functions that return multiple values, or splitting strings into parts.
				- You can use `*` to catch remaining values in a list:
					- ```python
					  a, *rest = [1, 2, 3, 4]  # a=1, rest=[2,3,4]
					  ```
					- Especially useful for variable-length unpacking
			- ### Assorted Notes
			  collapsed:: true
				- [Cython](https://cython.org/) a [superset](https://en.wikipedia.org/wiki/Superset) of the programming language [Python](https://en.wikipedia.org/wiki/Python_(programming_language)), which allows developers to write Python code (with optional, C-inspired syntax extensions) that yields performance comparable to that of [C](https://en.wikipedia.org/wiki/C_(programming_language))
				- Logging
				  collapsed:: true
					- Examples
						- ```python
						  import logging // Python's standard library logging module
						  from logger import LogAdaptor
						  log = LogAdaptor(logging.getLogger(), extra={})
						  ```
							- `logger.py`
							  collapsed:: true
								- ```python
								  import logging
								  
								  LOGGING_CONFIG = {
								  "version": 1,
								  "formatters": {}
								  },
								  "handlers": {
								  "console": {},
								  "file": {},
								  "loggers": {
								  "": {}
								  }
								  // all of these are stubs
								  
								  class LogAdaptor(logging.LoggerAdapter):
								  def process(self, msg, kwargs):
								  if "extra in kwargs: 
								  	msg_id = kwargs.get("extra".get("msgid", None)
								  	if msg_id is not None:
								  		return "(#%s) %s" % (msg_id, msg), kwargs
								  
								  return "%s" % (msg), kwargs							
								  ```
								- This extends the functionality of Python's `logging.LoggerAdapter` class. This class is used to preprocess log messages before they are logged, and it adds an additiona message identifier (`msgid`) to each log entry if such information is availale in the logging context.
									- `process` method is overridden
								- By default `logging` will stream log messages to the terminal
						- `log.info("Running startup checks...")`
						- `log.debug("Configuring Bluetooth adaptor...")`
						- `log.debug("Starting btmon thread...")`
						- `log.error`
						- `log.warn`
					-
				- Switch statement equivalent using pattern matching:
				  collapsed:: true
					- ```python
					  def http_error(status):
					  match status:
					  case 400:
					  	return "Bad request"
					  case 404:
					  	return "Not found"
					  case 418:
					  	return "I'm a teapot"
					  
					  # If an exact match is not confirmed, this last case will be used if provided
					  case _:
					  	return "Something's wrong with the internet"
					  ```
				- Variable naming convention is `snake_case`
				- Variables are block-scoped(?) and work closer to JavaScript `let` rather than `var`
				- Fully Qualified Imports
				  collapsed:: true
					- To share singlton instances across different files in your Python app you should use FQI. This ensures that you are importing objects directly from their module path without creating new instances
					- Example: `from foo.bar import baz; b = baz`
					- Avoid Namespace Imports
						- Example:
							- ```python
							  import foo; b = foo.bar.baz
							  from foo import bar; b = bar.baz
							  ```
				- It's possible to assign multiple variables to the same value (e.g. `None`) using this pattern `var1 = var2 = var3 = None`
				- You can have functions handle arbitrary keyword arguments using `**kwargs`
				  collapsed:: true
					- Example:
					  ```python
					  def output(self, **kwargs):
					  return super().output(**kwargs)
					  ```
				- `super()` function
				  collapsed:: true
					- Used to gain access to methods in a superclass (AKA parent class) that have been overridden in subclasses, without having to know the exact name or signature of the method in the superclass
					- Example:
					  ```python
					  class BaseClass:
					  def some_method(self):
					  # original implementation or initial 
					  pass
					  
					  class SubClass(BaseClass):
					  def some_method(self):
					  result = super().some_method() 
					  # Add additional functionality after
					  return result
					  ```
					- Usecases
						- Allows invoking inherited methods in Python classes, which helps in maintaining and extending existing functonalities without duplicating code
				- `_` prefix for function names is a convention to indicate it's intended for internal use within the class or module. Unlike C# for example there's no way to create a private method
				- Abstract Base Classes (ABCs)
				  collapsed:: true
					- `from abc import ABCMeta, abstractmethod`
					- The `ABCMeta` class is a metaclass that can be used to create ABCs in Python
					- A metaclass is a class of a class, which means it defines how a class behaves and interacts with it's environment, including inheritance, method resolution order, and other aspects of class creation.
					- An abstract class is a class that cannot be instantiated on its own and is meant to be subclassed.
					- `ABCMeta` provides the infrastructure for defining abstract base classes and methods that must be implemented by subclasses.
					- `abstractmethod` is a decorator that can be used to define abstract methods in an ABC. Abstract methods are declared but not implemented, and any subclass of the ABC must provide an implementation for these methods.
						- Alt wording: This is a decorator used to declare methods in an abstract base class as abstract. An abstract method is a method that has no implementation in the base class and must be implemented by any concrete (non-abstract) subclass.
						- By using this metaclass and method, you ensure that derived classes adhere to certain contracts defined by the base class, promoting a design where specific functionality is guaranteed across all implementations of the interface.
					- Example
						- Imagine you are designing a software system where multiple components should implement certain functionalities but must follow a standardised way of doing things. ABCs can be very useful for this purpose.
						- ```python
						  from abc import ABCMeta, abstractmethod
						  
						  class Animal(metaclass=ABCMeta):
						  @abstractmethod
						  def make_sound(self):
						  pass
						  
						  class Dog(Animal):
						  def make_sound(self):
						  return "Woof!"
						  
						  # Now if you try to instantiate an instance of Animal directly, it will raise a TypeError:
						  # >>> my_animal = Animal() # This would cause a TypeError because Animal is abstract and hasn't provided an implementation for make_sound.
						  ```
						- Animal is an ABC that declares an abstract method `make_sound`. Any class inheriting from `Animal` must implement the `make_sound` method. If you try to instantiate an object of a class derived from `Animal` without implementing `make_sound` then Python will raise an error.
				- First parameter of functions within a class are always `self`
				  collapsed:: true
					- This is a convention where `self` represents the instance of the class. It allows the method to access and manipulate its own data and attributes.
				- You can give a function a return type specifier to be `None`, meaning you don't add a `return` or similar
				  collapsed:: true
					- Example
					  ```python
					  def start(self) -> None:
					  print("hello")
					  ```
					- This is called a type hint, which specifies that the function does not return any value (`None`)
				- Factory method pattern
				  collapsed:: true
					- https://python-patterns.guide/gang-of-four/factory-method/
					- Functions that produce objects (incl. functions)
					- https://en.wikipedia.org/wiki/Factory_(object-oriented_programming)
					- https://refactoring.guru/design-patterns/factory-method
					- Example
						- ```python
						    def func1(): 
						  return "Hello" 
						  def func2(): 
						  return "World" 
						  
						  def factoryFunc(a): 
						  if a==1: 
						  	return func1 
						  if a==2: 
						  	return func2 
						  ```
				- Wheels
				  id:: 67a8e143-856e-4949-bd93-4c62cfe7ee1c
				  collapsed:: true
					- are interesting concept in Python [What Are Python Wheels and Why Should You Care? – Real Python](https://realpython.com/python-wheels/)
					- Getting Python wheel files
					  collapsed:: true
						- Assuming this directory structure:
							- ```
							  Root dir:
							  - output/
							  - Dockerfile.pip
							  - requirements.txt
							  ```
						- Run: `docker build --no-cavche --file Dockerfile.pip --output output .`
						- `Dockerfile.pip`
							- ```
							  FROM python:3.11-slim AS build
							  
							  WORKDIR /deps
							  
							  COPY requirements.txt .
							  
							  RUN python3 -m pip download --requirement requirements.txt --dest .pip
							  
							  RUN tar -czf .pip.tar.gz \
							    --mtime='UTC 1970-01-01' \
							    --sort='name' \
							    --owner=0 \
							    --group=0 \
							    --mode=774 \
							    -C .pip \
							    .
							  RUN sha256sum .pip/* | sort > .pipsha256
							  
							  FROM scratch
							  COPY --from=build /deps/.pip.tar.gz /deps/requirements.txt /deps/.pip.sha256 /
							  ```
					-
				- `if __name__ == "__main__":` pattern
				  collapsed:: true
				  Ensuring code only runs when script is executed, not when it's imported
					- This ensures all code within only runs when the script is executed directly, rather than when it's imported as a module in another script.
						- Usecases:
							- Testing - debug statements or testing code can be stored here, but it's not meant to be executed when the module is imported by other scripts.
					- Should use this in `main.py` only if at all
					- `__name__` = Every Python module has a built-in attribute called `__name__`. When the module is run directly, `__name__` is set to `"__main__"`. If the module is imported into another module, `__name__` is set to the name of the module.
					- `"__main__"` = This string literal is used as a convention to identify the main block of code in a script.
					- Example usage
						- ```python
						  # src/main.py`
						  def main():
						  print("This code will only run")
						  
						  if __name__ == "__main__":
						  main()
						  ```
						- `main()` will only be called when the script is run directly (`python scr/main.py`). If you import this module in another Python file, nothing inside it will execute because `__name__` would not be equal to `"__main__"` and thus the function `main()` would not be called.
				- Classes
				  collapsed:: true
					- You can have classes [inherit](https://docs.python.org/3/tutorial/classes.html#inheritance) from other classes
						- ```python
						  # class Dog:
						  class Dog(Animal):
						  ```
					- `def __init__():` is usually the first method in a class. It's a constructor that can be used to initialise variables
						- Example:
						  ```python
						  class Dog(Animal):
						  def __init__(self, rx: Queue, tx: Queue, turn_config: TURNConfig):
						  self.webrtc_proc: multiprocessing.Process
						  self.direction = WebRTCDirection("sendonly")
						  self
						  
						  super().__init__(Component.AUDIO, target=asyncio.run)
						  ```
						- `super()__init__()` = used to also initialise the superclass (parent class) Animal with it's own parameters
					- Class methods require `self` as the first parameter
						- https://pythontips.com/2013/08/07/the-self-variable-in-python-explained/
							- The first argument of every class method, including init, is always a reference to the current instance of the class. By convention, this argument is always named self. In the init method, self refers to the newly created object; in other class methods, it refers to the instance whose method was called
					- `@dataclass` decorator
						- This module generates special methods for classes such as `__init__`, `__repr__` and `__eq__`, based on the class attributes defined
						- Benefits
							- This allows you to easily create data-holding classes without having to write the boilerplate code for those class methods.
							- Simpler - easier to read and maintain these classes
							- Automatic Type Checking
							- Allows you to specify default values directly in the class definition
						- Example
							- ```python
							  from dataclasses import dataclass
							  
							  @dataclass
							  class Point:
							  x: int
							  y: int
							  z: int = 0 # default value
							  
							  p = Point(1, 2)
							  ```
								- `@dataclass` is applied to the class definition
								- The attributes `x`, `y` and `z` are defined with types.
								- An optional default value is specified for `z`.
								- When you create an instance of Point (e.g. `p = Point(1, 2)`) the constructor is automatically generated to initialise these attributes based on the provided arguments.
								- The string representation `__repr__` and the equality check `__eq__` are handled by default when using `@dataclass`.
				- Function decorators
				  collapsed:: true
					- They're a way to modify or extend the behaviour of functions without changing their source code
					- They're essentially higher-order functions that take another function and return a new function, often extending the original function's behaviour through composition. Decorators allow you to wrap a function with another functionality, providing flexibility and reuse of code.
					- Example
						- ```python
						  def my_decorator(func):
						  def wrapper(*args, **kwargs):
						  print("Function is blah")
						  result = func(*args, **kwargs)
						  return result
						  return wrapper
						  
						  @decorator_function
						  def my_function():
						  print("Hello, World!")
						  
						  say_hello()
						  ```
						- `my_function` will be passed as an argument to `decorator_function`, and it's return value (which should be a new function) will replace the original definition of `my_function`.
						- Usage:
						  When you call `say_hello()`, it actually calls `wrapper()` from `my_decorator`. Before executing the original `say_hello` function, `wrapper` prints a message indicating that the function is about to be called. After execution of `say_hello`, `wrapper` returns whatever value `say_hello` returned.
					- Benefits
						- Reusability - can reuse decorators on multiple functions
						- Extensibility - can add new functionity to a function such as logging, timing or access control
					- Usecases
						- Django frequently uses `@login_required` decorator for authentication, `@logged` to log method calls, `@timed` to measure execution time of functions
					- Python includes several built-in decorators like `property`, `staticmethod`, `classmethod`
				- Type Annotations
				  collapsed:: true
					- Examples
						- ```python
						  msg: QueueMessage
						  webrtc_msg: Union[SessionDescription, WebRTCConnectionState]
						  ```
						- `msg` is typed as `QueueMessage`, which means it'll check it has the correct attributes and methods associated with this type.
						- `webrtc_msg` is typed as a union of two types, which means it can be either one of these two types
				- `async`/`await`
				  id:: 67a8e143-a149-4f73-8207-169e5ad364d2
				  collapsed:: true
					- Subroutines are blocks of code in Python designed to perform specific tasks. They are categorized into two main types: functions and methods.
						- They are entered at one point and exited at another point.
					- Callbacks
						- A subroutine function which is passed as an argument to be executed at some point in the future.
					- [Coroutines](https://docs.python.org/3/glossary.html#term-coroutine) can be entered, exited and resumed at many different points, unlike subroutines. They are implemented via `async def`.
					- Can't execute an async function just by calling it, need to either:
						- Use the [`asyncio.run()` method](https://docs.python.org/3/library/asyncio-runner.html#asyncio.run) e.g. `
						- [Or any of these](https://docs.python.org/3/library/asyncio-task.html#id2)
					- The `await` keyword is used within coroutines to pause execution until an asynchronous operation completes.
				- [`pass` statement](https://docs.python.org/3/reference/simple_stmts.html#the-pass-statement)
				  collapsed:: true
					- It's a null operation — when it is executed, nothing happens. It is useful as a placeholder when a statement is required syntactically, but no code needs to be executed
					- For example an empty function or class
				- `try` statement
				  collapsed:: true
					- Can be used to [handle exceptions](https://docs.python.org/3/tutorial/errors.html#handling-exceptions)
					- [Exceptions](https://docs.python.org/3/library/exceptions.html) AKA logical errors, are separate from syntax errors
					- Example of how to catch all exceptions:
						- ```python
						  try:
						  whatever()
						  except Exception as e:
						  logging.error(traceback.format_exc())
						  ```
						- This catches more exception types than just a bare `except:`
					- [`except` clause](https://docs.python.org/3/reference/compound_stmts.html#except-clause)
						- `as` can be used to assign the error
							- Example:
								- ```python
								  try: 
								  function1()
								  except Exception as E:
								  function2(E)
								  ```
				- Imports
				  collapsed:: true
					- `import` = Python's standard library, third-party libraries
					- `from` = to import modules from standard library, third-party libs or your custom libs
						- Examples
							- `from AudioStreamHandler import AudioStreamHandlerClass` assuming `AudioStreamHandler.py` exists at the same level and that there's a class named `AudioStreamHandlerClass` within it
							- `from queue import Empty, Queue`
				- Managing development environments
				  collapsed:: true
					- Using virtual environments for each Python project
						- `python -m venv <env-name>`
							- `python -m venv .venv` is the convention
							  id:: 67a8e143-e71f-446e-8c6a-46c4a1310084
						- `source env/bin/activate` to start the virtual environment
						- `deactivate` to exit the virtual environment
					- `venv`
					  [[2025-02-22 Saturday]] What I'm using at work
					- Poetry
					- `conda`
					- Docker
					- pipenv
					- virtualenv
				- Looping backwards
				  id:: 66be2e28-8809-49b5-a5f2-853321eec973
				  collapsed:: true
					- ((65db1e62-be7f-411d-b0a2-da3027dd6c7e)) : ((66be2eed-c138-44c9-8cad-def9bf88a376))
					- ((663a579f-a6ac-4bc6-a2a9-05d3031ea2f1)) : ((66be2f9b-6fa5-42f3-9a07-092ba50ada7f))
					- Slicing
						- ```python
						  if __name__ == '__main__':
						   
						      # print numbers from 1 to 10 in reverse order
						      for i in range(1, 11)[::-1]:
						          print(i)
						  ```
					- Related: ((65d89c40-b7d3-412b-a6cc-dbcc033d73ee))
				- Global variables
				  collapsed:: true
					- You need to specify a variable as being `global` when you use it during a locally-scoped function, otherwise it'll create new local ones
					- Example
						- ```python
						  bucket = ""
						  key = ""
						  
						  def receive_message():
						    global bucket, key # If this line isn't included then it'll create new locally-scoped vars
						  
						    bucket = "bucket name"
						    key = "dw92mdwaa"
						  ```
				- F-strings
				  id:: 65b388c7-41fd-4365-af05-b65a77ccf2f8
				  collapsed:: true
					- formatted strings
						- `print(f"Test using {len(VAR_NUMBER_OF_ITEMS)} items")`
					- e.g. `f"Hello {your_name}, welcome"`
					- Introduced in Python 3.6, it's a concise and convenient way to embed expressions inside string literals. String interpolation?
					- Example
						- ```python
						  print(f"Error processing file in-memory: {e}")
						  ```
							- `e` being a variable already declared beforehand e.g. `e = "test"`
							-
						- ((642714a5-1d61-4067-a9fd-87d003c13a07)) : ((65b38f28-ea69-4c1f-a162-1f62f3aa1726))
				- How to use an environment variable, with hardcoded value fallback
				  collapsed:: true
					- Example
						- ```python
						  # First value is the env var, second is the fallback hardcoded value
						  queue_url = os.environ.get(
						  	"SQS_URL",
						    	"https://sqs.eu-west-1.amazonaws.com/325723532/test"
						  )
						  ```
				- Decorators
				  collapsed:: true
					- Class decorators
						- `unique` is a class decorator for Enum that raises a ValueError if there are any duplicate enumeration values.
							- This code
							- ```python
							  from enum import unique, Enum
							  
							  @unique
							  class Mistake(Enum):
							      ONE = 1
							      TWO = 2
							      THREE = 3
							      FOUR = 3
							  ```
							- Produces this error:
							  ```
							  ValueError: duplicate values found in <enum 'Mistake'>: FOUR -> THREE
							  ```
							- [Enum docs](https://docs.python.org/3/library/enum.html)
					- Method decorators
						- `@property` class method decorator
						  collapsed:: true
							- ```python
							  class Celsius:
							      def __init__(self, temperature=0):
							          self._temperature = temperature
							  
							      @property
							      def temperature(self):
							          return self._temperature
							  
							      @temperature.setter
							      def temperature(self, value):
							          if value < -273:
							              raise ValueError("Temperature below -273 is not possible")
							          self._temperature = value
							  
							      @temperature.deleter
							      def temperature(self):
							          print("Deleting temperature...")
							          del self._temperature
							  
							  # Usage:
							  c = Celsius(25)
							  print(c.temperature)  # Accesses via getter, prints 25
							  c.temperature = 30    # Sets via setter
							  # c.temperature = -300 # Raises ValueError
							  del c.temperature     # Calls the deleter
							  ```
							- Explicit methods (without `@property`)
								- ```python
								  class Celsius:
								      def __init__(self, temperature=0):
								          self._temperature = temperature
								  
								      def get_temperature(self):
								          return self._temperature
								  
								      def set_temperature(self, value):
								          if value < -273:
								              raise ValueError("Temperature below -273 is not possible")
								          self._temperature = value
								  
								      def del_temperature(self):
								          print("Deleting temperature...")
								          del self._temperature
								  
								  # Usage:
								  c = Celsius(25)
								  print(c.get_temperature())  # Access via explicit getter
								  c.set_temperature(30)       # Set via explicit setter
								  # c.set_temperature(-300)   # Raises ValueError
								  c.del_temperature()         # Delete explicitly
								  ```
							- Explanation
								- Without @property, users must call methods explicitly (e.g., get_temperature() instead of c.temperature).
								- This makes the interface less Pythonic and less intuitive.
								- It burdens the client code and makes refactoring harder if the implementation changes (e.g., switching from direct attribute to calculated property).
								- Using @property hides this boilerplate and provides a clean attribute-like syntax with encapsulation and validation.
							- Summary:
								- The @property decorator wraps getter/setter/deleter methods so they behave like attributes, improving readability and usability. Without it, explicit method calls are needed, which is more verbose and less idiomatic in Python.
								- You can use multiple `@property` for class methods if there are different methods for each getter
				- [Type annotations](https://typing.python.org/en/latest/spec/annotations.html), similar to TypeScript
				  collapsed:: true
					- ```python
					  def greeting(name: str) -> str:
					      return 'Hello ' + name
					  ```the expected type of the name argument is `str`. Analogically, the expected return type is `str`
				- How to specify types for parameters
				  collapsed:: true
					- ```python
					  def handler(
					      host: str,
					      port: int,
					      instance: special.host.Event
					  ):
					      return "blah"
					  ```
				- Python classes and abstract base classes
				  collapsed:: true
					- ```python
					  from abc import ABC, abstractmethod
					  
					  class IDevice(ABC):
					  	@abstractmethod
					  	def battery_temperature(self) -> float:
					  	"""
					  	Retrieve the battery temperature of the target device in degrees celsius.
					  
					  	Returns:
					  		float: The battery temperature of the target device.
					  	"""
					  	
					  	pass
					  
					  class AndroidDevice(IDevice):
					  	def __init__(self, device: ADBDevice):
					  		self.__device: ADBDevice = device
					  		self.__connection_state = DeviceConnectionState.OFFLINE
					  	
					  	def battery_temperature(self) -> float:
					  	temperature = float(int(self.__device.shell("dumpsys battery get temp")) / 10)
					  	return temperature
					  
					  def main():
					  	pass
					  
					  if __name__ == "__main__":
					  	main()
					  ```
				- Encapsulation
				  collapsed:: true
					- Uses double underscores (__device, __connection_state) for private attributes.
					- These attributes are name-mangled to prevent accidental access and to signify they're intended for internal use.
					- Example: `self.__device: ADBDevice = device`
						- Double underscore `__` prefix in attribute names triggers name mangling: Python internally renames such attributes to include the class name (e.g., `self.__device` becomes `_AndroidDevice__device`). This makes it harder to accidentally access or modify these attributes from outside the class or from subclasses, serving as a form of privacy.
					- Example
						- ```python
						  class Car:
						    def __init__(self):
						        self.__maxspeed = 200  # double underscore triggers name mangling
						    
						    def drive(self):
						        print(f'Max speed is {self.__maxspeed}')
						        
						  my_car = Car()
						  print(my_car.__maxspeed)  # Raises AttributeError
						  print(my_car._Car__maxspeed)  # Prints: 200
						  ```
					- A better design is to provide a getter method. This preserves encapsulation but lets clients access the value safely. For example:
						- ```python
						  class Car:
						    def __init__(self):
						        self.__maxspeed = 200
						    
						    def get_maxspeed(self):
						        return self.__maxspeed
						  - my_car = Car()
						  print(my_car.get_maxspeed())  # Prints: 200
						  ```
				- Main Entry Point Idiom
				  collapsed:: true
					- ```python
					  def main():
					    pass
					  if __name__ == "__main__":
					    main()
					  ```
					- This is a Python convention to distinguish code that runs when the script is executed directly vs. when it is imported as a module[general knowledge].
				- `for...in` loops
				- asyncio vs threading vs multiprocessing in Python [Perplexity](https://www.perplexity.ai/search/explain-running-adb-reverse-lo-RxrXHLzjSRGZuOt_v8AQsQ?18=d#79)
				  collapsed:: true
					- [Thread (computing) - Wikipedia](https://en.wikipedia.org/wiki/Thread_(computing)) multiple threads can be components of a single process, each managed independently by a scheduler. They may be executed concurrently via multithreading
					- [Threading](https://docs.python.org/3/library/threading.html)
					- Example utilising `argparse` and `threading`
						- ```python
						  import threading
						  import argparse
						  
						  def main(): 
						  	parser = argparse.ArgumentParser(description="Gather maximum temperature")
						  	parser.add_argument('MAX_TEMPERATURE_SPECIFIED', nargs='*', help= "Float representation of celsius temperature")
						  	args = arser.parse_args()
						  	MAX_TEMPERATURE_CELSIUS = 40.0
						  	if len(args.MAX_TEMPRATURE_SPECIFIED) ==1:
						  		try:
						  			MAX_TEMPERATURE_CELSIUS = float(args.MAX_TEMPERATURE_SPECIFIED[0])
						  		except:
						  			pass
						  
						  	device_manager = DeviceManager()
						  	temperature_thread = threading.Thread(
						  		target = device_manager.monitor_battery_temperatures(MAX_TEMPERATURE_CELSIUS),
						  		args = [],
						  		daemon = True
						  	)
						  	device_amount = len(device_manager.devices_by_serial.values())
						  	temperature_thread.start()
						  	stop_threads = threading.Event()
						  	stop_threads.clear()
						  	while True: # Needed to keep threads alive, if main ends thread dies
						  		time.sleep(10)
						  		if (len(device_manager.devices_by_serial.values()) != device_amount):
						  			print("New devices detected please wait whilst they are registered")
						  			break # Kill main therefore kill threads therefore systemd restart with new device context
						  		else:
						  			pass
						  
						  # Example utilisation:
						  # python3 device_monitor.py   # 40C default
						  # python3 device_monitor.py 30    # 30C custom
						  ```
							- Tips:
								- Use `nargs='?'` for optional single argument instead of `nargs='*'`
								- Alternative `while` loop:
									- ```python
									    while not stop_threads.is_set():
									        # Use event wait to sleep efficiently and allow early wakeup if needed
									        stopped_early = stop_threads.wait(10)
									        if stopped_early:
									            break
									        if len(device_manager.devices_by_serial.values()) != device_amount:
									            print("New devices detected please wait whilst they are registered")
									            break
									  ```
									- Why:
										- Infinite Loop & Thread Coordination
										- The infinite while True loop is a crude way to keep the main thread alive, relying on break to exit.
										- This could consume unnecessary CPU or delay shutdown. Consider using `threading.Event` or other synchronization primitives.
										- Explanation of Fix for #5:
											- The infinite while True loop is replaced by while not stop_threads.is_set() which listens on the stop_threads event.
											- Instead of time.sleep(), stop_threads.wait(timeout) is used. This waits for either the event to be set or the timeout to elapse, allowing more responsive thread coordination.
											- The loop breaks as before when device count changes.
											- This avoids unnecessary CPU wakeups and provides a mechanism (stop_threads.set()) to trigger early exit cleanly if needed later.
					- A typical use case for threading includes managing a pool of worker threads that can process multiple tasks concurrently. Here’s a basic example of creating and starting threads using Thread:
						- ```python
						  import threading
						  import time
						  
						  def crawl(link, delay=3):
						    print(f"crawl started for {link}")
						    time.sleep(delay)  # Blocking I/O (simulating a network request)
						    print(f"crawl ended for {link}")
						  
						  links = [
						    "https://python.org",
						    "https://docs.python.org",
						    "https://peps.python.org",
						  ]
						  
						  # Start threads for each link
						  threads = []
						  for link in links:
						    # Using `args` to pass positional arguments and `kwargs` for keyword arguments
						    t = threading.Thread(target=crawl, args=(link,), kwargs={"delay": 2})
						    threads.append(t)
						  
						  # Start each thread
						  for t in threads:
						    t.start()
						  
						  # Wait for all threads to finish
						  for t in threads:
						    t.join()
						  ```
				- Event example [Perplexity](https://www.perplexity.ai/search/explain-running-adb-reverse-lo-RxrXHLzjSRGZuOt_v8AQsQ?18=d#83)
				- Python allows easily running a test HTTP server
				  collapsed:: true
					- `python3 -m venv .venv` whilst in a directory you want to share
					- `source .venv/bin/activate` to go into the venv
					- `python3 -m http.server` to host a server
					- You should then be able to access your working directory at http://localhost:8000 by default
				- Tuples syntax
				  collapsed:: true
					- Examples
						- `odd_numbers = (1, 3, 5, 7, 9)`
						- `(host, port)`
					- They're basically immutable lists
				- "Dunder" methods
				  collapsed:: true
					- The term "dunder" most commonly refers to the double underscore (__) characters used in Python to denote special methods, also known as "magic" or "dunder" methods. These methods, such as __init__, __str__, and __eq__, are automatically invoked by the Python interpreter in response to specific operations or events, like object creation or comparison. They act as a contract between the class developer and the Python interpreter, allowing user-defined objects to integrate seamlessly with built-in functions and operators. The name "dunder" is derived from "double underscore," reflecting the naming convention of these methods.
			- ### Quirks
				- Python buffers `stdout`/`stderr` by default
				  collapsed:: true
					- When running a PyInstaller-created Python binary as a systemd service, **print statements may not show up in the logs because Python's output is buffered by default**. This buffering means your print output is held in a buffer and not immediately flushed to stdout/stderr, which systemd captures for journaling.
					- Why print doesn't show up:
						- Python buffers stdout/stderr by default.
						- Systemd journal captures output from these streams.
						- Buffered output may be delayed or lost when the service stops or is interrupted.
					- Solution
						- Flush stdout after each print in your Python script, e.g.:
							- ```python
							  import sys
							  print("Message")
							  sys.stdout.flush()
							  ```
						- Optional - this didn't seem necessary in my testing [[2025-09-25 Thursday]]
							- Run Python in unbuffered mode in the service file:
								- If using a Python script
								  ```
								  ExecStart=/path/to/your/script.py -u
								  ```
								- If using a PyInstaller-created Python binary
								  ```
								  [Service]
								  Environment=PYTHONUNBUFFERED=1
								  ExecStart=/path/to/your/binary
								  ```
				- Unlike [[JavaScript]] which has `null` and `undefined` as falsy values, Python only has `None`
				  collapsed:: true
					- `return` without a return value is equivalent to `return None`
						- In JavaScript, a function without a return value yields `undefined`.
							- So conceptually, **Python’s `None` ≈ JavaScript’s `undefined`** (though they’re not interchangeable — Python has no `undefined` keyword).
					- Python’s `None` is *closer* to JavaScript’s `null`, not `undefined`
						- `None`/`null` both represent *“nothing here, intentionally”*
					- Python has **no equivalent** to JavaScript’s `undefined`
						- `undefined` means “this variable *exists*, but has never been assigned a value.”
						- If you try to access an unassigned variable, Python raises a **NameError**:
		- Learning resource sorted by priority
		  id:: e55a0ae7-6227-46f4-8ca2-fdb031227292
			- [Learn Python 3 | Codecademy](https://www.codecademy.com/courses/learn-python-3)
			  id:: cfc36ba4-077e-4c24-b372-fd0d6ea9bdd8
			  collapsed:: true
			  Recommended by Sophie Thornton (BAE LDN/School of Code)
				- Meta
					- ### Community
					  collapsed:: true
						- Learning to code is challenging, but it’s easier if you can team up. Ask questions, stay connected, and find motivation with multiple communal experiences through Codecademy:
						- [Community forum](https://discuss.codecademy.com/): ask and answer questions about anything on Codecademy.
						- [Discord](https://discord.com/invite/codecademy): chat in real-time with other learners across the globe.
						- [Chapters](https://community.codecademy.com/): find like-minded people in your area and learn to code together. Thereare even multiple virtual-first groups to join if you don’t find one nearby.
						- [Facebook group](https://www.facebook.com/groups/codecademy.community/): discuss the broader world of coding with tens of thousands of other learners.
						- [30-Day Challenge](https://www.codecademy.com/30daychallenge): join others in a sprint to make progress and make learning a habit.
				- # Hello World
				  collapsed:: true
				  
				  collapsed:: true
					- ## Hello World
						- `print()`
						  id:: 65e0444c-9e62-48e3-9dbc-692b48eb27bd
						  collapsed:: true
						  Prints value to the console
							- ```python
							  my_name = "Codecademy"
							  print("Hello and welcome " + my_name + "!")
							  ```
							- Related: ((642714a5-1d61-4067-a9fd-87d003c13a07)) : ((661ae022-4f35-4905-821b-946824c60399))
						- Initialising a variable doesn't need `var` infront of it
						  collapsed:: true
							- e.g.
							  ```python
							  my_name = "Codecademy"
							  ```
						- Semi-colons don't seem to be used, unlike [[JavaScript]]
						- `#` and `'''`is used for comments, unlike [[JavaScript]] : ((646349ae-f6ad-4d1e-a2d5-8e9caa13af70))
						  collapsed:: true
							- Examples
								- ```python
								  # This is a single-line comment in Python
								  
								  '''
								  This is a
								  multi-line comment
								  in Python
								  '''
								  ```
						- Like [[JavaScript]], can use `"` or `'` for strings. You can escape characters using `\`
						- **Variables**
							- Variables can't begin with a number, and the only allowed symbol is `_`
							- ```python
							  message_string = "Hello there"
							  # Prints "Hello there"
							  print(message_string)
							  ```
						- **Errors**
							- Two types of errors: syntax errors and exceptions
							- Two common errors: `SyntaxError` and `NameError`
								- `SyntaxError`
									- means there is something wrong with the way your program is written — punctuation that does not belong, a command where it is not expected, or
									  a missing parenthesis can all trigger a `SyntaxError`.
								- `NameError`
									- occurs when the Python interpreter sees a word it does not recognize. Code that contains something that looks like a variable but was never defined will throw a `NameError`.
						- **Numbers**
							- `int` AKA integer = a whole number
							- `float` AKA floating-point number = a decimal number
								- [Python’s documentation on floating-point limitations](https://docs.python.org/3/tutorial/floatingpoint.html).
							- Literal = a value which is not a variable
								- Example: `print(var1 + 3)`
									- 3 is a literal because it's the integer `3` and not a variable with the number 3 assigned to it
						- **Calculations**
							- ```python
							  # Prints "2.0"
							  print(10 / 5)
							  ```
								- Notice that when we perform division, the result has a decimal place. This is because Python converts all `int`s to `float`s before performing division
							- Mathematical operations in Python follow the standard mathematical ((65d4f537-1a1c-4df6-9305-4b70aacbc0c2))
						- ((65d50428-aecf-445e-b34c-d057af1304f9))
						- ((65d50b2d-a4bb-450f-a1a4-4f89dbe58909)) e.g. ((65d50b2d-0218-44f6-b846-780f44c83035))
						- **Multi-line Strings**
							- three quote-marks (`"""` or `'''`)
							- Example
								- ```python
								  leaves_of_grass = """
								  Poets to come! orators, singers, musicians to come!
								  Not to-day is to justify me and answer what I am for,
								  But you, a new brood, native, athletic, continental, greater than
								    before known,
								  Arouse! for you must justify me.
								  """
								  ```
							- If a multi-line string isn’t assigned a variable or used in an expression it is treated as a comment.
							- Related: [[JavaScript]] : ((65b39269-8f46-4d62-9ed1-bcd18e2765ba))
					- User Input
						- `input()` can be used to assign data to a variable using a prompt message
							- e.g.
							  ```python
							  likes_snakes = input("Do you like snakes? ")
							  ```
				- # Control Flow
				  collapsed:: true
					- ## Control Flow
						- Example image
						  collapsed:: true
							- ![image.png](../assets/image_1708795285841_0.png)
						- Control Flow includes the conditional statements that tells the computer whether or not to execute certain blocks of code
						- **Boolean Expressions**
							- True/False is set as `False` or `True` (note the capitalisation)
						- **Relational Operators**
						  AKA ((65d89c40-7642-4d2d-a9d6-f9cc38fac471))
						- **Boolean Variables**
							- You can set variables to `True` or `False`
							- You can also set them to a boolean by using ((65d89c40-7642-4d2d-a9d6-f9cc38fac471))
								- Examples
									- ```python
									  bool_one = 5 != 7 # True
									  bool_two = 1 + 1 != 2 # False
									  bool_three = 3 * 3 == 9 # True
									  ```
						- ((65db1e62-25b6-4a28-a77a-e687d257e100))
						- Booleans are building blocks of ((65d89c40-28e7-4eab-891e-9ea5d44e8d05)) and thus of control flow
						- Boolean Operators
						  AKA ((65d89c40-e967-456c-8274-451ef31462e2))
						- ((65d89c40-28e7-4eab-891e-9ea5d44e8d05)) e.g. ((3724a989-a497-468a-b17d-ab7f05de0af6))
					- ## Magic 8-Ball
						- ((65db64bc-91d6-4bef-af12-d0e30aa637ec)) : ((2c036eaa-7495-44d3-9b78-b267a49b0350))
					- ## Sal's Shipping
					- ## Errors in Python
						- ((65d89c40-28e0-4abb-bcfa-01687608a1ef))
				- # Lists
				  collapsed:: true
				  
				  collapsed:: true
					- ## Introduction to Lists
						- ((65d89c40-5e6f-4b12-b1cc-5d93e2b320cc))
						- ((65db6f46-9518-4bf2-ac3e-7ab95a0207c0))
						- `+` can be used to concatenate two lists:
							- ```python
							  items_sold = ["cake", "cookie", "bread"]
							  items_sold_new = items_sold + ["biscuit", "tart"]
							  print(items_sold_new)
							  # Prints ['cake', 'cookie', 'bread', 'biscuit', 'tart']
							  ```
						- Accessing List Elements (using bracket notation)
						  id:: 65db7226-ce4e-44bc-81dc-92c400d2765d
							- ```python
							  calls = ["Juan", "Zofia", "Amare", "Ezio", "Ananya"]
							  print(calls[2]) # Amare
							  ```
							- Negative index can be used to access the last element backwards
								- `-1` is the last
									- id:: 65db7c8f-721a-47e0-8448-06df499b98d1
									  ```python
									  pancake_recipe = ["eggs", "flour", "butter", "milk", "sugar", "love"]
									  print(pancake_recipe[-1]) # love
									  ```
								- `-2` is second last, etc
						- ((65db6f73-6378-4c36-8946-62803f98824f))
						- ### Two-Dimensional (2D) Lists
							- Example
								- ```python
								  heights = [["Jenny", 61], ["Alexus", 70], ["Sam", 67], ["Grace", 64]]
								  
								  tic_tac_toe = [
								              ["X","O","X"],
								              ["O","X","O"],
								              ["O","O","X"]
								  ]
								  ```
					- ## Gradebook
					- ## Working with Lists in Python
						- ((65db6f41-c061-4796-8542-1b1a66dfe81d))
							- {{embed ((65db6f41-c061-4796-8542-1b1a66dfe81d))}}
						- ((65db1e62-50fc-441b-94c9-c70aeca3a724))
						- ((65db1e62-be7f-411d-b0a2-da3027dd6c7e))
						- ((65db1e62-4930-4a89-8f9d-287d53fa4686))
						- ^^Skipped all content because I've already covered this in JavaScript^^
					- ## Working with Lists in Python
						- `mylist[-3:]` selects the last 3 items in a list
						- Slicing can be done via e.g.
						  ```python
						  mylist = ["a", "b", "c", "d", "e"]
						  mylist[1:3] # Up to index 3, but not including index 3
						  # mylist = ["a", "d", "e"]
						  ```
					- ## Len's Slice
					- ## Learn Python: Tuples
						- **What are tuples?**
							- Immutable version of a list
							- Example
								- ```python
								  my_info = ('Mike', 24, 'Programmer')
								  ```
							-
						- Tuple unpacking
							- ```python
							  my_info = ('Mike', 24, 'Programmer')
							  name, age, occupation = my_info
							  print(name) # 'Mike'
							  ```
						- Creating a one element tuple requires a trailing comma
							- ```python
							  one_element_tuple = (4,)
							  ```
					- ## Combining Lists: The ((65db1e62-2691-4453-a21d-e1dd7a716013)) Function
				- # Loops
				  collapsed:: true
				  
				  collapsed:: true
					- ((65d89c40-b7d3-412b-a6cc-dbcc033d73ee))
					- List Comprehensions
					  id:: 65ddfba0-5a45-403b-9cba-2dda61f844fc
					  collapsed:: true
						- More concise way of writing loops
						- Template
							- ```python
							  new_list = [<expression> for <element> in <collection>]
							  ```
						- Example
							- ```python
							  # Add 10 to every grade
							  grades = [90, 88, 62, 76, 74, 89, 48, 57]
							  scaled_grades = [score + 10 for score in grades]
							  ```
							- ```python
							  # Normal way version
							  numbers = [2, -1, 79, 33, -45]
							  doubled = []
							  
							  for number in numbers:
							    doubled.append(number * 2)
							  
							  print(doubled)
							  
							  # List Comprehension version
							  numbers = [2, -1, 79, 33, -45]
							  doubled = [num * 2 for num in numbers]
							  print(doubled)
							  ```
						- Conditionals
							- id:: 65de072f-476f-4db7-a2bd-89b8e96160f3
							  #+BEGIN_IMPORTANT
							  If you're using an `else` condition then you have to move the `if` keyword also
							  #+END_IMPORTANT
								- The placement of the conditional expression within the comprehension is dependent on whether or not an `else` clause is used. When an `if` statement is used without `else`, the conditional must go after `for <element> in <collection>`. If the conditional expression includes an `else` clause, the conditional must go before `for`.
								  id:: 65de07cf-fbe8-47f1-80af-eb27926d0524
							- Examples
								- Double numbers only if they're negative
								  ```python
								  numbers = [2, -1, 79, 33, -45]
								  negative_doubled = [num * 2 for num in numbers if num < 0]
								  print(negative_doubled)
								  ```
								- List only heights above 161
								  ```python
								  heights = [161, 164, 156, 144, 158, 170, 163, 163, 157]
								  can_ride_coaster = [height for height in heights if height > 161]
								  ```
								- ((65de072f-476f-4db7-a2bd-89b8e96160f3))
									- Double numbers only if they're negative else triple all positive numbers
									  ```python
									  numbers = [2, -1, 79, 33, -45]
									  doubled = [num * 2 if num < 0 else num * 3 for num in numbers ]
									  print(doubled)
									  ```
									- ```python
									  numbers = [2, -1, 79, 33, -45]
									  
									  no_if   = [num * 2 for num in numbers]
									  if_only = [num * 2 for num in numbers if num < 0]
									  if_else = [num * 2 if num < 0 else num * 3 for num in numbers]
									  ```
				- # Functions
				  collapsed:: true
				  ((65d89c40-6df9-42a2-8c7f-0436ebaf7ac7)) | Skipped because I don't think there's anything Python-specific I need to learn
				- # Code Challenges
				- # Strings
				  id:: 65d89c40-9752-4c2b-91c1-e867001153e1
				  collapsed:: true
					- ## Introduction to Strings
						- ((65d89c40-82d5-4a1f-aef4-2794999cccd6))
						- String concatenation, either:
						  id:: 65db6ced-003e-4523-bb1b-6528e664313c
							- `print("The triangle area is", area)`
							- `print(f"The rectangle area is {area}")`
						- Colon selection
							- ```python
							  least_favorite_fruit = "cantaloupe"
							  print(least_favorite_fruit[5:8]) # lou
							  ```
					- ## String Methods
						- `strip()` removes whitespace
						- `strip(":")` removes colons from a string
						- `find()` searches a string for its argument and returns the index location of that argument
						- `format()` makes your code more legible by making your string appear in a single set of `"`
						- `title()` capitalises the first letter of each word in a string
							- Related: ((646349f4-ccf3-42d4-be86-bbafbec3e0ad))
						- `split('a')` will remove each `a` and create a new item in the array for the rest of the string (up to another instance of `a`, and repeat)
						- ```python
						  greeting = ["Hello", "my", "name", "is", "Earl"]
						  "_".join(greeting)
						  print(greeting) # ”Hello_my_name_is_Earl”
						  ```
				- # Modules
				  collapsed:: true
				  
				  collapsed:: true
					- ## Modules in Python
						- Python allows us to package code into ((65d89c40-9b6b-4d81-843f-9390f7d559d9)) or ((65d89c40-7296-46fa-91a4-f6147b1f3e9e)) of files called ((65d89c40-9430-4a7d-add8-41e1ecdb916d))
							- ((56f64c9f-11b9-4643-9394-8b8108489567))
						- ((65d89c40-b341-4a75-8002-a6020e483cce))
						- ((65db64bc-91d6-4bef-af12-d0e30aa637ec))
						- ((65db1e62-be7f-411d-b0a2-da3027dd6c7e))
						- Python is inaccurate at adding two decimal numbers together unless you use the module ((65f57be5-b68a-4416-b862-1dcea566717a)) (floating point errors)
					- ## Datetimes
						- ((65d89c40-b341-4a75-8002-a6020e483cce))
					- ## [pipenv](https://pipenv.pypa.io/en/latest/)
					  collapsed:: true
					  
					  collapsed:: true
						- `pip3 install --user pipenv`
						  collapsed:: true
						  Installation
							- Troubleshooting
								- warnings about certain directories not being on PATH
									- ```bash
									  The scripts pipenv and pipenv-resolver are installed in '/home/yourusername/.local/bin' which is not on PATH.
									  Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
									  
									  ...
									  
									  $ pipenv
									  -bash: pipenv: command not found
									  ```
									- Solution
										- `nano ~/.bash_profile`
										- Add
										  ```bash
										  # set PATH so it includes the user's private bin if it exists
										  if [ -d "$HOME/.local/bin" ] ; then
										    export PATH="$HOME/.local/bin:$PATH"
										  fi
										  ```
									- ((644c0b9b-cdd7-48ca-900d-1ae586db9309))
						- `pipenv --version`
						  Check version
						- # How to use
							- ## `pipenv --three`
							  Initialise a Python3 virtual environment in your current directory
								- A `Pipfile` gets automatically created in that directory which lists the dependencies etc and `Pipfile.lock`
								- `Pipfile`
									- Version being `*` means that it'll accept any version
										- e.g.
										  ```
										  [packages]
										  numpy = "*"
										  ```
								- `Pipfile.lock`
								  id:: 66042889-0582-47e6-aba9-40dddac51c5c
									- Similar to ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) : ((646349f7-b85c-45bd-ad53-d1044a9a2fbf)) - it contains metadata e.g. which specific versions of packages you have installed, it is automatically updated by the program itself,
							- ## `pipenv install <package>`
							  Installs a ((653f8c4f-ffdd-436d-9286-e7d5c669b42c)) package into your current virtual environment
								- e.g. `pipenv install numpy`
								- ### How to install a specific version
									- Example
										- ```bash
										  pipenv install requests==2.18.1
										  ```
											- It'll appear in ((66042889-0582-47e6-aba9-40dddac51c5c)) as:
												- ```
												  [packages]
												  requests = "==2.18.1"
												  ```
							- ## `pipenv shell`
							  Switches you from host shell to `pipenv` shell, using the ((66042889-0582-47e6-aba9-40dddac51c5c)) that was created in the current directory
								- `CTRL + D` or command `exit` = exit this `pipenv shell`
								-
						- {Archive}
						  collapsed:: true
							- [Python Walkthrough Virtual Environments with Pipenv - YouTube](https://youtu.be/BVr-6Ki96XM)
							-
				- # Dictionaries
					- ## Creating ((65d89c40-6b83-446b-86f7-4d76effc3c5e))
					- ## Using ((65d89c40-6b83-446b-86f7-4d76effc3c5e))
					- ## Scrabble
					- ## Using Dictionaries
					- ## Abruptly Goblins
				- # Files
					- ## Learn Python: ((65d89c40-9b6b-4d81-843f-9390f7d559d9))
					- ## Python Files
					- ## Hacking the Fender
				- # Classes
					- ## Introduction to Classes
					- ## Basta Fazoolin'
				- # Code Challenges II
				- # Next Steps
				- # [Cheatsheets](https://www.codecademy.com/learn/learn-python-3/modules/learn-python3-hello-world/cheatsheet)
				- Related: ((65d4b9de-9743-4361-a3ac-8dda0f78ff60))
			- [Python Docs | Codecademy](https://www.codecademy.com/resources/docs/python)
			  id:: 65d4b9de-9743-4361-a3ac-8dda0f78ff60
			  collapsed:: true
				- Concepts
					- [Binascii Module](https://www.codecademy.com/resources/docs/python/binascii-module)
					- [Built-in Functions](https://www.codecademy.com/resources/docs/python/built-in-functions)
					  collapsed:: true
						- [.format()](https://www.codecademy.com/resources/docs/python/built-in-functions/format)
						  Used to format different types of objects into strings.
						- [abs()](https://www.codecademy.com/resources/docs/python/built-in-functions/abs)
						  Returns the absolute value of a numeric argument.
						- [all()](https://www.codecademy.com/resources/docs/python/built-in-functions/all)
						  Returns True if every item in an iterable evaluates to True, otherwise, it returns False.
						- [any()](https://www.codecademy.com/resources/docs/python/built-in-functions/any)
						  Takes in an iterable object such as a list or tuple and returns True if any of the elements in the iterable are True. If none of the elements in the iterable are True, returns False.
						- [ascii()](https://www.codecademy.com/resources/docs/python/built-in-functions/ascii)
						  Receives as input an object containing string data, and returns the object as a printable representation with escapes for non-ASCII characters (accented characters).
						- [bin()](https://www.codecademy.com/resources/docs/python/built-in-functions/bin)
						  Converts an integer into its binary equivalent string.
						- [bool()](https://www.codecademy.com/resources/docs/python/built-in-functions/bool)
						  Converts a value to a Boolean True or False value.
						- [breakpoint()](https://www.codecademy.com/resources/docs/python/built-in-functions/breakpoint)
						  Engages, configures, and changes the debugger program used in a script.
						- [bytearray()](https://www.codecademy.com/resources/docs/python/built-in-functions/bytearray)
						  Returns an array of the given bytes of an object.
						- [bytes()](https://www.codecademy.com/resources/docs/python/built-in-functions/bytes)
						  Returns a byte immutable object representing the given bytes of an object.
						- [callable()](https://www.codecademy.com/resources/docs/python/built-in-functions/callable)
						  Returns True if an object is callable, and False if an object is not callable.
						- [chr()](https://www.codecademy.com/resources/docs/python/built-in-functions/chr)
						  Returns Unicode characters represented by integers ranging between 0 and 1,114,111.
						- [classmethod()](https://www.codecademy.com/resources/docs/python/built-in-functions/classmethod)
						  Converts a given function into a class method.
						- [compile()](https://www.codecademy.com/resources/docs/python/built-in-functions/compile)
						  Returns a runnable code object created from a string.
						- [complex()](https://www.codecademy.com/resources/docs/python/built-in-functions/complex)
						  Converts a given string into a complex number.
						- [delattr()](https://www.codecademy.com/resources/docs/python/built-in-functions/delattr)
						  Allows the user to delete attributes from an object.
						- [dict()](https://www.codecademy.com/resources/docs/python/built-in-functions/dict)
						  Initializes a new dictionary from mapping n-number of object (key, value) pairs.
						- [dir()](https://www.codecademy.com/resources/docs/python/built-in-functions/dir)
						  Returns the list of valid attributes of the passed object.
						- [divmod()](https://www.codecademy.com/resources/docs/python/built-in-functions/divmod)
						  Returns the quotient and remainder of the division of two numbers.
						- [enumerate()](https://www.codecademy.com/resources/docs/python/built-in-functions/enumerate)
						  id:: 663a579f-9a40-4bfb-948b-8422fa6bd674
						  Returns a list of tuples containing an index and an element for each of the elements in an iterator.
							- Related: ((65db1e62-be7f-411d-b0a2-da3027dd6c7e))
						- [eval()](https://www.codecademy.com/resources/docs/python/built-in-functions/eval)
						  Returns the value of a Python expression passed as a string.
						- [exec()](https://www.codecademy.com/resources/docs/python/built-in-functions/exec)
						  Executes a code object or string containing Python code.
						- [filter()](https://www.codecademy.com/resources/docs/python/built-in-functions/filter)
						  Returns a filter object that applies a function to each item in an iterable and returns the values that are True.
						- [float()](https://www.codecademy.com/resources/docs/python/built-in-functions/float)
						  Returns a float value based on a string, numeric data type, or no value at all.
						- [frozenset()](https://www.codecademy.com/resources/docs/python/built-in-functions/frozenset)
						  Returns a new frozenset using an optional iterable object such as a string or list.
						- [getattr()](https://www.codecademy.com/resources/docs/python/built-in-functions/getattr)
						  Returns the value of the named property in the specified object.
						- [globals()](https://www.codecademy.com/resources/docs/python/built-in-functions/globals)
						  Returns a dictionary with all the global variables and symbols for the current program.
						- [hasattr()](https://www.codecademy.com/resources/docs/python/built-in-functions/hasattr)
						  Returns True if an object has an attribute and False otherwise.
						- [hash()](https://www.codecademy.com/resources/docs/python/built-in-functions/hash)
						  Returns the hash value as a fixed sized integer.
						- [help()](https://www.codecademy.com/resources/docs/python/built-in-functions/help)
						  Displays documentation of an object using the Python help utility.
						- [hex()](https://www.codecademy.com/resources/docs/python/built-in-functions/hex)
						  Converts an integer number to a lowercase hexadecimal string.
						- [id()](https://www.codecademy.com/resources/docs/python/built-in-functions/id)
						  Gives a unique number for any object in Python.
						- [input()](https://www.codecademy.com/resources/docs/python/built-in-functions/input)
						  Prompts the user for data and returns it as a string.
						- [int()](https://www.codecademy.com/resources/docs/python/built-in-functions/int)
						  Takes in a value that can be converted into an integer, and returns a copy of the value in the int datatype.
						- [isinstance()](https://www.codecademy.com/resources/docs/python/built-in-functions/isinstance)
						  Returns True if the given object is the specified type. Otherwise the function will return False.
						- [issubclass()](https://www.codecademy.com/resources/docs/python/built-in-functions/issubclass)
						  Returns True if a given class is a subclass of one or more classes.
						- [len()](https://www.codecademy.com/resources/docs/python/built-in-functions/len)
						  id:: 65db1e62-50fc-441b-94c9-c70aeca3a724
						  Returns the length of an object, which can either be a sequence or collection.
							- The built-in `len()` function returns the length of an object, which can either be a sequence or collection.
							- ## Syntax
							  
							  ```
							  len(object)
							  ```
							  
							  An `object` passed to the `len()` function is commonly one of the following:
							- It can be a sequence such as a [string](https://www.codecademy.com/resources/docs/python/strings) or [tuple](https://www.codecademy.com/resources/docs/python/tuples).
							- It can also be a collection such as a [dictionary](https://www.codecademy.com/resources/docs/python/dictionaries) or [set](https://www.codecademy.com/resources/docs/python/sets).
							- ## Example
							- The example below demonstrates how the `len()` function is used in a Python program:
								- ```python
								  print(len("Hello, World!"))
								  # Output: 13
								  ```
							- ```python
							  trainer_name = "Code Ninja"
							  
							  badges = {
							    "pewter city": "boulder badge",
							    "cerulean city": "cascade badge",
							    "vermillion city": "thunder badge"
							  }
							  
							  pokemon_team = ["Pikachu", "Charmander", "Pidgeotto"]
							  
							  print(len(trainer_name))
							  print(len(badges))
							  print(len(pokemon_team))
							  
							  ```
							- ## Codebyte Example
							- In the example below, the `len()` function is used to return the length of a string, dictionary, and [list](https://www.codecademy.com/resources/docs/python/lists):
						- [list()](https://www.codecademy.com/resources/docs/python/built-in-functions/list)
						  id:: 65db1e62-3d97-41c4-bac7-932940ded142
						  collapsed:: true
						  Returns a list from an iterable.
							- The **`list()`** function returns a [list](https://www.codecademy.com/resources/docs/python/lists) from an [iterable](https://www.codecademy.com/resources/docs/python/iterators).
							- ## Syntax
								- ```python
								  list(iterable)
								  ```
								- The `iterable` parameter can be one of the following:
									- A sequence type such as a [string](https://www.codecademy.com/resources/docs/python/strings), [range object](https://www.codecademy.com/resources/docs/python/built-in-functions/range), list, or [`tuple`](https://www.codecademy.com/resources/docs/python/tuples).
									- An iterable container such as a list, tuple, [`dictionary`](https://www.codecademy.com/resources/docs/python/dictionaries), or [`set`](https://www.codecademy.com/resources/docs/python/sets).
									- An iterable object such as one returned by the [`iter()`](https://www.codecademy.com/resources/docs/python/iterators/iter) function.
								- If no `iterable` is passed, the `list()` function returns an empty list.
							- ## Example
								- `print(list(dictionary))`
								  id:: 660bf582-8a43-401b-a4c1-cec79eb52d4b
									- ```python
									   test_scores = {"Grace":[80, 72, 90], "Jeffrey":[88, 68, 81], "Sylvia":[80, 82, 84], "Pedro":[98, 96, 95], "Martin":[78, 80, 78], "Dina":[64, 60, 75]}
									  print(list(test_scores))
									  # Prints ["Grace", "Jeffrey", "Sylvia", "Pedro", "Martin", "Dina"]
									  ```
								- The example below demonstrates how the `list()` function is used to create a list from a dictionary:
									- ```python
									  language_difficulties = list({"Python" : "Hard", "Java" : "Medium", "HTML" : "Easy"})
									  print(language_difficulties)
									  
									  empty_list = list()
									  print(empty_list)
									  ```
									- This will print the following output:
										- ```python
										  ['Python', 'Java', 'HTML']
										  []
										  ```
								- ### Codebyte Example
									- The following examples shows three different cases of using the `list()` function:
										- ```python
										  animals_tuple = ("cat", "dog", "hamster")
										  print(f"Tuple example with list(): {list(animals_tuple)}")
										  
										  print("------------------------------------")
										  
										  animal_string = "crocodile"
										  print(f"String example with list(): {list(animal_string)}")
										  
										  print("------------------------------------")
										  
										  my_range = range(1, 4)
										  print(f"Range example with list(): {list(my_range)}")
										  ```
						- [map()](https://www.codecademy.com/resources/docs/python/built-in-functions/map)
						  Returns an iterator that takes a function and applies it to every item in an iterable.
						- [max()](https://www.codecademy.com/resources/docs/python/built-in-functions/max)
						  Returns the highest value from values given or an iterable.
						- [memoryview()](https://www.codecademy.com/resources/docs/python/built-in-functions/memoryview)
						  Creates a memoryview object that allows Python code to access the internal data of an object without making a copy of it.
						- [min()](https://www.codecademy.com/resources/docs/python/built-in-functions/min)
						  Returns the lowest value from values given or an iterable.
						- [next()](https://www.codecademy.com/resources/docs/python/built-in-functions/next)
						  Returns the next element from an iterable object.
						- [oct()](https://www.codecademy.com/resources/docs/python/built-in-functions/oct)
						  Used to get an octal value of an integer number
						- [open()](https://www.codecademy.com/resources/docs/python/built-in-functions/open)
						  Used for opening files in a Python program.
						- [ord()](https://www.codecademy.com/resources/docs/python/built-in-functions/ord)
						  Returns the integer that represents the Unicode character argument.
						- [pow()](https://www.codecademy.com/resources/docs/python/built-in-functions/pow)
						  Returns the value of a base number x to the power of an exponent y, with an optional modulus z.
						- [print()](https://www.codecademy.com/resources/docs/python/built-in-functions/print)
						  Prints the string representation of an object.
						- [property()](https://www.codecademy.com/resources/docs/python/built-in-functions/property)
						  Declares a range of functions to manipulate class attributes.
						- [range()](https://www.codecademy.com/resources/docs/python/built-in-functions/range)
						  id:: 65db1e62-be7f-411d-b0a2-da3027dd6c7e
						  collapsed:: true
						  Returns a sequence of numbers based on the given range
							- `range(3, 15, 4)` is a range object that starts at `3` and goes up to `15` (non-inclusive) in increments of 4
							- Examples
								- ```python
								  range(1, 13)
								  # (1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12)
								  ```
								- `-1` as step argument to iterate backward
								  id:: 66be2eed-c138-44c9-8cad-def9bf88a376
									- ```python
									  if __name__ == '__main__':
									   
									      # print numbers from 1 to 10 in reverse order
									      for i in range(10, 0, -1):
									          print(i)
									  ```
									- In case you need the index, make use of the ((663a579f-9a40-4bfb-948b-8422fa6bd674))
									  ```python
									  if __name__ == '__main__':
									   
									      for i, x in enumerate(range(10, 0, -1)):
									          print((i, x))
									  ```
						- [repr()](https://www.codecademy.com/resources/docs/python/built-in-functions/repr)
						  Returns a printable string describing the object that is passed in.
						- [reversed()](https://www.codecademy.com/resources/docs/python/built-in-functions/reversed)
						  id:: 663a579f-a6ac-4bc6-a2a9-05d3031ea2f1
						  collapsed:: true
						  Takes in an iterable object, such as a list, string, or a tuple and returns a reversed iterator object.
							- Examples
								- Can be used to loop backwards
								  id:: 66be2f9b-6fa5-42f3-9a07-092ba50ada7f
									- ```python
									  if __name__ == '__main__':
									   
									      # print numbers from 1 to 10 in reverse order
									      for i in reversed(range(1, 11)):
									          print(i)
									  ```
						- [round()](https://www.codecademy.com/resources/docs/python/built-in-functions/round)
						  Takes a number and an integer as parameters, and returns the number with decimal places equal to the integer.
						- [set()](https://www.codecademy.com/resources/docs/python/built-in-functions/set)
						  Returns a new set based on an optional iterable object such as a list.
						- [setattr()](https://www.codecademy.com/resources/docs/python/built-in-functions/setattr)
						  Sets the value of the attribute of an object.
						- [sorted()](https://www.codecademy.com/resources/docs/python/built-in-functions/sorted)
						  id:: 65db1e62-4930-4a89-8f9d-287d53fa4686
						  Takes in an iterator object, such as a list, tuple, dictionary, set, or string, and sorts it according to a parameter.
						- [staticmethod()](https://www.codecademy.com/resources/docs/python/built-in-functions/staticmethod)
						  Transforms a method to a static method.
						- [str()](https://www.codecademy.com/resources/docs/python/built-in-functions/str)
						  Takes in a value that can be converted into a string, and returns a copy of the value in the string datatype.
						- [sum()](https://www.codecademy.com/resources/docs/python/built-in-functions/sum)
						  Takes in an iterable object, such as a list or tuple, and returns the sum of all elements.
						- [super()](https://www.codecademy.com/resources/docs/python/built-in-functions/super)
						  Returns a temporary object that allows a given class to inherit the methods and properties of a parent or sibling class.
						- [tuple()](https://www.codecademy.com/resources/docs/python/built-in-functions/tuple)
						  id:: 65db1e62-deeb-421c-a395-946b496fce3e
						  collapsed:: true
						  Creates one new ((65d89c40-66da-4169-95ad-9f3aefb00de2)).
							- ## Syntax
								- ```python
								  tuple_instance(iterable)
								  ```
								- The `iterable` parameter is optional and is an object that can be looped over, such as a [list](https://www.codecademy.com/resources/docs/python/lists) or [string](https://www.codecademy.com/resources/docs/python/strings). If an `iterable` is not provided, an empty tuple is created.
							- ## Codebyte Example
								- The following is an example of how the `tuple()` function is used to create a new tuple from a list:
									- ```python
									  my_list = [1, 2, 3]
									  
									  my_tuple = tuple(my_list)
									  
									  print(my_tuple)
									  ```
						- [type()](https://www.codecademy.com/resources/docs/python/built-in-functions/type)
						  id:: 65db1e62-25b6-4a28-a77a-e687d257e100
						  collapsed:: true
						  Returns the data type of the argument passed to the function.
							- The **`type()`** function returns the data type of the argument passed to it. When the argument is an instance of a [class](https://www.codecademy.com/resources/docs/python/classes), it returns the class that it is an instance of.
							- ## Syntax
							  
							  ```
							  type(some_object)
							  ```
							  
							  The `type()` function primarily accepts `some_object` as a parameter, which can be any of Python’s [data types](https://www.codecademy.com/resources/docs/python/data-types).
							- ## Example
								- The `type()` function can be used to confirm the data type of the object `spam`:
								  
								  ```python
								  spam = 10
								  
								  print(type(spam))
								  
								  # Output: int
								  ```
						- [vars()](https://www.codecademy.com/resources/docs/python/built-in-functions/vars)
						  Returns the \_\_dict\_\_ attribute of an object.
						- [zip()](https://www.codecademy.com/resources/docs/python/built-in-functions/zip)
						  id:: 65db1e62-2691-4453-a21d-e1dd7a716013
						  collapsed:: true
						  Takes multiple iterators as input and returns a single zip object made up of an iterator of multiple ((65d89c40-66da-4169-95ad-9f3aefb00de2)).
							- ## Syntax
								- ```python
								  zip(iterator1, iterator2, ...)
								  ```
							- #+BEGIN_WARNING
							  The zip iterator will be consumed if you do expressions like `print` for it. You need to store it as a list before printing in order to preserve it.
							  #+END_WARNING
								- It'll otherwise appear as an empty object on subsequent `print`s.
							- ## Examples
								- ```python
								  names = ["Jenny", "Alexus", "Sam", "Grace"]
								  heights = [61, 70, 67, 64]
								  names_and_heights = zip(names, heights)
								  print(names_and_heights)
								  # <zip object at 0x7f1631e86b48>
								  # This is the location of the var in memory
								  converted_list = list(names_and_heights)
								  print(converted_list)
								  # [('Jenny', 61), ('Alexus', 70), ('Sam', 67), ('Grace', 64)]
								  
								  ```
								- `zip()` can be used to combine iterators such as lists. Objects will be combined from left to right.
									- ```python
									  my_pets = ['cat', 'dog', 'bird', 'great white shark']
									  my_pets_weight_in_pounds = [9, 50, 0.33, 2000]
									  
									  combined = zip(my_pets, my_pets_weight_in_pounds)
									  
									  print(list(combined))
									  # Output: [('cat', 9), ('dog', 50), ('bird', 0.33), ('great white shark', 2000)]
									  ```
								- Because `zip()` returns an iterator, it is necessary to use the `list()` function, or a similar function like `tuple()` or `set()`, to work with the result:
									- ```python
									  my_languages = ['Python', 'Swift', 'Lisp']
									  number_of_months = [10, 24, 50]
									  
									  combined = zip(my_languages, number_of_months)
									  
									  print("A zip object printed and it's type:")
									  print(combined)
									  print(type(combined))
									  
									  print("\n A zip object mapped to a list and it's type:")
									  
									  combined = list(combined)
									  
									  print(combined)
									  print(type(combined))
									  
									  print("\n A zip object mapped to a tuple and it's type:")
									  
									  combined = tuple(combined)
									  
									  print(combined)
									  print(type(combined))
									  ```
								- If one of the iterators passed in as a parameter to `zip()` contains more objects than another, then the extra objects will be ignored:
									- ```python
									  numbers = [1, 2, 3, 4, 5]
									  letters = ['a', 'b', 'c']
									  
									  combined = zip(numbers, letters)
									  
									  print(list(combined))
									  # Output: [(1, 'a'), (2, 'b'), (3, 'c')]
									  ```
									- Notice how `4` and `5` are not included.
								- You can also unzip a zip object:
									- ```python
									  # Zipping two lists
									  artists = ["Bosch", "Bruegel", "Bonheur"]
									  paintings = ["Garden of Earthly Delights", "Parable of the Sower", "The Horse Fair"]
									  
									  combined = zip(artists, paintings)
									  combined = list(combined)
									  
									  print(combined)
									  
									  # Unzipping a zip object
									  artists, paintings = zip(*combined)
									  
									  print("The artists are: ")
									  print(artists)
									  
									  print("The paintings are: ")
									  print(paintings)
									  ```
					- [Casting](https://www.codecademy.com/resources/docs/python/casting)
					- [Classes](https://www.codecademy.com/resources/docs/python/classes)
					  id:: 65d89c40-9115-428b-8046-fe014e270fd9
					- [Collections Module](https://www.codecademy.com/resources/docs/python/collections-module)
					- [Command Line Arguments](https://www.codecademy.com/resources/docs/python/command-line-arguments)
					- [Comments](https://www.codecademy.com/resources/docs/python/comments)
					- [Conditionals](https://www.codecademy.com/resources/docs/python/conditionals)
					  id:: 65d89c40-28e7-4eab-891e-9ea5d44e8d05
					  collapsed:: true
						- Conditionals take an expression, which is code that evaluates to determine a value, and checks if it is `True` or `False`. If it’s `True`, we can tell our program to do one thing — we can even account for `False` to do another.
						- As we write more complex programs, conditionals allow us to address multiple scenarios and make our programs more robust.
						- If Statement
						  id:: 3724a989-a497-468a-b17d-ab7f05de0af6
						  collapsed:: true
							- The Python `if` statement is used to determine the execution of code based on the evaluation of a Boolean expression.
							- If the `if` statement expression evaluates to `True`, then the indented code following the statement is executed.
							- If the expression evaluates to `False` then the indented code following the if statement is skipped and the program executes the next line of code which is indented at the same level as the if statement.
							- ```python
							  test_value = 100
							  
							  if test_value > 1:
							    print("This code is executed!")
							  
							  if test_value > 1000:
							    print("This code is NOT executed!")
							  
							  print("Program continues at this point.")
							  ```
							- ```python
							  if is_raining:
							  print("bring an umbrella")
							  if 2 == 4 - 2:
							  print("apple")
							  ```
						- Else Statement
						  id:: 65db60c3-c3c3-4d1c-8f65-30a2e1eaa14a
						  collapsed:: true
							- The Python `else` statement provides alternate code to execute if the expression in an if statement evaluates to `False`.
							- The indented code for the `if` statement is executed if the expression evaluates to `True`. The indented code immediately following the `else` is executed if and only if the expression evaluates to `False`.
							- To mark the end of the else block, the code must be unindented to the same level as the starting if line.
							- ```python
							  if weekday:
							    print("wake up at 6:30")
							  else:
							    print("sleep in")
							  ```
						- Elif Statement
						  id:: 65db60a9-a35c-42b5-9fc2-98683ab9a6f1
						  collapsed:: true
							- The Python `elif` statement allows for continued checks to be performed after an initial `if` statement. An `elif` statement differs from the else statement because another expression is provided to be checked, just as with the initial `if` statement.
							- If the expression is `True`, the indented code following the `elif` is executed. If the expression evaluates to False, the code can continue to an optional `else` statement.
							- Multiple elif statements can be used following an initial `if` to perform a series of checks. Once an `elif` expression evaluates to `True`, no further `elif` statements are executed.
							- ```python
							  pet_type = "fish"
							  
							  if pet_type == "dog":
							    print("You have a dog.")
							  elif pet_type == "cat":
							    print("You have a cat.")
							  elif pet_type == "fish":
							    # This is performed
							    print("You have a fish")
							  else:
							    print("Not sure!")
							  ```
						- Codebyte Example
						  collapsed:: true
							- ```python
							  pH = 2
							  
							  if pH < 7:
							    print("Acidic")
							  elif pH > 7:
							    print("Basic")
							  else:
							    print("Neutral")
							  ```
							- What do you think will happen if `pH` is changed to 7?
					- [Data Types](https://www.codecademy.com/resources/docs/python/data-types)
					  id:: 663a579f-1fbc-4702-9250-8e1078bf115b
					  collapsed:: true
						- Python is a strongly typed language, in the sense that at runtime it prevents typing errors and it engages in little implicit type conversion or [casting](https://www.codecademy.com/resources/docs/python/casting), i.e. converting one type to another without a specific call to a conversion function.
						- ```python
						  codecademy = 575
						  codecademy = "575 broadway"
						  ```
						- After line 1, `codecademy` is an `int`. After line 2, `codecademy` is a `str`.
						- Python includes the following categories of built-in data types:
							- ((65d89c40-82d5-4a1f-aef4-2794999cccd6)) type: `str`
							- Boolean type: `bool`
							- Binary types: `bytes`, `bytearray`, `memoryview`
							- Number types: `int`, `float`, `complex`
							- Sequence Types: `list` ( ((65d89c40-5e6f-4b12-b1cc-5d93e2b320cc)) i.e. arrays), `range`, `tuple`
							- Set types: `set`, `frozenset`
							- Dictionary type: `dict` ( ((65d89c40-6b83-446b-86f7-4d76effc3c5e)) i.e. objects)
						- ## type()
							- The `type()` function can be used to retrieve the data type of an object:
							- ```python
							  message = "Hello, world!"
							  
							  print(type(message))
							  # Output: <class 'str'>
							  ```
						- ## isinstance()
							- The `isinstance()` function can be used to test if an object is an instance of a specified type. This will print a boolean value for each function call, indicating if the object is an instance of the given type:
							- ```python
							  word = "purple"
							  languages = ("Python", "JavaScript", "Go")
							  
							  print(isinstance(word, str)) # Output: True
							  print(isinstance(languages, list)) # Output: False
							  print(isinstance(languages, tuple)) # Output: True
							  ```
					- [Dates](https://www.codecademy.com/resources/docs/python/dates)
					  id:: 65d89c40-b341-4a75-8002-a6020e483cce
					  collapsed:: true
						- [datetime](https://docs.python.org/3/library/datetime.html)
							- Intro
								- Python has a built-in module called [datetime](https://docs.python.org/3/library/datetime.html) that can be used to create and modify `datetime` objects.
								- Because the module comes built-in with Python, installation is not required, but we do need to import it at the top of a Python file.
							- Syntax
								- ```python
								  import datetime
								  from datetime import datetime # alternate, recommended for most of the methods below
								  ```
							- Creating datetime Objects
								- The `datetime` module has three main types available:
									- ((65e0444b-5ce0-4d71-92fd-ec9118cffdc8)): Returns a date and time in the year-month-day and hour-minute-second formats.
									- ((65e0444b-cf5f-4fdc-9cf0-cb7480f032fa)): Returns a date in the year-month-day format.
									- ((65e0444b-ae3c-461e-bf35-13c77f1c3cc1)): Returns a time in the hour-minute-second format with optional microsecond and timezone information.
								- Durations between any of these types can be returned by the ((65e0444b-8e58-4574-9989-c044f2fce0e3)) method.
							- Dates
								- [.datetime()](https://www.codecademy.com/resources/docs/python/dates/datetime)
								  id:: 65e0444b-5ce0-4d71-92fd-ec9118cffdc8
								  collapsed:: true
								  Returns a new object with date and time properties.
									- The `.datetime()` method returns a new object with date and time properties.
									- Syntax
										- ```python
										  datetime.datetime(YYYY, MM, DD, hh, mm, ss)
										  # `hh, mm, ss` are optional
										  ```
									- Examples
										- ```python
										  birthday = datetime(1993, 2, 11)
										  print(birthday.year) # 1993
										  print(birthday.weekday()) # 3 (Thursday. 0 = Mon)
										  ```
										- Subtraction allows you to compute the ((65e0444b-8e58-4574-9989-c044f2fce0e3))
										  id:: 66034e1f-a532-4fc6-9e66-4577f10269ff
											- ```python
											  datetime(2018, 1, 1) - datetime(2017, 1, 1)
											  # datetime.timedelta(days=365)
											  datetime.now() - datetime(2017, 1, 1)
											  # datetime.timedelta(days=318, seconds=69145, microseconds=690112)
											  ```
									- The following parameters must be valid when passed into the `.datetime()` method:
										- | Parameter | Required? | Description                                                                     | Range                                            |
										  | --------- | --------- | ------------------------------------------------------------------------------- | ------------------------------------------------ |
										  | `YYYY`    | Yes       | The year expressed in one to four digits.                                       | 1 - 9999                                         |
										  | `MM`      | Yes       | The month expressed in one or two digits.                                       | 1 - 12                                           |
										  | `DD`      | Yes       | The day of the month expressed in one or two digits.                            | 1 - the number of days in a given month and year |
										  | `hh`      | ✕         | The hour in a given 1-day period that can be expressed as one or two digits.    | 0 - 24                                           |
										  | `mm`      | ✕         | The minute in a given 1-hour period that can be expressed as one or two digits. | 0 - 60                                           |
										  | `ss`      | ✕         | The second in a given 1-hour period that can be expressed as one or two digits. | 0 - 60                                           |
									- ## Codebyte Example
										- A date and time can be retrieved and stored in a variable as shown below:
										- ```python
										  import datetime
										  
										  meeting = datetime.datetime(2021, 10, 5, 10, 5, 31)
										  
										  print(meeting)
										  ```
								- [.datetime.now()](https://www.codecademy.com/resources/docs/python/dates/now)
								  collapsed:: true
								  Returns the _current_ date and timestamp.
									- The `.datetime.now()` method returns a new `datetime` object with the current local date and timestamp.
									- Syntax
										- ```python
										  datetime.datetime.now(time_zone=None)
										  ```
										- The result from the `.datetime.now()` method contains the year, month, day, hour, minute, second, and microsecond (expressed as `YYYY-MM-DD hh:mm:ss.ffffff`).
										- It also accepts an optional `time_zone` parameter, which is set to `None` by default.
									- ## Codebyte Example
										- The current date and time can be retrieved and stored in a variable as shown below:
										- ```python
										  import datetime
										  
										  today = datetime.datetime.now()
										  
										  print(today)
										  ```
								- [datetime.date()](https://www.codecademy.com/resources/docs/python/dates/date)
								  id:: 65e0444b-cf5f-4fdc-9cf0-cb7480f032fa
								  collapsed:: true
								  Returns a date object in the year-month-day format.
									- The `datetime.date()` method returns a date object in the year-month-day format.
									- Syntax
										- ```python
										  datetime.date(YYYY, MM, DD)
										  ```
										- All parameters passed to the `datetime.date()` method in the snippet above are required and must be passed in order. Otherwise, a `TypeError` is thrown.
										- | Parameter | Description                                          | Range                                        |
										  | --------- | ---------------------------------------------------- | -------------------------------------------- |
										  | `YYYY`    | The year expressed in four digits.                   | 1 - 9999                                     |
										  | `MM`      | The month expressed in one or two digits.            | 1 - 12                                       |
										  | `DD`      | The day of the month expressed in one or two digits. | 1 - number of days in a given month and year |
									- ## Codebyte Example
										- A date can be retrieved and stored in a variable as shown below:
										- ```python
										  import datetime
										  
										  meeting_date = datetime.date(2021, 10, 5)
										  
										  print(meeting_date)
										  ```
								- [datetime.timedelta()](https://www.codecademy.com/resources/docs/python/dates/timedelta)
								  id:: 65e0444b-8e58-4574-9989-c044f2fce0e3
								  collapsed:: true
								  Returns a duration, resolved to microseconds, that occurs between dates, times, and datetimes.
									- The `datetime.timedelta()` method returns an object representing a duration, resolved to microseconds, that occurs between [`date`](https://www.codecademy.com/resources/docs/python/dates/date), [`time`](https://www.codecademy.com/resources/docs/python/dates/time), and [`datetime`](https://www.codecademy.com/resources/docs/python/dates/datetime) objects.
									- Syntax
										- ```python
										  datetime.timedelta(days=0, seconds=0, microseconds=0, milliseconds=0, minutes=0, hours=0, weeks=0)
										  ```
										- All of the parameters are optional and default to zero.
									- Examples
									- ## Codebyte Example
										- We can perform different operations on a `datetime` object. For example, if we want to add 2 months to the current date, it can be done as below:
										- ```python
										  import datetime
										  
										  # Assign current datetime
										  current_date = datetime.datetime.now()
										  
										  date_after_two_months = current_date + datetime.timedelta(days = 30*2)
										  
										  print(date_after_two_months)
										  # Displays date 2 months after the current date
										  ```
									- Related:
										- ((65e0444b-5ce0-4d71-92fd-ec9118cffdc8)) : ((66034e1f-a532-4fc6-9e66-4577f10269ff))
											- {{embed ((66034e1f-a532-4fc6-9e66-4577f10269ff))}}
								- [.time()](https://www.codecademy.com/resources/docs/python/dates/time)
								  id:: 65e0444b-ae3c-461e-bf35-13c77f1c3cc1
								  collapsed:: true
								  Returns the seconds elapsed since the epoch.
									- The `datetime.time()` method returns a time in seconds that has passed since the epoch set on the computer.
									- Syntax
										- ```
										  datetime.time(hour=0, minute=0, second=0, microsecond=0, tzinfo=None)
										  ```
										- The epoch is usually set as `January 1, 1970, 00:00:00 (UTC)` on most operating systems, excluding any leap seconds.
									- ## Codebyte Example
										- The time can be retrieved and stored in a variable as shown below:
										- ```python
										  import datetime
										  
										  meeting_time = datetime.time(10, 5, 31)
										  
										  print(meeting_time)
										  ```
								- [`strptime`](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-behavior)
								  collapsed:: true
								  AKA string parse | Allows you to parse string dates into a datetime object.
									- Use the format codes documentation to know what codes to use to convert your string.
									- Examples
										- ```python
										  parsed_date = datetime.strptime('Jan 15, 2018', '%b %d, %Y')
										  ```
								- [`strftime`](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-behavior)
								  collapsed:: true
								  AKA string format | Allows you to render a date as a string.
									- Examples
										- ```python
										  date_string = datetime.strftime(datetime.now(), '%b %d, %Y')
										  # 'Nov 15, 2018'
										  ```
							- {Archive}
								- ## [Python Walkthrough Using Datetimes in Python3 - YouTube](https://youtu.be/smDBZDvsm0I)
					- [Decorators](https://www.codecademy.com/resources/docs/python/decorators)
					- [Dictionaries](https://www.codecademy.com/resources/docs/python/dictionaries)
					  id:: 65d89c40-6b83-446b-86f7-4d76effc3c5e
					  collapsed:: true
					  Mostly equivalent to [[JavaScript]] : ((63f33e7c-e71b-4d14-b352-7b9fe2d600b1))
						- Meta
							- Differences/Similarities with [[JavaScript]] : ((63f33e7c-e71b-4d14-b352-7b9fe2d600b1))
							  id:: 66044236-7c13-489c-90d8-c596c760179a
							  collapsed:: true
								- Differences
									- Of ((65d89c40-6b83-446b-86f7-4d76effc3c5e))
										- Keys can be any immutable data type (like strings, numbers, tuples) instead of strings-only
										- No inherent methods
										- No inherent inheritance mechanisms via prototype chains
									- Of [[JavaScript]] : ((63f33e7c-e71b-4d14-b352-7b9fe2d600b1))
										- Can access properties through [dot notation](<((63f8fedc-7c7f-4902-abd1-b925c86c93ce))>)
										- Iteration uses a ((635eb08f-a372-4f5b-9072-e574620dbea4)), instead of Python's ((2db45cf2-69a5-46d9-aacb-fcf40f7f4480))
								- Similarities
									- Unordered set of `key: value` pairs
									- Can access properties through [bracket notation](<((65db7226-ce4e-44bc-81dc-92c400d2765d))>)
						- ## Intro
							- A dictionary is an unordered data set of `key: value` pairs.
							- It provides a way to map pieces of data to each other and allows for quick access to values associated with keys.
							- In Python, dictionaries are dynamic and mutable, which means they can change.
							- **Note:** As of Python version 3.7, dictionaries are ordered based on insertion, but this is not the case in previous versions.
						- ## Syntax
							- The syntax of a dictionary is as follows:
								- ```python
								  dictionary_name = { key1: value1,  key2: value2,  key3: value3 }
								  ```
							- Each entry in a dictionary is a key-value pair. Each pair is separated by a comma. Whitespace is optional.
							- Dictionary keys must be immutable types such as numbers and strings because keys should not change. Keys cannot be lists or dictionaries because they are mutable, and it will raise a `TypeError`.
							- Values can be any type, such as strings, numbers, lists, and even other dictionaries.
						- ## Examples
							- ```python
							  menu = {"avocado toast": 6, "carrot juice": 5, "blueberry muffin": 2}
							  subtotal_to_total = {20: 24, 10: 12, 5: 6, 15: 18}
							  students_in_classes = {"software design": ["Aaron", "Delila", "Samson"], "cartography": ["Christopher", "Juan", "Marco"], "philosophy": ["Frederica", "Manuel"]}
							  person = {"name": "Shuri", "age": 18, "family": ["T'Chaka", "Ramonda"]}
							  ```
						- # Common Operations
							- ## Creating a Dictionary
								- An empty dictionary is created with curly braces:
									- ```python
									  diner = {}
									  ```
								- An empty dictionary can also be created using the built-in function, `dict()`, with no arguments:
									- ```python
									  diner = dict()
									  ```
								- A dictionary with entries:
									- ```python
									  coffee_shop = { "cold brew": 3.50, "latte": 4.25, "cappucino": 3.99 }
									  ```
									- The three key-value pairs in the `coffee_shop` dictionary:
										- `"cold brew": 3.50`
										- `"latte": 4.25`
										- `"cappucino": 3.99`
							- ## Accessing a Dictionary
								- The values in a dictionary can be accessed by passing the associated key name in a `dictionary[key]` syntax:
									- ```python
									  coffee_shop = { "cold brew": 3.50, "latte": 4.25, "cappucino": 3.99 }
									  
									  print(coffee_shop["cold brew"])
									  # Output: 3.5
									  ```
								- When a value is retrieved from a key that does not exist, `KeyError` is raised. If a value is assigned to a key that doesn’t exist, the new key-value pair will be added. If a value is assigned to an existing dictionary key, it replaces the existing value.
									- How to avoid `KeyError` - add an ((3724a989-a497-468a-b17d-ab7f05de0af6)) and the `in` keyword
										- Example
											- ```python
											  key_to_check = "Landmark 81"
											  
											  if key_to_check in building_heights:
											    print(building_heights["Landmark 81"])
											  ```
									- `in`
									  id:: 660c1753-1d46-4507-9c99-996d98c85e21
										- Has these uses
											- `if eleemnt in sequence:`
											- `for element in sequence:`
											- Check presence of a `key` in a dictionary
												- Example
													- ```python
													  inventory = {"iron spear": 12, "invisible knife": 30, "needle of ambition": 10, "stone glove": 20, "the peacemaker": 65, "demonslayer": 50}
													  
													  print(12 in inventory)
													  # False
													  ```
													- ```python
													  inventory = {"iron spear": 12, "invisible knife": 30, "needle of ambition": 10, "stone glove": 20, "the peacemaker": 65, "demonslayer": 50}
													  
													  print("the peacemaker" in inventory)
													  # True
													  ```
							- ## Adding an Entry
								- To add an entry, use square brackets to create an index into a `new_key` and assign it a `new_value`:
								- ```python
								  my_dict[new_key] = new_value
								  ```
								- **Example:**
									- ```python
									  menu = {"avocado toast": 6}
									  menu["oatmeal"] = 3
									  # {"avocado toast": 6, "oatmeal": 3}
									  ```
								- ((660434f1-fdd9-4e76-9dd4-d1b9069b3597)) can be used to add multiple at once
							- ## Replacing an Entry in an Existing Dictionary
								- If a key needs to be updated in an existing dictionary, it uses the same syntax for adding an entry into a dictionary (`dictionary[new_key] = new_value`), but instead, the `new_key` argument is replaced with an already existing key in the desired dictionary (`dictionary[existing_key] = new_value`).
									- ```python
									  person_age = { "Mark": 55, "Shiela": 28, "Bryce": 24, "Jim": 41, "Eric": 33, "Ally": 23 }
									  
									  # Looks like it's Mark's Birthday! Let's update our dictionary to reflect his new age:
									  person_age['Mark'] = 56
									  ```
										- Now, when the `"Mark"` key is accessed from the `person_age` dictionary, it will produce the value `56`.
							- ## Iterating Through a Dictionary
								- There are several ways to iterate through a dictionary depending on which data that is accessed: keys, values, or both.
								- keys
									- ```python
									  oscars = {"Best Picture": "Moonlight", "Best Actor": "Casey Affleck", "Best Actress": "Emma Stone", "Animated Feature": "Zootopia"}
									  
									  for element in oscars:
									    print(element)
									    # "Best Picture"
									    # "Best Actor"
									    # "Best Actress"
									    # "Animated Feature"
									  ```
								- The following codebyte consists of four `for` loops that iterate through the `coffee_shop` dictionary:
									- ```python
									  coffee_shop = { "cold brew": 3.50, "latte": 4.25, "cappucino": 3.99 }
									  
									  for key in coffee_shop.keys():
									      print(key)
									  
									  for value in coffee_shop.values():
									      print(value)
									  
									  for item in coffee_shop.items():
									      print(item)
									  
									  for key, value in coffee_shop.items():
									      print(key, value)
									  ```
								- The `for` loops access and print each key, value, key-value tuple, and individual key-values in `coffee_shop`, respectively.
							- ## Creating a Dictionary using Dictionary Comprehension
							  AKA dict comprehension
								- Like a ((65ddfba0-5a45-403b-9cba-2dda61f844fc)), a dictionary comprehension is a Pythonic way to create a dictionary. They can be used to filter and manipulate data in tons of useful ways.
								- ### Syntax
									- ```python
									  new_dict = { expression for key, value in old_dict.items() if condition }
									  ```
									- ```python
									  new_dict = {key:value for key, value in zip(list1, list2)}
									  ```
										- ((6605321d-57cd-450c-9405-f79aba4c941d))
								- ### Examples
									- Using ((65db1e62-2691-4453-a21d-e1dd7a716013)) (combining two lists to make an iterator of multiple ((65d89c40-66da-4169-95ad-9f3aefb00de2)) ), then converting it into a dictionary (each tuple becomes a `key: value` pair)
									  id:: 6605321d-57cd-450c-9405-f79aba4c941d
										- ```python
										  names = ['Jenny', 'Alexus', 'Sam', 'Grace']
										  heights = [61, 70, 67, 64]
										  students = {key:value for key, value in zip(names, heights)}
										  # {'Jenny': 61, 'Alexus': 70, 'Sam': 67, 'Grace': 64}
										  ```
										- ```python
										  drinks = ["espresso", "chai", "decaf", "drip"]
										  caffeine = [64, 40, 0, 120]
										  zipped_drinks = zip(drinks, caffeine)
										  drinks_to_caffeine = {key:value for key, value in zipped_drinks}
										  # {'espresso': 64, 'chai': 40, 'decaf': 0, 'drip': 120}
										  ```
								- The `if` condition at the end is optional, but is a great tool for filtering data. For example, given a dictionary with a person’s name and age, make a new dictionary that only contains people with an age under 25:
									- ```python
									  person_age = { "Mark": 55, "Shiela": 28, "Bryce": 24, "Jim": 41, "Eric": 33, "Ally": 23 }
									  person_age_filtered = { name: age for name, age in person_age.items() if age < 25 }
									  ```
								- The expression is `name: age`, as that’s how the new dictionary will be formatted. Then, the typical for loop iteration, `for name, age in person_age.items()`. Lastly, the `if` condition filters out the results.
								- The expression can also perform operations on the data being extracting. For example, to create a dictionary with key value pairs of a number and its square given a list of numbers:
									- ```python
									  nums_list = [ 1, 2, 3, 4, 5 ]
									  nums_squared = { num: num**2 for num in nums_list }
									  ```
								- `nums_squared` will produce a result of: `{ 1: 1, 2: 4, 3: 9, 4: 16, 5: 25 }`
								- The following built-in methods listed below help with manipulating dictionaries and the objects within:
						- # Methods
							- ## Common operations using the methods
								- ((660434f1-c165-45ed-94d2-7604d3930ce2)) - lookup a value for a specified key
								- ((660434f1-e4d7-40bc-b081-e0e8418a4e4c)) - delete a key
								- Either: ((65db1e62-3d97-41c4-bac7-932940ded142)) or ((660434f1-1e1b-4000-a5f8-1f0c280986db)) to return the list of keys
									- ((660bf582-8a43-401b-a4c1-cec79eb52d4b))
									- ((660bf650-2fd6-459f-8a93-14f6b3d10ee7))
								- ((660434f1-470b-46a2-8812-a641da81481e)) - return the list of values
								- ((660434f1-50b5-4e29-bd37-bef0c1e0ae50)) - return the list of `key-value` pairs
								-
							- All
								- [.clear()](https://www.codecademy.com/resources/docs/python/dictionaries/clear)
								  Removes all entries in a dictionary.
								- [.copy()](https://www.codecademy.com/resources/docs/python/dictionaries/copy)
								  Returns a copy of a dictionary.
								- [.fromkeys()](https://www.codecademy.com/resources/docs/python/dictionaries/fromkeys)
								  Returns a dictionary with the specified keys.
								- [.get()](https://www.codecademy.com/resources/docs/python/dictionaries/get)
								  id:: 660434f1-c165-45ed-94d2-7604d3930ce2
								  collapsed:: true
								  Returns the `value` of a dictionary entry for a specified `key`, with an optional fallback value.
									- The `.get()` method will return the value of a dictionary entry for a specified key. It may also specify a fallback value if the specified key does not exist in the dictionary.
									- This method is an alternative to the `dictionary[key]` syntax that does not produce an exception when a key doesn’t exist.
									- ## Syntax
										- ```python
										  dictionary.get(key, value)
										  ```
										- Where `key` is the key of the value to return and `value` is an optional value to return if `key` does not exist in `dictionary`. If `value` isn’t specified, the fallback value will be `None`.
									- ## Examples
										- The following example creates a dictionary, then retrieves some values for keys using `.get()`:
											- ```python
											  d = {1:'one', 2:'two', 3:'three'}
											  print(d.get(3))
											  print(d.get(4))
											  print(d.get(4, 'empty'))
											  ```
								- [.items()](https://www.codecademy.com/resources/docs/python/dictionaries/items)
								  id:: 660434f1-50b5-4e29-bd37-bef0c1e0ae50
								  collapsed:: true
								  Returns a list of tuples for each key-value pair in a dictionary.
									- The `.items()` method of a Python dictionary returns a list of [tuples](https://www.codecademy.com/resources/docs/python/tuples) for each key-value pair in a dictionary. It takes no arguments.
									- Syntax
										- ```python
										  dictionary.items()
										  ```
									- Example
										- The following example creates a dictionary, then prints the dictionary and the output from `.items()`:
											- ```python
											  d = {1:'one', 2:'two', 3:'three'}
											  d_items = d.items()
											  print(d_items)
											  # dict_items([(1, 'one'), (2, 'two'), (3, 'three')])
											  ```
										- Iterating thrrough
											- ```python
											  biggest_brands = {"Apple": 184, "Google": 141.7, "Microsoft": 80, "Coca-Cola": 69.7, "Amazon": 64.8}
											  
											  for company, value in biggest_brands.items():
											   print(company + " has a value of " + str(value) + " billion dollars. ")
											  
											  # Apple has a value of 184 billion dollars.
											  # Google has a value of 141.7 billion dollars.
											  # Microsoft has a value of 80 billion dollars.
											  # Coca-Cola has a value of 69.7 billion dollars.
											  # Amazon has a value of 64.8 billion dollars.
											  ```
											- ```python
											  pct_women_in_occupation = {"CEO": 28, "Engineering Manager": 9, "Pharmacist": 58, "Physician": 40, "Lawyer": 37, "Aerospace Engineer": 9}
											  
											  for key, value in pct_women_in_occupation.items():
											    print(f"Women make up {value} percent of {key}s.")
											  # Women make up 28 percent of CEOs.
											  # Women make up 9 percent of Engineering Managers.
											  # Women make up 58 percent of Pharmacists.
											  ```
								- [.keys()](https://www.codecademy.com/resources/docs/python/dictionaries/keys)
								  id:: 660434f1-1e1b-4000-a5f8-1f0c280986db
								  collapsed:: true
								  Returns a list of keys for a dictionary.
									- The `.keys()` method of a Python dictionary returns list of its keys. It takes no arguments.
									- Syntax
										- ```python
										  dictionary.keys()
										  ```
									- Note: it returns a `dict_keys` object, which is a view-only and not mutable iterable
									  id:: 660c074d-2a53-4634-864d-79f7ea7e52ea
									- Examples
										- `print(dictionary.keys())`
										  id:: 660bf650-2fd6-459f-8a93-14f6b3d10ee7
										  Creates a dictionary then prints all of its keys
											- ```python
											  d = {1:'one', 2:'two', 3:'three'}
											  d_keys = d.keys()
											  print(d_keys)
											  ```
								- [.pop()](https://www.codecademy.com/resources/docs/python/dictionaries/pop)
								  id:: 660434f1-e4d7-40bc-b081-e0e8418a4e4c
								  collapsed:: true
								  Returns the value of a specified key, then removes the key-value pair from a dictionary.
									- The `.pop()` method of a Python dictionary returns the value of a specified key, then removes the key-value pair from the dictionary.
									- ## Syntax
										- ```python
										  dictionary.pop(key)
										  ```
										- Where `key` is the key of the value to return and the entry to remove.
									- ## Examples
										- The following example creates a dictionary and “pops” a value from it:
											- ```python
											  d = {1:'one', 2:'two', 3:'three'}
											  d_value = d.pop(2)
											  print(d_value)
											  print(d)
											  ```
								- [.popitem()](https://www.codecademy.com/resources/docs/python/dictionaries/popitem)
								  Returns the last inserted key-value pair from a dictionary as a tuple, and removes the entry.
								- [.setdefault()](https://www.codecademy.com/resources/docs/python/dictionaries/setdefault)
								  Returns the value of a specified key. If the key does not exist, it is inserted with the specified value.
								- [.update()](https://www.codecademy.com/resources/docs/python/dictionaries/update)
								  id:: 660434f1-fdd9-4e76-9dd4-d1b9069b3597
								  collapsed:: true
								  Adds the entries in a specified dictionary, or iterable of key-value pairs, to a dictionary.
									- The `.update()` method returns new Python dictionary with entries from another dictionary, or some other iterable, added to it.
									- Syntax
										- ```python
										  dictionary.update(entries)
										  ```
										- Where `entries` is another dictionary or an iterable of key-value pairs. Pairs in `dictionary` are replaced by any pair in `entries` with a duplicate key.
									- Examples
										- ```python
										  plays = {'Satisfaction': 29, 'Imagine': 44}
										  plays.update({"Purple Haze": 1})
										  # {'Satisfaction': 29, 'Imagine': 44, 'Purple Haze': 1}
										  ```
										- ```python
										  sensors.update({"pantry": 22, "guest room": 25, "patio": 34})
										  # {"pantry": 22, "guest room": 25, "patio": 34}
										  ```
										- Codebyte Example
											- The following example creates two dictionaries, then adds the entries from one to the other.
											- ```python
											  d1 = {1:'one',2:'two', 3:'three'}
											  d2 = {4:'four', 5:'five', 6:'six'}
											  d1.update(d2)
											  print(d1)
											  ```
								- [.values()](https://www.codecademy.com/resources/docs/python/dictionaries/values)
								  id:: 660434f1-470b-46a2-8812-a641da81481e
								  collapsed:: true
								  Returns a view of values for a dictionary.
									- The `.values()` method returns all of its values of a Python dictionary in a view object that will reflect any changes to the dictionary values. It takes no arguments.
									- Syntax
										- dictionary.values()
									- ((660c074d-2a53-4634-864d-79f7ea7e52ea))
									- Examples
										- `list(test_scores.values())`
										- The following example creates a dictionary, then prints all the values:
											- ```python
											  d = {1:'one', 2:'two', 3:'three'}
											  d_values = d.values()
											  print(d_values)
											  # ['one', 'two', 'three']
											  d[3] = 'four'
											  print(d_values)
											  # ['one', 'two', 'three', 'four']
											  ```
										- Iterating over a list of values
											- ```python
											  test_scores = {"Grace":[80, 72, 90], "Jeffrey":[88, 68, 81], "Sylvia":[80, 82, 84], "Pedro":[98, 96, 95], "Martin":[78, 80, 78], "Dina":[64, 60, 75]}
											  
											  for score_list in test_scores.values():
											   print(score_list)
											  # [80, 72, 90]
											  # [88, 68, 81]
											  # [80, 82, 84]
											  # [98, 96, 95]
											  # [78, 80, 78]
											  # [64, 60, 75]
											  ```
										- Iterating over list of values and adding up the total
											- ```python
											  num_exercises = {"functions": 10, "syntax": 13, "control flow": 15, "loops": 22, "lists": 19, "classes": 18, "dictionaries": 18}
											  total_exercises = 0
											  for item in num_exercises.values():
											    total_exercises += item
											  print(total_exercises)
											  ```
								- ### [More methods](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict)
					- [Dunder Methods](https://www.codecademy.com/resources/docs/python/dunder-methods)
					- [Errors](https://www.codecademy.com/resources/docs/python/errors)
					  id:: 65d89c40-28e0-4abb-bcfa-01687608a1ef
					  collapsed:: true
						- The two types of **errors** in Python are syntax errors and exceptions.
						- ## Syntax Errors
							- Syntax errors (also known as parsing errors) occur when a sequence of characters, or tokens, violates the syntax of the Python programming language:
							- ```
							  File "script.py", line 1
							    while True print("Hello world!")
							                     ^
							  SyntaxError: invalid syntax
							  ```
							- The parser repeats the offending line and displays a little arrow `^` pointing at the earliest point in the line where the error was detected.
							- The error is caused by (or at least detected at) the token preceding the arrow in the example, the error is detected at the [`print()`](https://www.codecademy.com/resources/docs/python/built-in-functions/print) function, since a colon `:` is missing before it.
							- File name and line number are printed to state where the error originated.
							- Some common syntax errors are:
								- Misspelling a Python keyword.
								- Missing colon :.
								- Missing closing parenthesis ), square bracket ], or curly brace }.
						- ## Exceptions
							- Even if a statement or expression is syntactically correct, it may cause an error when an attempt is made to execute it. Errors detected during execution are called exceptions and are not unconditionally fatal. Most exceptions are not handled by programs, however, and result in error messages as shown here:
							- ### Value Error
							  collapsed:: true
								- `ValueError` is thrown when a function’s argument is of the correct type, but an inapprpriate value, such as being out of range.
								- ```
								  Traceback (most recent call last):
								  File "script.py", line 1, in <module>
								  int('xyz')
								  ValueError: invalid literal for int() with base 10: 'xyz'
								  ```
							- ### Name Error
							  collapsed:: true
							  Thrown when an object could not be found e.g. unknown variable
								- ```
								  Traceback (most recent call last):
								  File "script.py", line 1, in <module>
								  age
								  NameError: name 'age' is not defined
								  ```
								- This can occur if a variable is used before it has been assigned a value or if a variable name is spelled differently than the point at which it was defined.
								- Some common name errors are:
									- Misspelling a variable name.
									- Forgetting to define a variable.
							- ### Index Error
							  collapsed:: true
								- `IndexError` is thrown when trying to access an item at an invalid index.
								- ```
								  Traceback (most recent call last):
								  File "script.py", line 1, in <module>
								  employees[3]
								  IndexError: list index out of range
								  ```
							- ### Module Not Found Error
							  collapsed:: true
								- `ModuleNotFoundError` is thrown when a module could not be found.
								- ```
								  Traceback (most recent call last):
								  File "script.py", line 1, in <module>
								  import notamodule
								  ModuleNotFoundError: No module named 'notamodule'
								  ```
							- ### Type Error
							  collapsed:: true
							  Thrown when an operation is applied to an object of an inappropriate type.
								- ```
								  Traceback (most recent call last):
								  File "script.py", line 1, in <module>
								  max(True)
								  TypeError: 'bool' object is not iterable
								  ```
								- Some common types errors are:
									- Accidentally adding or subtracting a string value.
									- Call a function on something of the incorrect type.
							- ### Zero Division Error
							  collapsed:: true
								- `ZeroDivisionError` is thrown when the second operator in the division is zero.
								- ```
								  Traceback (most recent call last):
								  File "script.py", line 1, in <module>
								  ratio = 100 / 0
								  ZeroDivisionError: division by zero
								  ```
					- [Files](https://www.codecademy.com/resources/docs/python/files)
					  id:: 65d89c40-9b6b-4d81-843f-9390f7d559d9
					  collapsed:: true
						- **Files** are named locations on the computer’s disk that permanently store information for future use of its data. They are used to permanently store data in non-volatile memory (e.g. hard disk) as opposed to volatile sources like Random Access Memory [RAM](https://www.codecademy.com/resources/docs/general/computer-hardware/ram), which loses its data when the computer is turned off.
						- ## File Handling
							- Handling files is a common feature that many languages use to work with the computer’s file system. In Python, file handling is possible and usually takes place in the following order:
								- 1.  Open (or create) the file.
								- 2.  Perform operations on the file, such as reading or writing to it.
								- 3.  Close the file to free up any resources used.
							- Example
								- ```python
								  # Create, or overwrite, a file and open for writing
								  file = open("myfile.txt", "w")
								  file.write("Hello world!")
								  file.close()
								  
								  # Open existing file to read and print text content
								  file = open("myfile.txt", "r")
								  first_two_bytes = file.read(2)
								  next_three_bytes = file.read(3)
								  the_rest = file.read()
								  print(first_two_bytes, next_three_bytes, the_rest, sep="\n")
								  file.close()
								  ```
							- The small example below demonstrates how one process of file handling could work:
								- ```python
								  # Create, or overwrite, a file and open for writing
								  file = open("myfile.txt", "w")
								  file.write("Hello world!")
								  file.close()
								  
								  # Open existing file to read and print text content
								  file = open("myfile.txt", "r")
								  first_two_bytes = file.read(2)
								  next_three_bytes = file.read(3)
								  the_rest = file.read()
								  print(first_two_bytes, next_three_bytes, the_rest, sep="\n")
								  file.close()
								  ```
							- In the first part of the code example, a plain text file named `myfile.txt` was created and opened in the `"w"` “write”-mode. Then a piece of text was written to the file and closed afterward.
							- In the next part, a few calls to the `.read()` method are assigned to some [variables](https://www.codecademy.com/resources/docs/python/variables) and then each one is [printed](https://www.codecademy.com/resources/docs/python/built-in-functions/print) on a new line:
								- ```
								  He
								  llo
								   world!
								  ```
						- ## Files and the Command Line
							- Python files can be run as [command line arguments](https://www.codecademy.com/resources/docs/python/command-line-arguments) using their filename.
							- ```python
							  python example_file.py
							  
							  # Alternate
							  python3 example_file.py
							  ```
							- This executes a file’s inner `__main__` environment variable, which then runs the code within. This code may include variable declarations, operations, and function calls.
							- ### More on `__main__`
								- Any time a `.py` file is run and interpreted, certain variables are set up and linked with the file. This includes `__main__` environment variable, which is assigned as the file’s `__name__` variable. All Python programs feature these variables, which can be verified as in the following example:
									- ```python
									  # example.py
									  
									  import imported_example
									  
									  if __name__ == '__main__':
									    print('Example file: ' + __name__)
									  
									  print('Imported example file: ' + imported_example.__name__)
									  ```
								- When `python example.py` is run on the command line, the following will be printed:
									- ```
									  Example file: __main__
									  Imported example file: imported_example_file
									  ```
								- The main file being run, `example.py`, has its `__name__` set to `__main__` while the `imported_example.py` file’s `__name__` is literally set to the name of the file.
								- More information about file methods in Python can be found below.
						- ## Methods
							- [.close()](https://www.codecademy.com/resources/docs/python/files/close)
							  : Allows the user to close an open file within the IDE.
							- [.read()](https://www.codecademy.com/resources/docs/python/files/read)
							  : Allows the user to read the contents of an open file and return the number of associated bytes.
							- [.readline()](https://www.codecademy.com/resources/docs/python/files/readline)
							  : Returns the first line of content from an open file.
							- [.remove()](https://www.codecademy.com/resources/docs/python/files/remove)
							  : Allows the user to delete a file if it exists.
							- [.rmdir()](https://www.codecademy.com/resources/docs/python/files/rmdir)
							  : Allows the user to delete a folder if it exists.
							- [.seek()](https://www.codecademy.com/resources/docs/python/files/seek)
							  : Allows the user to move the location of the file handle's reference point within an open file from one place to another.
							- [.truncate()](https://www.codecademy.com/resources/docs/python/files/truncate)
							  : Allows the user to resize the file to a given number of bytes when the file is accessed through the append mode.
							- [.unlink()](https://www.codecademy.com/resources/docs/python/files/unlink)
							  : Allows the user to delete a file path if it exists.
							- [.writable()](https://www.codecademy.com/resources/docs/python/files/writable)
							  : Allows the user to check if a file is writable or not. The function will return True if the file is writable and accessed in append or write mode, and False if it was accessed in read mode.
							- [.write()](https://www.codecademy.com/resources/docs/python/files/write)
							  : Adds additional text to a file when the file is opened in append mode.
					- [Functions](https://www.codecademy.com/resources/docs/python/functions)
					  id:: 65d89c40-6df9-42a2-8c7f-0436ebaf7ac7
					  collapsed:: true
						- Some tasks need to be performed multiple times within a program. Rather than rewrite the same code in multiple places, a function may be defined using the `def` keyword. Function definitions may include parameters, providing data input to the function.
						- Syntax
							- ```python
							  def my_function(value):
							    return value + 1
							  
							  print(my_function(2))
							  print(my_function(3 + 5))
							  ```
							- Functions may return a value using the `return` keyword followed by a `value`. They can then be called, or invoked, elsewhere in the program. The output from the snippet above would look like this:
							- ```python
							  3
							  9
							  ```
							- **Note:** Function names in Python are written in snake_case.
						- Return Values
							- The `return` keyword is used to return a value from a Python function. The value returned from a function can be assigned to a variable which can then be used in the program.
							- In the example below, the `check_leap_year()` function returns a string that indicates if the passed parameter is a leap year or not.
							- ```python
							  def check_leap_year(year):
							    if year % 4 == 0:
							      return str(year) + " is a leap year."
							    else:
							      return str(year) + " is not a leap year."
							  
							  year_to_check = 2018
							  
							  returned_value = check_leap_year(year_to_check)
							  
							  print(returned_value)
							  ```
							- The resulting output will look like this:
							  `2018 is not a leap year.`
						- Returning Values With `yield`
							- A function can also return values with the `yield` keyword. Like `return`, `yield` suspends the function’s execution and returns the value specified. Unlike `return`, the `yield` statement retains the state of the function and will resume where it left off on the next function call (i.e. execution resumes after the last `yield` statement). This way, the function can produce a number of values over time.
							- Functions using `yield` rather than `return` are known as [generator](https://www.codecademy.com/resources/docs/python/generators) functions. Such a function can be used as an [iterator](https://www.codecademy.com/resources/docs/python/iterators).
							- The example below will automatically generate successive Fibonacci numbers.
								- ```python
								  # Function to produce infinite Fibonacci numbers
								  def fibonacci():
								    # Generate first number
								    a = 1
								    yield a
								  
								    # Generate second number
								    b = 1
								    yield b
								  
								    # Infinite loop
								    while True:
								      # Return sum of a + b
								      c = a + b
								      yield c
								      # Function resumes loop here on next call
								      a = b
								      b = c
								  
								  # Iterate through the Fibonacci sequence until a limit is reached
								  for num in fibonacci():
								    if num > 50:
								      break
								    print(num)
								  ```
							- This will output the following:
								- ```
								  1
								  1
								  2
								  3
								  5
								  8
								  13
								  21
								  34
								  ```
						- Higher-Order Functions
							- In Python, functions are treated as first-class objects. This means that they can be assigned to variables, stored in data structures, and passed to or returned from other functions.
							- Functions are considered to be “higher-order” values because they can be used as parameters or return values for other functions. One example is the built-in `filter()` function:
							- ```python
							  # Returns True if n is a perfect square, and False otherwise
							  
							  def is_perfect_square(n):
							    return (n ** 0.5).is_integer()
							  
							  numbers = [3, 4, 37, 9, 7, 32, 25, 81, 79, 100]
							  
							  perfect_squares = filter(is_perfect_square, numbers)
							  
							  print(list(perfect_squares))
							  ```
							- `filter()` takes a predicate (a function that returns a boolean value) and an iterable, and returns a new iterable containing all elements of the first one that makes the predicate true.
						- [Anonymous Functions](https://www.codecademy.com/resources/docs/python/functions/anonymous-functions)
						  Defines a function without a name using the lambda keyword
						- [Arguments/Parameters](https://www.codecademy.com/resources/docs/python/functions/arguments-parameters)
						  Supplies data to a defined function when it is called in a program
					- [Functools Module](https://www.codecademy.com/resources/docs/python/functools-module)
					- [Generators](https://www.codecademy.com/resources/docs/python/generators)
					- [Glob Module](https://www.codecademy.com/resources/docs/python/glob-module)
					- [IDLE](https://www.codecademy.com/resources/docs/python/idle)
					- [Inheritance](https://www.codecademy.com/resources/docs/python/inheritance)
					- [Iterators](https://www.codecademy.com/resources/docs/python/iterators)
					  id:: 663a579f-35a7-4aaa-bb87-ccd05d776239
						- In Python, an iterator is an object representing a collection of elements (such as data or methods) where each element can be accessed by traversing through the collection to perform the required tasks.
						- An iterator supports the `next()` function which takes no arguments and always returns the next element of the collection. When all elements are exhausted, it returns the `StopIteration` exception.
						- # Iterables
							- Objects that can be converted into iterators are called iterables. Datatypes such as lists, tuples, dictionaries, and sets are iterable, meaning that they can be converted into iterators using the `iter()` function.
							- The difference between an iterable and an iterator can be easily be understood by considering iterable as a birthday cake that we need to distribute to a number of people. We cut cake into several pieces using the `iter()` function to get an iterator. Then we use `next()` to distribute each piece.
							- Also, it is important to understand that all iterators are iterable but the converse is not true.
						- # Code for an Iterator using a List
							- The following code shows the generation of an iterator from a list using the `iter()` function and usage of the `next()` function by manually iterating through all the items of the iterator. When there are no more elements left in an iterator, it returns the `StopIteration` exception.
							- **Note:** Once an iterator has been iterated through, it cannot be re-iterated again.
							- ```python
							  # Defining list cake, which is iterable
							  cake = ["piece1", "piece2", "piece3"]
							  
							  # Converting list into an iterator using iter() function
							  cake_ready_to_distribute = iter(cake)
							  
							  # Iterating through iterator, returns piece1
							  print(next(cake_ready_to_distribute))
							  
							  # Iterating through iterator, returns piece2
							  print(next(cake_ready_to_distribute))
							  
							  # Iterating through iterator, returns piece3
							  print(next(cake_ready_to_distribute))
							  
							  # Iterating through iterator, returns StopIteration exception
							  try:
							    print(next(cake_ready_to_distribute))
							  except StopIteration:
							    print("stop iteration error")
							  ```
						- # Iterator in a `for` loop
							- The `for` loop has built-in `iter()` and `next()` functions, which allows running iterations more elegantly.
							- ```python
							  # Defining list cake, which is iterable
							  cake = ["piece1", "piece2", "piece3"]
							  
							  # The for loop itself convert iterable into iterator and returns elements
							  for piece in cake:
							    print(piece)
							  ```
						- # Iteration using a `while` loop
							- The `while` loop does not have the built-in `iter()` and `next()` functions as in the `for` loop, so the `iter()` and `next()` functions need to be used separately.
							- ```python
							  # Defining list cake, which is iterable
							  cake = ["piece1", "piece2", "piece3"]
							  
							  # Converting list into iterator using iter() function
							  cake_ready_to_distribute = iter(cake)
							  
							  # Initiate a infinite loop which stops when the iterator is exhausted
							  while True:
							    try:
							      # Printing the next piece
							      print(next(cake_ready_to_distribute))
							    except StopIteration:
							      # If StopIteration is raised, break from loop
							      break
							  ```
						- # Creating a User-Defined Iterable Object
							- Since an iterable object is an object that can be converted into Iterator, for an object to be iterable it needs to support the `iter()` function and the iterator generated must also support `next()`.
							- ```python
							  class cake:
							    def __init__(self, maxPieces=0):
							      self.maxPieces = maxPieces
							  
							    def __iter__(self):
							      self.piece = 0
							      return self
							  
							    def __next__(self):
							      if self.piece < self.maxPieces:
							        self.piece += 1
							        return "piece" + str(self.piece)
							      else:
							        raise StopIteration
							  
							  # Creating object cake along with number of pieces to be distributed
							  cake_before_cutting = cake(10)
							  
							  # The object cake is iterable as we defined iter function
							  cake_after_cutting = iter(cake_before_cutting)
							  
							  while True:
							    try:
							      # Printing next piece
							      print(next(cake_after_cutting))
							    except StopIteration:
							      # If StopIteration is raised, break from loop
							      break
							  ```
							- In the above code, built-in `iter()` function is equivalent to user-defined `__iter__()` method, when `iter()` function is invoked it invokes `__iter__()` method after checking the data type of input argument.
							- Similarly, `next(cake_after_cutting)` is same as `cake_after_cutting.__next__()`. When `next()` function is invoked it invokes `__next__()` method after checking data type of input argument.
						- # Related:
							- ((65d89c40-b7d3-412b-a6cc-dbcc033d73ee))
							- ((663a579f-a6ac-4bc6-a2a9-05d3031ea2f1)) : ((66be2f9b-6fa5-42f3-9a07-092ba50ada7f))
					- [JSON Module](https://www.codecademy.com/resources/docs/python/json-module)
					- [Keywords](https://www.codecademy.com/resources/docs/python/keywords)
					  collapsed:: true
						- Certain keywords are reserved in Python and are not available to be assigned as variables or named functions. There are many keywords where some specialize in control-flow (e.g. `if/else` and `for`) while others work as [operators](https://www.codecademy.com/resources/docs/python/operators) (e.g. `and`, `in`, and `is`).
						- Keywords
							- [assert](https://www.codecademy.com/resources/docs/python/keywords/assert)
							  Confirms the truthiness of a given statement.
							- [class](https://www.codecademy.com/resources/docs/python/keywords/class)
							  Used for defining classes in Python.
							- [del](https://www.codecademy.com/resources/docs/python/keywords/del)
							  Removes an object from the namespace of a Python shell or environment.
							- [global](https://www.codecademy.com/resources/docs/python/keywords/global)
							  Creates a global variable that can be updated.
							- ((660c1753-1d46-4507-9c99-996d98c85e21))
							- [lambda](https://www.codecademy.com/resources/docs/python/keywords/lambda)
							  Produces an anonymous function expression.
					- [Lists](https://www.codecademy.com/resources/docs/python/lists)
					  id:: 65d89c40-5e6f-4b12-b1cc-5d93e2b320cc
					  collapsed:: true
					  Equivalent to [[JavaScript]] : ((64024e3f-2a66-4456-816f-f0b00cfd0c4e))
						- A **list** in Python is a sequence [data type](https://www.codecademy.com/resources/docs/python/data-types) used for storing a comma-separated collection of objects in a single [variable](https://www.codecademy.com/resources/docs/python/variables). Lists are always ordered and can contain different types of objects (strings, integers, booleans, etc.). Since they are mutable data types, lists are a good choice for dynamic data (that may be added or removed over time).
						- ### Syntax
							- ```python
							  # With square brackets
							  list_a = []
							  
							  # With built-in function
							  list_b = list()
							  ```
							- Lists can either be defined with square brackets (`[]`) or with the built-in `list()` constructor method. In any case, the values initially passed to the new list must be comma-separated.
							- The following example showcases how lists can hold items of the same type or a mix of different types:
								- ```python
								  list_1 = [1, 2, 3, 4, 5, 6, 7, 8, 9]
								  
								  list_2 = ["one", 2, "3"]
								  ```
						- ### Stacks and Queues
							- Python lists can also be made to behave like stacks and queues.
							- Stacks follow a “last-in, first-out” insertion order. This behavior can be showcased with the [`.append()`](https://www.codecademy.com/resources/docs/python/lists/append) and [`.pop()`](https://www.codecademy.com/resources/docs/python/lists/pop) methods for adding to and removing from the top of the stack, respectively:
								- ```python
								  stack_example = ["a", "b", "c"]
								  print(stack_example)
								  # Output: ['a', 'b', 'c']
								  
								  stack_example.append(1)
								  stack_example.append(2)
								  stack_example.append(3)
								  print(stack_example)
								  # Output: ['a', 'b', 'c', 1, 2, 3]
								  
								  stack_example.pop()
								  stack_example.pop()
								  print(stack_example)
								  # Output: ['a', 'b', 'c', 1]
								  ```
							- Queues follow a “first-in, first-out” insertion order and also utilize the `.append()` and `.pop()` methods:
								- ```python
								  queue_example = ["a", "b", "c"]
								  print(queue_example)
								  # Output: ['a', 'b', 'c']
								  
								  queue_example.append(1)
								  queue_example.append(2)
								  print(queue_example)
								  # Output: ['a', 'b', 'c', 1, 2]
								  
								  queue_example.pop(0)
								  print(queue_example)
								  # Output: ['b', 'c', 1, 2]
								  ```
							- While using a list as a queue is possible, it is not efficient because applying `.pop()` to the first item requires shifting all remaining items by one spot and reassigning indices. Instead, a `deque` object from the [`collections`](https://www.codecademy.com/resources/docs/python/collections-module) module should be used to efficiently add/remove from a queue.
						- Video Walkthrough
							- Watch this video for a step-by-step demonstration on how to create and edit Python lists.
							- https://www.youtube.com/embed/mZdNLYYJNis
						- ### List Methods
						  
						  id:: 65db6f41-c061-4796-8542-1b1a66dfe81d
							- [.append()](https://www.codecademy.com/resources/docs/python/lists/append)
							  id:: 65db6f46-9518-4bf2-ac3e-7ab95a0207c0
							  collapsed:: true
							  Adds an item to end of the list | Equivalent to [[JavaScript]] : ((63679853-975f-4456-b131-53731a001078))
								- The Python list method `.append()` adds an item to the end of a list.
								- Syntax
									- ```python
									  list.append(item)
									  ```
									- The `.append()` will place the object passed in as a new element at the very end of the list. Printing the list afterwards will visually show the appended value.
									- This method is not to be confused with returning an entirely new list with the passed object.
								- Example
									- To add `'🥚'` to the end of the `grocery` list:
									- ```python
									  grocery = ['🍉', '🍪', '🥬', '🥕']
									  
									  grocery.append('🥚')
									  
									  print(grocery)
									  # Output: ['🍉', '🍪', '🥬', '🥕', '🥚']
									  ```
								- Codebyte Example
									- To add `'tulips'` to the end of the `orders` list:
									  
									  ```python
									  orders = ['daisies', 'periwinkle']
									  
									  orders.append('tulips')
									  
									  print(orders)
									  ```
							- [.clear()](https://www.codecademy.com/resources/docs/python/lists/clear)
							  Removes all items from the list.
							- [.copy()](https://www.codecademy.com/resources/docs/python/lists/copy)
							  Returns a shallow copy of a list.
							- [.count()](https://www.codecademy.com/resources/docs/python/lists/count)
							  Searches a list for a particular item and returns the number of matching entries found.
							- [.extend()](https://www.codecademy.com/resources/docs/python/lists/extend)
							  Adds list elements to end of the list.
							- [.index()](https://www.codecademy.com/resources/docs/python/lists/index)
							  Finds the first occurrence of a particular value within the list.
							- [.insert()](https://www.codecademy.com/resources/docs/python/lists/insert)
							  collapsed:: true
							  Adds an item at a specified index in the list.
								- Adds an item at a specified index in the list.
								- ## Syntax
									- ```python
									  list.insert(index, item)
									  ```
									  
									  The `.insert()` method takes in two parameters:
									- The index that you want to insert into.
									- The item that you want to insert at the specified index.
								- ## Example
									- To add an item at index 2 of `store_line` list:
									- ```python
									  store_line = ['Karla', 'Maxium', 'Martim', 'Isabella']
									  
									  store_line.insert(2, 'Vikor')
									  
									  print(store_line)
									  # Output: ['Karla', 'Maxium', 'Vikor', 'Martim', 'Isabella']
									  ```
									- ```python
									  friends = ["Annabelle", "Greg", "Katya", "Sol"]
									  
									  friends.insert(-3, "Gus")
									  # ["Annabelle", "Gus", "Greg", "Katya", '"Sol"].
									  
									  friends.insert(-3, "Gus")
									  # ["Annabelle", "Greg", "Gus", Katya", "Sol"]
									  ```
							- [.pop()](https://www.codecademy.com/resources/docs/python/lists/pop)
							  Removes an item from a list while also returning it.
								- `pop()` with no number will pop the last element off
							- [.remove()](https://www.codecademy.com/resources/docs/python/lists/remove)
							  id:: 65db6f73-6378-4c36-8946-62803f98824f
							  collapsed:: true
							  Removes an item from a list by passing in the value of the item to be removed as an argument.
								- The `.remove()` method removes an item from a list by passing in the value of the item to be removed as an argument.
								- Syntax
									- ```python
									  list.remove(item)
									  ```
									- In the case where two or more elements in the list have the same value, the first occurrence of the element is removed.
								- Example
									- ```python
									  inventory = ['⚽', '🏀', '⚾️', '🎾', '🏐']
									  
									  inventory.remove('⚾️')
									  
									  print(inventory)
									  # Output: ['⚽', '🏀', '🎾', '🏐']
									  ```
								- Codebyte Example
									- To remove the first occurrence of `'eggs'`:
									- ```python
									  grocery_list = ['blueberries', 'mochi', 'eggs', 'chocolate']
									  
									  grocery_list.remove('eggs')
									  
									  print(grocery_list)
									  ```
							- [.reverse()](https://www.codecademy.com/resources/docs/python/lists/reverse)
							  Reverse the elements in the list.
							- [.sort()](https://www.codecademy.com/resources/docs/python/lists/sort)
							  Sorts the contents of the list it is called on.
							- ### [More methods](https://docs.python.org/3/library/array.html)
					- [Loops](https://www.codecademy.com/resources/docs/python/loops)
					  id:: 65d89c40-b7d3-412b-a6cc-dbcc033d73ee
					  collapsed:: true
						- A **loop** is a control structure that can execute a statement or group of statements repeatedly. Python has three types of loops: `while` loops, `for` loops, and nested loops.
						- # While Loops
						  id:: 13052bf3-e6e0-4b13-821e-fb77716ce0ff
							- A `while` loop will repeatedly execute a code block as long as a condition evaluates to `True`.
							- The condition of a `while` loop is always checked first before the block of code runs. If the condition is not met initially, then the code block will never run.
							- ```python
							  while condition:
							    # Code inside
							  ```
							- This loop will only run 1 time:
								- ```python
								  hungry = True
								  
								  while hungry:
								    print("Time to eat!")
								    hungry = False
								  ```
							- This loop will run 5 times:
								- ```python
								  i = 1
								  
								  while i < 6:
								    print(i)
								    i = i + 1
								  ```
							- ((65db1e62-50fc-441b-94c9-c70aeca3a724)) can be used to help iterate over lists
								- Example
									- ```python
									  ingredients = ["milk", "sugar", "chocolate"]
									  index = 0
									  
									  while index < len(ingredients):
									    print(ingredients[index])
									    index += 1
									  ```
						- # For Loop
						  id:: 2db45cf2-69a5-46d9-aacb-fcf40f7f4480
							- A `for` loop can be used to iterate over and perform an action one time for each element in a list.
							- Proper for loop syntax assigns a temporary value, the current item of the list, to a variable on each successive iteration:
								- ```python
								  for <temporary variable> in <collection>:
								    <action>
								  ```
							- `for` loop bodies must be indented to avoid an `IndentationError`.
								- ```python
								  dog_breeds = ["boxer", "bulldog", "shiba inu"]
								  
								  # Print each breed:
								  for breed in dog_breeds:
								    print(breed)
								  ```
							- Equivalent to [[JavaScript]] : ((635eb08f-a372-4f5b-9072-e574620dbea4))
								- #+BEGIN_TIP
								  To do a standard [[JavaScript]] : ((63679853-6e6e-4fce-87bc-93f106c2e05d)) loop you should ((65ddf492-2ab5-4bc6-8b0c-bd8a65ed3850)) or instead use ((13052bf3-e6e0-4b13-821e-fb77716ce0ff)) (`e.g. i = 0 /n while i < 6:`)
								  #+END_TIP
							- Combine with ((65db1e62-be7f-411d-b0a2-da3027dd6c7e)) to perform an arbitrary number of iterations
							  id:: 65ddf492-2ab5-4bc6-8b0c-bd8a65ed3850
								- #+BEGIN_TIP
								  The temporary variable (i) is still zero-indexed.
								  #+END_TIP
								- Example
									- ```python
									  for i in range(6):
									    print("This is iteration number", str(i+1)) # prints as a string
									  ```
						- # Nested Loops
							- Loops can be nested inside other loops. Nested loops can be used to access items of lists which are inside other lists. The item selected from the outer loop can be used as the list for the inner loop to iterate over.
							- ```python
							  groups = [["Jobs", "Gates"], ["Newton", "Euclid"], ["Einstein", "Feynman"]]
							  
							  # This outer loop will iterate over each list in the groups list
							  for group in groups:
							    # This inner loop will go through each name in each list
							    for name in group:
							      print(name)
							  ```
						- # `break` Keyword
							- In a loop, the `break` keyword escapes the loop, regardless of the iteration number. Once break executes, the program will continue to execute after the loop.
							- ```python
							  numbers = [0, 254, 2, -1, 3]
							  
							  for num in numbers:
							    if (num < 0):
							      print("Negative number detected!")
							      break
							    print(num)
							  ```
							- In this example, the output would be:
								- ```
								  0
								  254
								  2
								  Negative number detected!
								  ```
						- # `continue` Keyword
							- The `continue` keyword is used inside a loop to skip the remaining code inside the loop code block and begin the next loop iteration.
							- Example
								- ```python
								  big_number_list = [1, 2, -1, 4, -5, 5, 2, -9]
								  
								  # Print only positive numbers:
								  for i in big_number_list:
								    if i < 0:
								      continue
								    print(i)
								  ```
						- # Video Walkthrough
							- In this video, you will learn how to use the for and while loops in a Python script.
							- https://www.youtube.com/embed/qKjJFz4lUoQ
						- # Related:
						  id:: 663a579f-b5da-43b8-853d-ab0cc219276e
							- ((663a579f-35a7-4aaa-bb87-ccd05d776239))
							- ((66be2e28-8809-49b5-a5f2-853321eec973))
							- ((65ddfba0-5a45-403b-9cba-2dda61f844fc))
					- [Math Module](https://www.codecademy.com/resources/docs/python/math-module)
					- [Memoization](https://www.codecademy.com/resources/docs/python/memoization)
					- [Modules](https://www.codecademy.com/resources/docs/python/modules)
					  id:: 65d89c40-9430-4a7d-add8-41e1ecdb916d
					  collapsed:: true
						- A **module** is a Python file that contains functions, definitions, and statements that can be included in other files within an application. Technically, all files with the `.py` [format](https://www.codecademy.com/resources/docs/general/file-formats) are modules.
						- Conceptually, modules are named units of code that can be reused across applications and allows us to access shared libraries (collections of modules) and packages (modules with nested modules and packages). Instead of entering commands directly into a Python interpreter, code can be saved as a module for later use in other applications.
						- Creating and Importing Modules
						  collapsed:: true
							- A module can be created by saving a Python file with the `.py` file extension. It can then be imported into another `.py` file with an `import` statement.
							- For example, a separate `video_player.py` file that was previously saved can be imported in other files:
							- ```python
							  import video_player # Import the whole module
							  from module_name import object_name # If you just want to import one object from a module
							  ```
							- The program now has access to all functions, objects, and statements contained within the `video_player` module.
						- Importing Specific Resources
						  collapsed:: true
							- Instead of importing the whole module, individually named resources can be specified. For example:
							- ```python
							  from video_player import VideoPlayer
							  ```
							- This will import only the `VideoPlayer` class from a given `video_player` module, rather than all types of collections contained within it.
							- It’s often useful to import only what is needed to avoid slowing the program down and polluting the local namespace where the code runs.
						- Namespaces and Scope
						  id:: 56f64c9f-11b9-4643-9394-8b8108489567
							- By default the namespace of imported modules is that of the module, but you can create an alias for it using the `as` keyword. For example:
								- ```python
								  from bs4 import BeautifulSoup as bs
								  ```
								- Aliasing is especially convenient for shortening module names and managing the local namespace where our code executes.
							- Once a module is imported, it is within the scope of the program and it can be accessed in the local namespace.
							- What are namespaces?
								- Basically the name we reference an imported module as (basically a ((65d89c40-625d-40b7-b0f3-3fd9052902d4)) )
								- Your local namespace is where your code is run
							- Not best practice: you can import every ((65d89c40-625d-40b7-b0f3-3fd9052902d4)) / ((65d89c40-6df9-42a2-8c7f-0436ebaf7ac7)) / ((65d89c40-9115-428b-8046-fe014e270fd9)) from a module by using:
								- ```python
								  from module_name import *
								  ```
								- #+BEGIN_WARNING
								  This could **pollute** our local namespace if you already have data with the same name in the local namespace.
								  #+END_WARNING
						- Other notes
							- Files are modules, so they can be imported into each other
						- Python Standard Modules
						  id:: 65db653f-a199-4d92-b73e-4141827f782a
							- Python comes with several different built-in modules that provide a variety of functions. They include:
								- [`collections`](https://www.codecademy.com/resources/docs/python/collections-module)
								  Provides additional collection types.
								- The [`functools`](https://www.codecademy.com/resources/docs/python/functools-module) module provides functions supporting a [functional programming](https://www.codecademy.com/resources/docs/general/programming-paradigms/functional-programming) approach.
								- The [`glob`](https://www.codecademy.com/resources/docs/python/glob-module) module allows matching file paths per [Unix](https://www.codecademy.com/resources/docs/general/unix) shell rules.
								- The [`json`](https://www.codecademy.com/resources/docs/python/json-module) module provides functions for dealing with [JSON](https://www.codecademy.com/resources/docs/general/json) objects.
								- The [`math`](https://www.codecademy.com/resources/docs/python/math-module) module provides useful mathematical functions.
								- [`random`](https://www.codecademy.com/resources/docs/python/random-module)
								  id:: 65db64bc-91d6-4bef-af12-d0e30aa637ec
								  collapsed:: true
								  Provides functions for dealing with random numbers
									- In Python, the built-in [`random` module](https://docs.python.org/3/library/random.html) is used to randomly generate numbers as well as randomly manipulate collections such as [lists](https://www.codecademy.com/resources/docs/python/lists) and [strings](https://www.codecademy.com/resources/docs/python/strings).
									- This module can be used when imported at the top of a Python file:
										- ```python
										  import random
										  ```
									- The `random` variable can then be used for executing the module’s built-in methods, like the ((3ad4bcfe-9557-48f9-b45e-094ba0912853)) method below:
										- ```python
										  random.random()
										  ```
									- ## Methods
										- [.choice()](https://www.codecademy.com/resources/docs/python/random-module/choice)
										  Returns a random item chosen from an iterable argument, such as a list or a dictionary.
										- [.randint()](https://www.codecademy.com/resources/docs/python/random-module/randint)
										  id:: 2c036eaa-7495-44d3-9b78-b267a49b0350
										  collapsed:: true
										  Returns a random integer that exists between two values.
											- The `.randint()` method returns a random integer that exists between two `int` values, `int_a` and `int_b` (inclusive), passed as arguments.
											- ## Syntax
												- ```python
												  random.randint(int_a, int_b)
												  ```
												- Another way of writing this would be `random.randrange(int_a, int_b + 1)`.
											- ## Example
												- In the example below, `.randint()` is used to return a random number between `0` and `50`:
												- ```python
												  import random
												  
												  print(random.randint(0, 50))
												  ```
											- ## Codebtye Example
												- The `.randint()` method can also be applied to negative `int` values, as shown in the example below:
												- ```python
												  import random
												  
												  print(random.randint(-25, 25))
												  ```
										- [.random()](https://www.codecademy.com/resources/docs/python/random-module/random)
										  id:: 3ad4bcfe-9557-48f9-b45e-094ba0912853
										  Returns a pseudo-random floating-point number between 0 and 1.
										- [.randrange()](https://www.codecademy.com/resources/docs/python/random-module/randrange)
										  Selects a random number from a defined range of int values.
										- [.sample()](https://www.codecademy.com/resources/docs/python/random-module/sample)
										  collapsed:: true
										  Returns a list of items randomly selected from a given population.
											- ```python
											  #random.sample takes a list and randomly selects k items from it
											  new_list = random.sample(list, k)
											  #for example:
											  nums = [1, 2, 3, 4, 5]
											  sample_nums = random.sample(nums, 3)
											  print(sample_nums) # 2, 5, 1
											  ```
										- [.seed()](https://www.codecademy.com/resources/docs/python/random-module/seed)
										  Initializes a pseudo-random number generator with a seeded value and sets the first number.
										- [.shuffle()](https://www.codecademy.com/resources/docs/python/random-module/shuffle)
										  Takes a list and randomly re-orders the items.
										- [.uniform()](https://www.codecademy.com/resources/docs/python/random-module/uniform)
										  Returns a pseudo-random floating-point number between two given numbers.
								- The [`time`](https://www.codecademy.com/resources/docs/python/time-module) module provides various functions for dealing with time.
							- Others
								- ((65d89c40-b341-4a75-8002-a6020e483cce))
								- [decimal](https://docs.python.org/3/library/decimal.html)
								  id:: 65f57be5-b68a-4416-b862-1dcea566717a
								  collapsed:: true
									- ```python
									  from decimal import Decimal
									  
									  cost_of_gum = Decimal('0.10') # instead of `0.10`
									  cost_of_gumdrop = Decimal('0.35') # instead of `0.35`
									  
									  cost_of_transaction = cost_of_gum + cost_of_gumdrop
									  # Returns 0.45 instead of 0.44999999999999996
									  ```
						- Python Third-Party Modules
							- Python has a very broad selection of third-party modules that are devoted to particular tasks.
							- These are third-party Python modules that have topic entries:
								- [NumPy](https://www.codecademy.com/resources/docs/numpy): a popular open-source Python library used for complex mathematical operations and multi-dimensional [arrays](https://www.codecademy.com/resources/docs/general/data-structures/array).
								- [Pandas](https://www.codecademy.com/resources/docs/pandas): a popular open-source Python module used for data analysis and manipulation.
							- Below is a selection of other third-party modules of note:
								- [PySpark](https://www.codecademy.com/resources/docs/python/modules/pyspark)
								  A Python API for Apache Spark, consisting of several modules.
								- [Pytorch](https://www.codecademy.com/resources/docs/python/modules/pytorch)
								  An open-source framework that offers an optimized tensor library for deep learning.
								- [tqdm](https://www.codecademy.com/resources/docs/python/modules/tqdm)
								  A module that allows the generation of progress bars in Python.
					- [Modulo](https://www.codecademy.com/resources/docs/python/modulo)
					- [Operators](https://www.codecademy.com/resources/docs/python/operators)
					  collapsed:: true
						- ...
						- ## Arithmetic Operators
							- Python has the following arithmetic operators:
								- Addition, `+`, which returns the sum of two numbers.
								- Subtraction, `-`, which returns the difference of two numbers.
								- Multiplication, `*`, which returns the product of two numbers.
								- Division, `/`, which returns the quotient of two numbers.
								- Exponentiation, `**`, which returns the value of one number raised to the power of another.
								  id:: 65d50428-aecf-445e-b34c-d057af1304f9
								  collapsed:: true
									- Examples
										- ```python
										  # 2 to the 10th power, or 1024
										  print(2 ** 10)
										  
										  # 8 squared, or 64
										  print(8 ** 2)
										  
										  # 9 * 9 * 9, 9 cubed, or 729
										  print(9 ** 3)
										  
										  # We can even perform fractional exponents
										  # 4 to the half power, or 2
										  print(4 ** 0.5)
										  ```
								- Modulus, `%`, which returns the remainder of one number divided by another.
								- Floor division, `//`, which returns the integer quotient of two numbers.
						- ## Assignment Operators
						  id:: 65d50b2d-a4bb-450f-a1a4-4f89dbe58909
							- Python includes the following assignment operators:
								- The `=` operator assigns the value on the right to the variable on the left.
								- The `+=` operator updates a variable by incrementing its value and reassigning it.
								  id:: 65d50b2d-0218-44f6-b846-780f44c83035
								- The `-=` operator updates a variable by decrementing its value and reassigning it.
								- The `*=` operator updates a variable by multiplying its value and reassigning it.
								- The `/=` operator updates a variable by dividing its value and reassigning it.
								- The `%=` operator updates a variable by calculating its modulus against another value and reassigning it.
						- ## Comparison Operators
						  id:: 65d89c40-7642-4d2d-a9d6-f9cc38fac471
						  AKA Comparators AKA relational operators
							- Python has the following comparison operators:
								- `==`
								  AKA Equal to | Returns`True` if two values are equal.
								- `!=`
								  AKA Not equal to | Returns `True` if two values are not equal.
								- Less than, `<`, for returning `True` if left value less than right value.
								- Less than or equal to, `<=`, for returning `True` if left value is less than or equal to right value.
								- Greater than, `>`, for returning `True` if left value greater than right value.
								- Greater than or equal to, `>=`, for returning `True` if left value greater than or equal to right value.
						- ## Logical Operators
						  
						  id:: 65d89c40-e967-456c-8274-451ef31462e2
						  AKA Boolean operators
							- Python has the following logical operators:
								- `and`
								  Returns `True` if both statements are `True`.
									- Examples
										- ```python
										  (1 + 1 == 2) and (2 + 2 == 4)   # True
										  
										  (1 > 9) and (5 != 6)            # False
										  
										  (1 + 1 == 2) and (2 < 1)        # False
										  
										  (0 == 10) and (1 + 1 == 1)      # False
										  ```
								- `or`
								  Returns `True` if either statement is `True`.
									- Only one component needs to be `True` for an or statement to be `True`.
									- Examples
										- ```python
										  True or (3 + 4 == 7)    # True
										  (1 - 1 == 0) or False   # True
										  (2 < 0) or True         # True
										  (3 == 8) or (3 > 4)     # False
										  ```
								- `not`
								  Returns `True` if its associated statement is `False`.
									- Examples
										- ```python
										  not True == False
										  not False == True
										  
										  not 1 + 1 == 2  # False
										  not 7 < 0       # True
										  
										  if not credits >= 120:
										    print("You do not have enough credits to graduate.")
										  
										  if not credits >= 120 and not gpa >= 2.0:
										    print("You do not meet either requirement to graduate!")
										  ```
						- ## Order of Operations
						  id:: 65d4f537-1a1c-4df6-9305-4b70aacbc0c2
							- Python evaluates an expression in order of precedence as follows:
								- Items in parentheses, (`(`…`)`), have the highest level of precedence, expressions within them are evaluated first.
								- Exponentiation (`**`)
								- Multiplication and division operators (`*`, `/`, `//` & `%`)
								- Addition and subtraction (`+` & `-`)
								- Comparison (`<`, `<=`, `>` & `>=`)
								- Equality (`==` & `!=`)
								- `not`
								- `and`
								- `or`
							- **Note:** Items at the same precedence are evaluated left to right. The exception to this is exponentiation, which evaluates right to left.
					- [OS Path Module](https://www.codecademy.com/resources/docs/python/os-path-module)
					- [pip](https://www.codecademy.com/resources/docs/python/pip)
					- [Random Module](https://www.codecademy.com/resources/docs/python/random-module)
					- [Recursion](https://www.codecademy.com/resources/docs/python/recursion)
					- [Regular Expressions](https://www.codecademy.com/resources/docs/python/regex)
					  id:: 65d89c40-dc16-48dd-a5b8-8ade7bf2be04
					- [Requests Module](https://www.codecademy.com/resources/docs/python/requests-module)
					- [Scope](https://www.codecademy.com/resources/docs/python/scope)
					- [Sets](https://www.codecademy.com/resources/docs/python/sets)
					  id:: 65d89c40-7296-46fa-91a4-f6147b1f3e9e
					  collapsed:: true
						- A set is an unordered collection of elements without any duplicates.
						- Sets are especially useful for performing logical operations like finding the union, intersection, or difference between collections of elements. For example, sets could be used to determine mutual friends on a social networking site.
						- Syntax
							- ```
							  set_A = set(iterable)
							  
							  set_B = {element_A, element_B, ..., elementZ}
							  ```
							  
							  There are several ways to create a set, which include:
							- Using the built-in [`set()`](https://www.codecademy.com/resources/docs/python/built-in-functions/set) function and passing in an optional `iterable` parameter.
							- Hard-coding a set with dictionary-like syntax (`{}`) where each element is unique.
						- Codebyte Example
							- In the example below, sets are created with lists and the `set()` function. The following observations can be made:
								- The first time the `animals` set is created with no parameters and printed, “set()” is printed to the shell.
								- When the `dog_breeds` set is created, it has duplicate elements with a `corgi` value that is reduced to one by the time the set is printed.
							- ```python
							  animals = set()
							  print(animals)
							  
							  animals = set(['aardvark', 'snail', 'squid'])
							  oceans = {'Pacific', 'Atlantic', 'Indian', 'Southern', 'Arctic'}
							  dog_breeds = {'pug', 'golden retriever', 'corgi', 'pug', 'corgi'}
							  
							  print("Animals:", animals)
							  print("Oceans:", oceans)
							  print("Dog Breeds:", dog_breeds)
							  ```
						- Methods
							- [.difference()](https://www.codecademy.com/resources/docs/python/sets/difference)
							- : Returns a new set of objects unique to a given set when compared to others.
							- [.discard()](https://www.codecademy.com/resources/docs/python/sets/discard)
							- : Removes a specified element from a set.
							- [.intersection()](https://www.codecademy.com/resources/docs/python/sets/intersection)
							- : Returns a new set with objects that exist inside two or more sets
							- [.isdisjoint()](https://www.codecademy.com/resources/docs/python/sets/isdisjoint)
							- : Checks whether two sets contain a common element in them.
							- [.issubset()](https://www.codecademy.com/resources/docs/python/sets/issubset)
							- : Checks whether all elements in one set exist within another specified set.
							- [.remove()](https://www.codecademy.com/resources/docs/python/sets/remove)
							- : Removes the specified element from a set.
							- [.union()](https://www.codecademy.com/resources/docs/python/sets/union)
							- : Returns a new set that combines objects from all sets involved, removing any duplicates.
							- [frozenset()](https://www.codecademy.com/resources/docs/python/sets/frozenset)
							- : Returns a new set or frozenset object whose elements are picked from a given iterable.
					- [Strings](https://www.codecademy.com/resources/docs/python/strings)
					  id:: 65d89c40-82d5-4a1f-aef4-2794999cccd6
					  collapsed:: true
						- ...
						- A string is a sequence of characters contained within a pair of single quotes (`'`) or double quotes(`"`). Strings can store words, sentences, or whole paragraphs. They can be any length and can contain letters, numbers, symbols, and spaces.
							- ```python
							  message1 = "I am a string"
							  message2 = 'I am also a string'
							  ```
						- Other [data types](https://www.codecademy.com/resources/docs/python/data-types) such as `integers`, `doubles`, and `booleans` can also be `strings` if they are wrapped in quotes.
							- | Example                    | String? |
							  | -------------------------- | ------- |
							  | “2” (with double-quotes)   | Yes ✅  |
							  | ‘3.6’ (with single-quotes) | Yes ✅  |
							  | “True” (also in quotes)    | Yes ✅  |
							  | 7 (integer)                | No ❌   |
							  | Hello (no quotes)          | No ❌   |
							  | True (boolean)             | No ❌   |
						- Strings are immutable; they cannot change. Every time an operation is performed on a string, a new string is created in memory.
						- # Accessing the Characters of a String
							- Strings in Python are technically a type of [list](https://www.codecademy.com/resources/docs/python/lists) — one in which each character is a separate element. This means each character in a string can be individually accessed by index, like with the elements in a list:
							- ```python
							  myString = "Hello, World!"
							  
							  var_1 = myString[0]
							  var_2 = myString[7:]
							  var_3 = myString[1:4]
							  
							  print("var_1: " + var_1) # Output: var_1: H
							  print("var_2: " + var_2) # Output: var_2: World!
							  print("var_3: " + var_3) # Output: var_3: ell
							  ```
							- If an attempt is made to access an index out of bounds, it will return an `IndexError`.
								- ```python
								  name = "phillis"
								  name[8] # Throws an IndexError
								  ```
						- # Multi-line Strings
							- Strings can be long or short. For longer text, a multi-line string can be used. Multi-line strings begin and end with three single or double quotes:
								- ```python
								  my_string = """If it were done when 'tis done, then 'twere well
								  It were done quickly: if the assassination
								  Could trammel up the consequence, and catch
								  With his surcease success; that but this blow
								  Might be the be-all and the end-all here,
								  But here, upon this bank and shoal of time,
								  We'ld jump the life to come."""
								  ```
						- # Escape Characters
							- Sometimes a string may have a character that Python tries to interpret, such as `'`.
								- ```python
								  my_string = 'It's a lovely day!'
								  
								  print(my_string)
								  ```
							- This will raise an error, because the interpreter thinks the second `'` marks the end of the string.
								- ```
								    File "main.py", line 1
								      my_string = 'It's a lovely day!'
								                      ^
								  SyntaxError: invalid syntax
								  ```
							- These characters can be “escaped” by adding a backslash beforehand. The `\` is called an escape character.
							- The backslash will not be visible if the string is printed:
								- ```python
								  my_string = 'It\'s a lovely day!'
								  
								  print(my_string)
								  # Output: It's a lovely day!
								  ```
							- This problem can be avoided by wrapping strings containing `'` characters in double quotes:
								- ```python
								  my_string = "It's a lovely day!"
								  
								  print(my_string)
								  # Output: It's a lovely day!
								  ```
							- Python also has a series of non-printing characters that can modify strings. For example, `\n` adds a new line and `\t` adds a tab:
								- ```python
								  note = "I am on top!\nI am on bottom. \n\tI am indented!"
								  print(note)
								  ```
							- This will output:
								- ```
								  I am on top!
								  I am on bottom.
								          I am indented!
								  ```
						- # Modifying Strings
							- Python has special [operators](https://www.codecademy.com/resources/docs/python/operators) to modify strings. For example, `+` can be used to concatenate strings, and `*` can be used to multiply a string. The keyword `in` can be used to see if a given character or substring exists in a `string`.
								- ```python
								  string_one = "Hello, "
								  string_two = "World! "
								  combo = string_one + string_two
								  
								  print(combo)
								  # Output: Hello, World!
								  
								  new_combo = combo * 2
								  
								  print(new_combo)
								  # Output: Hello, World! Hello, World!
								  
								  if "World" in new_combo:
								    print("It's here!")
								    # Output: It's here!
								  ```
							- Strings can also be formatted with either of the following:
							- The `f/F` flag (placed before the opening quotation mark).
							- The [.format()](https://www.codecademy.com/resources/docs/python/strings/format) method (requires manually adding placeholders).
						- # Comparing Strings
							- Python can use comparison [operators](https://www.codecademy.com/resources/docs/python/operators) to compare the contents of two strings. The operators behave as they do with numeric arguments:
							- | Operator | Term                     | Description                                                                              |
							  | -------- | ------------------------ | ---------------------------------------------------------------------------------------- |
							  | `==`     | Equal                    | Returns `True` if two strings are equal.                                                 |
							  | `!=`     | Not equal                | Returns `True` if two strings are not equal.                                             |
							  | `<`      | Less than                | Returns `True` if the left string is lexically prior the right string.                   |
							  | `>`      | Greater than             | Returns `True` is the left string comes lexically after the right string.                |
							  | `<=`     | Less than or equal to    | Returns `True` if the left string is equal to or lexically prior to the right string.    |
							  | `>=`     | Greater than or equal to | Returns `True` if the left string is equal to or comes lexically after the right string. |
							- The following example demonstrates string comparison:
								- ```python
								  string_one = "Hello"
								  string_two = "World"
								  
								  print(string_one > string_two)
								  print(string_one < string_two)
								  ```
						- # Built-in String Methods
						  id:: 663a579f-ea11-4ded-834a-f29a987bd3e6
							- Python has a number of built-in string methods that manipulate strings. However, when these methods are called, the original string will not be changed, so any modifications will need to be saved to a new variable. A few useful built-in string methods are listed below.
							- [.capitalize()](https://www.codecademy.com/resources/docs/python/strings/capitalize)
							  Takes in a string, and returns a copy of the string in capital case.
							- [.casefold()](https://www.codecademy.com/resources/docs/python/strings/casefold)
							  Returns a copy of the string with all characters in lowercase.
							- [.center()](https://www.codecademy.com/resources/docs/python/strings/center)
							  Returns a new string with the specified padding.
							- [.count()](https://www.codecademy.com/resources/docs/python/strings/count)
							  Finds the number of times the specified substring occurs within a given string.
							- [.encode()](https://www.codecademy.com/resources/docs/python/strings/encode)
							  Encodes a given string.
							- [.endswith()](https://www.codecademy.com/resources/docs/python/strings/endswith)
							  Checks whether or not a string ends with a given value.
							- [.find()](https://www.codecademy.com/resources/docs/python/strings/find)
							  Takes in a substring (and optionally start/end index), return the index number of the first occurrence of the substring inside a string.
							- [.format()](https://www.codecademy.com/resources/docs/python/strings/format)
							  Returns a string with values inserted via placeholders.
							- [.format_map()](https://www.codecademy.com/resources/docs/python/strings/format-map)
							  Returns the values from a given dictionary.
							- [.index()](https://www.codecademy.com/resources/docs/python/strings/index)
							  Searches through a string variable for the occurrence of a pattern or a substring.
							- [.isalnum()](https://www.codecademy.com/resources/docs/python/strings/isalnum)
							  Returns True if all the characters in a given string are alphanumeric.
							- [.isalpha()](https://www.codecademy.com/resources/docs/python/strings/isalpha)
							  Returns True if all characters in a string are letters of the alphabet, otherwise it returns False.
							- [.isascii()](https://www.codecademy.com/resources/docs/python/strings/isascii)
							  Returns True if all characters in a string are ASCII characters; otherwise, it returns False.
							- [.isdecimal()](https://www.codecademy.com/resources/docs/python/strings/isdecimal)
							  Checks whether a string consists of only decimal characters.
							- [.isdigit()](https://www.codecademy.com/resources/docs/python/strings/isdigit)
							  Checks if all the elements in the string are digits and returns a boolean flag.
							- [.isidentifier()](https://www.codecademy.com/resources/docs/python/strings/isidentifier)
							  Takes in a string and returns True if the string is a valid Python identifier, else returns False.
							- [.islower()](https://www.codecademy.com/resources/docs/python/strings/islower)
							  Takes in a string and returns True if all the letters in the string are in lowercase, else returns False. Ignores spaces, newlines, numeric and special characters in the string.
							- [.isnumeric()](https://www.codecademy.com/resources/docs/python/strings/isnumeric)
							  : Verifies that all the characters within the string variable are numeric.
							- [.isprintable()](https://www.codecademy.com/resources/docs/python/strings/isprintable)
							  Returns True if all characters in the string are printable or the string is empty, otherwise False if any character in the string is nonprintable.
							- [.isspace()](https://www.codecademy.com/resources/docs/python/strings/isspace)
							  Checks if all the characters in a string are whitespace characters.
							- [.istitle()](https://www.codecademy.com/resources/docs/python/strings/istitle)
							  Checks if a given string is in title case.
							- [.isupper()](https://www.codecademy.com/resources/docs/python/strings/isupper)
							  Takes in a string and returns True if all the letters in the string are in uppercase, else returns False. Ignores spaces, newlines, numeric and special characters in the string.
							- [.join()](https://www.codecademy.com/resources/docs/python/strings/join)
							  Concatenates all items from an iterable into a single string.
							- [.ljust()](https://www.codecademy.com/resources/docs/python/strings/ljust)
							  Left-aligns a string with a specified fill character
							- [.lower()](https://www.codecademy.com/resources/docs/python/strings/lower)
							  Takes a string, and returns a copy of that string in which all letters are lowercase. Numbers and symbols are not changed.
							- [.lstrip()](https://www.codecademy.com/resources/docs/python/strings/lstrip)
							  Removes leading characters from a string.
							- [.partition()](https://www.codecademy.com/resources/docs/python/strings/partition)
							  Searches a string for a given keyword and splits that string into a three part tuple.
							- [.replace()](https://www.codecademy.com/resources/docs/python/strings/replace)
							  Replace a specific substring with another substring.
							- [.rfind()](https://www.codecademy.com/resources/docs/python/strings/rfind)
							  Finds the last occurrence of a specified substring and returns the starting index.
							- [.rindex()](https://www.codecademy.com/resources/docs/python/strings/rindex)
							  Locates the highest index of the substring within a string variable.
							- [.rjust()](https://www.codecademy.com/resources/docs/python/strings/rjust)
							  Adds padding to the left of the given string.
							- [.rpartition()](https://www.codecademy.com/resources/docs/python/strings/rpartition)
							  Used to split a string into three parts based on a specified separator.
							- [.rsplit()](https://www.codecademy.com/resources/docs/python/strings/rsplit)
							  Splits a string into a list of substrings from the right end of the string based on a specified delimiter.
							- [.rstrip()](https://www.codecademy.com/resources/docs/python/strings/rstrip)
							  Removes trailing characters from a string.
							- [.split()](https://www.codecademy.com/resources/docs/python/strings/split)
							  Converts a string to a list. It takes a specified delimiter and a maximum number of items to split as optional parameters.
							- [.splitlines()](https://www.codecademy.com/resources/docs/python/strings/splitlines)
							  Used to split a multi-line string into a list of lines.
							- [.startswith()](https://www.codecademy.com/resources/docs/python/strings/startswith)
							  Checks whether or not a string starts with a given value.
							- [.strip()](https://www.codecademy.com/resources/docs/python/strings/strip)
							  Eliminates any trailing spaces at the beginning and end of a string. Specific characters can be passed in as an argument to be removed instead.
							- [.swapcase()](https://www.codecademy.com/resources/docs/python/strings/swapcase)
							  Takes a string and returns a copy of that string in which all lowercase letters are uppercase, and all uppercase letters are lowercase. Numbers and symbols are not changed.
							- [.title()](https://www.codecademy.com/resources/docs/python/strings/title)
							  Takes in a string and returns a copy of the string formatted in the title case: each word in the string is capitalized.
							- [.translate()](https://www.codecademy.com/resources/docs/python/strings/translate)
							  Replaces characters in a string based on a mapping table.
							- [.upper()](https://www.codecademy.com/resources/docs/python/strings/upper)
							  Takes a string, and returns a copy of that string in which all letters are uppercase. Numbers and symbols are not changed.
							- [.zfill()](https://www.codecademy.com/resources/docs/python/strings/zfill)
							  Returns a string with zeros padding the left side based on the integer given.
							- [maketrans()](https://www.codecademy.com/resources/docs/python/strings/maketrans)
							  Returns a transition table based on the given strings.
							- Related: ((66be1acb-459b-4849-a539-0baac3ff3070)) : ((b57f9d17-c0b5-44cb-b89c-296f40c6d691))
						- # Related: ((65d89c40-9752-4c2b-91c1-e867001153e1))
					- [Substrings](https://www.codecademy.com/resources/docs/python/substrings)
					- [Threading](https://www.codecademy.com/resources/docs/python/threading)
					- [Time Module](https://www.codecademy.com/resources/docs/python/time-module)
					- [Tuples](https://www.codecademy.com/resources/docs/python/tuples)
					  id:: 65d89c40-66da-4169-95ad-9f3aefb00de2
					  collapsed:: true
					  Mostly equivalent to an immutable ((65d89c40-5e6f-4b12-b1cc-5d93e2b320cc))
						- Meta
							- Differences/Similarities with ((65d89c40-5e6f-4b12-b1cc-5d93e2b320cc))
								- Differences
									- Of ((65d89c40-66da-4169-95ad-9f3aefb00de2))
										- Immutable
										- Higher performance and memory-efficiency
									- Of ((65d89c40-5e6f-4b12-b1cc-5d93e2b320cc))
										- Lists use `[]`, tuples use `()`
								- Similarities
									- Iterable
									- Supports indexing and slicing
									- Supports nested data structures like any other data type within
						- ## Intro
							- A tuple is a data structure comprised of comma-separated values.
							- Similar to ((65d89c40-5e6f-4b12-b1cc-5d93e2b320cc)) except they are immutable.
							- Tuple elements can be of different [data types](https://www.codecademy.com/resources/docs/python/data-types).
							- Tuples also support built-in sequence functions such as [`len()`](https://www.codecademy.com/resources/docs/python/built-in-functions/len), [`min()`](https://www.codecademy.com/resources/docs/python/built-in-functions/min), and [`max()`](https://www.codecademy.com/resources/docs/python/built-in-functions/max).
						- ## Syntax
							- There are multiple ways to create tuples in Python:
								- ```python
								  # With built-in function
								  tuple_instance(value1, value2, ..., valueN)
								  
								  # With parentheses (multi-item)
								  tuple_instance = (value1, value2, ..., valueN)
								  
								  # With parentheses (single item with a trailing comma)
								  tuple_instance = (singleValue, )
								  
								  # With no parentheses (but with a trailing comma)
								  tuple_instance = singleValue,
								  ```
							- The built-in ((65db1e62-deeb-421c-a395-946b496fce3e)) function accepts an iterable value such as a list and returns a new tuple. Tuples can also be created with just parentheses (or no parentheses).
							- > **Note:** If the tuple is made with just parentheses and has only one element, it must contain a trailing comma. Otherwise, Python may interpret the surrounding parentheses as an expression instead of a tuple:
								- ```python
								  # This will be treated as an int, not a tuple.
								  streaming_days = (3)
								  
								  print(f"Value is {streaming_days}. Type is {type  > (streaming_days)}")
								  # Output: Value is 3. Type is <class 'int'>
								  ```
						- ## Packing and Unpacking Tuples
							- When values are assigned to a tuple, it is “packed.” When those same values are utilized later on in a program, the tuple is “unpacked.”
								- ```python
								  # Packed tuple
								  my_tuple = (1, 2, 3)
								  
								  # Unpacked tuple
								  (one, two, three) = my_tuple
								  
								  print(one)
								  print(two)
								  print(three)
								  
								  """
								  Output:
								  1
								  2
								  3
								  """
								  ```
							- > **Note:** The number of variables must be equal to the number of values in the tuple. Otherwise, an asterisk (`*`) must be used to gather the remaining values in a list:
								- ```python
								  # Packed tuple
								  my_tuple = (1, 2, 3, 4, 5)
								  
								  # Unpacked tuple
								  (one, two, *three) = my_tuple
								  
								  print(one)
								  print(two)
								  print(three)
								  """
								  Output:
								  1
								  2
								  [3, 4, 5]
								  """
								  ```
						- ## Accessing and Updating Tuples
							- Like most sequence types in Python, tuple elements can be accessed by index:
								- ```python
								  my_tuple = ("Code Ninja", "Python")
								  
								  print(my_tuple[1]) # Output: Python
								  ```
							- Referencing a non-existent index will raise an `IndexError`.
							- Tuples can also be sliced with the following syntax:
								- ```python
								  tuple[start_index : stop_index : step]
								  ```
							- The following is an example of slicing a tuple:
								- ```python
								  my_tuple = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
								  print(my_tuple[1 : 9 : 2])
								  # Output: (2, 4, 6, 8)
								  ```
							- Like strings, tuples can also be concatenated to form a single tuple:
								- ```python
								  tuple_1 = (1, 2, 3)
								  
								  tuple_2 = (4, 5, 6)
								  
								  print(tuple_1 + tuple_2)
								  # Output: (1, 2, 3, 4, 5, 6)
								  ```
						- ## Codebyte Example
							- Even though tuples themselves cannot be changed, and their elements can’t be reassigned, after creation, there are some workarounds to this immutability. For example, if any of the tuple elements are themselves a mutable data type or structure, it can be modified or their elements reassigned:
								- ```python
								  list_1 = ["Netflix", "Hulu"]
								  list_2 = ["Amazon", "Apple TV"]
								  
								  streaming_platforms = (list_1, list_2)
								  
								  print(f"Original tuple: {streaming_platforms}\n")
								  
								  streaming_platforms[0].append("YouTube")
								  # This is allowed
								  
								  print(f"After appending to list: {streaming_platforms}\n")
								  
								  streaming_platforms[0][-1] = "YT"
								  # This is also allowed
								  
								  print(f"After reassigning list item: {streaming_platforms}\n")
								  
								  streaming_platforms[1] = "Twitch"
								  # Reassignment of list to string will throw an error
								  ```
						- ## Video Walkthrough
							- Watch this video which illustrates the characteristics of Python tuples.
							  
							  <iframe width="560" height="315" src="[YouTube](https://www.youtube.com/embed/qM7Iz_DRDH8") title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen=""></iframe>
						-
					- [Unittest Module](https://www.codecademy.com/resources/docs/python/unittest-module)
					- [Variables](https://www.codecademy.com/resources/docs/python/variables)
					  id:: 65d89c40-625d-40b7-b0f3-3fd9052902d4
				- Related:
					- ((cfc36ba4-077e-4c24-b372-fd0d6ea9bdd8))
					- ((7cc348b0-a232-4687-a29f-6483103a90ba))
			- [Python 3 Path | Pluralsight](https://app.pluralsight.com/paths/skills/python-3)
			  collapsed:: true
				- Courses
					- _Entry-level_
						- [Python 3: The Big Picture](https://app.pluralsight.com/library/courses/python-3-big-picture)
						  collapsed:: true
							- ## Why Python
							  collapsed:: true
								- This course is about Python 3.0 - 3.11, though some talk about Python 2
								- Pros/Cons of ((629ccb26-9513-49ea-946c-5b33f145c698))
								  id:: 6524165b-df01-4604-b087-36948ddba94f
									- Pros
										- Simple to learn
											- No need to learn about compilers or build systems
											- No need to learn about memory vs disk usage
											- No need to learn about operating systems
											- Easy to read and understand
										- Simple to use
											- One way to do things usually
											- Focus on simplicity
											- Focus on beautiful, readable code
										- Great community
											- [Our Community | Python.org](https://www.python.org/community) - countless packages, great tools
											- [PEP 0 – Index of Python Enhancement Proposals (PEPs) | peps.python.org](https://www.python.org/dev/peps) - central location for community development to propose new features, collect input, document design decisions
										- Widely used
										  id:: 652416f2-4894-444c-a86d-f18d829cd471
											- Movie effects, scripting in Blender, web development, data science, education and learning, scripting, AI, math
											- Web development - [FastAPI](https://fastapi.tiangolo.com/) / ((646349df-3dfb-4073-baba-acbe4bb9506c)) / Bottle for APIs, ((646349e5-a416-452a-a03c-8bbf9eb817d7))/TurboGears/web2py for websites, Django CMS/WagTail/Mezzaninefor apps (CMS, ERP)
											- Data Science includes Big Data and ((646349df-1faa-4497-b76f-648a0f3845cc))
											- Education and Learning - popular for STEM learning, computer science/programming course, hardware/embedded engineering, Jupyter Notebooks
											- Machine and Application Scripting
										- In high demand
											- Python since 2019 has more Stack Overflow questions than even [[JavaScript]]
											- ((65241dd5-1d9f-459f-8f16-f4bbfdb4565c)) shows Python as the most popular for Google search queries
											- Most popular according to [IEEE](https://spectrum.ieee.org/top-programming-languages-2022) (above C, C++, C#)
											- Most popular according to [TIOBE](https://www.tiobe.com/tiobe-index) (above C, Java, C++, C#)
									- ## Cons
									- Unclear
									- Comparisons
							- ## What is Python
							  collapsed:: true
								- Syntax
									- Most popular languages use a ((640c8362-cdc6-44a3-b991-a338f1d05b5a))-like syntax that includes curly brackets for code blocks, semi-colons for line endings. Includes ((640c8362-cdc6-44a3-b991-a338f1d05b5a)), ((646349e5-6faa-4638-a681-e2218087d789)), ((63e40d8d-784b-4c11-925c-5847395b972f)), [[C#]], ((646349e5-1c66-47b8-87ee-79d9bbf5e3c0)), ((629ccb26-7067-4d20-b985-1073caec7aaa)), etc
									  id:: 65241f1e-6a5a-4f50-a080-cd4875d8bbba
									- Python doesn't have a ((640c8362-cdc6-44a3-b991-a338f1d05b5a))-like syntax because it has the principles that "beautiful is better than ugly" and "readability counts"
									- Significant Whitespace is utilised. Spaces/tabs matter, unlike other languages which utilise curly brackets
								- General-purpose and high-level
									- General-purpose language allows it to be ((652416f2-4894-444c-a86d-f18d829cd471)) across many industries/applications
									- High-level means it's less verbose, less time-consuming to write, more human-readable
								- Multi-paradigm
									- Object-oriented, ((63fe5474-f771-4530-8f8a-58b55c71204e)) and structured programming
									- Structured Programming
									  id:: 652421a6-8dcd-4bf9-bc71-e331324b9cdd
										- introduced Control Structures and Subroutines
										- Control Structures like If/Else, Loops,
											- Related: ((646349af-27f7-495d-93c8-29a7f7ff45ec))
										- Subroutines e.g. Procedures, Functions, Methods
									- Functional Programming builds on ((652421a6-8dcd-4bf9-bc71-e331324b9cdd))
										- It focuses on the Algorithms within a program
									- Object-oriented also builds on ((652421a6-8dcd-4bf9-bc71-e331324b9cdd))
								- Interpreted (rather than compiled)
									- The CPU's language is it's Instruction Set Architecture (ISA). Code is translated into ISA by either compilation or interpretation, which happens in real-time
									- Python runtime handles interpretation
									- Python _can_ be compiled
								- Garbage-collected
									- i.e. it's automated for you
								- Dynamically-typed
									- Like [[JavaScript]] and unlike ((629ccb26-1eab-4686-a7b8-f9433a871440))
									- A variable can change type
									- Type checking happens at runtime
									- It allows duck typing - basically gives us more flexibility
							- ## Python Pros and Cons
								- Pros
									- Comprehensive Standard Library
									  collapsed:: true
										- As opposed to having a minimal standard library, which allows it to evolve separately from the language and having to maintain a bunch of complexity that the application never uses, at the expense of having to pull in a lot of 3rd-party libraries when building a non-trivial application
										- Allows a lot of room to experiment with the language without having to learn 3rd-party libraries.
										- Python's SL includes
											- Common data structures like collections, lists, sets, dictionaries
											- File I/O - lets you read and write files
											- Dates and times
											- Compression and archiving
											- User interfaces
											- Working with CSV or XML files
											- Working with audio data
										- [Documentation](https://docs.python.org/3/library/index.html)
									- Community-driven
									  collapsed:: true
										- Since Python 2 release in 2000 Python's development became more community-backed and transparent via Python Enhancement Proposals
										- [PEP 20 – The Zen of Python | peps.python.org](https://peps.python.org/pep-0020) is a great read for learning why Python is designed the way it is
										- [Community | Python.org](https://python.org/community-landing) - many different ways to connect
										- [Python Software Foundation](https://python.org/psf-landing)
									- 3rd-party libraries
									  collapsed:: true
										- [PyPi](https://pypi.org)
										  id:: 653f8c4f-ffdd-436d-9286-e7d5c669b42c
										  AKA Python Package Index
										- Uses Pip to install packages. It comes installed by default with many Python distributions and installs
										- `pip install SomePackage`
										- Pip package manager helps us track our own dependencies and those of the packages we're installing
										- We can track a group of packages as a package group
										- Pip can help us to make sure we're using the right version of a package
										- Popular libraries
											- Data Science
												- NumPy, Pandas, Matplotlib, Tensorflow, Keras, Scikit Learn
											- Web Development
												- ((646349df-3dfb-4073-baba-acbe4bb9506c)), Requests, Django
											- Images/Computer Vision
												- Pillow, Pygal, OpenCV, Mahotas
											- Applications
												- wxPython (GUI), PyGTK (GUI), Fire (CLI), Kivy (Mobile/Multi-touch), Pygame
									- 3rd-party tools
										- ((663a58ef-1fbe-4f03-980c-2bb421e9eb3a)) software
											- Pydev - Eclipse-based
											- Pycharm by JetBrains
											- Spyder - for scientific use and data analysis
											- See ((643a72a8-069f-4684-af20-14a6ca2f9325))
										- Code Tools
											- flake8 - Style Guide Enforcement
											- PyLint - Code Analysis
											- Black - Code Formatter
											- Intel's vtune suite - Performance Analyser
								- Cons
									- Interpreted
										- Quite slow out-of-the-box compared to compiled languages like ((640c8362-cdc6-44a3-b991-a338f1d05b5a)), ((646349e5-6faa-4638-a681-e2218087d789)), ((646349e5-1c66-47b8-87ee-79d9bbf5e3c0))
									- Not Native
										- High memory usage, lack of native security sandbox
										- Have led to low adoption in browsers and mobile
										- Used a fair amount of server, but little on desktop and mobile
									- Dynamic
										- Runtime errors are harder to debug
								- Workarounds
									- CPython allows compiling code for better performance
									- Optional Typing Hints works around dynamic typing (similar to ((629ccb26-1eab-4686-a7b8-f9433a871440)))
						- [Python 3 Fundamentals](https://app.pluralsight.com/library/courses/python-3-fundamentals)
						  id:: 65240a6d-d36e-460c-ba88-5a1b04203cf8
						  collapsed:: true
							- ## Run Python and Explore Data Types
								- ### Data Types
								  collapsed:: true
									- Python code can be written either in:
										- The Python Interactive Shell
											- ```python
											  >>> 10 + 20 + 30
											  60
											  ```
										- A Python File
											- `script.py`
											- A Python script or file is where you create longer Python programs
									- Savings numbers to variables
										- ```python
										  length = 10
										  width = 20
										  area = length * width
										  ```
									- Python infers the type (i.e. dynamic typing)
								- ### Install Python
								  collapsed:: true
									- `python --version` = check if Python is installed
									- `python3 --version` = check if Python 3 is installed
									- Otherwise go to [Download Python | Python.org](https://python.org/downloads)
									- `python` or `python3` = Open Python Interactive Shell
										- It'll show `>>>` if you're in it
										- `quit()` or `CTRL + D` = exits the Python Interactive Shell
									- In ((63209272-1088-4824-a762-4ac7ded04b0a))
										- Extensions : install `Python` extension by Microsoft
										- ((6341c0c5-3f09-420f-833c-96b8e3b886bc)) : search `Python: Select Interpreter` : choose the latest version of Python that you just installed
									- ((6540df86-e6fa-44aa-8a73-f1aed1f04708))
									  id:: 6540dee3-b646-49dc-8504-46d36276dc4a
									- `print("Hello World")` = print `Hello World` to CLI
									- Alternatively run `python hello.py` to run that file (rather than ((6540df86-e6fa-44aa-8a73-f1aed1f04708)) )
								- ### Strings and Input and Output
								  collapsed:: true
									- `int()` function can convert `float` to `int`
										- ```python
										  amount = int(10.6)
										  print(amount)
										  # 10
										  ```
									- `float()` function can convert `int` to `float`
										- ```python
										  amount = float(10)
										  print(amount)
										  # 10.0
										  ```
									- Strings can be inferred from `'` single or `"` double quotes
										- Need to use `"` if your string already contains a `'` e.g. `"Sarah's store"`
									- String concatenation works like [[JavaScript]]
									- `input()` function creates a prompt pop-up with input field
										- ```python
										  my_name = input("What's your name?")
										  ```
										- Note: it'll be entered as a string, so you'll want to wrap it with `int()` to convert it to a number if your input field requires it
											- ```python
											  age = int(input("How old are you?\n"))
											  ```
											- To convert it back to a string
												- ```python
												  print("My age is " + str(age))
												  ```
									- `/` operator divides to make a `float`
									- `//` divides to make an `int` (whole number), rounding down
							- ## Conditionals and Imports
								- ### Conditionals
								  collapsed:: true
								  
								  collapsed:: true
									- The 6 Python Comparators
										- `<` less than
										- `<=`
										- `==`
										- `>=`
										- `>`
										- `!=`
									- `if` statement
										- Example
											- ```python
											  temperature = 95
											  if temperature > 80:
											    	print("It's too hot!")
											  elif temperature < 60: # Else If
											      print("It's too cold!")
											  else:
											      print("Enjoy the outdoors!")
											  ```
										- Usually 4 spaces are used for indentation
									- `or` operator
										- ```python
										  if temperature > 80 or temperature < 60:
										      print("Stay inside!")
										  else:
										    	print("Enjoy the outdoors!")
										  ```
									- `not` operator
										- Example
											- ```python
											  forecast = "rainy"
											  
											  if not forecast == "rainy"
											  	print("Go outside!")
											  else:
											    	print("Stay inside!")
											  ```
									- `and` operator
										- Example
											- ```python
											  computer_choice = 'scissors'
											  user_choice = input('Do you want rock, paper, or scissors?')
											  
											  if computer_choice == user_choice:
											    	print('TIE')
											  elif user_choice == ‘rock’ and computer_choice == ‘scissors':
											  	print('WIN')
											  ```
									- `Boolean` variables are `True` or `False`
									- ((646349f4-5cfc-4661-b1be-43cb99c9e073)) is being used for naming variables in this course, unsure if this is convention
								- ### Import Python Modules
								  collapsed:: true
								  
								  collapsed:: true
									- [Docs for Python Standard Library](https://docs.python.org/3/library)
									- Example
										- ```python
										  import random
										  
										  roll = random.randInt(1,6)
										  print("The computer rolled a " + str(roll))
										  ```
							- ## Lists and Loops
								- ### Lists and Loops
								  collapsed:: true
								  
								  collapsed:: true
									- Lists
									  AKA arrays in [[JavaScript]]
										- Examples
											- ```python
											  empty = [] # Empty list
											  words = ['LOL', 'IDK', 'TBH'] # List of strings
											  ```
									- `append()` method
									  Add items to a list
										- Example
											- ```python
											  acronyms = []
											  
											  acronyms.append('LOL')
											  acronyms.append('IDK')
											  
											  print(acronyms)
											  ```
									- `remove()` method
									  Remove items from a list by specifying their value
										- ```python
										  acronyms = ['LOL', 'IDK', 'SMH']
										  
										  acronyms.remove('LOL')
										  
										  print(acronyms)
										  # acronyms = ['IDK', 'SMH']
										  ```
									- `del`
									  Remove items from a list by specifying their index
										- Example
											- ```python
											  acronyms = ['LOL', 'IDK', 'SMH']
											  
											  del acronym[0]
											  
											  print(acronyms)
											  # acronyms = ['IDK', 'SMH']
											  ```
									- Check `if` exists in list
										- ```python
										  if 1 in [1, 2, 3, 4, 5]:
										    	print('True')
										  ```
										- ```python
										  acronyms = ['LOL', 'IDK', 'SMH']
										  word = 'LOL'
										  
										  if word in acronyms:
										    	print('True')
										  ```
									- `for` loop
										- ```python
										  acronyms = ['LOL', 'IDK', 'SMH']
										  
										  for acronym in acronyms:
										    	print(acronym)
										  ```
											- Similar to ((635eb08f-9a44-4545-88c0-b7064e94f590))
								- ### Loops with range()
								  collapsed:: true
								  
								  collapsed:: true
									- `range()` function
									  A way to limit how long you loop for
										- Example
											- ```python
											  range(0, 7, 1)
											  ```
												- `0` = Start value (optional. `0` by default)
												- `7` = Stop value (optional. `1` by default)
												  id:: 65414bd3-392c-4635-a0f9-3a406067aff8
												- `1` = Step value
											- ```python
											  range(7)
											  # (0, 1, 2, 3, 4, 5, 6)
											  
											  range(2, 14, 2)
											  # (2, 4, 6, 8, 10, 12)
											  # Starts at 2, stops before 14
											  ```
									- `for` loop using `range()`
										- ```python
										  for i in range(7):
										    	print(i)
										  # It will loop 7 times, starting at 0 and ending at 6
										  ```
							- ## Dictionaries, JSON and Pip
								- ### Dictionaries
								  collapsed:: true
								  
								  collapsed:: true
								  AKA ((63f33e7c-e71b-4d14-b352-7b9fe2d600b1)) in [[JavaScript]]
									- A dictionary maps keys to values
										- Example
											- ```python
											  acronyms = {}
											  ```
											- ```python
											  acronyms = {'LOL': 'laugh out loud',
											             'IDK': "I don't know",
											             'TBH': 'to be honest'}
											  
											  print(acronyms['LOL'])
											  # 'laugh out loud'
											  ```
									- Keys can be any type for key or value e.g. numbers, strings
									- Objects can be added like so:
										- ```python
										  acronyms = {}
										  
										  acronyms['LOL'] = 'laugh out loud'
										  acronyms['IDK'] = "I don't know"
										  acronyms['TBH'] = 'to be honest'
										  
										  print(acronyms)
										  # acronyms = {'LOL': 'laugh out loud',
										  # 'IDK': "I don't know",
										  # 'TBH': 'to be honest'}
										  ```
									- Updating values in our dictionary
										- ```python
										  acronyms['TBH'] = 'honestly'
										  print(acronyms['TBH'])
										  # 'honestly'
										  ```
									- `del` keyword to delete dictionary items
										- ```python
										  acronyms = {'LOL': 'laugh out loud',
										              'IDK': "I don't know",
										              'TBH': 'to be honest'}
										  
										  del acronyms['LOL']
										  print(acronyms)
										  # acronyms = {'IDK': "I don't know",
										  # 'TBH': 'to be honest'}
										  ```
									- `get()` is a better way to lookup a value, because it won't crash the program if the key isn't in the dictionary
										- ```python
										  acronyms = {'LOL': 'laugh out loud',
										              'IDK': "I don't know",
										              'TBH': 'to be honest'}
										  
										  definition = acronyms.get('BTW')
										  # returns `None` - AKA null
										  ```
									- `None` is `null` in [[JavaScript]] i.e. absence of a value
									-
								- ### Combining Lists and Dictionaries
								  collapsed:: true
								  
								  collapsed:: true
									- A List of Lists
										- ```python
										  menus = [ ['Egg Sandwich', 'Bagel', 'Coffee'],
										            ['BLT', 'PB&J', 'Turkey Sandwich'],
										            ['Soup', 'Salad', 'Spaghetti', 'Taco'] ]
										  
										  print(menus[0][1])
										  # Bagel
										  ```
									- A Dictionary of Lists
										- ```python
										  menus = { 'Breakfast' : ['Egg Sandwich', 'Bagel', 'Coffee'],
										            'Lunch' : ['BLT', 'PB&J', 'Turkey Sandwich'],
										            'Dinner' : ['Soup', 'Salad', 'Spaghetti', 'Taco'] }
										  
										  print('Breakfast Menu:\t', menus['Breakfast'])
										  # Breakfast Menu: ['Egg Sandwich', 'Bagel', 'Coffee']
										  ```
									- Using a dictionary's key and value in a `for` loop
										- ```python
										  menus = { 'Breakfast' : ['Egg Sandwich', 'Bagel', 'Coffee'],
										            'Lunch' : ['BLT', 'PB&J', 'Turkey Sandwich'],
										            'Dinner' : ['Soup', 'Salad', 'Spaghetti', 'Taco'] }
										  
										  for name, menu in menus.items():
										    	print(name, ':', menu)
										  ```
								- ### Reading JSON and Installing Packages
								  collapsed:: true
								  
								  collapsed:: true
									- [`requests` library](https://requests.readthedocs.io) to make HTTP requests
									- `sudo apt install python3-pip` on Kubuntu 24.10
									- `pip3 --version` = check if pip3 is installed
									- `pip3 requests` = install `requests` package via `pip3`
									- How to do a HTTP request
										- Example
											- ```python
											  import requests
											  
											  response = requests.get('http://api.open-notify.org/astros.json')
											  json = response.json()
											  print(json)
											  
											  for person in json['people']:
											    	print(person['name'])
											  ```
								- ### Create a Python Virtual Environment using [venv](https://docs.python.org/3/library/venv.html)
								  id:: 6541f026-6d71-46d4-a23e-d4197d68b21d
								  collapsed:: true
									- Steps
										- `pip install virtualenv`
										  Install Python Virtual Environment package
										- `python3 -m venv /path/to/new/virtual/environment`
										  Create a new virtual environment
											- e.g.
												- `python3 -m venv myenv`
											- Alternatively
												- `virtualenv myenv`
												- Unsure which is better
										- `source myenv/bin/activate` = open the `myenv` virtual environment
											- e.g. `source myenv/bin/activate`
										- 3. In ((63209272-1088-4824-a762-4ac7ded04b0a)) ((6341c0c5-3f09-420f-833c-96b8e3b886bc)) : `Python: Select Interpreter` : select the `venv` environment
									- `pip3 list packages`
										- Or `pip list`
									- Optional
										- `pip install -r requirements.txt`
										  id:: 654b6d01-63a5-4387-a338-87d7eb3aa579
											- Related: ((654b7053-547c-48ff-9b31-9b6b9dcc5b8f))
										- `deactivate` = exit the virtual environment
								- ### Demo: Using an API
								  collapsed:: true
								  
								  collapsed:: true
									- ```python
									  import requests
									  
									  url = 'https://api.weatherapi.com/blah/'
									  response = requests.get(url)
									  weather_json = response.json()
									  
									  temp = weather_json.get('current').get('temp_f')
									  
									  print(weather_json)
									  ```
							- ## Functions
							  collapsed:: true
								- Examples
									- ```python
									  def greeting(name):
									  	print('Hello', name)
									  ```
									- ```python
									  def addition(a, b):
									    	return a + b
									  ```
									- ```python
									  def main():
									    	print('Hello', name)
									  ```
								- Functon definition
									- ```python
									  def greeting(name):
									  	print('Hello', name)
									  ```
										- `def` keyword for `define`
										- `greeting` = example function name
										- `name` = 0 to many parameters
										- `print('Hello', name)` = function body
								- Global vs local scope for variables
								-
							- ## Classes and Objects
								- ### Classes
								  collapsed:: true
								  
								  collapsed:: true
									- Objects can have state and behaviour
										- e.g. A chihuahua dog
											- `Name`, `Breed`, `Hungry` as state
											- `Barking`, `Whining`, `Wagging Tail` as behaviours
									- Defining the robot dog class
									  collapsed:: true
										- ```python
										  class Robot_Dog:
										    def __init__(self, name, breed):
										      self.name = name
										      self.breed = breed
										  ```
											- `__init__()`
											  id:: 6561d45e-6a5a-426a-81f8-003510e3f3e9
											  method that let's us initialise the robot's properties
											- `self` = always the first param of ((6561d45e-6a5a-426a-81f8-003510e3f3e9)). Refers to the instance of the class that we're creating or the current object (similar to ((64024e3f-159e-41ab-800d-5a5bf7e98bda))?)
											- `name` and `breed` = properties we want to initialise
											- `self.name` and `self.breed` = initialise these properties as the passed-in values
										- Alternatively can be written like so for clarity, and it works the same:
										  ```python
										  class Robot_Dog:
										    def __init__(self, name_val, breed_val):
										      self.name = name_val
										      self.breed = breed_val
										  ```
										- Main program
											- ```python
											  my_dog = Robot_Dog('Spot', 'Chihuahua')
											  print(my_dog.name)
											  print(my_dog.breed)
											  ```
												- `my_dog` = new instance of the class
												- `Robot_Dog` = name of the class
									- Creating a class method
									  collapsed:: true
										- id:: 6561d956-6938-42b9-a986-e6db343f0b92
										  ```python
										  class Robot_Dog:
										    def __init__(self, name, breed):
										      self.name = name
										      self.breed = breed
										    # Start of class method
										    def bark(self):
										      print('Woof Woof!')
										  ```
											- `def` = it's a method AKA function within an object
											- `self` = always the first parameter
										- To call it
											- ```python
											  my_dog = Robot_Dog('Spot', 'Chihuahua')
											  my_dog.bark()
											  ```
									- Examples
										- ((6561d956-6938-42b9-a986-e6db343f0b92))
										- ```python
										  from employee import Employee
										  
										  class Company:
										    def __init__(self):
										      self.employees = []
										  
										    def add_employees
										    	self.employees.append(new_employee)
										  ```
								- Importing
								  collapsed:: true
									- ```python
									  from employee import Employee
									  ```
										- `from employee` = from `employee.py` (different file)
										- `import Employee` = import `Employee` class
								- ### Class Inheritance
								  collapsed:: true
								  
								  collapsed:: true
									- Has-a vs Is-a relationships
										- Has-a relationships
											- A company **has** employees
											- A robot **has a** battery
										- Is-a relationships
										  AKA inheritance
											- A robot dog **is a** robot
											- A robot cat **is a** robot
									- Inheritance
										- Robot would be a base (AKA parent) class, so Robot_Dog and Robot_Cat would be derived (AKA child) class
										- Creates a hierarchy of classes that share properties and methods
									- Creating a Child Class
										- ```python
										  class Robot_Dog(Robot):
										    def make_noise(self):
										      print('Woof woof!')
										  ```
											- `Robot` = parent class
											- Adding an ((6561d45e-6a5a-426a-81f8-003510e3f3e9)) is optional, it otherwise will use the parent class's version
											- `def make_noise` = method specific to this child class
										- Creating an instance of child class:
											- ```python
											  my_robot_dog = Robot_Dog('Bud')
											  ```
												- `Robot_Dog()` = constructor
									- Method Overriding
										- If you add a method with the same name to a child class, it'll instead use that child class method
									- Calling `super()`
										- This can be used to access a parent classes' methods
										- Example
											- ```python
											  class Robot_Dog(Robot):
											    def make_noise(self):
											      super().make_noise()
											      print('Bork bork!')
											  ```
										- You might use this so you can have some but not all the properties of the parent class
											- Example
											  
											  ```python
											  class Employee:
											    def __init__(self, fname, lname)
											    	self.fname = fname
											      self.lname = lname
											  
											  class SalaryEmployee(Employee):
											    def __init__(self, fname, lname, salary):
											      super().__init__(fname, lname)
											      self.salary = salary
											  ```
							- ## Working with Files
								- ### Exceptions
								  collapsed:: true
									- Syntax error vs exceptions
										- An extra `)` for example usually results in an `SyntaxError: unmatched )` and it tells you the line number where the error is
										- Exceptions
											- e.g. `KeyError` can be caused for trying to look up a property that doesn't exist in an object
									- We can catch exceptions with a `try/except` block
										- Using this allows our program to keep running without being stopped right there
										- `try` = code that may cause an exception
										- `except` = print an error message on exception
										- Example
											- ```python
											  acronyms = {'LOL': 'laugh out loud',
											              'IDK': "I don't know",
											              'TBH': 'to be honest' }
											  try:
											    definition = acronyms['BTW']
											  except:
											    print('They key does not exist')
											  ```
									- `finally` can be added after `try/except`
										- Will be executed regardless if the `except` gets triggered or not
										- Can be used to clean up resources or close objects
										- Example
											- ```python
											  acronyms = {'LOL': 'laugh out loud',
											              'IDK': "I don't know",
											              'TBH': 'to be honest' }
											  try:
											    definition = acronyms['BTW']
											  except:
											    print('They key does not exist')
											  finally:
											    print('The acronyms we have defined are:')
											  print('The program keeps going...')
											  ```
									- Creating a program where we can raise an exception
										- Example
											- ```python
											  def remainder_division(a, b):
											    # Start of raise an exception
											    if b == 0:
											      raise ZeroDivisionError
											    # End
											    result = a//b
											    remainder = a%b
											    print(a, '/', b, ‘is', result,
											          'remainder', remainder)
											  ```
											- Custom exception
											  ```python
											  def remainder_division(a, b):
											    # Start of raise an exception
											    if b == 0:
											      raise Exception('Divisor cannot be 0')
											    # End
											    result = a//b
											    remainder = a%b
											    print(a, '/', b, ‘is', result,
											          'remainder', remainder)
											  ```
								- ### Reading Files
								  collapsed:: true
								  
								  collapsed:: true
									- Creating a program where the user can look up acronyms
										- Ask the user what acronym they want to look up?
										  logseq.order-list-type:: number
										- Open the file
										  logseq.order-list-type:: number
										- Read each line of the file
										  logseq.order-list-type:: number
										- Check if current acronym matches the user's acronym
										  logseq.order-list-type:: number
										- Print the definition
										  logseq.order-list-type:: number
									- Opening a file
									  collapsed:: true
										- `open()`
											- Returns a `File` object has methods like `read()` and `write()`
											- Example
											  ```python
											  file = open('acronyms.txt')
											  ```
											- It's very important to `close()` a `File` object that's been opened
										- `with`
											- This keyword makes sure the `File` is properly closed when the file operations are done even if an exception is raised.
											- Example
											  ```python
											  with open('acronyms.txt') as file:
											    # Do file operations here
											  ```
										- Alternatively a longer way to close a file without the keyword `with` is to use `try/finally` block
											- ```python
											  file = open('acronyms.txt')
											  try:
											    # Do file operations here
											    pass
											  finally:
											    file.close()
											  ```
									- Reading a file
									  collapsed:: true
										- `read()`
										  Returns the whole file as a `String` by default. Or it will return the specified number of bytes.
											- Example
												- ```python
												  with open('acronyms.txt') as file:
												    result = file.read()
												    print(result)
												  ```
										- `readline()`
										  Returns the next line of the file as a `String`
											- Example
												- ```python
												  with open('acronyms.txt') as file:
												    result = file.readline()
												    print(result)
												  
												    result = file.readline()
												    print(result)
												  ```
										- `readlines()`
										  Returns a list of `Strings` of all of the lines in the file.
											- Example
												- ```python
												  with open('acronyms.txt') as file:
												    result = file.readlines()
												    for line in result:
												      print(line)
												  ```
										- Using a loop to read from a file object
											- Example
												- ```python
												  with open('acronyms.txt') as file:
												    for line in file:
												      print(line)
												  ```
												- Equivalent to:
												  ```python
												  with open('acronyms.txt') as file:
												    result = file.readlines()
												    for line in result: file:
												      print(line)
												  ```
									- Example
										- ```python
										  look_up = input("What software acronym would you like to look up?\n")
										  
										  found = False
										  with open('acronyms.txt') as file:
										    for line in file:
										      if look_up in line:
										        print(line)
										        found = True
										        break
										  if not found:
										    print('The acronym does not exist')
										  ```
								- ### Writing Files
									- Part of code:
									- ```python
									  acronym = input('What acronym do you want to add?\n')
									  definition = input('What is the definition?\n')
									  with open('acronyms.txt', 'w') as file:
									    file.write(acronym + ' - ' + definition + '\n')
									  ```
								- ### File Manipulation
									- Python has several built-in modules for file manipulation - `os`, `shutil` and `pathlib`
									- `os` can be used to for example make directories, list files and move files
									- Making a directory
										- ```python
										  import os
										  
										  os.mkdir('/Users/Sarah/Desktop/CleanedUp/')
										  ```
									- Listing all entries in a directory
										- ```python
										  import os
										  
										  folder = '/Users/Sarah/Desktop/'
										  entries = os.scandir(folder)
										  
										  for entry in entries:
										    print(entry.name)
										  ```
									- Check if a directory entry is a file or subdirectory
										- ```python
										  import os
										  
										  folder = '/Users/Sarah/Desktop/'
										  entries = os.scandir(folder)
										  
										  for entry in entries:
										    if os.path.isfile(entry):
										      print('File:', entry.name)
										    elif os.path.isdir(entry):
										      print('Directory:', entry.name)
										  ```
									- Create an absolute path name
										- ```python
										  import os
										  
										  folder_destination = '/Users/Sarah/Desktop/CleanedUp/'
										  new_name = os.path.join(folder_destination, 'new.text')
										  # Note: string concatenation could be used instead of `join()` but it doesn't check for correct format and isn't best practice
										  ```
									- Move a file
										- ```python
										  import os
										  
										  folder_original = '/Users/Sarah/Desktop/'
										  folder_destination = '/Users/Sarah/Desktop/CleanedUp/'
										  
										  location_original = os.path.join(folder_original, 'new.txt')
										  location_destination = os.path.join(folder_destination, 'new.txt')
										  
										  os.rename(location_original, location_destination)
										  # allows us to move a file to a new path
										  ```
									- Cleaning up files on the desktop
					- _Practitioner_
						- [Classes and Object-oriented Programming in Python 3](https://app.pluralsight.com/library/courses/python-3-classes-object-oriented-programming)
						- [Working with Files in Python 3](https://app.pluralsight.com/library/courses/python-3-working-files)
						- [Working with Databases in Python 3](https://app.pluralsight.com/library/courses/python-3-working-databases)
			- http://www.learpythonthehardway.com/
			- [The Python Standard Library](https://docs.python.org/3/library/index.html)
			  collapsed:: true
				- [`asyncio`](https://docs.python.org/3/library/asyncio.html)
				  Asynchronous I/O
				- [`logging`](https://docs.python.org/3/library/logging.html)
				  collapsed:: true
					- `logging.getLogger("asyncio").setLevel(logging.ERROR)`
						- After having imported it in a previous step (i.e.`import asyncio`) this reduces debug messages in logs so that it'll only report errors, not all events
				- `typing` - Typing Hints
					- `def wrapper(ui_subclass: Type[Display]) -> Type[Display]:`
			- [GitHub - dabeaz-course/python-mastery: Advanced Python Mastery (course by @dabeaz)](https://github.com/dabeaz-course/python-mastery)
			- [Full Stack Python](http://www.fullstackpython.com)
			- [futurecoder: learn python from scratch](https://futurecoder.io/)
			  collapsed:: true
				- [GitHub - alexmojaki/futurecoder: 100% free and interactive Python course for beginners](https://github.com/alexmojaki/futurecoder)
				-
			- [W3Schools - Python](https://www.w3schools.com/python/default.asp)
			  id:: 66be1acb-459b-4849-a539-0baac3ff3070
			  collapsed:: true
				- [Python Reference](https://www.w3schools.com/python/python_reference.asp)
					- [Python Built-in Functions](https://www.w3schools.com/python/python_ref_functions.asp)
					- [Python String Methods](https://www.w3schools.com/python/python_ref_string.asp)
					  id:: b57f9d17-c0b5-44cb-b89c-296f40c6d691
					  collapsed:: true
						- [capitalize()](https://www.w3schools.com/python/python_ref_string.aspref_string_capitalize.asp)Converts the first character to upper case
						- [casefold()](https://www.w3schools.com/python/python_ref_string.aspref_string_casefold.asp)Converts string into lower case
						- [center()](https://www.w3schools.com/python/python_ref_string.aspref_string_center.asp)Returns a centered string
						- [count()](https://www.w3schools.com/python/python_ref_string.aspref_string_count.asp)Returns the number of times a specified value occurs in a string
						- [encode()](https://www.w3schools.com/python/python_ref_string.aspref_string_encode.asp)Returns an encoded version of the string
						- [endswith()](https://www.w3schools.com/python/python_ref_string.aspref_string_endswith.asp)Returns true if the string ends with the specified value
						- [expandtabs()](https://www.w3schools.com/python/python_ref_string.aspref_string_expandtabs.asp)Sets the tab size of the string
						- [find()](https://www.w3schools.com/python/python_ref_string.aspref_string_find.asp)Searches the string for a specified value and returns the position of where it was found
						- [format()](https://www.w3schools.com/python/python_ref_string.aspref_string_format.asp)Formats specified values in a string format\_map()Formats specified values in a string
						- [index()](https://www.w3schools.com/python/python_ref_string.aspref_string_index.asp)Searches the string for a specified value and returns the position of where it was found
						- [isalnum()](https://www.w3schools.com/python/python_ref_string.aspref_string_isalnum.asp)Returns True if all characters in the string are alphanumeric
						- [isalpha()](https://www.w3schools.com/python/python_ref_string.aspref_string_isalpha.asp)Returns True if all characters in the string are in the alphabet
						- [isascii()](https://www.w3schools.com/python/python_ref_string.aspref_string_isascii.asp)Returns True if all characters in the string are ascii characters
						- [isdecimal()](https://www.w3schools.com/python/python_ref_string.aspref_string_isdecimal.asp)Returns True if all characters in the string are decimals
						- [isdigit()](https://www.w3schools.com/python/python_ref_string.aspref_string_isdigit.asp)Returns True if all characters in the string are digits
						- [isidentifier()](https://www.w3schools.com/python/python_ref_string.aspref_string_isidentifier.asp)Returns True if the string is an identifier
						- [islower()](https://www.w3schools.com/python/python_ref_string.aspref_string_islower.asp)Returns True if all characters in the string are lower case
						- [isnumeric()](https://www.w3schools.com/python/python_ref_string.aspref_string_isnumeric.asp)Returns True if all characters in the string are numeric
						- [isprintable()](https://www.w3schools.com/python/python_ref_string.aspref_string_isprintable.asp)Returns True if all characters in the string are printable
						- [isspace()](https://www.w3schools.com/python/python_ref_string.aspref_string_isspace.asp)Returns True if all characters in the string are whitespaces
						- [istitle()](https://www.w3schools.com/python/python_ref_string.aspref_string_istitle.asp) Returns True if the string follows the rules of a title
						- [isupper()](https://www.w3schools.com/python/python_ref_string.aspref_string_isupper.asp)Returns True if all characters in the string are upper case
						- [join()](https://www.w3schools.com/python/python_ref_string.aspref_string_join.asp)Converts the elements of an iterable into a string
						- [ljust()](https://www.w3schools.com/python/python_ref_string.aspref_string_ljust.asp)Returns a left justified version of the string
						- [lower()](https://www.w3schools.com/python/python_ref_string.aspref_string_lower.asp)Converts a string into lower case
						- [lstrip()](https://www.w3schools.com/python/python_ref_string.aspref_string_lstrip.asp)Returns a left trim version of the string
						- [maketrans()](https://www.w3schools.com/python/python_ref_string.aspref_string_maketrans.asp)Returns a translation table to be used in translations
						- [partition()](https://www.w3schools.com/python/python_ref_string.aspref_string_partition.asp)Returns a tuple where the string is parted into three parts
						- [replace()](https://www.w3schools.com/python/python_ref_string.aspref_string_replace.asp)Returns a string where a specified value is replaced with a specified value
						- [rfind()](https://www.w3schools.com/python/python_ref_string.aspref_string_rfind.asp)Searches the string for a specified value and returns the last position of where it was found
						- [rindex()](https://www.w3schools.com/python/python_ref_string.aspref_string_rindex.asp)Searches the string for a specified value and returns the last position of where it was found
						- [rjust()](https://www.w3schools.com/python/python_ref_string.aspref_string_rjust.asp)Returns a right justified version of the string
						- [rpartition()](https://www.w3schools.com/python/python_ref_string.aspref_string_rpartition.asp)Returns a tuple where the string is parted into three parts
						- [rsplit()](https://www.w3schools.com/python/python_ref_string.aspref_string_rsplit.asp)Splits the string at the specified separator, and returns a list
						- [rstrip()](https://www.w3schools.com/python/python_ref_string.aspref_string_rstrip.asp)Returns a right trim version of the string
						- [split()](https://www.w3schools.com/python/python_ref_string.aspref_string_split.asp)Splits the string at the specified separator, and returns a list
						- [splitlines()](https://www.w3schools.com/python/python_ref_string.aspref_string_splitlines.asp)Splits the string at line breaks and returns a list
						- [startswith()](https://www.w3schools.com/python/python_ref_string.aspref_string_startswith.asp)Returns true if the string starts with the specified value
						- [strip()](https://www.w3schools.com/python/python_ref_string.aspref_string_strip.asp)Returns a trimmed version of the string
						- [swapcase()](https://www.w3schools.com/python/python_ref_string.aspref_string_swapcase.asp)Swaps cases, lower case becomes upper case and vice versa
						- [title()](https://www.w3schools.com/python/python_ref_string.aspref_string_title.asp)Converts the first character of each word to upper case
						- [translate()](https://www.w3schools.com/python/python_ref_string.aspref_string_translate.asp)Returns a translated string
						- [upper()](https://www.w3schools.com/python/python_ref_string.aspref_string_upper.asp)Converts a string into upper case
						- [zfill()](https://www.w3schools.com/python/python_ref_string.aspref_string_zfill.asp)Fills the string with a specified number of 0 values at the beginning
						- Related: ((65d4b9de-9743-4361-a3ac-8dda0f78ff60)) : ((663a579f-ea11-4ded-834a-f29a987bd3e6))
					- [Python List/Array Methods](https://www.w3schools.com/python/python_ref_list.asp)
					- [Python Dictionary Methods](https://www.w3schools.com/python/python_ref_dictionary.asp)
					- [Python Tuple Methods](https://www.w3schools.com/python/python_ref_tuple.asp)
					- [Python Set Methods](https://www.w3schools.com/python/python_ref_set.asp)
					- [Python File Methods](https://www.w3schools.com/python/python_ref_file.asp)
					- [Python Keywords](https://www.w3schools.com/python/python_ref_keywords.asp)
					  id:: 48fb97f8-9cfa-4dcb-b025-65f44f136161
					  collapsed:: true
						- [and](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_and.asp)A logical operator
						- [as](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_as.asp)To create an alias
						- [assert](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_assert.asp)For debugging [break](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_break.asp)To break out of a loop [class](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_class.asp)To define a class [continue](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_continue.asp)To continue to the next iteration of a loop
						- [def](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_def.asp)
						  To define a function
						- [del](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_del.asp)To delete an object
						- [elif](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_elif.asp)Used in conditional statements, same as else if
						- [else](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_else.asp)Used in conditional statements
						- [except](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_except.asp)Used with exceptions, what to do when an exception occurs
						- [False](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_false.asp)Boolean value, result of comparison operations
						- [finally](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_finally.asp)Used with exceptions, a block of code that will be executed no matter if there is an exception or not
						- [for](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_for.asp)To create a for loop
						- [from](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_from.asp)To import specific parts of a module
						- [global](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_global.asp)To declare a global variable
						- [if](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_if.asp)To make a conditional statement
						- [import](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_import.asp)To import a module
						- [in](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_in.asp)To check if a value is present in a list, tuple, etc.
						- [is](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_is.asp)To test if two variables are equal
						- [lambda](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_lambda.asp)To create an anonymous function
						- [None](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_none.asp)Represents a null value
						- [nonlocal](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_nonlocal.asp)To declare a non-local variable
						- [not](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_not.asp)A logical operator
						- [or](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_or.asp)A logical operator
						- [pass](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_pass.asp)A null statement, a statement that will do nothing
						- [raise](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_raise.asp)To raise an exception
						- [return](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_return.asp)To exit a function and return a value
						- [True](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_true.asp)Boolean value, result of comparison operations
						- [try](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_try.asp)To make a try...except statement
						- [while](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_while.asp)To create a while loop withUsed to simplify exception handling
						- [yield](https://www.w3schools.com/python/python_ref_keywords.aspref_keyword_yield.asp)To return a list of values from a generator
					- [Python Built-in Exceptions](https://www.w3schools.com/python/python_ref_exceptions.asp)
					- [Python Glossary](https://www.w3schools.com/python/python_ref_glossary.asp)
					- ## Module Reference
						- [Python Random Module](https://www.w3schools.com/python/module_random.asp)
						- [Python Requests Module](https://www.w3schools.com/python/module_requests.asp)
						- [Python math Module](https://www.w3schools.com/python/module_math.asp)
						- [Python cmath Module](https://www.w3schools.com/python/module_cmath.asp)
			- Changelog
			  collapsed:: true
				- 3.14
					- [Python 3.14 brings template string literals, free-threading, and stdlib subinterpreters | AlternativeTo](https://alternativeto.net/news/2025/10/python-3-14-brings-template-string-literals-free-threading-and-stdlib-subinterpreters/)
					-
		- Completed learning resources (references)
			- [Object-Oriented Programming with Python](https://www.jbinternational.co.uk/course/3859/object-oriented-programming-theory-with-python-training-course-london-uk) - remote live course with JBI Training
			  id:: 6838253f-b1cb-40d6-bc22-3d53900ff7a6
			  collapsed:: true
			  `~/Documents/Git/1MY_REPOS/0-COURSES/Object Oriented Programming with Python | JBI Training/`
				- Course details
					- **Fundamentals: Classes and methods**
						- Computer architecture and programming languages
						- Python as a high-level, object-oriented language
						- Objects as abstractions, for thinking
						- The class statement
						- The explicit self
						- The initialiser method `__init__`
						  collapsed:: true
							- ```python
							  class Person:
							    	def __init__(self, fname, sname):
							  		self.firstname = fname
							          self.surname = sname
							  ```
								- Attributes are `firstname`, `surname`
								- Arguments/paramters are in the brackets (`fname`, `sname`)
							- Base constructor
							- `dir(variable)` can be used to see the available methods of your class
							- `variable.__dict__` can be used to see the class init?
							-
						- Bound methods
						- Attributes and the built-in attribute access functions
						- References and assignment (how Python works)
						- Mutable objects (and call by object)
						- Object copying
					- **Object Oriented Features**
						- Class attributes
						- Class methods
						- Properties
						- Private attributes
						- Single inheritance
						- Inheritance to extend and modify the parent
						- The use of super
						- Cooperative multiple inheritance
						- Inheritance as a type heirarchy
						- Mixing Classes
						- Attribute lookup and the method resolution order
						- The type system: isinstance and issubclass
					- **Inside Python Objects**
						- The instance dictionary
						- Slots
						- Class dictionaries
						- The descriptor protocol
					- **Python Protocols**
						- Magic methods and Python protocols
						- The string representation protocol
						- The container protocols
						- Implementing custom containers
						- Inheriting from collections.abc.MutableSequence
					- **Alternative Approaches**
						- namedtuples
						- dataclasses
						- type as a class factory
					- **Object oriented theory:**
						- History of Object Oriented Programming
						- The pillars of OOP
						- Abstraction
						- Inheritance
						  id:: 6838256b-9e11-44cc-94a0-6170bf299c55
						  collapsed:: true
							- is used to reduce code duplication
							- Inherits methods and attributes from superclass (parent class)
								- ```python
								  class Animal:
								    	def whoami(self):
								        	return "Animal"
								      ...
								  
								  class Cat(Animal):
								   	...
								      
								  class Dog(Animal):
								   	... 
								  
								  c = Cat()
								  c.whoami() # "Animal"
								  ```
							- Overriding methods
							  id:: 686bbc77-65aa-4f3d-a360-6f8c6e4e7ccf
								- ```python
								  class Animal:
								    	def speak(self):
								        	return "Hello"
								  
								  class Cat(Animal):
								    	def speak(self):
								        	return "Meow"
								      
								  class Dog(Animal):
								   	... 
								  
								  c = Cat()
								  c.speak() # "Meow"
								  ```
							- Inheriting constructors from superconstructor
								- ```python
								  class Animal:
								   	def __init__(self, name, age):
								        	self.name = name
								          self.age = age
								          
								    	def speak(self):
								        	return "Hello"
								  
								  class Cat(Animal):
								    	def __init__(self, colour, name, age):
								        	super().__init__(name, age)
								          self.colour = colour
								    
								    	def speak(self):
								        	return "Meow"
								      
								  
								  c = Cat()
								  c.speak() # "Meow"
								  ```
							- Multiple inheritance
								- ```python
								  class Dog(Animal, DoMaths): # leftmost takes priority, it can't be overridden by later classes
								  ```
								- In Java you instead use interfaces for multiple inheritance
							- Example
								- ```python
								  class A: 
								    	def method_a(self):
								        	print("I can walk")
								  
								  class B(A):
								    	def method_b():
								        	pass
								  
								  b = B()
								  b.method_a()
								  ```
						- Encapsulation
						  collapsed:: true
							- A class contains attributes + methods
							- ((686b96f4-e219-49d3-8412-ef45d6ff3f3c))
						- Polymorphism
						  id:: 6838256b-91b1-4e31-86c3-7531a3184dfc
						  collapsed:: true
							- When a method produces different results depending on the object which is calling the method
								- Examples
									- ((686bbc77-65aa-4f3d-a360-6f8c6e4e7ccf))
									- Procedural programming
										- ```python
										  def addition(a,b):
										    return + b
										  
										  addition(1,5)
										  addition("python", "programmming")
										  ```
							- It helps with code readability
							- Example
								- ```python
								  ```
						- Inheritance and the "is a" relationship
						- Object oriented design principles
						- Design patterns
						- The Liskov Substitution Principle
						- ((690fcaf7-ba08-4d17-839f-246bc2edcd9a))
					- **Optional advanced topics (third day):**
						- **Advanced OOP Concepts:**
							- Interfaces and API design
							- Abstract base classes and protocols
							- Type hints and static typing with mypy
							- Class decorators
							- Metaclasses
							- Context managers and the with statement
							- Weak references and destructors
						- **OOP Design Principles**
							- SOLID principles
							- Law of Demeter
							- Liskov Substitution Principle
							- Composition vs inheritance
							  collapsed:: true
								- ```python
								  class Person:
								    	def __init__(self, fname, sname):
								        	self-firstname = fname
								          self.surname = sname
								          self-account = None
								  ```
									- Not mandatory to have an `account`, but can use this variable in other class methods for example
								- ((686cda04-2f21-49e3-b3c4-6c1b69675367))
							- Domain Driven Design
							- Test Driven Development
							- Stop writing classes
							- The hexagon pattern (microservices)
							- The C4 Model for system architecture
				- Worksheets
					- ((686bcbff-a2a5-44f9-81b8-5c66188ebaa0))
					- ((686bcb9b-e06a-43bc-a5c0-4d96c7478350))
					- ((686bbafc-1aab-463f-a89f-9add6f78ffb0))
					- ((686bc573-9fcd-4031-9588-3497a3edb021))
					- ((686bd22a-0dde-492c-bec3-d5207f338b81))
					- ((686bd4bf-6208-4ec3-b218-bfd39344ca5b))
					- ((686bd6ec-fdd0-4878-a335-c61f871a2782))
					- ((686ceec9-aad9-419b-be36-9f4466988a15))
					- ((686cf42c-670b-4c55-bcad-35d8337d5c7f))
					- ((686cf93c-7a38-47e9-b969-103dab18da24))
					- ((686d0be4-cbde-490b-b561-3eee0505488d))
					- ((686d0da3-12a9-4bb3-93d3-efb0ecfcfd7c))
					- ((686d14d3-cb37-4b83-8303-d56043c7d589))
				- # Day 1
				  collapsed:: true
					- ## Morning
						- Lists, either
							- `numbers = []`
							- `numbers = list()` - this works better for writing higher-order functions
						- ((65ddfba0-5a45-403b-9cba-2dda61f844fc))
						- Higher-order functions take functions as an argument. They're fast, concise, functional programming
							- e.g. `map`, `filter`, ``
							- `map` are preferred for efficiency over a loop (efficient in processing speed + syntax)
							- `map` =  transformation
							- `filter` = search
							- `reduce` = aggregation
								- `from functools import reduce`, it's not in Standard Library
								- ```python
								  ans = reduce(lambda x,y: x + y, numbers)
								  ```
						- Type annotations don't make code run faster, it's for developer experience only. Can't replicate the speed of typed languages
						- Anonymous functions = `lambda`
							- ```python
							  e = list(map(lambda a:a +1, numbers))
							  ```
								- first `a` being the parameter
						- Data hiding
						  id:: 686b96f4-e219-49d3-8412-ef45d6ff3f3c
							- Data can be modified and accessed  from outside the class unless you prefix an attribute with `__`
								- ```python
								  def __init__(self, fname, sname):
								  	self.__firstname = fname
								      self.__surname = sname
								      self.__address = None
								  ```
							- i.e. private vs public
							- If it's private you have to use the classes methods to update the values of the class instance, you can't just assign a value directly
							- If it's public you can also inject arbitrary variables
								- ```python
								  p = Person('Allan', 'Turing')
								  p.age = 38
								  dir(p) # Shows the new variable has been added
								  ```
							- Keep the habit to make it public initially because other libraries often try to manipulate data in this way which may be incompatible. Can refactor for private later
						- Tuples are comma-separated set of values that are immutable
							- ```python
							  d = 'kiwi','apple'
							  d = ('kiwi','apple') # convention to add smooth brackets
							  ```
							- Tuples can be used to prevent additional attributes
								- ```python
								  __slots__ = ('firstname','surname','address') # before def __init__
								  ```
						- `print(class_instance)` isn't human-readable - instead use `to_string` method
							- ```python
							  def __str__(self): # toString
							    	return f'(self.firstname) (self.surname)'
							    
							  ```
						- `__` prefix makes a class method private, however the `__` suffix means that it's an inherited (official?) method
						- `Python_OOP_1.ipynb`
						  id:: 686bcbff-a2a5-44f9-81b8-5c66188ebaa0
					- ## Late Morning
						- Task 1
							- ```python
							  class BankAccount:
							      def __init__(self, balance=0):
							          self.balance = balance
							      
							      def deposit(self, amount):
							          self.balance += amount
							      
							      def withdraw(self, amount):
							          if amount > self.balance:
							              print("Insufficient funds")
							          else:
							              self.balance -= amount
							      
							      def get_balance(self):
							          return self.balance
							      
							  account1 = BankAccount()
							  account1.deposit(50)
							  account1.withdraw(25)
							  account1.get_balance()
							  ```
						- Handle exceptions in constructor to prevent errors
						- To handle multiple accounts
							- ```python
							  class Person:
							      def __init__(self, fname, sname):
							          self.firstname = fname
							          self.surname = sname
							          self.account_list = []
							         
							  	def get_firstname(self):
							          return self.firstname
							  
							      def add_account(self, acc):
							          self.account_list.append(acc)
							          
							      def get_account(self, i):
							          return self.account_list[i]
							  
							      def count(self):
							          return len(self.account_list)
							  
							      def __str__(self): # toString
							          return f'{self.firstname} {self.surname}'
							  
							      def addition(self, a, b):
							          return a + b
							      
							  
							  acc = BankAccount(60)
							  acc2 = BankAccount(160)
							  p = Person('Allan', 'Turing')
							  p.add_account(acc)
							  p.add_account(acc2)
							  
							  print(p.get_account(1))
							  ```
						- setter and getter methods set the value of an attribute vs return the value
							- ```python
							  def set_firstname(self, fname):
							    	self.firstname = fname
							  
							  def get_firstname(self):
							    	return self.firstname
							  ```
					- ## Afternoon
						- `Python_OOP_2.ipynb`
						  id:: 686bcb9b-e06a-43bc-a5c0-4d96c7478350
						- ((6838256b-9e11-44cc-94a0-6170bf299c55))
						- ((6838256b-91b1-4e31-86c3-7531a3184dfc))
						- Factory methods for creating classes
							- Instead of `self` as a parameter it can use `cls`
						- `OOP_Activity.ipynb`
						  id:: 686bbafc-1aab-463f-a89f-9add6f78ffb0
						  collapsed:: true
							- Task 1
								- ```python
								  class Person:
								      def __init__(self, name, email, phone):
								          self.name = name
								          self.email = email
								          self.phone = phone
								      
								      def get_name(self):
								          return self.name
								      
								      def get_email(self):
								          return self.email
								      
								      def get_phone(self):
								          return self.phone
								      
								  class Volunteer(Person):
								      def __init__(self, name, email, phone, v_id, monthly_hours):
								          super().__init__(name, email, phone)
								          self.v_id = v_id
								          self.monthly_hours = monthly_hours
								      
								      def get_id(self):
								          return self.v_id
								      
								      def get_monthly_hours(self):
								          return self.monthly_hours
								      
								      def set_monthly_hours(self, monthly_hours):
								          self.monthly_hours = monthly_hours
								  
								  p = Person('Bob', 'wdad@aol.com', '0770313')
								  v = Volunteer('Sally', 'dwad@mail.com', '077123', '31231', '20')
								  v.get_name()
								  ```
						- Abstract classes
						  id:: 686bc568-0586-4ef8-ac26-09d4ec681021
						  collapsed:: true
							- `AbstractClasses.ipynb`
							  id:: 686bc573-9fcd-4031-9588-3497a3edb021
							- ![image.png](../assets/image_1751895212534_0.png)
							- Template for implementing a method, where they each have different method but a method name in common
							- It defines a common interface that all subclasses must implement
							- Opposite of abstract methods is concrete
							- A class with only abstract methods and no concrete is called an interface
							- ```python
							  from abc import ABC, abstractmethod
							  
							  class Polygon(ABC): # abstract class, some methods are abstract, but some have implementation; interface
							      # abstract method
							      @abstractmethod
							      def noofsides(self):
							          pass
							      @abstractmethod
							      def addition(self, a, b):
							          pass
							  ```
								- `@abstractmethod` is a decorator
									- It's an existing function that is executed whenever your function is called
									- Using decorators is a great way to extend the functionality of functions
							- Task 4
								- ```python
								  from abc import ABC, abstractmethod
								  
								  class Shape:
								      @abstractmethod
								      def calculate_area(self):
								          pass
								  
								  class Square(Shape):
								      def __init__(self, side_length):
								          self.side_length = side_length
								      
								      def calculate_area(self):
								          return self.side_length ** 2
								      
								  square1 = Square(5)
								  square1.calculate_area()
								  ```
							- Related: ((686bd22a-0dde-492c-bec3-d5207f338b81))
						- Decorators and Generators
						  id:: 686bd38a-2a98-411b-98a3-9398503681a5
							- They're not linked, not sure why they're being talked together
							- `Decorators_Generators.ipynb`
							  id:: 686bd22a-0dde-492c-bec3-d5207f338b81
								- Decorators are a great way to extend the functionality of a function without having to figure out where you need to add the functionality to an existing function
								- Decorators are applied from bottom to top
									- ```python
									  @split_string
									  @uppercase_decorator
									  
									  def say_hi():
									      return 'hello there'
									  say_hi()
									  ```
								- Creating decorators
									- ```python
									  def uppercase_decorator(function): #parameter is a function
									      def wrapper(): # inner function can access parameter of outer function
									          func = function() # here func is function - obtained from parameter of outer function
									          make_uppercase = func.upper() #func calls the string method upper() to turn a string to uppercase
									          return make_uppercase # now return the upcased string
									  
									      return wrapper
									  ```
							- Generators
								- Generators return data in chunks by utilising `yield` instead of `return` to return data in multiple stages
								- Generators use `yield`. `yield` keyword is like return but it instead pauses and waits instead of terminating
									- ```python
									  def my_gen():
									    	yield 3
									      yield 5
									      yield 4
									      yield 11
									      
									  a_gen = my_gen()
									  print(next(a_gen))
									  print(next(a_gen))
									  ```
						- Test Driven Development
						  id:: 686bd6af-6d00-4d36-b7f3-da69c23dec65
							- `Test Driven Development - Part 2.ipynb`
							  id:: 686bd6ec-fdd0-4878-a335-c61f871a2782
							- `pytest -v test_everything.py` to execute
								- ```python
								  from things import add
								  
								  def test_checking():
								      assert 1 == 1
								      
								  def test_check2():
								    	assert 3 == 3
								  
								  def test_add():
								    	assert add(1,2) == 3
								  ```
								- `things.py`
									- ```python
									  def add(a,b):
									      return a + b
									  ```
							- `@pytest.fixture` initiates an instance of your method for every test
								- e.g.
				- # Day 2
				  collapsed:: true
					- ## Morning
						- `Test Driven Development - Part 1.ipynb`
						  id:: 686bd4bf-6208-4ec3-b218-bfd39344ca5b
							- OOP is about using classes as the main construct for organising code
							- Class - a template, blueprint for creating objects. It precedes the existence of objects - classes are needed first
							- Composition example, no ((6838256b-9e11-44cc-94a0-6170bf299c55))
							  id:: 686cda04-2f21-49e3-b3c4-6c1b69675367
								- ```python
								  class Car:
								    	def __init__(self, model, price, windows):
								        	self.model = model
								          self.price = price
								          self.wheel = None
								          self.windows = windows
								        
								  class Wheel:
								    	def __init__(self, s):
								        	self.size = s
								  
								  class Windows:
								    	def __init__(self, colour):
								        	self.colour = colour
								  
								  class Owner:
								    	def __init__(self, firstname, surname):
								        	self.firstname = firstname
								          self.surname = surname
								  
								  car = Car('Honda', 2000, None)
								  ```
									- `self.size` = attribute, because you're creating a new variable
										- It's then be assigned with the value of the parameter `size`
							- Reviewing
								- ((6838256b-9e11-44cc-94a0-6170bf299c55))
								- ((686bd38a-2a98-411b-98a3-9398503681a5))
								- `__init__` is known as a constructor, or specifically an initaliser
							- ### Another Task
							  collapsed:: true
								- WIP 1
									- 2 tests
										- ```python
										  import pytest
										  from calculator import Calculator
										  
										  # Constants
										  
										  NUMBER_1 = 3.0
										  NUMBER_2 = 2.0
										  
										  # Fixtures
										  
										  @pytest.fixture
										  def calculator():
										      return Calculator()
										  
										  # Helper
										  
										  def verify_answer(expected, answer, last_answer):
										      assert expected == answer
										      assert expected == last_answer
										  
										  # Test Cases
										  
										  def test_last_answer_init(calculator):
										      assert calculator.last_answer == 0.0
										  
										  def test_multiply(calculator):
										      answer = calculator.multiply(NUMBER_1, NUMBER_2)
										      verify_answer(6.0, answer, calculator.last_answer)
										  ```
									- 2 tests passed
										- ```python
										  class Calculator:
										      def __init__(self):
										          self.last_answer = 0.0
										      
										      def multiply(self, a, b):
										          self.last_answer = a * b
										          return self.last_answer
										  ```
								- WIP 2
									- ```python
									  @pytest.mark.parametrize("a,b,expected", [
									      (NUMBER_1, NUMBER_2, NUMBER_1),
									      (NUMBER_2, NUMBER_1, NUMBER_1),
									      (NUMBER_1, NUMBER_1, NUMBER_1),
									  ])
									  def test_maximum(calculator, a, b, expected):
									      answer = calculator.maximum(a, b)
									      verify_answer(expected, answer, calculator.last_answer)
									  ```
									- Test passed
										- ```python
										  def maximum(self, a, b):
										    if a > b:
										      self.last_answer = a
										    else:
										      self.last_answer = b
										      return self.last_answer
										  ```
							- Related: ((686bd6ec-fdd0-4878-a335-c61f871a2782))
						- `Constructors_overloading.ipynb`
						  id:: 686ceec9-aad9-419b-be36-9f4466988a15
						  collapsed:: true
							- If you make two functions with the same name, you have to use the last function
							- Overloading in Python can be tricky but done like so:
								- ```python
								  class A(): 
								      def __init__(self,a,b,c=None): 
								          if(type(a)==int and type(b)==int and c==None): 
								              print("c(int a , int b)") 
								               
								          elif(type(a)==str and type(b)==int and c==None): 
								              print("c(String a , int b)") 
								               
								          elif(type(a)==str and  type(b)==str and c==None): 
								              print("c(String a , String b)") 
								               
								          elif(type(a)==str and type(b)==str and type(c)==int): 
								              print("c(String a , String b , int c)") 
								               
								          else: 
								              print("c(String a , String b , int c)") 
								  ```
							- You may want to overload constructors so that parameters are optional
								- ![image.png](../assets/image_1751969792092_0.png)
								- Alternative can use default values as `None`
									- `def __init__(self, firstname = None, middlename = None, surname = None)`
							- `//` = integer division i.e. rounds the result to an integer
							- `__setattr__()` function
								-
						- `classmethods_statics.ipynb`
						  id:: 686cf42c-670b-4c55-bcad-35d8337d5c7f
							- Class methods and class variables
								- **### class methods**
								- are methods that are called on the class itself, not on a specific instance.
								- it belongs to a class level, and all class instances share a class method.
								- a class method is bound to the class and not the object of the class.
								- it can access only class variables.
								- it can modify the class state by changing the value of a class variable that would apply across all the class objects.
								- **The class method has a **`cls`**** as the first parameter, which refers to the class.****
								- It doesn't affect class instances
							- Class variables
								- ```python
								  class Student:
								      school_name = 'ABC School'
								      def __init__(self, name, age):
								          pass
								  ```
							- Class methods
								- ```python
								  class Student:
								      def __init__(self, name, age):
								          pass
								  
								      @classmethod
								      def change_school(cls, name):
								          print(Student.school_name)
								          Student.school_name = name
								  ```
								- Unlike instance methods this will affect all instances, new and existing
								- You need both the `@classmethod` decorator + `cls` parameter
							- Factory methods
								- ```python
								  from datetime import date
								  
								  class Student:
								      def __init__(self, name, age):
								          self.name = name
								          self.age = age
								  
								      @classmethod
								      def calculate_age(cls, name, birth_year):
								          # calculate age and set it as a age
								          # return new object
								          return cls(name, date.today().year - birth_year)
								  
								      def show(self):
								          print(f"{self.name}'s age is {self.age}")
								  
								  jessa = Student('Jessa', 20)
								  jessa.show()
								  
								  # create new object using the factory method
								  joy = Student.calculate_age("Joy", 1999) # factory method
								  joy.show()
								  ```
									- They use `return cls` prefix or `return Student`, it's the same thing
									- They can be used to create instances of a class in different ways than just `instance1 = Student(var1, var2)`
							- Static methods
								- They don't use `cls` or `self`
								- They're utility methods often used by other methods
							- `Activities_1.ipynb`
							  id:: 686cf93c-7a38-47e9-b969-103dab18da24
								- Function comments
									- ```python
									  @classmethod
									  def get_total_accounts(cls):
									    """Get total number of accounts created"""
									    return cls.total_accounts
									  
									  @classmethod
									  def get_total_accounts(cls):
									    '''Get total number 
									    of accounts created'''
									    return cls.total_accounts
									  ```
									- `help(get_total_accounts()` in Python will show the code comment
									- `get_total_accounts.__doc__` does similar
					- ## Afternoon
						- Dictionaries in Python
							- `{'name':'Bob', 'salary': 35000, 'department':'Phyics'}`
						- `Exceptions.ipynb`
						  id:: 686d0be4-cbde-490b-b561-3eee0505488d
							- `try...except` to handle errors
								- ```python
								  a = 35
								  b = 0
								  
								  try:
								    	a/b
								  except: ZeroDivisionError:
								    	print('not allowed')
								  ```
							- Classes start with a capital e.g. `TypeError`
							- `else` and `finally` clauses
						- `Overview_OOP_MRO.ipynb`
						  id:: 686d0da3-12a9-4bb3-93d3-efb0ecfcfd7c
							- Class diagrams in UML
							- Mixin is used as an intermediary between two classes, it's useless by itself
							- `__mro__` defines the order methods are resolved (Method Resolution Order) in multiple inheritance
								- ```python
								  class Wrestler(Fighter, Employee)
								  ```
						- `Activities_2.ipynb`
						  id:: 686d14d3-cb37-4b83-8303-d56043c7d589
						  collapsed:: true
							- `__str__` is used as `toString` method usually
							- Task 1)
							- Task 2) Another factory method example
								- ```python
								  import time
								  
								  class Date:
								      def __init__(self, year, month, day):
								          self.year = year
								          self.month = month
								          self.day = day
								  
								      @classmethod
								      def today(cls):
								          tm = time.localtime()
								          return cls(tm.tm_year, tm.tm_mon, tm.tm_mday)
								  
								  d = Date.today()
								  ```
							- Task 3
								- ```python
								  class Parent:
								      def method(self):
								          print("Parent")
								  
								  
								  class A(Parent):
								      def method(self):
								          print("A")
								          super().method()
								  
								  
								  class B(Parent):
								      def method(self):
								          print("B")
								          super().method()
								  
								  
								  class C(A, B):
								      pass
								  
								  
								  C().method()
								  
								  # Lessons:
								  # Don't duplicate functionality in multiple subclasses
								  # Note that super() methods are executed last of all
								  # `C.__mro__` can be executed to see what the Method Resolution Order actually is
								  ```
							- Task 4) Mixin
								- ```python
								  class Dog:
								      def noise(self):
								          return "Woof"
								  
								      def chase(self):
								          return "Chasing!"
								  
								  
								  class Bike:
								      def noise(self):
								          return "Ding!"
								  
								      def pedal(self):
								          return "Pedaling!"
								  
								  
								  class Loud:
								      def noise(self):
								          return super().noise().upper() # uppercase
								  
								  
								  class LoudDog(Loud, Dog):
								      pass
								  
								  
								  class LoudBike(Loud, Bike):
								      pass
								  
								  LoudBike().noise()
								  # 'DING!'
								  ```
						- ```python
						      @classmethod
						      def get_school_info(cls):
						          return f"School: {cls.school_name}, Total Students: {cls.total_students}"
						      
						      @staticmethod
						      def is_passing_grade(grade):
						          return grade >= 60
						  
						      @classmethod
						      def change_school_name(cls, new_name):
						          school_name = new_name
						          return f"{cls.school_name} updated to {new_name}"
						  ```
						- Number to string coercion
							- ```python
							  result = 87
							  name = 'Bob'
							  
							  print(name + result)
							  print(f'{name} {result}')
							  ```
						- `jmkanyaru@gmail.com`
						-
				- Related: ((63fe5472-f72c-4a29-9067-7d7edc128d06))
			- ((63fe5472-f72c-4a29-9067-7d7edc128d06)) features
			  id:: 6828f32a-48e0-44dc-835b-6e46001d7d2b
				- [`@dataclass` decorator](https://docs.python.org/3/library/dataclasses.html)
				  collapsed:: true
					- `p = Point(1, 2)` example
						- ```python
						  p.x = 1
						  p.y = 2
						  p.z = 0   # default value
						  ```
				- Related: ((63fe5472-f72c-4a29-9067-7d7edc128d06))
	- # Applications/Usecases
		- Scripting
		  id:: 65cd4034-f782-4595-9f55-9baa2c3460cf
		  collapsed:: true
			- ((685fd5ae-ab52-4377-924e-b2d0bfb74241)) [and PEP 723](https://www.cottongeeks.com/articles/2025-06-24-fun-with-uv-and-pep-723) to allow running scripts without needing a virtual environment
			  collapsed:: true
				- OP
					- uv also provides this nifty tool called `uvx` (kinda like `npx` from the Node/NPM ecosystem for Javascript/Typescript packages) which can be used to invoke a Python tool inside a package. `uvx` takes care of creating a (cached) disposable virtual environment, setting up the right Python version and installing all the dependencies before running.
					- ```bash
					  $ uvx ruff --version
					  Installed 1 package in 5ms
					  ruff 0.12.0
					  ```
					- ## PEP 723 - Inline script metadata[¶](https://www.cottongeeks.com/articles/2025-06-24-fun-with-uv-and-pep-723#pep-723---inline-script-metadata)
						- [PEP 723](https://peps.python.org/pep-0723/) is a Python Enhancement Proposal that _specifies a metadata format that can be embedded in single-file Python scripts to assist launchers, IDEs and other external tools which may need to interact with such scripts._
						- Here is the example directly lifted from the proposal:
						- ```python
						  # /// script
						  # requires-python = ">=3.11"
						  # dependencies = [
						  #   "requests<3",
						  #   "rich",
						  # ]
						  # ///
						  
						  import requests
						  from rich.pretty import pprint
						  
						  resp = requests.get("https://peps.python.org/api/peps.json")
						  data = resp.json()
						  pprint([(k, v["title"]) for k, v in data.items()][:10])
						  ```
					- Can then run this with `uv run pep.py`
					- Shebang line
						- Note the shebang line: `#!/usr/bin/env -S uv run --script`. It is important to specify `uv run` with the `--script` flag when used on the shebang line.
					- Example2: `./ytt.py https://www.youtube.com/watch?v=zgSQr0d5EVg`
						- ```python
						  #!/usr/bin/env -S uv run --script
						  # /// script
						  # requires-python = ">=3.8"
						  # dependencies = [
						  #     "youtube-transcript-api",
						  # ]
						  # ///
						  
						  import sys
						  import re
						  from youtube_transcript_api import YouTubeTranscriptApi
						  from youtube_transcript_api.formatters import TextFormatter
						  
						  if len(sys.argv) < 2:
						      print('Usage: provide YouTube URL or video_id as argument', file=sys.stderr)
						      sys.exit(1)
						  
						  url_or_id = sys.argv[1]
						  
						  # Extract video ID from URL if it's a full URL
						  video_id_match = re.search(r'(?:v=|/)([a-zA-Z0-9_-]{11})', url_or_id)
						  if video_id_match:
						      video_id = video_id_match.group(1)
						  else:
						      # Assume it's already a video ID
						      video_id = url_or_id
						  
						  try:
						      ytt_api = YouTubeTranscriptApi()
						      transcript = ytt_api.fetch(video_id)
						      formatter = TextFormatter()
						      print(formatter.format_transcript(transcript))
						  except Exception as e:
						      print(f'Error: {e}', file=sys.stderr)
						      sys.exit(1)
						  ```
			- https://sh.readthedocs.io/en/latest/index.html
			- Related: [[Programming]] : ((65cd3f7c-24c9-4260-b67c-2fe5f005e6a2))
		- `field-device/create_tunnel.py`
		  collapsed:: true
		  Example of how to manage reverse SSH tunnel forwarding
			- ```python
			  import paramiko
			  import sys
			  import time
			  import threading
			  from socket import socket
			  from select import select
			  from ppadb.client import Client as AdbClient
			  
			  SSH_PORT = 22
			  ADB_SERVER_IP = "localhost"
			  
			  # Hold all threads associated with the connection ,allowing us to ensure they are close when a connction drops
			  connection_threads = []
			  
			  # Handle the actual forwarding of data back and forth through the reverse tunnel
			  def handler(
			    chan: paramiko.channel.Channel,
			    host: str,
			    port: int,
			    threads_stop: threading.Event
			    ):
			    sock = socket()
			    try:
			    	sock.connect((host, port))
			    except Exception as e:
			      print("Forwarding request to %s:%d failed: %r" % (host, port e))
			    	return
			  
			    print(
			      "Connected! Tunnel open %r -> %r -> %r"
			      % (chan.origin_addr, chan.getpeername(), (host, port))
			    )
			    while not thread_stop.is_set():
			  	  r, w, x = select([sock, chan], [], [])
			    	if sock in r:
			        data = sock.recv(1024)
			        if len(data) == 0:
			            break
			        sock.send(data)
			    chan.close()
			    sock.close()
			    print("Tunnel closed from %r" % (chan.origin_addr,))
			  
			  # Await a connection through the tunnel and initialise a handler to deal with it
			  def accept_connection(
			    remote_host: str,
			    remote_port: int,
			    transport: paramiko.transport.Transport,
			    thread_stop: threading.Event
			    ):
			    while not thread_stop.is_set():
			      chan = transport.accept(10)
			      if chan is None:
			          continue
			      thr = threading.Thread(
			          target=handler,
			          args=(chan, remote_hist, remote_port, thread_stop),
			          daemon = True
			      )
			      connection_threads.append(thr)
			      thr.start()
			  
			  # Open the reverse tunnel to allow communication from the server to the device
			  def reverse_forward_tunnel(
			    server_port: int,
			    remote_host: str,
			    remote_port: int,
			    transport: paramiko.transport.Transport,
			    stop_threads: threading.Event
			    ):
			    transport.request_port_forward("", server_port)
			    connection_thread = threading.Thread(
			      target = accept_connection, 
			      args = (remote_host, remote_port, transport, stop_threads),
			      daemon = True
			    )
			    connection_threads.append(connection_thread)
			    connection_thread.start()
			  
			  def main():
			    stop_threads = threading.Event()
			    stop_threads.clear()
			  
			    ssh_client = paramiko.SSHClient()
			    ssh_client.load_system_host_keys()
			    transport = ssh_client.get_transport()
			    ip_address = sys.argv[1]
			  
			    while True:
			      print(f"Attempting connection {ip_address}")
			      try:
			          ssh_client.connect(
			              ip_address, 
			              SSH_PORT
			              "user"
			          )
			          transport = ssh_client.get_transport()
			          reverse_forward_tunnel(WEBSOCKIFY_OUTPUT_PORT, ADB_SERVER_IP, ADB_SERVER_PORT, transport, stop_threads)
			  
			          while transport.is_active():
			              print("Connection is healthy")
			              time.sleep(10)
			  
			          stop_threads.set()
			          for thread in connection_threads:
			              thread.join()
			          del connection_threads[:]
			          stop_threads.clear()
			  
			      except exception as e:
			          print(f"Connection failed with error : {e}")
			          time.sleep(5)
			  
			  if __name__ == "__main__":
			  	main()
			  ```
	- # Ecosystem
		- ## Modules
			- Standard Library
				- `os`
				  collapsed:: true
					- `os.system`
						- ((68f7812f-6700-46cc-9cfb-2048994fed5b))
				- `subprocess`
				  collapsed:: true
					- Converting running a command using `os.system` to using `subprocess.Popen`
					  id:: 68f7812f-6700-46cc-9cfb-2048994fed5b
						- Example
							- Originally:
							  ```python
							  import os
							  os.system("start.sh")
							  ```
							- Becomes:
							  ```python
							  import subprocess
							  process = subprocess.Popen(["bash", "start.sh"])
							  ```
						- Explanation
							- ### `os.system()`
								- Very old, simple way to run a command.
								- Runs the command in a **new shell** (`/bin/sh`).
								- Blocks (waits) until the command completes.
								- Returns only the **exit code** (integer), not the output.
								- Harder to handle errors or capture logs.
							- ### `subprocess.Popen()`
								- Modern, flexible way to run external programs.
								- Doesn’t block by default — **runs asynchronously**.
								- Lets you:
									- Capture output (`stdout` / `stderr`)
									- Provide input
									- Control environment variables
									- Terminate the process
									- Avoid invoking an intermediate shell
			- `argparse` 
			  collapsed:: true
			  handles command-line arguments
				- AKA for sending arguments/flags when executing a Python script
				- Example
					- Executing a script
						- ```bash
						  python script.py 5.5
						  ```
					- In a separate function to the `main` loop:
						- ```python
						  import argparse
						  
						  def parse_args():
						      parser = argparse.ArgumentParser(description="test")
						      parser.add_argument('test2', nargs='*', help="test3")
						      return parser.parse_args()
						  
						  def main():
						      args = parse_args()
						  
						      test2 = None
						      if len(args.test2) == 1:
						          try:
						              test2 = float(args.test2[0])
						          except ValueError:
						              pass
						  
						      print(f"test2 = {test2}")
						  
						  if __name__ == "__main__":
						      main()
						  
						  ```
					- ```python
					  import argparse
					  
					  def main():
					      parser = argparse.ArgumentParser(description="test")
					      parser.add_argument('test2', nargs='*', help="test3")
					      args = parser.parse_args()
					  
					      if len(args.test2) == 1:
					          try:
					              test2 = float(args.test2[0])
					          except:
					              pass
					  
					      print(f"test2 = {test2}")
					  ```
						- ### `parser = argparse.ArgumentParser(description="test")`
							- Creates an **argument parser object** with a description `"test"`.
							- That description is shown when the user runs:
							- ```bash
							  python script.py --help
							  ```
						- ### `parser.add_argument('test2', nargs='*', help="test3")`
							- Adds a **positional argument** named `test2`.
							- `'test2'` → The name of the argument.
							- `nargs='*'` → Means it will accept **zero or more values**.
							- `help="test3"` → The help message for that argument.
							- So you could run the script as:
							- ```bash
							  python script.py
							  python script.py 123
							  python script.py 1 2 3
							  ```
							- and in all cases, `args.test2` will be a **list of strings**.
							- Example:
								- `python script.py 1 2 3` → `args.test2 == ['1', '2', '3']`
						- ### `args = parser.parse_args()`
							- Parses the command-line arguments and returns them in a `Namespace` object (`args`).
						- ```python
						  if len(args.test2) == 1:
						      try:
						          test2 = float(args.test2[0])
						      except:
						          pass
						  
						  ```
							- If there’s exactly one argument, it tries to convert it to a **float** (a number).
							- If conversion fails, it silently ignores the error (but that’s not ideal—see below).
			- `enum`
			  collapsed:: true
				- Enums
				  AKA enumerations
					- Pros/Cons
						- Pros
							- Replaces magic numbers or strings with meaningful names, making code easier to read and understand
							- Useful for switching on states, comparisons, or validating values in your code.
					- Data types that define a set of symbolic, named constants that are grouped together for clarity, safety, and readability
					- Features
						- In [[Python]]
							- ((68d27a88-5cfa-4b35-95f1-1a7b466a320f))
					- Examples
						- In [[Python]]
						  id:: 68cd7186-fdf4-4e98-9cde-f39f7909d6b0
							- ```python
							  from enum import Enum
							  
							  class Status(Enum):
							      PENDING = 1
							      IN_PROGRESS = 2
							      COMPLETED = 3
							      FAILED = 4
							  ```
					- Accessing values in an enum
						- In the ((68d10df3-8e92-4884-8463-3f38bf31b10c))
							- Using dot notation and it's attributes
							  id:: 68d27a88-5cfa-4b35-95f1-1a7b466a320f
								- `DeviceConnectionState.OFFLINE.name` = `"OFFLINE"`
								- `DeviceConnectionState.OFFLINE.value` will be `"0"`
							- Converting Enum to a list to use their order (index)
								- ```python
								  list(DeviceConnectionState)[0]       # Returns DeviceConnectionState.OFFLINE
								  list(DeviceConnectionState)[0].name  # Returns "OFFLINE"
								  list(DeviceConnectionState)[0].value # Returns "0"
								  list(DeviceConnectionState)[1]       # Returns DeviceConnectionState.DEVICE
								  list(DeviceConnectionState)[1].name  # Returns "DEVICE"
								  list(DeviceConnectionState)[1].value # Returns "1"
								  ```
				- `from enum import Enum, unique`
				- `@unique` class decorator
				  id:: 68cd70a2-aa4d-4ea8-840b-00fffdcb81ae
					- This is a decorator that ensures all enum values are unique. If you accidentally assign the same value to multiple names, @unique will raise an error.
					- Example
					  id:: 68d10df3-8e92-4884-8463-3f38bf31b10c
						- ```python
						  @unique
						  class DeviceConnectionState(Enum)
						     OFFLINE = "0"
						     DEVICE = "1"
						  ```
			- `pytest`
			  id:: 68dbece2-53aa-438f-b0dc-bf45f503beb9
			  collapsed:: true
			  Unit testing framework
				- Fixtures
				  collapsed:: true
				  i.e. using flags when executing a test to pass in variables
					- `conftest.py`
						- Example
							- ```python
							  import pytest
							  
							  def pytest_addoption(parser):
							    parser.addoption(
							    	"--devices",
							      action="store",
							      default=0,
							      type=int,
							      help="Number of devices expected in the test"
							    )
							  
							  @pytest.fixture
							  def devices(request)
							  	return request.config.getoption("--devices")
							  ```
								- `test_integration_device_monitor.py`
									- ```python
									  import pytest
									  import subprocess
									  from device_monitor import DeviceConnectionState, AndroidDevice, DeviceManager
									  from unittest.mock import patch
									  from ppadb.client import Client as ADBClient
									  from ppadb.device import Device as ADBDevice
									  
									  def test_devices_detected(capsys, devices):
									    device_manager = DeviceManager()
									    device_manager._DeviceManager__track_devices()
									    assert len(device_manager.devices_by_serial_values()) == devices
									  
									  def test_temperature_detected(capsys, devices):
									    if devices == 0:
									      pytest.skip("Skipping: requires --devices to be greater than 0")
									    device_manager = DeviceManager()
									    MAX_TEMP_C = 40.0
									    device_manager.monitor_battery_temperatures(MAX_TEMP_C)
									    
									    result = subprocess.run(
									    	["adb", "shell", "dumpsys", "battery", "get", "temp"],
									      capture_output=True,
									      text=True,
									    )
									    temp = result.stdout.strip()
									    temp_celsius = float(temp) / 10
									    
									    captured = capsys.readouterr()
									    lines = captured.out.splitlines()
									    assert any (f"{temp_celsius} is the current temp" in line for line in lines)
									  ```
								- Can trigger the pytest with `pytest test_integration_device_monitor.py --devices 1` for example
				- [`pytest-mock`](https://pypi.org/project/pytest-mock/)
				  id:: 68dbece7-5497-4678-8dac-ec557e29d8e9
				  collapsed:: true
					- Relies on `unittest.mock`, which is now part of Python's standard library from 3.3+. Small wrapper to make it easier to use with `pytest`
					- [Where to patch](https://docs.python.org/3/library/unittest.mock.html#where-to-patch) - it should be where a function instantiates a class, rather than within the class itself for example
					- ## Lines
						- `assert_called_once_with()` - Confirms the correct shell command was executed
							- `mock_device.shell.assert_called_once_with('dumpsys battery get temp')`
					- ## Usage
						- `mocker.Mock()` vs `mocker.MagicMock()`
						  collapsed:: true
							- ## `mocker.Mock()`
								- Basic mock object.
								- You can assign attributes and call methods freely:
									- ```python
									  mock_device = mocker.Mock()
									  mock_device.some_method()
									  mock_device.value = 42
									  ```
								- Does **not** implement Python “magic” methods (dunder methods) by default.
									- Examples: `__getitem__`, `__iter__`, `__len__`, `__enter__`, `__exit__`
							- ## `mocker.MagicMock()`
								- Subclass of `Mock` with **default implementations of magic/dunder methods**.
								- Useful if the object needs to behave like a sequence, context manager, or support other Python special methods:
									- ```python
									  mock_device = mocker.MagicMock()
									  len(mock_device)           # works because __len__ is implemented
									  for x in mock_device:       # works because __iter__ is implemented
									  with mock_device as m:     # works because __enter__/__exit__ are implemented
									  ```
								- Everything `Mock()` can do, `MagicMock()` can do **plus** the magic methods.
						- `mocker` vs `monkeypatch` as parameter
						  collapsed:: true
							- ### `mocker`
								- Comes from the **`pytest-mock` plugin**, which is basically a **wrapper around `unittest.mock`**.
								- Provides a pytest fixture `mocker` that exposes all the functionality of `Mock`, `MagicMock`, and `patch`.
								- Lets you do **classic mocking of objects, classes, or functions**.
								- Example
									- ```python
									  def test_connect(mocker):
									      from src.your_module import connect_adb
									      mock_dm = mocker.Mock()
									      mocker.patch("src.your_module.time.sleep", lambda x: None)
									      
									      connect_adb(mock_dm)
									      mock_dm.connect.assert_called_once()
									  ```
								- Similar to `unittest.mock.patch` but integrated as a pytest fixture.
								- Very handy for **patching imports, methods, or classes**, especially when you need to replace an object with a mock.
							- ### `monkeypatch`
								- Built-in **pytest fixture**.
								- Allows you to temporarily **replace objects, attributes, environment variables, or `sys.argv`** during a test.
								- Works automatically if you declare it as a function argument in a pytest test.
								- ### Example:
									- ```python
									  import pytest
									  
									  def test_argv(monkeypatch):
									      import sys
									      monkeypatch.setattr(sys, "argv", ["script_name", "50"])
									      from src.your_module import parse_args
									      assert parse_args() == 50
									  ```
								- Great for **patching system-level things** (`sys`, `os.environ`, `time.sleep`) or replacing functions temporarily.
								- Easy to use with pytest without importing `unittest.mock`.
					- ## Example
					  id:: 68f0f9d4-6d30-4154-8007-89a2918c860e
						- [Python tests | Pytest Mock and Patch - YouTube](https://www.youtube.com/watch?v=WlY8xJt8XMU)
						  collapsed:: true
							- Template
								- ```python
								  from unittest.mock import patch
								  from <directory name.file name> import <function1> # the one you want to assert
								  
								  @patch('<directory name.file name>.function2')
								  def test_function1_from_function2(mock_get):
								    mock_get.return_value = "def"
								    assert function1() == "def123"
								  ```
							- Example
								- ```python
								  from unittest.mock import patch
								  from app.fetch_www import parse
								  
								  @patch('app.fetch_www.fetch_net')
								  def test_parse_from_fetch_net(mock_get):
								    mock_get.return_value = "def"
								    assert parse() == "def123"
								  ```
						- [Intro to Python Mocks | Python tutorial - YouTube](https://www.youtube.com/watch?v=xT4SV7AH3G8) = `unittest.mock` library
						  collapsed:: true
							- Your function
							  ```python
							  import requests
							  
							  def len_joke():
							    joke = get_joke()
							    return len(joke)
							  
							  def get_joke():
							    url = 'http://api.icndb.com/jokes/random'
							    
							    response = requests.get(url)
							    
							    if response.status_code == 200:
							      joke = response.json()['value']['joke']
							    else:
							      joke = 'No jokes'
							      
							    return joke
							  
							  if __name__ == '__main__':
							    print(get_joke())
							  ```
							- Your test
							  ```python
							  import unittest
							  from unittest.mock import patch
							  from main import 
							  
							  class TestJoke(unittest.TestCase):
							    
							    @patch('main.get_joke')
							    def test_len_joke(self, mock_get_joke):
							      mock_get_joke.return_value = 'one'
							      self.assertEqual(len_joke(), 3)
							      
							  if __name__ == '__main__':
							    unittest.main()
							  ```
						- Original
						  collapsed:: true
							- ```python
							  # Your wrapper class (example)
							  class AndroidDevice:
							      def __init__(self, adb_device: ADBDevice):
							          self._adb_device = adb_device
							  
							      @property
							      def battery_temperature(self):
							          # in real life, might call: self._adb_device.shell("dumpsys battery")
							          return int(self._adb_device.shell("dumpsys battery | grep temperature").strip())
							  
							  def test_battery_temperature():
							    sample_client = ADBClient(host="localhost", port=7777)
							    sample_device = AndroidDevice(ADBDevice(sample_client, 'test1'))
							    assert sample_device.battery_temperature == 330
							  ```
							- With mocking
							  ```python
							  import pytest
							  from unittest.mock import MagicMock
							  from ppadb.client import Client as ADBClient
							  from ppadb.device import Device as ADBDevice
							  
							  def test_battery_temperature(mocker):
							      # Mock ADB device
							      mock_adb_device = mocker.MagicMock(spec=ADBDevice)
							      
							      # Pretend shell returns "330"
							      mock_adb_device.shell.return_value = "330"
							  
							      # Inject into our AndroidDevice wrapper
							      sample_device = AndroidDevice(mock_adb_device)
							  
							      # Assert our property parses correctly
							      assert sample_device.battery_temperature == 330
							  ```
						- GPT
						  collapsed:: true
							- ```python
							  def test_register_callback(mocker):
							      dm = DeviceManager()
							  
							      # Create mock function
							      fake_callback = mocker.Mock()
							  
							      # Register it
							      dm.register_callback(fake_callback)
							      assert fake_callback in dm.callbacks
							  
							  
							  def test_notify_all_calls_registered_callbacks(mocker):
							      dm = DeviceManager()
							      fake_callback1 = mocker.Mock()
							      fake_callback2 = mocker.Mock()
							  
							      dm.register_callback(fake_callback1)
							      dm.register_callback(fake_callback2)
							  
							      dm.notify_all()
							  
							      fake_callback1.assert_called_once_with("Device connected!")
							      fake_callback2.assert_called_once_with("Device connected!")
							  
							  ```
								- ## Line-by-line explanation
									- ### `def test_register_callback(mocker):`
										- Defines a pytest test function.
										- The argument `mocker` is a fixture provided by the **`pytest-mock`** plugin.
										  
										  It gives you an interface to create mocks and spies (`mocker.Mock()`, `mocker.patch()`, etc.).
										  
										  ---
										- ### `dm = DeviceManager()`
										- Creates a new instance of the class under test.
										- This is the object whose behavior we’re verifying.
										  
										  ---
										- ### `fake_callback = mocker.Mock()`
										- Makes a **mock function**.
										- It behaves like a callable function but records every time it’s called and with what arguments.
										- Think of it as a “spy” you can inspect later.
										  
										  ---
										- ### `dm.register_callback(fake_callback)`
										- Calls your code under test.
										- In the `DeviceManager` class, this should store the function in `self.callbacks`.
										  
										  ---
										- ### `assert fake_callback in dm.callbacks`
										- Checks that `register_callback` actually stored the function.
										- This ensures that the `DeviceManager` correctly registered the callback.
										- ---
									- ### `def test_notify_all_calls_registered_callbacks(mocker):`
										- A second, separate test function for verifying that callbacks are **called**, not just stored.
										- `dm = DeviceManager()`
										  New instance again (tests should be isolated).
										- ### `fake_callback1 = mocker.Mock()`
										- ### `fake_callback2 = mocker.Mock()`
										- Create **two** independent mock functions so you can see if both get called.
										  
										  ---
										- ### `dm.register_callback(fake_callback1)`
										- ### `dm.register_callback(fake_callback2)`
										- Add both mocks to `DeviceManager.callbacks`.
										  
										  ---
										- ### `dm.notify_all()`
										- This should loop through all registered callbacks and call them with `"Device connected!"`.
										  
										  ---
										- ### `fake_callback1.assert_called_once_with("Device connected!")`
										- ### `fake_callback2.assert_called_once_with("Device connected!")`
										- These are **assertions provided by `unittest.mock`**.
										- They check that:
											- Each mock was called exactly **once**.
											- The call included exactly the argument `"Device connected!"`.
											  
											  If either callback wasn’t called, or was called with the wrong argument, pytest will show a detailed failure message like:
											- ```
											  AssertionError: Expected call: mock('Device connected!')
											  Actual call: mock('Device disconnected!')
											  ```
								- Summary
									- | Line                        | Purpose                                    |
									  | --------------------------- | ------------------------------------------ |
									  | `mocker.Mock()`             | make fake callable that tracks calls       |
									  | `dm.register_callback()`    | exercise your real code                    |
									  | `assert ... in ...`         | verify registration behavior               |
									  | `dm.notify_all()`           | trigger callbacks                          |
									  | `assert_called_once_with()` | verify each callback was invoked correctly |
						- Device monitor examples
						  id:: 68ef9075-fab2-48c2-bf1b-3bf4cccbb59b
						  collapsed:: true
							- Meta
								- `python3 -m pytest tests/test_unit_device_monitor.py`
								- Directory structure
								  collapsed:: true
									- ```
									  my_project/
									  ├── pyproject.toml
									  ├── requirements.txt
									  ├── README.md
									  ├── src/
									  │   ├── __init__.py
									  │   └── device_monitor.py
									  │   └── android_device.py
									  │   └── main.py
									  ├── tests/
									  │   ├── conftest.py
									  │   └── test_unit_device_monitor.py
									  ```
									- Related: ((68e66df0-0f54-44b1-90b6-44769a958927))
								- `pyproject.toml`
								  collapsed:: true
									- ```
									  [tool.pytest.ini_options]
									  pythonpath = ["src"]
									  testpaths = ["tests"]
									  addopts = "-v" # verbose output
									  ```
								- Test imports
								  collapsed:: true
									- ```python
									  import pytest
									  from unittest.mock import Mock, MagicMock, patch
									  from src.android_device import DeviceConnectionState, AndroidDevice
									  from src.device_manager import DeviceManager
									  from src.main import parse_args, connect_adb, main
									  from ppadb.device import Device as ADBDevice
									  ```
							- `class DeviceManager:`
							  collapsed:: true
								- Code
									- ```python
									  class DeviceManager:
									      def __init__(self):
									          self.__adb_client = ADBClient("test")
									          self.__track_devices_connection = None
									  
									      def __connect(self):
									          self.__track_devices_connection = self.__adb_client.create_connection()
									  
									      def __track_devices(self):
									          device_notifications = self.__track_devices_connection.receive()
									  
									      def __manage_device_health(self, device, maxtemp):
									        connection_state = device.connection_state
									        if connection_state != DeviceConnectionState.ONLINE:
									          print("tst")
									          return
									        try:
									          temperature = device.battery_temperature
									          if temperature > maxtemp:
									            print("test"
									            device.shutdown()
									  ```
								- Test
									- ```python
									  from unittest.mock import MagicMock
									  from src.device_manager import DeviceManager
									  from src.device_module import DeviceConnectionState  # wherever this enum lives
									  
									  def test_manage_device_health_offline_device():
									      manager = DeviceManager()
									  
									      # Create a fake device
									      device = MagicMock()
									      device.connection_state = DeviceConnectionState.OFFLINE
									  
									      # Act
									      manager._DeviceManager__manage_device_health(device, maxtemp=50)
									  
									      # Assert
									      # Should NOT call shutdown() because device is offline
									      device.shutdown.assert_not_called()
									  
									  def test_manage_device_health_temperature_exceeds():
									      manager = DeviceManager()
									  
									      # Fake device that is online
									      device = MagicMock()
									      device.connection_state = DeviceConnectionState.ONLINE
									      device.battery_temperature = 75  # higher than max
									      device.shutdown = MagicMock()
									  
									      # Act
									      manager._DeviceManager__manage_device_health(device, maxtemp=50)
									  
									      # Assert
									      device.shutdown.assert_called_once()
									  
									  def test_manage_device_health_temperature_within_limit():
									      manager = DeviceManager()
									  
									      device = MagicMock()
									      device.connection_state = DeviceConnectionState.ONLINE
									      device.battery_temperature = 40  # below max
									      device.shutdown = MagicMock()
									  
									      # Act
									      manager._DeviceManager__manage_device_health(device, maxtemp=50)
									  
									      # Assert
									      device.shutdown.assert_not_called()
									  ```
							- `class DeviceManager.__track_devices()`
							  collapsed:: true
								- Code
									- ```python
									  class DeviceManager:
									      def __init__(self):
									          self.__adb_client = ADBClient("test")
									          self.__track_devices_connection = None
									  
									      def __connect(self):
									          self.__track_devices_connection = self.__adb_client.create_connection()
									  
									      def __track_devices(self):
									          device_notifications = self.__track_devices_connection.receive()
									  ```
								- Test
									- ```python
									  from unittest.mock import MagicMock, patch
									  from src.device_manager import DeviceManager
									  
									  
									  def test_track_devices_calls_receive():
									      # Patch ADBClient inside module under test
									      with patch("src.device_manager.ADBClient") as MockADBClient:
									          mock_client = MockADBClient.return_value
									          fake_connection = MagicMock()
									  
									          # The ADB client returns our fake connection when create_connection() is called
									          mock_client.create_connection.return_value = fake_connection
									  
									          # Instantiate DeviceManager and connect
									          manager = DeviceManager()
									          manager._DeviceManager__connect()  # call private connect()
									  
									          # Act — call the private __track_devices method
									          manager._DeviceManager__track_devices()
									  
									          # Assert — ensure receive() was called
									          fake_connection.receive.assert_called_once()
									  
									  ```
							- `main loop`
							  collapsed:: true
								- ```python
								  # main.py
								  from device_manager import DeviceMan
								  from utils import parse_args
								  
								  def main():
								      MAX_T_C = parse_args()
								      dev_man = DeviceMan()
								      while True:
								          dev_man.monitor_bt(MAX_T_C)
								  
								  if __name__ == "__main__":
								      main()
								  ```
								- Test
									- ```python
									  import pytest
									  from unittest.mock import MagicMock
									  
									  import main  # your module under test
									  
									  
									  def test_device_manager_instantiated(mocker):
									      # Mock dependencies
									      mock_device_man = mocker.patch("main.DeviceMan")  # replaces DeviceMan with a Mock class
									      mock_parse_args = mocker.patch("main.parse_args", return_value=42)
									  
									      # Mock the infinite loop by making monitor_bt raise a break condition after 1 call
									      instance = mock_device_man.return_value
									      instance.monitor_bt.side_effect = [None, KeyboardInterrupt()]
									  
									      # Run main() — it will stop after the simulated KeyboardInterrupt
									      with pytest.raises(KeyboardInterrupt):
									          main.main()
									  
									      # Assert DeviceMan() was called once
									      mock_device_man.assert_called_once()
									  
									      # Assert monitor_bt was called at least once
									      instance.monitor_bt.assert_called_with(42)
									  
									  ```
							- `battery_temp`
							  collapsed:: true
								- Code
									- ```python
									  class A:
									      def __init__(self, device):
									          self.__device = device
									  
									      @property
									      def battery_temperature(self):
									          temp = float(int(self.__device.shell('dumpsys battery get temp')) / 10)
									          return temp
									  ```
								- Test
									- ```python
									  def test_battery_temperature_returns_correct_value(mocker):
									      # Create a mock device
									      mock_device = mocker.Mock()
									      
									      # Mock the `shell` method to return a realistic adb value, e.g., "330"
									      mock_device.shell.return_value = "330"
									  
									      # Pass mock device into our class
									      obj = A(mock_device)
									  
									      # Access the property under test
									      result = obj.battery_temperature
									  
									      # Verify correct behavior
									      assert result == 33.0  # 330 / 10 = 33.0
									      mock_device.shell.assert_called_once_with('dumpsys battery get temp')
									  ```
							- `monitor_battery_temp`
							  collapsed:: true
								- Code
									- ```python
									  class DeviceManager:
									      def __init__(self):
									          self.__adb_client = ADBClient("test")
									          self.__track_devices_connection = None
									  
									      def __connect(self):
									          self.__track_devices_connection = self.__adb_client.create_connection()
									  
									      def __track_devices(self):
									          device_notifications = self.__track_devices_connection.receive()
									  
									      def monitor_battery_temperatures(self, maxtemp):
									        self.__traack_devices()
									        devices = self.devices_by_serial.values()
									        try:
									          for device in devices:
									        	  self.__manage_device_health(device, maxtemp)
									        except Exception as e:
									        	print("error")
									  ```
								- Test
									- ```python
									  from unittest.mock import MagicMock
									  from src.device_manager import DeviceManager
									  
									  def test_monitor_battery_temperatures_calls_manage_device_health():
									      # Arrange
									      manager = DeviceManager()
									      
									      # Fake devices
									      device1 = MagicMock()
									      device2 = MagicMock()
									      manager.devices_by_serial = {
									          "123": device1,
									          "456": device2
									      }
									  
									      # Patch private methods so we don't execute real logic
									      manager._DeviceManager__track_devices = MagicMock()
									      manager._DeviceManager__manage_device_health = MagicMock()
									  
									      maxtemp = 50
									  
									      # Act
									      manager.monitor_battery_temperatures(maxtemp)
									  
									      # Assert
									      manager._DeviceManager__track_devices.assert_called_once()
									      
									      # __manage_device_health should be called once per device with maxtemp
									      manager._DeviceManager__manage_device_health.assert_any_call(device1, maxtemp)
									      manager._DeviceManager__manage_device_health.assert_any_call(device2, maxtemp)
									      assert manager._DeviceManager__manage_device_health.call_count == 2
									  
									  ```
							- `main.py`
							  collapsed:: true
								- Code
									- ```python
									  def parse_args():
									    parser = argparse.ArgumentParser(description="Gather max temp")
									    parser.add_argument("MAX_TEMP_SPECIFIED", nargs="*", help="Float representation of celsius temperature")
									    args = parser.parse_args()
									    MAX_TEMP_CELSIUS = 40.0
									    if len(args.MAX_TEMP_SPECIFIED) == 1:
									      try:
									        MAX_TEMP_CELSIUS = float(args.MAX_TEMP_SPECIFIED[0])
									      except Exception:
									        pass
									    print(f"Maximum temperature in celsius is: {MAX_TEMP_CELSIUS}")
									    return MAX_TEMP_CELSIUS
									  
									  def connect_adb(device_manager):
									    while True:
									      try: 
									        device_manager.connect()
									        break
									      except Exception:
									        time.sleep(5)
									  
									  def main() -> None:
									    MAX_TEMP_CELSIUS = parse_args()
									    device_manager = DeviceManager()
									    connect_adb(device_manager)
									    while True:
									      device_maanger.monitor_battery_temperatures(MAX_TEMP_CELSIUS)
									      time.sleep(10)
									      
									  if __name__ == "__main__":
									    main()
									  ```
								- Test
									- `parse_args()`
										- ```python
										  import pytest
										  from src.your_module import parse_args
										  
										  import sys
										  
										  def test_parse_args_default(monkeypatch):
										      # No arguments → default
										      monkeypatch.setattr(sys, "argv", ["script_name"])
										      assert parse_args() == 40.0
										  
										  def test_parse_args_valid(monkeypatch):
										      monkeypatch.setattr(sys, "argv", ["script_name", "55"])
										      assert parse_args() == 55.0
										  
										  def test_parse_args_invalid(monkeypatch):
										      monkeypatch.setattr(sys, "argv", ["script_name", "not_a_number"])
										      assert parse_args() == 40.0
										  ```
									- `connect_adb`
										- ```python
										  from unittest.mock import MagicMock
										  import time
										  import pytest
										  from src.your_module import connect_adb
										  
										  def test_connect_adb_success(monkeypatch):
										      mock_dm = MagicMock()
										      # Connect succeeds immediately
										      mock_dm.connect.return_value = None
										  
										      # Patch time.sleep to avoid real delay
										      monkeypatch.setattr(time, "sleep", lambda x: None)
										  
										      connect_adb(mock_dm)
										  
										      mock_dm.connect.assert_called_once()
										  ```
									- `main`
										- ```python
										  from unittest.mock import MagicMock, patch
										  from src.your_module import main
										  
										  def test_main(monkeypatch):
										      # Mock parse_args to return 50
										      monkeypatch.setattr("src.your_module.parse_args", lambda: 50)
										  
										      # Patch DeviceManager to return a mock
										      mock_dm = MagicMock()
										      monkeypatch.setattr("src.your_module.DeviceManager", lambda: mock_dm)
										  
										      # Patch time.sleep to avoid delays
										      monkeypatch.setattr("src.your_module.time", MagicMock())
										      
										      # Patch monitor_battery_temperatures to stop after one call
										      mock_dm.monitor_battery_temperatures = MagicMock(side_effect=KeyboardInterrupt)
										      
										      with pytest.raises(KeyboardInterrupt):
										          main()
										  
										      # Ensure the mocked methods were called
										      mock_dm.connect.assert_called_once()
										      mock_dm.monitor_battery_temperatures.assert_called_once_with(50)
										  ```
				- Flags
					- `-s` / `--capture=no`
					  Prevent pytest from suppressing print statements
				- Examples
				  collapsed:: true
					- ((68dbece7-5497-4678-8dac-ec557e29d8e9)) : ((68f0f9d4-6d30-4154-8007-89a2918c860e))
		- _Frameworks_
			- Django
			  id:: 646349e5-a416-452a-a03c-8bbf9eb817d7
			  collapsed:: true
				- django is a framework to make web applications, you could use it to make a CMS, but you can also use it to make whatever you want
				- and example of a django cms is wagtail , heres a link http://wagtail.io/
			- ((646349df-3dfb-4073-baba-acbe4bb9506c))
			- ### GUI frameworks
			  collapsed:: true
				- [pyimgui](https://github.com/pyimgui/pyimgui)
				  id:: 68e50d96-04bf-4a99-900a-cd9d11491132
				  collapsed:: true
				  AKA Cython-based Python bindings for ((68e514d8-b525-45df-90ed-e42d1ebfc5ea))
					- [Contents — pyimgui 2.0.0 documentation](https://pyimgui.readthedocs.io/)
					- Python bindings for the amazing ((68e514d8-b525-45df-90ed-e42d1ebfc5ea)) C++ library - a Bloat-free Immediate Mode Graphical User Interface.
					- ImGui redraws the entire screen multiple times per second, so it's mainly used by game developers (where constant full redrawing per frame is common already)
					- ### Built on
						- [Dear ImGui](https://github.com/ocornut/imgui)
						  id:: 68e514d8-b525-45df-90ed-e42d1ebfc5ea
						  collapsed:: true
						  Bloat-free Graphical User interface for C++ with minimal dependencies
							- Pros/Cons
								- meant for content creation tools and visualization / debug / internal tools (as opposed to UI for the average end-user)
									- it's very inflexible as far as customization, theming and animation goes. If you don't like how it looks and behaves, tough luck.
							- [Gallery](https://github.com/ocornut/imgui/issues/6478)
							- ### Ecosystem
								- https://github.com/ImGuiNET/ImGui.NET
								- ((68e50d96-04bf-4a99-900a-cd9d11491132))
							- [Learning Resources]
								- [Immediate-Mode Graphical User Interfaces - 2005](https://www.youtube.com/watch?v=Z1qyvQsjK5Y)
								  collapsed:: true
									- Immediate mode as opposed to retained mode
										- In short, retained mode means that there is no general GUI definition for your application but only direct calls that create new windows and widgets or query their state whenever they are needed and on every frame that is rendered.
										- Actual pipeline of drawing commands is constructed as you go and executed only when you need it. Defining whole GUI on every frame may seem counterintuitive and inefficient. Anyway, such approach is very flexible and allows you to iterate your UI designs very fast.
									- Retained mode
										- Init: Multiple Create calls to make a bunch of widgets, CSS etc
										- Update: ? we don't care about how it does things
										- Callbacks/interactivity: CRUD
										- Pros/Cons
											- Pros
											- Cons
												- Spreads UI elements over many different files
									- Immediate mode
										- Loops and If statements to present UI elements
									- Casey Muratori's immediate mode implementation
										- Example structure
											- ```
											  UI Context
											  ==========
											  ui_id 	Hot,
											  ui_id	Active,
											  
											  ----
											  struct ui_id
											  {
											  	int Owner,
											      int Item,
											      int Index
											  }
											  ```
												- UI Context
													- Core structure is the UI Context - this tracks the state
													- In retained mode GUIs they tend to hold the state of UI elements which haven't been interacted with yet e.g. text fields
														- Immediate mode prefers to hold extremely little state - only when something has been interacted with then is state added
													- Hot = prepares to be interacted with e.g. it highlights a UI element on mouseover
													- Active = you've interacted with it
					- ## Documentation
						- Boilerplate skeleton
						  collapsed:: true
							- [Basic GUI drawing loop (official docs)](https://pyimgui.readthedocs.io/en/latest/guide/first-steps.html#basic-gui-drawing-loop)
								- ```python
								  import imgui
								  
								  # initilize imgui context (see documentation)
								  imgui.create_context()
								  imgui.get_io().display_size = 100, 100
								  imgui.get_io().fonts.get_tex_data_as_rgba32()
								  
								  # start new frame context
								  imgui.new_frame()
								  
								  # open new window context
								  imgui.begin("Your first window!", True)
								  
								  # draw text label inside of current window
								  imgui.text("Hello world!")
								  
								  # close current window context
								  imgui.end()
								  
								  # pass all drawing comands to the rendering pipeline
								  # and close frame context
								  imgui.render()
								  imgui.end_frame()
								  ```
							- ((68e63f2a-971f-4967-a8d2-856e2fcdfdf7)) : ((68e63f2d-43cb-41d7-aea9-f499e334ce50))
					- ### Ecosystem
						- [GitHub - tpecholt/imrad: ImRAD is a GUI builder for the ImGui library](https://github.com/tpecholt/imrad)
					- Alternatives
						- Godot
					- [Learning Resources]
						- [Pythonizing Imgui feat. Cython and contributing to open source](https://www.youtube.com/watch?v=wh_W-veFpKU)
						  id:: 68e63f2a-971f-4967-a8d2-856e2fcdfdf7
						  collapsed:: true
							- Boilerplate skeleton
							  id:: 68e63f2d-43cb-41d7-aea9-f499e334ce50
								- ```python
								  def main():
								    imgui.create_context() # initialise the library
								    window = impl_glfw_init() # ask OS for a window using glfw
								    
								    impl = GlfwRenderer(window) # tell imgui to render to that window
								    
								    io = imgui.get_io()
								    jb = io.fonts.add_font_from_file_ttf(path_to_font, 30) # pick font
								    impl.refresh_font_texture()
								    
								    # render loop
								    while not glfw.window_should_close(window): 
								      render_frame(impl, window, jb)
								      
								    impl.shutdown()
								    glfw.terminate()
								    
								  def render_frame(impl, window, font):
								    # process any mouse inputs and start a new frame
								    glfw.poll_events()
								    impl.process_inputs()
								    imgui.new_frame()
								    
								    # clear the window buffer
								    gl.glClearColor(0.1, 0.1, 0.1, 1)
								    gl.glClear(gl.GL_COLOR_BUFFET_BIT)
								    
								    # imgui commands which define the GUI
								    imgui.push_font(font)
								    frame_commands()
								    imgui.pop_font()
								    
								    # render the GUI
								    imgui.render()
								    impl.render(imgui.get_draw_data())
								    glfw.swap_buffers(window)
								  
								  def frame_commands():
								    pass
								    
								  if __name__ == "__main__"
								    main()
								  ```
							- `def frame_commands()`
							  Contains the logic for defining the UI
								- Window inside app
									- ```python
									  def frame_commands():
									    imgui.begin("A window!")
									    imgui.text("Hello, world!")
									    imgui.end()
									  ```
								- Main menu bar
									- ```python
									  def frame_commands():
									    	# have the exit menu item actually quit the app
									   	io = imgui.get_io()
									      if io.key_ctrl and io.keys_down[glfw.KEY_Q]:
									        sys.exit(0)
									        
									    	if imgui.begin_main_menu_bar():
									        # if menu bar is displayed, make a file menu
									        if imgui.begin_menu("File"):
									          clicked, selected = imgui.menu_item("Quit", "Ctrl+Q")
									          if clicked:
									            sys.exit(0)
									          imgui.end_menu()
									        imgui.end_main_menu_bar()
									  ```
					- Related: [GitHub - hoffstadt/DearPyGui: Dear PyGui: A fast and powerful Graphical User Interface Toolkit for Python with minimal dependencies](https://github.com/hoffstadt/DearPyGui)
				- [reactpy: It's React, but in Python](https://github.com/reactive-python/reactpy)
				- [tkinter](https://docs.python.org/3/library/tkinter.html)
				- https://github.com/hoffstadt/DearPyGui
				- [Qt for Python](https://doc.qt.io/qtforpython-6/)
				  AKA PySide
				- [PyQT](http://www.riverbankcomputing.com/software/pyqt/)
				  by [Riverbank Computing](https://www.riverbankcomputing.com)
				- [NiceGUI](https://nicegui.io/)
				- [Streamlit](https://streamlit.io/)
		- Libraries
			- ((65cc910a-c62b-4904-a414-2f691223b95f))
			- FastAPI
			  collapsed:: true
				- as an alternative to node-swagger, good way to learn more Python
			- [Paramiko](https://pypi.org/project/paramiko/) module is used for SSH
		- Tooling
			- [uv](https://github.com/astral-sh/uv)
			  id:: 685fd5ae-ab52-4377-924e-b2d0bfb74241
			  collapsed:: true
			  Package and project manager, written in Rust | A single tool to replace `pip`, `pip-tools`, `pipx`, `poetry`, `pyenv`, `twine`, `virtualenv`, etc
				- Installation
					- `pipx install uv`
					  [[2025-11-25 Tuesday]] Current
					- `brew install uv`
				- `uv venv .venv` is equivalent to ((67a8e143-e71f-446e-8c6a-46c4a1310084))
				  id:: 686afbd1-9ccd-4ef0-8336-98cbc39eade3
				- `source .venv/bin/activate`
				- `uv pip install -r requirements-dev.txt`
				- `uv pip install ipykernel`
				- Managing versions
					- Requesting a version
						- `uv venv --python 3.11.6 .venv`
						  When creating a virtual environment
					- Example
						- `uv python list`
						- `uv python install 3.12`
				- [Reference](https://docs.astral.sh/uv/reference/cli/)
			- [ruff](https://docs.astral.sh/ruff/)
			  id:: 685fd5e7-fedc-48f7-b6c0-3a9512acad9f
			  collapsed:: true
			  Python linter and code formatter, written in Rust | Replaces Flake8, isort, and Black
				- [ruff](https://github.com/astral-sh/ruff)
				- Install it in a virtual environment (or globally)
				- `ruff check` = check all files in working directory
				- `ruff check --fix` = check and fix all files in working directory
				- `ruff format` = format all files in working directory
			- Static type checkers
			  collapsed:: true
				- Similar concept to ((629ccb26-1eab-4686-a7b8-f9433a871440))
				- What alternatives can I consider? There are four Python static type checkers that can be considered: mypy and Pyright have been released to the community for a while and have well established user bases. Pyrefly, ty were announced recently at PyCon US 2025 and are in active development stage in the current time of August 2025 when this was written.
				- mypy - https://github.com/python/mypy
				- Pyright - https://github.com/microsoft/pyright
				- Pyrefly - https://github.com/facebook/pyrefly
				- [ty](https://docs.astral.sh/ty/)
				  id:: 1a74c88a-a1fc-48b0-8fb2-06bbcfb8acda
				  Python type checker, written in Rust
					- [ty](https://github.com/astral-sh/ty)
					- Related: ((69188f0b-8d7e-4f00-9379-4b775481a3bf))
				- Abandoned
					- [GitHub - google/pytype: A static type analyzer for Python code](https://github.com/google/pytype)
			- [PyInstaller](https://pyinstaller.org)
			  collapsed:: true
			  For bundling Python scripts into single executable binaries mainly
				- Example
					- ```bash
					  pyinstaller -F dir/device_monitor.py --distpath dir/dist --specpath dir --workpath dir/build --name OUTPUT1
					  ```
					- packages the Python script `device_monitor.py` as a single-file executable using PyInstaller, and specifies custom output locations and naming. Here’s what each option means:
					- PyInstaller analyzes `dir/device_monitor.py`, finds its imports, and bundles everything needed to run it
					- ### Explanation of Each Option
						- **`-F` or `--onefile`**
						  Tells PyInstaller to bundle everything (your script, Python interpreter, dependencies) into a single executable file, instead of a folder with many files.[](https://pyinstaller.org/en/v4.2/usage.html)
							- **`dir/device_monitor.py`**
							  The path to your Python script to be packaged.
							- Note: change this to `main.py` or your equivalent entrypoint script if you have separated your module into multiple files.
						- **`--distpath dir/dist`**
						  Sets the output directory for the final executable (the default is `./dist`, but here it is changed to `dir/dist`).[](https://pyinstaller.org/en/stable/man/pyinstaller.html)
						- **`--specpath dir`**
						  Saves the `.spec` file—a configuration file PyInstaller generates describing how to build your project—inside `dir` instead of the current working directory.[](https://pyinstaller.org/en/v4.2/usage.html)
						- **`--workpath dir/build`**
						  Puts all intermediate files and logs created during the build inside `dir/build` (default is `./build`).[](https://pyinstaller.org/en/stable/man/pyinstaller.html)
						- **`--name OUTPUT1`**
						  The output executable file (and spec file) will be named `OUTPUT1` instead of using the script name.
		- Entities
			- Astral
			  id:: 69188f0b-8d7e-4f00-9379-4b775481a3bf
			  collapsed:: true
			  Rust-based tooling
				- Creators of
					- ((685fd5ae-ab52-4377-924e-b2d0bfb74241))
					- ((685fd5e7-fedc-48f7-b6c0-3a9512acad9f))
					- ((1a74c88a-a1fc-48b0-8fb2-06bbcfb8acda))
					- [PYX](https://astral.sh/pyx)
					  collapsed:: true
					  Python-native package registry, written in Rust
						- PYX is not a replacement for PyPI but rather a private package registry and a frontend or middleware layer designed to enhance the package installation experience, particularly when used with the uv tool. PYX can be used to host internal or private packages within an organization, providing a curated view of public sources like PyPI for compliance or security reasons. It aims to solve specific challenges, such as the difficulty in installing complex packages like PyTorch, CUDA, or libraries that build against them (e.g., FlashAttention, DeepSpeed), by offering faster install speeds, better control over builds, and GPU-aware installations. PYX is described as a paid service with potential future free tiers, designed to work hand-in-glove with uv to provide a more optimized, secure, and efficient package management workflow.
		- Related: ((63e2667d-bffb-447c-9442-5802f293903d))
	- [Learning Resources]
	  collapsed:: true
		- ((e55a0ae7-6227-46f4-8ca2-fdb031227292))
			- {{embed ((e55a0ae7-6227-46f4-8ca2-fdb031227292))}}
		- BAE recommendations
			- Via the Connect Home, click Quick links, and find and click spark enterprise and learning platform, login with SSO to access LinkedIn Learning.
			- FreeCodecamp.org - python (8hours) may have some useful clips to refresh understanding of python. [Python Tutorial for Beginners (with mini-projects) - YouTube](https://www.youtube.com/watch?v=qwAFL1597eM)
			- Python: Importing Data course on Pluralsight may be useful - [https://app.pluralsight.com/paths/skill/python-importing-data](https://app.pluralsight.com/paths/skill/python-importing-data) It covers txt, csv, and JSON (part one - working with files in python - may be a little irrelevant)
			- Python Pandas: [Viewing and inspecting data with pandas (linkedin.com)](https://www.linkedin.com/learning/using-python-with-excel-22676328/viewing-and-inspecting-data-with-pandas?dApp=76959373&leis=LAA&resume=false&u=102489394) - useful for importing .xlsx, .csv , .json.
		- [djangobook tutorials](http://www.djangobook.com/en/2.0/index.html)
		- [djangodocs tutorials](https://docs.djangoproject.com/en/1.5/intro/tutorial01/)
		- [GitHub - TheAlgorithms/Python: All Algorithms implemented in Python](https://github.com/TheAlgorithms/Python)
		-
	- Related: ((645562eb-9ee1-4bcb-9d4a-c5fd9afc68ed))