# OT-GAN : Amélioration des GANs par Transport Optimal

## Description
Ce projet implémente un réseau antagoniste génératif (GAN) amélioré par la théorie du transport optimal, appliqué à la génération d'images de chiffres manuscrits (MNIST). Cette approche permet de surmonter certaines limitations des GANs traditionnels, notamment en termes de stabilité de l'entraînement et de qualité des images générées.

## Auteurs
- Dan Allouche ([@DanAlloucheDM](https://github.com/DanAlloucheDM)) - Developer focused on data, AI, machine learning & automation
- Nicolas Dahan

## Fonctionnalités
- Génération d'images de chiffres manuscrits de haute qualité
- Implémentation de l'algorithme de Sinkhorn pour le transport optimal
- Architecture GAN améliorée basée sur les travaux de Salimans et al. (2018)
- Support d'accélération GPU pour l'entraînement

## Structure du projet
- `OT_GAN.ipynb` : Notebook Jupyter contenant l'implémentation complète
- `OT_GAN.pdf` : Documentation détaillée du projet
- `ot_gan_critic.pt` : Modèle pré-entraîné du critique
- `ot_gan_gen.pt` : Modèle pré-entraîné du générateur

## Prérequis
- Python 3.7+
- PyTorch
- TorchVision
- NumPy
- Matplotlib
- Pillow

## Installation
```bash
pip install torch torchvision numpy matplotlib pillow
```

## Utilisation
1. Clonez ce dépôt :
```bash
git clone git@github.com:DanAlloucheDM/OT-GAN.git
cd OT-GAN
```

2. Ouvrez le notebook Jupyter :
```bash
jupyter notebook OT_GAN.ipynb
```

3. Pour l'entraînement (environ 1 heure avec GPU) :
   - Exécutez toutes les cellules du notebook
   - Décommentez la section d'entraînement en supprimant les "#" devant `otgan = train(args, resume_training)`

4. Pour utiliser le modèle pré-entraîné :
   - Assurez-vous que les fichiers `ot_gan_critic.pt` et `ot_gan_gen.pt` sont dans le même répertoire
   - Exécutez la section de test pour générer des échantillons

## Architecture
Le projet comprend deux composants principaux :
- **Générateur** : Transforme un vecteur de bruit en images de chiffres manuscrits
- **Critique** : Évalue la qualité des images générées via une distance cosinus

La convergence est assurée par l'algorithme de Sinkhorn qui calcule les plans de transport optimal entre les distributions réelle et générée.

## Résultats
Les images générées présentent une grande diversité et une haute qualité, surpassant les résultats des GANs traditionnels sur le dataset MNIST.

## Référence
Salimans, T., Zhang, H., Radford, A., & Metaxas, D. (2018). Improving GANs using optimal transport.

## Licence
MIT

## Contact
Pour toute question concernant ce projet, n'hésitez pas à me contacter à [dan.allouche@deep-model.com](mailto:dan.allouche@deep-model.com) 