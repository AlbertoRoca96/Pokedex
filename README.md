# Pokedex
README
CREDIT:
This project began as semester project directed by Dr. Rai, a professor at Longwood University, Samuel Hillman and I worked on this from Febuary to May of 2025. This project was then further extended to what it is now, directed by Dr. Marmorstein, another professor of computer science at Longwood University. 
This folder must contain four data files and the live-capture script.

predict\_live.py
The script that captures a fixed rectangle of the screen, converts the pixels the same way they were prepared during training, runs the trained ResNet-50 and shows the Pokémon name and confidence on the screen. When you press Space or Enter it looks up the matching flavour text and speaks it.

pokedex\_resnet50.h5
The fine-tuned ResNet-50 weights that the script loads to make its predictions.

class\_indices.json
A dictionary written at training time that maps each numeric class index back to the readable Pokémon name. The script needs it to turn the model’s top-1 index into the label that is painted on the frame and used to find flavour text.

flavor\_text.json
A local cache of English Pokédex flavour-text lines created by crawl\_flavortext.py. When you press the trigger key the script pulls the first line for the current Pokémon from this file and hands it to the text-to-speech engine.

fulldex (directory)
All the training images grouped one sub-folder per Pokémon. It is not required to run the live program but is useful if you want to retrain or inspect the dataset.

To run predict\_live.py the following Python packages have to be installed in the active environment:

opencv-python
numpy
mss
tensorflow or tensorflow-cpu
pyttsx3
pygetwindow (only needed if you plan to set WINDOW\_TITLE so the script can auto-centre the capture rectangle)

After those packages are present and the five items above are in the same directory you can start the live Pokédex with:

python predict\_live.py
