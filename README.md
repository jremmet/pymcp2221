# pymcp2221
This is a python driver for the Microchip MCP2221/MCP2221A USB 2.0 to I2C/UART protocol converters
([manufacturer's page](https://www.microchip.com/en-us/product/MCP2221A)).

First and foremost, there are python packages for the same chip available [here](https://github.com/nonNoise/PyMCP2221A) and [here](https://github.com/pilotak/python-mcp2221). If you use them and are satisfied, you probably won't find improvements in my package. If you're missing some features however, my code is meant to expose every chip feature described in the datasheet in a systematic manner, for python 3.3+.

##### Implemented features
- Status/Set Parameters (0x10) - ok
- Read Flash Data (0xB0) - ok
- Write Flash Data (0xB1) - ok
- Send Flash Access Password (0xB2) - ok
- I2C Write Data (0x90) - ok
- I2C Write Data Repeated Start (0x92) - ok
- I2C Write Data No Stop (0x94) - ok
- I2C Read Data (0x91/0x40) - ok
- I2C Read Data Repeated Start (0x93/0x40) - ok
- Set GPIO Output Values (0x50) - ok
- Get GPIO Values (0x51) - ok
- Set SRAM Settings (0x60) - ok, except GPIO directions/values through SRAM (duplicate with 0x50)
- Get SRAM Settings (0x61) - ok, except GPIO directions/values through SRAM (duplicate with 0x51)
- Reset Chip (0x70) - ok

Every feature marked *ok* is implemented, but some of them, like I2C, haven't been tested in real conditions.

# Requirements
- [hidapi](https://pypi.org/project/hidapi)

# Setup
From command line, use:

    ```
    python setup.py install
    ```

or for Linux/OSX:

    ```
    sudo python setup.py install
    ```

# Examples
See *examples* folder.

# Tests
The *tests* folder contains unit tests for most of the aspects of this package. To run them, use:

    ```
    python -m unittest
    ```

# API
I may format docs in a neat way at some point. In the meantime you can rely on python docstrings, which are rather complete already.

Two ways to do that:
1) from the command line, use pydoc:
    ```bash
    pydoc mcp2221
    ```
2) from within python:
    ```python
    import mcp2221; help(mcp2221)
    ```
