# CKAN Chameleon CSS
A easy way to create a custom CSS for [CKAN](http://ckan.org) in any color you like.

# Usage

## Monitoring the .styl file and compile automatically

- Install Stylus
```bash
brew install git
brew install node
brew install npm
npm install stylus -g
git clone https://github.com/feup-infolab-rdm/ckan-chameleon-css.git
cd ckan-chameleon-css
stylus -w css/
```
(brew is for the Mac, use apt-get on Linux)

- Edit the hue_rotate value in constants.styl file for the hue you want
```stylus
hue_rotate=101deg
```

- Stylus will compile the .styl into css
- Upload your css into the css installation
  - You can also open the `test/Welcome - CKAN.html` file to preview how a home page of CKAN would look with your new CSS  ;-)
- Edit the admin.py file, adding an entry to your custom CSS (or replace it with the one in this git repo
- Select the custom CSS in the CKAN admin panel
- Reload and you are done!
