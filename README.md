# Django Application with bundle rendering for Vue.js + Vuetify

Demo of a Django app using Webpack Bundle Tracker to create entry points for a Vue.js + Vuetify application.

# Getting Started

## Prerequisites

Python  
Npm

## Installing

Install Python dependencies with

```
pip install -r requirements.txt
```

Change directory to \`vue\` folder

Install Javascript dependencies with

```
npm install
```

## Deployment

In the \`vue\` folder, run

```
npm run build
```

This will create a file called webpack-stat.json which provides mapping between entry points in the webpack config and the called bundle in Django templates.

Example:

- In home.html, a Django template, is

```
  <div id="app"></div>
  {% render_bundle 'main' %}
```

- It will render bundle 'main', where 'main' is a defined entry point in the webpack config that points to \`main.js\`
- The webpack-stat.json will keep the mapping of these files after processing Babel transformations and such

Change back to root and run

```
python manage.py runserver
```

Your server should be running on [127.0.0.1:8000](http://127.0.0.1:8000).  
If you open it you should see 'hello'.

## Built With

- [Django](https://www.djangoproject.com/) - Python Web Framework
- [Webpack Bundle Tracker](https://github.com/owais/webpack-bundle-tracker) - "Spits out some stats about webpack compilation process to a file."
- [Vue Loader](https://vue-loader.vuejs.org/) - allows loading Single-File Components
- [Vuetify](https://vuetifyjs.com/en/) - Vue UI component library

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
