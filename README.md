# Configurer Matomo sous Nuxt3

## Installation 
```bash
npm install --save vue-matomo
```

## Configuration

Créez un fichier `plugins/matomo.client.ts`

```ts
import VueMatomo from 'vue-matomo'

export default defineNuxtPlugin(nuxtApp => {
    nuxtApp.vueApp.use(VueMatomo, {
		// Remplacez par votre url matomo
        host: 'https://matomo.votre-nom-de-domaine.fr',
		// Id du site
        siteId: 1,
       // Option permettant de suivre les changements de route
        router: nuxtApp.$router,
		// Option activant le suivi des liens sortants
        enableLinkTracking: true,
		// Défini si le suiivi Matomo necessite le consentement
        requireConsent: false,
		// Tracking première page
        trackInitialView: true,
		// Désactive les cookies
        disableCookies: true,
		// Desactive le consentement pour l'utilisation de cookies
        requireCookieConsent: false,
    })

})
```

Nuxt enregistre automatiquement les plugins qui sont situés à la racine du dossier `plugins`

Pour plus d'informations sur les paramètres rendez-vous sur : https://github.com/AmazingDreams/vue-matomo

