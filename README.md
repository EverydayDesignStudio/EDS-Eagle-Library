# EDS-Eagle-Library
_Eagle footprints of electronic components used in EDS projects._

When working on PCB design projects, you will encounter all sorts of components that you might want to include in your design. Some manufacturers make Eagle files available for use; others don't. When you wish to incorporate a part that doesn't have readily available Eagle files available you'll have to create your own Eagle Device from a components' datasheet.

## What is an Eagle Library?

![Library-Device](https://www.autodesk.com/products/eagle/blog/wp-content/uploads/2017/03/2017-03-08_14-58-22-1.png)

In short, when you use a component (called a *Device* in Eagle) it consists of a *symbol* and a *package*. The symbol is the symbolic representation as used in a circuit diagram. The package is the physical shape and layout on the PCB of that component.

To illustrate, below, you see the *symbol* for the MPL3115A2 Altimeter used in Capra. This is an abstraction of the component, showing only its terminals (or 'pins') and their names.

![MPL3115A2 symbol](https://raw.githubusercontent.com/EverydayDesignStudio/guides/master/EagleSymbol1.png)

This is the corresponding package. Note that the actual physical size of the component and the relative configuration of the terminals is reflected in the package.
![MPL3115A2 symbol](https://raw.githubusercontent.com/EverydayDesignStudio/guides/master/EaglePackage1.png)

To further contextualise; this is the *symbolic* circuit diagram of the MPL3115A2 Altimeter as used in Capra:

![Eagle Symbol](https://raw.githubusercontent.com/EverydayDesignStudio/guides/master/EagleSymbol2.png)

Whereas this is the same altimeter shown  as a *package* on the PCB layout (note that the two pull up resistors R4 & R5 are not shown in this image).

![Eagle Package](https://raw.githubusercontent.com/EverydayDesignStudio/guides/master/EaglePackage2.png)

Without changing the circuit diagram, the PCB layout could be changed. For example, there are many other ways the traces could be routed for this circuit. Or, instead of using a 0402 size capacitor for C5, a different size could be chosen [(more about SMD component sizes here)](http://www.resistorguide.com/resistor-sizes-and-packages/). This doesn't change the *circuit* only its *physical design*. Note that some chips are available in several packages. Take for example the MCP3008 Analog-to-Digital Converter (ADC); available in three packages as shown below (screenshot from the [MCP3008 datasheet](http://ww1.microchip.com/downloads/en/DeviceDoc/21295d.pdf)). Depending on what size is desired, and what soldering technology is available; one might choose one form over another. An incomplete description of some standard packages can be found [here](https://www.electronics-notes.com/articles/electronic_components/surface-mount-technology-smd-smt/packages.php)
![MCP3008 Packages](https://raw.githubusercontent.com/EverydayDesignStudio/guides/master/Packages.png)

## How do I proceed?
In order to make collaboration possible, all people who use an Eagle design file must have access to the same Eagle components. That's why it's advisable to use this collaborative Eagle library and push any new components to this repo. It'll save you time because you won't have to create packages from scratch and it will make collaboration easier, as it will allow others in the studio to build on the designs you create.

### Using this Library

1. Locate where Eagle saves your local libraries. On a mac this is `/Users/*username*/Documents/EAGLE/libraries/`. Note down the directory.

2. Open a terminal window and navigate to this directory. Then, clone this repo into it.

3. Next, in Eagle, open the Library Manager (`Library > Open Library Manager`)

4. Click the tab 'Available', then click 'browse'. Locate the cloned repo and add the Library. The `EDS_Eagle_Library` will now appear in the list of available libraries.

5. Click the `EDS_Eagle_Library` in the list, then click the `Use` button. Quit the Library Manager.

6. Now, when designing a Schematic in Eagle, when you issue the `Add` command, you can search 'EDS_Eagle_Library' and find its contents, ready to be used.

### Creating new Components

Although it seems a little overwhelming and convoluted at first, creating your custom devices in Eagle is easy! It also gives you the freedom to do specific things with your components that might typically not be done (like a heatsink under your chip, or a specific marking around a component).

An elaborate guide on how to create custom components in Eagle can be found [here](https://www.autodesk.com/products/eagle/blog/library-basics-part-1-creating-first-package-autodesk-eagle/). When adding components to the library, be sure to push your changes to keep the master branch up to date!

An automated way of creating packages is through Autodesks online tool [Library.io](https://library.io/). This tool also creates 3D models of your components for use in Fusion360.

### Resources

The symbol and the package shown in the examples above were both made based on the [MPL3115A2's datasheet](https://cdn.sparkfun.com/datasheets/Sensors/Pressure/MPL3115A2.pdf). Datasheets can be found on vendors' websites such as:
- [Adafruit](https://www.adafruit.com/)
- [Sparkfun](https://www.sparkfun.com/)
- [Digikey](https://www.digikey.ca/)
- [Mouser](https://www.mouser.ca/)

Furthermore, it is good to know that Adafruit and Sparkfun open-source their products. So whenever you've used a breakout board from either vendor, you can find the schematic and PCB layout on the respective product page to include in your own PCB design project.
