# Theme Manager Module

Provides a standard way for managing themes and theme configurations.  
Implements an admin UI with a theme selector for the [Admin Module](https://github.com/Platform-OS/pos-module-admin)

## Usage

Once you have the theme manager module installed in your application it'll provide a standard way for theme modules to register their theme configurations.  
It also uses the `hook_headscripts` hook from the Core module to register theme-specific scripts, styles and the theme configuration from the currently selected theme. 

You can select the active theme from the list of available themes on the admin UI at `/admin/themes`

## Hooks

Implements the `hook_admin_menu` hook provided by the admin module to show the "Themes" admin page.  
Implements the `hook_module_info` hook to register itself into the Module registry provided by the [Core Module](https://github.com/Platform-OS/pos-module-core).
Implements the `hook_permission` hook to use access control in the admin interface.
Implements the `hook_headscripts` hook to register theme-specific head scripts from the active theme.  

Provides the `hook_theme_variables` hook for theme modules so they can register their own theme config with the necessary design tokens (colors, sizes, fonts) and theme specific scripts / frontend assets. See: [/lib/queries/theme/get_variables.liquid](https://github.com/Platform-OS/pos-module-theme-manager/blob/master/public/views/partials/lib/queries/theme/get_variables.liquid#L2)
