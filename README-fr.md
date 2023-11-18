<h1 align="center">Honeygain Pot</h1>
<h4 align="center">🐝Un bot qui réclame le Honeygain pot chaque jour🍯</h4>
<h4 align="center">Propulsé par GitHub Actions et Python</h4>
<p align="center">
<img alt="Statut du déclencheur quotidien" src="https://github.com/gorouflex/HoneygainPot/actions/workflows/daily.yml/badge.svg">
<img alt="Statut du déclencheur manuel" src="https://github.com/gorouflex/HoneygainPot/actions/workflows/manual.yml/badge.svg"> (*)
<p align="center">
  <a href="https://github.com/gorouflex/HoneygainPot/">English 🇺🇸</a>
  •
  <a href="README-vn.md">Tiếng Việt 🇻🇳</a>
  •
  <a href="README-fr.md">Français 🇫🇷</a>
<p align="center">
  <a href="Debug.md">Débogage</a>     
  •
  <a href="#fonctionnalités">Fonctionnalités</a>
  •
  <a href="#utilisation">Utilisation</a>     
</p>
 <p align="left">
   
<img src="Img/Logo.png"               
     width="170" 
     height="170"></p>
    
> [!NOTE]
> English: This is not a 100% accurate translation for French
> - Mettez toujours à jour votre repo en suivant le repo original pour obtenir les dernières mises à jour + corrections de bugs, je ne prendrai pas en charge quoi que ce soit si votre repo est obsolète.
> - Si vous rencontrez des erreurs lors de l'utilisation de GitHub Actions, veuillez vous référer à cette [section de débogage](Debug.md)
> - (*): Ne pas fork ce repo si deux de ces (pas seulement 1) badges de statut GitHub Actions montrent un échec, et attendez jusqu'à ce que 1 de ceux-ci ou deux de ceux-ci montrent un succès, puis vous pouvez fork à nouveau
> - Les workflows de 'Réclamation quotidienne' s'exécutent toujours à 14:00 UTC +0, si vous voulez le changer, référez-vous à [ceci](https://github.com/gorouflex/HoneygainPot#how-to-change-the-schedule-to-fit-with-my-timezone-before-the-pot-is-reset)
> <img src="https://i.imgur.com/htGeFlY.jpg">
  
# Fonctionnalités

- Réclamez le Honeygain pot et les récompenses des réalisations tous les jours avec GitHub Actions 🔥
- Vérification de votre solde actuel

# Utilisation

  1. [Faites un fork de ce dépôt](https://github.com/gorouflex/HoneygainPot/fork)
  2. Accédez à votre dépôt forké
  3. Allez dans Paramètres > Secrets et Variables > Actions. Et cliquez sur le bouton `Nouveau secret de dépôt`
  4. Pour le nom secret, utilisez `MAIL_JWD` pour définir votre mail Honeygain et `PASS_JWD` pour votre mot de passe
  5. Accédez à votre dépôt forké et allez dans l'onglet Actions, puis appuyez sur le bouton `Je comprends mes workflows, activez-les`

![GitSettings](https://github.com/gorouflex/HoneygainPot/assets/98001973/d8d33621-5717-488d-9a80-6db395c8ac9d)

## Comment changer l'horaire pour correspondre à mon fuseau horaire avant la réinitialisation du pot ?

> [!IMPORTANT]
Chemin du fichier des workflows quotidiens (par défaut à 14:00 UTC +0) : `.github/workflows/daily.yml`

Eh bien, GitHub utilise l'heure UTC (UTC +0) pour planifier les workflows, donc nous devrions la convertir à notre fuseau horaire.

Par exemple : Si je veux définir le déclencheur quotidien pour se déclencher à 21:00 (UTC +7), je dois le définir à 14:00 (format 24 heures) (UTC±0) (2+7=9).
```
name: Daily claim
on:
  schedule:
    - cron: '0 14 * * *' # <- UTC Time, replace 0 14
```

Ainsi, si je veux que le déclencheur quotidien s'exécute à 5:00 (UTC +7), je dois le définir à 22:00 (UTC±0) (utilisez le format 24 heures) :
```
name: Daily claim
on:
  schedule:
    - cron: '0 22 * * *' # UTC Time
```


> [!NOTE]
> Les horaires des déclencheurs GitHub Actions peuvent parfois être retardés de jusqu'à 15 minutes en raison d'une forte demande, donc ne vous inquiétez pas !

## Remerciements
- [MrLolf](https://github.com/MrLoLf/) pour [HoneygainAutoClaim](https://github.com/MrLoLf/HoneygainAutoClaim)
- [rfoal](https://github.com/rfoel/) x [duolingo](https://github.com/rfoel/duolingo) pour l'idée
