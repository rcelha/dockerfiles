FROM rcelha/android-sdk

# deps
RUN apt-get update && apt-get install -y xterm;

# MOTOROLA DEVICE
RUN echo SUBSYSTEM=="usb", ATTR{idVendor}=="22b8", MODE="0666", GROUP="plugdev" | tee /etc/udev/rules.d/51-android-usb.rules

# NODE
RUN curl -sL https://deb.nodesource.com/setup_4.x | bash -
RUN apt-get install -y nodejs

# Ract stuff
RUN npm install -g flow-bin react-native-cli
