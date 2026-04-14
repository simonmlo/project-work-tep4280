Denne oppskriften gjelder hver gang man skal gjøre simulering på ny mesh for å tilslutt analysere GCI. Bruker fine mesh som eksempel. 

Xtracoarse=940
Coarse=2300
Medium=5478
Fine=13248
Xtrafine=32230

1 : Slett gammel data

(hvis du får problemer med dette så kan det hende denne funker: source /usr/lib/openfoam/openfoam2312/etc/bashrc )
* foamListTimes -rm
* rm -r postProcessing

2 : Finn navn på mesh som skal brukes
Du er her /GCI-3grid_simuleringer - gå til :
* skrivc: cd icoFoam-fine/caseDict
* skriv: ls caseDict (ser navnet på meshen i dette tilfelle: blockMeshDict_fine

3 : Aktiver riktig mesh for simuleringen
Gå tilbake til /GCI-3grid_simuleringer/icoFoam-fine
* cp caseDict/blockMeshDict_fine system/blockMeshDict

4 : Lag mesh og simmuler
* blockMesh (Hvis du vil være sikker på om du har riktig mesh aktivert kan du sjekke ncells (tabell over for hva some er riktig))
* icoFoam

5 : Repeat for de resterende 4 meshene.


