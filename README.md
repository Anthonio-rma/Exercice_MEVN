# Exercice_MEVN

# Exercice 1 – Déclaration et manipulation des objets 
Travail demandé: 
1. Afficher le nom de tous les étudiants

const etudiants = [
 { id: 1, nom: "Rakoto", filiere: "GL", moyenne: 12 },
 { id: 2, nom: "Rabe", filiere: "IG", moyenne: 9 }
];

etudiants.forEach(etudiant => {
  console.log(etudiant.nom);
});

2. Utiliser la destructuration pour extraire nom et moyenne

const etudiants = [
 { id: 1, nom: "Rakoto", filiere: "GL", moyenne: 12 },
 { id: 2, nom: "Rabe", filiere: "IG", moyenne: 9 }
];

etudiants.forEach(({ nom, moyenne }) => {
  console.log("Nom :", nom, "- Moyenne :", moyenne);
});


# Exercice 2 – Manipulation des tableaux (map, filter) 
const etudiants = [
 { id: 1, nom: "Rakoto", filiere: "GL", moyenne: 12 },
 { id: 2, nom: "Rabe", filiere: "IG", moyenne: 9 }
];

// 1. filter() → étudiants ayant une moyenne ≥ 10
const admis = etudiants.filter(e => e.moyenne >= 10);
console.log("Étudiants admis :", admis);

// 2. map() → tableau contenant uniquement les noms
const noms = etudiants.map(e => e.nom);
console.log("Noms des étudiants :", noms);

// 3. Ajouter 1 point à toutes les moyennes (sans modifier l’original)
const nouvellesMoyennes = etudiants.map(e => ({
  ...e,
  moyenne: e.moyenne + 1
}));

console.log("Nouvelles moyennes :", nouvellesMoyennes);
console.log("Tableau original inchangé :", etudiants);


# Exercice 3 – Fonctions fléchées et template literals 
const etudiant = { id: 1, nom: "Rakoto", filiere: "GL", moyenne: 12 };

// 1. Fonction fléchée
const afficherEtudiant = (etudiant) => {
  // 2. Template literal pour afficher le message
  console.log(`L’étudiant ${etudiant.nom} de la filière ${etudiant.filiere} a une moyenne de ${etudiant.moyenne}`);
};

// Appel de la fonction
afficherEtudiant(etudiant);


# Exercice 4 – Programmation asynchrone (async / await)
const etudiants = [
 { id: 1, nom: "Rakoto", filiere: "GL", moyenne: 12 },
 { id: 2, nom: "Rabe", filiere: "IG", moyenne: 9 }
];

// Simulation d'un appel API
function chargerEtudiants() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      // Ici, on peut simuler une erreur avec reject("Erreur de chargement !");
      resolve(etudiants);
    }, 2000);
  });
}

// 1. Fonction async pour récupérer les étudiants
const afficherEtudiants = async () => {
  try {
    // 2. Récupérer les étudiants avec await
    const liste = await chargerEtudiants();
    
    // 3. Afficher la liste après le chargement
    console.log("Liste des étudiants :", liste);
  } catch (error) {
    // 4. Gérer les erreurs
    console.error("Erreur lors du chargement :", error);
  }
};

// Appel de la fonction
afficherEtudiants();


# Exercice 5 –
const etudiants = [
  { id: 1, nom: "Rakoto", filiere: "GL", moyenne: 12 },
  { id: 2, nom: "Rabe", filiere: "IG", moyenne: 9 }
];

// 1️ Calcul de la somme des moyennes avec reduce
const sommeMoyennes = etudiants.reduce((acc, etudiant) => acc + etudiant.moyenne, 0);

// 2️ Calcul de la moyenne générale
const moyenneGenerale = sommeMoyennes / etudiants.length;

// 3️ Affichage du résultat
console.log(`La moyenne générale de la classe est : ${moyenneGenerale}`);



