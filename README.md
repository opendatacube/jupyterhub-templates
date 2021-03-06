**This repository is no longer used. The JupyterHub templates for the DEA Sandbox are now maintained in [GeoscienceAustralia/dea-sandbox-templates](https://github.com/GeoscienceAustralia/dea-sandbox-templates).**

# JupyterHub Templates

This repository contains templates used for JupyterHub.
* `custom` contains customized templates

Note: By default, JupyterHub already has these files in `/usr/local/share/jupyterhub/templates`

# Customised Errors
The `custom/error.html` is extending https://github.com/jupyterhub/jupyterhub/blob/master/share/jupyterhub/templates/error.html

the Structure of the template is
```python
  {% block h1_error %}
  {% endblock h1_error %}

  {% block error_detail %}
  {% endblock error_detail %}
```
use `{{ super() }}` to inherit original message, or leave it out to completely override the `{% block %}`.

## 403

## 401
### template code snippet 
```python
{% elif status_code == 401 %}
{{ super() }}
<p>
    Please <a href="https://{{ domain_name }}/hub/logout">login</a> again!
</p>
```

### Sandbox error html render
```html
<div class="error">
  <h1>401 : Unauthorized</h1>
  <p> 
    Please <a href="https://sandbox.dev.dea.ga.gov.au/hub/logout">login</a> again!
  </p> 
  <p>
    Session is expired!
  </p>
</div>
```

## 400

## 500
