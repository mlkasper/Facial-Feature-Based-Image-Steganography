# Facial Feature Based Image Steganography 

This is a project for NDSU's CSCI 404. The project main purpose to take an image, detect facial features, and then encode a secret message into that image. It encodes the message using the method of changing the least significant bit of the pixels to keep the message hidden and the image almost unaltered. 

Installation
------------

On Linux:

1. Run ``` sudo apt-get install cmake ```

2. Clone this repository to your local machine.

3. Run ```sudo apt-get install gfortran libopenblas-dev liblapack-dev && sudo apt-get install libjpeg-dev zlib1g-dev && sudo apt-get install imagemagick```
to install the required packages.

4. Run ``` pip3 install -r requirements.txt ``` from the projects root directory.

On Windows:

2. Clone this repository to your local machine.

2. Run ``` python -m pip install -r requirements.txt ``` from the project's root directory.

On MacOS: 

1. Open Terminal and run ```pip3 install cmake```

2. Clone this repository to your local machine.

3. Run ```pip3 install -r requirements.txt``` from the projects root directory.

Installation Issues
------------

On Linux:
If you get an error installing ```scipy-1.6.2``` 
1. Run ```sudo apt-get install gfortran libopenblas-dev liblapack-dev```
2. Try to run ``` pip3 install -r requirements.txt ``` again.

If you get an error installing ```Pillow-6.1.0``` 
1. Run ```sudo apt-get install libjpeg-dev zlib1g-dev```
2. Try to run ``` pip3 install -r requirements.txt ``` again.

On Windows: 
If you get an error installing ```requirements.txt```
1. Download Visual Studio Build Tools [here](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=15#)
2. Run ```python -m pip install -r requirements.txt```

If you continue to get errors:
1. Download all dependancies manually through a new terminal window. 
2. Ex. ```pip install Pillow```

On MacOS: 
If you don't have pip3 installed
1. Open Terminal and run ```curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py```
2. Run ```python3 get-pip.py```

If you get an error installing ```requirements.txt``` 
1. Download xCode off the MacOS App Store or click [here](https://apps.apple.com/us/app/xcode/id497799835?mt=12) to download. 
2. Run ```pip3 install -r requirements.txt``` again.

If you continue to have errors
1. Install all dependencies through a new terminal windows. 
2. Ex. ```pip3 install Pillow```

Usage
-----

On MacOS and Linux:
```python3 facial_recog/steg.py```

On Windows: 
```python facial_recog/steg.py```

Compatibility
-----------
JPEG and other lossy compression formats are not supported. 

Known Issues
------------
1. If an image has a message encoded to it, and you encode a message with two facial features it will not decode properly the first time. It needs to be encoded again for it to decode properly. 
    - This could be fixed in two ways.
        - When encoding a picture it could copy an original to that file location so it's a clean photo everytime you encode. 
        - Create a function to clear the image of any messages saved. 
            - Again if you encode twice this will fix the problem anyway. 
2. Some messages lengths may crash due to being too big for the facial feature selected. 
    - The program will check the maximum length of a message by using the full face. This could be improved by finding out what facial feature is already used and calculate the length of the new feature and adding the two byte sizes together.
