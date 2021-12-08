Cloudbeaver is based on DBeaver platform, so firstly you need to configure [DBeaver in Eclipse](https://github.com/dbeaver/dbeaver/wiki/Develop-in-Eclipse).  

The rest steps are the same from the Eclipse perspective:
1. Import Cloudbeaver project via import wizard "General->Existing Maven Projects";
2. Update Maven project if some modules failed to build;
3. Import Cloudbeaver launch configuration, which located at "./server/product/web-server/CloudbeaverServer.product.launch".

For some Linux systems, you also need to install the following GTK plugins to build DBeaver successfully:
- org.eclipse.e4.ui.swt.gtk;
- org.eclipse.equinox.launcher.gtk.linux;
- org.eclipse.swt.gtk.linux.
