## Output file Paths
### Script Language

All the __Output file Paths__ is written in Python language.
### What the box does ?

This part box of the Workflow nammed  __Output file Paths__ is for (as its name suggests) the input XML verifiying and reading. We must therefore retrieve the values that interest us.

We must check the structure of the XML input file by running a specific XSD file.

In the case of this Workflow (*Canonical Intake*), we need to retrieve the values for the number and the name of the configurations, the number of treatments, the frequencies as well as the name of the post-processing process (his list is not exhaustive).

*__Output file Paths__ box is preceded by the __Create Folders__ box which consist in the repository creation (contained in the *namesOfFolder* agregate) and followed by the __Get Mesh & Models Frequencies__ box which consist in the recovery of the linear frequencies and the mesh frequencies (this is just, in fact linear frequencies to which we applied a step).*

![Initialization components](https://user-images.githubusercontent.com/45098441/72733881-11081980-3b99-11ea-8d64-d0a6db042717.jpeg)
----------------------------


### Which files to import ?

To execute the script __Output file Paths__ correctly, we need to import Python libraries.
The table below lists all the imports to be made :

| Import name | Import location |
| ------ | ------ |
| XMLAnanax2dCanonicalIntake | `/python/api/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |
| Logger | `/python/workflows/common` |
| CommonFunctions | `/python/workflows/common` |
| PiffPostprocessing | `/python/workflows/ductnoise/common/postprocessing` |
| PiffPostprocessingAnanax2dCanonicalIntake | `/python/workflows/ductnoise/fannoise/ananax/ananax2d_canonical_intake` |

### What about variables ?

The table below lists all the variables to be created in Isight and their role :

__Inputs variables to be given to Isight or received from previous boxes :__ 

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| pathOfPythonSrcFolder | Python source folder path wich contain all librairies | STRING | X |- |
| pathOfJobFolder | Job folder path to copy all results | STRING | X | - |
| nameOfLogsFolder | Name of result logs folder | STRING | X | - |
| verbosity | Verbosity schema value | STRING | X | - |


__Outputs variables to send to following boxes :__

| Variable Name | Variable description | Type | Input | Output |
| ------ | :------------: | :------: | :------: |  :------: |
| linearFrequencies | All linear frequencies from the XML file | ARRAY DOUBLE | - | X |
| numberOfConfigurations | Number of Configurations from the XML file | INT | - | X |
| pathOfLogsFolder | Logs folder rsults path | STRING | - | X |
| pathsOfUserFieldmeshes | User Field Meshes path | STRING | - | X |
| maxNodeMemory | Max node memory available | INT | - | X |
| numberOfCoresByNode | Number of core in each node memory | INT | - | X |
| maxNumberOfProcesses | Maximum number of processes | INT | - | X |
| memorySecurityCriteria | Security criteria for memory | REAL | - | X |
| namesOfPostprocessingProcesses | Array containing all post processing processes names | ARRAY STRING | - | X |
| areBaseline | True if inputs are Baseline | BOOLEAN | - | X |
