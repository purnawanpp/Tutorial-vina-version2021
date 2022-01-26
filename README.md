## Redocking-6pib
redocking 6pib using autodock vina new version (2021)

## Using Vina forcefield
Validasi dengan menggunakan Re-Docking

## Pengaturan PATH
1. Instalasi Mgl tools 1.5.6 cari python.exe di foldernya dan jadikan path
2. Installasi ADFR Versi windows jadikan path yaitu /bin karena ada autogrid4

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

### Untuk Docking senyawa Uji Curcumin menggunakan Vina forcefield tuliskan perintah ini diterminal
1. vina --receptor 6pib_protein.pdbqt --ligand 6pib_ligand.pdbqt --config grid.txt --exhaustiveness=8 --out 6pib_ligand_vina_out.pdbqt > hasil.txt
2. vina_split --input 6pib_ligand_vina_out.pdbqt
