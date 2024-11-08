# Robotics I

Here you can find code related to the lecture Robotics I.

## Exercise Sheet 1

### Exercise 3 (Concatenation of Coordinate Transforms)

What does applying a homogeneous transformation matrix yield, if it contains both a (non-identity) rotation and translation? And what is the effect of multiplying from the left vs. from the right? Visualize the solution of exercise 3 and play around with the parameters using this simple python script. It is an all-in-one file written to be easily understandable, and just requires a very few common python packages (numpy and matplotlib).

![Robot pose in the x/y-plane](img/exercise_sheet_1__exercise_3__illustration.png)

### Exercise Sheet 2

#### Exercise 1 (Transformations)

[./exercise_2_1__transformations/](./exercise_2_1__transformations/)

While exercise 1.3 was about applying the transformation, with just the option to try out the effect of performing the calculations differently, this exercise 2.1 is now about systematically investigating
- How a homogeneous transformation matrix is interpreted
- How to convert poses between coordinate systems
- How a transformation applied from the left acts compared to one applied from the right

### Robotics Toolbox Example

[./robotics_toolbox_example/](./robotics_toolbox_example/)

This example shows how to load a Franka Emika "Panda" robot into the simulation of the Robotics Toolbox, and to move it by setting a task space goal for its end effector.

## Installation

### Download the Code

1. Make sure you have git installed on your computer. Then, clone the repository:
   ```shell
   cd /A/folder/on/your/system/to/store/the/code
   git clone https://git.h2t.iar.kit.edu/teaching/code/robotics-i.git
   cd robotics-i
   ```

### Setup a Virtual Environment

1. Decide which management tool you want to install for your virtual environments. Depending on your operating system, you can choose between these options:
   - Windows: use *conda*
   - Linux: use either *conda* or *virtualenv*
   - MacOS: use *conda*

   Perform the installation depending on your decision:

   1. If you decided for *conda*:
      - Follow the [official instructions](https://docs.conda.io/projects/miniconda/en/latest/#quick-command-line-install).
        Depending on which system (Windows, macOS, or Linux) you are working on, you need to follow the different instructions on that page.
        See also troubleshooting sections below.
      - Open a shell or terminal from your system and run the following.
         - Windows: search the program `Anaconda Prompt` and run it. See also the troubleshooting section below.
         - Linux: `Ctrl + Alt + T`
      - Create a virtual environment. In the shell or terminal, run
        ```shell
        conda create -n robotics-i python=3.10
        ```
      - Activate the created virtual environment. In the shell or terminal, run
        ```shell
        conda activate robotics-i
        ```

   1. If you decided for *virtualenv*:
      - Install virtualenv:
         ```shell
         sudo apt install python3-virtualenv
         ```
      - Create a virtual environment ("venv" is the path where it is installed to, and may be changed):
         ```shell
         virtualenv venv
         ```
      - Activate the created virtual environment:
         ```shell
         source venv/bin/activate
         ```

3. Install dependencies:
   ```shell
   pip install -r mi_code_requirements_all.txt
   ```

### Using the Jupyter Notebooks

1. Activate created virtual environment if not already active.
   1. If you are using *conda*:
      - In the shell or terminal, run
         ```shell
         conda activate robotics-i
         ```
   2. If you are using *virtualenv*:
      - In the shell or terminal, run
         ```shell
         source venv/bin/activate
         ```
2. Run jupyter-notebook server
   ```shell
   jupyter notebook
   ```

3. View the notebooks. A web-browser will pop up showing the working directory of the robotics-i code repository.
   If not, then you can copy the link in the shell or terminal and paste it to your web-browser, or press ctrl and click
   the link.
   - The notebook files end with a `.ipynb` extension.
   - Open a notebook in the web interface.
   - You can now explore the notebook by running the cells one by one and editing the code to experiment with the example.



#### About Jupyter Notebook

Most examples are implemented in a [Jupyter Notebook](https://jupyter.org/).
To run them, activate the example's virtual environment and run `jupyter notebook`:

```bash
cd path/to/the/example

jupyter notebook
```

A web-page should automatically be opened it your web browser.
If not, open the URL that is printed by the `jupyter notebook` command
(e.g. `file:///home/user/.local/share/jupyter/runtime/nbserver-22023-open.html`)

The notebook files end with a `.ipynb` extension.
Open a notebook in the web interface.

You can now explore the notebook by
running the cells one by one and editing the code to experiment with the example.


### Troubleshooting

#### Setup conda environment on Windows

Installation:

```shell
cd /some/temporal/folder/on/your/machine
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe -o miniconda.exe
start /wait "" miniconda.exe /S
del miniconda.exe
```

if `start` command does not work. Then you can also open the folder in the file manager program `Explorer` and double click
the downloaded `miniconda.exe` and follow the instructions in the GUI.

After installation, you can search the program `Anaconda Prompt` and run it.

If you want to change the default working directory to the robotics-i code folder, you can follow the instructions below:
- Go to Start and search for `Anaconda Prompt`
- Right click `Anaconda Prompt` and choose `Open File Location`, which will open a folder of shortcuts.
- Right click the `Anaconda Prompt` shortcut
- Choose `Properties` and
- You can now adjust the starting dir in the `Start in` box, replace it with the path to your robotics-i code folder


#### Setup conda environment on Linux

Open a terminal, or `Ctrl+Alt+T`
```shell
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm -rf ~/miniconda3/miniconda.sh
# For bash
~/miniconda3/bin/conda init bash
# For zsh
~/miniconda3/bin/conda init zsh
```

