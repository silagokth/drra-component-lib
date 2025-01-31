# DRRA Component Library

This repository contains the DRRA component library. The library is a collection of components that can be used to build a DRRA application.

## Compilation and Installation

To compile the library, run the following commands:

```bash
mkdir build
cd build
cmake ..
make
```

The complete library will be compiled in the `build/library` directory. You can copy the folder to wherever you want to use the library.

## Usage

This library should be used by the [Vesyla-Suite](https://github.com/silagokth/vesyla-suite-4) program. To let the program know where the library is located, you need to set the `VESYLA_SUITE_PATH_COMPONENTS` environment variable to the path of the library. For example, if you have copied the library to `/usr/local/lib/drra-component-library`, you can set the environment variable by running the following command:

```bash
export VESYLA_SUITE_PATH_COMPONENTS=/usr/local/lib/drra-component-library
```

## Customization

You can add more custom components to the library by adding them to the `lib` directory. The easiest way to do this is to copy an existing component and modify it to suit your needs. You need to modify the following files:

- `arch.json`: The architecture description file.
- `isa.json`: The instruction set description file.
- `rtl.sv`: The RTL description file. Note that, this is a template file, you should only modify the contents of the module description. If it's a resource component, you should adjust the input and output ports definition based on the size (how many slots) of the resource.
- `timing_model`: The timing behavior of the component. Used by the instruction scheduler.
