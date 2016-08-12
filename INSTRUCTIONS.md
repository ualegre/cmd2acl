Instructions for RC-ASE(Requirements for Context-Aware Systems Engineering)
======
0. Prerequisites
	- Eclipse EMF neon with Git (EGit) plugins correctly installed. The code was created in Eclipse EMF Mars.2 Release 4.5.2
	- Acceleo 
	- A Context Dependency Diagram in Modelio, created with the RC-ASE module and exported to ".uml" and ".xmi" format. 
		* In Modelio 3.5, right click on your project folder and choose Import/Export->Export->Export XMI
		* Select the desired folder for the output and the ".uml" extension
	
1. Clone this repository to your local hard drive.

2. Open an Eclipse Modelling Tools  instance in your preferred workspace (different than the folder where you have downloaded your repository)

3. Click on File->Import->General->Existing Projects into Workspace. Then select the folder where the repository has been cloned.

3. Paste your ".uml" diagram to the folder icase/model/
	 * The files you can already find there are part of an example, if you do not have yet your diagram you can use them, if you already have it, you can get rid of them. 
	 * When you export an RC-ASE Context Dependency Diagram in modelio, you will get two files: <your_project>.uml and rcase.entities.profile.uml), just paste them on icase/model/
	 
4. Generate the metamodel using the rcase.entities.profile.uml file:  
		a) File->New->Other->Eclipse Modelling Framework->EMF Project->(Next)->(Insert name and next)->UML Model->(Next)->(Browse workspace and select rcase.entities.profile.uml)->(Next)->
			(Select rcaseentities as root pacakge and the rest as referenced generator models)->(Finish)
		b) Open the .genmodel file of the EMF project. Right click on 'Rcase.entities' and press generate all. 
		c) Click on Project->Clean->Clean all projects->OK

5. Set up the running configurations:
	* Right click on icase/main/main.mtl -> Run as->Run configurations
	* Project: (Browse) icase
	* Main class: (Browse) Main - icase.main
	* Model: (Browse/Find) /icase/model/<your_project>.uml
	* Target: /icase/output
	* Runner: Acceleo plugin application
	* Click on Run 
	
6. You should be able to see your generated code in icase/output


