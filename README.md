## Redocking-6pib (English Version) 
redocking 6pib using autodock vina new version in OS Windows 10 (2021)

## Using Vina forcefield
Validation using Re-Docking

## PATH settings
1. Installing Mgl tools 1.5.6 find python.exe in the folder and make the path
2. Installing ADFR Windows version make the path /bin because there is autogrid4
3. Download vina https://github.com/ccsb-scripps/AutoDock-Vina/releases/download/v1.2.3/vina_1.2.3_windows_x86_64.exe and rename vina_1.2.3_windows_x86_64.exe to vina.exe
4. Input vina.exe in your path 

## Separation of ligands and proteins using Biovia Discovery Studio
1. Separate the protein, remove the water and the ligands
2. Separate ligands, remove protein, water


## Protein preparation autodock tools
1. Separate water and ligands first using Biovia Discovery Studio
2. Click File Read Molecules look for protein.pdb
3. Added Hydrogen with Edit-Add Hydrogen-All
4. Edit add gasteiger payload
5. Edit-Hydrogen Merge Non Polar
6. Grid-Macromolecules-Choose
7. save protein.pdbqt

## Ligand preparation autodock tools
1. Click File Read Molecules, look for ligand.pdb
2. Added Hydrogen with Edit-Add Hydrogen-All
3. Edit add gasteiger payload
4. Edit-Hydrogen Merge Non Polar
5. Ligand-Input-choose
6. Select ligand.pdb
7. ligand-Toorsion tree-detect root
8. ligand-output-save as ligand.pdbqt

### Command in terminal to find Grid Box using Autogrid
python.exe prepare_gpf.py -l 6pib_ligand.pdbqt -r 6pib_protein.pdbqt -y
autogrid4 -p 6pib_protein.gpf -l 6pib_protein.glg

## Create the GridBox File
1. Open the file with 6pib_protein.gpf
2. Record npts 41 40 40 as size x, y, z
3. Record gridcenter -0.004 -0.187 0.078 as center x, y, z
4. Create a grid.txt file in it that says:
center_x = -0.004
center_y = -0.187
center_z = 0.078
size_x = 40
size_y = 40
size_z = 40

### For Docking/Redocking Test compound using Vina forcefield write this command in terminal
1. vina --receptor 6pib_protein.pdbqt --ligand 6pib_ligand.pdbqt --config grid.txt --exhaustiveness=8 --out 6pib_ligand_vina_out.pdbqt > results.txt
2. vina_split --input 6pib_ligand_vina_out.pdbqt
## Using Vina forcefield
Validasi dengan menggunakan Re-Docking

## Pengaturan PATH
1. Instalasi Mgl tools 1.5.6 cari python.exe di foldernya dan jadikan path
2. Installasi ADFR Versi windows jadikan path yaitu /bin karena ada autogrid4
3. Download vina https://github.com/ccsb-scripps/AutoDock-Vina/releases/download/v1.2.3/vina_1.2.3_windows_x86_64.exe and rename vina_1.2.3_windows_x86_64.exe to vina.exe
4. Input vina.exe in your path 

## Pemisahan ligand dan protein menggunakan Biovia Discovery Studio
1. Pisahkan Protein, buang air dan liganndya
2. Pisahkan ligand, buang protein, air 

## Preparasi Protein autodock tools
1. Dipisahkan air dan ligannya terlebih dahulu menggunakan Biovia Discovery Studio
2. Klik File Read Molecules cari protein.pdb
3. Dilakukan penambahan Hidrogen dengan Edit-Add Hidrogen-All
4. Edit tambahkan muatan gasteiger
5. Edit-Hidrogen Merge Non Polar
6. Grid-Macromolecules-Choose
7. save protein.pdbqt

## Preparasi Ligand autodock tools
1. Klik File Read Molecules cari ligand.pdb
2. Dilakukan penambahan Hidrogen dengan Edit-Add Hidrogen-All
3. Edit tambahkan muatan gasteiger
4. Edit-Hidrogen Merge Non Polar
5. Ligand-Input-choose
6. Pilih ligand.pdb
7. ligand-Toorsion tree-detect root
8. ligand-output-save as ligand.pdbqt

### Perintah di terminal untuk mengetahui Grid Box menggunakan Autogrid
python.exe prepare_gpf.py -l 6pib_ligand.pdbqt -r 6pib_protein.pdbqt -y
autogrid4 -p 6pib_protein.gpf -l 6pib_protein.glg

## Buat File GridBoxnya
1. Buka file dengan 6pib_protein.gpf
2. Catat npts 41 40 40 sebagai size x, y, z
3. Catat gridcenter -0.004 -0.187 0.078 sebagai center x, y, z
4. Buat file grid.txt didalamnya tertulis :
center_x = -0.004
center_y = -0.187
center_z = 0.078
size_x = 40
size_y = 40
size_z = 40

### For Docking/Redocking Test compound using Vina forcefield write this command in terminal
1. vina --receptor 6pib_protein.pdbqt --ligand 6pib_ligand.pdbqt --config grid.txt --exhaustiveness=8 --out 6pib_ligand_vina_out.pdbqt > hasil.txt
2. vina_split --input 6pib_ligand_vina_out.pdbqt
