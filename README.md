# DEEP TALK

Guide exploitation :

	Logiciel requis :
		- anaconda
		- tesseract OCR (Imperativment dans 'C:\Tesseract-OCR\tesseract')
	Etapes :
		- creer un environement virtuel en se basant sur le fichier spec-file.txt fourni dans /location/
			-> conda create --name myenv --file spec-file.txt
		- activer cet environement
			-> activate myenv
		- installes les packages (Verifier chemin /location/requirements.txt)
			-> pip install -r requirements.txt
				Si erreur avec transformers executer commande :
					-> git clone https://github.com/huggingface/transformers
					-> cd transformers
					-> pip install .
		- demarer le serveur
			-> executer la commande flask run (Serveur flask tourne sur le port 5000)
		- demarrer le client web 
			-> commande "npm start" dans le dossier /client-web (Clietn web tourne sur le port 3000)

Problemes eventuels :

			Problem :
			File "c:\users\dell\desktop\tpt\v4\deeptalk\client-web\api\venv\lib\site-packages\torch\__init__.py", line 81, in <module>
			from torch._C import *
			ImportError: DLL load failed: La procédure spécifiée est introuvable.
			Solution:

			Download win-64/intel-openmp-2018.0.0-8.tar.bz2 from https://anaconda.org/anaconda/intel-openmp/files

			Extract it and put the dll files in Library\bin into
			C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v9.0\bin

			Make sure your cuda directory is added to your %PATH% environment variable
			
			
			Problem :
			File "c:\users\dell\desktop\tpt\v4\deeptalk\client-web\api\venv\lib\site-packages\google\protobuf\descriptor.py", line 47, in <module>
			from google.protobuf.pyext import _message
			ImportError: DLL load failed: La procédure spécifiée est introuvable.
			Solution:
			pip install protobuf==3.6.0
			
			1export  virtual environement sur conda 
			2activer le nouveau environement
			3trouver facon a externaliser lenvironnement (possibilité: fichier yml et l'importer sur la machine)
			
			
			Problem : 
				Appel Api flask erreur proxy react and CORS limitations
					ajouter ligne : proxy:	"http://localhost:5000" sur le package.json