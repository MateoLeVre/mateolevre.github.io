# Configuration du Formulaire de Contact

Ce site utilise Formspree pour gérer l'envoi des emails du formulaire de contact de manière sécurisée, sans exposer votre adresse email publiquement.

## Étapes de configuration

### 1. Créer un compte Formspree (Gratuit)

1. Allez sur [https://formspree.io](https://formspree.io)
2. Cliquez sur "Get Started" ou "Sign Up"
3. Créez un compte gratuit (vous pouvez utiliser votre compte GitHub)

### 2. Créer un nouveau formulaire

1. Une fois connecté, cliquez sur "+ New Form"
2. Donnez un nom à votre formulaire (ex: "Portfolio Contact Form")
3. Entrez votre adresse email (celle où vous recevrez les messages)
4. Cliquez sur "Create Form"

### 3. Récupérer l'ID du formulaire

Après avoir créé le formulaire, Formspree vous donnera un ID de formulaire qui ressemble à :
```
https://formspree.io/f/xwkgowyz
```

L'ID dans cet exemple est : `xwkgowyz`

### 4. Mettre à jour le fichier contact.html

1. Ouvrez le fichier `contact.html`
2. Recherchez la ligne suivante (environ ligne 539) :
   ```html
   <form id="contactForm" class="contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```
3. Remplacez `YOUR_FORM_ID` par votre ID Formspree :
   ```html
   <form id="contactForm" class="contact-form" action="https://formspree.io/f/xwkgowyz" method="POST">
   ```

### 5. Tester le formulaire

1. Enregistrez le fichier `contact.html`
2. Commitez et pushez les changements vers GitHub
3. Attendez quelques minutes que GitHub Pages se mette à jour
4. Visitez votre site et testez le formulaire de contact
5. Le premier envoi nécessitera une confirmation sur Formspree

## Fonctionnalités

Le formulaire de contact :
- ✅ Protège votre adresse email (elle n'apparaît pas dans le code source)
- ✅ Prévient le spam avec la protection intégrée de Formspree
- ✅ Supporte la traduction FR/EN
- ✅ Affiche des messages de succès/erreur
- ✅ Est entièrement responsive
- ✅ Plan gratuit : 50 soumissions/mois

## Alternatives à Formspree

Si vous préférez une autre solution, voici quelques alternatives :

1. **Web3Forms** - [https://web3forms.com](https://web3forms.com)
   - Gratuit, 250 soumissions/mois
   - Configuration similaire à Formspree

2. **EmailJS** - [https://www.emailjs.com](https://www.emailjs.com)
   - Gratuit, 200 emails/mois
   - Nécessite plus de configuration JavaScript

3. **Netlify Forms** - Si vous hébergez sur Netlify au lieu de GitHub Pages
   - Gratuit, 100 soumissions/mois

## Support

Si vous rencontrez des problèmes :
- Consultez la documentation Formspree : [https://help.formspree.io](https://help.formspree.io)
- Vérifiez que l'ID du formulaire est correct
- Assurez-vous que votre site est bien déployé sur GitHub Pages
