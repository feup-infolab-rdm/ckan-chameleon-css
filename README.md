# CKAN Chameleon CSS
A easy way to create a custom CSS for [CKAN](http://ckan.org) in any color you like.

# Usage

## Monitoring the .styl file and compile automatically

- Install Stylus
```bash
brew install git &&
brew install node &&
brew install npm &&
npm install stylus -g &&
git clone https://github.com/feup-infolab-rdm/ckan-chameleon-css.git &&
cd ckan-chameleon-css &&
stylus -w css/
```
(brew is for the Mac, use apt-get on Linux)

- Edit the target_color value in constants.styl file for the color you want to be the main color 
```stylus
target_color=#8C2D19 //color of FEUP
```

- Stylus will compile the .styl into css
- Upload your css (chameleon.css, for example) into the css installation
  - Location folder is `/usr/lib/ckan/default/src/ckan/ckan/public/base/css`
  - You can also open the `test/Welcome - CKAN.html` file to preview how a home page of CKAN would look with your new CSS  ;-)
- Edit the admin.py file, adding an entry to your custom CSS 
  - Add this line
       ```python
       def _get_config_form_items(self):
       # Styles for use in the form.select() macro.
       styles = [{'text': 'Default', 'value': '/base/css/main.css'},
                 {'text': 'Red', 'value': '/base/css/red.css'},
                 {'text': 'Green', 'value': '/base/css/green.css'},
                 {'text': 'Maroon', 'value': '/base/css/maroon.css'},
                 {'text': 'Fuchsia', 'value': '/base/css/fuchsia.css'},                  
                 {'text': 'Your Custom Theme', 'value': '/base/css/chameleon.css'}] # <<<<<<<<<< NEW LINE
        ```
  
  - Located at `/usr/lib/ckan/default/src/ckan/ckan/controllers/admin.py`
- Select the custom CSS in the CKAN admin panel
- Reload and you are done!
