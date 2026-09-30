# Programmation système

# CM1 - Introduction


### Qu'est-ce qu'un système d'exploitation (SE) ?
- Interface pour relier le hardware aux applications utilisées par l'utilisateur sur une machine.

### Rôles d'un SE
- (Pour un utilisateur) Machine virtuelle - Pas besoin de connaître le hardware.
- (Pour le hardware) Gestion des ressources - Gestion spatio-temporelle

Donc 2 modes d'utilisation :
- Mode utilisateur
  - Certaines instructions du CPU interdites
  - Pas d'accès direct à la mémoire
  - Pas de crash du système (on prend un SIG kill)
- Mode Kernel
  - Toutes les instructions du CPU sont autorisées.
  - Accès direct à la mémoire
  - Les problèmes font crash la machine
- Mode switch pour passer d'un mode à l'autre. Entre l'user mode et le kernel mode, il y a plusieurs anneaux de protection (0, 1, 2, 3)

## Appels système
Appels fait des applications (mode utilisateur) au kernel (mode kernel)
Ils se font au travers d'une librairie intermédiaire (très fines) en C \
`printf, write, syscall` \
Et appellent des instructions : \
`open, close, read, write` \
Si on voulait ne pas passer par le C, il faudrait faire de l'assembleur !


Tips :
- `make` Pour compiler un fichier avec les règles par défaut.
- `strace -e write ./hello >dev/null` Pour afficher les appels systèmes produits.

