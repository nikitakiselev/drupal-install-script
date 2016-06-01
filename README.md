# Drupal 7 installation with drush

```
drush dl drupal-7.x --drupal-project-rename=drupalsite
cd drupalsite

drush site-install standard --account-name=admin --account-pass=admin --db-url=mysql://root:password@localhost/[database]

drush dl drush_language, admin_menu, adminimal_admin_menu, devel, fancybox, token, ctools, jquery_update, l10n_update, module_filter, pathauto,views, ckeditor, insert, transliteration -y

git clone https://github.com/fancyapps/fancyBox.git sites/all/libraries/fancybox

drush en admin_menu, devel, fancybox, token, ctools, jquery_update, l10n_update, module_filter, pathauto, views, ckeditor, contact, field_ui, file, list, menu, number, syslog, admin_menu_toolbar, adminimal_admin_menu, views_ui, insert, transliteration -y

drush dis color, dashboard, shortcut, toolbar, overlay -y

drush language-add ru
drush language-default ru
drush l10n-update-refresh && drush l10n-update

drush dl professional_theme -y
drush en professional_theme -y

drush vset theme_default professional_theme

drush cc all

rm install* INSTALL* LICENSE.txt MAINTAINERS.txt README.txt CHANGELOG.txt COPYRIGHT.txt UPGRADE.txt
```
