# Avant propos
Les Classes et interfaces de toute librairie 'axeldjaha' commencent toujours par AD, qui signifie Axel Djaha (l'auteur).
# permissionlibrary
Librairie pour gérer les permissions au cours de l'exécution d'une application. Plutôt utile pour les version d'android >= 6
# Gradle
compile 'axeldjaha.library:permission:1.0'
# Usage
Demander une permission à l'utilisateur est très simple:

        /**
         * Demander des permissions utiles pour exécuter une action.
         * Toutes les permissions doivent être déclarées dans le manifest avant d'appeler cette méthode.
         * Les demandes de permissions sont obligatoires pour les versions d'Android >= 6.
         *
         * @param activity instance d'une activité
         * @param permissions tableau contenant les permissions à demander, chaque permission étant de la forme: 
         *                    Manifest.permission.NOM_DE_LA_PERMISSION
         * @param permissionListener écouteur d'évènement (callback) permettant de savoir si les permissions ont
         *                           été acceptées ou pas par l'utilisateur. Instance de ADPermissionListener
         */
        ADPermission.check(activity, permissions, new ADPermissionListener() {
            @Override
            public void onPermissionGranted() {
                //permission acceptée, faire qqch ici
            }

            @Override
            public void onPermissionDenied() {
                //permission refusée, faire qqch ici
                Toast.makeText(activity, "Acceptez les autorisations pour continuer", Toast.LENGTH_SHORT).show();
            }
        });

