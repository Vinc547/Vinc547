- 👋 Hi, I’m @Vinc547
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Vinc547/Vinc547 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import random

# Dictionnaire contenant les logos des marques et leur nom
logos = {
    "Nike": "nike_logo.png",
    "Adidas": "adidas_logo.png",
    "Puma": "puma_logo.png",
    "Reebok": "reebok_logo.png",
    "Under Armour": "under_armour_logo.png"
}

# Liste contenant les noms de toutes les marques
marques = list(logos.keys())

def afficher_logo(marque):
    """Affiche le logo correspondant à la marque"""
    print("Devinez le logo de cette marque :")
    print(logos[marque])

def jouer():
    """Fonction principale du jeu"""
    marque_correcte = random.choice(marques)
    autres_marques = marques.copy()
    autres_marques.remove(marque_correcte)
    choix_possibles = random.sample(autres_marques, 3)
    choix_possibles.append(marque_correcte)
    random.shuffle(choix_possibles)

    afficher_logo(marque_correcte)
    print("Quelle marque correspond à ce logo ?")
    for i, marque in enumerate(choix_possibles):
        print(f"{i+1}. {marque}")

    reponse = input("Entrez le numéro de votre choix : ")
    if reponse.isdigit():
        choix_utilisateur = int(reponse)
        if 1 <= choix_utilisateur <= 4:
            if choix_possibles[choix_utilisateur - 1] == marque_correcte:
                print("Bravo, vous avez trouvé la bonne marque !")
            else:
                print("Désolé, ce n'est pas la bonne réponse.")
                print(f"La bonne réponse était : {marque_correcte}")
        else:
            print("Veuillez entrer un numéro valide.")
    else:
        print("Veuillez entrer un numéro.")

# Programme principal
if __name__ == "__main__":
    jouer()
