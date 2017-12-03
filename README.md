# Avant propos
Les Classes et interfaces de toute librairie 'axeldjaha' commencent toujours par AD (Axel Djaha).
# Description
Librairie pour gérer les permissions au cours de l'exécution d'une application. Plutôt utile pour les version d'android >= 6
# Gradle
compile 'axeldjaha.library:permission:1.0'
# Usage
Demander une permission à l'utilisateur est très simple:

        /**
         * On crée une instance de ADPermission,
         * on définit les permissions à demander ainsi que l'écouteur d'évènement
         * @param permissions tableau contenant les permissions à demander.
         *                    Chaque permission étant de la forme: Manifest.permission.NOM_DE_LA_PERMISSION
         *                    Exemple: String[] permissions = {Manifest.permission.SEND_SMS,...}         */
        ADPermission.newInstance(ExempleActivity.this)
                .setPermissions(permissions)
                .setListener(new ADPermissionListener() {
                    @Override
                    public void onPermissionGranted() {
                        //permission acceptée, faire qqch ici
                    }
                })
                .check();



