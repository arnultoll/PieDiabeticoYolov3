ENTRENAMIENTO DE YOLOV3 



Este modelo esta realizado con TensorFlow js, ademas de anaconda y Python 2.1.5 permite detectar con un modelo entrenado el pie diabetico por medio de fotografia o video
a continuación les presentraré imágenes del mismp.

test1_catface.jpg
test2_catface.jpg
test3_catface.jpg




ADJUNTO ENLACE CON TODOS LOS ARCHIVOS COMPLETOS: https://drive.google.com/open?id=19du_34yeIGT2M-jVSvjnJs4N8zGoEIuF
### Pipeline Overview

PARA DESARROLLAR ESTE MODELE TIENE DIFERENTES PASOS Y HERRAMIENTAS

 1. [Image Annotation](/1_Image_Annotation/)
	 - Instalar  Microsoft's Visual Object Tagging Tool (VoTT)
	 - anotar las imagenes
 2. [Training](/2_Training/)
 	- Descargar pre-trained weights
 	- entrenar su modelo YOLO model con las anotaciones de las imagenes 
 3. [Inference](/3_Inference/)
 	- Detect objects permite detectar cada uno de las imagenes y videos

## estructura de repositorio
+ [`1_Image_Annotation`](/1_Image_Annotation/)
+ [`2_Training`](/2_Training/)
+ [`3_Inference`](/3_Inference/)
+ [`Data`](/Data/)
+ [`Utils`](/Utils/)

## para inicializar 

### Requisitos
The only hard requirement is a running version of python 3.3 or newer. To install the latest python 3.x version go to 
- [python.org/downloads](https://www.python.org/downloads/) 

and follow the installation instructions. Note that this repo has only been tested with python 3.6 and thus it is recommened to use `python3.6`.

To speed up training, it is recommended to use a **GPU with CUDA** support. For example on [AWS](/2_Training/AWS/) you can use a `p2.xlarge` instance (Tesla K80 GPU with 12GB memory). Inference is very fast even on a CPU with approximately ~2 images per second. 


### Instalación

#### 1a Setting up Virtual Environment [Linux or Mac]

Clone this repo with:
```
git clone https://github.com/AntonMu/TrainYourOwnYOLO
cd TrainYourOwnYOLO/
```
Crear un entorno Virtual **(Linux/Mac)** Environment (requires [venv](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/) which is included in the standard library of Python 3.3 or newer):
```
python3 -m venv env
source env/bin/activate
```

#### 1b correr el entorno en windows [Windows]
Use the [Github Desktop GUI](https://desktop.github.com/) to clone this repo to your local machine. Navigate to the `TrainYourOwnYOLO` project folder and open a power shell window by pressing **Shift + Right Click** and selecting `Open PowerShell window here` in the drop-down menu.

Create Virtual **(Windows)** Environment (requires [venv](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/) which is included in the standard library of Python 3.3 or newer):

```
py -m venv env
.\env\Scripts\activate
```
![PowerShell](/Utils/Screenshots/PowerShell.png)
Make sure that, from now on, you **run all commands from within your virtual environment**.

#### 2 Instalar lo paquedes dependiendo del sistema operativo [Windows, Mac or Linux]
Install all required packages with:

```
pip install -r requirements.txt
```
If this fails, you may have to upgrade your pip version first with `pip install pip --upgrade`. If your system has working CUDA drivers, it will use your GPU automatically for training and inference.

## inicializar el test (Inference only)
To test the cat face detector on test images located in [`TrainYourOwnYOLO/Data/Source_Images/Test_Images`](/Data/Source_Images/Test_Images) run the `Minimal_Example.py` script in the root folder with:

```
python Minimal_Example.py
```

