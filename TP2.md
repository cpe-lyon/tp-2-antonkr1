# TP 2 Bash
## _Exercice 1. Variables d'environnement_
1 - Les commandes tapées par l'utilisateur se retrouvent dans les fichiers affichés par la variable d'environnement PATH (printevn PATH)  
2 - cd~ permet de retourner dans son repertoir personnel   
3 - LANG sert à determiner la langue du système, PWD permet de determiner le type du fichier dans lequel on se trouve, OLDPWD fait la même chose que PWD mais avec le dernier dossier dans lequel on se trouvait. printenv SHELL  
4 - Création de variable MY_VAR="abc" puis printenv MY_VAR pour afficher son contenu et s'assurer qu'elle existe.  
5 - Après execution de la commande bash la variable n'existe plus étant donné que ce n'était pas une variable permanent mais temporaire.  
6 -     
7 - L'affectation est correct   
8 - On fait un echo Bonjour à vous, $NOM! sans ' '  
9 - Je n'ai appercu aucune différence entre les deux.  
10 - Il suffit de faire echo $HOME = $PATH  
. = dossier courant / .. = dossier parent / ~ = /home/(home de l'utilisateur)
 ## _Exercice 2. Contrôle de mot de passe_
  #!/bin/bash

read -s -p 'Saisissez votre mot de passe :' pswd

if [ $PASSWORD = $pswd ]; then
        echo 'Mot de passe correct'
else
        echo 'Mot de passe incorrect'
fi

 ## _Exercice 3. Expressions rationnelles_
 
 #!/bin/bash

function is_number()
{
    re='^[+-]?[0-9]+([.][0-9]+)?$'
      if ! [[ $1 =~ $re ]] ; then
                return 1
        else
                return 0
        fi
}

is_number $1

if [ $? -eq 0 ]; then

 echo "ce nombre est un nombre réel"

else
 echo "ce nombre n'est pas un nombre réel"
fi
 ## _Exercice 4. Contrôle d'utilisateur_
 
#!/bin/bash

if [ -z $1 ] ; then

echo "Utilisation :"$0 "nom_utilisateur"

elif  [ $USER =  $1 ] ; then

echo 'Cet utilisateur existe'

else

echo "Cet utilisateur n'existe pas"

fi

## _Exercice 5. Factorielle_

#!/bin/bash

counter=$1

i=1
while [ $counter -gt 0 ]
do
   i=$(( $i * $counter ))
   counter=$(( $counter - 1 ))
done

echo $i





