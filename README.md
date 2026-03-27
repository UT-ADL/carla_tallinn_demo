# Tallinn Demo Map for CARLA

A custom CARLA simulator map featuring a Tallinn city environment.

## Installation

1. Download [CARLA 0.9.15](https://tiny.carla.org/carla-0-9-15-linux).

2. Extract the file to a new folder. We will call this extracted folder `<CARLA ROOT>`.

   ```
   tar xzvf CARLA_0.9.15.tar.gz
   ```

3. Download the [tallinn_demo.tar.gz](https://drive.google.com/file/d/1txOROweNe1qoZAvp5ha6EI0daTwoIExB/view?usp=drive_link) map package.

4. Copy `tallinn_demo.tar.gz` inside the `Import` folder under the `<CARLA ROOT>` directory.

5. Run `./ImportAssets.sh` from the `<CARLA ROOT>` directory. This will install the `tallinn_demo` map.

   ```bash
   ./ImportAssets.sh
   ```

6. Delete the `tallinn_demo.tar.gz` file from the `Import` folder.

7. Install CARLA dependencies:

   ```
   pip install -r PythonAPI/examples/requirements.txt
   ```

8. Export the CARLA root directory as an environment variable. Make sure to replace the path with the location where CARLA is extracted.

   ```
   export CARLA_ROOT=$HOME/path/to/carla
   ```

9. Set up the Python path:

   ```
   export PYTHONPATH=$PYTHONPATH:${CARLA_ROOT}/PythonAPI/carla/dist/carla-0.9.15-py3.7-linux-x86_64.egg:${CARLA_ROOT}/PythonAPI/carla/agents:${CARLA_ROOT}/PythonAPI/carla
   ```

   **Note:** For convenience, add both exports to `~/.bashrc` so they are set automatically whenever you open a terminal.

## Running the Tallinn Demo Map with traffic using a custom script

1. Clone [carla_tallinn_demo](https://github.com/UT-ADL/carla_tallinn_demo.git) to a directory of your choice:
   ```
   git clone https://github.com/UT-ADL/carla_tallinn_demo.git
   ```

2. Launch CARLA:

   ```
   $CARLA_ROOT/CarlaUE4.sh
   ```

3. Load Tallinn demo map, generate traffic and start manual control (from `carla_tallinn_demo`):

   ```
   python drive_tallinn.py
   ```
   
## Running the Tallinn Demo Map with default CARLA setup

1. Launch CARLA:

   ```
   $CARLA_ROOT/CarlaUE4.sh
   ```

2. Load Tallinn demo map:

   ```
   $CARLA_ROOT/PythonAPI/util/config.py -m tallinn_demo
   ```

3. Generate traffic:

   ```
   $CARLA_ROOT/PythonAPI/examples/generate_traffic.py
   ```

4. Start manual control:

   ```
   $CARLA_ROOT/PythonAPI/examples/manual_control.py
   ```
   
## Related Projects

- [UT-ADL Lexus Model](https://github.com/UT-ADL/carla_lexus.git) — University of Tartu Lexus vehicle model for CARLA
